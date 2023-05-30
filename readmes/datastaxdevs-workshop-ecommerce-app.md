<!--- STARTEXCLUDE --->
<h2><a class="anchor" aria-hidden="true" id="building-an-e-commerce-website"> </a>🔥 Building an E-commerce Website 🔥</h2>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-ecommerce-app" target="_blank"><img src="https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod" alt="Gitpod ready-to-code" /></a><br />
<a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://discord.com/widget?id=685554030159593522&amp;theme=dark" target="_blank"><img src="https://img.shields.io/discord/685554030159593522" alt="Discord" /></a></p>
<img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/splash.png?raw=true" align="right" width="400px"/>
<h2><a class="anchor" aria-hidden="true" id="materials-for-the-session"> </a>Materials for the Session</h2>
<p>It doesn't matter if you join our workshop live or you prefer to do at your own pace, we have you covered. In this repository, you'll find everything you need for this workshop:</p>
<ul>
<li><a href="./slides_wk1.pdf" target="_blank">Slide deck - week 1</a></li>
<li><a href="./slides_wk2.pdf" target="_blank">Slide deck - week 2</a></li>
<li><a href="./slides_wk3.pdf" target="_blank">Slide deck - week 3</a></li>
<li><a href="./slides_wk4.pdf" target="_blank">Slide deck - week 4</a></li>
<li><a href="https://community.datastax.com/" target="_blank">Questions and Answers</a></li>
<li>[Worskhop code] (<a href="https://github.com/datastaxdevs/workshop-ecommerce-app" target="_blank">https://github.com/datastaxdevs/workshop-ecommerce-app</a>)</li>
</ul>
<p>If you cannot attend this workshop live, recordings of this workshop and many more is available on <a href="https://youtube.com/datastaxdevs" target="_blank">Youtube</a>.</p>
<h2><a class="anchor" aria-hidden="true" id="homework"> </a>Homework</h2>
<img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/build-an-ecommerce-app.png" width="200" align=right />
<p>Complete the homework to earn the badge for this workshop (<strong>awarded only at the end of the series</strong>).</p>
<ol>
<li>Implement Google login and take SCREENSHOT(s).</li>
<li>Don't worry about submitting it just yet.  We'll have instructions on how to do that at the end of the series!</li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="table-of-contents"> </a>📋 Table of contents</h2>
<ol>
<li><a href="#1-introduction" target="_blank">Introduction</a></li>
<li><a href="#2-create-astra-db-instance" target="_blank">Create your Database</a></li>
<li><a href="#3-create-your-schema" target="_blank">Create your schema</a></li>
<li><a href="#4-populate-the-data" target="_blank">Populate the dataset</a></li>
<li><a href="#5-create-your-token" target="_blank">Create a token</a></li>
<li><a href="#6-setup-your-application" target="_blank">Setup your application</a></li>
<li><a href="#7-enable-social-login" target="_blank">Enable Social Login</a></li>
<li><a href="#8-run-unit-tests" target="_blank">Run Unit Tests</a></li>
<li><a href="#9-start-the-application" target="_blank">Start the Application</a></li>
</ol>
<h2><a class="anchor" aria-hidden="true" id="1-introduction"> </a>1. Introduction</h2>
<p>Are you building or do you support an e-commerce website?  If so, then this content is for <strong>you</strong>!</p>
<p>Worldwide digital sales in 2020 eclipsed four trillion dollars (USD).  Businesses that want to compete, need a high performing e-commerce website.  Here, we will demonstrate how to build a high performing persistence layer with DataStax <strong><code>ASTRA DB</code></strong>.</p>
<p>Why does an e-commerce site need to be fast?  Because most consumers will leave a web page or a mobile app if it takes longer than a few seconds to load.  In the content below, we will cover how to build high-performing data models and services, helping you to build a e-commerce site with high throughput and low latency.</p>
<h2><a class="anchor" aria-hidden="true" id="2-create-astra-db-and-streaming-instances"> </a>2. Create Astra DB and Streaming Instances</h2>
<p>You can skip to step 2c if you have already created a keyspace <code>ecommerce</code> in database <code>demos</code>. Otherwise (if you did not attend the previous installment of the e-commerce worksop):</p>
<p><strong><code>ASTRA DB</code></strong> is the simplest way to run Cassandra with zero operations - just push the button and get your cluster. No credit card required, $25.00 USD credit every month, roughly 20M read/write operations, 80GB storage monthly - sufficient to run small production workloads.</p>
<h4><a class="anchor" aria-hidden="true" id="2a-register"> </a>✅ 2a. Register</h4>
<p>If you do not have an account yet, register and sign in to Astra DB: This is FREE and NO CREDIT CARD is required. <a href="https://astra.dev/yt-11-30" target="_blank">https://astra.datastax.com</a>: You can use your <code>Github</code>, <code>Google</code> accounts or register with an <code>email</code>.</p>
<p><em>Make sure to chose a password with minimum 8 characters, containing upper and lowercase letters, at least one number and special character</em></p>
<h4><a class="anchor" aria-hidden="true" id="2b-create-a-db-on-the-free-plan"> </a>✅ 2b. Create a DB on the &quot;FREE&quot; plan</h4>
<p>Follow this <a href="https://docs.datastax.com/en/astra/docs/creating-your-astra-database.html" target="_blank">guide</a>, to set up a pay as you go database with a free $25 monthly credit. You will find below recommended values to enter:</p>
<ul>
<li>
<p><strong>For the database name</strong> - <code>demos</code></p>
</li>
<li>
<p><strong>For the keyspace name</strong> - <code>ecommerce</code></p>
</li>
</ul>
<p><em>You can technically use whatever name(s) you want and update the code to reflect the keyspace. This is really to get you on a happy path for the first run.</em></p>
<ul>
<li>
<p><strong>For provider and region</strong>: For Astra DB, select GCP as a provider and then the related region is where your database will reside physically (choose one close to you or your users).</p>
</li>
<li>
<p><strong>Create the database</strong>. Review all the fields to make sure they are as shown, and click the <code>Create Database</code> button.</p>
</li>
</ul>
<p><strong>👁️ Walkthrough</strong></p>
<p><em>The Walkthrough mentions a different keyspace, make sure to use <code>ecommerce</code></em></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/astra-create-db.gif?raw=true" alt="image" /><br />
You will see your new database <code>pending</code> in the Dashboard.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/db-pending.png?raw=true" alt="my-pic" /></p>
<h4><a class="anchor" aria-hidden="true" id="2c-ensure-the-database-turns-to-active-state"> </a>✅ 2c. Ensure the database turns to active state</h4>
<p>To connect to the database programmatically, you need to make sure the status will change to <code>Active</code>. This happens when the database is ready, and will only take 2-3 minutes. You will also receive an email when it is ready.</p>
<p><strong>👁️ Expected Output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/db-active.png?raw=true" alt="my-pic" /></p>
<p>If it's in a <code>standby</code> state you can hit <code>Connect</code> and <code>CQL Console</code> on top.</p>
<p>You should see a message something like below.</p>
<p><strong>👁️ Expected Output</strong></p>
<pre lang="cql"><code>{&quot;message&quot;:&quot;Resuming your database, please try again shortly.&quot;}
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="2d-create-a-streaming-tenant-and-topics-on-the-free-plan"> </a>✅ 2d. Create a Streaming Tenant and Topics on the &quot;FREE&quot; plan</h4>
<p>Here we will walk through how to create an Astra Streaming Tenant.  Start by clicking the &quot;Create Stream&quot; button in the left navigation pane.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/create-stream.png?raw=true" alt="image" /></p>
<p>On the next page, provide a name for your tenant and select a provider/region.  Click the blue &quot;Create Tenant&quot; button when complete.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/create_streaming_tenant.png?raw=true" alt="image" /></p>
<p>Note that Tenant Names must be unique across providers.  To ensure uniqueness, name it &quot;ecommerce-&quot; followed by your name or company.</p>
<p>Now we need to create topics <em>within</em> our tenant.  Click on the link or on the &quot;Topics&quot; tab.  You should see the &quot;default&quot; namespace with an &quot;Add Topic&quot; button (on the right).  Click the &quot;Add Topic&quot; button.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/add_topic1.png?raw=true" alt="image" /></p>
<p>Name the topic &quot;pending-orders&quot; and make sure that the &quot;Persistent&quot; switch is selected.  Don't worry about the &quot;Partitioned&quot; switch for now.  Click the &quot;Add Topic&quot; button when ready.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/add_topic2.png?raw=true" alt="image" /></p>
<p>Repeat this process to add 3 more topics:</p>
<ul>
<li>picked-orders</li>
<li>shipped-orders</li>
<li>completed-orders</li>
</ul>
<p>When you are done, your &quot;Topics&quot; tab should look similar to this:</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/streaming_topics_final.png?raw=true" alt="image" /></p>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="3-create-your-schema"> </a>3. Create your schema</h2>
<p><strong>Introduction</strong><br />
This section will provide DDL to create three tables inside the &quot;ecommerce&quot; keyspace: category, price, and product.</p>
<h4><a class="anchor" aria-hidden="true" id="session-1-product-data-model"> </a>Session 1 - Product data model</h4>
<p>The <code>product</code> table supports all product data queries, and uses <code>product_id</code> as a single key.  It has a few columns for specific product data, but any ad-hoc or non-standard properties can be added to the <code>specifications</code> map.</p>
<p>The <code>category</code> table will support all product navigation service calls.  It is designed to provide recursive, hierarchical navigation without a pre-set limit on the number of levels.  The top-most level only exists as a <code>parent_id</code>, and the bottom-most level contains products.</p>
<p>The <code>price</code> table was intentionally split-off from product.  There are several reasons for this.  Price data is much more likely to change than pure product data (different read/write patterns).  Also, large enterprises typically have separate teams for product and price, meaning they will usually have different micro-service layers and data stores.</p>
<p>The <code>featured_product_groups</code> table was a late-add, to be able to provide some extra &quot;atmosphere&quot; of an e-commerce website.  This way, the UI has a means by which to highlight a few, select products.</p>
<h4><a class="anchor" aria-hidden="true" id="session-2-shopping-cart-data-model"> </a>Session 2 - Shopping Cart data model</h4>
<p>The <code>user_carts</code> table supports cart metadata.  Carts are not expected to be long-lived, so they have a default TTL (time to live) of 60 days (5,184,000 seconds).  Carts also have a <code>name</code> as a part of the key, so that the user can have multiple carts (think &quot;wish lists&quot;).</p>
<p>The <code>cart_products</code> table holds data on the products added to the cart.  The cart uses <code>product_timestamp</code> as the first clustering key in descending order; this way products in the cart will be listed with the most-recently-added products at the top.  Like <code>user_carts</code>, each entry has a 60 day TTL.</p>
<h4><a class="anchor" aria-hidden="true" id="session-3-user-profile-data-model"> </a>Session 3 - User Profile data model</h4>
<p>The <code>user</code> table holds all data on the user, keyed by a single PRIMARY KEY on <code>user_id</code>.  It's main features contain TEXT (string) data for common user properties, as well as a collection of <code>addresses</code>.  This is because users (especially B-to-B) may have multiple addresses (mail-to, ship-to, bill-to, etc).  The <code>addresses</code> collection is built on a special user defined type (UDT) and <code>FROZEN</code> to treat the collection as a Binary Large OBject (BLOB) to reduce tombstones (required by CQL).</p>
<p>As mentioned above, the <code>address</code> UDT contains properties used for postal contacts.  All properties are of the TEXT datatype.</p>
<p>The <code>user_by_email</code> table is intended to be used as a &quot;manual index&quot; on email address. Essentially, it is a lookup table returning the <code>user_id</code> associated with an email address.  This is necessary as <code>user_email</code> is nigh-unique (in terms of cardinality of values), and thus a CQL secondary index would perform quite poorly.</p>
<h4><a class="anchor" aria-hidden="true" id="session-4-order-processing-system-data-model"> </a>Session 4 - Order Processing System data model</h4>
<p>The <code>order_by_id</code> table holds detail on each order.  It partitions on <code>order_id</code> for optimal data distribution, and clusters on <code>product_name</code> and <code>product_id</code> for sort order.  The columns specific to the order itself (and not a product) are <code>STATIC</code> so that they are only stored once (with the partition key).</p>
<p>The <code>order_by_user</code> table holds a reference to each order by <code>user_id</code>.  The idea, is that this table is queried by <code>user_id</code> and the results are shown on an &quot;order history&quot; page for that user.  Then, each order can be clicked-on, revealing the detail contained in the <code>order_by_id</code> table.  <code>order_id</code> is a TimeUUID (version 1 UUID) type, which is converted into a human-readable timestamp in the service layer.</p>
<p>The <code>order_status_history</code> table maintains a history of each status for an order.  It is meant to be used with queries to the <code>order_by_id</code> table, so that a user may see the status progression of their order.</p>
<h3><a class="anchor" aria-hidden="true" id="3a-open-the-cqlconsole-on-astra"> </a>✅ 3a. Open the CqlConsole on Astra</h3>
<pre lang="sql"><code>use ecommerce;
</code></pre>
<h3><a class="anchor" aria-hidden="true" id="3b-execute-the-following-cql-script-to-create-the-schema"> </a>✅ 3b. Execute the following CQL script to create the schema</h3>
<pre lang="sql"><code>/* Session 1 - Product data model */
/* category table */
CREATE TABLE IF NOT EXISTS category (
    parent_id UUID,
    category_id UUID,
    name TEXT,
    image TEXT,
    products LIST&lt;TEXT&gt;,
PRIMARY KEY (parent_id,category_id));

/* price table */
CREATE TABLE IF NOT EXISTS price (
    product_id TEXT,
    store_id TEXT,
    value DECIMAL,
PRIMARY KEY(product_id,store_id));

/* product table */
CREATE TABLE IF NOT EXISTS product (
    product_id TEXT,
    product_group TEXT,
    name TEXT,
    brand TEXT,
    model_number TEXT,
    short_desc TEXT,
    long_desc TEXT,
    specifications MAP&lt;TEXT,TEXT&gt;,
    linked_documents MAP&lt;TEXT,TEXT&gt;,
    images SET&lt;TEXT&gt;,
PRIMARY KEY(product_id));

/* featured product groups table */
CREATE TABLE IF NOT EXISTS featured_product_groups (
    feature_id INT,
    category_id UUID,
    name TEXT,
    image TEXT,
    parent_id UUID,
    price DECIMAL,
PRIMARY KEY (feature_id,category_id));

/* Session 2 - Shopping Cart data model */
CREATE TABLE IF NOT EXISTS user_carts (
    user_id uuid,
    cart_name text,
    cart_id uuid,
    cart_is_active boolean,
    user_email text,
    PRIMARY KEY (user_id, cart_name, cart_id)
) WITH default_time_to_live = 5184000;

CREATE TABLE IF NOT EXISTS cart_products (
    cart_id uuid,
    product_timestamp timestamp,
    product_id text,
    product_description text,
    product_name text,
    quantity int,
    PRIMARY KEY (cart_id, product_timestamp, product_id)
) WITH CLUSTERING ORDER BY (product_timestamp DESC, product_id ASC)
  AND default_time_to_live = 5184000;

/* Session 3 - User Profile data model */
CREATE TYPE IF NOT EXISTS address (
  type TEXT,
  mailto_name TEXT,
  street TEXT,
  street2 TEXT,
  city TEXT,
  state_province TEXT,
  postal_code TEXT,
  country TEXT
);

CREATE TABLE IF NOT EXISTS user (
  user_id UUID,
  user_email TEXT,
  picture_url TEXT,
  first_name TEXT,
  last_name TEXT,
  locale TEXT,
  addresses LIST&lt;FROZEN&lt;address&gt;&gt;,
  session_id TEXT,
  password TEXT,
  password_timestamp TIMESTAMP,
  PRIMARY KEY (user_id)
);

CREATE TABLE IF NOT EXISTS user_by_email (
  user_email TEXT PRIMARY KEY,
  user_id UUID
);

/* Session 4 - Order Processing System data model */
CREATE TABLE IF NOT EXISTS order_by_id (
    order_id timeuuid,
    product_name text,
    product_id text,
    order_shipping_handling decimal static,
    order_status text static,
    order_subtotal decimal static,
    order_tax decimal static,
    order_total decimal static,
    payment_method text static,
    product_price decimal,
    product_qty int,
    shipping_address address static,
    PRIMARY KEY (order_id, product_name, product_id)
) WITH CLUSTERING ORDER BY (product_name ASC, product_id ASC);

CREATE TABLE IF NOT EXISTS order_by_user (
    user_id uuid,
    order_id timeuuid,
    order_status text,
    order_total decimal,
    PRIMARY KEY (user_id, order_id)
) WITH CLUSTERING ORDER BY (order_id DESC);

CREATE TABLE IF NOT EXISTS order_status_history (
    order_id timeuuid,
    status_timestamp timestamp,
    order_status text,
    PRIMARY KEY (order_id, status_timestamp)
) WITH CLUSTERING ORDER BY (status_timestamp DESC);
</code></pre>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="4-populate-the-data"> </a>4. Populate the Data</h2>
<h4><a class="anchor" aria-hidden="true" id="4a-execute-the-following-script-to-populate-the-tables-with-the-data-below"> </a>✅ 4a. Execute the following script to populate the tables with the data below</h4>
<h4><a class="anchor" aria-hidden="true" id="session-1-product-data"> </a>Session 1 - Product data</h4>
<pre lang="sql"><code>INSERT INTO category (name,category_id,image,parent_id) VALUES ('Clothing',18105592-77aa-4469-8556-833b419dacf4,'ls534.png',ffdac25a-0244-4894-bb31-a0884bc82aa9);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Tech Accessories',5929e846-53e8-473e-8525-80b666c46a83,'',ffdac25a-0244-4894-bb31-a0884bc82aa9);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Cups and Mugs',675cf3a2-2752-4de7-ae2e-849471c29f51,'',ffdac25a-0244-4894-bb31-a0884bc82aa9);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Wall Decor',591bf485-de09-4b46-8fd2-5d9dc7ca101e,'bh001.png',ffdac25a-0244-4894-bb31-a0884bc82aa9);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('T-Shirts',91455473-212e-4c6e-8bec-1da06779ae10,'ls534.png',18105592-77aa-4469-8556-833b419dacf4);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Hoodies',6a4d86aa-ceb5-4c6f-b9b9-80e9a8c58ad1,'',18105592-77aa-4469-8556-833b419dacf4);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Jackets',d887b049-d16c-46e1-8c94-0a1280dedc30,'',18105592-77aa-4469-8556-833b419dacf4);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Mousepads',d04dfb5b-69c6-4e97-b572-e9e390165a84,'',5929e846-53e8-473e-8525-80b666c46a83);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Wrist Rests',aa161129-d456-45ba-b1f0-fac7898b6d06,'',5929e846-53e8-473e-8525-80b666c46a83);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Laptop Covers',1c4b8599-78df-4f93-9c52-578bd959a3a5,'',5929e846-53e8-473e-8525-80b666c46a83);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Cups',7536fdef-fcd9-44a3-9360-0bffd2904408,'',675cf3a2-2752-4de7-ae2e-849471c29f51);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Coffee Mugs',20374300-185c-4ee5-b0bc-77fbdc3a21ed,'',675cf3a2-2752-4de7-ae2e-849471c29f51);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Travel Mugs',0660483e-2fad-447b-b19a-63ab4935e482,'',675cf3a2-2752-4de7-ae2e-849471c29f51);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Posters',fdbe9dcb-6878-4216-a64d-27c094b1b075,'',591bf485-de09-4b46-8fd2-5d9dc7ca101e);
INSERT INTO category (name,category_id,image,parent_id) VALUES ('Wall Art',943482f9-070c-4390-bb30-2107b6fe653a,'bh001.png',591bf485-de09-4b46-8fd2-5d9dc7ca101e);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('Men''s &quot;Go Away...Annotation&quot; T-Shirt',99c4d825-d262-4a95-a04e-cc72e7e273c1,'ls534.png',91455473-212e-4c6e-8bec-1da06779ae10,['LS534S','LS534M','LS534L','LS534XL','LS5342XL','LS5343XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('Men''s &quot;Your Face...Autowired&quot; T-Shirt',3fa13eee-d057-48d0-b0ae-2d83af9e3e3e,'ln355.png',91455473-212e-4c6e-8bec-1da06779ae10,['LN355S','LN355M','LN355L','LN355XL','LN3552XL','LN3553XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('Bigheads',2f25a732-0744-406d-baee-3e8131cbe500,'bh001.png',943482f9-070c-4390-bb30-2107b6fe653a,['bh001','bh002','bh003']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('DataStax Gray Track Jacket',f629e107-b219-4563-a852-6909fd246949,'dss821.jpg',d887b049-d16c-46e1-8c94-0a1280dedc30,['DSS821S','DSS821M','DSS821L','DSS821XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('DataStax Vintage 2015 MVP Hoodie',86d234a4-6b97-476c-ada8-efb344d39743,'dsh915.jpg',6a4d86aa-ceb5-4c6f-b9b9-80e9a8c58ad1,['DSH915S','DSH915M','DSH915L','DSH915XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('DataStax Black Hoodie',b9bed3c0-0a76-44ea-bce6-f5f21611a3f1,'dsh916.jpg',6a4d86aa-ceb5-4c6f-b9b9-80e9a8c58ad1,['DSH916S','DSH916M','DSH916L','DSH916XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('Apache Cassandra 3.0 Contributor T-Shirt',95ae4613-0184-46ee-b4b0-adfe882754a8,'apc30a.jpg',91455473-212e-4c6e-8bec-1da06779ae10,['APC30S','APC30M','APC30L','APC30XL','APC302XL','APC303XL']);
INSERT INTO category (name,category_id,image,parent_id,products) VALUES ('DataStax Astra &quot;One Team&quot; Long Sleeve Tee',775be203-1a84-4822-9645-4da98ca2b2d8,'dsa1121.jpg',91455473-212e-4c6e-8bec-1da06779ae10,['DSA1121S','DSA1121M','DSA1121L','DSA1121XL','DSA11212XL','DSA11213XL']);

INSERT INTO price(product_id,store_id,value) VALUES ('LS534S','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LS534M','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LS534L','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LS534XL','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LS5342XL','web',16.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LS5343XL','web',16.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN355S','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN355M','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN355L','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN355XL','web',14.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN3552XL','web',16.99);
INSERT INTO price(product_id,store_id,value) VALUES ('LN3553XL','web',16.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA1121S','web',21.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA1121M','web',21.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA1121L','web',21.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA1121XL','web',21.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA11212XL','web',23.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSA11213XL','web',23.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSS821S','web',44.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSS821M','web',44.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSS821L','web',44.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSS821XL','web',44.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH915S','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH915M','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH915L','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH915XL','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH916S','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH916M','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH916L','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('DSH916XL','web',35.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC30S','web',15.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC30M','web',15.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC30L','web',15.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC30XL','web',15.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC302XL','web',17.99);
INSERT INTO price(product_id,store_id,value) VALUES ('APC303XL','web',17.99);

INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS534S','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s Small &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'Small','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS534M','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s Medium &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'Medium','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS534L','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s Large &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS534XL','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s Extra Large &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'Extra Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS5342XL','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s 2x Large &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'2x Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LS5343XL','LS534','Go Away Annotation T-Shirt','NerdShirts','NS101','Men''s 3x Large &quot;Go Away...Annotation&quot; T-Shirt','Having to answer support questions when you really want to get back to coding?  Wear this to work, and let there be no question as to what you''d rather be doing.',{'size':'3x Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ls534.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN355S','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s Small &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'Small','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN355M','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s Medium &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'Medium','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN355L','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s Large &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN355XL','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s Extra Large &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'Extra Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN3552XL','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s 2x Large &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'2x Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('LN355XL','LN355','Your Face is an @Autowired @Bean T-Shirt','NerdShirts','NS102','Men''s 3x Large &quot;Your Face...Autowired&quot; T-Shirt','Everyone knows that one person who overuses the &quot;your face&quot; jokes.',{'size':'3x Large','material':'cotton, polyester','cut':'men''s','color':'black'},{'ln355.png'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA1121S','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - Small','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'Small','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA1121M','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - Medium','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'Medium','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA1121L','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - Large','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'Large','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA1121XL','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - Extra Large','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'Extra Large','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA11212XL','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - 2X Large','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'2X Large','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSA11213XL','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee','DataStax','DSA1121','DataStax Astra &quot;One Team&quot; Long Sleeve Tee - 3X Large','Given out at the internal summit, show how proud you are to talk about the world''s best multi-region, multi-cloud, serverless database!',{'size':'3X Large','material':'cotton, polyester','color':'black'},{'dsa1121.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC30S','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - Small','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'Small','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC30M','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - Medium','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'Medium','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC30L','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - Large','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'Large','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC30XL','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - Extra Large','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'Extra Large','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC302XL','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - 2X Large','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'2X Large','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('APC303XL','APC30','Apache Cassandra 3.0 Contributor T-Shirt','Apache Foundation','APC30','Apache Cassandra 3.0 Contributor T-Shirt - 3X Large','Own a piece of Cassandra history with this Apache Cassandra 3.0 &quot;Contributor&quot; shirt.  Given out to all of the contributors to the project in 2016, shows the unmistakable Cassandra Eye on the front, with the
engine rebuild&quot; on the back.',{'size':'3X Large','material':'cotton, polyester','color':'black'},{'apc30.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSS821S','DSS821','DataStax Gray Track Jacket','DataStax','DSS821','DataStax Gray Track Jacket - Small','This lightweight polyester jacket will be your favorite while hiking the trails or teeing off.',{'size':'Small','material':'polyester','color':'gray'},{'dss821.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSS821M','DSS821','DataStax Gray Track Jacket','DataStax','DSS821','DataStax Gray Track Jacket - Medium','This lightweight polyester jacket will be your favorite while hiking the trails or teeing off.',{'size':'Medium','material':'polyester','color':'gray'},{'dss821.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSS821L','DSS821','DataStax Gray Track Jacket','DataStax','DSS821','DataStax Gray Track Jacket - Large','This lightweight polyester jacket will be your favorite while hiking the trails or teeing off.',{'size':'Large','material':'polyester','color':'gray'},{'dss821.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSS821XL','DSS821','DataStax Gray Track Jacket','DataStax','DSS821','DataStax Gray Track Jacket - Extra Large','This lightweight polyester jacket will be your favorite while hiking the trails or teeing off.',{'size':'Extra Large','material':'polyester','color':'gray'},{'dss821.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH915S','DSH915','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS915','DataStax Vintage 2015 MVP Hoodie - Small','Given out to MVPs at the 2015 DataStax Cassandra Summit.  Warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Small','color':'black'},{'dsh915.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH915M','DSH915','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS915','DataStax Vintage 2015 MVP Hoodie - Medium','Given out to MVPs at the 2015 DataStax Cassandra Summit.  Warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Medium','color':'black'},{'dsh915.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH915L','DSH915','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS915','DataStax Vintage 2015 MVP Hoodie - Large','Given out to MVPs at the 2015 DataStax Cassandra Summit.  Warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Large','color':'black'},{'dsh915.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH915XL','DSH915','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS915','DataStax Vintage 2015 MVP Hoodie - Extra Large','Given out to MVPs at the 2015 DataStax Cassandra Summit.  Warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Extra Large','color':'black'},{'dsh915.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH916S','DSH916','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS916','DataStax Black Hoodie - Small','Super warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Small','color':'black'},{'dsh916.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH916M','DSH916','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS916','DataStax Black Hoodie - Medium','Super warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Medium','color':'black'},{'dsh916.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH916L','DSH916','DataStax Vintage 2015 MVP Hoodie','DataStax','DSS916','DataStax Black Hoodie - Large','Super warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Large','color':'black'},{'dsh916.jpg'});
INSERT INTO product(product_id,product_group,name,brand,model_number,short_desc,long_desc,specifications,images)
VALUES ('DSH916XL','DSH916','DataStax Black Hoodie','DataStax','DSS916','DataStax Black Hoodie - Extra Large','Super warm!  You will underestimate how many times you will fall asleep wearing this!',{'size':'Extra Large','color':'black'},{'dsh916.jpg'});

INSERT INTO featured_product_groups (feature_id,name,category_id,image,price,parent_id) VALUES (202112,'DataStax Gray Track Jacket',f629e107-b219-4563-a852-6909fd246949,'dss821.jpg',44.99,d887b049-d16c-46e1-8c94-0a1280dedc30);
INSERT INTO featured_product_groups (feature_id,name,category_id,image,price,parent_id) VALUES (202112,'DataStax Black Hoodie',b9bed3c0-0a76-44ea-bce6-f5f21611a3f1,'dsh916.jpg',35.99,6a4d86aa-ceb5-4c6f-b9b9-80e9a8c58ad1);
INSERT INTO featured_product_groups (feature_id,name,category_id,image,price,parent_id) VALUES (202112,'Apache Cassandra 3.0 Contributor T-Shirt',95ae4613-0184-46ee-b4b0-adfe882754a8,'apc30a.jpg',15.99,91455473-212e-4c6e-8bec-1da06779ae10);
INSERT INTO featured_product_groups (feature_id,name,category_id,image,price,parent_id) VALUES (202112,'DataStax Astra &quot;One Team&quot; Long Sleeve Tee',775be203-1a84-4822-9645-4da98ca2b2d8,'dsa1121.jpg',21.99,91455473-212e-4c6e-8bec-1da06779ae10);

</code></pre>
<p>Although it's not advised to use wildcards as below, you can verify the data has been created with the following command.</p>
<pre><code>select * from CATEGORY;
</code></pre>
<p><strong>Notes:</strong></p>
<ul>
<li>The &quot;top&quot; categories of the product hierarchy can be retrieved using a <code>parent_id</code> of &quot;ffdac25a-0244-4894-bb31-a0884bc82aa9&quot;.</li>
<li>Without specifying a <code>category_id</code>, all categories for the <code>parent_id</code> are returned.</li>
<li>When a category from the &quot;bottom&quot; of the hierarchy is queried, a populated <code>products</code> ArrayList will be returned.  From there, the returned <code>product_id</code>s can be used with the <code>/product</code> service.</li>
<li>Category navigation is achieved by using the <code>parent_id</code> and <code>category_id</code> properties returned for each category (to build the &quot;next level&quot; category links).</li>
<li><code>/category/ffdac25a-0244-4894-bb31-a0884bc82aa9</code>  =&gt;  Category[Clothing, Cups and Mugs, Tech Accessories, Wall Decor]</li>
<li><code>/category/ffdac25a-0244-4894-bb31-a0884bc82aa9/18105592-77aa-4469-8556-833b419dacf4</code>  =&gt;  Category[Clothing]</li>
<li><code>/category/18105592-77aa-4469-8556-833b419dacf4</code>  =&gt;  Category[T-Shirts, Hoodies, Jackets]</li>
<li><code>/category/91455473-212e-4c6e-8bec-1da06779ae10</code>  =&gt;  Category[Men's &quot;Your Face...Autowired&quot; T-Shirt, Men's &quot;Go Away...Annotation&quot; T-Shirt]</li>
<li>The featured products table is a simple way for web marketers to promote small numbers of products, and have them appear in an organized fashion on the main page.  The <code>feature_id</code> key is simply an integer, with the default being <code>202112</code> (for December, 2021).  You can (of course) use other numeric naming schemes.</li>
</ul>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="5-create-your-tokens"> </a>5. Create your tokens</h2>
<h4><a class="anchor" aria-hidden="true" id="5a-create-the-astra-db-token"> </a>✅ 5a. Create the Astra DB token</h4>
<p>Following the <a href="https://docs.datastax.com/en/astra/docs/manage-application-tokens.html" target="_blank">Manage Application Tokens docs</a> create a token with <code>Database Admnistrator</code> roles.</p>
<ul>
<li>
<p>Go the <code>Organization Settings</code></p>
</li>
<li>
<p>Go to <code>Token Management</code></p>
</li>
<li>
<p>Pick the role <code>Database Administrator</code> on the select box</p>
</li>
<li>
<p>Click Generate token</p>
</li>
</ul>
<p><strong>👁️ Walkthrough</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/astra-create-token.gif?raw=true" alt="image" /></p>
<p>This is what the token page looks like. You can now download the values as a CSV. We will need those values but you can also keep this window open for use later.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/astra-token.png?raw=true" alt="image" /></p>
<ul>
<li><code>appToken:</code> We will use it as a api token Key to interact with APIs.</li>
</ul>
<h4><a class="anchor" aria-hidden="true" id="5b-save-your-db-token-locally"> </a>✅ 5b. Save your DB token locally</h4>
<p>To know more about roles of each token you can have a look to <a href="https://www.youtube.com/watch?v=TUTCLsBuUd4&amp;list=PL2g2h-wyI4SpWK1G3UaxXhzZc6aUFXbvL&amp;index=8" target="_blank">this video.</a></p>
<p><strong>Note: Make sure you don't close the window accidentally or otherwise - if you close this window before you copy the values, the application token is lost forever. They won't be available later for security reasons.</strong></p>
<blockquote>
<p><strong>⚠️ Important</strong></p>
<pre><code>The instructor will show you on screen how to create a token
but will have to destroy to token immediately for security reasons.
</code></pre>
</blockquote>
<p>We are now set with the database and credentials and will incorporate them into the application as we will see below.</p>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h4><a class="anchor" aria-hidden="true" id="5c-view-the-astra-streaming-token-and-connection-details"> </a>✅ 5c. View the Astra Streaming token and connection details</h4>
<p>Click on the &quot;Connect&quot; tab.  Take note of your tenant name and broker service URL.  It's a good idea to copy/paste those into a text editor for now.  When you're ready, click on the &quot;Token Manager&quot; link.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/broker_service_url.png?raw=true" alt="image" /></p>
<p>You should have one token created by default.  Click on the copy icon on the right.  Paste your token into a text editor for now.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/copy_stream_token.png?raw=true" alt="image" /></p>
<p>Later on, we will use this information to populate environment variables, allowing us to connect to our Astra Streaming tenant.  It will be similar to the example below:</p>
<pre><code>export ASTRA_STREAM_TENANT=ecommerce-aaron
export ASTRA_STREAM_URL=&quot;pulsar+ssl://pulsar-gcp-uscentral1.streaming.datastax.com:6651&quot;
export ASTRA_STREAM_TOKEN=&quot;eyJhMBhGYBlahBlahBlahNotARealToken37hOAv9t1fHIhJLAHw&quot;
</code></pre>
<h4><a class="anchor" aria-hidden="true" id="5d-save-your-streaming-token-locally"> </a>✅ 5d. Save your Streaming token locally</h4>
<h2><a class="anchor" aria-hidden="true" id="6-setup-your-application"> </a>6. Setup your application</h2>
<p><a href="https://gitpod.io/#https://github.com/datastaxdevs/workshop-ecommerce-app" target="_blank"><img src="https://gitpod.io/button/open-in-gitpod.svg" alt="Open in Gitpod" /></a></p>
<h3><a class="anchor" aria-hidden="true" id="know-your-gitpod"> </a>Know your Gitpod</h3>
<p>Take a moment to read this entire section since it'll help you with the rest of the workshop as you'll be spending most of your time in Gitpod. If you're familiar with Gitpod, you can easily skip this entire section.</p>
<p>The extreme left side has the explorer view(1). The top left, middle to right is where you'll be editing files(2), etc. and the bottom left, middle to right is what we will refer to as the Gitpod terminal window(3) as shown below.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-01-home-annotated.png?raw=true" alt="gitpod" /></p>
<p>You can always get back to the file explorer view whenever by clicking on the hamburger menu on the top left followed by <code>View</code> and <code>Explorer</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Filexplorer0.png?raw=true" alt="gitpod" /></p>
<p>You can allow cutting and pasting into the window by clicking on <code>Allow</code> as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/allow.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>6a: Enter the token</strong></p>
<p>To run the application you need to provide the credentials and identifier to the application. you will have to provide 4 values in total as shown below</p>
<p>Copy the environment sample file as below.</p>
<pre><code>cp .env.example .env
</code></pre>
<p>Open the <code>.env</code> file as below.</p>
<pre><code>gp open .env
</code></pre>
<ul>
<li>
<p>In Astra DB go back to home page by clicking the logo</p>
</li>
<li>
<p>Select you database <code>demos</code> in the left panel and then copy values for <code>cloud-region</code> and <code>database-id</code> (clusterID) from the details page as shown below.</p>
</li>
<li>
<p><em>The DatabaseID is located on the home page</em></p>
</li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/astra-config-1.png?raw=true" alt="Ecom Welcome Screen" /></p>
<ul>
<li><em>The Database region (and keyspace) are located in the details page</em></li>
</ul>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/astra-config-2.png?raw=true" alt="Ecom Welcome Screen" /></p>
<ul>
<li>
<p>Replace <code>application-token</code> with values shown on the Astra token screen or picking the values from the CSV token file your dowloaded before including the AstraCS: part of the token.</p>
</li>
<li>
<p><em>Make sure the Token looks something like (with AstraCS: preceeding <code>AstraCS:xxxxxxxxxxx:yyyyyyyyyyy</code></em></p>
</li>
</ul>
<pre lang="yaml"><code># Copy this file to .env and fill in the appropriate values. Refer to README.md
# for instructions on where to find them.
export ASTRA_DB_ID=
export ASTRA_DB_REGION=
export ASTRA_DB_APP_TOKEN=
export ASTRA_DB_KEYSPACE=ecommerce
export ASTRA_STREAM_TENANT=
export ASTRA_STREAM_URL=
export ASTRA_STREAM_TOKEN=
export GOOGLE_CLIENT_ID=
export GOOGLE_CLIENT_SECRET=
</code></pre>
<p>Make sure to inject the environment variables by running the following command</p>
<pre><code>source .env
</code></pre>
<p>Verify that the environment variables are properly setup with the following command</p>
<pre><code>env | grep -i astra
</code></pre>
<p>You should see four environment variables (not shown here).</p>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="7-enable-social-login"> </a>7. Enable Social Login</h2>
<p>Now that we're done with tests, let's <code>cd</code> to the top directory.</p>
<pre><code>/workspace/workshop-ecommerce-app/
</code></pre>
<p>On a tab in a browser navigate to <a href="https://console.cloud.google.com/apis/credentials" target="_blank">https://console.cloud.google.com/apis/credentials</a>.</p>
<p>Consent to using APIs and services and you should finally be presented a screen that looks like below and pick values as shown.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthconsent1.png?raw=true" alt="ouath" /></p>
<p>Pick the appropriate values as shown below and complete the consent.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthconsent2.png?raw=true" alt="ouath" /></p>
<p>Make sure the project is setup for internal testing (and not for production) as shown below with the &quot;MAKE INTERNAL&quot;.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthconsent3.png?raw=true" alt="ouath" /></p>
<p>Now click on the <code>credentials</code> tab, <code>+ CREATE CREDENTIALS</code> tab and finally the <code>OAuth Client ID</code> dropdown as shown in the following screen.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthcred0.png?raw=true" alt="ouath" /></p>
<p>You will be presented with a screen for entering the <code>Authorized JavaScript Origins</code> and <code>Authorized redirect URIs</code> as shown below.</p>
<p>You'll need the following URIs. Make a note of this. We will use <code>http</code> instead of <code>https</code> as illustrated below.</p>
<p>For the <code>Authorized JavaScript Origins</code> use the following value from the Gitpod terminal window,</p>
<pre lang="bash"><code>echo $(gp url 8080 | sed 's/https/http/')
</code></pre>
<p>For the <code>Authorized redirect URIs</code> use the following from the GitPod terminal window.</p>
<pre lang="bash"><code>echo $(gp url 8080 | sed 's/https/http/')/login/oauth2/code/google
</code></pre>
<p>Enter the respective values as shown below which enables URI redirection and SSO for the app.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthcred1.png?raw=true" alt="ouath" /></p>
<p>Make sure you enter the above values correctly as shown and hit <code>CREATE</code> on bottom as shown.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthcred2.png?raw=true" alt="ouath" /></p>
<p>Now you're ready to fetch the credentials  by using the copy 'n paste icons on right as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthcred3.png?raw=true" alt="ouath" /></p>
<p>You can copy and paste them in the <code>.env</code> file as entries for Google <code>GOOGLE_CLIENT_ID</code> and <code>GOOGLE_CLIENT_SECRET</code>.</p>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="8-run-unit-tests"> </a>8. Run Unit Tests</h2>
<p>The application is now set you should be able to interact with your DB. Let's demonstrate some capabilities.</p>
<p>✅ <strong>8a: Use CqlSession</strong></p>
<p>Interaction with Cassandra are implemented in Java through drivers and the main Class is <code>CqlSession</code>.</p>
<p>Higher level frameworks like Spring, Spring Data, or even quarkus will rely on this object so let's make sure it is part of your Spring context with a <code>@SpringBootTest</code>.</p>
<p>Let's change to the sub-directory from the terminal window as shown below.</p>
<pre><code>cd backend
</code></pre>
<p>Let's run the first test with the following command.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.tutorials.Test01_Connectivity
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre lang="bash"><code>[..init...]
Execute some Cql (CqlSession)
+ Your Keyspace: sag_ecommerce
+ Product Categories:
Clothing
Cups and Mugs
Tech Accessories
Wall Decor
List Databases available in your Organization (AstraClient)
+ Your OrganizationID: e195fbea-79b6-4d60-9291-063d8c9e6364
+ Your Databases:
workshops	 : id=8c98b922-aeb0-4435-a0d5-a2788e23dff8, region=eu-central-1
sample_apps	 : id=c2d6bd3d-6112-47f6-9b66-b033e6174f0e, region=us-east-1
sdk_tests	 : id=a52f5879-3476-42d2-b5c9-81b18fc6d103, region=us-east-1
metrics	 : id=d7ded041-3cfb-4dd4-9957-e20003c3ebe2, region=us-east-1
</code></pre>
<p>✅ <strong>8b: Working With Spring Data</strong></p>
<p>Spring Data allows Mapping <code>Object &lt;=&gt; Table</code> based on annotation at the java bean level. Then by convention CQL query will be executed under the hood.</p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.tutorials.Test02_SpringData
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre lang="bash"><code>Categories:
- Clothing with children:[T-Shirts, Hoodies, Jackets]
- Cups and Mugs with children:[Cups, Coffee Mugs, Travel Mugs]
- Tech Accessories with children:[Mousepads, Wrist Rests, Laptop Covers]
- Wall Decor with children:[Posters, Wall Art]
</code></pre>
<p>✅ <strong>8c: Working With Rest Controller</strong></p>
<p><code>TestRestTemplate</code> is a neat way to test a web controller. The application will start on a random port with <code>@SpringBootTest(webEnvironment=WebEnvironment.RANDOM_PORT)</code></p>
<pre lang="bash"><code>mvn test -Dtest=com.datastax.tutorials.Test03_RestController
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre lang="bash"><code>List Categories:
Clothing
Cups and Mugs
Tech Accessories
Wall Decor
</code></pre>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h2><a class="anchor" aria-hidden="true" id="9-start-the-application"> </a>9. Start the Application</h2>
<p>You can install the backend with the credentials using the following command</p>
<pre><code>cd /workspace/workshop-ecommerce-app
mvn install -f backend/pom.xml -DskipTests
</code></pre>
<p>✅ <strong>9a: Know your public URL</strong></p>
<p>The workshop application has opened with an ephemeral URL. To know the URL where your application endpoint will be exposed you can run the following command in the terminal after the build has completed. **Please note this URL and we will open this up in a new browser window if required later **.</p>
<pre lang="bash"><code>gp url 8080
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-02-url.png?raw=true" alt="gitpod" /></p>
<p>✅ <strong>9b: Check APIs are not available (yet)</strong></p>
<p>Run the following command in the Gitpod terminal window</p>
<pre><code>curl localhost:8080/api/v1/products/product/LS534S
</code></pre>
<p><strong>👁️ Expected output</strong></p>
<pre><code>curl: (7) Failed to connect to localhost port 8080: Connection refused
</code></pre>
<p>Not to be overly concerned as we're going to be starting the application that will be served from the port.</p>
<p>✅ <strong>9c: Start the application</strong></p>
<p>To start the application, we've provided a very simple convenience script that can be run as below.</p>
<pre lang="bash"><code>./start.sh
</code></pre>
<p>Pay attention to popups being blocked as shown below and allow the popups.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/PopupBlocked.png?raw=true" alt="gitpod" /></p>
<p>You may encounter the following at different steps and although this may not be applicable right away, the steps are included <strong>in advance</strong> and summarized here so that you can keep an eye out for it. Different paths and different environments might be slightly different although Gitpod levels the playing field a bit.</p>
<p>Your e-commerce application should be up and running.</p>
<p>✅ <strong>9d: Check APIs are now available</strong></p>
<p>Get back to Gitpod tab/window.</p>
<p>Leave the application running and open up another <code>shell</code> in the Gitpod terminal window by clicking on <code>+</code> and clicking on <code>bash</code> dropdown as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-newbash1.png?raw=true" alt="gitpod" /></p>
<p>This will bring up a new <code>bash</code> shell as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-newbash2.png?raw=true" alt="gitpod" /></p>
<p>Issue the following command in that shell as you did earlier.</p>
<pre><code>curl localhost:8080/api/v1/products/product/LS534S
</code></pre>
<p>and you should see some output indicating that the API server is serving our ecommerce APIs.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-newbash3.png?raw=true" alt="gitpod" /></p>
<p>Try a few other APIs (<strong>Hint: Look for the <code>RestController</code> java files in the respective sub-directories.</strong>).</p>
<p>✅ <strong>9e: OPTIONAL - Open in Gitpod preview window</strong></p>
<p>This might be useful for troubleshooting if your application does not automatically open up a browser tab.</p>
<p>If you want, you can run the following command to open your application in the preview window of Gitpod (it's much easier to use the app running in browser, though).</p>
<pre><code>gp preview $(gp url 8080)
</code></pre>
<p>As indicated in the output below it's a very <code>Simple Browser</code>.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/gitpod-preview-1.png?raw=true" alt="gitpod" /></p>
<p>If your application is running in the preview window but you have difficulty accessing it from the browser pay attention to popups being blocked by the browser as explained before.</p>
<p>✅ <strong>9f: Get the Open API specification</strong></p>
<p>In the new shell window open the specification in the preview or browser with the following command</p>
<pre><code>gp preview $(gp url 8080)/swagger-ui/index.html
</code></pre>
<p>The preview window looks like below. <strong>It might help to close all the tabs or open this URL in a browser by clicking on the <code>open in browser</code> tab on the top right as shown</strong>.</p>
<p><strong>👁️ Expected output</strong></p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/swagger2.png?raw=true" alt="image" /></p>
<p>Here's how it looks in the browser tab.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/swagger.png?raw=true" alt="image" /></p>
<p>This is the docs for the open APIs that enables the frontend or any other program to obtain the data and manipulate it with REST-based CRUD operations.</p>
<p>The complete app is running in the browser as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/splash.png?raw=true" alt="image" /></p>
<p>✅ <strong>9g: Use your social login</strong></p>
<p>Hit login as shown below</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthlogin0.png?raw=true" alt="login" /></p>
<p>You should be presented with the Google SSO Login option. Click on the icon as shown below.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthlogin1.png?raw=true" alt="login" /></p>
<p>Pick the Google user account and proceed to login as you would with Google.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthlogin2.png?raw=true" alt="login" /></p>
<p>If all the values are wired properly you should see the following screen with the icon above showing that the authentication worked as below and the <code>Logout</code> button now available.</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/Oauthauthenticated.png?raw=true" alt="ouath" /></p>
<p>and voila, just like that we are done setting up user profile with Google. We can implement Github and other social logins similarly.</p>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<p>✅ <strong>9h: Process your order(s)</strong></p>
<p>Did you put items in your cart and check out?  You will likely have an order waiting in your &quot;pending-orders&quot; topic.  To simulate moving the orders between topics, a small Order Processor was created.  To build and run:</p>
<pre><code>source .env
cd orderProcessor
mvn clean install
</code></pre>
<p>Once that process completes, have a look at the <code>target/</code> directory.  You should see a JAR named <code>ecom-0.0.1-SNAPSHOT-spring-boot.jar</code>.  To process an order on the &quot;pending-orders&quot; topic, you need to have it &quot;picked.&quot;  To simulate a picking process, try this:</p>
<pre><code>java -jar target/ecom-0.0.1-SNAPSHOT-spring-boot.jar pick
</code></pre>
<p>If an order is present, you should see the order JSON get processed and moved to the next topic:</p>
<pre><code>{&quot;cartId&quot;:&quot;b8a5bd07-2337-44de-8890-582e88e29754&quot;,&quot;cartName&quot;:&quot;b8a5bd07-2337-44de-8890-582e88e29754&quot;,&quot;orderId&quot;:&quot;e8ecd3b0-498b-11ed-b5a7-fbd1f5143654&quot;,&quot;userId&quot;:&quot;f1dbd2c0-bda4-4ccc-93dd-4aecd78758f5&quot;,&quot;productList&quot;:[{&quot;productId&quot;:&quot;DSS821XL&quot;,&quot;productName&quot;:&quot;DataStax Gray Track Jacket&quot;,&quot;productQty&quot;:1,&quot;productPrice&quot;:44.99},{&quot;productId&quot;:&quot;APC30XL&quot;,&quot;productName&quot;:&quot;Apache Cassandra 3.0 Contributor T-Shirt&quot;,&quot;productQty&quot;:1,&quot;productPrice&quot;:15.99}],&quot;orderStatus&quot;:&quot;PENDING&quot;,&quot;orderTimestamp&quot;:&quot;Oct 11, 2022, 5:41:17 PM&quot;,&quot;orderSubtotal&quot;:60.98,&quot;orderShippingHandling&quot;:4,&quot;orderTax&quot;:3.05,&quot;orderTotal&quot;:68.03,&quot;shippingAddress&quot;:{&quot;street&quot;:&quot;123 Limon Gala Rd.&quot;,&quot;city&quot;:&quot;Maple Grove&quot;,&quot;stateProvince&quot;:&quot;Minnesota&quot;,&quot;postalCode&quot;:&quot;55369&quot;,&quot;country&quot;:&quot;United States&quot;}}
Pushed order e8ecd3b0-498b-11ed-b5a7-fbd1f5143654 to ecommerce-aaron/default/picked-orders
</code></pre>
<p><a href="#-table-of-contents" target="_blank">🏠 Back to Table of Contents</a></p>
<h1><a class="anchor" aria-hidden="true" id="done"> </a>Done?</h1>
<p>Congratulations: you made it to the end of today's workshop. You will notice that the application is still incomplete as we're evolving it. More building to follow!!!</p>
<p><img src="https://github.com/datastaxdevs/workshop-ecommerce-app/raw/master/data/img/build-an-ecommerce-app.png" alt="Badge" /></p>
<p><strong>... and see you at our next workshop!</strong></p>
<blockquote>
<p>Sincerely yours, The DataStax Developers</p>
</blockquote>
