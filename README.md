# EatOut

![App Screenshot](/src/screenshot.png)

## An app for finding safe places to eat nearby

**EatOut** is a mobile first web app for finding cafes, restaurants and canteens nearby and checking their food hygiene rating. Simply enter your postcode in the search field and get a list of venues nearest first.

## To see the MVP on Heroku, navigate here: https://safe-garden-52184.herokuapp.com/

### Techologies

The app was built using **"create-react-app"**. At the moment the app is only web-based. I used **React Hooks** for this project and **Material UI** for styling.

The app uses two open source **APIs** (no keys required). First, **https://postcodes.io/** converts the user entered postcode into lat-long, then a list of venues and their food hygiene ratings is obtained from **https://api.ratings.food.gov.uk/**. As these APIs are open source, there is a limited number of calls that can be made in a certain period, so if you get an error 403, try again the next day.

### Installation and set-up

- clone the repo and run `yarn` to donwload dependencies.
- run `yarn start` to launch and navigate to localhost:8080 to view in your browser.

### How it works

The user is presented with a search field, where they can enter their postcode. The app converts the postcode into the lat-long coordinates (first API call), then fetches the list of 30 nearest restaurants, cafes and canteens and their food hygiene ratings sorted by distance (second API call).

### Todos:

- Postcode validation on the search field
- Google Maps API to plot venus on the map
- Autocomplete address on the search field (also using Google Maps API)
- Write tests
