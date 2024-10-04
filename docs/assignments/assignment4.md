---
title: Assignment 4
layout: doc
---

# A4

[TrueTide repo](https://github.com/jennet-zamanova/truetide)

[TrueTide deployment](https://truetide.vercel.app/)

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
  file: ObjectId # stored with GridFS
}
```

```
LabelDoc {
  _id: ObjectId,
  label: String,
  items: ObjectId[],
  topic: String
}
```

```
CitationDoc {
  _id: ObjectId,
  url: URL,
  items: ObjectId[]
}
```

[Data Model](https://viewer.diagrams.net/?tags=%7B%7D&lightbox=1&highlight=0000ff&edit=_blank&layers=1&nav=1&title=test.drawio#R%3Cmxfile%3E%3Cdiagram%20id%3D%226a731a19-8d31-9384-78a2-239565b7b9f0%22%20name%3D%22Page-1%22%3E7Vxbc9o4FP4tfeAxjO6yHwMJ7cy2M52mnXYfDSjgrcGMMU3SX78yyBddnHKxDVk2D210wLL1fUffOUeS08PDxfP7JFjNP8VTEfUQmD738F0PIYQxlv9llpedBSLs7SyzJJwqW2l4CH8LZQTKugmnYq19MY3jKA1XunESL5dikmq2IEniJ%2F1rj3Gk33UVzIRleJgEkW39Hk7TubJC5pcffBDhbK5u7SG%2B%2B2AcTH7OknizVPdbxkux%2B2QR5N2oMa7nwTR%2BqpjwfQ8PkzhOd78tnociynDNEdtdN6r5tHjkRCzTfS5YDW75c8zC94NP35c%2F%2Fvr87eeX9Q2knO46%2BhVEG4WGet70JYdnO0CR9QN6ePA0D1PxsAom2adP0iOkbZ4uItmC8tfHMIqGcRQnsr2FAw%2FWaRL%2FFLmxh%2FCU%2B2MAik9yzOH2%2BniZKg9BnmyrxxNJKp5rhw4LQKWTingh0uRFfiW%2FgBHcV%2BNULkpzWp5KvnFum1eoRr4yBsrHZkX3JdjyF4X3YdjDK8AeEqAhD6mNPGEO5DFoEXlyBuTHHiW0Q%2BQLAHPkgcPpmcvpCz7agB6dAXo28cT4sTPoCTb1BjEbegpd0NMWocdngN5nHAesM%2Bixrzu976O%2BL2dC%2FgPtGUBcNDQhPhDnZFYQ%2F7YWiYW6vE7mOuLPiBdZBFDwjYJFGGVj%2FSCiXyINJ4ED16xdoWS0%2FZH2IApnS2mbSHDlU5kcYYNiealMifytXedZkV9DloPSWv441fkrJkmFMZgnnFXGCuOJjNkx%2BUGs12G8fLukjYDHAa0jbZYE01CU91LmaZjIVDsbN75bx5us7yb4lTTpBCMXwdwxJQvjiQTbCe%2B3Lx%2F%2Fq%2BQ2wZg1JX2WR7cqZ2WOrbFWmk%2FkjVm8fQzGWSX6Vpm79ygjqFXmkGfkIVAm5C7ysOckrzSfSJ5v07Sc3malu5k65IAxC5hq%2BKkmIc4kwgGcVLFkklf8FKqBpUEyE8V4c1cXU23FwIY4EVGQhr%2F0BYTTQMpTxFNBeswVoTWQ4BlBws2AxDEb3nrtgUQhOyNItlbaqMnnelBNBdtRQBYq1pq37Qtkrnoe1BMM5AxXwJVivJb1qxt%2BjkM5iEq9od8NE2ZK5m6Q6rrqCp3RFTG6QnZXO2SsrrYeUSCxp5M4Vp8e0iRczixXKWtCs%2BjLSmsyGNzXRjE7CGpR1%2FAZV1zd25f2j4uEmuU5cZTnEDvrwibmp2P56Uqg55zrPu53Cry3xwrIEcJoF8RVdk4WxiIr0YWR7xuGFfY38gvmMnib0oj0KQaOFkYI9K6w3VWTwui1Ez3P5CTkfydpwUkIsKNna04yorcjauSq0heSlx%2FVxt%2BZsPdp3rx7VkK%2Fa730yjr3GOfKt2WPq5byZMlcFXfWok15FjRvBwk82rtQtqRfLiObzgZJm87meZfobLAlVzutnMrZt7Z8sd%2Baq9kJJcxXPA53NB%2BYfWFM2vMt396iOCYXfQSe8OCbykUhQcRSCODIR51bpE3ko8S389GrAR%2Fqq8rlQYFOoKegw1JgBLz7LT8NZHnMoY7FJN5%2FjcRcGKZthmL52NZCtH98LCZWb3ZnDUokBXuckWrTVYrwC%2FqMIT3f82VYez0Mb1ufRRLKMWcbEyfFZpf3HRybO%2FY%2B7FvOx492Pg5RX6oS83xGKeSIGSKG2qw6KOiwNG1ftPBFu80bFy1oi9bXZCO%2BhlNhu0ynW6ZoRAd8WL9l6vqqvRFhboNruYoaWvbINccbmkhhgHGUgXkuf0SuwwyokcMMhfJWSB7K8QvlP29yW5xjNgm8umS2Ad4YNTNPn%2FQJtoWE0j7lDi2p2E%2Bkz67rR2Fkz89Xk%2F8A%2BdNJ7QGQi0z%2BCTIYAN3m%2FtiueVsLo7fIvxs2tBvvzr68w8LojYy8ngb%2FDQa4xUB6AyHT%2BUbMLybcoYH0BgKjN%2BjorblIWnOWltlT910wSTdBVCvAkp%2FdiSXNFyyBzKaR1NjoVn2wCKfTrI9BItbh72C87S%2Bbu6tsdNvx0kGP3mXfiNNAHdkj9Vm%2B43yterFGdd4rXlrRXFJNmxNOMNQxinQ%2BjdWu%2BPFxLU5PiHCHBb9r0ovnMN0VcZz6qr2r4WTVoNplCZc1XiqNZgo4t4QcvI7fuYQwRCVKHvFgVs5xpjsMZxJTgLgsyTzuEYKOUxZundrnBPaJ7xMKKMn%2B9boWGd9y2WCTzuPk3TnUpeJyGOlqc%2BOBBuQFtyIvOqU3xrp8Q%2BJC9tIS%2FeUKpzbQijJAp%2FxIi0wSI9XJPyJNXxQr0jdiaYoT6SKzeBlEH%2BN4pfqpPwCnyxmyE0xGxmOB9qjrMCFbR6nVoubOwtXsw3DaB7WbdBARcnTacUTXrctD7nTVHEQ2N9s3TKRzjCyflBMzrasUHC%2FzvJKymmV2ra5YClSVDURfk41D3jL09JwQO94ydAajJgqKOnrsFZiMnjRehZOLZwa%2FKugHMEPNbB1DR6ndNTXcTU1gb7xdGDGwqRlDubkKwvdeTW2TGbuumtQUVBfGTINTBliJqHd%2BOWN2%2FZRHm2WwEHZKemn8eA1NHZ4jURxauwBy7BPF71bBev0UJ9OLZ6YpTWPWATNyAfOG22v0UtEmYpVll7eynJOjk5ClrlMfF0ZUQwLHsLkV5nwJtGue7Jyg5Em9A3w9HEHsGyXOBahcPpu7eK9p5HiLrjyI0Wvg0K1RDR%2F%2FghR9nclO34eC5u18apTx%2B5%2BEBHqchcWLIZ1V2NxegCs1YRhekWZDmfVcYHDNnc1J0HY99IoootykyL8EiuxVqpKiz%2FH6iiYR5dYZIPqnP0%2FTOV12mRemYrG%2BEorsc8nIdTahIVJks%2FwLgLuwVf6JRXz%2FLw%3D%3D%3C%2Fdiagram%3E%3C%2Fmxfile%3E)

![Data Modle](/../assets/images/a4/data_model.svg)

## Data Modeling

**concept: Authentication**  
purpose: log in/register a user  
state:  
`username`: User -> one String  
`password`: User -> one String

**concept: Sessioning[User]**  
purpose: enable authenticated actions for an extended period of time  
state:  
`session`: Session -> one User

**concept: Postings[Author, File]**  
purpose: share experiences and information  
state:  
`author`: Post -> one Author  
`file`: Post -> one File

**concept: Labeling[Item]**  
purpose: tag `Items`  
state:  
`tags`: Item -> (tag) set String  
`topics`: (topic) String -> (tag) set String

**concept: Citing[Item]**  
purpose: get sources to support `Item`  
state:  
`citations`: Content -> set String

## TrueTide

**TrueTide** is designed for _`international students`_ navigating new environments and cultures. Adjusting to life in a new country can be overwhelming, and students often struggle to find _`accurate`, `culturally relevant`_ information. **TrueTide** helps bridge that gap by providing a _`diverse`_ range of perspectives on controversial topics from national policies to local slang and customs.

The app's key feature is its **`DualView`**, which allows users to see opposing viewpoints on controversial topics, fostering critical thinking.
To support responsible information-sharing, **TrueTide** offers _`easy-to-use`_ fact-checking tools and recommends relevant **`Citations`** to users as they post content, making it simple to back up information. **TrueTide** offers a trusted and culturally aware platform, easing the transition for students as they learn more about their new surroundings.

<!-- **With features like _customized_ **`Feeds`** that adapt to cultural contexts, ????** -->

(May update more based on implementation needs)

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
