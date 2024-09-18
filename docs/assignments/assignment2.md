---
title: Assignment 2
layout: doc
---

# A2

## Broad application goals of TrueTide

The intended audience is _international students_ who are trying to assimilate to their new environments and learn more about them. Because these students are new to whatever country they are in, it is important for them to get diverse perspectives on matters as important as policy and as "low-key" as local slang and culture. **TrueTide** would give a more `diverse` set of information with `easy` fact-checking.

## Scrapbook of comparables

#### Quora

|       Profile credentials to get more reliable users        | Submissions checked by moderating (is it actually checked though?) |
| :---------------------------------------------------------: | :----------------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/quora-credentials.png) |     ![](/../assets/images/a2/comparables/quora-submission.png)     |

|        Employment credentials (that are not checked by anyone)         |
| :--------------------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/quora-occupation-credentials.png) |

#### Reddit

|    Auto moderator (using LLMs to fact check? could backfire)    | Rewarding users for providing factual information or reporting misinformation |
| :-------------------------------------------------------------: | :---------------------------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/reddit-auto-moderator.png) |            ![](/../assets/images/a2/comparables/reddit-badges.png)            |

|       Just comments proving my point on perspectives       | Images could be fake and some though should be given to it |
| :--------------------------------------------------------: | :--------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/reddit-diversity.png) |   ![](/../assets/images/a2/comparables/reddit-image.png)   |

#### Stack overflow

|      Mentioning a new user when publishing       | Keep track of reputation, amount of times they helped the community and how long they were in the community |
| :----------------------------------------------: | :---------------------------------------------------------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/so-new.png) |                            ![](/../assets/images/a2/comparables/so-profile.png)                             |

![](/../assets/images/a2/comparables/so.png)

#### X

| Marking user's credibility (however it mainly is for $ and criteria very vague) |           Marking even better user's credibility           |
| :-----------------------------------------------------------------------------: | :--------------------------------------------------------: |
|           ![](/../assets/images/a2/comparables/x-blue-checkmark.png)            | ![](/../assets/images/a2/comparables/x-gold-checkmark.png) |

| Community member's reporting misinformation themselves (nerds like correcting others) |             Though criteria to join kinda weird             | But hey this (readers add context) but somehow for videos? |
| :-----------------------------------------------------------------------------------: | :---------------------------------------------------------: | :--------------------------------------------------------: |
|                 ![](/../assets/images/a2/comparables/x-community.png)                 | ![](/../assets/images/a2/comparables/x-community-notes.png) | ![](/../assets/images/a2/comparables/x-misinformation.png) |

|             Pinning profiles that users wanna see more             |             Report profiles that do not wanna see             |     Reasoning for why a piece of content is shown     |
| :----------------------------------------------------------------: | :-----------------------------------------------------------: | :---------------------------------------------------: |
| ![](/../assets/images/a2/comparables/x-control-diversity-more.png) | ![](/../assets/images/a2/comparables/x-control-diversity.png) | ![](/../assets/images/a2/comparables/x-diversity.png) |

#### YouTube

| Verified doctor: can it be used for other professions - what proffesions should have this? |         but also how messy can the criteria be?          |
| :----------------------------------------------------------------------------------------: | :------------------------------------------------------: |
|               ![](/../assets/images/a2/comparables/youtube-health-more.png)                | ![](/../assets/images/a2/comparables/youtube-health.png) |

|   what if you do not want to post videos but do want to comment   | This type of filtering but to show only non-sponsored posts |
| :---------------------------------------------------------------: | :---------------------------------------------------------: |
| ![](/../assets/images/a2/comparables/youtube-health-comments.png) |  ![](/../assets/images/a2/comparables/youtube-filters.png)  |

<!-- #### Other

|     |     |
| :-: | :-: | -->

## Brainstorming feature ideas

- **Side-by-Side Perspectives:** Display posts with opposing views side by side, including a neutral perspective, allowing users to easily compare and understand different angles on a topic.

