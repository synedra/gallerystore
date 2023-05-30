<h1><a class="anchor" aria-hidden="true" id="benchmark-your-astra-db-with-nosqlbench"> </a>Benchmark your Astra DB with NoSQLBench</h1>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-nosqlbench" target="_blank"><img src="https://img.shields.io/badge/Gitpod-hands--on-blue?logo=gitpod" alt="Gitpod hands-on" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/master/images/nosqlbench_banner.png?raw=true" />
<p>Time: <em>2 hours</em>. Difficulty: <em>Intermediate</em>. <a href="#create-your-astra-db-instance" target="_blank">Start Building!</a></p>
<p>The goal of this workshop is to get you familiar with the powerful and versatile<br />
tool <strong><a href="https://docs.nosqlbench.io/" target="_blank"><code>NoSQLBench</code></a></strong>. With that, you can perform<br />
<strong>industry-grade, robust benchmarks<br />
aimed at several (distributed) target systems, especially NoSQL databases</strong>.</p>
<p>Today you'll be benchmarking Astra DB, a database-as-a-service built on top of<br />
Apache Cassandra. Along the way, you will learn the basics of NoSQLBench.</p>
<p>In this repository you will find all material and references you need:</p>
<ul>
<li><a href="https://discord.gg/dBHRakusMN" target="_blank">NoSQLBench Discord</a></li>
<li><a href="https://docs.nosqlbench.io/" target="_blank">NoSQLBench homepage</a></li>
<li><a href="#create-your-astra-db-instance" target="_blank">Exercises</a></li>
<li><a href="#before-you-start" target="_blank">Step-by-step guide</a></li>
<li><a href="https://dtsx.io/discord" target="_blank">DataStaxDevs Discord server</a> to keep in touch with us</li>
<li><a href="https://community.datastax.com/" target="_blank">Our Q&amp;A forum</a> (think StackOverflow for Cassandra and all things DataStax)</li>
<li><a href="slides/datastaxdevs-workshop-benchmarking-nosqlbench.pdf" target="_blank">Slide deck</a></li>
</ul>
<!-- - [Workshop video](#) -->
<h4><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>Table of Contents</h4>
<ol>
<li><a href="#before-you-start" target="_blank">Before you start</a></li>
<li><a href="#create-your-astra-db-instance" target="_blank">Create your Astra DB instance</a></li>
<li><a href="#launch-gitpod-and-setup-nosqlbench" target="_blank">Launch Gitpod and setup NoSQLBench</a></li>
<li><a href="#run-benchmarks" target="_blank">Run benchmarks</a></li>
<li><a href="#workloads" target="_blank">Workloads</a></li>
<li><a href="#homework-assignment" target="_blank">Homework assignment</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="before-you-start"> </a>Before you start</h2>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/master/images/attention.png?raw=true" width="80" align="left" />
<blockquote>
<p><strong>Heads up</strong>: these instructions are available in two forms:<br />
a short and to-the-point one (<em>this one</em>),<br />
with just the useful commands if you are watching us live; and<br />
a <a href="extended_README.md" target="_blank">longer one</a>,<br />
with lots of explanations and details, designed for those who follow this workshop<br />
at their own pace. Please choose what best suits you!</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="faq"> </a>FAQ</h3>
<ul>
<li>What are the prerequisites?</li>
</ul>
<blockquote>
<p>This workshop is aimed at data architects, solution architects, developers, or anybody who<br />
wants to get serious about measuring the performance of their data-intensive system.<br />
You should know what a (distributed) database is, and have a general understanding of the<br />
challenges of communicating over a network.</p>
</blockquote>
<ul>
<li>Do I need to install a database or anything on my machine?</li>
</ul>
<blockquote>
<p>No, no need to install anything. You will do everything in the browser.<br />
(That being said, the knowledge you gain today will probably be best put to<br />
use once you install NoSQLBench on some client machine to run tests.)</p>
</blockquote>
<blockquote>
<p>You can also choose to work on your machine instead of using Gitpod: there's<br />
no problem with that, just a few setup and operational changes to keep<br />
in mind. We will not provide live support in this case, though,<br />
assuming you know what you are doing.</p>
</blockquote>
<ul>
<li>Is there anything to pay?</li>
</ul>
<blockquote>
<p><strong>No.</strong> All materials, services and software used in this workshop is <em>free</em>.</p>
</blockquote>
<ul>
<li>Do you cover NoSQLBench 4 or 5?</li>
</ul>
<blockquote>
<p>Ah, I see you are a connoisseur. We focus on the newly-release <strong>NoSQLBench 5</strong>,<br />
but we provide tips and remarks aimed at those still using nb4.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h3>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/master/images/nosqlbench_badge_artwork.png?raw=true" width="200" align="right" />
<p>To complete the workshop and get a verified &quot;NoSQLBench&quot; badge,<br />
follow these instructions:</p>
<ol>
<li>Do the hands-on practice, either during the workshop or by following the instructions in this README;</li>
<li>(optional) Complete the &quot;Lab&quot; assignment as detailed <a href="homework/homework.md" target="_blank">here</a>;</li>
<li>Fill the submission form <a href="https://dtsx.io/homework-nosqlbench" target="_blank">here</a>. Answer the theory questions and (optionally) provide a <em>screenshot</em> of the completed &quot;Lab&quot; part;</li>
<li>give us a few days to process your submission: you should receive your well-earned badge in your email inbox!</li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="create-your-astra-db-instance"> </a>Create your Astra DB instance</h2>
<p>First you must create a database: an instance of Astra DB, which<br />
you will then benchmark with NoSQLBench.</p>
<blockquote>
<p>Don't worry, you will create<br />
it within the &quot;Free Tier&quot;, which offers quite a generous free<br />
allowance in terms of monthly I/O (about 40M operations per month)<br />
and storage (80 GB).</p>
</blockquote>
<p><a href="https://astra.datastax.com" target="_blank"><img src="images/create_astra_db.png?raw=true" /></a></p>
<p>You need to:</p>
<ul>
<li>create an Astra DB instance <a href="https://awesome-astra.github.io/docs/pages/astra/create-instance/#c-procedure" target="_blank">as explained here</a>, with <strong>database name</strong> = <code>workshops</code> and <strong>keyspace name</strong> = <code>nbkeyspace</code>;</li>
<li><em>(this will happen automatically with the previous one)</em> generate and retrieve a DB Token <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#c-procedure" target="_blank">as explained here</a>. <strong>Important</strong>: use the role <em>&quot;DB Administrator&quot;</em> if manually creating the token.</li>
<li>generate and download a Secure Connect Bundle <a href="https://awesome-astra.github.io/docs/pages/astra/download-scb/#c-procedure" target="_blank">as explained here</a>;</li>
</ul>
<p>Moreover, keep the Astra DB dashboard open: it will be useful later. In particular, locate the<br />
Health tab and the CQL Console.</p>
<h2><a class="anchor" aria-hidden="true" id="launch-gitpod-and-setup-nosqlbench"> </a>Launch Gitpod and setup NoSQLBench</h2>
<p><strong>Ctrl-click on the Gitpod button below</strong> to spawn your very own environment + IDE:</p>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-nosqlbench" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<p>In a few minutes, a full IDE will be ready in your browser, with a file<br />
explorer on the left, a file editor on the top, and a console (<code>bash</code>) below it.</p>
<h3><a class="anchor" aria-hidden="true" id="install-nosqlbench"> </a>Install NoSQLBench</h3>
<p>To download NoSQLBench, type or paste this command in your Gitpod console:</p>
<pre lang="bash"><code>curl -L -O https://github.com/nosqlbench/nosqlbench/releases/latest/download/nb5
</code></pre>
<p>then make it executable and move it to a better place:</p>
<pre lang="bash"><code>chmod +x nb5
sudo mv nb5 /usr/local/bin/
</code></pre>
<p>Ok, now check that the program starts: invoking</p>
<pre lang="bash"><code>nb5 --version
</code></pre>
<p>should output the program version (something like <code>5.17.3</code> or higher).</p>
<h4><a class="anchor" aria-hidden="true" id="version-used"> </a>Version used</h4>
<p>This workshop is built for the newly-released NoSQLBench 5.</p>
<h3><a class="anchor" aria-hidden="true" id="upload-the-secure-connect-bundle-to-gitpod"> </a>Upload the Secure Connect Bundle to Gitpod</h3>
<p>Locate, with the file explorer on your computer, the bundle file that<br />
you downloaded earlier (it should be called<br />
<code>secure-connect-workshops.zip</code>)<br />
and simply <strong>drag-and-drop</strong> it to the file navigator panel<br />
(&quot;Explorer&quot;) on the left of the Gitpod view.</p>
<details><summary>Show me</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/gitpod_uploading_bundle_1_annotated.png?raw=true" />
</details>
<p>Once you drop it you will see it listed in the file explorer itself.<br />
As a check, you can issue the command</p>
<pre lang="bash"><code>ls /workspace/workshop-nosqlbench/secure*zip -lh
</code></pre>
<p>so that you get the <em>absolute path to your bundle file</em> (and also verify that it is<br />
the correct size, about 12-13 KB).</p>
<details><summary>Show me</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/gitpod_uploading_bundle_2b_annotated.png?raw=true" />
</details>
<h3><a class="anchor" aria-hidden="true" id="configure-the-astra-db-parameters"> </a>Configure the Astra DB parameters</h3>
<p>Copy the provided template file to a new one and open it in the Gitpod<br />
file editor:</p>
<pre lang="bash"><code>cp .env.sample .env
gp open .env
# (you can also simply locate the file
#  in the Explorer and click on it)
</code></pre>
<p>Insert the &quot;Client ID&quot; and &quot;Client Secret&quot; of the DB Token you created earlier<br />
and, if necessary, adjust the other variables.</p>
<details><summary>Show me what the .env file would look like</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/dotenv2.png?raw=true" />
</details>
<p>Now, source this file to make the definitions therein available to this shell:</p>
<pre lang="bash"><code>. .env
</code></pre>
<p>To check that the file has been sourced, you can try with:</p>
<pre lang="bash"><code>echo ${ASTRA_DB_KEYSPACE_NAME}
</code></pre>
<p>and make sure the output is not an empty line.</p>
<p>(Note that you will have to source the file in any new shell you plan to use).</p>
<h2><a class="anchor" aria-hidden="true" id="run-benchmarks"> </a>Run benchmarks</h2>
<p>Everything is set to start running the tool.</p>
<h3><a class="anchor" aria-hidden="true" id="a-short-dry-run"> </a>A short dry run</h3>
<p>Try launching this very short &quot;dry-run benchmark&quot;, that instead of actually<br />
reaching the database simply prints a series of CQL statements to the console<br />
(as specified by the <code>driver=stdout</code> parameter):</p>
<pre lang="bash"><code>nb5 cql-keyvalue2 astra                 \
    driver=stdout                       \
    rampup-cycles=10                    \
    main-cycles=10                      \
    keyspace=${ASTRA_DB_KEYSPACE_NAME}
</code></pre>
<p>You will see 21 (fully-formed, valid CQL) statements being printed:<br />
one <code>CREATE TABLE</code>, then ten <code>INSERT</code>s<br />
and then another ten between <code>SELECT</code>s and further <code>INSERT</code>s.</p>
<blockquote>
<p><strong>Note</strong>: we will use workload <code>cql-keyvalue2</code> throughout. This is functionally<br />
identical to the <code>cql-keyvalue</code> workload but is expressed in the newer syntax for<br />
<code>yaml</code> workloads, which comes handy when later dissecting its content.<br />
If you are working with NoSQLBench 4, remember to drop the trailing <code>2</code><br />
from the workload name in the following!</p>
</blockquote>
<p>Now re-launch the above dry run and look for differences in the output:</p>
<pre lang="bash"><code>nb5 cql-keyvalue2 astra                 \
    driver=stdout                       \
    rampup-cycles=10                    \
    main-cycles=10                      \
    keyspace=${ASTRA_DB_KEYSPACE_NAME}
</code></pre>
<p>is the output identical to the previous run down to the actual &quot;random&quot; values?</p>
<p>You can also peek at the <code>logs</code> directory now: it is created automatically and<br />
populated with some information from the benchmark at each execution of <code>nb</code>.</p>
<h3><a class="anchor" aria-hidden="true" id="benchmark-your-astra-db"> </a>Benchmark your Astra DB</h3>
<p>It is now time to start hitting the database!</p>
<p>This time you will run with <code>driver=cql</code> to actually reach the database:<br />
for that to work, you will provide all connection parameters set up earlier.</p>
<p>The next run will ask NoSQLBench to perform a substantial amount of operations,<br />
in order to collect enough statistical support for the results.</p>
<p>Here is the full command to launch:</p>
<pre lang="bash"><code>nb5 cql-keyvalue2                                                         \
    astra                                                                 \
    username=${ASTRA_DB_CLIENT_ID}                                        \
    password=${ASTRA_DB_CLIENT_SECRET}                                    \
    secureconnectbundle=${ASTRA_DB_BUNDLE_PATH}                           \
    keyspace=${ASTRA_DB_KEYSPACE_NAME}                                    \
    cyclerate=50                                                          \
    driver=cql                                                            \
    main-cycles=9000                                                      \
    rampup-cycles=9000                                                    \
    errors='OverloadedException:warn'                                     \
    --progress console:5s                                                 \
    --log-histograms 'histogram_hdr_data.log:.*.main.result.*:20s'        \
    --log-histostats 'hdrstats.log:.*.main.result.*:20s'
</code></pre>
<details><summary>Show me the command breakdown</summary>
<p>Note that some of the parameters (e.g. <code>keyspace</code>) are workload-specific.</p>
<table>
<thead>
<tr>
<th>command</th>
<th>meaning</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>cql-keyvalue2</code></td>
<td>workload</td>
</tr>
<tr>
<td><code>astra</code></td>
<td>scenario</td>
</tr>
<tr>
<td><code>username</code></td>
<td>authentication</td>
</tr>
<tr>
<td><code>password</code></td>
<td>authentication</td>
</tr>
<tr>
<td><code>secureconnectbundle</code></td>
<td>Astra DB connection parameters</td>
</tr>
<tr>
<td><code>keyspace</code></td>
<td>target keyspace</td>
</tr>
<tr>
<td><code>cyclerate</code></td>
<td>rate-limiting (cycles per second)</td>
</tr>
<tr>
<td><code>driver=cql</code></td>
<td>driver to use (CQL, for AstraDB/Cassandra)</td>
</tr>
<tr>
<td><code>main-cycles</code></td>
<td>how many operations in the &quot;main&quot; phase</td>
</tr>
<tr>
<td><code>rampup-cycles</code></td>
<td>how many operations in the &quot;rampup&quot; phase</td>
</tr>
<tr>
<td><code>errors</code></td>
<td>behaviour if errors occur during benchmarking</td>
</tr>
<tr>
<td><code>--progress console</code></td>
<td>frequency of console prints</td>
</tr>
<tr>
<td><code>--log-histograms</code></td>
<td>write data to HDR file (see later)</td>
</tr>
<tr>
<td><code>--log-histostats</code></td>
<td>write some basic stats to a file (see later)</td>
</tr>
</tbody>
</table>
<p>This way of invoking <code>nb</code>, the <a href="https://docs.nosqlbench.io/docs/workloads_101/11-named-scenarios/" target="_blank">&quot;named scenario&quot;</a><br />
way, is not the only one: it is also possible to have a finer-grained control over what activities should<br />
run with a full-fledged <a href="https://docs.nosqlbench.io/docs/reference/cli-scripting/" target="_blank">CLI scripting</a> syntax.</p>
<blockquote>
<p><strong>Note</strong>: the syntax of the <code>errors</code> parameter has been improved in NoSQLBench 5<br />
to allow for a <a href="https://docs.nosqlbench.io/docs/reference/error-handlers/" target="_blank">finer control</a> (with multiple directives,<br />
such as <code>errors='NoNodeAvailable.*:ignore;InvalidQueryException.*:counter;OverloadedException:warn'</code>).<br />
On version 4 you should revert to a simpler parameter,<br />
such as <code>errors=count</code>, instead of the above.</p>
</blockquote>
</details>
<p>The benchmark should last about ten minutes, with the progress being<br />
printed on the console as it proceeds.</p>
<p>While this runs, have a look around.</p>
<h4><a class="anchor" aria-hidden="true" id="database-contents"> </a>Database contents</h4>
<p>Now it's time to find out <em>what is actually being written to the database</em>.</p>
<p>Choose your database in the Astra main dashboard and click on it;<br />
next, go to the &quot;CQL Console&quot; tab in the main panel. In a few seconds the<br />
console will open in your browser, already connected to your database and<br />
waiting for your input.</p>
<details><summary>Show me how to get to the CQL Console in Astra</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/astra_get_to_cql_console.gif?raw=true" />
</details>
<p>Start by telling the console that you will be using the <code>nbkeyspace</code> keyspace:</p>
<pre><code>USE nbkeyspace;
</code></pre>
<p>Check what tables have been created by NoSQLBench in this keyspace:</p>
<pre><code>DESC TABLES;
</code></pre>
<p>You should see table <code>keyvalue</code> listed as the sole output.<br />
Look at a a few lines from this table:</p>
<pre><code>SELECT * FROM keyvalue LIMIT 20;
</code></pre>
<details><summary>Show me what the output looks like</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/select_cql.png?raw=true" />
</details>
<p>Ok, mystery solved. It looks like the table contains simple key-value pairs,<br />
with two columns seemingly of numeric type. Check with:</p>
<pre><code>DESC TABLE keyvalue;
</code></pre>
<p>Oh, looks like both the key and the value columns are of type <code>TEXT</code>:<br />
good for adapting this ready-made benchmark to other key/value stores.</p>
<details><summary>Show me what the output looks like</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/desctable_cql.png?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="database-health"> </a>Database health</h4>
<p>Locate your database in the Astra main dashboard and click on it;<br />
next, go to the &quot;Health&quot; tab in the main panel. You will see what essentially<br />
is a Grafana dashboard, with a handful of plots being displayed within the<br />
tab - all related to how the database is performing in terms of reads and writes.</p>
<details><summary>Show me the Database Health tab in Astra UI</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/astra_db_health2_annotated.png?raw=true" />
</details>
<p>Check the operations per second from the &quot;Requests Combined&quot; plot;<br />
then have a look at the &quot;Write Latency&quot; and &quot;Read Latency&quot; plots<br />
and take note of some of the percentiles shown there.</p>
<details><summary>Show me "sample values" one could read from the graph</summary>
<p>Below is a real-life example of the values that could result from a <code>cql-keyvalue2</code><br />
benchmark session in the <em>main</em> phase:</p>
<table>
<thead>
<tr>
<th>Percentile</th>
<th>Write Latency</th>
<th>Read Latency</th>
</tr>
</thead>
<tbody>
<tr>
<td>P50</td>
<td>709     <em>µs</em></td>
<td>935     <em>µs</em></td>
</tr>
<tr>
<td>P75</td>
<td>831     <em>µs</em></td>
<td>1.31  <em>ms</em></td>
</tr>
<tr>
<td>P90</td>
<td>904     <em>µs</em></td>
<td>1.53  <em>ms</em></td>
</tr>
<tr>
<td>P95</td>
<td>1.04  <em>ms</em></td>
<td>1.77  <em>ms</em></td>
</tr>
<tr>
<td>P99</td>
<td>2.45  <em>ms</em></td>
<td>15.6   <em>ms</em></td>
</tr>
</tbody>
</table>
</details>
<h4><a class="anchor" aria-hidden="true" id="final-summary-in-logs"> </a>Final summary in &quot;logs/&quot;</h4>
<p>When the benchmark has finished, open the latest <code>*.summary</code> file and look<br />
for <code>cqlkeyvalue2_astra_main.result-success</code>.</p>
<p>Under that metric title, you will see something similar to:</p>
<pre><code>cqlkeyvalue2_astra_main.result-success
             count = 15000
         mean rate = 50.00 calls/second
     1-minute rate = 49.94 calls/second
     5-minute rate = 50.29 calls/second
    15-minute rate = 50.57 calls/second
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="additional-histostats-datafile"> </a>Additional &quot;histostats&quot; datafile</h4>
<p>Use this script to generate a graph of the data collected as &quot;histostats&quot;:</p>
<pre lang="bash"><code>./hdr_tool/histostats_quick_plotter.py \
    hdrstats.log \
    -m cqlkeyvalue2_astra_main.result-success
</code></pre>
<p>and then open, in the Gitpod editor, the <code>hdrstats.png</code> image just created.</p>
<details><summary>Show me the generated "histostats" plot</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/histostats_plot3.png?raw=true" width="360" />
</details>
<blockquote>
<p>The version of the plotter script included in this repo is for <strong>educational purposes only</strong>:<br />
for general use, please head to<br />
<a href="https://pypi.org/project/nb-hdr-plotter/" target="_blank">the official release page</a>.</p>
</blockquote>
<p>The timings will be larger than those from the Astra health tab: indeed,<br />
these are &quot;as seen on the client side&quot; and include more network hops.</p>
<h4><a class="anchor" aria-hidden="true" id="hdr-extensive-histogram-data"> </a>HDR extensive histogram data</h4>
<p>Use this script to generate plots from the detailed &quot;HDR histogram data&quot;<br />
generated during the benchmark:</p>
<pre lang="bash"><code>./hdr_tool/hdr_tool.py \
    histogram_hdr_data.log \
    -b -c -s \
    -p SampleData \
    -m cqlkeyvalue2_astra_main.result-success
</code></pre>
<details><summary>Show me the plots generated by the HDR file</summary>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/hdr_baseplot2.png?raw=true" width="260"/>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/hdr_stabilityplot2.png?raw=true" width="260"/>
<img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/hdr_percentileplot2.png?raw=true" width="260"/>
</details>
<blockquote>
<p>The version of the plotter script included in this repo is for <strong>educational purposes only</strong>:<br />
for general use, please head to<br />
<a href="https://pypi.org/project/nb-hdr-plotter/" target="_blank">the official release page</a>.</p>
</blockquote>
<p>Again, the timings are larger than those found on the Astra health tab<br />
(i.e. on server-side): these<br />
measurements are reported &quot;as seen by the testing client&quot;.</p>
<h3><a class="anchor" aria-hidden="true" id="metrics-metrics-metrics"> </a>Metrics, metrics, metrics</h3>
<p>Launch a new benchmark, this time having NoSQLBench start a dockerized<br />
Grafana/Prometheus stack for metrics (it will take a few more seconds to start):</p>
<pre><code>nb5 cql-keyvalue2                                                         \
    astra                                                                 \
    username=${ASTRA_DB_CLIENT_ID}                                        \
    password=${ASTRA_DB_CLIENT_SECRET}                                    \
    secureconnectbundle=${ASTRA_DB_BUNDLE_PATH}                           \
    keyspace=${ASTRA_DB_KEYSPACE_NAME}                                    \
    cyclerate=50                                                          \
    rampup-cycles=15000                                                   \
    main-cycles=15000                                                     \
    errors='OverloadedException:warn'                                     \
    --progress console:5s                                                 \
    --docker-metrics
</code></pre>
<details><summary>Show me the run with Docker metrics</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/grafana_startingdockermetrics.png?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="grafana-dashboard"> </a>Grafana dashboard</h4>
<p>Reach the Grafana container in a new tab, with an URL that has <code>3000-</code><br />
in front of your Gitpod URL (e.g.<br />
<code>https://3000-datastaxdevs-workshopnos-[...].gitpod.io</code>).</p>
<p>The default credentials to log in to Grafana are ... <code>admin/admin</code>. Once you're<br />
in, don't bother to reset your password (click &quot;Skip&quot;). You'll get to the Grafana<br />
landing page. Find the &quot;Dashboards&quot; icon in the leftmost menu bar and pick the<br />
&quot;Manage&quot; menu item: finally, click on the &quot;NB4 Dashboard&quot; item you should see<br />
listed there. Congratulations, you are seeing the data coming from NoSQLBench.</p>
<details><summary>Show me how to get to the Grafana plots</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/grafana_dashboard.gif?raw=true" />
</details>
<blockquote>
<p>You may find it convenient to set the update frequency to something like 10<br />
seconds and the displayed time window to 5 minutes or so (upper-right controls).</p>
</blockquote>
<p>The dashboard comprises several (interactive) plots, updated in real time.</p>
<details><summary>Show me the dashboard contents</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/grafana_plots.png?raw=true" />
</details>
<h4><a class="anchor" aria-hidden="true" id="a-glance-at-prometheus"> </a>A glance at Prometheus</h4>
<p>To reach the Prometheus container, which handles the &quot;raw&quot; data behind Grafana,<br />
open a modified URL (this time with <code>9090-</code>) in a new tab.</p>
<details><summary>Show me the Prometheus UI</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/prometheus2.gif?raw=true" />
</details>
<p>Click on the &quot;world&quot; icon next to the &quot;Execute&quot; button in the search bar:<br />
in the dialog that appears you can look for specific metrics.<br />
Try to look for <code>result_success</code> and confirm, then click &quot;Execute&quot;.</p>
<blockquote>
<p><strong>Tip:</strong> switch to the &quot;Graph&quot; view for a more immediate visualization.<br />
The graphs display &quot;raw&quot; data, hence are in units of nanoseconds.</p>
</blockquote>
<p>To make sense of the (heterogeneous) results, some filtering is in order --<br />
but we are not entering too much into the details of Prometheus here.</p>
<p>Just to pique your interest, try pasting these examples and click &quot;Execute&quot;:</p>
<pre><code># filtering by metadata
{__name__=&quot;result_success&quot;, type=&quot;pctile&quot;, alias=~&quot;.*main.*&quot;}

# aggregation
avg_over_time({__name__=&quot;result_success&quot;, type=&quot;pctile&quot;, alias=~&quot;.*main.*&quot;}[10m])

# another aggregation, + filtering
max_over_time({__name__=&quot;result_success&quot;, type=&quot;pctile&quot;, alias=~&quot;.*main.*&quot;}[10m])
</code></pre>
<h2><a class="anchor" aria-hidden="true" id="workloads"> </a>Workloads</h2>
<p>This part is about how workloads are defined.</p>
<blockquote>
<p><strong>Tip</strong>: feel free to interrupt the previous benchmark, if it still runs,<br />
with Ctrl-C. You won't need it anymore.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="inspect-cql-keyvalue"> </a>Inspect &quot;cql-keyvalue&quot;</h3>
<p>Ask NoSQLBench to dump to a file the <code>yaml</code> defining the workload<br />
you just ran:</p>
<pre lang="bash"><code>    nb5 --copy cql-keyvalue2
</code></pre>
<p><em>(you can also get a comprehensive list of all available workloads with<br />
<code>nb5 --list-workloads</code>, by the way, and a more fine-grained output with<br />
<code>nb5 --list-scenarios</code>.)</em></p>
<p>A file <code>cql-keyvalue2.yaml</code> is created in the working directory.<br />
You can open it (clicking on it in the Gitpod explorer or by running<br />
<code>gp open cql-keyvalue2.yaml</code>).</p>
<p>Have a look at the file and try to identify its structure and the various<br />
phases the benchmark is organized into.</p>
<p>There are profound differences in the way the same workload is expressed<br />
in the NoSQLBench 4 yaml file and the NoSQLBench 5 format.</p>
<details><summary>Show me the differences</summary>
    <img src="https://github.com/datastaxdevs/workshop-nosqlbench/raw/main/images/cql-keyvalue-nb4-vs-nb5.png?raw=true" />
</details>
<h3><a class="anchor" aria-hidden="true" id="play-with-workloads"> </a>Play with workloads</h3>
<p>A good way to understand workload construction is to start from simple ones.</p>
<p>To run the following examples please go to the appropriate subdirectory:</p>
<pre><code>cd workloads
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="example-1-talking-about-food"> </a>Example 1: talking about food</h4>
<p>Run the first example (and then look at the corresponding<br />
<code>simple-workload.yaml</code>) with:</p>
<pre><code>nb5 run driver=stdout workload=simple-workload cycles=12
</code></pre>
<p>Look at how <em>bindings</em> connect the sequence of operations to &quot;execute&quot;<br />
(in this case, simply print on screen) with the data to be used in<br />
them.</p>
<h4><a class="anchor" aria-hidden="true" id="example-2-animal-meeting"> </a>Example 2: animal meeting</h4>
<p>Run the second example, which is an example of structuring a workload<br />
in <em>phases</em> (and then open <code>workload-with-phases.yaml</code>):</p>
<pre><code>nb5 workload-with-phases default driver=stdout
</code></pre>
<p>Notable features of this workload are its multi-phase structure<br />
(a nearly universal feature of actual benchmarks), the use<br />
of the <code>ratio</code> parameter, and the usage of template parameters in the<br />
definition.</p>
<h2><a class="anchor" aria-hidden="true" id="homework-assignment"> </a>Homework assignment</h2>
<p>The &quot;Lab&quot; part of the homework, which requires you to finalize<br />
a workload <code>yaml</code> and make it work according to specifications,<br />
is detailed on <a href="homework/homework.md" target="_blank">this page</a>.</p>
<p><strong>To submit your homework, please use <a href="https://dtsx.io/homework-nosqlbench" target="_blank">this form</a>.</strong></p>
