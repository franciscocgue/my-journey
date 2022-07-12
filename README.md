# My Journey

### Some intro

<p>A few days ago a video caught my eye. It explained what a web developer would have done different, were he to start today the path to become a developer. Many of the ideas were interesting, but one particular one was new to me: keeping a diary.</p>

<p>This is nice for two reasons. First, it lets you see your development. Yes, we all get better with practice, interest and some work. But <i>how good</i>? And do we remember all those issues we faced on the way? A diary of teh journey should help keeping track. Second, it lets others see who you are, and how you got there. This might be some added value to the CV, for example.</p>

### Until now - June 2022

<p>Unfortunately I am not starting this at the beginning of the path, but around 1 year later. Or 5, since I started working. I graduated from a master in Aerospace Engineering in late 2017. Until done I did some few-months internships, mainly working with Matlab, or other in-house software. Every thing related to Aircraft modelling (trajectory first, then propulsion systems). In September 2017 I move to Germany, where I start working as an engineer in a US company.</p>

<p>For the first 1 to 2 years I work both both as a process (manufacturing) engineer, and I am also very involved in the finance department. Even if these tasks are not related, it allows me to have a broader and more interesting picture about the company. After this time I work uniquely as process engineer.</p>

<p>During this 5 years I develop SCADA (Supervisory Control adn Data Acquisition) solutions. This means, the window that operators will see in the shopflor. This includes both backend and forntend.</p>

(( not finished ))

### July 2022

#### <i>TL;DR</i>

<p><i>I start to develop a chess game as a hobby project to start learning, for example, about TypeScript.</i></p>

<p>All the project on which I work are work-related projects. That is, I have no <i>hobby</i> projects. Hobby projects are great for one main reason: they let you decide what you want to do, and this means the possibility of <b>learning new things</b>. And this is just great.</p>

<p>In the fast-paced industry it is usually not possible to try, test and learn new things. Once a solution meets the requirements, it is enough. And this is good, I am not saying the opposite. But from a self-development standpoint, this is not enough. One needs more.</p>

<p>Sometimes you want to code again every thing (third time's the charm). Or try a new approach. Or just improve it. Or add new features. And I will use these hobby projects as a way to learn new things, including:</p>

<ul>
<li>Docker & Kubernetes</li>
<li>React Redux</li>
<li>React Testing Library</li>
<li>Jest</li>
<li>AI</li>
<li>Webpack</li>
<li>Babel</li>
</ul>

<p>And many more. In some others, the intention is to deepen the knowledge. Is the case if Nodejs and git, for example. This is how the chess game begins :)</p>

### July 8th, Friday

When I started using TypeScript a few days ago I was unsure. It looked like it required more work than it actually paid off. But in search of motivation I kept reading how nice it was, specially for large projects. And how it was like documenting the code.

Well, I am beginning to agree. The autocompletion is great when the IDE (let's say, vs code) behind knows what the type is. So if you do in JavaScript something like `const whatIsMyType;`, then vs code will not be able to autocomplete when you type `whatIsMyType.`. But if you did `const iHaveAType: string[]`, then it will greatly help you by providing you with autocomplete functions proper of an Array, such as `.includes` and others.

As for the documentation, you will no longer have Objects whose key-value pairs have uncertain types.

But yes, it is still a pain to be <i>forced</i> to add types to every single thing you write.

### July 12th, Monday

Today I was going to add new features to the chess game. In the end I decided to see how testing in React works (after adding 'turns' feature, so that white player cannot move twice, etc.).

I was reading a bit on testing in the weekend, and until now it seemed like an obscure blackbox. There are several testing types, unit tests and integration (whose threshold in React components is vague). Very simplified as well, one can use React-Testing-Library and / or Jest. There are of course other options. 

In this first contact with React testing (let's be honest, with testing), I am using just Jest. Not having created the project with CRA, I had to fight some initial setup, including some new devDependencies (react-test-rendered, jest, babel-jest and @babel/preset-typescript, ts-jest). Last two added due to having TypeScript files (it seems you cannot import a .ts file into .js, so I had to have .ts test files to be able to import the .tsx components).

Using CSS modules also complicated a bit the setup, but [Mocking CSS Modules](https://jestjs.io/docs/webpack#mocking-css-modules) explains how to do this very gracefully.

So it was an interesting setup, but in the end, as usually, it paid off. I added the most simple test file for a Cell rendering (in the Chess board). I run `npm test`, which calls `jest` command. It passed the (snapshot) test. Then I made a mistake (on purpose, of course) in which a white cell gets a class for a black one. I run the test agains and it fail the test! Wonderfull. It even detailed why it failed: class had changed. And this is how snapshot tests work, they compare the current snapshot to a previous (even commited) one. Really cool.

This is great to get started into more serious testing, and having a way to make sure any refractoring does not change the rendered components.
