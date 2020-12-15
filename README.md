# hw18-PWA  - Budget Tracker

## Summary

This assignment involved building routes and models to supplement front-end code already provided for a fitness tracking application so that it is intended to be fully functional. However, there was a bug in the workout accumulator which tallies all the exercises where duration was omitted - it took a while to find that defect and fix it in the provided front-end workout.js file.

The front-end code had already been built and a directory structure for the html, js for that was provided. Functionally, the provided code enabled entry, saving and update of workouts plus the ability to visualize previously entered workouts via a dashboard. But the application lacked middleware integration with a datbase, and the focus of the assignment was to define the schema, build the Express model and routes, leveraging Mongoose in conjunction with a Mongo database deployed on Heroku.

The application is fully functional and deployed on Heroku and this link: https://fitness-trakker.herokuapp.com. Here is a screen shot of the working application's dashboard :

![img](https://github.com/fhsal/hw17-fitnessTracker/blob/main/fitness-tracker-dashboard-screenshot.jpg)

Several components are used in the application, built around the MVC structure provided where front-end code for html, js and data are stored within the 'public' folder structure. A seed file was also provided. I added several directories and files to the app to drive the app, define schema, set routes and models, they are:

(1) server.js drives the app setup by requiring express, mongoose and path; setting up the ports for local and Heroku serving, app.use configuration, mongo connection, required routes and listner to start the server.

(2) index.js and workout.js provide the models for the app. workout.js defines the schema and exports the model as Workout using Mongoose to build the model.

(3) html routes are driven by htmlRoutes.js which defines the endpoints for the three pages in the app: index.html for the home page, excercise.html for workout entry and update and stats.html for the dashboard.

(4) api routes are driven by apiRoutes.js which requires the workout model and defines the endpoints for get/post/put workouts, which largely involve storing and retrieving json objects from the mongo database 'workout' table 'workouts'; put involves individual excercises while post and get involve storing an entire workout or retrieving all workouts via a separate route called '/api/workouts/range' where the range is always all workouts.

---

## User Story

- As a user, I want to be able to view create and track daily workouts. I want to be able to log multiple exercises in a workout on a given day. I should also be able to track the name, type, weight, sets, reps, and duration of exercise. If the exercise is a cardio exercise, I should be able to track my distance traveled.

## Business Context

A consumer will reach their fitness goals more quickly when they track their workout progress.

## Acceptance Criteria

When the user loads the page, they should be given the option to create a new workout or continue with their last workout.

The user should be able to:

- Add exercises to a previous workout plan.

- Add new exercises to a new workout plan.

- View the combined weight of multiple exercises on the `stats` page.
