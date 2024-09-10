---
title: Assignment 1
layout: doc
---

# A1

## Prep

**Hunch**: Misinformation in social media. I want to talk about possible factual misinformation or general information shared from only a single perspective that leads people to have at best very restrictive at worst wrong opinions on some topics.

**Interviewees**: I interviewed two people whom I will call Ms. G and Mr. D. I wanted to get opinions from people who are 1. from different countries since that intrinsically would give a different perspective on the issue and 2. work in different fields. Ms. G works in a consulting firm and while she tries to learn more about the technical sides of her projects her field of expertise is business. Mr. D is a research engineer at MIT, so his background allows him to have a better understanding of the social media that he uses. Ms. G is from Turkmenistan but lived in UAE and studied in the US, so while we are from the same country she had experience living in other countries and has a broader friend group ([will come back to this later](#perspectives)). Mr. D is from South Korea, but he works in the US now. So these two people are very different from each other and are certainly different from me, so I thought I would be able to get a bigger variety of responses.

**Note taking + questions**: because the interviewees did not want to be recorded, I took all the notes by writing them down and immediately went over the responses after the conversation. While the questions were not set in stone, the general outline included starter questions like "What are some social media apps that you use frequently? Which one of them do you actually like?". To continue the conversation into the misinformation world questions like "Were you ever frustrated or shocked by news you got on social media? Was there a time when you learned about something that you thought was completely wrong but ended up being correct?" etc. were brainstormed. These questions would hopefully veer the interviewee into talking about news and information they get from social media and how truthful/objective it is.

Here are some notes I took:
| 1 | 2 | 3 |
|:-:|:-:|:-:|
|![Notes from the interview with Ms. G](/../assets/images/a1-interview-notes-1.jpg){style="width: 100"}|![Continued notes from the interview with Ms. G](/../assets/images/a1-interview-notes-2.jpg){style="width: 100"}|![Notes from the interview with Mr. D](/../assets/images/a1-interview-notes-2.jpg){style="width: 100"}|

## Interviews

### Ms. G

#### No trust

Since this was my first interview it was hard to ask questions that mattered to my hunch but some of the discussions were surprisingly helpful. In this day and age, people try to be more analytical or just not take social media as seriously, and Ms. G is no exception. She shared that generally when she sees some interesting information on let's say Instagram she would google it to make sure it is correct, and that this seems like the best way to ensure that the information is correct. While this ensures the correctness of the information it also involves an extra step of `going out of the app, opening Google, searching the information, and with unknown probability open the app back again`.

#### Reason for no trust

She shared that she would do something similar if she wanted to buy a new product, but this time instead of googling the product she would do a real-life equivalent and go to the store in person. The reason behind it is that she bought once a ring right before her engagement because she saw ads on social media. These ads portrayed the ring as having a big diamond and looked like a good deal. However, because she did not pay attention to the measurements fully when the ring arrived, she realized it was way smaller than what she wanted/expected (not the best surprise before an engagement). Since refund policies were also not the greatest, she stopped buying things online. Even if she sees the ads or recommendations made by influencers for products on social media, Ms. G would go to the in-person store first and only then make a decision. While she got used to this process, the misinformation once shared on social media - through ads or influencers - led to a more cumbersome approach to shopping.

#### Perspectives

Finally, we also talked about the general content she consumes on social media platforms. Instagram is one of the platforms she uses a lot to see what her "friends are up to" and what is generally happening in the world. She shared that, for example, recently she has been seeing a lot of political content on her feed. The main reason for this is that she has friends on opposing sides of conflicts due to her background and living experiences. This is why she gets to see both sides of the same story and how the different sides approach the current events. In that sense, she is very lucky, but not everyone gets to see both sides of the story because social media platforms, once finding what you are interested in, keep showing the same type of content, but not necessarily from different perspectives.

### Mr. D

This interview was not much easier because the interviewee was a person of few words. We discussed a bit about what type of social media platforms he uses a lot. During the discussion around YouTube, he shared that he does not like that the "title became more attracting and thumbnails ... just look too fishy". Compared to say how it used to be 10 years ago now he does not really trust these videos with crazy thumbnails and does not even take social media platforms seriously.

#### No Trust

He shared that he watches more short-form content for sports analysis. This is when he got more animated and engaged, so we continued the discussion around sports news on social media. Mr. D shared that he tries to get the sports news only through the official accounts. However, when he tries to get that content on X, he would still be shown these "unofficial" accounts. Some of them support whatever team was discussed in the previous post. Some of them are even deliberately faking official accounts. These fake accounts would make posts like "One of the players decided to transfer to a different team". After the initial shock though, he would usually notice that this is not an actual account and even if he is still invested in knowing for sure he would investigate himself. Again, he does not trust these accounts but it adds an extra step where he needs to go and check for himself.

Among the accounts that are not faking, even strong supporters of the team can get a bit annoying to Mr. D. These supporters (that have some affiliation with whatever team) would exaggerate the achievements of the supporting team and the loss of the opposing team to the point where it is "laughable". However, Mr. D does not consider it as misinformation, but more of a way people act in general when they are strong fans of something.

## Design Opportunities

- show opposing points of view by getting the "opposites" of the hashtags and the caption under a video/post. E.g., Messi vs Ronaldo, Trump vs Biden, democratic vs republican etc. This would help Mr. D to see the different "laughable" versions of the game analysis but also help those who are not as lucky as [Ms. G](#perspectives) to get both perspectives on an issue.

- crosschecking information by providing links to articles and research papers generated by some ML related to the caption and possibly video content. This would let [Ms. G](#no-trust) and [Mr. D](#no-trust-1) who prefer to investigate themselves do it faster and possibly within the app (it could be very biased if just done through LLMs but still an idea)

- easily see non-sponsored versions of the content for example by clicking on a button on the screen and it would show you all videos/posts that are non-sponsored but also feature the product in discussion. This would be useful for Ms. G to find real reviews (since non-sponsored) on the [ring she wanted to buy](#reason-for-no-trust) and get an in-person-like experience of the product.

- filter to show only official accounts / non-sponsored content about search or general feed (similar to the previous point and it's pretty easy to implement the first part). Pretty simple idea that ensures that [Mr. D](#no-trust-1) can get all of his information on X easily without having to be fooled by the fakers and overexaggerating sponsored accounts.

Note: could not find a way to link to specific part of the sentence so linked to headers.
