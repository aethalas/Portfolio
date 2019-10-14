<template>
  <div class="alternate-style max-width">
    <ProjectDisplay :data="project" v-for="(project, index) in projectsLimited" :key="index" />
    <div style="padding: 15px;">
      <b-button class="button" pill block v-on:click="showAllProjects = !showAllProjects">
        <i class="material-icons">
        {{showAllProjects === true ? "expand_less" : "expand_more"}}
        </i>
      </b-button>
    </div>
  </div>
</template>

<script>
  import ProjectDisplay from './ProjectDisplay.vue'

  export default {
    components: {
      ProjectDisplay
    },

    computed: {
      projectsLimited () {
        if (this.showAllProjects) {
          return this.projects;
        } else {
          return this.projects.slice(0, 10);
        }
      }
    },

    data: function () {
      return {
        projects: [
          { percent: '100', name: 'TamaLife', img: 'tamalife', youtube: '', website: '', github: 'https://github.com/aethalas/TamaLife', desc: 'Virtual Pet | Unity & C#', about: '<p>TamaLife is a virtual pet based on the classic Tamagotchi we all know and love from the 90s.</p>  <p>This game is built using the Unity3D game engine and is written in the C# language, primarily as a passion project, but also be launched on the Google Play Store upon its completion as the first game under my wife and I’s Fluff ‘n’ Howl Studios.</p> <p>TamaLife has been designed with simplicity in mind: don’t expect anything revolutionary here! The game logic consists of real-world statistical change over time, with the pet needing to be cared for on a regular basis by the user to keep alive through attributes such as happiness, energy and intellect. These attributes are changed using algorithms that decay their value over-time and need the player to remain vigilant to keep their Tama alive and healthy.</p> <p>All illustrations and sound design in this game were designed by my wife, Kaling Tyson.</p> '  },
          { percent: '100', name: 'Ragnarok M Database', img: 'ragnarokm-database', youtube: '', website: 'http://ragnarokm.jonnyhtyson.com', github: 'https://github.com/aethalas/RagnarokM', desc: 'Data Scraping | Vue.js, PHP & SQL', about: '<p>Ok – so, I’m a huge video gamer, and as of late, I’ve moved into the mobile gaming spectrum after having become a husband. (I have found my time spent playing console or PC games increasingly limited.) As a kid, I played a whole lot of Gravity’s <b>Ragnarök Online</b> -- a South-Korean game based on Norse mythology -- so it was a huge surprise to me when I saw a mobile version of the popular MMO appear on the Google Play Store (and, presumably, Apple’s App Store too!)</p> <p> The game is addictive! But there seems to be a distinct lack of explanation in-game, with which creatures can drop certain items, and which items can do what. So, this lack of explanation made me want to build a solution to my own problem, and hopefully, it will help a few other people along the way, too. There are already various wiki’s on the internet that achieve a similar solution to what I have built with the application, but other wiki’s use a multi-page, archaic structure that just irks me with the powerful alternatives out there today in React, Vue, etc. </p> <p> This application is the answer. With a behind-the-scenes algorithm that will scour the internet for data in regards to the game, updating an internal database with this information, the Ragnarök M Database is powered by Vue.js in addition to the bootstrap library. It’s aim is to give the user a single-page application that is powerful and ease to use with the ability to search for any given item, monster, or card in the Ragnarök M mobile game in a dynamic way, without the user ever having to leave the page. </p> ' },
          { percent: '100', name: 'Procedural Terrain Generation', img: 'procedural-terrain-generation', youtube: 'https://www.youtube.com//embed/B8Mu5VrBYmM', website: '', github: 'https://github.com/aethalas/Procedural-Terrain-Generation', desc: 'Procedural Generation | Unity | C#', about: "<p>For our dissertation project, I decided to investigate procedural generation for terrain in a computer game environment. The project was built alongside an investigative report of 21,000 words which explored the nature of terrain generation through the use of Perlin noise and other similar methods. This project was the result of a year-long module at university and was built using the Unity engine, and programmed using C#, both of which had not been used previously and were therefore seen as a means to further develop personal skills.</p> <p>This project uses a system in which chunks of terrain are synthesised and associated a level of detail (LOD) depending on their distance from a player character. As the player nears the chunks of terrain, the detail levels (the number of polygons used to show the chunk) are increased. In addition, the further a player strays from a chunk, it will eventually be deleted from memory altogether and newer chunks are created in their place. Using this method, the player will feel like they walk through an endlessly generated world.&nbsp;</p> <p>For each chunk that is above a certain LOD threshold, that chunk will generate assets, such as trees, rocks and grass on its vertices depending on their height values. For example, trees can only spawn above the water level. This creates somewhat believable landscapes but is probably a rudimentary approach to tackling this problem and comes with its own headaches; what happens if the bushes spawn in areas that would not allow strong, natural growth? This not taken into consideration by the algorithm behind the generation.</p> <p>This project does have its flaws, however, and was detrimental to me achieving a First class grade. The placement of trees and other objects are created and placed randomly according to various height parameters, and this is actioned every time a new chunk is created in the world. This means that, for example, if the player were to track back the way they came, the world would be completely different than what they first encountered. Obviously, if this were used in a real game, it would be jarring and break the immersion. This is something that should be remedied should the system be used for a real game.</p> <p>This module took place on a third-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2018.</p> <p>I achieved a&nbsp;<strong>2:1</strong>&nbsp;for this project, with a 67/100 score. As this project was my dissertation, it counted toward my final grade.</p>" },
          { percent: '100', name: 'Beat My Bot', img: 'beat-my-bot', youtube: 'https://www.youtube.com/embed/bfTYnKd99ck', website: '', github: 'https://github.com/aethalas/Beat-My-Bot', desc: 'A* Algorithm | State Machine | C++ & DirectX', about: "<p>For this project, we were given instructions to create a team of AI bots that were capable of beating their opponent. It is titled Beat My Bot as the enemy team's bots are programmed, badly, by the lecturer.</p> <p>We were instructed to build a state machine that the bots would utilise, allowing them to switch between these states seamlessly, with each state using different behaviours, such as wall avoidance or seeking a target. These states were governed by the bots current predicament, allowing the bots to think effectively enough to win against the opposing team.</p> <p>To further develop this system, we were tasked with implementing a pathfinding system the bots could use to increase their accuracy in finding their destination. This was done by first filling the map with nodes. This was achieved by using a recursive function: blanketing the map with four squares, with increasingly smaller areas until they hit an arbitrarily set number. For each iteration of this loop, a node was placed in the centre of the square, taking care to only place them outside the boundary of the maps 'walls.' Once this was achieved, the A* algorithm was implemented to use this network of nodes to manoeuvre bots around the playing field.</p> <p>The final mission for this project was to implement networking features that would allow the game to run on a 'server' and have a 'client' connect to view the game playing out. This was achieved by sending structs of the bots position vectors, among other bits of information, through a basic Winsock connection.&nbsp;</p> <p>This module took place on a third-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2018.</p> <p>I achieved a&nbsp;<strong>First</strong>&nbsp;for this project, with a 76/100 score. As this project took place in my third-year, it counted toward my final grade.</p> <p>The overall grade for my&nbsp;<strong>Specialist Games Programming</strong>&nbsp;module, which also included a written 3000-word essay on my multi-threaded architecture of the project, was a&nbsp;<strong>First</strong>&nbsp;class result of 76/100.</p>" },
          { percent: '100', name: 'Non Solum De', img: 'non-solum-de', youtube: 'https://www.youtube.com//embed/L7smiTj2flc', website: '', github: 'https://github.com/aethalas/Non-Solum-De', desc: '2D Pixel Game | Space Shooter | C++ & DirectX', about: "<p>For this project, we were tasked with creating a two-dimensional video game which consisted of endless scrolling in one direction, a player-controlled spaceship, and an assortment of enemy types.</p> <p> In completing this project, the final game can be played in its entirety and consists of: a high score system, progressively harder content, a procedurally generated landscape, and power-ups in the form of homing missiles. </p> <p> The purpose of this assignment was to put into practise all we had learned on object-orientation in the C++ programming language and took place on a second-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2017. </p> <p> I achieved a <b>2:1</b> for this project, with an 64/100 score. As this project took place in my second-year, it counted toward my final grade. </p> <p> The overall grade for my <b>Programming for Games 3</b> module, which included a written exam, was a <b>First</b> class result of 78/100. </p> " },
          { percent: '100', name: 'Auxentius Package', img: 'auxentius-package', youtube: 'https://www.youtube.com/embed/41rQHRvb5CQ', website: '', github: 'https://github.com/aethalas/Auxentius-Package', desc: 'Game Design | Voice Acting | Skyrim Creation Kit', about: "<p>In my first year at university, we were tasked with creating an add-on for Bethesda's <b>The Elder Scrolls V: Skyrim</b>. This add-on would be centred around a wizard named 'Auxentius,' whose tower was located just outside of the city of Morthal, and would take the player on a concise quest taking no longer than 20 minutes of gameplay.</p> <p> The synthesis of this project included multiple facets of the Skyrim Creation Kit, such as the use of Papyrus scripting languages, environmental placement and design, voice acting, enemy placement and AI, and a questline with branched dialogue options. </p> <p> One of the main objectives of this module was to generate a team building exercise that would enable us to learn to communicate effectively with each other to produce a high-quality piece of work. Each of the group members was given specific targets, a few of which would rely on other group members providing work promptly to allow the development to continue flawlessly. </p> <p> This project was completed by a group of three students: myself, Alastair Usher and Aidan Harrison at the University of Northumbria in Newcastle upon Tyne, 2016. We achieved a <b>First</b> for this project, with a 77/100 score, although it should be noted that, as this was a first-year project, this grade was not factored into our final grade. </p> " },
          { percent: '100', name: 'Auxilium', img: 'auxilium', youtube: 'https://www.youtube.com/embed/cl0DRmXqFX8', website: '', github: '', desc: 'UI & Sound Design | Unreal Engine | Blueprints', about: "<p>For this project, we were tasked with creating a video game in a game engine of our choice. We decided to use Epic Games' Unreal Engine, as we had worked with it previously in an earlier assignment.</p> <p> As a group, we decided to go with a first-person shooter game set in a post-apocalyptic world, with appropriate enemies, obstacles and a basic storyline involving the hunt for a vaccine. </p> <p> The objective of this task was to break the workflow between our group of 4 members: I was tasked with creating the user interface (the main menu, skill tree, HUD and objectives) as well as the sound design. These tasks were implemented using the blueprint system. </p> <p> The module took place on a third-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2018. </p> <p> I achieved a <b>First</b> for this project, with a 76/100 score. As this project took place in my third-year, it counted toward my final grade. </p> <p> The overall grade for my <b>Combined Games Project 3</b> module, which included project management documentation, was a <b>First</b> class result of 76/100. </p> " },
          { percent: '100', name: 'Beyond the Gate', img: 'beyond-the-gate', youtube: '', website: '', github: '', desc: 'Third-person game | Unreal Engine | Blueprints', about: "<p>For this project, we were tasked with creating a group project in Epic Games' Unreal Engine. This game would need to be roughly ten minutes long, include various game mechanics, such as the ability to jump, fight enemies, and collect pickups.</p> <p>As a group, we decided to pick an over-the-shoulder style game, with platforming-themed sections, enemies, a boss-fight in the shape of a giant Troll, and a timer in which the level must be completed. </p> <p>The main objective of this task was to work with other students to create a product, with various project management skills being used to emphasize the fact. We created a GitHub repository to keep things available for all group members, talked directly over social media, and ensured each of us were able to work independently away from the university without any hiccups. </p> <p>My individual task for this project was the user interface, which I created using Adobe Photoshop and Unreal Engine's blueprints. </p> <p>The completion of this project was then put through a user testing phase with friends and family, after signing a consent form, to polish the product and eliminate any errors that were present. </p> <p>This module took place on a second-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2017. </p> <p>I achieved a <b>First</b> for this project, with an 82/100 score. As this project took place in my second-year, it counted toward my final grade. </p> <p>The overall grade for my <b>Combined Games Project 2</b> module, which included a written section on a usability evaluation, was a <b>First</b> class result of 83/100. </p> " },
          { percent: '100', name: 'Space Shooter', img: 'space-shooter', youtube: 'https://www.youtube.com/embed/aoVrt2a0QUc', website: '', github: 'https://github.com/aethalas/Space-Shooter', desc: 'Object Factory | Android Studio | Java', about: "<p>For this project, we were tasked with creating a simple Android game using Android Studio and the Java programming language.</p> <p> This project was done in a group of two students: myself, and a class mate, with my work consisting of the power-up homing missiles and the object factory design pattern used to create an endless wave of opponents for the player to dodge throughout the game. </p> <p> The purpose of this assignment was to learn how to write code for a mobile device, taking memory constraints into consideration, and took place on a third-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2018. </p> <p> I achieved a <b>First</b> for this project, with an 71/100 score. As this project took place in my third-year, it counted toward my final grade. </p> <p> The overall grade for my <b>Advanced Games System Architecture</b> module, which included a written essay, was a <b>First</b> class result of 70/100. </p> " },
          { percent: '100', name: 'Mission Simulator', img: 'mission-simulator', youtube: 'https://www.youtube.com/embed/HsaXH4DHTyk', website: '', github: 'https://github.com/aethalas/Mission-Simulator', desc: 'Console Application | Database | SQL & C++', about: "<p>For this project, we were tasked with creating software capable of loading a database file and querying it depending on a parameter entered by the client.<p> <p>This project was based on a fictitious Mission Simulation product, wherein a database of agents with varying skill levels and salaries, companies and missions were created using SQLite. Each agent in the database was assigned to work for one of the companies where they would be able to accept a mission given by their associated company. When the user enters the name of one of these 'agents' they are able to quickly determine which mission they are capable of achieving, given their current skill level and salary demands.</p> <p>The planning for this project started with the synthesis of an entity relationship diagram (ERD) before the schema was created. The database records were then automatically created using C++.</p> <p>The purpose of this assignment was to learn structured query language and took place on a second-year module in a Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2017.</p> <p>I achieved a <b>First</b> for this project, with an 82/100 score. As this project took place in my second-year, it counted toward my final grade.</p> <p> The overall grade for my <b>Games Architecture and Development</b> module, which included a written exam, was a <b>First</b> class result of 75/100. </p> " },
          { percent: '100', name: 'Simple Solitaire', img: 'simple-solitaire', youtube: 'https://www.youtube.com/embed/brMhLpSoye8', website: '', github: 'https://github.com/aethalas/Simple-Solitaire', desc: 'Console Game | C++', about: "<p>For this project, we were tasked to synthesise a game of solitaire using the console. A matrix was instantiated using C-style arrays, to make up a 5 by 5 board, with each index of this array being represented by a peg. The centre of the board was an empty space. The user was then asked to select a coordinate ranging from 1,1 (the bottom left peg) to 5,5 (the top right peg.) Once a selection had been made, the user was prompted to move that peg in a direction (N,S,E,W). This was only possible if the peg could 'jump' over another peg, thus removing that peg from the board entirely. The game would be over once there were no longer any moves possible and a score for the user would be calculated as a result.</p> <p> The purpose of this assignment was to solidify basic programming methodologies and was part of a first-year module which took place roughly 6 months into my first year Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2015. </p> <p> I achieved a <b>First</b> for this project, with a 75/100 score, although it should be noted that, as this was a first-year project, this grade was not factored into my final grade. </p> <p> The overall grade for my <b>Programming for Games 1</b> module, which includes two other projects, was a <b>First</b> class result of 76/100. </p> " },
          { percent: '100', name: 'Penny Game', img: 'penny-game', youtube: 'https://www.youtube.com/embed/-mqmzoTSV4I', website: '', github: 'https://github.com/aethalas/Penny-Game', desc: 'Console Game | C++', about: "<p>My very first programming assignment tasked us with creating a simple game between a user and the computer. An arbitrary stack of coins is presented at the beginning of the game, with the aim being to take between 1 and 5 at a time, with the end goal being to leave the opponent with the final coin. Once either the computer or the user has the final coin, they are declared the loser.</p> <p> The purpose of this assignment was to learn about functions and their role in programming, basic C-style data structures, the importance of commented code and good coding practices, with this project taking place some 2 months into my first year Computer Games Programming course at the University of Northumbria in Newcastle upon Tyne, 2015. </p> <p> I achieved a <b>First</b> for this project, with a 93/100 score, although it should be noted that, as this was a first-year project, this grade was not factored into my final grade. </p> <p> The overall grade for my <b>Programming for Games 1</b> module, which includes two other projects, was a <b>First</b> class result of 76/100. </p> " },
        ],
        showAllProjects: false,
      }
    },
  }
</script>

<style scoped>
  .button {
    font-family: 'Exo', sans-serif;
    text-shadow: 2px 2px 4px #000000;
    font-weight: bold;
    vertical-align: bottom; 
    border: none;
    border-radius: 15px;
    background: rgba(181, 193, 204, 0.7);
    font-size: 0.9vw;
    color:#ffffff; 
    margin-top: 10px;
    margin: 0 auto;
    width: 85%;
  }

  .button:hover {
    background:#ffffff;
    color:#000000;
    text-shadow: 2px 2px 4px #000000;
  }

  .alternate-style {
    background: #e5e7e7;
    padding: 1vw;
    background: repeating-linear-gradient(
      120deg,
      #ffffff,
      #ffffff 10px,
      #f8f9ff 10px,
      #f8f9ff 20px
    );
  }

  .max-width {
    max-width: 100%;
    margin: 0 auto;
  }

  .material-icons {
    font-size: 0.8vw;
  }

  h3 {
    color: white;
    font-size: 0.8vw;
    text-shadow: 2px 2px 4px #000000;
  }

  @media (max-width: 1400px) {
    h1, h2, h3 {
      font-size: 15px;
    }
    
    .material-icons {
      font-size: 15px;
    }
   }
</style>