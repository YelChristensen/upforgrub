# EatOut

![App Screenshot](/react-ui/src/assets/screenshot.png)

## An app for finding safe places to eat nearby

**EatOut** is a mobile first web app for finding cafes, restaurants and canteens nearby and checking their food hygiene rating. Simply enter your postcode in the search field and get a list of venues nearest first. Alternative click "Use my location" and let the app do the rest. From the venue list you can click "Directions" to use google maps to navigate to your chosen venue.

## To see the MVP on Heroku, navigate here: https://safe-garden-52184.herokuapp.com/

### Techologies

The app was built using **"create-react-app"**. At the moment the app is only web-based. I used **React Hooks** for this project and **Material UI** for styling.

The app uses two open source **APIs** (no keys required). First, **https://postcodes.io/** checks if the entered postcode is valid. If it is, the second API call converts the user entered postcode into lat-long, then a list of venues and their food hygiene ratings is obtained from **https://api.ratings.food.gov.uk/**. As these APIs are open source, there is a limited number of calls that can be made in a certain period, so if you get an error 403, try again the next day.

This would have been a front-end only app, but I had to set up a proxy server in order to deal with CORS.

### Installation and set-up

Because this app is made of two npm projects, after the repo is cloned, there are two places to run `npm` commands:

1. Node API server at the root
2. React UI

#### Run the API server

In a terminal:

<pre><code>
#Initial setup
npm install

#Start the server
npm start
</code></pre>

#### Run the React UI

In a separate terminal from the API server, start the UI:

<pre><code>
#Always change directory, first
cd react-ui/

#Initial setup
npm install

#Start the server
npm start
</code></pre>

### How it works

The user is presented with a search field, where they can enter their postcode. The app first checks if the postcode is valid (first API call). The valid postcode is converted into lat-long coordinates (second API call), then fetches the list of 30 nearest restaurants, cafes and canteens and their food hygiene ratings sorted by distance (third API call).
Alternatively, the user can use geolocation option whereby the generated lat-long value pair is used to fetch the venue list and create google maps directions.

### Todos:

- add bars, pubs and takaways to the venue list
- write tests
