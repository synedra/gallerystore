<h2><a class="anchor" aria-hidden="true" id="introduction-to-nosql-databases"> </a>🎓🔥 Introduction to NoSQL Databases</h2>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/intro-to-nosql-cover.png?raw=true" alt="image" /></p>
<p>These instructions will lead you step by step for the workshop on introducing the NoSQL Databases technologies.</p>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="#" target="_blank">Workshop video</a></li>
<li><a href="./slides.pdf" target="_blank">Slide deck</a></li>
<li><a href="https://bit.ly/cassandra-workshop" target="_blank">Discord chat</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="participation-badge-homework"> </a>Participation Badge / Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/intro-to-nosql-badge.png?raw=true" width="200" align="right" />
<p>To get the verified badge, you have to complete the following steps:</p>
<ol>
<li>Complete the practice steps of this workshop as explained below. Steps 1-4 (Astra account + tabular/document/key-value databases) are mandatory, step 5 (graph database) is optional. Take a screenshot of completion of the last step for sections 2, 3 and 4 (either a CQL command output or a response in the Swagger UI). <em>NOTE: When taking screenshots ensure NOT to copy your Astra DB secrets!</em></li>
<li>Submit the practice <a href="https://dtsx.io/nosql-ws-hw" target="_blank">here</a>, answering a few &quot;theory&quot; questions and also attaching the screenshots.</li>
</ol>
<!-- x. Complete [try-it-out scenario](https://www.datastax.com/try-it-out) and make a screenshot of the "scenario completed" screen -->
<h2><a class="anchor" aria-hidden="true" id="practice"> </a>Practice</h2>
<ol>
<li><a href="#1-login-or-register-to-astradb-and-create-database" target="_blank">Login or Register to AstraDB and create database</a></li>
<li><a href="#2-tabular-databases" target="_blank">Tabular Databases</a></li>
<li><a href="#3-document-databases" target="_blank">Document Databases</a></li>
<li><a href="#4-keyvalue-databases" target="_blank">Key-Value Databases</a></li>
<li><a href="#5-graph-databases" target="_blank">Graph Databases</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-login-or-register-to-astradb-and-create-database"> </a>1. Login or Register to AstraDB and create database</h2>
<p><strong><code>ASTRADB</code></strong> is the simplest way to run Cassandra with zero operations at all - just push the button and get your cluster. No credit card required,<br />
a monthly free credit to use, covering about 20M reads/writes and 80GB storage (sufficient to run small production workloads), all for FREE.</p>
<h3><a class="anchor" aria-hidden="true" id="1a-register-a-free-account-on-astra"> </a>✅ 1a. Register a free account on Astra</h3>
<p>Click the button below to login or register on DataStax Astra DB. You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</p>
<p><a href="https://astra.dev/5-18" target="_blank"><img src="https://github.com/datastaxdevs/workshop-graphql-netflix/raw/master/img/create_astra_db.png?raw=true" /></a></p>
<p><strong>Use the following values when creating the database</strong> (this makes your life easier further on):</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Value</th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>database name</strong></td>
<td><code>workshops</code></td>
</tr>
<tr>
<td><strong>keyspace</strong></td>
<td><code>nosql1</code></td>
</tr>
<tr>
<td><strong>Cloud Provider</strong></td>
<td>Stick to GCP and then pick an &quot;unlocked&quot; region to start immediately</td>
</tr>
</tbody>
</table>
<p>More info on account creation <a href="https://awesome-astra.github.io/docs/pages/astra/create-account/" target="_blank">here</a>.</p>
<p>You will see your new database as <code>pending</code> or <code>initializing</code> on the Dashboard.<br />
The status will then change to <code>Active</code> when the database is ready: this will only take 2-3 minutes.<br />
At that point you will also receive a confirmation email.</p>
<h2><a class="anchor" aria-hidden="true" id="2-tabular-databases"> </a>2. Tabular databases</h2>
<p>In a tabular database we will store ... tables! The Astra DB Service is built on Apache Cassandra™, which is tabular. Let's start with this.</p>
<blockquote>
<p><strong>Tabular databases</strong> organize data in rows and columns, but with a twist from the traditional RDBMS. Also known as wide-column stores or partitioned row stores, they provide the option to organize related rows in partitions that are stored together on the same replicas to allow fast queries. Unlike RDBMSs, the tabular format is not necessarily strict. For example, Apache Cassandra™ does not require all rows to contain values for all columns in the table. Like Key/Value and Document databases, Tabular databases use hashing to retrieve rows from the table. Examples include: Cassandra, HBase, and Google Bigtable.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="2a-describe-your-keyspace"> </a>✅ 2a. Describe your Keyspace</h3>
<p>At database creation you provided a keyspace, a logical grouping for tables.<br />
Let's visualize it.<br />
In Astra DB go to CQL Console to enter the following commands</p>
<h4><a class="anchor" aria-hidden="true" id="select-your-db"> </a>Select your db</h4>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/01.png?raw=true" alt="image" /></p>
<h4><a class="anchor" aria-hidden="true" id="go-to-the-cql-console"> </a>Go to the Cql Console</h4>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/02.png?raw=true" alt="image" /></p>
<h4><a class="anchor" aria-hidden="true" id="enter-the-describe-command"> </a>Enter the describe command</h4>
<p>... and press Enter:</p>
<pre lang="sql"><code>DESCRIBE KEYSPACES;
</code></pre>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/03.png?raw=true" alt="image" /></p>
<h3><a class="anchor" aria-hidden="true" id="2b-create-table"> </a>✅ 2b. Create table</h3>
<h4><a class="anchor" aria-hidden="true" id="table-creation"> </a>Table creation</h4>
<p>Execute the following Cassandra Query Language commands</p>
<pre lang="sql"><code>USE nosql1;

CREATE TABLE IF NOT EXISTS accounts_by_user (
  user_id         UUID,
  account_id      UUID,
  account_type    TEXT,
  account_balance DECIMAL,
  user_name       TEXT      STATIC,
  user_email      TEXT      STATIC,
  PRIMARY KEY ( (user_id), account_id)
)   WITH CLUSTERING ORDER BY (account_id ASC);
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="check"> </a>Check</h4>
<p>Check keyspace contents and structure:</p>
<pre lang="sql"><code>DESCRIBE KEYSPACE nosql1;
</code></pre>
<p><em>👁️ Expected output</em></p>
<pre><code>CREATE KEYSPACE nosql1 WITH replication = {'class': 'NetworkTopologyStrategy', 'eu-central-1': '3'}  AND durable_writes = true;

CREATE TABLE nosql1.accounts_by_user (
    user_id uuid,
    account_id uuid,
    account_balance decimal,
    account_type text,
    user_email text static,
    user_name text static,
    PRIMARY KEY (user_id, account_id)
) WITH CLUSTERING ORDER BY (account_id ASC)
    AND additional_write_policy = '99PERCENTILE'
    AND bloom_filter_fp_chance = 0.01
    AND caching = {'keys': 'ALL', 'rows_per_partition': 'NONE'}
    AND comment = ''
    AND compaction = {'class': 'org.apache.cassandra.db.compaction.UnifiedCompactionStrategy'}
    AND compression = {'chunk_length_in_kb': '64', 'class': 'org.apache.cassandra.io.compress.LZ4Compressor'}
    AND crc_check_chance = 1.0
    AND default_time_to_live = 0
    AND gc_grace_seconds = 864000
    AND max_index_interval = 2048
    AND memtable_flush_period_in_ms = 0
    AND min_index_interval = 128
    AND read_repair = 'BLOCKING'
    AND speculative_retry = '99PERCENTILE';
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="2c-working-with-data"> </a>✅ 2c. Working with DATA</h3>
<h4><a class="anchor" aria-hidden="true" id="insert-some-entries-into-the-table"> </a>Insert some entries into the table</h4>
<pre lang="sql"><code>INSERT INTO accounts_by_user(user_id, account_id, account_balance, account_type, user_email, user_name)
VALUES(
    1cafb6a4-396c-4da1-8180-83531b6a41e3,
    811b56c3-cead-40d9-9a3d-e230dcd64f2f,
    1500,
    'Savings',
    'alice@example.org',
    'Alice'
);

INSERT INTO accounts_by_user(user_id, account_id, account_balance, account_type)
VALUES(
    1cafb6a4-396c-4da1-8180-83531b6a41e3,
    83428a85-5c8f-4398-8019-918d6e1d3a93,
    2500,
    'Checking'
);

INSERT INTO accounts_by_user(user_id, account_id, account_balance, account_type, user_email, user_name)
VALUES(
    0d2b2319-9c0b-4ecb-8953-98687f6a99ce,
    81def5e2-84f4-4885-a920-1c14d2be3c20,
    1000,
    'Checking',
    'bob@example.org',
    'Bob'
);
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="read-values"> </a>Read values</h4>
<pre lang="sql"><code>SELECT * FROM accounts_by_user;
</code></pre>
<blockquote>
<p>Such a full-table query is strongly discouraged in most distributed databases<br />
as it involves contacting many nodes to assemble the whole result dataset:<br />
here we are using it for learning purposes, not in production and on a table<br />
with very few rows!</p>
</blockquote>
<p><em>👁️ Expected output</em></p>
<pre><code> user_id                              | account_id                           | user_email        | user_name | account_balance | account_type
--------------------------------------+--------------------------------------+-------------------+-----------+-----------------+--------------
 0d2b2319-9c0b-4ecb-8953-98687f6a99ce | 81def5e2-84f4-4885-a920-1c14d2be3c20 |   bob@example.org |       Bob |            1000 |     Checking
 1cafb6a4-396c-4da1-8180-83531b6a41e3 | 811b56c3-cead-40d9-9a3d-e230dcd64f2f | alice@example.org |     Alice |            1500 |      Savings
 1cafb6a4-396c-4da1-8180-83531b6a41e3 | 83428a85-5c8f-4398-8019-918d6e1d3a93 | alice@example.org |     Alice |            2500 |     Checking

(3 rows)
</code></pre>
<blockquote>
<p>Notice that all three rows are &quot;filled with data&quot;, despite the second of the insertions above skipping the <code>user_email</code> and <code>user_name</code> columns:<br />
this is because these are <strong>static columns</strong> (i.e. associated to the whole partition) and their value had been written already in the first insertion.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="read-by-primary-key"> </a>Read by primary key</h4>
<pre lang="sql"><code>SELECT user_email, account_type, account_balance
  FROM accounts_by_user
  WHERE user_id=0d2b2319-9c0b-4ecb-8953-98687f6a99ce
    AND account_id=81def5e2-84f4-4885-a920-1c14d2be3c20;
</code></pre>
<p><em>👁️ Expected output</em></p>
<pre><code> user_email      | account_type | account_balance
-----------------+--------------+-----------------
 bob@example.org |     Checking |            1000

(1 rows)
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="2d-working-with-partitions"> </a>✅ 2d. Working with PARTITIONS</h3>
<p>But data can be grouped, we stored together what should be retrieved together.</p>
<h4><a class="anchor" aria-hidden="true" id="try-a-query-not-compatible-with-the-data-model"> </a>Try a query not compatible with the data model</h4>
<details><summary>(Optional: click to expand)</summary>
<pre><code>SELECT account_id, account_type, account_balance
   FROM accounts_by_user
   WHERE account_id=81def5e2-84f4-4885-a920-1c14d2be3c20;
</code></pre>
<!-- ```
InvalidRequest: Error from server: code=2200 [Invalid query] message="Cannot execute this query as it might involve data filtering and thus may have unpredictable performance. If you want to execute this query despite the performance unpredictability, use ALLOW FILTERING"
```
 -->
<p><strong><code>Yes, we know</code></strong>, and now let's see why.</p>
<pre><code>TRACING ON;
SELECT account_id, account_type, account_balance
   FROM accounts_by_user
   WHERE account_id=81def5e2-84f4-4885-a920-1c14d2be3c20
   ALLOW FILTERING;
TRACING OFF;
</code></pre>
<blockquote>
<p><em>Note</em>: <code>ALLOW FILTERING</code> is almost never to be used in production, we use it here to see what happens!</p>
</blockquote>
<p><em>👁️ Output</em></p>
<pre><code> account_id                           | account_type | account_balance
--------------------------------------+--------------+-----------------
 81def5e2-84f4-4885-a920-1c14d2be3c20 |     Checking |            1000

(1 rows)
</code></pre>
<p>But also (<em>&quot;Anatomy of a full-cluster scan&quot;</em>):</p>
<pre><code>Tracing session: e97b98b0-d146-11ec-a4e5-19251c2b96e1

 activity                                                                                                                   | timestamp                  | source      | source_elapsed | client
----------------------------------------------------------------------------------------------------------------------------+----------------------------+-------------+----------------+-----------------------------------------
                                                                                                         Execute CQL3 query | 2022-05-11 16:25:03.675000 | 10.0.63.218 |              0 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
 Parsing SELECT[....]_by_user\n   WHERE account_id=81def5e2-84f4-4885-a920-1c14d2be3c20\n   ALLOW FILTERING; [CoreThread-0] | 2022-05-11 16:25:03.676000 | 10.0.63.218 |            229 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                                         Preparing statement [CoreThread-0] | 2022-05-11 16:25:03.676000 | 10.0.63.218 |            445 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                                Computing ranges to query... [CoreThread-0] | 2022-05-11 16:25:03.681000 | 10.0.63.218 |           5970 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                         READS.RANGE_READ message received from /10.0.63.218 [CoreThread-9] | 2022-05-11 16:25:03.682000 | 10.0.31.189 |             -- | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                Submitting range requests on 25 ranges with a concurrency of 1 (0.0 rows per range expected) [CoreThread-0] | 2022-05-11 16:25:03.682000 | 10.0.63.218 |           6197 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                       Submitted 1 concurrent range requests [CoreThread-0] | 2022-05-11 16:25:03.682000 | 10.0.63.218 |           6312 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                             Sending READS.RANGE_READ message to /10.0.32.75, size=227 bytes [CoreThread-9] | 2022-05-11 16:25:03.682000 | 10.0.63.218 |           6436 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                            Sending READS.RANGE_READ message to /10.0.31.189, size=227 bytes [CoreThread-8] | 2022-05-11 16:25:03.682000 | 10.0.63.218 |           6436 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                         READS.RANGE_READ message received from /10.0.63.218 [CoreThread-4] | 2022-05-11 16:25:03.683000 |  10.0.32.75 |             -- | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
             Executing seq scan across 0 sstables for (min(-9223372036854775808), min(-9223372036854775808)] [CoreThread-4] | 2022-05-11 16:25:03.683000 |  10.0.32.75 |            444 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
             Executing seq scan across 0 sstables for (min(-9223372036854775808), min(-9223372036854775808)] [CoreThread-9] | 2022-05-11 16:25:03.684000 | 10.0.31.189 |            356 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                       Read 1 live rows and 0 tombstone ones [CoreThread-4] | 2022-05-11 16:25:03.684000 |  10.0.32.75 |            789 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                       Read 1 live rows and 0 tombstone ones [CoreThread-9] | 2022-05-11 16:25:03.684000 | 10.0.31.189 |            731 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                          Enqueuing READS.RANGE_READ response to /10.0.32.75 [CoreThread-4] | 2022-05-11 16:25:03.684000 |  10.0.32.75 |            897 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                         Enqueuing READS.RANGE_READ response to /10.0.31.189 [CoreThread-9] | 2022-05-11 16:25:03.684000 | 10.0.31.189 |            731 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                            Sending READS.RANGE_READ message to /10.0.63.218, size=212 bytes [CoreThread-7] | 2022-05-11 16:25:03.684000 |  10.0.32.75 |            954 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                            Sending READS.RANGE_READ message to /10.0.63.218, size=212 bytes [CoreThread-1] | 2022-05-11 16:25:03.684000 | 10.0.31.189 |           1098 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                          READS.RANGE_READ message received from /10.0.32.75 [CoreThread-9] | 2022-05-11 16:25:03.685000 | 10.0.63.218 |           9626 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                         READS.RANGE_READ message received from /10.0.31.189 [CoreThread-1] | 2022-05-11 16:25:03.702000 | 10.0.63.218 |          27526 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                        Processing response from /10.0.32.75 [CoreThread-0] | 2022-05-11 16:25:03.856000 | 10.0.63.218 |         181075 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                       Processing response from /10.0.31.189 [CoreThread-0] | 2022-05-11 16:25:03.856000 | 10.0.63.218 |         181193 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
Didn't get enough response rows; actual rows per range: 0.04; remaining rows: 99, new concurrent requests: 1 [CoreThread-0] | 2022-05-11 16:25:03.856000 | 10.0.63.218 |         181384 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
                                                                                                           Request complete | 2022-05-11 16:25:03.856560 | 10.0.63.218 |         181560 | 2898:d2d9:30d9:4a4f:acec:3e3a:3a76:4a7b
</code></pre>
</details>
<h4><a class="anchor" aria-hidden="true" id="retrieve-data-from-a-whole-partition"> </a>Retrieve data from a whole partition</h4>
<pre lang="sql"><code>SELECT account_id, account_type, account_balance
  FROM accounts_by_user
  WHERE user_id=1cafb6a4-396c-4da1-8180-83531b6a41e3;
</code></pre>
<p><em>👁️ Expected output</em></p>
<pre><code> account_id                           | account_type | account_balance
--------------------------------------+--------------+-----------------
 811b56c3-cead-40d9-9a3d-e230dcd64f2f |      Savings |            1500
 83428a85-5c8f-4398-8019-918d6e1d3a93 |     Checking |            2500

(2 rows)
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-document-databases"> </a>3. Document Databases</h2>
<p>Let's do some hands-on with document database queries.</p>
<blockquote>
<p><strong>Document databases</strong> expand on the basic idea of key-value stores where “documents” are more complex, in that they contain data and each document is assigned a unique key, which is used to retrieve the document. These are designed for storing, retrieving, and managing document-oriented information, often stored as JSON. Since the Document database can inspect the document contents, the database can perform some additional retrieval processing. Unlike RDBMSs which require a static schema, Document databases have a flexible schema as defined by the document contents. Examples include: MongoDB and CouchDB. Note that some RDBMS and NoSQL databases outside of pure document stores are able to store and query JSON documents, including Cassandra.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="3a-cassandra-native-json-support"> </a>✅ 3a. Cassandra native JSON support</h3>
<p>It is not widely known, but Cassandra accepts JSON queries out of the box. You can find more information <a href="https://docs.datastax.com/en/cql-oss/3.3/cql/cql_using/useInsertJSON.html" target="_blank">here</a>.</p>
<details><summary>Show native JSON support</summary>
<h4><a class="anchor" aria-hidden="true" id="json-syntax-for-insertions"> </a>JSON syntax for insertions</h4>
<p>Insert data into Cassandra with JSON syntax:</p>
<pre lang="sql"><code>INSERT INTO accounts_by_user JSON '{
  &quot;user_id&quot;: &quot;1cafb6a4-396c-4da1-8180-83531b6a41e3&quot;,
  &quot;account_id&quot;: &quot;811b56c3-cead-40d9-9a3d-e230dcd64f2f&quot;,
  &quot;user_email&quot;: &quot;alice@example.org&quot;,
  &quot;user_name&quot;: &quot;Alice&quot;,
  &quot;account_type&quot;: &quot;Savings&quot;,
  &quot;account_balance&quot;: &quot;8500&quot;
}' ;
</code></pre>
<blockquote>
<p>Warning: missing fields in the provided JSON will entail explicit insertion of corresponding <code>null</code> values.</p>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="json-output-when-querying"> </a>JSON output when querying</h4>
<p>In the same way you can retrieve JSON out of Cassandra (<a href="https://docs.datastax.com/en/cql-oss/3.3/cql/cql_using/useQueryJSON.html" target="_blank">more info here</a>).</p>
<pre lang="sql"><code>SELECT JSON account_type, account_balance
  FROM accounts_by_user
  WHERE user_id=1cafb6a4-396c-4da1-8180-83531b6a41e3;
