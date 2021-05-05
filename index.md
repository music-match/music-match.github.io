# Table of Contents
- [Overview](#overview)
- [Approach](#approach)
- [Deployment](#deployment)
- [Developer Guide](#developer-guide)
- [User Guide](#user-guide)
- [Development History](#development-history)
- [Community Feedback](#community-feedback)
- [Meet the Developers](#meet-the-developers)

# Overview

### The Problem
Many UH students have musical talents, but there is no easy way for them to find others with similar tastes and compatible musical abilities. Thus, they cannot experience the fun of informal jam sessions which could progress into performing musical groups.

### The Solution
The [Music Match](https://github.com/music-match/music-match) application developed by [Music Match Inc.](https://github.com/music-match) allows students to login and create a profile indicating their musical tastes, their musical capabilities, and their musical goals (from occasional, informal jam sessions to performing bands). Users can share their own jam sessions through Youtube links to a Youtube video to their own jam.

# Approach
Once a profile is created, others can browse the profiles filtered by specific tastes, capabilities, and goals to find compatible musicians to contact.

Students can also set up notifications to find out automatically when a profile is created that satisfies criteria that they specify.

Admins can monitor the site for inappropriate content, and create new categories of musical tastes, capabilities, and goals.

Some mockup pages include:
- Landing Page
- User home Page
- About Us Page
- User profile Page
- Edit Profile Page
- Browse Jams by other users
- Browse users by name or musical interests.

# Deployment

The [Music Match Website](http://143.198.236.70/) is available live!

![ci-badge](https://github.com/music-match/music-match/workflows/ci-music-match/badge.svg)

# Developer Guide

## Installation
- First, [install meteor](https://www.meteor.com/developers/install).
- Second, download the [Music Match Repo](https://github.com/music-match/music-match) into your local system.
- Third, open a terminal and navigate into the music-match/app directory.
- Fourth, install the required meteor libraries by typing the following into the terminal:

```
$ meteor npm install
```

## Running the Application
- Upon completion of the installation process, ensure you are still in the music-match/app directory and enter the following into the terminal:

```
$ meteor npm run start
```

- If this is your first time starting the application, it will create the default data. This should be the output:

```
=> Started proxy.
=> Started MongoDB.
W20210424-15:39:27.766(-10)? (STDERR) Note: you are using a pure-JavaScript implementation of bcrypt.
W20210424-15:39:27.867(-10)? (STDERR) While this implementation will work correctly, it is known to be
W20210424-15:39:27.867(-10)? (STDERR) approximately three times slower than the native implementation.
W20210424-15:39:27.867(-10)? (STDERR) In order to use the native implementation instead, run
W20210424-15:39:27.867(-10)? (STDERR) 
W20210424-15:39:27.868(-10)? (STDERR)   meteor npm install --save bcrypt
W20210424-15:39:27.868(-10)? (STDERR) 
W20210424-15:39:27.868(-10)? (STDERR) in the root directory of your application.
I20210424-15:39:28.646(-10)? Creating the default user(s)
I20210424-15:39:28.646(-10)?   Creating user ethanwc@hawaii.edu.
I20210424-15:39:28.818(-10)?   Creating user garcia77@hawaii.edu.
I20210424-15:39:28.968(-10)?   Creating user icce@hawaii.edu.
I20210424-15:39:29.115(-10)?   Creating user ajp808@hawaii.edu.
I20210424-15:39:29.263(-10)?   Creating user john@foo.com.
I20210424-15:39:29.430(-10)? Creating default profiles.
I20210424-15:39:29.430(-10)?   Adding: Philip Johnson (john@foo.com)
I20210424-15:39:29.434(-10)?   Adding: Ethan Chee (ethanwc@hawaii.edu)
I20210424-15:39:29.436(-10)?   Adding: Preston Garcia (garcia77@hawaii.edu)
I20210424-15:39:29.437(-10)?   Adding: Isaiah Eusebio (icce@hawaii.edu)
I20210424-15:39:29.438(-10)?   Adding: Adam Parrilla (ajp808@hawaii.edu)
I20210424-15:39:29.440(-10)? Creating default Music Interests.
I20210424-15:39:29.453(-10)? Creating default Jams.
I20210424-15:39:29.468(-10)? Creating default Featured Jam.
I20210424-15:39:29.477(-10)? Creating list of Possible interests.
I20210424-15:39:29.533(-10)? Monti APM: completed instrumenting the app
=> Started your app.

=> App running at: http://localhost:3000/
   Type Control-C twice to stop.
   
```
Ignore “bcrypt warning”: Bcrypt is used for password checking and it is safe to ignore the warning during development stages.

- You can now open up your app on a webpage at: [http://localhost:3000/](http://localhost:3000/)
- To reset the app, exit meteor by pressing Control-C into the terminal, and type:

```
$ meteor reset
```

# User Guide
These will be the mockup pages that will be used as a basis for this final project.

## Landing Page
<img src="images/landing-page.png">

Upon entering the site, the user has the ability to:
- Login to their previously created account
- Register and create a new account
- Visit the About Us Page
- View the News and Events of the website
- Watch the Featured Jam 

## Create Profile Page
<img src="images/create-profile-page.png">

When a new user registers an account, they will be redirected to create their profile. New users must finish creating their profile before gaining access to the entirety of the site.

At the minimum, new users must enter information in the required fields:
- Name
- Image URL
- Goals
- Music Skill Level

If the user does not fill out any required fields, an error message appears upon clicking the Submit button.

## User Home Page

The first variation of the home page involves an existing profile for the logged in user. A preview of this page is shown below:
<img src="images/home-page.png">

Upon logging in, the user has the ability to:
- Do anything from the landing page
- View their [own profile](#profile-page)
- Visit the [Browse Users page](#browse-users-page)
- View [all the jams](#browse-jams-page) shared by other users, view [own jams](#my-jams-page) they shared, and [create new jams](#create-jams-page)
- If the user is an admin, they will be able to navigate to the admin pages: [Browse Users (Admin)](#browse-users-admin-page) and [Browse Jams (Admin)](#browse-jams-admin-page)

The second variation of the home page is only displayed when a user logs in with no profile setup in the system. A preview of this page is shown below:
<img src="images/home-page-no-profile.png">
Typically, this page is only seen if the user recently registered an account or if their profile was deleted by an admin.

Upon logging in, the user has the ability to:
- Do anything from the landing page
- Visit the [Create Profile page](#create-profile-page)

## Profile Page
<img src="images/view-profile.png">

This page will be an exploded version of a single user, containing more information such as:
- Name
- Physical Address
- Phone
- Email Address
- Goals
- Instruments that they play
- Music Interests
- Music Skill Level

If the profile belongs to the user logged in, they will be able to:
- Edit their Profile
- Delete their Profile. There will be a secondary confirmation before deleting a profile.

## Edit Profile Page
<img src="images/edit-profile.png">

This will edit the profile information for a user, which contain edit fields for:
- Name
- Physical Address (optional)
- Phone (optional)
- Image URL
- Goals
- Instruments that they play
- Music Interests
- Music Skill level

## Browse Users Page
The Browse Users page allows users to view a snapshot of other user profiles and easily search for users by name or music interest.
<img src="images/browse-users.png">

User profiles are displayed on cards that contain the following information:
- Name
- Email Address
- Goals
- Music Interests
- Profile Picture
- "View Profile" button

The "View Profile" button takes the user to the profile page of the card it was clicked on. This page is similar to the [My Profile](#profile-page) page except that the user cannot edit or delete the profile if they are not the owner.

Users can search for profiles by typing a name or music interest in the search bar. The page will automatically display profiles that adhere to the criteria specified by the search bar.

## Browse Jams Page
The Browse Jams page allows users to view jams posted by other users and easily search for jams by title or description.
<img src="images/browse-jams.png">

Jams are displayed on cards where users have the ability to:
- Play the embedded YouTube video
- View the jam recommender
- Like the jam
- Comment on the jam

Upon clicking on the owner of the jam in the "Recommended By" section, the user will be redirected to the owner's profile page. This page is similar to the [My Profile](#profile-page) page except that the user cannot edit or delete the profile if they are not the owner.

Users can search for jams by typing the title or description of the jam in the search bar. The page will automatically display jams that adhere to the criteria specified by the search bar.

## My Jams Page
The My Jams page displays all the jams owned by the user.
<img src="images/my-jams.png">

Jams are displayed on cards that contain the following information:
- Jam Title
- Embedded YouTube video
- Description
- Owner of the jam
- "Edit" button
- "Comments" button
- "Delete" button

This page is similar to the [Browse Jams](#browse-jams) page in that the cards of the jams contain the same information with additional features to "Edit" and "Delete" the jam.

If the user has not shared any jams to the site, a page will be displayed notifying them that they do not have any jams and a button to redirect them to share a jam:
<img src="images/no-jams.png">

## Liked Jams Page
<img src="images/liked-jams-page.png">

This page displays the cards of all the jams the user has liked. Unliking jams on will remove it from this page.

This page is similar to the [Browse Jams](#browse-jams) page in that the cards of the jams contain the same information.

If the user did not like any jams, a page will be displayed notifying them that they do not have any liked jams and a button to redirect them to browse all the jams:
<img src="images/no-liked-jams.png">

## Create Jams Page
<img src="images/create-jams.png">

This will allow you to create a jam, which requires the three fields for a jam:
- Title
- Youtube Video Link
- Description

## Comment Modal
<img src="images/comment-modal.png">

Each jam has a comment functionality. A modal pops up that allows users to:
- Read comments posted by other users on that jam
- Post comments
- Delete their own comments
- Admins can delete all comments

## Browse Users Admin Page
<img src="images/users-admin-page.png">

In this page, admin users have the ability to:
- View all profiles
- Edit and delete profiles

## Browse Jams Admin Page
<img src="images/jams-admin-page.png">

In this page, admin users have the ability to:
- View all jams
- Edit and delete jams
- View the comments for that jam
- Change the Featured Jam to be displayed in the Landing/Home Page

## About Us Page
<img src="images/about-us-page.png">

In this page, viewers have the ability to: 
- Read more about Music Match
- Visit the Project Page
- Read a short bio about the developers
- Link to developers Github and LinkedIn

# Development History

- Goals of [Milestone 1](https://github.com/music-match/music-match/projects/1): Create Mockup Pages, start Front-End Development, and Initial Deployment
- Goals of [Milestone 2](https://github.com/music-match/music-match/projects/2): Significantly improve functionality of app, continue Front-End Development
- Goals of [Milestone 3](https://github.com/music-match/music-match/projects/3): Significantly improve functionality of app from M2, find at least five UH community members to test site, implement acceptance testing 

# Community Feedback

> I like how it is simple to use and is quick, user friendly, and has a cool name. I am not a fan of the color scheme, particularly the orange with black. I think the black is fine, but maybe not the orange. Also add a dislike button! I'm using this on safari and I couldn't play the youtube videos on the site. I had to open it on youtube. Good job!

— Tamah Tyau, Biology

> I like how you can meet new people and share interesting music that you think others may like. I suggest to add the ability to tag songs when adding them similar to how you made your personal interests, the ability to sort songs differently (alpha, latest posted, most likes, by poster, etc.), further the comment section (comment on a comment), a miniplayer in the background so that you can explore the rest of the site while listening to one song.

— Evan Kawaoka, Economics

> I like the nice interface, cute bear gif, and layout of the jams are well sized. The signout page could use touchups (ex. background pictures). I suggest finding a way to tell the user to login/signup to use the site. When creating an account, have short descriptions/directions for each box. Have a big "browse jams" on the home page since its the main focus of the site. Allow user to apply genre filters when uploading jams. Sort jams by likes, genre. Not sure how featured video is picked but ideas could be random, by likes, trending etc.

— Kenton Wong, Mechanical Engineering

> I like the simplicity of the overall website, very straight forward. Being nitpicky, I don't like how the icons on the home page aren't links that can be clicked on to direct you to 'Jams' for example. I suggest making the heart logo and 'Music Match' one home page button instead of two separate buttons. When a comment is made on a song can you show how many comments are on the song similar to how many likes there are on a song. Could you make it so that even if you don't have an account you can see what other people posted, but you need an account to post stuff and like and comment and things like that. The website is easy to navigate but some guidance on the homepage may make it easier for people that are using the website for the first time. Maybe make a way to chat with other people. Since this website is to meet other people with similar musical taste a chat function would be nice to have everything done on the website, but is unnecessary. But would be really cool.

— Scott Yuk, Information and Computer Sciences

> Having the ability to add a YouTube link to a Jam is pretty cool. However, there is no pagination of Jams, therefore as the database of Jams increases, the longer I will need to scroll. If I give a really long description, then the card that's associated with that Jam will be huge. Pretty nice, I think the image in the landing page is bit too blurry and the word "Music Match" can just have a transparent background.

— Jeff Wong, Information and Computer Sciences

# Meet the Developers

- [Preston Garcia](https://prestontgarcia.github.io/)
	- In this project, I hope to experience working with a team while following the agile project management model. I also hope to hone my frontend and backend website development skills through the creation of our website.
- [Ethan Chee](https://ethancheez.github.io/)
	-  I would like to be able to design a website from scratch quickly, containing many features and user interfaces.
- [Isaiah Eusebio](https://icce2k.github.io/)
	-  I would like to gain more experience in app development and working with Meteor and React. Also, I would like to develop my teamwork and project management skills. 
- [Adam Parrilla](https://adamjparrilla.github.io/)
	- I’d like to work on adapting web designs to use the things we’ve learned to create a website. I’d also like to gain experience working with a group to design a project and expand my portfolio. 

