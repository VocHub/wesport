# NotESPN

## Description

A web applications for sports enthuasists to view up to date player information and statistics, as well as their favourite teams's information, statistics, and current standings in their respective leagues.

## Technologies

* HTML
* CSS
* JavaScript
* jQuery
* Bootstrap 4
* API-NBA
* Football Pro API
* API-Football
* API-Basketball

## Goal of the Project

#### Build a Wep Application from scratch using multiple Server-Side API requests

In order to ensure the web application is responsive, we used Bootstrap's components and grid layout so that the contents are intact in a variety of screen sizes. To do this, we needed to use relational ratio for positions and widths and heights. In addition, we needed a navigation bar and a footer that was consistent through all pages and would be responsive.

As a web application for sports enthuasiats, we needed to be able to search player info and stats from the top leagues for each respective sports. For our Minimal Viable Product (MVP), we decided to start out with BasketBall and Soccer to have a functional website ready for deployment within our time constraints. To do this, we used 4 APIs to search for players and teams, and will populate the page with the player or team's information.

## What Can You Find on NotESPN?

1. Navigational bar created from Bootstrap for easy navigation between Soccer pages and Basketball pages.

2. Carousel Images to showcase current events, and exciting game profile.

3. Trending topics on current hot topics and match ups.

4. Dedicated search pages, for your favourite players and teams, for both Soccer and Basketball.

5. Total point standings from the top Basketball league.

6. Latest and current self-updating League tables from 3 major soccer leagues in the world.

## Usage

The following images are examples of the web application's appearance and functionality:

![Image](./Assets/notespn1.png)
![Image](./Assets/notespn2.png)
![Image](./Assets/notespn3.png)
![Image](./Assets/notespn4.png)

## What We Did

#### Server-Side API requests

````
function bbPlayerSearch() { 
    var personName = document.querySelector("#searchBox").value

    $.ajax({
        url: `https://api-nba-v1.p.rapidapi.com/players/lastName/${personName}`,
        crossDomain: true,
        method: "GET"
    })
    .then(function(response) {

        // Displays player info on screen
        var ballInfo = response.api.players[0]
    
        $('#bbName').html(`<h1>${ballInfo.firstName} ${ballInfo.lastName}</h1>`)
        $('#info').html(`
        <p class="playerInfo">Date of Birth: ${ballInfo.dateOfBirth}</p>
        <p>Height: ${ballInfo.heightInMeters}m</p>
        <p>Weight: ${ballInfo.weightInKilograms}kg</p>
        <p>College name: ${ballInfo.collegeName}</p>
        <p>Country: ${ballInfo.country}</p>
        <p>Years pro: ${ballInfo.yearsPro}</p>
        <p>Jerser number: ${ballInfo.leagues.standard.jersey}</p>
        <p>Position: ${ballInfo.leagues.standard.pos}</p>`)
    })
}
````

#### League Tables

````
<table id="western">
    <tr>
        <th colspan="4">WESTERN CONFERENCE</th>
    </tr>
    <tr>
        <th>Rank</th>
        <th>Badge</th>
        <th>Team</th>
        <th>Points</th>
    </tr>
</table>
````

#### Search Functions

````
function changeSlide(event){
    event.preventDefault();

    document.querySelector('.searchPage').classList.remove('active-slide')
    document.querySelector('.searchPage').classList.add('hide')
    document.querySelector('.searchResults').classList.add('active-slide')
    document.querySelector('.searchResults').classList.remove('hide')
    
    if (event.target.id == 'searchBtn') {
        bbPlayerSearch()
    } else if (event.target.id == 'searchTeamBtn'){
        bbTeamSearch()
    }else if (event.target.id == 'soccerSearchBtn'){
        soccerPlayerSearch()
    }else if (event.target.id == 'soccerSearchTeamBtn'){
        soccerTeamSearch()
    } else {
        console.log('ERROR!!!!ERROR!!!!ERROR!!!!ERROR!!!!')
    }
    
}
````

#### Trending Page

````
<h2>Basketball</h2>

<div class="row">
    <div class="col-sm-4">
        <div class="card">
            <div class="card-body">
            <h5 class="card-title">NBA Finals: From afar, watching Game 1 of Lakers-Heat with Chris Bosh</h5>
            <img src="https://a4.espncdn.com/combiner/i?img=%2Fphoto%2F2020%2F0813%2Fnba_mega_playoff_orange_HT_16x9.jpg" alt="NBA Finals 2020">                
            <a href="https://www.espn.com/nba/story/_/id/30005679/nba-finals-afar-watching-game-1-lakers-heat-chris-bosh" target="_blank" class="btn btn-primary">Learn more</a>
            </div>
        </div>
    </div>
</div>
````

## Contributors

* Shaun ([@SSamoridny](https://github.com/SSamoridny))
* Aaron ([@whiteowl00](https://github.com/whiteowl00))
* Nathan ([@npcoding25](https://github.com/npcoding25))
* JoeJo ([@Learningitnow](https://github.com/Learningitnow))
* Dailey ([@scaredofseagles](https://github.com/scaredofseagles))

## URL

See the web application [here](https://npcoding25.github.io/Project-1/)

## Licence

MIT License

Copyright (c) 2020 Dailey Kaze

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
