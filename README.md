# Node Inverview Project

Create a Node project utilizing Express and MongoDB that provides personalized weather information using OpenWeather. Users should be able to search weather anonymously but also able to create an account that allows them to save personal weather locations.

Project will utilize the following resources:
* Set up OpenWeather account at https://openweathermap.org/api to get an API key
* Use Heroku to host your app at https://www.heroku.com/home
* Use MongoDB to host your data at https://www.mongodb.com/cloud/atlas 

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
    - Route does note require return data
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
4. Ability to save location
    - Route should accept the following JSON:
    ```json
    {
      "city": String,
      "state": String,
      "zipCode": int,
    }
    ```
7. Ability to fetch saved weather [Need data structure]
8. Ability to fetch user data [Need data structure]
9. Ability to login [Need data structure]
10. Ability to view saved locations [Need data structure]
11. Ability to delete saved location [Need data structure]
12. Ability to delete account

Above routes should accept the following JSON:
1.  
```json
{
  "city": String
  "zipCode" int
}
```

Above routes should return the following JSON:
