# FlashChat

FlashChat is from a tutorial by Angelu Yu with the focus on working with tableviews, one of the most fundamental component of modern iOS apps. Tableviews are used everywhere from mail apps to the Messages app. It’s a crucial part of every iOS developer’s tool belt. This tutorial taught everything with Table Views, creating custom cells, and making our own cloud-based backend database.

## Introduction

Flash Chat is an internet based messaging app similar to WhatsApp, the popular messaging app that was bought by Facebook for $22 billion. I used a service called Firebase Firestore as a backend database to store and retrieve our messages from the cloud, in addition to creating and verifying accounts while logging into the app.

## Skills used

* Cocoapods and Swift Package Manager
* Store data in the cloud using Firebase Firestore
* Query and sort the Firebase database
* Firebase for user authentication, registration and login
* Embed View Controllers in a Navigation Controller
* Create animations using loops

## Process and challenges

FlashChat had many components to worth through, including a welcome screen. To add a bit of flair, I added a typing animation to the named of the app using a for loop. Taking each letter of the app name, I was able to have them show up individually after each other by putting them into an array and displaying the contents of the array on a .3 second interval.

![Simulator Screen Recording - iPhone 14 Pro - 2023-02-08 at 16 25 27](https://user-images.githubusercontent.com/113778995/217665362-e4aaf6b8-3965-474a-885e-837b7a6f2c2d.gif)

In addition, IQKeyboardManager was used to have the view slide up when the keyboard was in use for text fields in the lower half of the screen to improve user experience.

Moving on to the register screen, FirebaseAuth was needed to make sure that users can create an account if they didn't have on in the database. It was a simply createUser method. The login view was nearly identical, simply needed to check the database to make sure that the username and password already existed.

![Simulator Screen Recording - iPhone 14 Pro - 2023-02-08 at 15 48 34](https://user-images.githubusercontent.com/113778995/217666154-71657194-4e4a-4fbc-8ea5-84e01785d6b3.gif)

The chat tableview is where the meat of the operation was. First I needed to make sure it was connected to the Firestore database to send and retrieve messages properly to each user account. Once that was finished, I created a function for loading all the messages from the database and to display them in the tableview in the center of the view. For each messages that was downloaded from the database, it appended it to an array that would populate the tableview. I then reloaded the tableview after loading the messages through the main thread.

In addition to loading all the messages, I needed a function that would send them to Firebase as well. That function sent the message text, sender and time so it could be sorted by recieved date.

With the Firebase Swift Package (or Cocoapod), creating these functions for sending and retrieving from the database required minimal amounts of code and were straightforward to learn and implement.

For the tableview, I created custom cells, which required to design them in a new storyboard file. This way I could add a image displaying who the sender was from, or which messages you sent, similar to a real messaging app. The custom cell had all three elements on at once, but programmatically I could hide one part if I sent it or recieved it (i.e., the bubble on the left wouldn't show if I sent the message, and the one of the right wouldn't if I recieved a message), allowing the text to stretch to fill the empty space left. 

<img width="370" alt="Screenshot 2023-02-08 at 4 40 16 PM" src="https://user-images.githubusercontent.com/113778995/217667624-12c35a23-5eab-4d50-bac3-591da1bae07e.png">

After all those tasks were completed, the finished app is a usable messaging app to send and recieve message with different user profiles.

![Simulator Screen Recording - iPhone 14 Pro - 2023-02-08 at 15 48 56](https://user-images.githubusercontent.com/113778995/217667948-52d222ea-c4f8-4f82-bd75-3b10418e3365.gif)


## Reflection

In addition to learning how to code and implement a database to store and retrieve messages, it was helpful to learn how to use the backend of a database, in this case the Firebase website and how to use the database itself. There was a lot in this tutorial that can be used in nearly any app that I might design in the future as messaging apps and tableviews are extremely commonplace nowadays. Needing a way to store and retrieve all that data just goes hand in hand as well.



