---
title: Assignment 3
layout: doc
---

# A3

## TrueTide

**TrueTide** is designed for _international students_ navigating new environments and cultures. Adjusting to life in a new country can be overwhelming, and students often struggle to find _accurate, culturally relevant_ information. **TrueTide** helps bridge that gap by providing a _diverse_ range of perspectives on everything from national policies to local slang and customs.

The app's key feature is its **DualView**, which allows users to see opposing viewpoints on controversial topics, fostering critical thinking.
To support responsible information-sharing, **TrueTide** offers _easy-to-use_ fact-checking tools and recommends relevant **citations** to users as they post content, making it simple to back up information. Additionally, the app uses a _community-driven_ **review** system that helps users verify the credibility of content, encouraging accountability and collaboration. With features like **customized feeds** that adapt to cultural contexts, **TrueTide** offers a trusted and culturally aware platform, easing the transition for students as they learn more about their new surroundings.

## Functional design

### Concepts

#### 1

**Name:** Authentication  
**Purpose:** Users are able to log in to get personalized content and to interact with others  
**Operational principle:** After registering with a username and password, the user can log in using their credentials  
**State:**  
used: **set** String  
userInfo: `used` -> **one** `<String, Boolean>`  
**Actions:**  
`register` (name, pass: String, out user: User) -- create new user.  
`authenticate` (name, pass: String, out user: User) -- authenticate the user if correct pair is given.

#### 2

**Name:** Sessioning  
**Purpose:** Keep users logged in so they do not have to do it all the time
**Operational principle:** Once a user is logged in, the user remains logged in until the session is manually ended  
**State:**  
`sessions`: `s` Session -> **one** `user` User  
**Actions:**  
`startSession(user: User, out s: Session)` -- Begins a session for the user.  
`getUser (s: Session, out user: User)` -- give the user given the session.  
`endSession(s: Session)` -- Ends the session.

<!-- (could be initiated by some criteria like last activity and whether user is trying to access sensitive information) -->

#### 3

**Name:** Posting  
**Purpose:** Users share experinces and information with others about new locations, potential cultural differences, etc.
**Operational principle:** User records content and labels it. The content can be recommended to other users.  
**State:**  
`ContentLabel`: `Content` -> set String (tags for the content)  
**Actions:**  
`upload(input: Media, out item: Content)` -- Creates new content from user input. (also will make integration testing way simpler)
`addLabel(item: Content, labels: set String)` -- add labels to the content (possibly location, general topic, etc.).  
`share(item: Content, out url: URL)` — Shares content and generates a URL to view the content. (may remove)

(international students learn more about their country)

#### 4

**Name:** Citing  
**Purpose:** Encourages verification of facts, promoting responsible knowledge-sharing through citations (similar to wikipedia) and easy way for other users to fact-check.  
**Operational principle:** Users receive recommended citation sources for their content and can either accept or add their own. Viewers of the content can see and access these citations.  
**State:**  
`Citations`: `Content` -> set String  
**Actions:**  
`getCitations(item: Content, out citations: set Strings)` -- Suggests citation sources for a piece of content.  
`addCitations(item: Content, citations: set Strings)` -- Adds citations to content.  
`openCitation(citation: String)` -- opens a citation link in the webapp.

(making easy to comfirm information, foster analytical thinking and getting used to citing - not a videly-pratcices thing everywhere. Hopefully, will develop a habit of cross-checking information, a crucial skill in diverse cultural environments)

#### 5

**Name:** Feed  
**Purpose:** Get personalized stream of content suggestions to view  
**Operational principle:** When user opens the app, some content gets suggested based on user preferences (determined by user input)  
**State:**  
`allContent`: `content` Content
`contentLabels`: `content` Content -> `labels` set String  
`contentViewers`: `content` Content -> `User` set String
**Actions:**  
`refresh(preferences: set String, out content: set Content)` -- suggest content based on preferences

#### 6

