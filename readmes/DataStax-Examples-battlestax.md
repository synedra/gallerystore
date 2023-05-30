<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="battlestax"> </a>BattleStax</h1>
<p><em>50 minutes, Advanced, <a href="https://github.com/DataStax-Examples/battlestax#prerequisites" target="_blank">Start Building</a></em></p>
<p><a href="https://gitpod.io/from-referrer/" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p>BattleStax is a stateful JAMStack game that is wholesome fun for the entire crew.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/battlestax/master/hero.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Deploy a scalable JAMStack app to production</li>
<li>Leverage a good CI/CD process to manage your JAMStack App</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="how-this-works"> </a>How this works</h2>
<p>The BattleStax players watch a lobby screen while playing the game on their devices.</p>
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/battlestax/master/tutorial/architecture1.png" alt="image" /></p>
<p><a href="https://jamstack.org/" target="_blank">JAMstack</a> is a big leap forward in how we can write web applications that are easy to write, deploy, scale, and also maintain. Using this approach means that newly created content is rendered from a content API, while a static render of it is being built into the site for future.</p>
<h2><a class="anchor" aria-hidden="true" id="get-started"> </a>Get Started</h2>
<p>To build and play with this app, follow the build instructions that are located here: <a href="https://github.com/DataStax-Examples/battlestax#prerequisites" target="_blank">https://github.com/DataStax-Examples/battlestax</a></p>
<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="running-battlestax"> </a>Running BattleStax</h1>
<p>Follow the instructions below to get started.</p>
<h2><a class="anchor" aria-hidden="true" id="prerequisites"> </a>Prerequisites</h2>
<p>Let's do some initial setup by creating a serverless(!) database.</p>
<h3><a class="anchor" aria-hidden="true" id="datastax-astra"> </a>DataStax Astra</h3>
<ol>
<li>
<p>Create a <a href="https://dtsx.io/3jGT8b4" target="_blank">DataStax Astra account</a> if you don't already have one:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-register-basic-auth.png" alt="image" /></p>
</li>
<li>
<p>On the home page. Locate the button <strong><code>Create Database</code></strong><br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-dashboard.png" alt="image" /></p>
</li>
<li>
<p>Locate the <strong><code>Get Started</code></strong> button to continue<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-select-plan.png" alt="image" /></p>
</li>
<li>
<p>Define a <strong>database name</strong>, <strong>keyspace name</strong> and select a database <strong>region</strong>, then click <strong>create database</strong>.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-create-db.png" alt="image" /></p>
</li>
<li>
<p>Your Astra DB will be ready when the status will change from <em><code>Pending</code></em> to <strong><code>Active</code></strong> 💥💥💥<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-active.png" alt="image" /></p>
</li>
<li>
<p>After your database is provisioned, we need to generate an Application Token for our App. Go to the <code>Settings</code> tab in the database home screen.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings.png" alt="image" /></p>
</li>
<li>
<p>Select <code>Admin User</code> for the role for this Sample App and then generate the token. Download the CSV so that we can use the credentials we need later.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-settings-token.png" alt="image" /></p>
</li>
<li>
<p>After you have your Application Token, head to the database connect screen and copy the connection information that we'll need later. We'll replace <code>ASTRA_DB_APPLICATION_TOKEN</code> with the <code>Token</code> value that is part of your Application Token.<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-db-connect.png" alt="image" /></p>
</li>
</ol>
<h3><a class="anchor" aria-hidden="true" id="github"> </a>Github</h3>
<ol>
<li>
<p>Click <code>Use this template</code> at the top of the <a href="https://github.com/DataStax-Examples/battlestax" target="_blank">GitHub Repository</a>:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-use-template.png" alt="image" /></p>
</li>
<li>
<p>Enter a repository name and click 'Create repository from template':<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-create-repository.png" alt="image" /></p>
</li>
<li>
<p>Clone the repository:<br />
<img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/github-clone.png" alt="image" /></p>
</li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="running-the-full-game"> </a>Running the full game</h2>
<p><em>Make sure you've completed the <a href="https://github.com/DataStax-Examples/battlestax#prerequisites" target="_blank">prerequisites</a> before starting this step</em></p>
<ul>
<li><a href="https://github.com/DataStax-Examples/battlestax#running-on-your-local-machine" target="_blank">Running on your local machine</a></li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="running-on-your-local-machine"> </a>Running on your local machine</h3>
<ol>
<li>Check out the <code>full-game</code> branch</li>
</ol>
<pre lang="sh"><code>git fetch
git checkout full-game
</code></pre>
<ol start="2">
<li>
<p>Create a <code>.env</code> file and fill it with values from the <code>.env.example</code> file.</p>
</li>
<li>
<p>Make sure the package dependencies are installed</p>
</li>
</ol>
<pre lang="sh"><code># install dependencies
npm install
</code></pre>
<ol start="3">
<li>Then, start the app in dev mode. Changes in the <code>src</code> or <code>functions</code> directories will trigger reloads.</li>
</ol>
<pre lang="sh"><code># start battlestax in dev mode
npm run dev
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="tutorial-steps"> </a>Tutorial Steps</h2>
<p>The above instructions are great to get you up and running pretty quickly, but if you would like to learn how to fully deploy the application to production with JAMStack then click the button below to get started.</p>
<p align="center">
<a href="https://github.com/DataStax-Examples/battlestax/wiki" target="_blank">
 <img src="https://dabuttonfactory.com/button.png?t=Open+the+workshop&f=Roboto-Bold&ts=26&tc=fff&hp=45&vp=20&c=11&bgt=unicolored&bgc=15d798" />
</a>
</p>
<!--- ENDEXCLUDE --->
