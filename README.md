# Project's name

Warhammer Tactics

## Description

Listado de organizacion de ejércitos Warhammer.

## Pages

**404** - 404 page when page doesn’t exist.

**Initial page** - The homepage to see what the app is all about with login and signup.

**Sign up** - A user can sign up with email.

**Login** - A user is able to log in on the webpage so user can get back to their account

**Logout** - A user is able to log out from the webpage/account



**Profile** - A user is able to see his profile and edit it or delete it.

**Delete profile** - A use is able to delete pet profile from their profile

**Update discription** - A user is able to update the information of their pets

**Edit armies** - A user is able to edit information of their pets to my profile based on a units catalog.



**Home** - A user is able to see others armies created by others users. 

**History** - A user can read a history about the faction selected.

**Units** - A user can read information about each unit from their faction.

**Army** - A user can build an army.


## Routes

| Name            | Method | Endpoint                      | Description                                      | Body                                  | Redirects       |
| --------------- | ------ | ----------------------------- | ------------------------------------------------ | ------------------------------------- | --------------- |
| Log in form     | GET    | /login                        | See the form to log in                           |                                       |                 |
| Log in          | POST   | /login                        | Log in the user                                  | {mail, password}                      | /               |
| Home            | GET    | /                               See the main page                                |                                       |                 |
| Log out         | GET    | /logout                       | Log out a user                                   |                                       | /               |
| Sign Up form    | GET    | /signup                       | See the form to sign up                          |                                       |                 |
| Sign Up         | POST   | /signup                       | Sign up a user                                   | {mail, password}                      | /
| Profile army    | GET    | /profile                      | See the profile page with editable form          |                                       |                 |
| Profile edited  | POST   | /profile                      | Send user's data changed                         | {user_email, password}                | /profilearmy     |
| Profile army delete    | POST   | /army_id/army/army_id/delete| Delete profile army from user's  colection  |                                       | /profilearmy  |

## Models

-User model

```javascript
 { username: String,
  email: {
    type: String,
    required: true,
    unique: true,
  },
  hashedPassword: {
    type: String,
    required: [true, 'password is required'],
  },}
```  

-Army model 
```javascript
 { faction: [imperial, dwarfs, elves, orks, skavens],
  { category: [ heroes, generals, infantry, cavalry, artillery ]
  }
```