**Name:** Crowd Review  
**Purpose:** Crowd-source fact-checking, support responsible knowledge-sharing, and limit bad behavior.  
**Operational principle:** User reports an item, and that item's score changes leading to the item potentially getting a prize.  
**State:**  
`flagged`: `item` -> set User  
`confirmed`: `item` -> set User  
`CredibiltyScores`: `item` Item -> **one** Number  
**Actions:**  
`flag(item: Item, comment: String, rating: Number, user: User, out score: Number)` -- Flag an item (if not reported previously by the user). Scoring of item based on report (rating and item's label) is updated and returned.  
`confirm(item: Item, user: User, out score: Number)` -- validate accuracy of an item (if not reported previously by the user ). Scoring of item based on validation is updated and returned.  
`showScore(item: Item, out score: Number)` -- show the credibility score for the Item.  
`system reward(item: Item, out rewardthing: Thing)` -- Rewards item for high score.
`system isControversial(item: Item, out controversial: Boolean)` -- checks whether item is controversial by comparing number of users it was reported and confirmed by.

(Foster analytical thinking, as a lot of times international students blindly believe a lot of things because is west viewed as "smarter")

#### 7

**Name**: DualView  
**Purpose**: Foster critical thinking by allowing users to view opposing perspectives on controversial topics  
**Operational Principle**: When a user searches for or views a potentially polarizing subject, the app shows two types of content with contrasting views, displayed next to each other.  
**Actions**:  
`getNext(currentContent: Item, out nextContent: Item)` --> Get related content with an opposing view to the `currentContent`
`system getOpposite(label: String, out oppositeLabel: String)` --> Finds the opposite label or perspective for the label.

(important to get different views especially in countries that are more polarized)

**NOTE:** I think these concepts are especially helpful if you think about content in terms of controversial and not controversial. Not controversial topics need more fact checking, so citing, reporting and credibility tracking helps with misinformation in that type of content. On the other hand, with more controversial topics just credibility score and citation from one-sided source does not give full picture, and not getting a different perspective on that type of content can be considered as not having full information (i.e. misiformation).

### Synchronizations

```
app TrueTide
  include Authenticating
  include Sessioning [Authenticating.User]
  include Posting[Authenticating.User]
  include Citing [Posting.Content] (can be comment in the future)
  include Feed [Authenticating.User, Posting.Content]
  include CrowdReview [Authenticating.User, Posting.Content]
  include DualView[Posting.Content] (can be comment in the future)

  sync register (username, password: String, out user: User)
    Authenticating.register (username, password, user)

  sync login (username, password: String, out content: set Content)
    user = Authenticating.authenticate (username, password)
    Sessioning.start (user, session)
    this.getFeed(user) # preferences may be stored in sessions

  sync authenticate (session: Session, out user: User)
    Sessioning.getUser (session, user)

  sync logout (session: Session)
    Sessioning.end (session)

  sync post(user: User, input: Media, labels: set String, out item: Content)
    content = Posting.upload(input)
    citations = Citing.getCitations(content)
    Citing.addCitations(content, citations)
    Posting.addLabel(content, labels)

  sync getFeed(user: User, out content: set Content)
    Feed.refresh(User.preferences) # get preferences from user input and/or current session

  # probably called due to `feed giving content and user clicking on content`
  sync viewContent(user: User, content: Content, out content: Content)
    if (not CrowdReview.isControversial(content))
      CrowdReview.showScore(content)

  sync viewNext(user: User, content: Content, out content: Content)
    DualView.getNext(content) # possibly do get feed if content is completely non-controversial
    if (not CrowdReview.isControversial(content))
      CrowdReview.showScore(content)

  sync notify(content: Cotent, out message: String)
    if CrowdReview.showScore(content) < treshold
      # involve some experts in the future and different notifications based on severity of misinformation
      someMessage = "The content has low credibility score. Please double-check the information"
      for user in Feed.contentViewers.content
        user.notify(someMessage)
```

(look at the wireframe to learn a bit more on how it may end up looking)  
There are more that can be added but it's hard to explain without user interaction (because users affect each other and each other's content through the concepts above - and sometimes after multiple iterations (also adding everything would probably mean I have an almost working code :sweat_smile:))

<!--  If a post receives a low credibility score, users could be prompted to either review the citations or add more sources to strengthen the content -->

### Dependency diagram

![dependecy diagram](/../assets/images/a3/Dependency-diagram.png)

## Wireframes

<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://embed.figma.com/design/SIYbJMj5eDb9jAKb6YFZE8/TrueTide---A3---Jennet-Zamanova?node-id=0-1&embed-host=share" allowfullscreen></iframe>

## Design tradeoffs

### 1. Notifying Users About Low Credibility Content

Options: (1) Notify users to do their own research when content has low credibility, (2) involve an expert panel for validation, or (3) outright mark the content as false.
Rationale: Involving an expert panel is resource-intensive and time-consuming, while outright marking content as false could create backlash, especially for controversial topics. The middle-ground solution—encouraging users to research further—allows the platform to maintain neutrality while promoting critical thinking.

### 2. Credibility Scores for Controversial Content

Options: (1) Apply credibility scores to all content equally, (2) exclude controversial content from scoring, or (3) use a “controversial” tag with the scores for polarizing issues.
Rationale: Credibility scores are less effective for polarizing content, as one-sided perspectives may dominate, skewing the score or both sides keep confirming and reporting the content giving weird score as a result. "Controversial" tag would signal to users that the content requires a nuanced view. This avoids oversimplification and fosters critical engagement with the material. The score can still be useful, especially if users do not exploit the reporting system to get rid of controversial topic, and use only for reporting of factual misinformation.

### 3. Sharing Location and Cultural Background

Options: (1) Require specific location and cultural details, (2) make this information optional but specific, or (3) allow for generic, high-level descriptors.
Rationale: To avoid recommending culturally inappropriate or irrelevant content, need to consider how location and background information could inform recommendations. However, many users are uncomfortable sharing personal details (Location and Cultural Background), as am I. So instead keep the options generic while also emphasizing its purpose to the users: to foster cross-cultural understanding and ensure that the feed is aware of cultural differences and provides relevant, culturally sensitive content. This approach balances privacy concerns with the need for cultural sensitivity in content recommendations, ensuring that the feed adapts to diverse user backgrounds without being intrusive.

Additional notes: for 2) no comments in the app so far either because it can lead to rage-bate and harassment when it comes to Dual View, so some expriments, psychology research, and user testing may be required. For 3) It's already challenging to adjust to a completely different country, so the last thing we want is for a social media app to make that experience harder.
