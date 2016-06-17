---
title       : Connecting to Teradata at eBay
description : This chapter will help you familiarise yourself with connecting R to Teradata in order to run SQL queries and get data into R dataframes.

--- type:VideoExercise lang:r xp:200 skills:1 key:f76c47fe1d

## Getting started with ebaytd

*** =video_link
https://player.vimeo.com/video/170761929

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## Which one of these is NOT required to use the ebaytd package?

*** =instructions
- An up to date Java Virtual Machine
- The RODBC package
- The RJDBC package
- A Teradata account

*** =hint
Remember the four steps - check out the ebaytd wiki page for more information.

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Well done! The RODBC package is not required - we choose to use the RJDBC package since it works more effectively across multiuple platforms (Windows, Mac and Unix)."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## Where should you go to get the latest version of the ebaytd package?

*** =instructions
- github.com
- CRAN
- wiki
- the hub

*** =hint
It is on an internal eBay site - that should help narrow it down!

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Exactly! This is an eBay specific package and is only available from the wiki - search for ebaytd to find the page."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_success, msg_bad, msg_bad)) 
```


--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## Which one of these is NOT a reason to call teradataInit()?

*** =instructions
- The first time I use ebaytd 
- When starting a new R session
- When my teradata password changes

*** =hint
teradataInit is designed to minimise the number of times you need to provide you Teradata credentials!

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Good job! Since Hopper is designed for interactive work we set that as the default.  You can override this using the system argument in teradataConnect()."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success, msg_bad)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## What is the default Teradata system that ebaytd connects to?

*** =instructions
- Mozart
- Vivaldi
- Hopper

*** =hint
Which is the system that is optimised for interactive queries rather than batch workloads?

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Exactly! This is an eBay specific package and is only available from the wiki - search for ebaytd to find the page."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad, msg_success)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## Does ebaytd() include functions to execute queries?

*** =instructions
- Yes
- No 

*** =hint
ebaytd() is only designed to make installing drivers and connecting to Teradata as easy as possible. 

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "That is right!  The ebaytd package has a dependency on the RJDBC package which implements the DBI methods (dbSendQuery and dbGetQuery) to allow you to submit queries - the function dbSendQuery and dbGetQuery are not part of the ebaytd package."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## If you want to run a SQL query and get the results back into an R dataframe which DBI method would you use?

*** =instructions
- dbSendQuery
- dbGetQuery
- dbDisconnect

*** =hint
The word 'get' in a function name usually means it returns data back to the calling program!

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "That's correct!  dbGetQuery() will return the results of the SQL query."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 2, feedback_msgs = c(msg_bad, msg_success,msg_bad)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## If you want to submit a CREATE TABLE query which DBI method would you use?

*** =instructions
- dbSendQuery
- dbGetQuery
- dbDisconnect

*** =hint
The word 'send' in a function name hints that this function does not fetch anything from the database!

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Spot on!  dbSendQuery() is typically used for submitting DDL (data definition language) queries - such as CREATE, DELETE, DROP, ALTER."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 1, feedback_msgs = c(msg_success, msg_bad, msg_bad)) 
```

--- type:MultipleChoiceExercise lang:r xp:50 skills:1
## When you are done and want to disconnect from Teradata what DBI method would you use?

*** =instructions
- dbSendQuery
- dbGetQuery
- dbDisconnect

*** =hint
I don't think you really need a hint!

*** =sct
```{r}
# The sct section defines the Submission Correctness Tests (SCTs) used to
# evaluate the student's response. All functions used here are defined in the 
# testwhat R package

msg_bad <- "That is not correct!"
msg_success <- "Exactly!  Once you call dbDisconnect() you will not be able to submit queries until you reconnect using teradataConnect()."

# Use test_mc() to grade multiple choice exercises. 
# Pass the correct option (Action, option 2 in the instructions) to correct.
# Pass the feedback messages, both positive and negative, to feedback_msgs in the appropriate order.
test_mc(correct = 3, feedback_msgs = c(msg_bad, msg_bad, msg_success)) 
```
