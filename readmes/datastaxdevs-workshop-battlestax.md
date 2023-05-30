<h1><a class="anchor" aria-hidden="true" id="jamstack-react-workshop"> </a>🚀 JamStack + 🧑‍🚀 React + 🧑‍💻 Workshop</h1>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a><br />
<a href="https://app.netlify.com/sites/battlestax-tutorial/deploys" target="_blank"><img src="https://api.netlify.com/api/v1/badges/e265340f-c6a6-4d7b-b24c-438b87c67876/deploy-status" alt="Netlify Status" /></a></p>
<p>Welcome to <strong>BattleStax</strong>, an online party game that you can enjoy with your friends. BattleStax is implemented as a <a href="https://jamstack.org/" target="_blank">JAMStack</a> app that uses <a href="https://stargate.io">Stargate</a>, <a href="https://www.netlify.com/jamstack/">Netlify</a>, <a href="https://dtsx.io/workshop">Astra</a>, and <a href="https://github.com/">GitHub</a> to demonstrate how to build and deploy an application using modern, scalable architectures.</p>
<p>In this 3 hour workshop you will create your own <strong>BattleStax</strong> game using <a href="https://reactjs.org/" target="_blank">React</a> and <a href="https://redux.js.org/">Redux</a> implemented with a CI/CD pipeline, global CDN network, and <a href="https://cassandra.apache.org/">Apache Cassandra</a> all using <strong>FREE</strong> tech.</p>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/battlestax.png" alt="log" /></p>
<h2><a class="anchor" aria-hidden="true" id="housekeeping"> </a>ℹ️ Housekeeping</h2>
<details><summary>Click to view the housekeeping items (<i><!--Youtube stream, -->Discord Chat,  Mentimeter quizz, the crew</i>)</summary>
<p>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop.</p>
<!-- 
### 🎥 Live and questions with Youtube**

