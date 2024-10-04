---
title: Assignment 4
layout: doc
---

# A4

## TrueTide

**TrueTide** is designed for _`international students`_ navigating new environments and cultures. Adjusting to life in a new country can be overwhelming, and students often struggle to find _`accurate`, `culturally relevant`_ information. **TrueTide** helps bridge that gap by providing a _`diverse`_ range of perspectives on controversial topics from national policies to local slang and customs.

The app's key feature is its **`DualView`**, which allows users to see opposing viewpoints on controversial topics, fostering critical thinking.
To support responsible information-sharing, **TrueTide** offers _`easy-to-use`_ fact-checking tools and recommends relevant **`Citations`** to users as they post content, making it simple to back up information. **With features like _customized_ **`Feeds`** that adapt to cultural contexts, ????** **TrueTide** offers a trusted and culturally aware platform, easing the transition for students as they learn more about their new surroundings.

[TrueTide repo](https://github.com/jennet-zamanova/truetide)

[TrueTide deployment](https://truetide.vercel.app/)

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
`register` (name, pass: String, out user: User) — create new user.  
`authenticate` (name, pass: String, out user: User) — authenticate the user if correct pair is given.

#### 2

**Name:** Sessioning  
**Purpose:** Keep users logged in so they do not have to do it all the time
**Operational principle:** Once a user is logged in, the user remains logged in until the session is manually ended  
**State:**  
`sessions`: `s` Session -> **one** `user` User  
**Actions:**  
`startSession(user: User, out s: Session)` — Begins a session for the user.  
`getUser (s: Session, out user: User)` — give the user given the session.  
`endSession(s: Session)` — Ends the session.

<!-- (could be initiated by some criteria like last activity and whether user is trying to access sensitive information) -->

#### 3

**Name:** Posting  
**Purpose:** Users share experinces and information with others about new locations, potential cultural differences, etc.
**Operational principle:** User records content and labels it. The content can be recommended to other users.  
**State:**
`allContents` -> set Content
**Actions:**  
`upload(input: Media, out item: Content)` — Creates new content from user input. (also will make integration testing way simpler)
`getText(item: Content, out text: String)` — Get text out of the content
(international students learn more about their country)

#### 4

**Name:** Labeling[Item]
**Purpose:** Tag items to easily tell what topic it belongs to
**Operational Principle:** Someone tags an item, other users can see the tag
`tags`: Item -> tags set String
`topics`: topic String -> tags set String
**Actions:**
`addTags(item: Item, tags: set String, out topics: set String)` — adds tags to the item
`getIteamsWithTag(tag: String, out items: set Item)` — return all items with given tag
`getTagsForItem(item: Item, out tags: set String)` — return all tags for the given item
`getAllTags(out tags: set String)` — return all tags

`getNext(currentItem: Item, out nextItem: Item)` — Get related item with an opposing view to the `currentItem`

<!-- `system addOpposite(item: Item, opposingItem: set Item)` — Updates the opposingItem state -->

`system getOppositeTag(tag: String, out oppositeTags: set String)` — Finds the opposite tags or perspectives for the tag.  
`system addTag(tag: String, out [rating: Number, topic: String])` — add the tag to topics and assign rating to both (NLP) (if exists already just return rating)

#### 5

**Name:** Citing  
**Purpose:** Encourages verification of facts, promoting responsible knowledge-sharing through citations (similar to wikipedia) and easy way for other users to fact-check.  
**Operational principle:** Users receive recommended citation sources for their content and can either accept or add their own. Viewers of the content can see and access these citations.  
**State:**  
`Citations`: `Content` -> set String  
**Actions:**  
`getCitations(text: String, out citations: set Strings)` — Suggests citation sources for a piece of content.  
`addCitations(item: Content, citations: set Strings)` — Adds citations to content.  
`openCitation(citation: String)` — opens a citation link in the webapp.

(making easy to comfirm information, foster analytical thinking and getting used to citing - not a videly-pratcices thing everywhere. Hopefully, will develop a habit of cross-checking information, a crucial skill in diverse cultural environments)

**Note:** not worried as much about scoping because as part of proof concept can convert mp4 to mp3 to get only audio, then do speech-to-text to get only text, and then use an LLM to get resources supporting the information: [chatgpt conversation to demo last step: can see which sites were searched by the model](https://chatgpt.com/share/66f6ce97-c2ac-8000-942e-96606dd50447). Assuming for POC we don't need a perfect prompt and model can be improved in the future.

<!-- Do we need this concept if labeling can return all we need? -->

#### 6

**Name:** Feed  
**Purpose:** Get personalized stream of content suggestions to view  
**Operational principle:** When user opens the app, some content gets suggested based on user preferences (determined by user input)  
**State:**  
`allContent`: `content` Content

<!-- `contentLabels`: `content` Content -> `labels` set String
`contentViewers`: `content` Content -> `User` set String   -->

**Actions:**  
`getNextContent(currentContent: Content, )`

`refresh(preferences: set String, out content: set Content)` — suggest content based on preferences

<!-- #### 7

**Name**: DualView[Item]
**Purpose**: Foster critical thinking by allowing users to view opposing perspectives on controversial topics
**Operational Principle**: When a user searches for or views a potentially polarizing subject, the app shows two types of content with contrasting views, displayed next to each other.
**State:**
`controversialRating`: `topic` String -> `rating` Number
`tagsForTopic`: `topic` String -> `tags, spectrumRating` set [String, Number]
`opposingItem`: `item` Item -> contents set Item
**Actions**:
`getNext(currentItem: Item, out nextItem: Item)` — Get related item with an opposing view to the `currentItem`
`system addOpposite(item: Item, opposingItem: set Item)` — Updates the opposingItem state
`system getOppositeTag(tag: String, out oppositeTags: set String)` — Finds the opposite tags or perspectives for the tag.
`system addTag(tag: String, out [controversialRating: Number, topic: String])` — add the tag to topics and assign rating to both (NLP) (if exists already just return rating) -->

<!-- #### 7

**Name**: ControverialTopic[]
**Purpose**:
**Operational Principle**:
**State:**
`controversialRating`: `topic` String -> `rating` Number
`tagsForTopic`: `topic` String -> `tags, spectrumRating` set [String, Number]
**Actions**:
`system getOppositeTag(topic: String, tag: String, out oppositeTags: set String)` — Finds the opposite tags in relation to the topic
`system addTag(tag: String, out [controversialRating: Number, topic: String])` — add the tag to topics and assign rating to both (NLP) (if exists already just return rating)

#### 7

**Name**: PairedItems[Item]
**Purpose**: Pair content and users to be view together
**Operational Principle**: When a user views one of the items, on a swipe the other item will be shown
**State:**
`pairedItem`: `item` Item -> contents set Item
**Actions**:
`getNext(currentItem: Item, out nextItem: Item)` — Get related random paired item
`system addPair(item: Item, pairedItem: set Item)` — Updates the pairedItem state -->

## Data Modeling

**concept: Authentication**  
purpose: log in/register a user  
state:  
username: User -> one String  
password: User -> one String

**concept: Sessioning[User]**  
purpose: enable authenticated actions for an extended period of time  
state:  
session: Session -> one User

**concept: Postings[Author, File]**  
purpose: share experiences and information  
state:  
author: Post -> one Author  
file: Post -> one File

**concept: Labeling[Item]**  
purpose: tag items  
state:  
tags: Item -> (tag) set String  
topics: (topic) String -> (tag) set String

**concept: Citing[Item]**  
purpose: get sources to support `Item`  
state:  
citations: Content -> set String

**concept: DualView[Item]**  
purpose: handle items with opposing views  
state:  
controversialRating: (topic) String -> (rating) Number  
tagsForTopic: (topic) String -> (tags, spectrumRating) set [String, Number]  
opposingItem: (item) Item -> (contents) set Item

<iframe frameborder="0" style="width:100%;height:1528px;" src="https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=test.drawio#R%3Cmxfile%3E%3Cdiagram%20id%3D%226a731a19-8d31-9384-78a2-239565b7b9f0%22%20name%3D%22Page-1%22%3E7V1bd5u4Fv4tffBjutBdPMZpM3PWac%2FqmnZWZx6JrThMifHCuEnm1x9hCwzawsVEEDttH2aCbAv49qd905Y0IVf3j79l0eruYzpXyQQH88cJeTfBmLAg0P8rWp52LUgysWtZZPHctO0bPsf%2FKtNofrjYxHO1bnwxT9Mkj1fNxlm6XKpZ3miLsix9aH7tNk2ad11FCwUaPs%2BiBLZ%2Bjef5nWlFPNx%2F8LuKF3fm1hKb97uJZt8WWbpZmvst06XafXIfld2Yd1zfRfP0odZE3k%2FIVZam%2Be6v%2B8crlRS4lojtfnfd8mn1yJla5l1%2BsJpeiseUx79NP35d%2FvXfT39%2B%2B2N9gZjAu46%2BR8nGoGGeN38q4dm%2BoCr6CSZk%2BnAX5%2BrzKpoVnz5oRui2u%2Fw%2B0VdI%2F3kbJ8lVmqSZvt7CQabrPEu%2FqbJxggmfSXVzW31SYo6K35vHUVmuHltfFVUAalKq9F7l2ZP%2BivkBZfwt2%2F2oZGQphYe9eFnJvruaZCkzjZGh1KLqfY%2Bt%2FsPAexzU5AWgDrkgER8MahQGDaA5g0Bz6gI68AA0IuXtapj%2BuVYZwFX%2FTisT9WNMq2Fa4H%2BbLvPr6D5Oirf7XSXfVR7PIvOBUWO4%2FGIN9OvtP90eJfFiqdtmGk79VLYUiCVE%2FVOtc8Jte1OSRrwt4nEIsVViQvKGxIiAEquGS11iVeMzJYaAxD6r9TpOl%2BcrtOtAioC1CW2RRfNY7e%2FlT5YIc1vTEccAHFScFIjzS7qKZ%2BcrTKHNUyQHHIGIyqbSFMHIMmNQaf7x4Xwldnj4%2BZBYEEKPgo4sNA6E9iG6KTzxcxXbe8k4xUOausCSGcGoFONYUguhfJbzyyJmsZ22EikOEKm7BTX5tSK0TjfZrAxtGDJvnEfZQuXVg5nXU%2FNGaASxzFQS5fH3ZqT0PFB44AeU23LcewMFvSAoxA8o2nxdXUp%2FoDDEXxAU6g2UnU33xhT6gqBA8w1R0s%2F12VwamHoBd913iLXFwKETTdYRzVLtS9RQ7DrGdOn1wKXXD8Wd5oaf0li%2FWXU3QoRl%2FGsJhrKb3bubX9bTMFZnFHRGYGc7dEBnW2pUaHRlC%2FQbBmNLZdG9DbOuuudliIEBMUh%2FYoDOCOzMJzGEIxDPs3i5APTYJ6XsrFORy6PT6ftWLw46gQ2vs57MavErW%2FnT3Q%2BkAkTJjnwgIs40lQ%2BNLWCQ%2FEqhlkEztEWudMRwQMsOKdYeyg7m4%2BrSOFrZVc53U9mJrt6nwfoC78MZAzcbUt3h5r1quadjdR2yukKwK5%2BaTg5jAkdiRVdP8xcrjmIFDaD9G4wV1%2BzymlnxhyZD9vRX%2FeLvQlW%2FZeXlu0ejundXT%2BaqK5vKidR%2BYX%2Fp4lhUcidQPFGpMhblzQjqzSUkgrdB7R9u9EwDOiS1yunvGrU%2BRXGm5v%2FJ1f36OKMf4XA%2Ba01unoTRRxJbCW3SMTfqxepTPbJsuP%2B3ub9xTAOePdLEmjpArpntAaHmUGl%2BTbP5H1F%2BtDd7DnBz1IQ7lOOiDeOGwUzUJQ7fXfVKplbJsIapqajS1dRg1ozdL1BAhgzehX07IXrH7nZfGPbl074MlAEchxeltv7FC%2F%2B8gH7HGfFC%2FOLFQLyQ0EEajBfdQ53q4pmBzvNmrUo2UTvUIeFwXLKq5jAN%2BxEJ4bIStfQHKabD8ah87GfmMW8DqSQ6ac%2Bvyg5UeUw0qucXwkTma0WaN%2BsRkda0IyLNghFTxteBfL8VRw%2BbyV02MzwynYOktHODQyZ0CLFUatA7oUOtrjDsyqOmY8GIHraLFZXFDN5yjpsJwlBbpsOWc3v1SWWxfueiFusoc%2Boi2tHm9IWJhnlvonEq33IccBlyxpDAtnZCQyalWTDiVIV%2FbUTOiiTno40Q1EZfso36Es8VZMdg5Z%2FEUf6Jr9lUXE1ayz9dX4WFJHY9b%2BlebG9uXq145OEq6UNQSC%2BEi4tYOLhYNT7PE0Fw7F9pAJQh0FnW%2BA5eTE%2BtOSPpViHDlfgyBIPr6ziBA%2FPck%2BGYyAbSPBwzImIY%2BunpKo%2FT5eubT8OsiXRIOnPaD9YExvmDeSH984iVwrRc1SPzyxfacWnifUEGzSRe7CvgyxsK0tcTuUDY7gzB3vw5Iy11vRwqwWiWb6LEWLA3Tv7sFrA0RA9MTDFstJVKLs0H9%2FF8XvQxzdQ6%2Fje62fZXjM1V8Xbb92XTCXtXfCPNo0JD6DYaWGaOVjRzrH8168xN55NqDXeDkWaUQF51LvlukSixhJfe3q7V851IMmKiwzWo1WOc7yJawUJzvQtoEcLmeh%2FPFhdPtYt%2B0axbRRxdBTO6imA6fuVIUomKZLHguHFzyTSGARY6QpVCUor7qQ4uLNdJmxkahtqjYrT4rxxbh4SAoG%2BiTX6nSfUCyqOuLEhTmVxw5kF7kEG0h13nPIwqOYv55xb%2FAB%2BZpfjlHxxHDtqJC82NLpxmgtWMBHLSR7foUCsxnfyj8vzJDFmtN1LdlGZafSzSZZR8SNOV6ad9yVyTjhgGD5ze3Cj844gZE0q3WqSVqf4WjrnljgU7UP8Y9k99Hd3x4HajJFzdbujLzXYfkAB6nlpf523xn2NLFSvmqzuQdn6q1dwAw1S3JgeNyRFbscBF6kR21lM%2BAsc2%2BcAqtkI%2BLab9xKTDAz%2FS4RTsIIBCx0Tn2LKBlnyWqShX8%2BnTWQwe4kk%2BjFgT%2FhR1rP8YUjqwnuvN1p%2BBZQAnJhdfYuH2Fg5Ydp4iGlIwMN0xa0nVv1LBhBLqM1dx9NiCgTFkF2%2FUW2TSTD13j0e7TM0gO%2B08V7fRJinYlRSx8LTajBB%2BoVZPUK0v%2BntSrx1oqSRo98Zb0zVOB%2FfH4VpVMF4P11rEzPBBco5cGoq4bTyCsmzg6II%2BbpUGokBYXQ3uTzv21Ps1hoqHX0arL%2BkO%2BP6jo%2B9IHGNU0dc6qpi9bOoFRhVcOVX4coXbkKWa0%2Bs4KnppWUl1Yl7EhfAVtFJr6WDo2lZtZCeCwYRCn%2BLbcWaanwe%2FsBa4IdR1W7sh8YcJg9Ndz%2Fk8%2FKup9pPCHyYFvqmnhzSbn7pe8pWtQcxyw6Sr2GVstQTrw85BJtSXqai2Sa2MOD8BocAUTXYeJpz5kgvjpyiXEZe8Hap2KP%2Bu7e1xMqFByd0OoQFvqXV5odAg5M37SQb28%2Bg8n4WsZw%2FLFUHjhQYvnLR6bVw9qXXDSNplNrw3V5G03RI54D42B1VBg63FtjaAsefum%2BPACk1HLXg%2ByO3XDz4KLaaLUwAfVlCWhQbL6F6d%2FmSp9OTy2WeI4BNw%2BBx75bxZRet1ESKdvGSQJ8HAKgNyAvk0x3Y16WqVrnWU5N4Q7cSk4yupwK1ASbj27hpZNgJa8wPG5DmHUlVHTzn90uqcKh9AE9tyOw5YqVypOtCcDIh0h%2F0mvR%2F%2FNRfhTRBAGfg6%2FisAWyu7zkWh3IE18XECWBvWHTZO8471jY5C2XBYYwA1Qo59FrnTKeIDYt2hGPzceA2XAzsT88SFNQ4HxBqmgGfpcqZWRZB4ucnv9Ptp83YO%2BUdfBWLc3u3YdZ7d2EYVJoX3YjKn3f08ItLm2N7nAZ3AdIpw1vAZIb3bRMn3WD38LCIS1i5MzLVv%2F8gCkh1c0%2BHPuTk6Vek8yuTgcTjtYhn1OBOEkH0ECQqotfKk%2BwbcJARH5tkbLgyeqxQws74f41fxT2QnUeAo2HWdOzn2IIdR0V5C2yWeP4%2BMKG4OdxScgJmU%2BICAPqXrn2gMEWH7Mdy1K6QnAenL%2FenwO5WoQ6W7j%2Bm8WPb8%2Fv8%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E"></iframe>

## Data representation

```
UserDoc {
  _id: ObjectId,
  username: String,
  password: String
}
```

```
SessionDoc {
  _id: ObjectId,
  user: ObjectId
}
```

```
PostingDoc {
  _id: ObjectId,
  author: ObjectId,
  file: MongoObject?
}
```

```
LabelDoc {
  _id: ObjectId,
  label: String,
  items: ObjectId[],
  topic: String,
  rating: Number
}
```

 <!-- tag: String, -->

```
CitationDoc {
  _id: ObjectId,
  url: URL,
  items: ObjectId[]
}
```

<!-- ```
ControversialTopicDoc {
  _id: ObjectId,
  topic: String,
  controversialRating: Number,
  tagsForTopic: {tag: String, spectrumRating: Number}[]
  opposingItems: ObjectId[][]
}
``` -->

<!-- possibly

```
PairedItemsDoc {
  _id: ObjectId,
  mainItem: ObjectId,
  pairedWithItems: ObjectId[]
}
``` -->
