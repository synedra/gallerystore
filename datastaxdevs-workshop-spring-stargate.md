<h1><a class="anchor" aria-hidden="true" id="img-src-https-github-com-datastax-academy-astraportia-blob-master-0-materials-ico-jpg-raw-true-alt-ok-workshop-spring-data-cassandra-and-stargate"> </a><img src="https://github.com/DataStax-Academy/AstraPortia/blob/master/0_materials/ico.jpg?raw=true" alt="ok" /> Workshop Spring Data Cassandra and Stargate</h1>
<p><a href="https://gitpod.io/#https://github.com/DataStax-Academy/workshop-spring-data-cassandra" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p>Today we showcase an application using <strong>Apache Cassandra™</strong> as a backend implemented with <strong>Spring Boot</strong>, <strong>Spring Data</strong>, the <strong><a href="http://stargate.io" target="_blank">Stargate</a></strong> and related SDK.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/splash.png?raw=true" alt="SplashScreen" /></p>
<p>Which better business domain than the TV Show <strong>Stargate</strong> hoping it will not bring any confusion ^^.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/pic-travel.png?raw=true" alt="SplashScreen" /></p>
<p>ℹ️ <strong>Frequently asked questions</strong></p>
<ul>
<li><em>Can I run the workshop on my computer?</em>
<blockquote>
<p>There is nothing preventing you from running the workshop on your own machine. If you do so, you will need <em>java jdk11+</em>, <em>Maven</em>, an IDE like <em>VSCode, IntelliJ, Eclipse, Spring STS</em>. You will have to adapt commands and paths based on your environment and install the dependencies by yourself. <strong>We won't provide support</strong> to keep on track with schedule.</p>
</blockquote>
</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://www.youtube.com/watch?v=mL9oDZPJfwk" target="_blank">Workshop video</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of contents</h2>
<ol>
<li><a href="#1-create-astra-db-instance" target="_blank">Create Astra DB Instance</a></li>
<li><a href="#2-create-table-and-insert-data" target="_blank">Create Tables and insert data</a></li>
<li><a href="#3-load-dataset-as-a-csv" target="_blank">Load dataSet as a CSV</a></li>
<li><a href="#4-create-astra-token" target="_blank">Create Astra Token</a></li>
<li><a href="#5-launch-gitpod" target="_blank">Launch Gitpod</a></li>
<li><a href="#6-know-your-gitpod" target="_blank">Know your Gitpod</a></li>
<li><a href="#7-setup-your-application" target="_blank">Setup your Application</a></li>
<li><a href="#8-run-some-unit-tests" target="_blank">Run Unit tests</a></li>
<li><a href="#9-run-the-application" target="_blank">Run the Application</a></li>
<li><a href="#10-using-stargate-rest-api" target="_blank">Using Stargate Rest API</a></li>
<li><a href="#11-using-stargate-document-api" target="_blank">Using Stargate Document API</a></li>
<li><a href="#12-walkthrough-sdk" target="_blank">Walkthrough Stargate SDK</a></li>
<li><a href="#13-homeworks" target="_blank">Homeworks</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-create-astra-db-instance"> </a>1. Create Astra DB Instance</h2>
<p><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 5M writes, 30M reads, 40GB storage monthly - sufficient to run small production workloads.</p>
<p>✅ <strong>Step 1a. If you do have an account yet register and sign In to Astra DB this is FREE and NO CREDIT CARD asked</strong> <a href="https://astra.dev/9-2" target="_blank">https://astra.datastax.com</a>: You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</p>
<p><em>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</em></p>
<p>✅ <strong>Step 1b. Create a &quot;pay as you go&quot; plan</strong></p>
<p>Follow this <a href="https://docs.datastax.com/en/astra/docs/creating-your-astra-database.html" target="_blank">guide</a>, to set up a pay as you go database with a free $25 monthly credit. You will find below recommended values to enter:</p>
<ul>
<li>
<p><strong>For the database name</strong> - <code>workshops</code></p>
</li>
<li>
<p><strong>For the keyspace name</strong> - <code>stargate</code></p>
</li>
</ul>
<p><em>You can technically use whatever you want and update the code to reflect the keyspace. This is really to get you on a happy path for the first run.</em></p>
<ul>
<li>
<p><strong>For provider and region</strong>: Choose a provider (GCP, Azure or AWS) and then the related region is where your database will reside physically (choose one close to you or your users).</p>
</li>
<li>
<p><strong>Create the database</strong>. Review all the fields to make sure they are as shown, and click the <code>Create Database</code> button.</p>
</li>
</ul>
<p>You will see your new database <code>pending</code> in the Dashboard.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/db-pending.png?raw=true" alt="my-pic" /></p>
<p>The status will change to <code>Active</code> when the database is ready, this will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<p><strong>👁️ Walkthrough</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/astra-create-db.gif?raw=true" alt="image" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="2-create-table-and-insert-data"> </a>2. Create Table and insert data</h2>
<p>Once the database is created we want to create the tables to insert Data.</p>
<p>✅ <strong>Step2a: Locate and open CQLConsole</strong></p>
<ul>
<li>
<p>Click the name of you database <code>workshops</code> in the panel on the left</p>
</li>
<li>
<p>Locate the tab <code>CQL Console</code>, the prompt will open, there is no need to enter credentials here.</p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/cqlshconsole.png?raw=true" alt="image" /></p>
<p>✅ <strong>Step 2b: Navigate to your keyspace</strong></p>
<blockquote>
<p>To ease the copy-paste you can use the small clipboard icons as show in the walkthrough. If the CTL+C and CTRL+V does not work in your browser you can also <em>right-click</em> and then select <em>paste</em>.</p>
</blockquote>
<ul>
<li>Enter the following statement in CQL console to list existing keyspaces, you should see the one you created with the database.</li>
</ul>
<pre lang="sql"><code>describe keyspaces;
</code></pre>
<ul>
<li>Enter the following statement in CQL console to select your keyspace:</li>
</ul>
<pre lang="sql"><code>use stargate;
</code></pre>
<p>✅ <strong>Step 2c: Create Entities</strong></p>
<ul>
<li>Enter the following statement in CQL console to Create a table <code>chevrons</code> with the following fields</li>
</ul>
<pre lang="sql"><code>CREATE TABLE IF NOT EXISTS stargate.chevrons(
   area text,
   code int ,
   name text,
   picture text,
   PRIMARY KEY ((area), code)
) WITH CLUSTERING ORDER BY (code ASC);
</code></pre>
<p>✅ <strong>Step 2d: Populate entries</strong></p>
<ul>
<li>Enter the following statement in CqlSH console to enter the different chevrons in the database</li>
</ul>
<pre lang="sql"><code>INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 1, 'Earth', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/001glyph-earth.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 2, 'Crater', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/002glyph-crater.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 3, 'Virgo', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/003glyph-virgo.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 4, 'Bootes', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/004glyph-bootes.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 5, 'Centaurus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/005glyph-centarus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 6, 'Libra', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/006glyph-libra.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 7, 'Serpenscaput', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/007glyph-serpenscaput.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 8, 'Norma', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/008glyph-norma.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 9, 'Scorpio', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/009glyph-scorpio.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 10, 'Cra', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/010glyph-cra.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 11, 'Scutum', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/011glyph-scutum.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 12, 'Sagitarus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/012glyph-sagittarius.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 13, 'Aquila', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/013glyph-aquila.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 14, 'Mic', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/014glyph-mic.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 15, 'Capricorn', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/015glyph-capricorn.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 16, 'Piscesaustrinus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/016glyph-piscesaustrinus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 17, 'Equuleus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/017glyph-equuleus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 18, 'Aquarius', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/018glyph-aquarius.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 19, 'Pegasus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/019glyph-pegasus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 20, 'Sculptor', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/020glyph-sculptor.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 21, 'Pisces', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/021glyph-pisces.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 22, 'Andromeda', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/022glyph-andromeda.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 23, 'Triangulum', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/023glyph-triangulum.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 24, 'Aries', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/024glyph-aries.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 25, 'Perseus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/025glyph-perseus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 26, 'Cetus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/026glyph-cetus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 27, 'Taurus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/027glyph-taurus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 28, 'Auriga', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/028glyph-auriga.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 29, 'Eridanus', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/029glyph-eridanus.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 30, 'Orion', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/030glyph-orion.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 31, 'Canisminor', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/031glyph-canisminor.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 32, 'Monoceros', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/032glyph-monoceros.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 33, 'Gemini', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/033glyph-gemini.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 34, 'Hydra', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/034glyph-hydra.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 35, 'Lynx', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/035glyph-lynx.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 36, 'Cancer', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/036glyph-cancer.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 37, 'Sextans', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/037glyph-sextans.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 38, 'Leominor', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/038glyph-leominor.jpg?raw=true');
INSERT INTO chevrons (area, code, name, picture) VALUES ('Milky Way', 39, 'Leo', 'https://github.com/datastaxdevs/workshop-spring-stargate/blob/main/images/glyphs/039glyph-leo.jpg?raw=true');
</code></pre>
<p>You can notice than those are real images, thanks to <a href="http://stargate-sg1-solutions.com/wiki/Main_Page" target="_blank">StargateWiki</a>.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/001glyph-earth.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/002glyph-crater.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/003glyph-virgo.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/004glyph-bootes.jpg?raw=true" alt="#" />...</p>
<p>✅ <strong>Step 2e: Show the results</strong></p>
<p>We have inserted 39 symbols of the <code>Milky Way</code> galaxy with <code>INSERT</code> statements but we could have used other solutions like <a href="https://github.com/datastax/dsbulk" target="_blank">dsbulk</a>, Spark, Apis or Astra Data Loader. We will show some of them to you later.</p>
<ul>
<li>Validate the number of chevrons</li>
</ul>
<pre lang="sql"><code>select count(*) from stargate.chevrons;
</code></pre>
<ul>
<li>Show the chevrons known for the <code>Milky Way</code> galaxy</li>
</ul>
<pre lang="sql"><code>select code,name from stargate.chevrons where area='Milky Way';
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-load-dataset-as-a-csv"> </a>3. Load dataSet as a CSV</h2>
<p>Inserting a couple of values with CQL console is great but quite verbose, correct? We created the table and inserted a few values.</p>
<p>In Astra DB there is a tool to speed up that process and both create and import data from a CSV, instead.</p>
<p>✅ <strong>Step 3a: Download the dataset</strong></p>
<p>To download the DATASET, <strong>right-click</strong> <em>(or CTRL + Click to open in new tab)</em> the button below and download the target file on your machine.</p>
<blockquote>
<p><em>If the file opens in the browser save it with the name <code>destinations.csv</code>. The name is important as the filename will be the table name.</em></p>
</blockquote>
<p align="left">
<a href="https://raw.githubusercontent.com/datastaxdevs/workshop-spring-stargate/main/dataset/destinations.csv" target="_blank">
 <img src="https://dabuttonfactory.com/button.png?t=Download Dataset&f=Roboto-Bold&ts=26&tc=fff&hp=45&vp=20&c=11&bgt=unicolored&bgc=15d798" />