- **Non-Sponsored Content:** Ensure only non-sponsored posts are shown, minimizing scams and delivering authentic, unfiltered reviews.

- **Occupation/Education Verification:** Verify users' professional or educational backgrounds to enhance credibility, especially for content creators and commenters.

- **Misinformation Watchbird:**

  - **Report System:** Users can flag misleading posts, which are then marked (with the number of reports made so far) and reviewed by moderators before removal.
  - **Notification Alerts:** Users receive notifications about the removal of a false post previously viewed (do not believe it!), helping them discern unreliable content.
  - **Reward System:** Reward accurate reporters and content creators who consistently provide truthful information.
  - **Flagging Mechanism:** Flag and reduce the credibility points of creators who repeatedly spread misinformation, with visible reports of their past infractions (to everyone).

- **Spotlight Feature:** Highlight profiles that user actively specifies visibility for, prioritizing those profiles' content over random profiles (unless the random profiles provide different perspectives).

- **Image Verification:** Authenticate user-shared images to ensure they are genuine and unaltered, with tampered images clearly labeled.

- **Citation Provision:** Automatically generate citations for information shared by creators (and commentors) similar to Wikipedia, allowing creators to confirm accuracy and enabling users to report discrepancies (based on experience with stackoverflow it would happen more often than one might think).

- **New Creator Privileges:** Newly registered users are identified as such, and reports on misinformation are handled more leniently to encourage content creation (similar to voting in hacker news).

- **Auto-Moderation:** Use AI to assess and rank the likelihood of misinformation in posts, displaying the ranking to users to guide their content consumption.

- **Labeling System:** Tag posts as more important or requiring stricter moderation, with these labels visible to users to indicate the content’s review status.

- **Recommendation Engine:**

  - Offer diverse perspectives
  - highlight factually accurate content
  - prioritize recommendations based on credible occupations or education
  - including location-specific content for cultural insights.

- **Customizable Filters:** Allow users to set content sensitivity preferences according to their cultural background, interests, and personal experiences (avoiding triggering content).

- **Impact Assessment:** Use AI to evaluate the potential harm of misinformation
  - involve **expert panels** to verify information in high-risk cases.

## VSD analysis

**Stakeholders**  
**Observation 1:** Stakeholders’ Roles and Credibility

_Criterion:_ Credibility Assessment  
_Prompt:_ How should the platform handle users who have multiple roles and report both accurate and misleading information?  
_Features:_ Current feature allows users with multiple roles to report information, but assumes only one of them when assigning crediility score.  
_Design Response:_ Implement a system that evaluates the credibility of users based on their reporting history and accuracy. For users with conflicting roles, create a system where their credibility score is recalibrated based on the proportion of accurate posts to misleading reports and vice versa. This ensures that users with misleading posts and good catches of others do not gain undue credibility (and have different badges: good critic, bad sharer to explain the score).

**Observation 2:** Kids

_Criterion:_ Kids' Use of the Platform  
_Prompt:_ How might the platform's design affect children's engagement and the reliability of their interactions?  
_Features:_ No age verification currently or age-appropriate filter currently.  
_Design Response_ (more like thoughts): Children are less inclined to engage in thorough fact-checking by clicking on links and are more likely to be drawn to interactive features like scores, perceiving them as part of a game. This would ensure that kids are learning at least a little about getting truthful information. However, the exposure to a wide range of information can be harmful, from trivial misinformation (e.g., myths like Santa Claus) to serious content (e.g., political or religious matters). Therefore, it is crucial to carefully curate the information displayed to avoid potential negative impacts. A dedicated "tweens mode" could address these issues by providing a safer, age-appropriate experience. However, ensuring robust verification without making it overly burdensome remains a challenge. Simple age verification methods are insufficient, while requiring government-issued documents may be impractical for widespread use (at least before the platform is so widespread that users are willing to take extra steps to conitunie using it).

**Time**  
**Observation 3:** The Long Now

