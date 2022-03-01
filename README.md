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

**Army** - A user can build an army.


## Routes

| Name            | Method | Endpoint                      | Description                                      | Body                                  | Redirects       |
| --------------- | ------ | ----------------------------- | ------------------------------------------------ | ------------------------------------- | --------------- |
| Log in form     | GET    | /login                        | See the form to log in                           |                                       |                 |
| Log in          | POST   | /login                        | Log in the user                                  | {mail, password}                      | /               |
| Log out         | GET    | /logout                       | Log out a user                                   |                                       | /               |
| Sign Up form    | GET    | /signup                       | See the form to sign up                          |                                       |                 |
| Sign Up         | POST   | /signup                       | Sign up a user                                   | {mail, password}                      | /               |
| Home            | GET    | /                             | See the main page and armies list                |                                       |                 |
| Army add        | POST   | /faction/armyId               | Build an army and saved                          |                                       |                 |
| Profile edited  | POST   | /userID/profile/edit          | Send user's data changed                         | {user_email, password}                | /profile        |
| Profile deleted | POST   | /userID/profile/delete        | User's data deleted                              |                                       | /login          |
| Profile army edit    | POST   | /userID/profile/armyID/edit| Edit profile army from user's  colection       |                                       | /profile        |
| Profile army delete  | POST   | /userID/profile/armyID/delete | Delete army                                 |                                       | /profile        |

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
 { heroe: {type: String, enum: ["Thorgrim" , "Ungrim"]},
   general: {type: String, enum: ["Maestro Ingeniero", "Herrero Rúnico", "Señor del Clan"]},
   infantry: {type: String, enum: ["Guerreros Enanos", "Rompehierros", "Barbaslargas", "Matadores", "Mineros", "Ballesteros", "Atronadores", "Dracohierros"]},
   artillery: {type: String, enum: ["Lanzaagravios", "Cañón", "Cañón órgano", "Lanzallamas", "Girocóptero", "Girocóptero bombardero"]},
   name: String,
   advice: String,
 }
```

