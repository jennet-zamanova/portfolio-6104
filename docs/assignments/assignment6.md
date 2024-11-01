---
title: Assignment 6
layout: doc
---

# A6

Here is the list of tasks I gave:

|          Title           |                                                   Description                                                   |                                                                                                                                                                                                             Rationale                                                                                                                                                                                                              |
| :----------------------: | :-------------------------------------------------------------------------------------------------------------: | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------: |
|    Create an Account     |                                    Create an account and log in to TrueTide.                                    |                                                                                                           This task warms up the user and verifies the accessibility of initial onboarding. It’s essential to determine if users understand the sign-up flow without assistance, which sets up the app for further use.                                                                                                            |
|     Find a Category      |                              Navigate to posts related to language/communication.                               |                                                                                                              Tests if users can locate categories and interpret paired posts. Reveals whether users intuitively understand the function of the category dropdown with `show posts` button and post pairing by theme.                                                                                                               |
| Find Supporting Evidence |                 Locate a post about Trump’s claims on immigrants and find evidence refuting it.                 | Now familiar with categories, users should be able to search for posts in politics and explore the supporting evidence feature. This tests user awareness of links and checks if users understand the role of links in supporting a post’s context. Moreover this would test whether users can see that posts are paired to have opposing views (since now we made it clear that they need to find a post disproving the original) |
|      Upload a Post       | Upload a video link and add supporting evidence with links and labels (all of the input will be provided by us) |                                                                           Although defaults (provided by us in future) may eventually assist users (which is why we provide the inputs), this task reveals their comprehension of the multi-step posting process and interaction with labels and supporting links. Evaluates ease of multi-step actions.                                                                           |
|      Edit Your Post      |                            Edit the post you uploaded by changing one of the links.                             |                            Evaluates if users can locate the editing interface by navigating to `My Posts` versus searching the home or category pages, ensuring they recognize how to modify content. This also can test the "may assist" claim in the above task's rationale because it resembles the posting that would happen in my goal app where supporting links and labels are app-recommended                             |
|     Go to All Posts      |                                       Return to the `All Posts` section.                                        |                                                                                                This final task checks if users can intuitively navigate back to a home page by clicking the logo or app name (the assumption I made in the last assignment). It also provides a natural session wrap-up, ending where they started.                                                                                                |

## Reports

### User 1

