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



**Home** - A user is able to see others armies created by others users. 

**My Armies** - A user can see all the armies he has created.

**Create army** -  A user can build an army.

**Delete army** - A use is able to delete pet profile from their profile

**Edit armies** - A user is able to edit information of their pets to my profile based on a units catalog.

**Units** - A user can see characteristics skills about the units.





## Routes

| Name            | Method | Endpoint                      | Description                                      | Body                                  | Redirects       |
| --------------- | ------ | ----------------------------- | ------------------------------------------------ | ------------------------------------- | --------------- |
| Log in form     | GET    | /login                        | See the form to log in                           |                                       |                 |
| Log in          | POST   | /login                        | Log in the user                                  | {mail, password}                      | /               |
| Log out         | GET    | /logout                       | Log out a user                                   |                                       | /               |
| Sign Up form    | GET    | /signup                       | See the form to sign up                          |                                       |                 |
| Sign Up         | POST   | /signup                       | Sign up a user                                   | {mail, password}                      | /               |
| Home            | GET    | /                             | See the main page and armies list                |                                       |                 |
| Army add        | POST   | /army               | Build an army and saved                          |                                       |                 |
| army edit    | POST   | /army/:id | Edit profile army from user's  colection       |                                       |         |
| army delete  | DELETE   | /army/:id | Delete army                                 |                                       |         |
| get all army  | GET   | /army | find army                                 |                                       |         |
| get one army  | GET   | /army/:id | find one army                                 |                                       |         |


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
  },
  armies: [{ type: Schema.Types.ObjectId, ref: 'Army' }],
  }
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

