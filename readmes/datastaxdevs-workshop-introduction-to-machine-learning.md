<h1><a class="anchor" aria-hidden="true" id="machine-learning-with-apache-spark-cassandra"> </a>Machine Learning with Apache Spark &amp; Cassandra</h1>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-machine-learning/raw/master/images/intro-to-ML-cover.png" alt="Workshop cover" /></p>
<p>Welcome to the <strong>Introduction to machine learning</strong> workshop! In this two-hour workshop, we show you how you can leverage the distributed <code>NoSQL database Apache Cassandra™</code> to save your datasets, train you models and predict at scale.</p>
<p>Want to learn about the awesomeness of distributed databases and computational systems?<br />
Want to get hands-on with DataStax's Cassandra-as-a-Service offering (<em>for free!</em>) and use popular Machine Learning tools and algorithms?<br />
Join in and follow along with this workshop!</p>
<ul>
<li>
<p>Spark + Cassandra = :heart:</p>
</li>
<li>
<p>Spark + DataStax Astra DB = :fire: :rocket: :stars:</p>
</li>
</ul>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<ol>
<li><a href="#1-objectives" target="_blank">Objectives</a></li>
<li><a href="#2-frequently-asked-questions" target="_blank">Frequently asked questions</a></li>
<li><a href="#3-materials-for-the-session" target="_blank">Materials for the Session</a></li>
<li><a href="#4-create-your-astra-db-instance" target="_blank">Create your Database</a></li>
<li><a href="#5-setup" target="_blank">Setup</a></li>
<li><a href="#6-algorithms" target="_blank">Algorithms</a></li>
<li><a href="#7-homework" target="_blank">Homework</a></li>
<li><a href="#8-whats-next" target="_blank">What's NEXT</a></li>
</ol>
<blockquote>
<p><a href="#-start-hands-on" target="_blank">🔖 Accessing HANDS-ON</a></p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="1-objectives"> </a>1. Objectives</h2>
<p>1️⃣ <strong>Learn about the NoSQL database Apache Cassandra™</strong></p>
<p>2️⃣ <strong>Meet Apache Spark™ and its superpowers</strong></p>
<p>3️⃣ <strong>Learn about the main ideas and practice of Machine Learning (ML)</strong></p>
<p>4️⃣ <strong>Get a practical understanding of some of the main ML algorithms</strong></p>
<p>🚀 <strong>Have fun with an interactive session (Python interactive notebooks + Cassandra + Spark)</strong></p>
<h2><a class="anchor" aria-hidden="true" id="2-frequently-asked-questions"> </a>2. Frequently asked questions</h2>
<details>
<summary><strong>1️⃣ Can I run this workshop on my computer?</strong></summary>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need: <code>git</code>, <code>docker</code>, <code>docker-compose</code>.</p>
<p>In this readme, we try to provide instructions for local development as well - but keep in mind that the main focus is development on Gitpod, hence <strong>we can't guarantee live support</strong> about local development in order to keep on track with the schedule. However, we will do our best to give you the info you need to succeed.</p>
</details>
<details>
<summary><strong>2️⃣ Are there other prerequisites?</strong></summary>
<p>You will need enough <em>real estate</em> on screen, we will ask you to open a few windows and it would not fit on mobiles (tablets should be OK).</p>
<p>You will need an Astra account: don't worry, we'll work through that in the following.</p>
</details>
<details>
<summary><strong>3️⃣ Do I need to pay for anything for this workshop?</strong></summary>
<p><strong>No.</strong> All tools and services we provide here are FREE. FREE not only during the session but also afterwards.</p>
</details>
<details>
<summary><strong>4️⃣ Will I get a certificate if I attend this workshop?</strong></summary>
<p>Attending the session is not enough. You need to complete the <a href="#7-homework" target="_blank">homework detailed below</a><br />
and you will get a nice badge that you can share on linkedin or anywhere else<br />
<em>(the badge conforms to the &quot;open badge&quot; specifications)</em>.</p>
</details>
<h2><a class="anchor" aria-hidden="true" id="3-materials-for-the-session"> </a>3. Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to work at your own pace,<br />
we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="/slides/slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">Discord chat</a></li>
<li><a href="https://stackoverflow.com/questions/ask?tags=cassandra" target="_blank">Ask on StackOverflow</a> (or <a href="https://dba.stackexchange.com/questions/ask?tags=cassandra">StackExchange</a> for operators)</li>
</ul>
<h3><a class="anchor" aria-hidden="true" id="requirements"> </a>Requirements</h3>
<ul>
<li><a href="https://git-scm.com/book/en/v2/Getting-Started-Installing-Git" target="_blank">git</a></li>
<li><a href="https://astra.dev/yt-8-31" target="_blank">DataStax Astra Registration</a> (<em>sign up with the email you used to register for the workshop!</em>)</li>
<li><a href="https://www.docker.com/products/docker-desktop" target="_blank">Docker</a></li>
<li><a href="https://docs.docker.com/compose/install/" target="_blank">Docker-compose</a> (<em>included with Docker Desktop for Mac and Windows installs</em>)</li>
</ul>
<hr />
<h1><a class="anchor" aria-hidden="true" id="start-hands-on"> </a>🏁 Start Hands-on</h1>
<h2><a class="anchor" aria-hidden="true" id="4-create-your-astra-db-instance"> </a>4. Create your Astra DB instance</h2>
<p><em><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, 40M read/write operations and about 80GB storage monthly for free - sufficient to run small production workloads. If you end your credits the databases will pause, no charge</em></p>
<p>Leveraging the <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">Database creation guide</a>, create a database. <em>Right-Click the following button</em> and <em>Open in a new TAB:</em></p>
<p><a href="https://astra.dev/yt-8-31" target="_blank" target="_blank" rel="noopener"><img src="images/create_astra_db_button.png?raw=true" /></a></p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Database Name</strong></td>
<td><code>workshops</code></td>
</tr>
<tr>
<td><strong>Keyspace Name</strong></td>
<td><code>machine_learning</code></td>
</tr>
<tr>
<td><strong>Regions</strong></td>
<td>Select <code>GOOGLE CLOUD</code>, then an Area close to you, then a region with no LOCKER 🔒 icons, those are the region you can use for free.</td>
</tr>
</tbody>
</table>
<blockquote>
<p><strong>ℹ️ Note:</strong> If you already have a database <code>workshops</code>, simply add a keyspace <code>machine_learning</code> using the <code>Add Keyspace</code> button on the bottom right hand corner of the DB dashboard page.</p>
</blockquote>
<p>While the database is being created, you will also get a<br />
<a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#b-prerequisites" target="_blank"><strong>Security token</strong></a>:<br />
save it somewhere safe, since you'll need it later during setup.</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p>The database status will change from <code>Pending</code> to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<blockquote>
<p>If you already had the database, you can still create a new token: see <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#b-prerequisites" target="_blank">here</a>.</p>
</blockquote>
<p>Then go to the <em>Connect</em> tab for your database and download your <strong>Secure Connect Bundle</strong>, as described <a href="https://awesome-astra.github.io/docs/pages/astra/download-scb/" target="_blank">at this link</a>. It's a ZIP file of about 12Kb, which you will need later.</p>
<p><a href="#-table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-setup"> </a>5. Setup</h2>
<p>We suggest to use Gitpod: <strong>right-click</strong> on the following button and <strong>open in new tab</strong>:</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-introduction-to-machine-learning" target="_blank"><img src="images/open_in_gitpod.svg?raw=true" /></a></p>
<blockquote>
<p>You can also run everything locally. In this case, you may need to know what you are doing, as we won't be able to troubleshoot live.</p>
</blockquote>
<p>If you are on Gitpod, simply follow the on-screen instructions to get everything running:</p>
<ul>
<li>⌛ <em>Wait 2-3 minutes as your IDE (and Linux box) gets provisioned...</em></li>
<li>When prompted in the Gitpod Console, enter the following information to connect to DB:
<ul>
<li>Astra DB Token ID</li>
<li>Astra DB Token Secret</li>
<li>Keyspace name (<code>machine_learning</code> by default)</li>
</ul>
</li>
<li>When asked, drag-and-drop (or copy) the Secure bundle to the required destination</li>
<li>⌛ <em>Wait another 1-2 minutes (while tables are created and populated in your database) ...</em></li>
<li>Eventually the Gitpod console will spawn a new tab with the Jupter UI running (<strong>check your pop-up blocker</strong> to let it through)</li>
<li>Insert the password <code>mlrules</code> to access the Jupyter UI</li>
</ul>
<details><summary>Steps for running locally (click to show)</summary>
<ul>
<li>Clone the repo, <code>cd</code> into it and launch <code>./init_tools.sh</code> (to get the required tools ready and <code>docker-compose</code> up and running).</li>
<li>Once that is finished, launch <code>./setup.sh</code> and follow the instructions, similarly as for Gitpod.</li>
</ul>
<blockquote>
<p>You may need to use some custom IP instead of <code>localhost</code> if you<br />
use docker-for-mac, docker-for-windows or similar installation.</p>
</blockquote>
<blockquote>
<p><em>Known Issue</em>: in some cases executing the exercises may lead to memory issues, especially<br />
on weaker or non-Linux machines due to docker limitations on memory. If you have any<br />
issues with exercises after the first few, try to clean up and start again<br />
<code>docker-compose kill &amp;&amp; docker-compose down &amp;&amp; docker-compose up -d</code>.<br />
You may need to repeat steps of the notebook you were working on.</p>
</blockquote>
</details>
<details><summary>🤦 "I messed up and I need to re-initialize" (click to show)</summary>
<p>Don't worry, it happens. Re-initialization of the full repo goes as follows:</p>
<ul>
<li><code>./init_tools.sh</code>: this downloads Astra DB client utilities and starts your <code>docker-compose</code> image(s). Make sure you have no running<br />
Docker images before re-launching this.</li>
<li><code>./setup.sh</code>: this allows you to re-create the secrets file. Launch again if you messed up with token info, bundle zipfile and so on. This, in turn, invokes the following ...</li>
<li><code>./initialize/initialize.sh</code>: table creation and bulk migration of needed datasets from files to database tables.</li>
</ul>
</details>
<h2><a class="anchor" aria-hidden="true" id="6-algorithms"> </a>6. Algorithms</h2>
<p>The main Jupyter web interface will list five numbered notebooks available.<br />
Each one illustrates a key algorithm in Machine Learning:</p>
<ul>
<li><strong>K-Means</strong> Clustering</li>
<li><strong>Naive Bayes</strong> inference</li>
<li><strong>Random Forest</strong> classification</li>
<li><strong>FP-Growth</strong> recommendation</li>
<li><strong>Collaborative Filtering</strong> recommendation</li>
</ul>
<p>Click a notebook to open it in a new tab, then you can run all code cells<br />
sequentially by clicking on them and hitting <code>Ctrl + Enter</code>.<br />
Watch each code cell execute (its numbering will display <code>[*]</code> while running)<br />
and, when it finishes, move on to the next.</p>
<blockquote>
<p><em>Note</em>: if you see errors such as empty or nonexisting tables, chances are<br />
you started the lab while the database was still being created or was in<br />
&quot;maintenance mode&quot;. To fix this, simply issue the command <code>./initialize/initialize.sh</code><br />
and wait one minute or so for it to complete.</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="7-homework"> </a>7. Homework</h2>
<p><em>Now it's your turn!</em></p>
<p>Try to improve the accuracy (as computed on the test set) of the<br />
Random Forest classification model by tweaking its parameters.<br />
You will need to re-train the model and re-evaluate the accuracy at each try.</p>
<blockquote>
<p>Tip: look at the <a href="https://spark.apache.org/docs/latest/api/python/reference/api/pyspark.ml.classification.RandomForestClassifier.html" target="_blank">documentation</a><br />
as a starting point, to see what options there are, pyspark.ml.classification.RandomForestClassifier).</p>
</blockquote>
<img src="https://github.com/datastaxdevs/workshop-introduction-to-machine-learning/raw/master/images/intro-ml-badge.png?raw=true" width="150" align="right" />
<p>You can proceed by selecting some parameters (such as <code>numTrees</code> or <code>maxDepth</code>),<br />
increase and decrease their value a bit, and compare the accuracy with the<br />
&quot;baseline&quot; result from the model you started with.<br />
Ideally you should change one parameter at a time,<br />
keeping all others the same as the &quot;baseline&quot;.<br />
Is the model accuracy more sensitive to <code>numTrees</code> or <code>maxDepth</code>?</p>
<p>If you really want to get serious, you could even automate this<br />
<em>hyperparameter search</em> in the code itself - possibly on a <em>grid</em> of choices<br />
for the parameters you want to test, such as:</p>
<pre><code>{numTrees in [5, 10, 20]} x {maxDepth in [2, 5, 10]} x { ... other parameters ... } ...
</code></pre>
<p><strong>Provide a screenshot of an improved choice of parameters, yielding an<br />
accuracy higher than the &quot;baseline&quot;</strong><br />
(Note: an improvement of at least 0.05 is possible).</p>
<p>Go to <a href="https://dtsx.io/homework-intro-ml" target="_blank">this form</a> to submit your homework, give us a few days to review it,<br />
and wait for your well-deserved &quot;Intro to Machine Learning&quot; badge!</p>
<h2><a class="anchor" aria-hidden="true" id="8-what-s-next"> </a>8. What's NEXT</h2>
<p>We've just scratched the surface of what you can do with</p>
<ul>
<li>Astra DB, built on Apache Cassandra™;</li>
<li>Apache Spark™;</li>
<li>the awesome algorithm in the Machine Learning field.</li>
</ul>
<p>Go take a look at <a href="https://www.datastax.com/dev" target="_blank">DataStax for Developers</a> to see what else is possible.<br />
There's plenty to dig into!</p>
<p><strong>Congratulations: you made to the end of today's workshop.</strong></p>
<p>Don't forget to <a href="#7-homework" target="_blank">submit your homework</a> and be awarded a nice verified badge!</p>
<p><strong>... and see you at our next workshop!</strong></p>
<blockquote>
<p>Sincerely yours, The DataStax Developers</p>
</blockquote>