</a>
</p>
<p>✅ <strong>Step 3b: Open Astra Data Loader</strong></p>
<p>Locate the <code>Upload Data</code> button to open the Data Loader.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-01-button.png" alt="#" /></p>
<p>✅ <strong>Step 3c: Upload the dataset</strong></p>
<p>Click on the area <em>Drag n drop a single file</em> and look for the file <code>destinations.csv</code> on your machine, this file has been downloaded in step <strong>3a</strong>.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-02-upload.png" alt="#" /></p>
<p>Once the file has been uploaded notice the <code>Upload Successful</code> message in green. You can now click <code>NEXT</code></p>
<p>✅ <strong>Step 3d: Define the target table</strong></p>
<ul>
<li>Locate the field Table Name and make sure it is set to <code>destinations</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-03-parsed.png" alt="#" /></p>
<p>Scroll down to show the the <strong>Keys and Clustering</strong> part of the screen and enter the following</p>
<ul>
<li>
<p>use the dropdown <code>galaxy</code> which will be our partition key (assuming there are less than 100,000 stargates in our galaxy) and a lot of galaxy ^^.</p>
</li>
<li>
<p><code>name</code> will be our clustering key in order to ensure a unique name of the planet in the galaxy.</p>
</li>
<li>
<p>You can now click <code>NEXT</code></p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-04-datamodel.png" alt="#" /></p>
<p>✅ <strong>Step 3e: Define the target keyspace</strong></p>
<ul>
<li>
<p>In the <strong>Target Keyspace</strong> combo box find and select our keyspace <code>stargate</code></p>
</li>
<li>
<p>Then click <code>NEXT</code></p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-05-keyspace.png" alt="#" /></p>
<p>✅ <strong>Step 3f: Show Data</strong></p>
<p>After a few seconds (about 30s),you will get an email informing you that the batch has been scheduled.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-06-mail1.png" alt="#" /></p>
<p>As you can see the operation here is asynchronous. About a minute later your will get another email to tell you the data has been inserted.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-07-mail2.png" alt="#" /></p>
<p>Using the CQL Console enter the CQL command that was suggested in the email as below.</p>
<pre lang="sql"><code>SELECT * FROM stargate.destinations LIMIT 10;
</code></pre>
<p><strong>👁️ Expected output</strong><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/dataloader-08-data.png" alt="#" /></p>
<p>❓ <strong>QUIZ:</strong> Try to find by the correct CQL statement to retrieve the coordinates of planet Chulak in our galaxy.</p>
<details><summary><b>Click to view Solution</b></summary>
<p>
<pre lang="sql"><code>SELECT chevron1,chevron2,chevron3,chevron4,chevron5,chevron6 FROM stargate.destinations WHERE galaxy='Milky Way' and name='Chulak';
</code></pre>
</p>
</details>
<p>Yes now we do have the cartouche (a carved tablet or drawing representing a scroll with rolled-up ends) - <code>9,2,23,16,37,20</code> (<a href="http://stargate-sg1-solutions.com/wiki/Chulak" target="_blank">You can check that we are correct</a>)</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/009glyph-scorpio.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/002glyph-crater.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/023glyph-triangulum.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/016glyph-piscesaustrinus.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/037glyph-sextans.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/020glyph-sculptor.jpg?raw=true" alt="#" /><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/glyphs/001glyph-earth.jpg?raw=true" alt="#" /></p>
<p>🎉🎉 <strong>Congratulations</strong> we do have both chevrons and coordinates of our destination.</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-create-astra-token"> </a>4. Create Astra Token</h2>
<p>However, to save <em>Teal'c</em> from <em>Apophysis</em> we still need to create a <strong>token</strong> that we will use as our credentials.</p>
<p>✅ <strong>Step 4a: Generate Token</strong></p>
<p>Following the <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">Manage Application Tokens docs</a> create a token with <code>Database Admnistrator</code> roles.</p>
<ul>
<li>
<p>Go the <code>Organization Settings</code></p>
</li>
<li>
<p>Go to <code>Token Management</code></p>
</li>
<li>
<p>Pick the role <code>Database Admnistrator</code> on the select box</p>
</li>
<li>
<p>Click Generate token</p>
</li>
</ul>
<p><strong>👁️ Walkthrough</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/astra-create-token.gif?raw=true" alt="image" /></p>
<p>This is what the token page looks like. You can now download the values as a CSV. We will need those values but you can also keep this window open for use later.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/astra-token.png?raw=true" alt="image" /></p>
<p>Notice the clipboard icon at the end of each value.</p>
<ul>
<li>
<p><code>clientId:</code> We will use it as a <em>username</em> to contact Cassandra</p>
</li>
<li>
<p><code>clientSecret:</code> We will use it as a <em>password</em> to contact Cassandra</p>
</li>
<li>
<p><code>appToken:</code> We will use it as a api token Key to interact with APIs.</p>
</li>
</ul>
<p>To know more about roles of each token you can have a look to <a href="https://www.youtube.com/watch?v=nRqu44W-bMU" target="_blank">this video.</a></p>
<p><strong>Note: Make sure you don't close the window accidentally or otherwise - if you close this window before you copy the values, the application token is lost forever. They won't be available later for security reasons.</strong></p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p>We are now set with the database and credentials. Let's start coding with Spring !</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-launch-gitpod"> </a>5. Launch Gitpod</h2>
<p><a href="https://www.gitpod.io/" target="_blank">Gitpod</a> is an IDE 100% online based on <a href="https://github.com/gitpod-io/vscode/blob/gp-code/LICENSE.txt?lang=en-US">VS Code</a>. To initialize your environment simply click on the button below <em>(CTRL + Click to open in new tab)</em> You will be asked for you github account, as needed.</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-spring-stargate" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p><strong>👁️ Expected output</strong></p>
<p><em>The screenshot may be slightly different based on your default skin and a few edits in the read me.</em></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-01-home.png?raw=true" alt="gitpod" /></p>
<p><strong>That's it.</strong> Gitpod provides all tools we will need today including <code>Maven</code> and exporting port <code>8080</code>. At initialization of the workspace we schedule a <code>mvn clean install</code> to download dependencies.</p>
<p>Also you may have noticed that a build is happening - even before we get started. The sample project already exists and loading the developer enviroment triggers a build to download all the maven dependencies so you don't have to.</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="6-know-your-gitpod"> </a>6. Know your gitpod</h2>
<p>✅ <strong>Step 6a: Know your public URL</strong></p>
<p>The workshop application has opened with an ephemeral URL. To know the URL where your application endpoint will be exposed you can run the following command in the terminal after the build has completed.</p>
<pre lang="bash"><code>gp url 8080
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-02-url.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 6b: Build the project</strong></p>
<ul>
<li>Using maven build the project and download its dependencies.</li>
</ul>
<pre lang="bash"><code>cd /workspace/workshop-spring-stargate/stargate-demo &amp;&amp; mvn clean package install -Dmaven.test.skip=true
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-04-build.png?raw=true" alt="gitpod" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="7-setup-your-application"> </a>7. Setup your application</h2>
<p>To run the application you need to provide the credentials and identifier to the application. you will have to provide 6 values in total as shown below</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-05-appyml.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 7a: Enter 3 values from the token</strong></p>
<ul>
<li>
<p>Open the file <code>stargate-demo/src/main/resources/application.yml</code> as show below.</p>
</li>
<li>
<p>Replace <code>client-id</code>, <code>clientSecret</code>, <code>application-token</code> with values shown on the Astra token screen or picking the values from the CSV token file your dowloaded before including the AstraCS: part of the token.</p>
</li>
</ul>
<blockquote>
<p>To ease the copy-paste you can use the small clipboard icons as show in the walkthrough.</p>
</blockquote>
<p>✅ <strong>Step 7b: Enter 3 values related to your DB</strong></p>
<ul>
<li>
<p>In Astra DB go back to home page by clicking the logo</p>
</li>
<li>
<p>Select you database <code>workshops</code> in the left panel and then copy values for <code>cloud-region</code> and <code>database-id</code> (clusterID) from the details page.</p>
</li>
</ul>
<p><strong>👁️ Walkthrough</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/copy-credentials.gif?raw=true" alt="gitpod" /></p>
<p>TADA your application is now configured we can finally play with some code.</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="8-run-some-unit-tests"> </a>8. Run some unit tests</h2>
<p>The application is now set you should be able to interact with your DB. Let's demonstrate some capabilities.</p>
<p>✅ <strong>Step 8a: Use CqlSession</strong></p>
<p>Interaction with Cassandra are implemented in Java through drivers and the main Class is <code>CqlSession</code>.</p>
<p>Higher level frameworks like Spring, Spring Data, or even quarkus will rely on this object so let's make sure it is part of your Spring context with a <code>@SpringBootTest</code>.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.demo.stargate.Ex1_UseCqlSessionTest
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre lang="bash"><code>[..]
+ Code=38, name='Leominor',
+ Code=39, name='Leo',
[OK] - Test Successfully you ROCK !
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 8.42 s - in com.datastax.demo.stargate.Ex1_UseCqlSessionTest
18:23:34.167 INFO  com.datastax.stargate.sdk.StargateClient      : Closing CqlSession.
[INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
-----------------------------------------------------------------------[INFO] BUILD SUCCESS
-----------------------------------------------------------------------[INFO] Total time:  13.985 s
[INFO] Finished at: 2021-04-27T18:23:34+02:00
------------------------------------------------------------------------
</code></pre>
<p>✅ <strong>Step 8b: Working With Spring Data</strong></p>
<p>Spring Data allows Mapping <code>Object &lt;=&gt; Table</code> based on annotation at the java bean level. Then by convention CQL query will be executed under the hood.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.demo.stargate.Ex2_UseSpringDataChevronTest
</code></pre>
<p>This test perform 3 operations:</p>
<ul>
<li>Find all Chevrons in the table</li>
<li>Find a chevron by its primary key</li>
<li>Find all chevrons in our galaxy (partition key)</li>
</ul>
<p><strong>👁️ Expected output</strong></p>
<pre lang="bash"><code>[...]
 [OK]  - Test #2.1 Successful - you ROCK !
[...]
[OK]  - Test #2.2 Successful - you ROCK !
[...]
[OK]  - Test #2.3 Successful - you ROCK !
</code></pre>
<p>We can also query the destination table to find coordinates:</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.demo.stargate.Ex3_UseSpringDataDestinationTest
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="9-run-the-application"> </a>9. Run the application</h2>
<p>✅ <strong>Step 9a: Start the application</strong></p>
<p>Navigate to the folder and simply start the application with the following command.</p>
<pre lang="bash"><code>cd /workspace/workshop-spring-stargate/stargate-demo
mvn spring-boot:run
</code></pre>
<p>Your application is now started you should have a peek at the logs here</p>
<pre lang="bash"><code>Picked up JAVA_TOOL_OPTIONS: -Xmx1879m
  _________ __                             __
  /   _____//  |______ _______  _________ _/  |_  ____
  \_____  \\   __\__  \\_  __ \/ ___\__  \\   __\/ __ \
  /        \|  |  / __ \|  | \/ /_/  &gt; __ \|  | \  ___/
 /_______  /|__| (____  /__|  \___  (____  /__|  \___  &gt;
        \/           \/     /_____/     \/          \/
 ________
 \______ \   ____   _____   ____
  |    |  \_/ __ \ /     \ /  _ \
  |    `   \  ___/|  Y Y  (  &lt;_&gt; )
 /_______  /\___  &gt;__|_|  /\____/
         \/     \/      \/

 DataStax Developer Advocate team

Starting StargateDemoApplication using Java 11.0.10 on
No active profile set, falling back to default profiles: default
+ Load Environment Variables
+ Load Builder parameters
+ HttpClient Initialized
+ API(s) Devops is [ENABLED]
+ Load Secure Connect: /home/gitpod/.astra/secure_connect_bundle_58a2e502-fccf-4524-ac22-e59277e63edc.zip
+ CQL Credentials: ${clientId}${/clientSecret}
+ API(s) Document is [ENABLED] https://58a2e502-fccf-4524-ac22-e59277e63edc-us-east-1.apps.astra.datastax.com/api/rest
+ API(s) REST Data is [ENABLED] https://58a2e502-fccf-4524-ac22-e59277e63edc-us-east-1.apps.astra.datastax.com/api/rest
+ API(s) GraphQL [ENABLED] https://58a2e502-fccf-4524-ac22-e59277e63edc-us-east-1.apps.astra.datastax.com/api/graphql
+ API(s) Cql is [ENABLED]
+ Keyspace stargate
[StargateClient] has been initialized
[AstraClient] has been initialized.
[THYMELEAF][restartedMain] Template Mode 'XHTML' is deprecated. Using Template Mode 'HTML' instead.
Started StargateDemoApplication in 7.883 seconds (JVM running for 8.497)
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-06-start.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 9b: Open a new terminal in gitpod</strong></p>
<p>The application is running on our first terminal. To enter new commands please create a new terminal in gitpod.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/new-terminal.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 9c: Open the application</strong></p>
<p>Are you ready? Now is the time to play the demo.</p>
<p>It is better to use a dedicated TAB in the browser to open the application in full screen. Use this command to show the URL.</p>
<pre lang="bash"><code>gp url 8080
</code></pre>
<p>If you have the link in the terminal gitpod, it's a lot easier to create a new tab by clicking <code>Follow link</code>.</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/follow-link.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 9d: Play the demo</strong></p>
<ul>
<li>Click the Stargate logo, the music starts if it did not start automatically</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/demo-home.png?raw=true" alt="SplashScreen" /></p>
<ul>
<li>
<p>Click on the planet name you want to reach here <code>CHULAK</code> the coordinates are not entered in the Stargate.</p>
</li>
<li>
<p>Click on one orange <code>chrevron</code> in the order to make the wheel start spinning. Click the chevrons one after the other to simulate the dialing. As soon as all chevrons are engaged the vortex will open.</p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/demo-home-2.png?raw=true" alt="SplashScreen" /></p>
<p>Activate the rest of the chevrons to open the stargate...Buckle up !</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/demo-home-3.png?raw=true" alt="SplashScreen" /></p>
<p>Congratulations you Played the demo !</p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/demo.gif?raw=true" alt="demo" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="10-using-stargate-rest-api"> </a>10. Using Stargate Rest API</h2>
<p>The gateway <a href="stargate.io" target="_blank">Stargate</a> allows you to execute the operations through a REST API. Let's list the chevrons.</p>
<p>✅ <strong>Step 10a: Open swagger</strong></p>
<p>In a terminal that is not running the demo enter the command in order to open the swagger UI from Astra (URL has been built based on the values you entered in <code>application.yaml</code>)</p>
<pre lang="bash"><code>/workspace/workshop-spring-stargate/open-swagger.sh
</code></pre>
<p><strong>👁️ Script output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/open-swagger.png?raw=true" alt="SplashScreen" /></p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/gitpod-07-swagger.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>Step 10b: List Chevrons</strong></p>
<ul>
<li>In the Swagger UI page locate the blue line <code>/v1/keyspaces/{keyspaceName}/tables/{tableName}/rows</code> in the block <code>DATA</code></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/restapi-retrieve-rows.png?raw=true" alt="gitpod" /></p>
<ul>
<li>
<p>Click the button <code>Try it Out</code> on the top right hand corner.</p>
</li>
<li>
<p>Enter the following values</p>
</li>
</ul>
<table>
<thead>
<tr>
<th>FIELD</th>
<th>VALUE</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>X-Cassandra-Token</strong></td>
<td><code>AstraCS....</code> (<em>your token</em>)</td>
</tr>
<tr>
<td><strong>keyspaceName</strong></td>
<td><code>stargate</code></td>
</tr>
<tr>
<td><strong>tableName</strong></td>
<td><code>chevrons</code></td>
</tr>
<tr>
<td><strong>pageSize</strong></td>
<td><em>let it blank</em></td>
</tr>
<tr>
<td><strong>pageState</strong></td>
<td><em>let it blank</em></td>
</tr>
</tbody>
</table>
<ul>
<li>Click the button <code>Execute</code></li>
</ul>
<p><strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/restapi-retrieve-rows-2.png?raw=true" alt="gitpod" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="11-using-stargate-document-api"> </a>11. Using Stargate Document API</h2>
<p>The REST API covers the same features as the CQL interface and you need to know your schema.</p>
<p>Stargate also provide a way to insert <strong>schemaless</strong> JSON Document as you would do with a document oriented datbase, you are welcomed.</p>
<p>✅ <strong>Step 11a: Create a document</strong></p>
<ul>
<li>
<p>Locate <code> ​/v2​/namespaces​/{namespace-id}​/collections​/{collection-id} Create a new document</code> in the block <code>DOCUMENT</code></p>
</li>
<li>
<p>Click the button <code>Try it Out</code> on the top right hand corner.</p>
</li>
<li>
<p>Enter the following values</p>
</li>
</ul>
<table>
<thead>
<tr>
<th>FIELD</th>
<th>VALUE</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>X-Cassandra-Token</strong></td>
<td><code>AstraCS....</code> (<em>your token</em>)</td>
</tr>
<tr>
<td><strong>namespace-id</strong></td>
<td><code>stargate</code></td>
</tr>
<tr>
<td><strong>collection-id</strong></td>
<td><code>sampledoc</code></td>
</tr>
<tr>
<td><strong>pageSize</strong></td>
<td><em>let it blank</em></td>
</tr>
<tr>
<td><strong>body</strong></td>
<td></td>
</tr>
</tbody>
</table>
<pre lang="json"><code>{
  &quot;videoid&quot;: &quot;e466f561-4ea4-4eb7-8dcc-126e0fbfd573&quot;,
  &quot;email&quot;: &quot;clunven@sample.com&quot;,
  &quot;title&quot;: &quot;A video&quot;,
  &quot;upload&quot;: &quot;2020-02-26 15:09:22 +00:00&quot;,
  &quot;url&quot;: &quot;http://google.fr&quot;,
  &quot;frames&quot;: [1, 2, 3, 4],
  &quot;tags&quot;: [&quot;cassandra&quot;, &quot;accelerate&quot;, &quot;2020&quot;],
  &quot;formats&quot;: {
    &quot;mp4&quot;: { &quot;width&quot;: 1, &quot;height&quot;: 1 },
    &quot;ogg&quot;: { &quot;width&quot;: 1, &quot;height&quot;: 1 }
  }
}
</code></pre>
<p><strong>Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/docapi-createdoc.png?raw=true" alt="gitpod" /></p>
<ul>
<li>Click the button <code>Execute</code></li>
</ul>
<p>The api will create a new table for the collection and insert the JSON document. A new unique identifier is generated and returned as <code>documentId</code>.</p>
<p><strong>Expected output</strong><br />
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/docapi-createdoc-2.png?raw=true" alt="gitpod" /></p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="12-walkthrough-sdk"> </a>12. Walkthrough SDK</h2>
<p>Well you had an overview about the APIs exposed by Stargate. There is also a <a href="https://docs.datastax.com/en/astra/docs/using-the-astra-graphql-api.html" target="_blank">GraphQL API if you want to know more</a>.</p>
<p>A SDK or <em>Software Developement Kit</em> is used here to ease the usage of each API. It is also the one creating a bean <code>CqlSession</code> that will be used with Spring Data Cassandra as is.</p>
<p>The Astra SDK has been installed with a single starter dependency. More information is <a href="https://github.com/datastax/astra-sdk-java/wiki" target="_blank">here</a></p>
<pre lang="xml"><code>&lt;dependency&gt;
  &lt;groupId&gt;com.datastax.astra&lt;/groupId&gt;
  &lt;artifactId&gt;astra-spring-boot-starter&lt;/artifactId&gt;
  &lt;version&gt;0.1.14&lt;/version&gt;
&lt;/dependency&gt;
</code></pre>
<p>✅ <strong>Step 12a: Using devops API with SDK</strong></p>
<p>In a gitpod terminal use Maven to execute a unit test illustrating the usage of the <code>Devops API</code> from the SDK.</p>
<pre lang="bash"><code>cd /workspace/workshop-spring-stargate/stargate-demo
mvn test -Dtest=com.datastax.demo.stargate.Ex4_SdkDevopsApi
</code></pre>
<p><strong>Expected Output</strong></p>
<pre lang="bash"><code>13:48:16.753 INFO  com.datastax.demo.stargate.Ex4_SdkDevopsApi   : Started Ex4_SdkDevopsApi in 6.184 seconds (JVM running for 7.136)
Database 'workshops'
+ id=3c7fc647-c03b-4a0c-aa6b-a00dd677ac53
+ region=eu-central-1
+ keyspace=stargate
</code></pre>
<p>✅ <strong>Step 12b: Using REST API with SDK</strong></p>
<p>In a gitpod terminal use Maven to execute a unit test illustrating the usage of the <code>REST API</code> from the SDK.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.demo.stargate.Ex5_SdkRestApi
</code></pre>
<p><strong>Expected Output</strong></p>
<pre lang="bash"><code>13:47:38.123 INFO  com.datastax.demo.stargate.Ex5_SdkRestApi     : Started Ex5_SdkRestApi in 6.375 seconds (JVM running for 7.375)
Earth
Crater
Virgo
Bootes
Centaurus
Libra
Serpenscaput
Norma
Scorpio
Cra
Scutum
Sagitarus
Aquila
Mic
Capricorn
Piscesaustrinus
Equuleus
Aquarius
Pegasus
Sculptor
13:47:41.173 INFO  com.datastax.stargate.sdk.StargateClient      : Closing CqlSession.
</code></pre>
<p>✅ <strong>Step 12c: Using DOC API with SDK</strong></p>
<p>In a gitpod terminal use Maven to execute a unit test illustrating the usage of the <code>DOC API</code> from the SDK.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.demo.stargate.Ex6_SdkDocApi
</code></pre>
<p><strong>Expected Output</strong></p>
<pre lang="bash"><code>13:46:43.360 INFO  com.datastax.demo.stargate.Ex6_SdkDocApi      : Started Ex6_SdkDocApi in 5.935 seconds (JVM running for 6.887)
Document:
+ id=063d3fe9-8ec0-4b9b-887a-90da52ee0f51
+ email= clunven@sample.com
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="13-homeworks"> </a>13. Homeworks</h2>
<img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/main/images/tutorials/badge.png?raw=true" width="200" align="right" />
<p>Don't forget to complete your upgrade and get your verified skill badge! Finish and submit your homework!</p>
<ol>
<li>Complete the practice steps from this repository as described above. Make screenshots alongside the steps</li>
<li>Learn more about spring in the <a href="https://www.datastax.com/dev/spring" target="_blank">course</a> and complete scenario <code>Build a Spring Boot REST Service</code> at the bottom of the page and make a screenshot of the &quot;congratulations&quot; page.</li>
<li>Submit your homework <a href="https://github.com/datastaxdevs/workshop-spring-stargate/issues/new?assignees=HadesArchitect&amp;labels=homework%2Cpending&amp;template=homework-assignment.md&amp;title=%5BHW%5D+%3CNAME%3E" target="_blank">here</a></li>
</ol>
<p>That's it, you are done! Expect an email next week!</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="14-the-end"> </a>14. The END</h2>
<p>Congratulations, your made it to the END of the show.</p>
<p><strong>💚 Share the love</strong></p>
<p><a href="https://www.facebook.com/sharer/sharer.php?u=https://github.com/datastaxdevs/workshop-spring-stargate" target="_blank"><img src="images/tutorials/share-facebook.png"/></a></p>
<p><a href="https://twitter.com/intent/tweet?url=https://github.com/datastaxdevs/workshop-spring-stargate&text=I attended a wonderful workshop today , thank you @Datastax, @clunven, @sonicdmg" target="_blank"><img src="images/tutorials//share-twitter.png"/></a></p>
<p><a href="https://www.linkedin.com/shareArticle?mini=true&url=https://github.com/datastaxdevs/workshop-spring-stargate&title=&summary=I attended a wonderful workshop today , thank you @Datastax, @clunven, @sonicdmg&source=" target="_blank"><img src="images/tutorials/share-linkedin.png"/></a></p>
<p><strong>🧑🏻‍🤝‍🧑🏽 Let's get in touch</strong></p>
<table>
<thead>
<tr>
<th><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/david.png" alt="B" /></th>
<th><img src="https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/cedrick.png" alt="B" /></th>
</tr>
</thead>
<tbody>
<tr>
<td>David Gilardi <br><a href="https://github.com/SonicDMG" target="_blank">@SonicDMG</a></td>
<td>Cedrick Lunven<br><a href="https://github.com/clun" target="_blank">@clun</a></td>
</tr>
</tbody>
</table>
<hr />
<p><a href=""><img src=" target="_blank"https://github.com/datastaxdevs/workshop-spring-stargate/raw/master/images/tutorials/thankyou.gif" alt="thankyou" /></a></p>