The workshop is live Streamed on youtube, twitch and linkedin. After the session the recordings will be available on our [`DataStax Developers YouTube channel`](https://www.youtube.com/channel/UCAIQY251avaMv7bBv5PCo-A)

*Click The image to join the stream*

[![stream](./tutorial/workshop-live.png)](https://vimeo.com/datastax/review/478138764/8983f4fca5)

-->
<h3><a class="anchor" aria-hidden="true" id="chat-with-discord"> </a>💬 Chat with Discord*</h3>
<p>Join our discord room <a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><em>The Fellowship of the Rings</em></a> to chat with the team and meet our 6k+ community there.</p>
<p><a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="./tutorial/discord.png" alt="stream" /></a></p>
<h3><a class="anchor" aria-hidden="true" id="quizz-with-mentimeter"> </a>❓ Quizz with Mentimeter</h3>
<p>This workshop is <em>INTERACTIVE</em>. Not only you interact with the speakers through questions but there is more:</p>
<ul>
<li>We want to ask you some questions</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/mentimeter.png" alt="stream" /></p>
<ul>
<li>We want you to mark when the exercise is complete</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/mentimeter2.png" alt="stream" /></p>
<ul>
<li>We want you win some SWAG with some competitions and live QUIZZES</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/mentimeter3.png" alt="stream" /></p>
<p>To do so we are using <a href="https://www.mentimeter.com/" target="_blank">Mentimeter</a>. To play with us follow the instructions below. The code is <strong><code>99 02 07 7</code></strong>. You can also <a href="https://www.menti.com/wzz24ja21f">open this link</a> in a new tab.</p>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/mentimeter4.png" alt="stream" /></p>
<h3><a class="anchor" aria-hidden="true" id="the-crew"> </a>🧑🏻‍🤝‍🧑🏽 The Crew</h3>
<p>The materials has been prepared with live with our great team</p>
<table>
<thead>
<tr>
<th><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/crew/chris.png" alt="B" /></th>
<th><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/crew/david.png" alt="B" /></th>
<th><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/crew/rebecca.png" alt="B" /></th>
<th><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/crew/cedrick.png" alt="B" /></th>
</tr>
</thead>
<tbody>
<tr>
<td>Chris Whilhite <br><a href="https://github.com/kidrecursive" target="_blank">@kidrecursive</a></td>
<td>David Gilardi <br><a href="https://github.com/SonicDMG" target="_blank">@SonicDMG</a></td>
<td>Rebecca Millis <br><a href="https://github.com/beccam" target="_blank">@beccam</a></td>
<td>Cedrick Lunven<br><a href="https://github.com/clun" target="_blank">@clun</a></td>
</tr>
</tbody>
</table>
<p><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/line.png" alt="stream" /></p>
<!--
## 🚀🚀 🚀  Let's Play the Game !

Brace yourselves, everybody goes to [https://battlestax-workshop.netlify.app/](https://battlestax-workshop.netlify.app/). 

[![.](./tutorial/rocket-animation.gif)](https://battlestax-workshop.netlify.app/)

-->
</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>🗓️ Table of Contents</h2>
<p><em>All the tutorials and readme files are on the <strong>master</strong>. Start there and then follow each step to get everything hooked up. Get a look at all branches <a href="https://github.com/datastaxdevs/workshop-battlestax/branches" target="_blank">here</a></em></p>
<ul>
<li><strong>Bootstraping</strong>
<ul>
<li>📚 <a href="./README_JAM.md" target="_blank">What is the JAMStack</a></li>
<li>⚒️ <a href="./README_step00.md" target="_blank">Setup and deploy your first app</a> <em>(branch <code>master</code>)</em></li>
</ul>
</li>
<li><strong>Step 1 - Serverless</strong>
<ul>
<li>📚 <a href="./README_Netlify.md" target="_blank">What can Netlify do for you</a></li>
<li>⚒️ <a href="./README_step01.md" target="_blank">Expose your &quot;hello world&quot; API</a> (<em>branch: <code>step-1</code></em>)</li>
</ul>
</li>
<li><strong>Step 2 - Implement a Serverless Data API</strong>
<ul>
<li>📚 <a href="./README_Astra_Stargate.md" target="_blank">What are DataStax Astra and Stargate</a></li>
<li>⚒️ <a href="./README_step02.md" target="_blank">Implement a CRUD Api in Astra</a> (<em>branch: <code>step-2</code></em>)</li>
</ul>
</li>
<li><strong>Step 3 - Client and State Management with Redux</strong>
<ul>
<li>📚 <a href="./README_Redux_React.md" target="_blank">What are Redux and React</a></li>
<li>⚒️ <a href="./README_step03.md" target="_blank">Create client state with Redux</a> (<em>branch: <code>step-3</code></em>)</li>
</ul>
</li>
<li><strong>Step 4 - React stuff</strong>
<ul>
<li>⚒️ <a href="./README_step04.md" target="_blank">Bind Redux to the User Interface</a> (<em>branch: <code>step-4</code></em>)</li>
</ul>
</li>
<li><strong>What's NEXT ?</strong> <em>(not the framework</em> 😈)
<ul>
<li>📚 <a href="./README_Resources.md" target="_blank">Extra Resources and certifications</a></li>
<li>💚 <a href="https://github.com/datastaxdevs/workshop-battlestax/blob/master/README_Resources.md#-share-the-love" target="_blank">Share the love</a></li>
</ul>
</li>
</ul>
<p><em>click the image to start !</em></p>
<p><a href="./README_JAM.md" target="_blank"><img src="https://github.com/datastaxdevs/workshop-battlestax/raw/master/./tutorial/are-you-ready.gif" alt="BattleStax JAMStack Workshop" /></a></p>
<p><strong>🏠 <a href="./README.md#%EF%B8%8F-table-of-contents" target="_blank">Table of Contents</a></strong> | <em><strong>next=&gt;</strong> 📚 <a href="./README_JAM.md">What is the JAMStack</a></em></p>