Criterion: User Dependence on Credibility Metrics
_Prompt:_ What are the potential risks of users becoming too reliant on credibility metrics?  
_Features:_ The platform emphasizes credibility and links but does not address potential over-dependence on these metrics.  
_Design Response:_ Introduce educational prompts and content that encourage users to critically evaluate information beyond the provided credibility scores. Develop features that foster critical thinking and independent verification, such as user guides on assessing credibility and diverse perspectives.

**Pervasiveness**  
**Observation 4:** Cultural Sensitivities and Post Types

Criterion: Accounting for Culture
_Prompt:_ How should the platform handle content to respect cultural sensitivities and user preferences?  
_Features:_ We brainstormed a feature that accounts for cultural sensitivities.  
_Design Response:_ Pay more attention to incorporating cultural sensitivity filters that adapt content visibility based on user cultural backgrounds and preferences. Additionally, create options for users to customize their content feed to align with their cultural sensitivities. This approach ensures that the platform remains respectful and relevant to diverse user groups.

**Values**  
_fairness, trust, security_

**Observation 5:** Value Tension: Privacy / Political realities + Indirect stakeholders

Criterion: Privacy and Information Display + verification effects on indirect stakeholders
_Prompt:_ How should the platform handle the display of background information in countries with varying levels of support for opposing views?  
_Features:_ The platform currently displays specific occupation and education information to display credibility, which may not be suitable for all users.  
_Design Response:_ Implement customizable privacy settings that allow users to choose whether to display their occupation information based on their location and cultural context. Provide options to show occupation information only to trusted users or within specific regions, while still using it to enhance credibility where appropriate - the score still is high for given content but other users will not be aware of the occupation. This balances transparency with user privacy concerns.

Moreover, we could just ask for backgorund information verification if the user wants to post or comment on a content. This way we would be affecting less (hopefully) servers of outside parties. If the information is verified then label it as so.

## Storyboarding and sketching

<!-- I, as creator, want to share factually accurate info and let people continue watching your content without leaving the app -> cite! User comes wtaches content, gets curious, goes to the link, verifies, comes back, reports as true, continues watching, creator's credibility and # of views increases -- could also add search videos with the linked articles to get a different explanation or point of view

I, as consumer, looking for a suncscreen to buy because I'm going to the beach soon. I go to TrueTide to get non-sponsored content. i watch video from chemist, then from dermatologist. But then I saw a video that did not make sense and the article says the reverse, so I report it. I listened to the derm and got my sunscreen. Im sitting at the beach and receive notification that video I reported is removed and was actually factually inaccurate. I get a analytical owl badge and Im happy I helped to stop spreading of misinformation! (probably will need to be specific on when we want to incorporate panel of experts vs moderators)

Everyone is talking about election in US and I heard a lot about indecision24. I, as consumer, wonder what other people think about it, so I do the search with location set to Boston. I get videos about democrats' view especially in MA, next video is however from republicans' pont of view and why they think their nominee is better. Now, I see why it's indecision and try to be more open to conversation when people talk to me about elections! -->

<!-- I, as creator, want to share factually accurate info and let people continue watching your content without leaving the app -> cite! creator's credibility and # of views increases -- could also add search videos with the linked articles to get a different explanation or point of view -->

### Flow 1

|                               Interesting topic!                               |                            Lemme share with others interested in space on TrueTide!                             |
| :----------------------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------------------: |
| ![Big Bang theory is so cool](/../assets/images/a2/storyboarding/creator1.jpg) | ![I should share with others interested in space on TrueTide!](/../assets/images/a2/storyboarding/creator2.jpg) |
|                           Big Bang theory is so cool                           |                           I should share with others interested in space on TrueTide!                           |

|                                            Cite so others can see!                                             |                 Now users will not leave my channel and will continue learning about space!                  |
| :------------------------------------------------------------------------------------------------------------: | :----------------------------------------------------------------------------------------------------------: |
| ![Cite the source I learned this from so others can see too!](/../assets/images/a2/storyboarding/creator3.jpg) | ![My credibility score is so high and I got so many views!](/../assets/images/a2/storyboarding/creator3.jpg) |
|                           Cite the source I learned this from so others can see too                            |                           My credibility score is so high and I got so many views!                           |

