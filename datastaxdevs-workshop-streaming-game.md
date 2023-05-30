<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="drapetisca-a-multiplayer-online-game-with-astra-streaming-and-websockets"> </a>Drapetisca: a multiplayer online game with Astra Streaming and Websockets</h1>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-streaming-game" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p>Time: <em>50 minutes</em>. Difficulty: <em>Intermediate</em>. <a href="#lets-start" target="_blank">Start Building!</a></p>
<p>A simple multiplayer online game featuring</p>
<ul>
<li>Astra Streaming (a messaging system in the cloud, built on top of Apache Pulsar)</li>
<li>Astra DB (a Database-as-a-service built on Apache Cassandra)</li>
<li>WebSockets</li>
<li>React.js for the front-end</li>
<li>the Python FastAPI framework for the back-end</li>
</ul>
<!--- ENDEXCLUDE --->
<p><img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/master/images/drapetisca_intro_v2.png" alt="Drapetisca screenshot" /></p>
<h2><a class="anchor" aria-hidden="true" id="objectives"> </a>Objectives</h2>
<ul>
<li>Understand the architecture of a streaming-based application</li>
<li>Learn how Apache Pulsar works</li>
<li>See the interplay between streaming and persistent storage (a.k.a. database)</li>
<li>Learn about Websockets on client- and server-side</li>
<li>Understand how a FastAPI server can bridge Pulsar topics and WebSockets</li>
<li>Understand the structure of a Websocket React.js application</li>
<li><strong>get your very own online gaming platform to share with your friends!</strong></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="frequently-asked-questions"> </a>Frequently asked questions</h2>
<ul>
<li><em>Can I run the workshop on my computer?</em></li>
</ul>
<blockquote>
<p>You don't have to, it's all already in the cloud! But there is nothing preventing you from running the workshop on your own machine.<br />
If you do so, you will need</p>
<ul>
<li>git installed on your local system</li>
<li><a href="https://www.whitesourcesoftware.com/free-developer-tools/blog/update-node-js/" target="_blank">node 15 and npm 7 or later</a></li>
<li><a href="https://www.python.org/downloads/" target="_blank">Python v3.8+ installed on your local system</a></li>
</ul>
<p>In this readme, we try to provide instructions for local development as well - but keep in mind that<br />
the main focus is development on Gitpod, hence <strong>We can't guarantee live support</strong> about local development<br />
in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.</p>
</blockquote>
<ul>
<li><em>What other prerequisites are there?</em></li>
</ul>
<blockquote>
<ul>
<li>You will need a GitHub account</li>
<li>You will also need an Astra account: don't worry, we'll work through that in the following</li>
</ul>
</blockquote>
<ul>
<li><em>Do I need to pay for anything for this workshop?</em></li>
</ul>
<blockquote>
<ul>
<li><strong>No.</strong> All tools and services we provide here are FREE.</li>
</ul>
</blockquote>
<ul>
<li><em>Will I get a certificate if I attend this workshop?</em></li>
</ul>
<blockquote>
<p>Attending the session is not enough. You need to complete the homeworks detailed below and you will get a nice participation certificate a.k.a. badge.</p>
</blockquote>
<ul>
<li><em>Why &quot;Drapetisca&quot;?</em></li>
</ul>
<blockquote>
<p><em>Drapetisca socialis</em>, known as &quot;invisible spider&quot;, is a very small and hard-to-notice spider found throughout Europe.<br />
Since this is a multiplayer game that lets players have social interactions in the play area, why not choose a spider<br />
with &quot;socialis&quot; in its name?</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="https://youtu.be/jfOBPlcd9eA" target="_blank">Workshop Video</a></li>
<li><a href="slides/DataStaxDevs-workshop-Build_a_Multiplayer_Game_with_Streaming.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/master/images/streaming-workshop.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your assignment and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps as described below until you have your own app running in Gitpod.</li>
<li>Now roll up your sleeves and modify the code in two ways: (1) we want the API to send a greeting to each new player in the chat box, and (2) we want the player names in the game area to match the icon color. <em>Please read the detailed guidance found <a href="#7-homework-instructions" target="_blank">below</a></em>.</li>
<li>Take a SCREENSHOT of the running app modified this way. <em>Note: you will have to restart the API and reload the client to see all changes!</em></li>
<li>Submit your homework <a href="https://dtsx.io/streaming-game-homework" target="_blank">here</a>.</li>
</ol>
<p>That's it, you are done! Expect an email in a few days!</p>
<h1><a class="anchor" aria-hidden="true" id="let-s-start"> </a>Let's start</h1>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<ol>
<li><a href="#1-create-your-astra-streaming-instance" target="_blank">Create your Astra Streaming instance</a></li>
<li><a href="#2-create-your-astra-db-instance" target="_blank">Create your Astra DB instance</a></li>
<li><a href="#3-load-the-project-into-gitpod" target="_blank">Load the project into Gitpod</a></li>
<li><a href="#4-api-setup" target="_blank">Set up/start the API</a></li>
<li><a href="#5-client-setup" target="_blank">Set up/start the client</a></li>
<li><a href="#6-play-the-game" target="_blank">Play!</a></li>
<li><a href="#7-homework-instructions" target="_blank">Homework instructions</a></li>
<li><a href="#8-selected-topics" target="_blank">Selected topics</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="astra-setup"> </a>Astra setup</h2>
<h3><a class="anchor" aria-hidden="true" id="1-create-your-astra-streaming-instance"> </a>1. Create your Astra Streaming instance</h3>
<p><em><strong><code>Astra Streaming</code></strong> is the simplest way to get a streaming infrastructure based on Apache Pulsar<br />
with zero operations at all - just push the button and get your streaming.<br />
No credit card required - with the <strong>free tier</strong> comes a generous monthly-renewed credit for you to use.</em></p>
<p><em><strong><code>Astra Streaming</code></strong> is tightly integrated with <code>Astra DB</code>, the database-as-a-service<br />
used in most of our workshops (see below, we will use it momentarily).<br />
<strong>If you already have an Astra account for Astra DB, you can use that<br />
one in the following (and jump to &quot;Create streaming&quot; below)!</strong></em></p>
<p>For more information on Astra Streaming, look at <a href="https://docs.datastax.com/en/astra-streaming/docs/" target="_blank">the docs</a>.<br />
For more information on Apache Pulsar, here is <a href="https://pulsar.apache.org/docs/en/concepts-overview/" target="_blank">the documentation</a>.</p>
<h4><a class="anchor" aria-hidden="true" id="1a-register"> </a>1a. Register</h4>
<p>Register and sign in to Astra at <code>astra.datastax.com</code> by clicking this button (better in a new tab with Ctrl-click or right-click):</p>
<p><a href="https://astra.dev/multiplayer-game" target="_blank"><img src="images/create_astra_button.png" /></a></p>
<p><em>you can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.<br />
Choose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character.<br />
You may be asked to verify your email, so make sure you have access to it.</em></p>
<details><summary>Show me the steps</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra_signup.gif?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="1b-create-streaming"> </a>1b. Create streaming</h4>
<p>Once registered and logged in, you will be able to create a new Astra Streaming topic: it will convey all messages for this app.</p>
<p>You can find the instructions in <a href="https://github.com/datastaxdevs/awesome-astra/wiki/Create-an-AstraStreaming-Topic" target="_blank">this wiki</a>: in our case, the parameters to use are:</p>
<ul>
<li>tenant name: <code>gameserver-&lt;something&gt;</code> (you have to make it unique, so attach a suffix of your choice)</li>
<li>namespace: <code>default</code> (we will NOT need to create a new one)</li>
<li>topic name: <code>worldupdates</code> (persistent=yes, partitioned=no)</li>
</ul>
<blockquote>
<p>Note: technically you can name your namespace and topic anything you want - but then you have to make sure<br />
the environment settings for your API code are changed accordingly (see later).</p>
</blockquote>
<details><summary>Show me the steps</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra_create_streaming_topic_v2.gif?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="1c-retrieve-streaming-connection-parameters"> </a>1c. Retrieve streaming connection parameters</h4>
<p>While you are at it, you should get two pieces of information needed later to connect to the topic from the API code. Those are the &quot;Broker Service URL&quot; and the &quot;Token&quot;,<br />
which can be obtained as described in <a href="https://github.com/datastaxdevs/awesome-astra/wiki/Create-an-AstraStreaming-Topic#-step-4-retrieve-the-broker-url" target="_blank">this wiki article</a>.</p>
<details><summary>Show me how to get the topic connection parameters</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/streaming_secrets.png?raw=true" />
</details>
<blockquote>
<p>The service URL looks something like <code>pulsar+ssl://pulsar-[...].streaming.datastax.com:6651</code>,<br />
while the token is a very long string such as <code>eyJhbGci [...] cpNpX_qN68Q</code>.<br />
<strong>The token is a secret string and you should keep it for yourself!</strong></p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="2-create-your-astra-db-instance"> </a>2. Create your Astra DB instance</h3>
<p>Besides the streaming platform, you'll also need a database for persistence of some<br />
game data (the server-side representation of the &quot;game world&quot;).</p>
<p>Correspondingly, you will need some connection parameters and secrets in order<br />
to later be able to access the database.</p>
<h4><a class="anchor" aria-hidden="true" id="2a-create-the-database"> </a>2a. Create the database</h4>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 20M read/write operations and 80GB storage monthly - sufficient to run small production workloads.</em></p>
<p>You will now create a database with a keyspace in it (a <em>keyspace</em> can contain <em>tables</em>.<br />
Today's application needs just a single table: it will be created for you the first time you<br />
will launch it, so don't worry too much).</p>
<img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/master/images/create_database_button.png" width="250" align=right />
<p>To create the database, locate the &quot;Create database&quot; button on the navigation bar on the left of the Astra UI, click on it and fill the required<br />
values:</p>
<ul>
<li>
<p><strong>For the database name</strong> - use <code>workshops</code>. While Astra DB allows you to fill in these fields with values of your own choosing, please follow our recommendations to ensure the application runs properly.</p>
</li>
<li>
<p><strong>For the keyspace name</strong> - use <code>drapetisca</code>. Please stick to this name, it will make the following steps much easier (you have to customize here and there otherwise). In short:</p>
</li>
<li>
<p><strong>For provider and region</strong>: Choose <strong>GCP</strong>, which is immediately available to a fresh account (AWS and Azure would have to be unlocked, <em>for free</em>, by contacting Support). Region is where your database will reside physically (choose one close to you or your users).</p>
</li>
<li>
<p><strong>Create the database</strong>. Review all the fields to make sure they are as shown, and click the <code>Create Database</code> button. You will be on the <strong>Free</strong> plan.</p>
</li>
</ul>
<table>
<thead>
<tr>
<th>Parameter</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td>Database name</td>
<td>workshops</td>
</tr>
<tr>
<td>Keyspace name</td>
<td>drapetisca</td>
</tr>
</tbody>
</table>
<p>You will see your new database as <code>Pending</code> in the Dashboard;<br />
the status will change to <code>Active</code> when the database is ready. This will only take 2-3 minutes<br />
(you will also receive an email when it is ready).</p>
<details><summary>Show me the how to create my Astra DB</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra_create_db.gif?raw=true" />
To create the database, please note that _the `db_name` and `ks_name` in the above image are just placeholders_.
</details>
<blockquote>
<p><em>Note</em>: if you already have a <code>workshops</code> database, for instance from a previous workshop with us, you can simply create the keyspace with the <code>Add Keyspace</code> button in your Astra DB dashboard: the new keyspace will be available in few seconds.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="2b-create-a-db-token"> </a>2b. Create a DB Token</h4>
<p>You need to create a <strong>DB token</strong>, which the API will later use as credentials to access the DB.</p>
<p>From the Astra DB UI, <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">create a token</a><br />
with <code>Database Administrator</code> roles.</p>
<img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/master/images/orgsettings.png" width="250" align=right />
<ul>
<li>Locate the &quot;Current Organization&quot; menu in the top-left of the Astra UI and select <code>Organization Settings</code></li>
<li>Go to <code>Token Management</code></li>
<li>Pick the role <code>Database Administrator</code> on the select box</li>
<li>Click Generate token</li>
</ul>
<details><summary>Show me the Astra DB token creation</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra-create-token.gif?raw=true" />
</details>
<blockquote>
<p><strong>Tip</strong>: you can quickly get to the &quot;Token Management&quot; also through the &quot;...&quot;<br />
menu next to the list of databases in your main Astra DB UI.</p>
</blockquote>
<p>The &quot;token&quot; is composed by three parts:</p>
<ul>
<li><code>Client ID</code>: it plays the role of <em>username</em> to connect to Astra DB;</li>
<li><code>Client Secret</code>: it plays the role of a <em>password</em>;</li>
<li><code>Token</code> (proper): <em>not needed today</em>. It would be used as API key to access Astra via the API Gateway.</li>
</ul>
<blockquote>
<p>You can either copy and paste the values or download them as a CSV (you'll need the <code>Client ID</code> and <code>Client Secret</code>momentarily). <em>To copy the values you can click on the clipboard icons.</em></p>
</blockquote>
<details><summary>Show me the generated Astra DB token</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra-token.png?raw=true" />
</details>
<blockquote>
<p>Make sure you download the CSV or copy the token values you need: once this page is closed,<br />
you won't be able to see your token again for security reasons! (then again, you can always issue a new token).</p>
</blockquote>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show token creation on screen,
but will then immediately destroy the token for security reasons.
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="2c-download-the-db-secure-connection-bundle"> </a>2c. Download the DB Secure Connection Bundle</h4>
<p>There's a last missing piece needed for the application to successfully connect<br />
to Astra DB: the &quot;secure connect bundle&quot;. You have to download it from the Astra UI<br />
and keep it ready for later usage.</p>
<blockquote>
<p>The secure bundle, a zipfile containing certificates and server address information,<br />
will have to be provided to the Cassandra driver when the connection is established<br />
(see later steps).</p>
</blockquote>
<p>Go to the Astra DB UI, find the <code>workshops</code> database and click on it:</p>
<ol>
<li>click on <code>Connect</code> tab;</li>
<li>click on <code>Connect using a driver</code> (any language will do);</li>
<li>click on the <code>Download Bundle</code> drop-down on the right;</li>
<li>finally click on <code>Secure Connect Bundle (&lt;region&gt;)</code> to start the download. The bundle file should have a name such as <code>secure-connect-workshops.zip</code> and be around 12KB in size. <em>Note: make sure you &quot;Save&quot; the zipfile whole, without unzipping/opening it (as some browser might suggest you to do.</em></li>
</ol>
<details><summary>Show me how to get the Astra DB bundle</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/astra_bundle.png?raw=true" />
</details>
<h2><a class="anchor" aria-hidden="true" id="configure-and-run-the-application"> </a>Configure and run the application</h2>
<h3><a class="anchor" aria-hidden="true" id="3-load-the-project-into-gitpod"> </a>3. Load the project into Gitpod</h3>
<p>Development and running will be done within a Gitpod instance (more on that in a second).</p>
<h4><a class="anchor" aria-hidden="true" id="3a-open-gitpod"> </a>3a. Open Gitpod</h4>
<p>To load the whole project (API + client) in your personal Gitpod workspace, please<br />
Ctrl-click (or right-click and open in new tab) on the following button:</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-streaming-game" target="_blank"><img src="images/open_in_gitpod_button.svg" /></a></p>
<p>(You may have to authenticate with Github or other providers along the process).<br />
Then wait a couple of minutes for the installations to complete, at which point you<br />
will see a message such as <code>CLIENT/API READY TO START</code> in the Gitpod console.</p>
<details><summary>Tell me what the Gitpod button does</summary>
<ul>
<li>An IDE is started on a containerized machine image in the cloud</li>
<li>there, this repo is cloned</li>
<li>some initialization scripts are run (in particular, dependencies get installed)</li>
<li>Gitpod offers a full IDE: you can work there, edit files, run commands in the console, use an internal browser, etc.</li>
</ul>
</details>
<blockquote>
<p>In case you prefer to work <em>on your local computer</em>, no fear! You can simply keep<br />
a console open to run the React client (<code>cd client</code>) and another for the<br />
Python API (<code>cd api</code>). For the former<br />
you will have to <code>npm install</code> and for the latter (preferrably in a virtual environment<br />
to keep things tidy and clean) you will have to install the required dependencies<br />
e.g. with <code>pip install -r requirements.txt</code>.<br />
(Mac users will also have to do a <code>brew install libpulsar</code> for the API to work.)<br />
The rest of this readme will draw your<br />
attention to the occasional differences between the Gitpod and the local routes, but<br />
we'll generally assume that if you work locally you know what you are doing. Good luck!</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="3b-gitpod-interface"> </a>3b. Gitpod interface</h4>
<p>This project is composed of two parts: client and API. For this reason, Gitpod<br />
is configured to spawn <em>three</em> different consoles: the &quot;default&quot; one for<br />
general-purpose actions, an &quot;api&quot; console and a &quot;client&quot; console (these two<br />
will start in the <code>api</code> and <code>client</code> subdirectories for you).<br />
<strong>You can switch between consoles by clicking on the items in the lower-right panels in your Gitpod</strong>.</p>
<details><summary>Show me a map of the Gitpod starting layout</summary>
<img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/gitpod_view.png?raw=true" />
<ol>
<li>File explorer</li>
<li>Editor</li>
<li>Panel for console(s)</li>
<li>Console switcher</li>
</ol>
</details>
<blockquote>
<p>Note: for your convenience, you find this very README open within the Gitpod<br />
text editor.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="4-api-setup"> </a>4. API setup</h3>
<p>Before you can launch the API, you have to configure connection details to it:<br />
you will do it through the dotenv file <code>.env</code>.</p>
<h4><a class="anchor" aria-hidden="true" id="4a-streaming-environment-variables-code-env-code-part-i"> </a>4a. Streaming environment variables (<code>.env</code>, part I)</h4>
<p>You need to pass the streaming connection URL and streaming token to the API for<br />
it to be able to speak to the Streaming topic. To do so, first <strong>go to the API console</strong><br />
and make sure you are in the <code>api</code> subdirectory.</p>
<blockquote>
<p>The <code>pwd</code> command should output <code>/workspace/workshop-streaming-game/api</code>.</p>
</blockquote>
<blockquote>
<p>If you are working locally, make sure you are in the <code>/api</code> subdirectory<br />
of the project for the following commands to work properly. Later anyway,<br />
in order to have both the API and the client running, you will need two<br />
consoles, one in each of the two <code>api</code> and <code>client</code> subdirectories.</p>
</blockquote>
<p>Then create a file <code>.env</code> by copying the <code>.env.sample</code> in the same directory,<br />
with the commands</p>
<pre><code># In the 'api' subdirectory
cp .env.sample .env
gp open .env
</code></pre>
<p>(the second line will simply open the <code>.env</code> file in the editor: you can also simply locate the file in Gitpod's file explorer and click on it).<br />
Fill the first lines in the file with the values found earlier<br />
on your Astra Streaming &quot;Connect&quot; tab (<em>keep the quotes in the file</em>):</p>
<ul>
<li><code>STREAMING_TENANT</code>: your very own tenant name as chosen earlier when creating the topic (step <code>1b</code>); it should be something like <code>gameserver-abc</code>.</li>
<li><code>STREAMING_SERVICE_URL</code>: it looks similar to <code>pulsar+ssl://pulsar-aws-useast2.streaming.datastax.com:6651</code></li>
<li><code>ASTRA_STREAMING_TOKEN</code>: a very long string (about 500 random-looking chars), see step <code>1c</code>. You can copy it on the Astra UI without showing it.</li>
</ul>
<blockquote>
<p>Note: treat your token as a personal secret: do not share it, do not commit it to the repo, store it in a safe place!</p>
</blockquote>
<blockquote>
<p>Note: in case you gave a different namespace/name to your topic, update <code>.env</code> correspondingly.<br />
If, moreover, you work locally you may have to check the <code>TRUST_CERTS</code> variable as well, depending<br />
on your OS distribution. Look into the <code>.env</code> file for some suggestions.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="4b-upload-the-db-secure-bundle-code-env-code-part-ii"> </a>4b. Upload the DB secure bundle (<code>.env</code>, part II)</h4>
<p>Remember the secure connect bundle you downloaded earlier from the Astra DB UI?<br />
It's time to upload it to Gitpod.</p>
<blockquote>
<p>If you work locally, skip the upload and just be aware of the full path to it for what comes next in the <code>.env</code> file.</p>
</blockquote>
<p>Locate the file on your computer using the &quot;finder/explorer&quot;.<br />
Drag and drop the bundle into the Gitpod explorer window: <em>make sure you drop it on the<br />
file explorer window in Gitpod.</em></p>
<details><summary>Show me how to drag-and-drop the bundle to Gitpod</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/drag-and-drop-bundle.png?raw=true" />
</details>
<p>As a check, you may want to verify the file is available in the right location with:</p>
<pre><code>ls -lh /workspace/workshop-streaming-game/secure-connect-*.zip
</code></pre>
<p>The output should tell you the exact path to the file (you can also make sure the file size is around 12KB<br />
while you are at it).</p>
<p><strong>This exact path to the file must go to line <code>ASTRA_DB_SECURE_CONNECT_BUNDLE</code> of the <code>.env</code> file.</strong><br />
The line has been pre-filled for you already, but if the bundle has a different name or is at a<br />
different location (e.g. if you work locally, or your DB has another name),<br />
make sure you change the value accordingly.</p>
<h4><a class="anchor" aria-hidden="true" id="4c-database-access-secrets-code-env-code-part-iii"> </a>4c. Database access secrets (<code>.env</code>, part III)</h4>
<p>With the secure bundle in place and set up in the <code>.env</code>, you can turn to the last missing<br />
piece: the secrets to access the DB.</p>
<p>Insert the Astra DB <code>Client ID</code> and <code>Client Secret</code> you obtained earlier as parts of the &quot;Astra DB Token&quot;<br />
in the <code>.env</code> file (again, keep the quotes around the values):</p>
<pre><code>ASTRA_DB_USERNAME=&quot;tByuQfj...&quot;
ASTRA_DB_PASSWORD=&quot;lGzF5,L...&quot;
</code></pre>
<blockquote>
<p>In case your keyspace has a name other than <code>drapetisca</code>, check the <code>ASTRA_DB_KEYSPACE</code> in your <code>.env</code> as well.</p>
</blockquote>
<p>Congratulations: you should now have completed the <code>.env</code> setup!</p>
<h4><a class="anchor" aria-hidden="true" id="4d-start-the-api"> </a>4d. Start the API</h4>
<p>Make sure you are in the API console and in the <code>api</code> subdirectory.<br />
You can now <strong>start the API</strong>:</p>
<pre><code># In the 'api' subdirectory
uvicorn api:app
</code></pre>
<p>You should see the API start and log some messages in the console, in particular</p>
<pre><code>INFO:     Application startup complete.
INFO:     Uvicorn running on http://127.0.0.1:8000 (Press CTRL+C to quit)
</code></pre>
<p>Congratulations: the API is up and is ready to accept client requests.<br />
Leave it running and turn your attention to the client.</p>
<blockquote>
<p>Note: this is how you start the API in a development environment. To deploy<br />
to production, you should set up a multi-process system service for <code>uvicorn</code><br />
with the <code>--workers</code> option and put the whole thing behind a<br />
reverse proxy. <em>This is not covered here</em>.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="5-client-setup"> </a>5. Client setup</h3>
<p>Make sure you <strong>go to the client console</strong> for the following<br />
(to switch consoles, look at the lower-right panel in your Gitpod layout).<br />
You should be in the <code>client</code> project subdirectory (i.e. the <code>pwd</code> command should print <code>/workspace/workshop-streaming-game/client</code>).</p>
<h4><a class="anchor" aria-hidden="true" id="5a-install-dependencies"> </a>5a. Install dependencies</h4>
<p>First ensure all required dependencies are installed:</p>
<pre><code># In the 'client' subdirectory
npm install
</code></pre>
<blockquote>
<p>Note: the command would take a few minutes on a fresh directory; we secretly instructed Gitpod<br />
to preinstall them just to save you some time in this step - still, we want<br />
you to go through it. Obviously, if you are working on your local environment,<br />
this will be slower.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="5b-start-the-client"> </a>5b. Start the client</h4>
<p>The client is ready to go! <strong>Launch it</strong> in development mode with:</p>
<pre><code># In the 'client' subdirectory
npm start
</code></pre>
<p>Let's assume you are working within Gitpod, which wraps locally-exposed ports<br />
and makes them accessible through ordinary HTTPS domain names.<br />
As the client is available, Gitpod will automatically open it in its &quot;simple browser&quot;,<br />
using a domain such as <code>https://3000-tan-swallow-2yz174hp.ws-eu17.gitpod.io</code>.<br />
This URL can be obtained also by typing, in the general-purpose Gitpod console,</p>
<pre><code>gp url 3000
</code></pre>
<p>(3000 being the port number locally used by npm to serve the client).<br />
This will match the URL shown in the address bar of your simple browser.</p>
<p>Note that you can also take this URL and open the application in a new tab,<br />
<strong>which you are encouraged to do to use your full screen</strong>.</p>
<blockquote>
<p>Note: we set up Gitpod for this workshop so as to make this URL accessible by anyone, to allow you<br />
to paste the link to your friends, thereby inviting them to your own game instance!</p>
</blockquote>
<blockquote>
<p>If you are running everything locally on your computer, instead, you can<br />
open the client on <code>http://localhost:3000</code> and use the<br />
default API location of <code>ws://localhost:8000</code> to enter the game.</p>
</blockquote>
<blockquote>
<p>Note: this is how you launch the client in development mode. For deploying<br />
to production, you should first build the project and then serve it from<br />
a static Web server. <em>This is not covered here</em>.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="6-play-the-game"> </a>6. Play the game!</h3>
<p>We finally have all pieces in place:</p>
<ul>
<li>an Astra Streaming topic;</li>
<li>an API bridging it to ...</li>
<li>... a client ready to establish WebSocket connections.</li>
<li>(and an Astra DB instance acting as persistent storage to back the API)</li>
</ul>
<p>It is time to play!</p>
<h4><a class="anchor" aria-hidden="true" id="6a-enter-the-game"> </a>6a. Enter the game</h4>
<p>Change your name if you desire (a spider name is drawn at random for you).<br />
You will also see that you are given a (read-only) unique player ID and that an API address<br />
is configured for the client to establish WebSocket connections to.</p>
<blockquote>
<p>The API location points to the instance of the API running alongside the client:<br />
you should generally not have to change it (but please notice the protocol is<br />
either <code>ws</code> or <code>wss</code>, which stand for WebSocket and Secure WebSocket respectively).</p>
</blockquote>
<p>To enter the game, click the &quot;Enter Game&quot; button.</p>
<details><summary>Show me the "Enter Game" form</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/drapetisca_2.png?raw=true" />
</details>
<p>Well done: you are in the game. You should see your player appear in the arena!</p>
<ul>
<li>To control your player, either use the on-screen arrow buttons or, after bringing the game field into focus, your keyboard's arrow keys;</li>
<li>you can use the in-game chat box on the left.</li>
</ul>
<details><summary>Show me the player after entering the game</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/drapetisca_3_v2.png?raw=true" />
</details>
<blockquote>
<p><strong>Note</strong>: if you experience a laggy game, especially with several players at once,<br />
it is probably due to the fact that you have no control over the physical location of your Gitpod instance:<br />
it may have been deployed far from the database. Remember that in a real-life online game great care<br />
is taken to keep all parts close to each other to keep latencies under control.<br />
If you want to play the game nevertheless, you can set the <code>USE_IN_MEMORY_STORAGE</code> variable<br />
to <code>&quot;1&quot;</code> in your <code>.env</code> and then stop-and-restart the API: this will replace usage of Astra DB<br />
with an in-memory local store; it is a development-only solution, however, that would of course<br />
not work were you to scale to several running instances of the API.</p>
</blockquote>
<p>Anything your player does is sent to the API through a WebSocket in the form of an &quot;update message&quot;;<br />
from there, it is published to the Astra Streaming topic (and persisted to the database).<br />
The API will then pick up the update<br />
and broadcast to all players, whose client will process it, eventually leading to a refresh of the game status<br />
on the front-end. All this happens in a near-real-time fashion at every action by every player.</p>
<blockquote>
<p>Note that the game shows the last sent message and the last received messages for you to better inspect<br />
the messaging pattern at play.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="6b-try-to-cheat"> </a>6b. Try to cheat</h4>
<p>Let's be honest: there's no multiplayer game without cheaters - at least, cheat attempts.<br />
So, for example, try to <em>walk beyond the boundaries of the play area</em>, to see what happens.<br />
Notice the &quot;Position&quot; caption on the left sidebar? If you keep an arrow key pressed<br />
long enough, you will sure be able to bring that position to an illegal value such as <code>(-1, 0)</code>.<br />
But as soon as you release the key, the position bounces back to a valid state.</p>
<p>Here's the trick: this &quot;position&quot;, shown in the client, is nothing more than a variable<br />
in the client's memory. Every update (including <code>(-1, 0)</code>) is sent to the API, which<br />
is the sole actor in charge of validation: an illegal value will be corrected and sent back<br />
to all clients (<em>consider the API has access to the game-world state persisted on DB<br />
and can handle collisions and the like</em>).<br />
In particular, your own client will adjust knowledge of its own position<br />
based on this feedback from the API - which is why you see the illegal value only briefly.</p>
<p>All of this must happen asynchronously, as is the nature of the communication between client<br />
and API. There is a lesson here, which has been hard-earned by online game devs over the years:<br />
<em>never leave validity checks in the hand of the client</em>.</p>
<blockquote>
<p>Remember the hordes of cheaters in ... er ... Diablo I ?</p>
</blockquote>
<p><strong>Implications on the architecture</strong></p>
<p>Unfortunately such an all-server architecture is more complex to achieve.<br />
One has to introduce a &quot;generation counter&quot; to avoid accidentally triggering<br />
infinite loops of spurious player-position updates - you can see this<br />
ever-increasing generation counter (<code>generation</code>) if you inspect the<br />
player-position updates shown at the bottom of the application.</p>
<p>In the client code, the crucial bit is to accept updates to your-own-position<br />
coming from the server, <em>only if they are recent enough</em>. For further inspection,<br />
have a look at:</p>
<ul>
<li>API: usage of <code>validatePosition</code> at line 66 of <code>api.py</code>;</li>
<li>Client: condition on <code>generation</code> at line 109 of <code>App.js</code> before invoking <code>setPlayerX</code> and <code>setPlayerY</code>.</li>
</ul>
<blockquote>
<p>Note: in this architecture, we very much <strong>want</strong> to have a server between<br />
clients and Pulsar topic, with the responsibility of performing validations.<br />
Even more so in a complex game, where each client action (message) triggers<br />
potentially several actions in the world. But we want to mention, in passing by,<br />
that Pulsar also offers its own<br />
<a href="https://pulsar.apache.org/docs/en/client-libraries-websocket/" target="_blank">native WebSocket interface</a><br />
(and so does Astra Streaming),<br />
for clients to directly connect to topics using that protocol.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="6c-bring-your-friends"> </a>6c. Bring your friends</h4>
<p>But wait ... this is a <em>multiplayer</em> game, isn't it? So, go ahead and open a new<br />
browser tab, then enter the game as someone else.</p>
<p>Hooray! As soon as you move around with this new player,<br />
you will see the whole architecture at work:</p>
<ol>
<li>client sends updates on your player's position through the &quot;player websocket&quot;;</li>
<li>API checks game state on DB and validates this update, taking action if needed;</li>
<li>API (a) publishes the validated player update to the Astra Streaming topic and (b) persists new game-state to DB;</li>
<li>API receives back new messages by listening to this same Astra Streaming topic;</li>
<li>API broadcasts updates on any player to all connected clients through the &quot;world websocket&quot;;</li>
<li>at each such update, the client's game arena is adjusted (for all connected clients).</li>
</ol>
<p>What is really cool is that <strong>you can give this URL to your friends</strong> and have them<br />
enter your very own game!</p>
<p><em>Please do this and tell the world about how easy it is to build a multiplayer real-time<br />
game with Astra Streaming!</em></p>
<h4><a class="anchor" aria-hidden="true" id="6d-fun-with-the-streaming-ui"> </a>6d. Fun with the Streaming UI</h4>
<p>The Astra Streaming interface makes it possible to eavesdrop on the topic and<br />
observe the messages passing through it. This may prove very useful for<br />
debugging.</p>
<p>In the Astra Streaming UI, head to the &quot;Try Me&quot; tab and make sure:</p>
<ul>
<li>the namespace and the (producer, consumer) topics are set to the values used earlier;</li>
<li>connection type is &quot;Read&quot;;</li>
<li>read position is &quot;Latest&quot;</li>
</ul>
<p>Good, now click &quot;Connect&quot;.</p>
<details><summary>Show me the "Try Me" interface</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/eavesdrop_streaming.gif?raw=true" />
</details>
<details><summary>A demo video of the "Try Me" feature (Youtube)</summary>
    <a href="https://youtu.be/WWYXeZh0S9k" target="_blank">
        <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/try-me-demo-video-thumbnail.png?raw=true" />
    </a>
</details>
<p>You now have a privileged view over the messages flowing through the Streaming<br />
topic. Now try writing something in the Chat box: can you see the corresponding<br />
message in the Streaming UI?</p>
<p>What kind of message do you see, instead, if you move you player?</p>
<p>But wait, there's more: now you can <strong>hack the system</strong>! Indeed, this same interface lets you<br />
produce surreptitious messages into the topic (&quot;Send&quot; button on the Streaming UI).<br />
Try to insert a message such as:</p>
<pre><code>{
    &quot;messageType&quot;: &quot;chat&quot;,
    &quot;payload&quot;: {
        &quot;id&quot;: &quot;000&quot;,
        &quot;name&quot;: &quot;Phantom!&quot;,
        &quot;text&quot;: &quot;Booo!&quot;
    },
    &quot;playerID&quot;: &quot;nonexistent&quot;
}
</code></pre>
<p>and keep an eye on the chat box.</p>
<p>Even better, try to inject a message such as <em>(you may have to adjust the <code>x</code>, <code>y</code> coordinates for this to be real fun)</em>:</p>
<pre><code>{
    &quot;messageType&quot;: &quot;brick&quot;,
    &quot;payload&quot;: {
        &quot;name&quot;: &quot;phantom brick!&quot;,
        &quot;x&quot;: 0,
        &quot;y&quot;: 0
    }
}
</code></pre>
<p>what happens in the game UI when you to this? Can you walk to that spot? (Why?)</p>
<blockquote>
<p>Also, have you noticed that the &quot;Try Me&quot; interface shows how each message you publish to the topic is echoed back to you?<br />
This is done by the API logic and is part of the game design.</p>
</blockquote>
<p>Now, you just had a little fun: but, seriously speaking, this ability to manually intervene in the stream of messages makes for a valuable debugging tool.</p>
<h4><a class="anchor" aria-hidden="true" id="6e-a-quick-look-at-the-data-on-db"> </a>6e. A quick look at the data on DB</h4>
<p>Any change to the game-world, either originated in the API or coming from<br />
a player (and then just validated at API level) is persisted on database.<br />
If you are curious, you can look at the raw data directly within the Astra DB UI.</p>
<p>Each time the API starts, it will generate a new &quot;game ID&quot;, under which all info<br />
pertaining to this particular game will be stored. In fact, <code>game_id</code> plays the<br />
role of<br />
<a href="https://docs.datastax.com/en/astra-cql/doc/cql/ddl/dataModelingApproach.html" target="_blank">partition key</a> in the underlying <code>drapetisca.objects_by_game_id</code> table.</p>
<blockquote>
<p>The topic of data storage and data modeling in Cassandra is huge and we won't<br />
do it justice here. Just bear with us to see the game data, and if you want<br />
to know more you can start from <a href="https://www.datastax.com/learn/data-modeling-by-example" target="_blank">Data modeling by example</a> and <a href="https://www.datastax.com/cassandra">What is Cassandra?</a>. You will embark on a long and exciting journey!</p>
</blockquote>
<p>Locate the &quot;CQL Console&quot; tab for the <code>workshops</code> database in your Astra DB dashboard<br />
and click on it. An interactive shell will be spawned for you, to type the following commands:</p>
<pre lang="sql"><code>USE drapetisca ;
SELECT * FROM objects_by_game_id ;
</code></pre>
<p>You should see several lines in the output, corresponding to the objects present in the game(s)<br />
and their properties.</p>
<blockquote>
<p>If you already started several games (e.g. by hitting Ctrl-C and restarting <code>uvicorn</code> in the API console), notice that the info for each of them is neatly grouped by the value of the <code>game_id</code> column.</p>
</blockquote>
<details><summary>Show me the game data in the Astra DB CQL Console</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/cql_console.gif?raw=true" />
</details>
<h3><a class="anchor" aria-hidden="true" id="7-homework-instructions"> </a>7. Homework instructions</h3>
<p>Here are some more details on how to do the homework. We require two modifications<br />
to the code, one on the API and one on the client. Once you change both, and restart,<br />
you will be able to take a screenshot showing the new game appearance and submit<br />
it to us!</p>
<h4><a class="anchor" aria-hidden="true" id="7a-server-side"> </a>7a. Server side</h4>
<p>We want a greeting message to be sent from the API to a new client right after<br />
they join. To do so, the <code>api.py</code> already imports a function <code>makeWelcomeUpdate</code><br />
that returns a &quot;chat message&quot; ready to be sent through the WebSocket.<br />
You may also want to make use of variable <code>newPlayerName</code> that is made available<br />
in the API code.</p>
<p><strong>You should add a line in the function <code>playerWSRoute</code> that creates the welcome<br />
chat message and sends it to the WebSocket</strong>. <em>Suggestion: this is really not<br />
so different from the geometry update any new client receives upon connecting.</em></p>
<h4><a class="anchor" aria-hidden="true" id="7b-client-side"> </a>7b. Client side</h4>
<p>We want the player names on the game field to have the same color as the player<br />
icons instead of always dark grey as they are now. If you look into <code>GameField.js</code>,<br />
you'll notice that the SVG <code>text</code> element currently has a class name <code>&quot;player-name&quot;</code>.</p>
<p><strong>Make it so that players (self/other) use different class names in their <code>text</code><br />
element and have a color matching their icon</strong>. <em>Suggestion: the right class name<br />
is already calculated a few lines above for you to use (you can check in <code>App.css</code> as well)</em>.</p>
<h4><a class="anchor" aria-hidden="true" id="7c-restart-test-and-take-a-screenshot"> </a>7c. Restart, test and take a screenshot</h4>
<p>Remember to stop and restart the API: go to its console, hit Ctrl-C and<br />
re-run <code>uvicorn api:app</code> to do so. All current WebSocket connections will<br />
be lost.</p>
<p>The client is running in development mode, so it should pick up any changes<br />
live and be immediately ready to serve the new version: reloading the app page<br />
(and re-entering the game) should be enough.</p>
<p>At that point you will be playing the improved game: homework completed!</p>
<details><summary>Show me the new features in the game</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/drapetisca_homework.png?raw=true" />
</details>
<h3><a class="anchor" aria-hidden="true" id="8-selected-topics"> </a>8. Selected topics</h3>
<p>Let us briefly mention some specific parts of the implementation of this game.</p>
<h4><a class="anchor" aria-hidden="true" id="8a-websockets-and-react"> </a>8a. WebSockets and React</h4>
<p>API and client communicate through WebSockets: in this way, we have a connection<br />
that is kept open for a long time and allows for a fast exchange of messages<br />
without the overhead of establishing a new connection for each message;<br />
moreover, this allows the server to push data without waiting for the client<br />
to initiate the exchange (as in the obsolete technique of client-side polling).<br />
WebSockets follow a robust and standardized <a href="https://datatracker.ietf.org/doc/html/rfc6455" target="_blank">protocol</a><br />
which makes it possible for us developers to concentrate on our game logic<br />
instead of having to worry about the communication internals.</p>
<p>In particular, this game uses two WebSockets:</p>
<ul>
<li>a &quot;player&quot; one for bidirectional client/server data transmission in a direct fashion;</li>
<li>a &quot;world&quot; one where the API route all messages picked up by the streaming topic. Most game status updates go through this route (with the exception of those directed at an individual player).</li>
</ul>
<p>You can find the corresponding variables <code>pws</code> and <code>wws</code> in the client code, respectively.</p>
<p>In Javascript, one <em>subscribes to an event</em> on an open WebSocket, providing<br />
a callback function with <code>webSocket.onmessage = &lt;callback&gt;</code>. But beware:<br />
if you simply try to read a React state (such as <code>generation</code>) from within<br />
the callback, you will generally get a stale value, <em>corresponding to the<br />
state when the subscription was made</em>. In practice, the state variable<br />
is &quot;closed over&quot;. To overcome this problem, and be able to access the latest<br />
updated value of the state, we declare a React &quot;reference&quot; with <code>useRef</code><br />
and, after linking it to the state we want to read, we use this reference<br />
within the callback to dynamically retrieve the current value of the state.</p>
<details><summary>Look at lines 49-50 and then 103 of `App.js`, for example.</summary>
    <img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/main/images/ref_code_1.png?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="8b-fastapi"> </a>8b. FastAPI</h4>
<p>This game's architecture involves a server. Indeed, we would not be able<br />
to implement it using only serverless functions, at least not in a way similar<br />
to what you see here, because of statefulness. We need a server able to sustain<br />
the WebSocket connections for a long time, on one side, and to maintain<br />
long-running subscriptions to the Pulsar topics on the other side.</p>
<p>We chose to create the API in Python, and to use<br />
<a href="https://fastapi.tiangolo.com/" target="_blank">FastAPI</a>, for a couple of very valid<br />
reasons. FastAPI integrates very well with the async/await features of modern<br />
Python, which results in a more efficient handling of concurrency. Moreover,<br />
it supports WebSockets (through its integration with<br />
<a href="https://www.starlette.io/" target="_blank">Starlette</a>) with a natural syntax that reduces<br />
the need for boilerplate code to near zero.</p>
<blockquote>
<p>There are other cool features of FastAPI (besides its namesake high performance),<br />
which we do not employ here but make it a prime choice. There is a clever<br />
mechanism to handle route dependencies aimed at reducing the amount of &quot;boring&quot;<br />
code one has to write; and there is native support for those small tasks<br />
that sometimes you have to trigger asynchronously right after a request completes,<br />
those that in other frameworks would have required to set up machinery like Celery.</p>
</blockquote>
<p>Have a look at <code>api.py</code> to see how a WebSocket connection is handled: decorating<br />
a certain function with <code>@app.websocket(...)</code> is almost everything you need to<br />
get started. One of the arguments of the function will represent the WebSocket<br />
itself, supporting methods such as <code>send_text</code> and <code>receive_text</code>. Each<br />
active WebSocket connection to the server will spawn an invocation of this<br />
function, which will run as long as the connection is maintained: the support<br />
for async/await guarantees that these concurrent executions of the<br />
WebSocket function will be scheduled efficiently with no deadlocks.</p>
<h4><a class="anchor" aria-hidden="true" id="8c-svg-tricks"> </a>8c. SVG Tricks</h4>
<p>One of the React components in the client code is the <code>GameField</code>, which<br />
represents an area where we draw the players. This is a single large SVG<br />
element, whose child elements are managed with the usual <code>jsx</code> syntax.</p>
<p>A technique that proved useful in this game is that of defining, and then<br />
re-using multiple times, &quot;patterns&quot;, basically as sprites. If you look<br />
at the <code>GameField.js</code> render code, you notice that the SVG first declares<br />
some <code>pattern</code> elements with certain <code>id</code>s (such as <code>lyco_other</code>).<br />
These patterns are then employed in various parts of the SVG to &quot;fill&quot;<br />
rectangles, which effectively makes it possible to use them as repeated sprites:</p>
<pre><code>    &lt;rect .... fill=&quot;url(#lyco_other)&quot;&gt;&lt;/rect&gt;
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="the-end"> </a>The End</h2>
<p>Congratulations, you made it to the end! Please share the URL of your game with<br />
your friends: who does not love a little cozy spider gathering?</p>
<p><em>(Please notice that after some inactivity your Gitpod instance will be hibernated:<br />
you will need to re-start client and server to be able to play again.)</em></p>
<p>Don't forget to complete and submit your <a href="#homework" target="_blank">homework</a> to claim<br />
your badge, and see you next time!</p>
<blockquote>
<p>DataStax Developers</p>
</blockquote>
<p><img src="https://github.com/datastaxdevs/workshop-streaming-game/raw/master/images/Theridion_grallator.png" alt="Theridion grallator" /></p>
