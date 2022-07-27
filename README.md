# My Journey

<p>A few days ago a video caught my eye. It explained what a web developer would have done different, were he to start anew the path to become a developer. Many of the ideas were interesting, but a particular one was new to me: keeping a diary. The argument was that this helps you track your growth and development.</p>

### Until now - June 2022

<p>Unfortunately I am not starting this at the beginning of the path, but 5 years later, since I started working. After finishing a master in Aerospace Engineering in Madrid in late 2017, I moved to Germany, where I began to work as engineer. Before that, I did a couple of internships related to aircraft systems modelling.

During the last years, I developed SCADA applications (Supervisory Control adn Data Acquisition). Both the backend and frontend, including the database design. The SCADA software used a Java version of Python, Jython. Apart from that, my first contacts with Python came from the need to automate some spreadsheets work, Excel. For that I used the awesome resource [Automate the Boring Stuff with Python](https://automatetheboringstuff.com/). Later, I had to face some repetitive tasks, which are as necessary as boring. For that I started using Selenium, and discovered how nice it felt to automate broswer tasks. To keep track of these files I used git.

Around one year ago, the environment changed to React and Node: web applications. So I started to learn JavaScript. And HTML adn CSS, with which I was already familiar. This opened a whole new set of possibilities and things I did not know: hosting applications in the cloud (AWS), CI/CD, Docker, etc.

<hr>

### July 1st, 2022

#### <i>Hobby projects: Chess Game</i>

I decided to start hobby projects to try things for which I do not have time in the fast-paced work environment. I picked a Chess game, for three main reasons:

<ul>
<li>Sharpen frontend skills</li>
<li>Interesting practice for backend & logic</li>
<li>Project can be easily extended: multiplayer, saving scores to DB, AI & single player, etc.</li>
</ul>

<p>The idea is to use this project as a way to learn, get familiar or improve, among others, the following items:</p>

<ul>
<li>TypeScript</li>
<li>Docker & Kubernetes</li>
<li>React Redux</li>
<li>React Testing Library</li>
<li>Jest</li>
<li>AI</li>
<li>Webpack</li>
<li>Babel</li>
<li>Debugging</li>
</ul>

<p>In some cases, the intention is to deepen the knowledge. In others, to have a basic understanding of the technology.</p>

<hr>

### July 8th, Friday

#### <i>Typescript</i>

When I started using TypeScript a few days ago I was unsure. It looked like it required more work than it actually paid off. But in search of motivation I kept reading how nice it was, specially for large projects. And how it was like documenting the code.

Well, I am beginning to agree. The autocompletion is great when the IDE (let's say, vs code) behind knows what the type is. So if you do in JavaScript something like `const whatIsMyType;`, then vs code will not be able to autocomplete when you type `whatIsMyType.`. But if you did `const iHaveAType: string[]`, then it will greatly help you by providing you with autocomplete functions proper of an Array, such as `.includes` and others.

As for the documentation, you will no longer have Objects whose key-value pairs have uncertain types.

But yes, it is still a pain to be <i>forced</i> to add types to every single thing you write.

<hr>

### July 12th, Monday

#### <i>Snapshot testing with Jest</i>

Today I was going to add new features to the chess game. In the end I decided to see how testing in React works (after adding 'turns' feature, so that white player cannot move twice, etc.).

I was reading a bit on testing in the weekend, and until now it seemed like an obscure blackbox. There are several testing types, unit tests and integration (whose threshold in React components is vague). Very simplified as well, one can use React-Testing-Library and / or Jest. There are of course other options. 

In this first contact with React testing (let's be honest, with testing), I am using just Jest. Not having created the project with CRA, I had to fight some initial setup, including some new devDependencies (react-test-rendered, jest, babel-jest and @babel/preset-typescript, ts-jest). Last two added due to having TypeScript files (it seems you cannot import a .ts file into .js, so I had to have .ts test files to be able to import the .tsx components).

Using CSS modules also complicated a bit the setup, but [Mocking CSS Modules](https://jestjs.io/docs/webpack#mocking-css-modules) explains how to do this very gracefully.

So it was an interesting setup, but in the end, as usually, it paid off. I added the most simple test file for a Cell rendering (in the Chess board). I run `npm test`, which calls `jest` command. It passed the (snapshot) test. Then I made a mistake (on purpose, of course) in which a white cell gets a class for a black one. I run the test agains and it fail the test! Wonderfull. It even detailed why it failed: class had changed. And this is how snapshot tests work, they compare the current snapshot to a previous (even commited) one. Really cool.

This is great to get started into more serious testing, and having a way to make sure any refractoring does not change the rendered components.

<hr>

### July 14th, Monday

#### <i>Debugging</i>

Todays learnings are as short as nice. And they are very short. A few weeks ago I deciding if buying a book whose title I do not remember, but it was something like <i>How to program </i>less <i>bad</i>. Ate the beginning there was a set of questions, aiming for the reader to realize if the book was needed or not. One of the questions was "How do you debug?". There where three possible anwers:

<ul>
<li>Who needs debugging anyway, the user will just inform about the bugs</li>
<li>I print / log everything to the console</li>
<li>I use debugging tool</li>
</ul>

We will skip the first answer (clearly the correct one). The last one did not actually say 'debugging tools', but some actual tool whose name I do not remember.
My case is the second one, I tend to print (console.log / print) eeeeeverything when I want to debug. Efficient, uh?

Well today printing was not enough, so I decided to take the step. Went to Google and typed 'react vscode debugging'.

I can only say it is awesome. Not only the potential, but also how easy it was, how simple it is to watch specific variables, etc. It reminds me to debugging in Matlab, back in the university when I had a single file (or a few anyway), and all was nice and sequential. I was afraid of how this would be in a React aüpplication, but it ended up being quite a nice experience. 


<hr>

### July 20th, Wednesday

#### <i>Google Fonts</i>

Today I was working on my [chess game](https://github.com/franciscocgue/chessdrez). Being a hobby project I freely decide what I want to work on, which features / part of the project. So today I thought it would be nice to have a basic timer or counter, to know how long is the current move taking for the current player.

Initially it was an incremental counter, increasing one unit per second. It was simple to convert it to a chronometer-like display, so that one and a half minutes looks like `01:30`. But the font was wrong. That display is calling for a digital-like font!

So after a bit of searching I found [Google Fonts](https://fonts.google.com/). I already knew them, but had never used. The experience was quite simple, both looking for fonts and then using then in my CSS file.

From my experience, when you show a project, the first thing to strike and produce an effect on the user is how the application <i>looks</i>. UX, performance, etc. are also important, but first thing is usually visualization.

<hr>

### July 25th, Monday

#### <i>Chessdrez I</i>

A few weeks ago I mentioned a chess game, as a way to practice, improve and learn new skills. This projects _chessdrez_ (chess translates into ajedrez in Spanish) is coming to life little by little. For now it is completely Front-end. This means games are not saved, multiplayer is not possible, etc.

To change this I will set a (hopefully) simple server with Node. From this server, the idea is to create 'play rooms', enable multiplayer with websockets, and to save game status. Some new Frontend features also need to be completed, to make the game more "enjoyable".

<hr>

### July 26th, Tuesday

#### <i>Chessdrez II</i>

So, I decided to document a bit the process.

Back when I started learning React a year ago, I used to write steps for the <i>future me</i>. But documenting the processes and the many how to's helped me actually remember the steps. So let us do it for the set up of the server.

<ol>
<li>Create <i>server</i> directory at the same level than <i>client</i>, just with <i>src</i>. These are our backend and frontend directories</li>
<li>
Create <i>index.js</i> file inside. <i>Note:</i> later we might want to use TyepeScript, but lets keep it simple for now. Sample file:
<pre>
  <code>
const express = require('express');

const app = express();
const port = process.env.PORT || 3000;

app.listen(port, () => {
    console.log('Server started on port ' + port.toString());
});
  </code>
</pre>

</li>

</ol>

After testing it works with `node .\src\server\index.js`, we keep adding stuff. First thing is to <i>serve</i> the file that Reacts creates, that is, the application. Since we are using Express, we will use its <i>sendFile</i>.

But where is this file compressing all the React SPA application? That depends on the webpack configuration. There should be an "output" key indicating where is the build located, after we run webpack command. This is normally different for Production and Development. In the latter we use "hot reload", which help us develop faster: after we save any change, this hot reload will load the new bundle file into memory. For this we need to install <i>webpack-dev-server</i>.

This I vaguely recalled from a couple of months ago when I was preparing a template / boilerplate that would:

<ul>
<li>Webpack and NOT CRA</li>
<li>Work well for a Node-React application</li>
<li>Enable hot-reloading for a great development experience</li>
</ul>

Details for this template can he seen in the repo, checking git logs history.

Another key step is to define a set of scripts in the <i>package.json</i> file. These scripts will do things such as:

<ul>
<li>Production: build React app</li>
<li>Production: serve our server file via <code>node index.js</code> file</li>
<li>Dev: build React app via webpack and its hot reloading</li>
<li>Dev: serve our server file, this time with <code>nodemon index.js</code>, where nodemon will automatically refresh any saved changes on index.js</li>
<li>Dev: I like to use <i>concurrently</i> to run both previous commands at the same time while in development</li>
<li>Testing scripts</li>
<li>... and run any commands needed in the Docker file, but that is for later</li>
</ul>

This is already too long, so I stop here. But than a detailed guide I just want to have an overview to guide the steps. Detail is always available in the repo ;)

<u><i>Update: </i></u> 

I just realized something which is interesting but also silly. In one of the steps above I mention <i>concurrently</i> to run the server index.js file, and serve the React application as well. This serving of the React application is loaded into memory and not in the <code>/dist</code> or <code>/public</code> directory. That means, the index.js file which serves the React application from the server (backend), does not have access to the React bundle (which is in memory).

So what happens is, webpack (dev) will serve the React bundle (lets say, in port 3000). But the command <code>node src/server/index.js</code> will start the server. The server tries to serve the React bundle from <code>/dist</code> (or <code>/public</code>), failing to find it. But every other thing the server does (APIs, for example, to provide the React application with database data, etc.) will work. 

Then, to access and test the application we need to open in the browser <code>http://localhost:3000/</code>, which is the React bundle, served by webpack, nothing to do with our backend server. BUT the server is running, so that if React needs something from it, it will work. In all this, the step that is missing is to let webpack know where is our server url. 

For that we can use DefinePlugin, to define a global variable configured at compile time, usable inside React (for example via:process.env.REACT_APP_BACKEND_URL ). Something like:

<i>webpack.config.js</i>

<pre>
  <code>
const { DefinePugin } = require('webpack');

// define backend URL depending of whether in prod or not
const react_app_backend_url = process.env.NODE_ENV !== 'prod' ? 'http://localhost:8080' : ''

module.exports = {
  entry: ...
  output: ...
  module: ...
  plugins: [
    new DefinePlugin({
      'process.env.REACT_APP_BACKEND_URL': JSON.stringify(react_app_backend_url)
    })
  ]
  ...
}
  </code>
</pre>


### July 27th, Wednesday

#### <i>Chessdrez III</i>

That comment from yesterday, very beautiful and it seems it could make sense. But we need proof, we need to test it.

We will set a simple route in the server, for a get request. Then in the React application we will add a button that makes this request. It will simply print something to the console. The objective is to prove that the React application as a bundle served from webpack does have access to the server, which is being run in parallel, <i>concurrently</i>.

When setting up the routes, some things that help:

<ul>
  <li>Test your route from <a href="https://www.postman.com/" target="_blank">Postman API Platform</a>. Note: to send request to localhost you might need to have the desktop version.</li>
  <li>Make sure the server is up and running</li>
  <li>If you get "Cross-Origin" requests errors, make sure you are using <i>cors</i></li>
</li>


</ul>