<!-- My first participant is my friend from back home, so she is actually in the target audience. I decided to test with her because I knew she would bash on any design I give her and will be super honest. The first couple of tasks felt very straightforward for her. Though she felt like logging in immediately after registration without prompting the user to login was unsafe. Mainly this is because she got used to all other software services/social media to prompt her to verify something and logging in manually.
I do not think that this is necessarily a bad thing especially since this could change in the future with the addition of safer logging in practicies/services used (though it was interesting to see a non-computer programmer's view/association of safety with re-logging in). On the second task, she could immediately tell that she needs to go to try to filter according to categories. However, the dropdown didn't react unless `show posts` was clicked which confused her for a second but she did not voice since she figured it out very fast. When I asked her in debrief whether she found it confusing, she said "yeah, I thought it would just react, but I get it - it was probably hard for you to implement". On the next task, she knew immediately to find political related posts but she could not tell what I meant by supporting evidence. I think the fact that I had post where default frame was same for both posts did not help. But she could not tell the difference between the two and hashtags did not help. When I later asked whether she could tell that posts are paired, she told me that she could not tell the color difference and did not notice the "VS" label at all. Moreover, when I asked her about links, she told me that she noticed them but did not want to click because of how nowadays people tell not to click on links in emails due to security. Even though she was testing from my laptop and new that I provided the data she still did not feel comfortable clicking on links and completely ignored them.
When it came to uploading the post it want smoothly for the most part, except she thought that these hashtags would correspond exactly to instagram hashtags and so she was wondering whether she needs to type the hash sign and was confused on why spaces from the hashtags were not removed. Note: She is an avid Instagram user (and I'm clearly not). She also said that she would've prefered to cancel or save her progress during the process of uploading a post. When I asked her whether she thinks there may be something on the screen that would let her do that, her response was "oh is this a button? would it cancel? oh, didn't realize it was a button". So I should be more careful with my neutrals and pay attention to whether they are even visible to everyone. Finally, after uploading she imediately to went to `My Posts` before I even told the next task and said that it would've made more sense if it immedately went to my posts tab when the upload is successful. Finally, she sould tell that clicking on the logo or app name would take her to home screen, so that was clear. -->

My first participant was a friend from back home who represents target audience of TrueTide well. I chose her because I knew her feedback would be honest and direct. Her experience highlighted several important takeaways across all tasks.

For **Account Creation**, she completed the signup process without help but expressed concern over being automatically logged in without further verification, mentioning, “it felt less secure.” Given the prevalence of re-authentication steps in popular social apps, her feedback indicates that including optional verification could help new users feel more secure about their accounts.

In the **Find a Category** task, she navigated the category dropdown easily but hesitated when the dropdown didn't respond immediately without clicking `show posts.` During our debrief, she admitted this caused slight confusion, saying, “I thought it would just react right away.” This response suggests she expected immediate feedback from the dropdown itself, indicating an opportunity to create a more intuitive, reactive interface.

For **Find Supporting Evidence**, she quickly identified the post but struggled to discern paired content and supporting links. She missed subtle visual cues (such as background color differences, the `VS` label, n by 2 grid) that distinguish the paired posts, and when prompted, she explained, “I didn’t even notice the label, and I could not tell the beige background was different [for different posts]” Her feedback signals that visual elements distinguishing paired posts need more contrast or visibility to reinforce the opposition feature.

Could not tell the color difference in the background colors:
![could not tell color difference](</../assets/images/a6/Screenshot 2024-10-31 233051.png>)

In **Upload a Post**, she encountered minor usability challenges, especially with hashtag input, noting that “it felt different from Instagram” and that she expected spaces to be auto-removed. This suggests she expected the hashtag experience to match familiar social platforms, especially for common user behaviors like entering hashtags. Additionally, she mentioned it would be nice to have options to cancel or save during upload, remarking, “oh, is this a button?” when I asked her to try to find whether this option is available currently on the screen. This interaction indicates the need for clearer action buttons to help guide users through multi-step processes more smoothly.

Did not notice cancel/did not think it was a button:
![cancel button problem](</../assets/images/a6/Screenshot 2024-10-31 223555.png>)

She navigated back to `My Posts` without issue, before even being tasked with **Edit Your Post**, but suggested that the upload confirmation screen should redirect users automatically to `My Posts.` This feedback underscores that post-upload flows should align more closely with users' expectations of post-creation workflows.

Finally, in **Go to All Posts**, she successfully used the logo to return to the home page, affirming the intuitiveness of this navigation method. Her feedback across tasks provided valuable insights into users' expectations and interactions with security cues, interface responsiveness, and familiar social media conventions, which will be essential in enhancing TrueTide's user experience.

### User 2

<!-- My second user was also my friend, and while she would not fit into the target audience per say she sould be one of the people posting content for newcomers to see.

She did not express concern about security. In cotrast, she was happy not to have to remember her password. She also could tell immediately the need to search from the dropdown for the second task. However, compared to the first user she did not hesitate before clicking on show posts because it was close to the dropdown. She also noticed the "posts retrieved successfully!" toast and got excited. When it came to finding supporting evidence she also knew to go to the politics category and found the post pretty fast. She was actually more inclined to click on the posts especially because they were youtube videos so it reminded more of clicking on youtube video to see singular post. She paid more attention to hashtags but still was not sure whether that's enough. I gave her more time to "explore" what else the post contains to try to find some supporting evidence. Soon enough she tried clicking on the links and figure out that they are related to the posts in some sense. When asked in debrief whether she could tell the relation in the posts she said it "did not quite", but she could tell that colors are different.
When it came to uploading post, she could tell that she needs to add the links and hashtags one-by-one (though I had default code for that if they are comma separated). Adding labels made sense. And just to compare with the first user, I asked to cancel here changes on her post and when prompted that way she could tell the cancel button right away. I think this goes on to show that when users are given tasks they understand that this is possible and try to find solutions, while in day-to-day usecase they might think I did not notice in 5 seconds so this feature just does not exist.
She also immediately wated to see her post and went to my posts. When it came editing, she told me once she saw the previous links and tags displayed one by one she could tell "aha, I was right they needed to be added one by one". Further confirming my suspicions. She got so excited she wanted to see her post among all posts. Unfortunately, there were only odd number of posts so hers did not show up. Once I added another post opposing it and showed her that they did get paired she was very satisfied! Finally she also could tell to go the homepage by clicking on the name of the app! -->

My second user was a friend, and although she wasn’t precisely the target audience, she represents a potential contributor for newcomers’ content. Her experience provided insightful comparisons, especially around ease of use and intuitive navigation.

For **Account Creation**, unlike the first user, she appreciated not needing a password, saying it “felt easier and less stressful.” This response highlighted a potential advantage of simplifying security, as she seemed reassured rather than skeptical about privacy—likely due to her familiarity with similar platforms that streamline access.

In the **Find a Category** task, she immediately recognized the dropdown search and the `show posts` button right beside it, navigating smoothly to complete the task without hesitation. This differs from the first participant, who hesitated at this point. Additionally, her positive response to the “posts retrieved successfully!” toast message illustrated that visual feedback can reinforce confidence in task completion, suggesting it may be worth expanding.

For **Find Supporting Evidence**, she showed an intuitive approach by heading to the politics category but then struggled to differentiate linked posts. The visual cues, such as different colors, helped but were ultimately insufficient in fully clarifying post relationships. She tried clicking on the posts themselves (since they had Youtube videos embeded, she thought this would function just like clicking on youtube thumbnails). I gave her more time to "explore" what else the post contains to try to find some supporting evidence. Soon enough she tried clicking on the links and figure out that they are related to the posts in some sense. In her debrief, she noted the links “did not quite connect.” This breakdown suggests that although she could identify visual distinctions, the functionality requires clearer cues to better communicate relationships.

When tasked with **Upload a Post**, she understood the step-by-step process for adding links and hashtags, suggesting that users accustomed to structured uploads might find the format intuitive. When I prompted her to cancel her changes, she identified the cancel button quickly, in contrast to the first user’s hesitation. This difference might suggest that once users are aware of a feature, they’re more likely to intuitively locate it later.

She also immediately navigated back to `My Posts`, before even being tasked with **Edit Your Post**. During editing, she noted the links and tags displayed individually, affirming her earlier assumption that they needed to be added one by one with a delighted “aha, I was right!”. This further confirmed my assumption that providing default options when user posts a video in the future would make the uploading task more intuitive.

She eagerly wanted to see her post among the others and expressed disappointment when it didn’t immediately appear (due to some logic restrictions I imposed knowingly). Once it did (by me creating another post that I knew would be opposing enough), she was visibly pleased, saying, “It’s so satisfying to see it paired!” This excitement reveals that feedback on user actions—such as pairing posts—can enhance engagement.

Finally, her intuitive click on the app name to return to the homepage to **Go to All Posts** also reinforces that this navigational cue was effective.

<!-- This comparison highlights a common usability insight: task-focused users often explore options, whereas casual users may need more guided discovery. -->

<!-- When she was uploading the post I realized how far away the add button is. the testers still could tell to click because it looked connected to teh text box and was very bright but it would be reverse to gisdalt principles. However, having it on the left side feels unituitive given other apps -->

## Opportunities for Improvement

<!-- ### Make the dropdown react on click

This is a minor linguistic flaw that may introduce minor friction like it did for the first user to get posts in a given category. Showing posts in a given category without prompting the user to click on aother button would easily solve this issue.

### Somehow make the links clearer

This is a more critical linguistic issue because both of the users struggled a lot with the links. We need to somehow specify whether a link is confirmed as valid/safe by us so that users like the first do not feel unsafe clicking on them. But a more important issue is to make clear that these links are trying to support the given post. Some things that could be done and would need to be tested again are:

- Add a Label: Insert a small label above the list of links, like “Supporting Evidence” or “Sources,” to clarify their purpose.

- Use Iconography: Add an icon (e.g., a book) next to each link to symbolize that these are resources for verification.

- Different Styling: Style the supporting links differently, such as with italicized text, or a muted color, to make them look more intentional and distinct from general links.

- Hover Tooltip: Add a tooltip on hover with a brief description, like “Click to view supporting evidence.”

### Improve the colors

moderate/major Physical/linguistic
Since User 1 could not tell the `cancel` button was actually a button and could not differentiate the colors for paired posts, it's important to make sure that the neutral colors are distinct and visible. For example, cancel button can have grey background and white text to still look more nuetral among everything but same style as the other buttons (considering the white text). For the background colors of the posts having more contrasting colors would help to differentiate the pairs.

### Provide defaults/examples

moderate physical
When it comes to adding the data(hashtags and links) one-by-one, the second test shows us that the default I was planning on (if vercel would let me access videos) would work. Where default is LLM providing suggestions for supporting sources and tags, which would be added in the list as shown below. Moreover, the hint text for the textarea being a dummy link or dummy hastag instead of `Add a Citation` would probably help too.

### Streamline some of the information flow

minor physical flaw. The easiest one is to navigate the user straight to `my posts` as suggested by one of the users and that would be apppreciated despite ot being voiced by the second user. -->

### Clarify Supporting Links’ Purpose and Safety

Major Linguistic Flaw: Both users found the links ambiguous and unclear in purpose, reducing their confidence and willingness to click. This is partly due to a lack of clarity on the function and safety of these links, which affected user trust.
**Solution Ideas:**

- Add a Label: A label like "Supporting Evidence" would clarify the links’ purpose immediately.
- Use Iconography: Adding an icon (e.g., a verified checkmark, book) could visually suggest these links are curated for accuracy and relevance.
- Distinct Styling: Styling the links uniquely (e.g., using italics or muted colors) would differentiate them from other content (general links) and signify their role as supportive references.
- Hover Tooltip: Tooltips could reinforce their purpose by displaying a phrase like “Click to view supporting evidence” on hover.

### Improve Button and Post Colors for Visibility

Moderate Physical Flaw: User 1 had difficulty recognizing the cancel button as clickable and struggled to distinguish between paired post colors. This issue affected both navigation and post identification due to similar neutral color tones.
**Solution:** Modify the color of the cancel button to a darker neutral background with white text to improve its visibility without overpowering other elements. For post differentiation, use contrasting background colors that make paired posts more recognizable.

Moreover, since `VS` was not even noticed to display opposition (especially by the first user) here some things we could add/modify for clarity:

- Headings for Viewpoints: Use a small heading above each video frame, like “Critic’s Perspective” and “Supporter’s Perspective.” This clarifies that they provide distinct viewpoints on the same topic.

- Icon Indication: Add small icons next to each post to signify different sides (e.g., thumbs up vs. thumbs down, or debate icons). Though this may end up unnoticed like `VS`

- Summary Text: Include a brief statement above the posts like “Explore opposing views on this topic” to guide users or enable users to add caption to their posts (as user1 stated gives more information than just hashtags).

Could not tell relation of the posts to each other:
![unnoticed difference in posts](</../assets/images/a6/Screenshot 2024-10-31 222653.png>)

### Add Default Examples/Suggestions for Tags and Links during Post Upload

Moderate Conceptual Opportunity: The second test user confirmed my suspicions that providing suggestions for label and link values would enhance clarity on the expected content format, aligning well with the planned LLM feature.
**Solution:** Implement the LLM-generated suggestions for tags and links (implemented - requires not using vercel). Additionally, placeholder text, such as “#Example” or “example.com/link,” could further guide users, replacing the current “Add a citation!” prompt.

Also, since user 1 was comparing the hashtags with Instagram's version so much, just renaming it to be `Tags` may resolve the issue to better match expectations. Users are likely to associate “tags” with a more flexible format, akin to platforms like Notability (reasoning: tags in Notability can have spaces and can be searched by # signed)

Suggestions would appear similar to this:
![LLM suggestions would look during upload](</../assets/images/a6/Screenshot 2024-10-31 232339.png>)

### Streamline Navigation to My Posts

Minor Physical Opportunity: One user suggested a shortcut to the “My Posts” page, which could ease the navigation flow. While this wasn’t voiced by the second user, it suggests a latent improvement opportunity.
**Solution:** Adding an option to redirect users directly to “My Posts” after posting could save them clicks, making the posting and reviewing process feel smoother.

Similarly

### Make the dropdown react on click

Minor Linguistic Flaw: This minor friction point emerged when the first user attempted to filter posts by category, which required an extra button click to confirm the selection. This additional action caused unnecessary interruption in their flow.
**Solution:** Configure the dropdown to auto-load the selected category when clicked, eliminating the need for a second button. This would streamline the process, providing a more intuitive experience for users.
