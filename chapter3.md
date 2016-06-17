---
title       : Upload data to TeraData - teradataFastload
description : In this chapter you will find out how to push data into Teradata from R
attachments :
  slides_link : https://s3.amazonaws.com/assets.datacamp.com/course/teach/slides_example.pdf

--- type:VideoExercise lang:r xp:50 skills:1 key:f76c47fe1d

## Introduction to teradataFastload

*** =video_link
https://player.vimeo.com/video/170761929

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## Where do you get the latest version of the ebaytd package?

*** =instructions
- github.com
- CRAN
- wiki
- the hub

*** =hint
It is on an internal eBay site - there are only two in that list!

*** =sct
```{r}
msg_bad <- "That is not correct!"
msg_success <- "Exactly! This is an eBay specific package and is only available from the wiki - search for ebaytd to find the page."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad)) 
```