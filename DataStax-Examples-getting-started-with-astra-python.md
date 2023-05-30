<!--- STARTEXCLUDE --->
<h1><a class="anchor" aria-hidden="true" id="getting-started-with-apache-cassandratm-and-python-using-datastax-astra-db"> </a>Getting Started with Apache Cassandra™ and Python using DataStax Astra DB</h1>
<p><em>50 minutes, Intermediate, <a href="https://github.com/DataStax-Examples/getting-started-with-astra-python#prerequisites" target="_blank">Start Building</a></em></p>
<p>This sample Python backend provides a REST API service that is used with the <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">Getting Started with Astra UI</a> to show a<br />
simple example of how to connect to and query DataStax Astra DBs.</p>
<!--- ENDEXCLUDE --->
<p><img src="https://raw.githubusercontent.com/DataStax-Examples/sample-app-template/master/screenshots/astra-sample-app-default.png" alt="image" /></p>
<h2><a class="anchor" aria-hidden="true" id="astra-db-quick-start"> </a>Astra DB Quick Start</h2>
<!--- STARTEXCLUDE --->
<ul>
<li><a href="https://dtsx.io/38B5JGj" target="_blank">Signup for DataStax Astra</a>, or login to your already existing account.</li>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-astra-db" target="_blank">Create an Astra DB Database</a> if you don't already have one.</li>
</ul>
<!--- ENDEXCLUDE --->
<ul>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-astra-db-keyspace" target="_blank">Create an Astra DB Keyspace</a> called <code>sag_netflix</code> in your database.</li>
<li><a href="https://github.com/DataStax-Examples/sample-app-template/blob/master/GETTING_STARTED.md#create-an-application-token" target="_blank">Generate an Application Token</a> with the role of <code>Database Administrator</code> for the Organization that your Astra DB is in.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="running-on-your-local-machine"> </a>Running on your local machine</h2>
<p>If you are familiar with Python, then you've likely gotten your hands on Python virtual environments.<br />
We'll be leveraging pyenv while setting up this backend, which will serve our<br />
Spacecraft frontend that will have you flying through the stars.</p>
<p>If you aren't familiar with Python, hop over to our <a href="https://helpdocs.datastax.com/aws/dscloud/astra/dscloudPythonDriver.html#Installingpyenv,Python,andvirtualenv" target="_blank">official documentation</a><br />
for setting that up on your machine, and come back here after you have it installed ( specifically after Step 5 of the Procedure ).</p>
<p>Now that we have that out of the way, we'll use pyenv to install Python 3.6.9</p>
<pre lang="sh"><code>pyenv install 3.6.9
</code></pre>
<p>Next create a new virtualenv using that Python version we just installed.</p>
<pre lang="sh"><code>pyenv virtualenv 3.6.9 astra-venv
</code></pre>
<p>Almost off to the races, go ahead and activate that virtualenv</p>
<pre lang="sh"><code>pyenv activate astra-venv
</code></pre>
<p>Woot, now 3 quick dependencies ( Flask, Flask CORS,  and the DataStax Cassandra Driver )</p>
<pre lang="sh"><code>pip install Flask flask-cors cassandra-driver
</code></pre>
<p>Last one, clone this repo</p>
<pre lang="sh"><code>git clone https://github.com/DataStax-Examples
/getting-started-with-astra-python.git
</code></pre>
<p>If everything above went smoothly, fingers crossed, then we are ready to rock.<br />
Go to the directory that you just cloned this repo into</p>
<pre lang="sh"><code>cd getting-started-with-astra-python
</code></pre>
<p>Fire up the engines</p>
<pre lang="sh"><code>FLASK_ENV=development FLASK_APP=getting_started_with_astra.py flask run
</code></pre>
<p>You should be met with the following output, note that it's running on <code>localhost</code> and port <code>5000</code></p>
<pre lang="sh"><code> * Serving Flask app &quot;getting_started_with_astra.py&quot; (lazy loading)
 * Environment: development
 * Debug mode: on
 * Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
 * Restarting with stat
 * Debugger is active!
 * Debugger PIN: 204-527-831
</code></pre>
<p>Once the backend is running, you can start the <a href="https://github.com/DataStax-Examples/getting-started-with-astra-ui" target="_blank">Getting Started with Astra UI</a> in order to use a web page that leverages this backend.</p>
