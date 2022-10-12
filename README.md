# Formula1 - Project 2

## Overview
“Formula 1 - Season Results” is a result of a 48-hour paired “React Hackathon” where it was required to create a front-end React app that consumes a public API. It took place two weeks after being introduced to React and API requests using Axios and three days after being introduced to React Routers.

I have worked with Milly Arkwright to create an app that tracks and displays information about the current season of Formula1. It consumes two public API, the Ergast Developer API for season schedule and stats, and Api-Formula-1 for the driver’s images.

## Deployment Link
Here is the link to the deployed version of the Formula 1 seasons tracker: 
https://formula1-seasonresults.netlify.app/

## Technologies Used 
- React.js 
- Axios 
- JavaScript (ES6)
- HTML5
- CSS3
- Sass
- React Bootstrap
- Git
- GitHub
- VSCode
- Netlify
- Google Chrome Dev Tools
- Google Fonts

## Planning
We started planning by brainstorming and searching for multiple APIs that both of us are interested in, and for APIs with documentations and formats that we could work with. We both decided to create an app that would be useful for F1 fans using an API with data about F1. We then went through the documentation of the API we chose together, noting down the routes and the necessary endpoints that would be used by the components that we want in our project. From this, we finalized the ideas of what components we want to include in our app, and where to get the data from.

**App components:**
- Home page displaying the upcoming race info and the current standings table
- Schedule page with cards of completed and upcoming race in chronological order
- Race Result page to display the results of a completed race
- Drivers Index Page which shows lists of drivers in this season as a grid
- Driver Profile Page to display the information of the driver and the profile image

**Wireframe vs. Final Product**
<img width="1030" alt="Screen Shot 2565-09-05 at 21 53 57" src="https://user-images.githubusercontent.com/77038679/195327137-4880d779-19b2-417c-bc0c-3ac1a0b61a13.png">
![Screen Shot 2565-09-05 at 21 58 33](https://user-images.githubusercontent.com/77038679/195327636-2661daa3-1fb8-4d52-9f4a-0c4e5d0adf68.png)
<img width="1110" alt="Screen Shot 2565-09-05 at 21 54 21" src="https://user-images.githubusercontent.com/77038679/195328138-991b2357-2e49-4179-842e-81143c4fdc35.png">

![Screen Shot 2565-09-05 at 21 58 50](https://user-images.githubusercontent.com/77038679/195328064-328d04ce-2a3b-42a4-b651-4f5b9c5d5ddf.png)

<img width="1077" alt="Screen Shot 2565-09-05 at 23 14 00" src="https://user-images.githubusercontent.com/77038679/195328295-0f11d088-5674-4a9d-be6f-c6d494d00afc.png">


![Screen Shot 2565-09-05 at 22 00 11](https://user-images.githubusercontent.com/77038679/195328250-b182a8ab-50d5-4d57-a729-688484d20d95.png)

We wanted to display the images of each driver dynamically, therefore we looked into another API that provides the images and decided to request the images from that API into our app for the drivers.

## Code Process
This is the first time we are pair-coding, and with limited time, the first approach taken was to list all the API endpoints required, and to create the skeleton of the React app together before dividing on separate components to work on. We communicated online at all times through Zoom, and worked together seamlessly via VSCode LiveShare function. 

Once we got all our ideas and components skeleton ready, we divided components to work on, me being responsible for the HomePage (Standings and Upcoming Race text), Race Results, and the NavBar. Milly worked on the schedule and drivers index, along with the driver profile pages. Even though we have divided components to work on, we would always communicate if we faced a problem and worked through the problems together. Since this was the first time implementing React bootstrap for responsiveness and most of the stylings, a lot of time was spent on making all the tables and grids responsive, and neat. I found styling the tables quite challenging especially when we aim to make it fit on a mobile view, but in the end it was managed. 

We used React Hooks, useState and useEffect for most of the pages, using useEffect to execute a function to make a request to the API, store them in a useState, then display them in JSX. 

<img width="708" alt="Screen Shot 2565-09-05 at 22 21 21" src="https://user-images.githubusercontent.com/77038679/195328970-c822fd4d-6f53-4c8b-aca7-63626b16b865.png">

For the Home page, the challenging part was displaying the information for the next race in the banner since the standings homepage does not have the information of the rounds, therefore another request to the current season's endpoint with the list of all races and its data has also been made.  Helper functions were created to store the data received from both endpoints, combining them, and create a function to display them which is then imported and used in the Homepage component. The process includes getting the current round number from the standings endpoint, and getting the data of all races from the current season endpoint. The current round number is then used as an index to get data for the “next round”, where it is then stored and displayed using the function nextRaceDisplay. This is the part I stumbled on, and was happy to get it to work in the end. 

<img width="782" alt="Screen Shot 2565-09-05 at 22 23 30" src="https://user-images.githubusercontent.com/77038679/195329053-7976ba41-1a97-4e66-a6cc-b3c0e2ca252c.png">

## Challenges

*Stylings*

As mentioned earlier in the coding process section, it was our first time to actually implement React Bootstrap so we learned about the functionalities and the usage within the 48 hours and tried our best to style it as if it was a proper platform with responsiveness so users could view it on mobile. We managed to work out the stylings and got the tables and grids to be responsive.

*Bridging a second API source to display Drivers and circuit images*

The second API with images of both the drivers and circuit has some limitations that did not allow us to make a request to get all images in one request due to the structure of the API and also the rate limit, therefore we were only able to make a request for the single Driver Profile pages. In order to display all the images, we found a method (an idea) close to the deadline of this project where it requires us to make several requests and store the images to local storage, but we did not manage to execute it in time. For this current season, we loaded the circuit images and the driver images in the grids in a static way.

## Wins / Key Learnings / Takeaways
I am happy that we managed to complete this in a short period of time, and achieved almost all of our goals on how we want our app to look like. I am most proud of the stylings achieved in this small timeframe, especially the responsiveness and the small details that were picked up during the 48 hours of implementing bootstrap and fully working with SASS for the first time. This is also the first time working with a partner on a team project, and I am very glad that we had exceptional communication and similar working styles! This enhances the collaboration in this project, and helped us push the boundaries we didn’t think we could achieve together. I also got to learn a lot from Milly, and we were able to fill the gaps and manage all the struggles we faced as a team.

## Bugs & Future Improvements

**Bugs**
There are currently no noticeable bugs in this project, however there can be a time when the driver’s image API reaches a rate limit and the images will not show if it has been clicked repeatedly. The driver’s images and the circuit images may not load correctly for the next season since there might be changes in the data itself, but that would have to be tested when the next season arrives. If the information is updated in the future and the drivers are different from the current status at development, there might not be an image for that driver.

**Future Improvements**
There are many things we would like to improve, including more data and functionality to make the app more complete. The improvements include:
- Display the images dynamically using API in the circuit (Schedule page) and driver’s images grid (Driver Index page)
- Search and filter functionality for Drivers Index page
- More information about the circuits and the race results
- User experience elements such as more labels for the user to know they can click on the completed race in the Schedule page to find the race result