</code></pre>
<p><em>👁️ Output</em></p>
<pre><code> [json]
-------------------------------------------------------
  {&quot;account_type&quot;: &quot;Savings&quot;, &quot;account_balance&quot;: 8500}
 {&quot;account_type&quot;: &quot;Checking&quot;, &quot;account_balance&quot;: 2500}

(2 rows)
</code></pre>
<p>This JSON support is but a wrapper around access to the same fixed-schema<br />
tables seen in the previous section (&quot;Tabular&quot;).</p>
</details>
<h3><a class="anchor" aria-hidden="true" id="3b-create-a-token-and-open-swagger"> </a>✅ 3b. Create a token and open Swagger</h3>
<p>We now turn to using Astra DB's Document API.</p>
<h4><a class="anchor" aria-hidden="true" id="token-creation"> </a>Token creation</h4>
<p>To do so, first you need to create an Astra DB token, which will<br />
be used for authentication to your database.</p>
<p><strong>Create a token with &quot;Database Administrator&quot; privileges following<br />
the instructions here: <a href="https://awesome-astra.github.io/docs/pages/astra/create-token/#c-procedure" target="_blank">Create an Astra DB token</a>.</strong><br />
(See also <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">the official docs on tokens</a>.)</p>
<p>Keep the &quot;token&quot; ready to use (it is the long string starting with <code>AstraCS:.....</code>).</p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token 
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<h4><a class="anchor" aria-hidden="true" id="swagger-ui"> </a>Swagger UI</h4>
<p>The Document API can be easily accessed through a Swagger UI:<br />
go the &quot;Connect&quot; page, stay in the &quot;Document API&quot; subpage, and locate the URL under the &quot;Launching Swagger UI&quot; heading:</p>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/connect.png?raw=true" alt="image" /></p>
<p>Locate the &quot;documents&quot; section in the Swagger UI. You are now ready to fire requests to the Document API.</p>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/05.png?raw=true" alt="image" /></p>
<h3><a class="anchor" aria-hidden="true" id="3c-create-a-new-empty-collection"> </a>✅ 3c. Create a new empty collection</h3>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger/swagger_3c.png" alt="Swagger 3c" /></p>
<ul>
<li>Access <em><strong>Create a new empty collection in a namespace</strong></em></li>
<li>Click <code>Try it out</code> button</li>
<li>Fill Header <code>X-Cassandra-Token</code> with <code>&lt;your_token&gt;</code></li>
<li>For <code>namespace-id</code> use <code>nosql1</code></li>
<li>For <code>body</code> use</li>
</ul>
<pre lang="json"><code>{ &quot;name&quot;: &quot;users&quot; }
</code></pre>
<ul>
<li>Click the <code>Execute</code> button</li>
</ul>
<p>You will get an <code>HTTP 201 - Created</code> return code.</p>
<blockquote>
<p><em>Note:</em> the response you just got from actually calling the API endpoint<br />
is given under the &quot;Server response&quot; heading. Do not confuse it with<br />
the &quot;Responses&quot; found immediately after, which are simply a documentation<br />
of all possible response codes (and the return object they quote are static<br />
example JSONs).</p>
</blockquote>
<details><summary>Click to show a screenshot</summary>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger_responses_annotated.png?raw=true" alt="image" /></p>
</details>
<h3><a class="anchor" aria-hidden="true" id="3d-create-new-documents"> </a>✅ 3d. Create new documents</h3>
<h4><a class="anchor" aria-hidden="true" id="add-a-first-document"> </a>Add a first document</h4>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger/swagger_3d.png" alt="Swagger 3d" /></p>
<ul>
<li>Access <em><strong>Create a new document</strong></em></li>
<li>Click <code>Try it out</code> button</li>
<li>Fill with Header <code>X-Cassandra-Token</code> with <code>AstraCS:...[your_token]...</code></li>
<li>For <code>namespace-id</code> use <code>nosql1</code></li>
<li>For <code>collection-id</code> use <code>users</code></li>
<li>For <code>body</code> use</li>
</ul>
<pre lang="json"><code>{
    &quot;accounts&quot;: [
        {
            &quot;balance&quot;: &quot;1000&quot;,
            &quot;id&quot;: &quot;81def5e2-84f4-4885-a920-1c14d2be3c20&quot;,
            &quot;type&quot;: &quot;Checking&quot;
        }
    ],
    &quot;email&quot;: &quot;bob@example.org&quot;,
    &quot;id&quot;: &quot;0d2b2319-9c0b-4ecb-8953-98687f6a99ce&quot;,
    &quot;name&quot;: &quot;Bob&quot;
}
</code></pre>
<ul>
<li>Click the <code>Execute</code> button</li>
</ul>
<p><em>👁️ Expected output (your <code>documentId</code> will be different)</em></p>
<pre lang="json"><code>{
  &quot;documentId&quot;: &quot;137d8609-87f6-4cb7-9506-e52f338e79e9&quot;
}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="add-another-document"> </a>Add another document</h4>
<p>Repeat with the following body, which has <em>a different structure</em>:</p>
<pre lang="json"><code>{
    &quot;accounts&quot;: [
        {
            &quot;balance&quot;: &quot;2500&quot;,
            &quot;id&quot;: &quot;83428a85-5c8f-4398-8019-918d6e1d3a93&quot;,
            &quot;type&quot;: &quot;Checking&quot;
        },
        {
            &quot;balance&quot;: &quot;1500&quot;,
            &quot;id&quot;: &quot;811b56c3-cead-40d9-9a3d-e230dcd64f2f&quot;,
            &quot;type&quot;: &quot;Savings&quot;
        }
    ],
    &quot;email&quot;: &quot;alice@example.org&quot;,
    &quot;id&quot;: &quot;1cafb6a4-396c-4da1-8180-83531b6a41e3&quot;,
    &quot;name&quot;: &quot;Alice&quot;
}
</code></pre>
<p>As before, the document will automatically be given an internal unique <code>documentId</code>.</p>
<h3><a class="anchor" aria-hidden="true" id="3e-retrieve-a-document-by-its-id"> </a>✅ 3e. Retrieve a document by its ID</h3>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger/swagger_3eB.png" alt="Swagger 3e" /></p>
<ul>
<li>Access <em><strong>Get a document</strong></em></li>
<li>Click <code>Try it out</code> button</li>
<li>Fill Header <code>X-Cassandra-Token</code> with <code>&lt;your_token&gt;</code></li>
<li>For <code>namespace-id</code> use <code>nosql1</code></li>
<li>For <code>collection-id</code> use <code>users</code></li>
<li>For <code>document-id</code> use Bob's <code>documentId</code> (e.g. <code>137d8609-87f6-4cb7-9506-e52f338e79e9</code> in the above sample output)</li>
<li>Click the <code>Execute</code> button</li>
</ul>
<p><em>👁️ Expected output</em></p>
<pre lang="json"><code>{
  &quot;documentId&quot;: &quot;137d8609-87f6-4cb7-9506-e52f338e79e9&quot;,
  &quot;data&quot;: {
    &quot;accounts&quot;: [
      {
        &quot;balance&quot;: &quot;1000&quot;,
        &quot;id&quot;: &quot;81def5e2-84f4-4885-a920-1c14d2be3c20&quot;,
        &quot;type&quot;: &quot;Checking&quot;
      }
    ],
    &quot;email&quot;: &quot;bob@example.org&quot;,
    &quot;id&quot;: &quot;0d2b2319-9c0b-4ecb-8953-98687f6a99ce&quot;,
    &quot;name&quot;: &quot;Bob&quot;
  }
}
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="3f-find-all-documents-in-a-collection"> </a>✅ 3f. Find all documents in a collection</h3>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger/swagger_3fB.png" alt="Swagger 3f" /></p>
<ul>
<li>Access <em><strong>Search documents in a collection</strong></em></li>
<li>Click <code>Try it out</code> button</li>
<li>Fill Header <code>X-Cassandra-Token</code> with <code>&lt;your_token&gt;</code></li>
<li>For <code>namespace-id</code> use <code>nosql1</code></li>
<li>For <code>collection-id</code> use <code>users</code></li>
</ul>
<p>Leave other fields blank (in particular, every query is paged in Cassandra).</p>
<ul>
<li>Click the <code>Execute</code> button</li>
</ul>
<p><em>👁️ Expected output (take note of the <code>documentId</code>s of your output for later)</em></p>
<pre lang="json"><code>{
  &quot;data&quot;: {
    &quot;6d0aafd9-3c2c-461f-92c6-08322eaef5da&quot;: {
      &quot;accounts&quot;: [
        {
          &quot;balance&quot;: &quot;2500&quot;,
          &quot;id&quot;: &quot;83428a85-5c8f-4398-8019-918d6e1d3a93&quot;,
          &quot;type&quot;: &quot;Checking&quot;
        },
        {
          &quot;balance&quot;: &quot;1500&quot;,
          &quot;id&quot;: &quot;811b56c3-cead-40d9-9a3d-e230dcd64f2f&quot;,
          &quot;type&quot;: &quot;Savings&quot;
        }
      ],
      &quot;email&quot;: &quot;alice@example.org&quot;,
      &quot;id&quot;: &quot;1cafb6a4-396c-4da1-8180-83531b6a41e3&quot;,
      &quot;name&quot;: &quot;Alice&quot;
    },
    &quot;137d8609-87f6-4cb7-9506-e52f338e79e9&quot;: {
      &quot;accounts&quot;: [
        {
          &quot;balance&quot;: &quot;1000&quot;,
          &quot;id&quot;: &quot;81def5e2-84f4-4885-a920-1c14d2be3c20&quot;,
          &quot;type&quot;: &quot;Checking&quot;
        }
      ],
      &quot;email&quot;: &quot;bob@example.org&quot;,
      &quot;id&quot;: &quot;0d2b2319-9c0b-4ecb-8953-98687f6a99ce&quot;,
      &quot;name&quot;: &quot;Bob&quot;
    }
  }
}
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="3g-search-document-with-a-where-clause"> </a>✅ 3g. Search document with a &quot;where&quot; clause</h3>
<p>The endpoint you just used can support <a href="https://docs.datastax.com/en/astra/docs/read-documents.html#_retrieving_a_document_using_a_where_clause" target="_blank"><code>where</code> clauses</a> as well,<br />
expressed as JSON. You don't need to navigate away from it do try the<br />
following:</p>
<p><img src="https://github.com/datastaxdevs/workshop-introduction-to-nosql/raw/master/images/swagger/swagger_3g.png" alt="Swagger 3g" /></p>
<ul>
<li>Access <em><strong>Search documents in a collection</strong></em> (you should be there already)</li>
<li>Click <code>Try it out</code> button</li>
<li>Fill Header <code>X-Cassandra-Token</code> with <code>&lt;your_token&gt;</code></li>
<li>For <code>namespace-id</code> use <code>nosql1</code></li>
<li>For <code>collection-id</code> use <code>users</code></li>
<li>For <code>where</code> use <code>{&quot;name&quot;: {&quot;$eq&quot;: &quot;Alice&quot;}}</code></li>
<li>Click the <code>Execute</code> button</li>
</ul>
<p><em>👁️ Expected output</em></p>
<pre lang="json"><code>{
  &quot;data&quot;: {
    &quot;6d0aafd9-3c2c-461f-92c6-08322eaef5da&quot;: {
      &quot;accounts&quot;: [
        {
          &quot;balance&quot;: &quot;2500&quot;,
          &quot;id&quot;: &quot;83428a85-5c8f-4398-8019-918d6e1d3a93&quot;,
          &quot;type&quot;: &quot;Checking&quot;
        },
        {
          &quot;balance&quot;: &quot;1500&quot;,
          &quot;id&quot;: &quot;811b56c3-cead-40d9-9a3d-e230dcd64f2f&quot;,
          &quot;type&quot;: &quot;Savings&quot;
        }
      ],
      &quot;email&quot;: &quot;alice@example.org&quot;,
      &quot;id&quot;: &quot;1cafb6a4-396c-4da1-8180-83531b6a41e3&quot;,
      &quot;name&quot;: &quot;Alice&quot;
    }
  }
}
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-key-value-databases"> </a>4. Key/Value Databases</h2>
<blockquote>
<p><strong>Key/Value databases</strong> are some of the simplest and yet powerful as all of the data within consists of an indexed key and a value. Key-value databases use a hashing mechanism, so that that given a key, the database can quickly retrieve the associated value. Hashing mechanisms provide constant time access, which means they maintain high performance even at large scale. The keys can be any type of object, but are typically a string. The values are generally opaque blobs (i.e. a sequence of bytes that the database does not interpret). Examples include: Redis, Amazon DynamoDB, Riak, and Oracle NoSQL database. Some tabular NoSQL databases, like Cassandra, can also service key/value needs.</p>
</blockquote>
<h3><a class="anchor" aria-hidden="true" id="4a-create-a-table-for-key-value"> </a>✅ 4a. Create a table for Key/Value</h3>
<p>Go to the CQL Console again and issue the following commands<br />
to create a new, simple table with just two columns:</p>
<pre lang="sql"><code>USE nosql1;

CREATE TABLE users_kv (
  key   TEXT PRIMARY KEY,
  value TEXT
);
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="4b-populate-the-table"> </a>✅ 4b. Populate the table</h3>
<p>Insert into the table all the following entries.<br />
Note that all inserted values, regardless of their &quot;true&quot; data type,<br />
have been coerced into strings according to the table schema.<br />
Also note how the keys are structured and how some entries reference other,<br />
effectively creating a set of interconnected pieces of information on the users:</p>
<pre lang="sql"><code>INSERT INTO users_kv (key, value) VALUES ('user:1cafb6a4-396c-4da1-8180-83531b6a41e3:name',       'Alice');
INSERT INTO users_kv (key, value) VALUES ('user:1cafb6a4-396c-4da1-8180-83531b6a41e3:email',      'alice@example.org');
INSERT INTO users_kv (key, value) VALUES ('user:1cafb6a4-396c-4da1-8180-83531b6a41e3:accounts',   '{83428a85-5c8f-4398-8019-918d6e1d3a93, 811b56c3-cead-40d9-9a3d-e230dcd64f2f}');

INSERT INTO users_kv (key, value) VALUES ('user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:name',       'Bob');
INSERT INTO users_kv (key, value) VALUES ('user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:email',      'bob@example.org');
INSERT INTO users_kv (key, value) VALUES ('user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:accounts',   '{81def5e2-84f4-4885-a920-1c14d2be3c20}');

INSERT INTO users_kv (key, value) VALUES ('account:83428a85-5c8f-4398-8019-918d6e1d3a93:type',    'Checking');
INSERT INTO users_kv (key, value) VALUES ('account:83428a85-5c8f-4398-8019-918d6e1d3a93:balance', '2500');

INSERT INTO users_kv (key, value) VALUES ('account:811b56c3-cead-40d9-9a3d-e230dcd64f2f:type',    'Savings');
INSERT INTO users_kv (key, value) VALUES ('account:811b56c3-cead-40d9-9a3d-e230dcd64f2f:balance', '1500');

INSERT INTO users_kv (key, value) VALUES ('account:81def5e2-84f4-4885-a920-1c14d2be3c20:type',    'Checking');
INSERT INTO users_kv (key, value) VALUES ('account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance', '1000');
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="4c-update-a-value"> </a>✅ 4c. Update a value</h3>
<p>You can imagine an application &quot;navigating the keys&quot; (e.g, from an user to an account) for instance<br />
when it must update a balance. The actual update would look like:</p>
<pre lang="sql"><code>INSERT INTO users_kv (key, value) VALUES ('account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance', '9000');
</code></pre>
<p>Let's check:</p>
<pre lang="sql"><code>SELECT * FROM users_kv WHERE key = 'account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance';
</code></pre>
<p><em>👁️ Expected output</em></p>
<pre><code> key                                                  | value
------------------------------------------------------+-------
 account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance |  9000

(1 rows)
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="alternative-update-syntax"> </a>Alternative update syntax</h4>
<p>The same result is obtained with</p>
<pre lang="sql"><code>UPDATE users_kv SET value = '-500' WHERE key = 'account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance';
</code></pre>
<p>indeed, in most key-value data stores, inserting and updating are one and the same operation<br />
since the main goal is usually the highest performance (hence, row-existence checks are skipped altogether).</p>
<p>Thus, writing entries with the key of a pre-existing entry will simply overwrite the less recent values,<br />
enabling a very efficient and simple deduplication strategy.</p>
<p>Check once more what's in the table:</p>
<pre lang="sql"><code>SELECT * FROM users_kv ;
</code></pre>
<p><em>👁️ Expected output</em></p>
<pre><code> key                                                  | value
------------------------------------------------------+------------------------------------------------------------------------------
 account:81def5e2-84f4-4885-a920-1c14d2be3c20:balance |                                                                         -500
   user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:accounts |                                       {81def5e2-84f4-4885-a920-1c14d2be3c20}
 account:811b56c3-cead-40d9-9a3d-e230dcd64f2f:balance |                                                                         1500
   user:1cafb6a4-396c-4da1-8180-83531b6a41e3:accounts | {83428a85-5c8f-4398-8019-918d6e1d3a93, 811b56c3-cead-40d9-9a3d-e230dcd64f2f}
      user:1cafb6a4-396c-4da1-8180-83531b6a41e3:email |                                                            alice@example.org
       user:1cafb6a4-396c-4da1-8180-83531b6a41e3:name |                                                                        Alice
       user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:name |                                                                          Bob
      user:0d2b2319-9c0b-4ecb-8953-98687f6a99ce:email |                                                              bob@example.org
    account:83428a85-5c8f-4398-8019-918d6e1d3a93:type |                                                                     Checking
    account:811b56c3-cead-40d9-9a3d-e230dcd64f2f:type |                                                                      Savings
    account:81def5e2-84f4-4885-a920-1c14d2be3c20:type |                                                                     Checking
 account:83428a85-5c8f-4398-8019-918d6e1d3a93:balance |                                                                         2500

(12 rows)
</code></pre>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-graph-databases"> </a>5. Graph Databases</h2>
<blockquote>
<p><strong>Graph databases</strong> store their data using a graph metaphor to exploit the relationships between data. Nodes in the graph represent data items, and edges represent the relationships between the data items. Graph databases are designed for highly complex and connected data, which outpaces the relationship and JOIN capabilities of an RDBMS. Graph databases are often exceptionally good at finding commonalities and anomalies among large data sets. Examples of Graph databases include DataStax Graph, Neo4J, JanusGraph, and Amazon Neptune.</p>
</blockquote>
<p>Astra DB does not contain yet a way to implement Graph Databases use cases. But at Datastax we do have a product called <a href="https://www.datastax.com/products/datastax-graph" target="_blank">DataStax Graph</a> that you can use for free when not in production.</p>
<p>For graph databases, the presenter will show a demo based on the example in the slides.</p>
<p>The hands-on practice for you is different. But since it cannot be done in the browser using<br />
Astra DB like the rest, it is kept separate and not included in today's curriculum.</p>
<p>🔥 Yet, you are strongly encouraged to try it at your own pace, on your own computer,<br />
by following the instructions given here: <a href="graph_databases.md" target="_blank">Graph Databases Practice</a>. 🔥</p>
<blockquote>
<p>Try it out, it's super cool!</p>
</blockquote>
<h2><a class="anchor" aria-hidden="true" id="the-end"> </a>THE END</h2>
<p>Congratulations! You made it to the END.</p>
<p>See you next time!</p>
<p><a href="#table-of-content" target="_blank">🏠 Back to Table of Contents</a></p>
