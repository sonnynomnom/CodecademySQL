# Codecademy - [Learn SQL](https://www.codecademy.com/learn/learn-sql)

### Final Projects

**Kickstarter** (press@kickstarter.com)

- Andrew Nicols, Senior Data Analyst (anicols@kickstarter.com)

**Warby Parker** Final Project (styles & pricing, customer & purchases)
 
- Maddie Tierney (maddie.tierney@warbyparker.com)
	EA to the CTO
- Ryan Tuck, Sofware Engineer, Data Engineering Team (ryan.tuck@warbyparker.com)
  - Runs their internal SQL course 
  
**Twitch** Final Project (Games) 

- Zach is sending email

**Coinbase** 

- Zach send out an email

**HackerNews** (hn@ycombinator.com)

- Scott Bell, Moderator Software (scott@ycombinator.com)
  - "We’ve been a little swamped."
  - It’s fine to use the HR logo as long as it’s clear that it’s not an official YC or HN project. It’s not that we mind being associated, we just can’t handle any extra support emails! ;)


**Magic Leap** (VR apps)

- Ye Lu, Strategic Finance Manager (lye@magicleap.com)
  - (~3 years and college friend)
  - Marketing is interested but wants Codecademy user data

**Twitch** Final Project (Games) 

- Zach is sending email

**Coinbase** 

- Zach send out an email

**Buffer** 

- Hailley Giffis, Public Relations Manager (hailley@bufferapp.com)
- Michael Erasmus, Data Lead (michael@buffer.com)

**BuzzFeed**

- Headlines Queries/Aggregates Project
  - Eugene forward email

**The Met** 				#analyst

**Meetup**

- (Sonny/Catherine) 	#business

**Airbnb**

- (Catherine) (contact.press@airbnb.com)

- Wall Street Journal (headlines)
- The New York Times (headlines)
- Spotify
- Netflix
- The New Yorker

NY-Based Companies

- **Venmo** (press@venmo.com)
- **OkCupid** (press@okcupid.com)
- Seamless
- New York Post
- FreshDirect
- Etsy
- Squarespace
- Compass
- Justworks
- Vimeo
- opendata.cityofnewyork.us

Headlines Project
- **TechCrunch** (advertise@techcrunch.com, joey@techcrunch.com)
- **Hacker News** (hn@ycombinator.com)
- **Reddit** (licensing@reddit.com, press@reddit.com)
- **The New Yorker** (mediarequests@newyorker.com)

---

**Sample Email**

Dear Coinbase,

My name is Sonny, and I develop curriculum for Codecademy, the best place for folks to learn to code and upskill their career.

We are currently building an introductory course on database usage, focusing on the language SQL. One of the main reasons that we have 45+ million users, is that learners know we offer courses that are relevant to their work. We think that using datasets from real companies like Coinbase will make this course more powerful and help our students achieve their goals.

🏅 **Ask:** We'd like to collaborate with you and your data team to incorporate some small (no more than 2000 rows) anonymized, non-confidential data into this course. For example, some tables of ledger/transaction data or even Bitcoin/Ethereum value data? Something to perform basic queries and aggregates on. If you would like this to be a final project, then maybe even joins on multiple tables.

If a dataset is too high-lift, we'd love to include a video of someone from your company discussing how they use SQL in their work. This would help our students see the value of what they're learning.

**By sharing data or video with us:**

We would cite Coinbase. Your feature would live on our evergreen course content plus our paid Intensive landing page that we feature to our 45+ million users.
Tweet/Blog about the collaboration to our 500k Twitter and 650k Facebook and send an email to our full email list at the beginning of May.
Open up future partnerships in our upcoming Blockchain and Machine Learning courses.
Most importantly, you'll be helping tens of millions of eager learners develop job-ready skills and build a better tomorrow.

**Next step: I will be the point of contact and I would love to answer questions from your data/marketing team and even brainstorm together to create a compelling next level SQL project.

Looking forward to hearing back,

Sonny Li

Curriculum Developer
Codecademy

575 Broadway, New York, NY | (330) 622-2307




# Warby Parker 👓

customers

```sql
sqlite>CREATE TABLE customers (
   'id' INTEGER,
   'first' TEXT,
   'last' TEXT
);
   
.mode csv

.import /Users/sonny/Desktop/warby/customers.csv customers
 
.schema
```

transactions

```sql
sqlite>CREATE TABLE transactions (
   'id' INTEGER,
   'customer_id' INTEGER,
   'date' DATE
);
   
.mode csv

.import /Users/sonny/Desktop/warby/transactions.csv transactions
 
.schema
```

transaction_items
```sql
sqlite>CREATE TABLE transaction_items (
   'transaction_item_id' INTEGER,
   'transaction_id' INTEGER,
   'item_id' INTEGER,
   'color_id' INTEGER,
   'quantity' INTEGER
);
   
.mode csv

.import /Users/sonny/Desktop/warby/transaction_items.csv transaction_items
 
.schema
```

items

```sql
sqlite>CREATE TABLE items (
   'id' INTEGER,
   'name' TEXT,
   'price' INTEGER
);
   
.mode csv

.import /Users/sonny/Desktop/warby/items.csv items
 
.schema
```


```sql
sqlite>CREATE TABLE colors (
   'id' INTEGER,
   'name' TEXT
);
   
.mode csv

.import /Users/sonny/Desktop/warby/colors.csv colors
 
.schema
```

## Marketing Funnels

home_try_on

```sql
sqlite>CREATE TABLE home_try_on (
   'user_id' TEXT,
   'number_of_pairs' TEXT,
   'address' TEXT
);
   
.mode csv

.import /Users/sonny/Desktop/warby-parker/home_try_on.csv home_try_on
 
.schema
```

purchase

```sql
sqlite>CREATE TABLE purchase (
   'user_id' TEXT,
   'product_id' INTEGER,
   'style' TEXT,
   'model_name' TEXT,
   'color' TEXT,
   'price' INTEGER
);
   
.mode csv

.import /Users/sonny/Desktop/warby-parker/purchase.csv purchase
 
.schema
```

quiz

```sql
sqlite>CREATE TABLE quiz (
   'user_id' TEXT,
   'style' TEXT,
   'fit' TEXT,
   'shape' TEXT,
   'color' TEXT
);
   
.mode csv

.import /Users/sonny/Desktop/warby-parker/quiz.csv quiz
 
.schema
```

survey

```sql
sqlite>CREATE TABLE survey (
   'question' TEXT,
   'user_id' TEXT,
   'response' TEXT
);
   
.mode csv

.import /Users/sonny/Desktop/warby-parker/survey.csv survey

 
.schema
```
