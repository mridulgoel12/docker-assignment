# Webapp

We're in trouble. We have a tight deadline, and our developer decided to go
on vacation without finishing what he was supposed to do!
Now, it's your time to save the day. Please help us with the following.

**NOTE**
If you see anything that can be improved (i.e., bad practices), please change
it! Feel free to change as much as you want to demonstrate your strong skills.

1. Starting up the application seems to crash. We're working with a heavy
   big-data database that takes time to boot.

   --- Added logic in Dockerfile to wait for db to be available.

2. Look at the mess he left in the `Dockerfile`, it needs some love.

   --- Updated Dockerfile according to the best practices.
       (Lighter image, combining dependencies, minimizing layers)

3. Seems like the developer needed to learn how to configure his
   application correctly.

   --- Implemented the missing logic in take_home.py

4. He forgot to implement the descendant's route! We were expecting to get
   something like the following:
    ```
    # This is a valid example.
    > GET /moments/28/descendants
    < Away
    < Business Travel Moments
    <         Business Trip Moment
    < Vacation Travel Moments
    <         Airport Moment
    <         Hotel Moment
    <         Traveling Moment
    <         Vacation Health & Fitness Moment
    <         Vacation Nightlife Moment
    <         Vacation Restaurant Moment
    <         Vacation Shopping Moment
    <         Vacation Sports Moment
    <         Weekend Getaway Moment

    # This solution would be valid too.
    > GET /moments/28/descendants
    < Away
    <     Vacation Travel Moments
    <             Weekend Getaway Moment
    <             Vacation Sports Moment
    <             Vacation Shopping Moment
    <             Vacation Restaurant Moment
    <             Vacation Nightlife Moment
    <             Vacation Health & Fitness Moment
    <             Traveling Moment
    <             Hotel Moment
    <             Airport Moment
    <     Business Travel Moments
    <             Business Trip Moment

    # However, this solution is **not valid.**
    > GET /moments/28/descendants
    < Away
    <     Business Travel Moments
    <     Vacation Travel Moments
    <             Business Trip Moment
    <             Weekend Getaway Moment
    <             Vacation Sports Moment
    <             Vacation Shopping Moment
    <             Vacation Restaurant Moment
    <             Vacation Nightlife Moment
    <             Vacation Health & Fitness Moment
    <             Traveling Moment
    <             Hotel Moment
    <             Airport Moment

    # These two are also valid examples.
    > GET /moments/67/descendants
    < Home Chores Moments
    <     Working from Home Moment
    <     Managing Finances Moment
    <     DIY Moment
    <     At-Home Workout Moment

    > GET /moments/101/descendants
    < Running Errands Moment
    ```
