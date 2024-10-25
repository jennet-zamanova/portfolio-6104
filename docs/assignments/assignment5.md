---
title: Assignment 5
layout: doc
---

# A5

## Heuristic Evaluation

<!-- ### Usability criteria: capture the broad overall goals that your visual and interactive designs might be trying to satisfy

Discoverability: how rapidly and easily can users understand how to operate the interface? Since TrueTide offers some new features not available in usual social media apps, it is important that users can actually understand what is offered and what is not. In my initial wireframe, it was hard to tell apart the dualview option (especially since even graders did not find it), so it would be more important to make it clear. Currently due to time crunch there will only be the option of dualviewing so maybe it will be more clear to the users. On a bigger screen we could accomodate for that by having the two posts side-by-side with say same background and text color as a pair different from the next pair. It would be harder to show it on a smaller screen. The only simple way to kind of chuck down the user's throat would be on to let the user swipe only horizontally if the opposite is not shown yet and swipe vertically only after the second video was shown. If we were to think about a more ready for change design it would still be hard to emulate the paired content if there is also option for non-paired content, so more thought is necessary.

Efficiency: once you know how to use an interface, can you use it to quickly and efficiently accomplish your goals? One of the main reasons I wanted citations concept was to make it more efficient for users to see supporting information and in a way promote fact-checking.

