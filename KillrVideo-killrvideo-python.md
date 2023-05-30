<h1><a class="anchor" aria-hidden="true" id="killrvideo-python"> </a>killrvideo-python</h1>
<p>Python implementation of KillrVideo service layer. Requires Python 3.</p>
<p>Install:</p>
<ul>
<li>Clone this repo
<ul>
<li><code>git clone &lt;&gt;</code></li>
<li><code>cd killrvideo-python</code></li>
</ul>
</li>
</ul>
<p>Dependencies:</p>
<ul>
<li>To run the Python services, we recommend using <code>venv</code> to create a Python virtual environment, which leverages the contents<br />
of <code>requirements.txt</code> to install the required Python libraries
<ul>
<li><code>python3 -m venv venv</code></li>
<li><code>source venv/bin/activate</code></li>
</ul>
</li>
<li>Alternatively, you can build the dependencies locally by emulating the <code>pip install</code> commands in <code>Dockerfile</code>.</li>
</ul>
<p>Running Python services in Docker:</p>
<ul>
<li>Run the script to build the Docker container:
<ul>
<li><code>scripts/docker-build.sh</code></li>
</ul>
</li>
<li>Run the services and supporting infrastructure in Docker
<ul>
<li><code>docker-compose up -d</code></li>
</ul>
</li>
</ul>
<p>(Alternate) Running the Python Services on the host (not in docker):</p>
<ul>
<li>Run supporting infrastructure using Docker
<ul>
<li><code>scripts/run-docker-backend-exernal.sh</code></li>
<li>Note this script makes use of the custom compose file <code>scripts/docker-compose-backend-external.yaml</code>, which references the environment variable <code>KILLRVIDEO_BACKEND</code>. The script sets this to the host IP.</li>
</ul>
</li>
<li>Run the Python services
<ul>
<li>In your IDE or shell, set the environment variables <code>KILLRVIDEO_DSE_CONTACT_POINTS</code> and <code>KILLRVIDEO_KAFKA_BOOTSTRAP_SERVERS</code> to point to localhost (<code>127.0.0.1</code>)</li>
<li><code>python killrvideo/__init__.py</code></li>
<li>To stop the docker services, run <code>scripts/stop-docker-backend-external.sh</code></li>
</ul>
</li>
</ul>
<p>For more advanced Docker configuration options including metrics, volume storage and OpsCenter, see the <a href="https://github.com/KillrVideo/killrvideo-docker-common" target="_blank">killrvideo-docker-common</a> repository.</p>
