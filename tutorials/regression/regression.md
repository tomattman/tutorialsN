---
title: MY_2205
description: example
tags: [ tutorial>MarinaTag, tutorial>beginner, tutorial>QA-lushneuski ]
primary_tag: tutorial:product/mobile
---



[ACCORDION-BEGIN [STEP 1](Accordion component which contains Images in Body)]
    
First Header | Second Header | Third Header | Fourth Header | Fifth Header | Sixth Header
------------ | ------------- | ------------ | ------------- | -------------| -------------
Content from cell 1 | Content from cell 2 | Content from cell 3 | Content from cell 4 | Content from cell 5 | Content from cell 6
Content.js in the first column | Content in the second column | Content in the third column | Content in the fourth column | Content in the fifth column | Content in the sixth column

[DONE]
[ACCORDION-END]




[ACCORDION-BEGIN [STEP 12](Accordion component which contains code block and no code block in Body)]
***Code blocks:***

**Example:sql** 
```sql
CREATE KEYSPACE videodb WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 1 };

use videodb;

// Basic entity table
// Object mapping ?
CREATE TABLE users (
   username varchar,
   firstname varchar,
   lastname varchar,
   email varchar,
   password varchar,
   created_date timestamp,
   total_credits int,
   credit_change_date timeuuid,
   PRIMARY KEY (username)
);

// One-to-many entity table
CREATE TABLE videos (
   videoid uuid,
   videoname varchar,
   username varchar,
   description varchar, 
   tags list<varchar>,
   upload_date timestamp,
   PRIMARY KEY (videoid)
);

// One-to-many from the user point of view
// Also know as a lookup table
CREATE TABLE username_video_index (
   username varchar,
   videoid uuid,
   upload_date timestamp,
   videoname varchar,
   PRIMARY KEY (username, videoid)
);

// Counter table
CREATE TABLE video_rating (
   videoid uuid,
   rating_counter counter,
   rating_total counter,
   PRIMARY KEY (videoid)
);

// Creating index tables for tab keywords
CREATE TABLE tag_index (
   tag varchar, 
   videoid uuid,
   timestamp timestamp,
   PRIMARY KEY (tag, videoid)
);

// Comments as a many-to-many 
// Looking from the video side to many users
CREATE TABLE comments_by_video (
   videoid uuid,
   username varchar,
   comment_ts timestamp,
   comment varchar,
   PRIMARY KEY (videoid,comment_ts,username)
) WITH CLUSTERING ORDER BY (comment_ts DESC, username ASC);

// looking from the user side to many videos
CREATE TABLE comments_by_user (
   username varchar,
   videoid uuid,
   comment_ts timestamp,
   comment varchar,
   PRIMARY KEY (username,comment_ts,videoid)
) WITH CLUSTERING ORDER BY (comment_ts DESC, videoid ASC);


// Time series wide row with reverse comparator
CREATE TABLE video_event (
   videoid uuid,
   username varchar,
   event varchar,
   event_timestamp timeuuid,
   video_timestamp bigint,
   PRIMARY KEY ((videoid,username), event_timestamp,event)
) WITH CLUSTERING ORDER BY (event_timestamp DESC,event ASC);
```


[DONE]
[ACCORDION-END]