Error tolerance: how easily can a user recover from making mistakes? In my initial wireframe, there was not much thought gien to error tolerance. There were simple ways to accomodate errors like being able to go back and reselect content, citations, labels before final submission. However, after the submission there was not much power for editing given and wrong citations and labels could lead to more misinformation (something I'm trying to prevent). So we need to make it clear that it is possible to edit content in that way to the users - so they don't go "welp, it got posted already."

### Physical heuristics: describe characteristics about the user interface that affect how users might operate it

Fitt’s Law: how quickly and easily can users reach for (or point to with their cursor) interface elements? In my initial wireframe, my links are at the bottom of the page in dual view, so one could argue that they are easily reachable because of it. However, selecting individual links is harder. One could imagine haveing buttons for each link, but that makes it seem like NOT a link, and having a dropdown would introduce additional step of clicking on dropdown to select link to go to. Considering all of this it may still be better to leave them as seperate links but have a bigger padding so clicking when you are close enough will perform expected action.

Perceptual fusion: how does the interface account for time delays? It's important to accomodate for time delays as we are using LLMs for some of the processing. Currently I didn't add any loaders but it would be good to have the loading icon and some text specific for operation that we expect to take long time.

### Linguistic level: describe cultural conventions and norms about the interface

Speak a user’s language: does the interface use simple, helpful informative messages? are there instances where messages might only be understandable by developers? It's especially important to speak the user's language in the case of TrueTide since these users are new to whatever country they are in, so we cannot assume that user's understand any of the slang. We would need to keep any messages presented as neutral as possible since there is enough controversial things in the app. The words used in the wireframe are mostly understandable and error/loading messages will be created to be understandable even by my mom (if she understands, most of internationals will)
Consistency: does the interface reuse the same names, symbols, and icons for the same concepts or actions? how consistent is the interface with others across the same application domain or platform? In my wireframe, I had `upload` for making a post. It may be more consistent with other apps to use `create`. I also had `preferences` to avoid implementing a whole search functionality, but currently I just have categories that could be used as "filter". This tend to be displaued at the top center of the page in informational websites (reddit, quora, etc), while it tends to be somewhere on the side in more common social media platforms (instagram, facebook etc.) - though tiktok has it in the center: not sure where that puts it 🤷🏽‍♀️. To make it more clear that it's supposed to be similar to search, I would have a dropdown for selecting category (which means for consistency sake I probably would not use dropdown for citation links). Moreover, people are used to the videos in instagram posts where it plays twice and then prompts to play again, so having the two posts side by side where first one plays, stops, second one plays, stops, prompts to play again either of them would be familiar enough. -->

### Usability criteria

#### Discoverability:

Since TrueTide introduces unique features like the dual-view option, it's crucial that users can easily identify and understand them. In the initial wireframe, distinguishing the dual-view feature was challenging (even for graders). To improve this, the design could enforce the dual-view interaction pattern more explicitly, such as by restricting swiping to horizontal movements until the second video is shown. On larger screens, placing paired content side by side with consistent background colors would also help visually connect them.

#### Efficiency:

The citation feature aims to streamline the process of accessing supporting information, encouraging fact-checking without users needing to leave the app. This quick-access design promotes efficient use by keeping resources accessible within the app’s interface.

#### Error Tolerance:

The wireframe currently lacks visible options for correcting errors after content submission, which could lead to misinformation—something TrueTide aims to prevent. An "edit post" feature should be integrated, clearly marked and easy to locate, allowing users to adjust labels or citations even after posting. This would align with the app's goal of promoting accurate information.

### Physical heuristics

#### Fitt’s Law:

In the current wireframe, supporting links are positioned at the bottom of the post and therefore screen, making them easy to access. However, their small size might make precise tapping challenging. Increasing the padding around each link would create a larger clickable area without introducing dropdowns (which would add steps) or buttons (which might not be visually associated with links). This change would improve accessibility without compromising the interface’s simplicity.

#### Perceptual Fusion:

Because TrueTide utilizes LLMs for processing, time delays may occur. To manage user expectations and maintain a smooth user experience, the interface should include loading icons and context-specific messages that inform users of ongoing processes. This approach helps keep users engaged and informed during any waiting period.

### Linguistic level

#### Speak a user’s language:

TrueTide’s language should remain simple and culturally neutral, catering to international students who may not be familiar with local slang or complex language. All notifications and error messages should use straightforward, accessible language to ensure clarity for users with varying levels of language proficiency.

#### Consistency:

In the wireframe, I used `upload` for making posts. For better consistency with other social media apps, `create` might be a more intuitive term. Similarly, `prefernces` would now become `categories` dropdown showing the selected category to view positioned at the top center of the screen - this could help users understand that the content displayed depends on their selection (this case also reinforces the fact that I should not use dropdown for citation links for the sake of consistency). Lastly, structuring the video playback to mimic Instagram's familiar style - where one video plays twice and prompts for replay - by having layback where one video plays, stops, and then the next plays before prompting the user to replay can help create a sense of familiarity while reinforcing the dual-view concept.

## Visual Design Study

Thoughts on colors: ![collage for colors](/../assets/images/a5/colors.png)

Thoughts on fonts: ![collage for fonts](/../assets/images/a5/fonts.png)

## Notes on differences from above

I decided not to implement the Instagram's playback style because these videos can contain all sorts of content that users may not want just playing out of nowhere when they open the app.
I also decided to not have a separate button for `Home` as it was in the initial code because users are more used to the fact clicking on app name/logo achieves the same thing. And when there is a separate home page it leads to think that there are multiple feed pages which I do not have.

# Notes on code submission

When Uploading please submit the youtube link that has embed in it (I only check for it to be a valid link and that
it's from youtube but embed would be too hard to explain to an average user and I would prefer the user to upload a file anyway).

For categories, the ones that are available are the ones that have posts in them. Note: there is no way for graders to know what category a post belongs to reliably because that is all handled in the backend (and if llm performs poorly - only Gemini is free so it probably will - it gets assigned to all).
If you made a post, the only way for you to reliably check that is though going to your posts. If there are odd number of posts in a given category, one of them for sure will not show up, because I'm pairing posts.

If you get error related to Gemini, we probably reached the token limit (even more likely the request number limit😔). This can happen when you upload a post and when you view posts on the homepage.
Since I'm not willing to spend money on this class, please reach out to me and test again the next day (I will try not to do anything LLM related that day, so you are less likely to reach the limit again)
To somewhat make the user feel better I added a link to go to page that would have just posts: unpaired, unprocessed.

Here are the links to the deployed version:  
[https://truetide-frontend.vercel.app/](https://truetide-frontend.vercel.app/)  

[https://truetide-frontend-jennets-projects-b71c0174.vercel.app/](https://truetide-frontend-jennets-projects-b71c0174.vercel.app/)  

[https://truetide-frontend-git-main-jennets-projects-b71c0174.vercel.app/](https://truetide-frontend-git-main-jennets-projects-b71c0174.vercel.app/)  

P.S. if you are wondering whether it's even possible to reach the limit, YUP it is: I did today so last changes were not fully tested in deployment - let's hope it doesn't crash (if it does: one more reason to stop using vercel) 
