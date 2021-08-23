# Node Inverview Project

Create a Node project utilizing Express and MongoDB that provides personalized weather information using OpenWeather. Users should be able to search weather anonymously but also able to create an account that allows them to save personal weather locations.

Project will utilize the following resources:
* Set up OpenWeather account at https://openweathermap.org/api to get an API key
* Use Heroku to host your app at https://www.heroku.com/home
* Use MongoDB to host your data at https://www.mongodb.com/cloud/atlas 

All routes below indicated with `^` are authenticated routes and need to validate the authorization header before returning any data or return a 401 response. All routes should return an appropriate response status. All routes should have testing in place utilizing Jest or Mocha.

Project should include routes that provide the following:
1. Ability to search weather by location using city or zip code
   - Route should accept the following JSON:
    ```json
    {
      "city": String
      "zipCode" int
    }
    ```
    - Route should return the following JSON:
    ```json
    {
      "current": {
        "temp": double,
        "low": double,
        "high": double,
        "icon": String
      },
      "tomorrow": {
        "temp": double,
        "low": double,
        "high": double,
        "icon": String
      },
      "dayAfterTomorrow": {
        "temp": double,
        "low": double,
        "high": double,
        "icon": String
      },
    }
    ```
2. Ability to create an account
    - Route should accept the following JSON:
    ```json
    {
      "email": String,
      "password": String,
    }
    ```
    - Route should validate the email and password
    - Route should return the following JSON:
    ```json
    {
      "token": String,
      "locations": [
        {
          "city": String,
          "state": String,
          "zipCode": int,
          "lat": double,
          "lng": double,
        }
      ],
    }
    ```
3. Ability to login
    - Route should accept the following JSON:
    ```json
    {
      "email": String,
      "password": String,
    }
    ```
    - Route should return the following JSON:
    ```json
    {
      "token": String,
      "locations": [
        {
          "city": String,
          "state": String,
          "zipCode": int,
          "lat": double,
          "lng": double,
        }
      ],
    }
    ```
4. ^Ability to save location
    - Route should accept the following JSON:
    ```json
    {
      "city": String,
      "state": String,
      "zipCode": int,
    }
    ```
    - Route does not require any return data
5. ^Ability to delete saved location
    - Route should accept these request parameters `userId` and `locationId`
    - Route does not require any return data
6. ^Ability to delete account
    - Route should accept the request parameter `userId`
    - Route should delete account along with all locations tied to the account

Two Mongoose Models should be utlized for this project:
- Users
    ```json
    {
      "email": String,
      "password": String,
    }
    ```
- Locations
    ```json
    {
      "_user": {
          type: Schema.Types.ObjectId,
          ref: "users",
      },
      "city": String,
      "state": String,
      "zipCode": int,
      "lat": double,
      "lng": double,
    }
    ```