<!-- I, am a consumer and chemistry student, looking for a suncscreen to buy because I'm going to the beach soon. I go to TrueTide to get non-sponsored content. i watch video from chemist, then from dermatologist. But then I saw a video that did not make sense and the article says the reverse, so I report it. I listened to the derm and got my sunscreen. Im sitting at the beach and receive notification that video I reported is removed and was actually factually inaccurate. I get a analytical owl badge and Im happy I helped to stop spreading of misinformation! (probably will need to be specific on when we want to incorporate panel of experts vs moderators) -->

### Flow 2

|                                                  I need new sunscreen!                                                   |                                                           Nonsponsored content from derms and cosmetology chemists on TrueTide                                                           |                                     Ineteresting video but sounds wrong... report                                      |
| :----------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------: |
| ![Chemistry student planning vacation, remembers he needs a sunscreen](/../assets/images/a2/storyboarding/consumer1.jpg) | ![Let me search non-sponsored reviews on sunscreens on TrueTide ... wow so many videos from dermatologists and cosmetology chemsists ](/../assets/images/a2/storyboarding/consumer2.jpg) | ![This video sounds wrong, we learned the opposite! Lemme report it](/../assets/images/a2/storyboarding/consumer3.jpg) |
|                           Chemistry student planning vacation, remembers he needs a sunscreen                            |                            Let me search non-sponsored reviews on sunscreens on TrueTide ... wow so many videos from dermatologists and cosmetology chemsists                            |                           This video sounds wrong, we learned the opposite! Lemme report it                            |

|                                                                     Notification on the beach?                                                                     |                                                              New Badge!                                                               |
| :----------------------------------------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------: |
| ![I'm on the beach using the new sunscreen recommended by a dermatologist, but I get notification from TrueTide](/../assets/images/a2/storyboarding/consumer4.jpg) | ![I was right the video was misleading and it was removed. Now I have a new badge!](/../assets/images/a2/storyboarding/consumer5.jpg) |
|                           I'm on the beach using the new sunscreen recommended by a dermatologist, but I get notification from TrueTide                            |                           I was right the video was misleading and it was removed. Now I have a new badge!                            |

<!-- Everyone is talking about election in US and I heard a lot about indecision24. I, as consumer, wonder what other people think about it, so I do the search with location set to Boston. I get videos about democrats' view especially in MA, next video is however from republicans' pont of view and why they think their nominee is better. Now, I see why it's indecision and try to be more open to conversation when people talk to me about elections! -->

### Flow 3

|                                                           Indecision24                                                            |                                                         Lemme see what the big deal is on Truetide                                                          |
| :-------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------------: |
| ![I'm a new international student and everyone is talking about indecision24 ](/../assets/images/a2/storyboarding/diversity1.jpg) | ![I wonder what other people think about it, so I do the search on TrueTide with location set to Boston](/../assets/images/a2/storyboarding/diversity2.jpg) |
|                            I'm a new international student and everyone is talking about indecision24                             |                            I wonder what other people think about it, so I do the search on TrueTide with location set to Boston                            |

|            After I set my location to be Boston I first get a post from a left-leaning person             |                                                After I swipe I get a post from a right-leaning person                                                 |                                                                             Indecision!                                                                              |
| :-------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
| ![I get videos about democrats' view especially in MA](/../assets/images/a2/storyboarding/diversity3.jpg) | ![next video is however from republicans' pont of view and why they think their nominee is better](/../assets/images/a2/storyboarding/diversity4.jpg) | ![Now, I see why it's indecision and try to be more open to conversation when people talk to me about elections!](/../assets/images/a2/storyboarding/diversity5.jpg) |
|                            I get videos about democrats' view especially in MA                            |                            next video is however from republicans' pont of view and why they think their nominee is better                            |                            Now, I see why it's indecision and try to be more open to conversation when people talk to me about elections!                            |
