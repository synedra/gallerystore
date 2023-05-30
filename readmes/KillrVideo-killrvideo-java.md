<h1><a class="anchor" aria-hidden="true" id="killrvideo-java"> </a>KillrVideo Java</h1>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a></p>
<p><a href="https://travis-ci.org/KillrVideo/killrvideo-java" target="_blank"><img src="https://travis-ci.org/KillrVideo/killrvideo-java.svg?branch=master" alt="Build Status" /></a></p>
<p>A reference application for Java developers looking to learn more about using <a href="http://cassandra.apache.org/" target="_blank">Apache Cassandra</a> and<br />
<a href="http://www.datastax.com/products/datastax-enterprise" target="_blank">DataStax Enterprise</a> in their applications and services. Learn more at <a href="https://killrvideo.github.io">Killrvideo</a>.</p>
<h2><a class="anchor" aria-hidden="true" id="the-latest-stable-build-of-killrvideo-java-is-a-href-https-github-com-killrvideo-killrvideo-java-tree-v2-1-0-v2-1-0-a-master-is-experimental-please-use-v2-1-0-if-you-attempting-to-follow-the-instructions-in-the-links-below"> </a>The latest stable build of KillrVideo Java is <a href="https://github.com/KillrVideo/killrvideo-java/tree/v2.1.0" target="_blank">v2.1.0</a>. Master is experimental. Please use v2.1.0 if you attempting to follow the instructions in the links below.</h2>
<h2><a class="anchor" aria-hidden="true" id="building-locally"> </a>Building Locally</h2>
<p><strong>Docker Way</strong></p>
<p><code>docker run -v ${PWD}:/opt/killrvideo-java -w /opt/killrvideo-java maven mvn install -DskipTests=true -Dmaven.javadoc.skip=true -B</code></p>
<p><strong>Maven Way</strong></p>
<p><code>mvn install</code></p>
<h2><a class="anchor" aria-hidden="true" id="running-locally"> </a>Running Locally</h2>
<p>Use these guides to get started running KillrVideo locally on your development machine:</p>
<ul>
<li><a href="https://killrvideo.github.io/getting-started/" target="_blank">Getting Started with KillrVideo</a>: Follow this to setup common dependencies like Docker.</li>
<li><a href="https://killrvideo.github.io/docs/languages/java/" target="_blank">Getting Started with Java</a>: Follow this to get this Java code<br />
running.</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="pull-requests-requests-for-more-examples"> </a>Pull Requests, Requests for More Examples</h2>
<p>This project will continue to evolve along with Cassandra and you can expect that as Cassandra and the DataStax<br />
driver add new features. This sample application will try and provide examples of those.</p>
<p>We will gladly accept any pull requests for bug fixes, new features, etc.  and if you have a request for an example<br />
that you don't see in the code currently, send me a message <a href="https://twitter.com/SonicDMG" target="_blank">@SonicDMG</a> or <a href="https://twitter.com/clunven">@clunven</a> on Twitter or open an issue<br />
<a href="https://github.com/KillrVideo/killrvideo-java/issues" target="_blank">here</a> on GitHub.</p>
<h2><a class="anchor" aria-hidden="true" id="license"> </a>License</h2>
<p>Copyright 2018 David Gilardi, Cedrick Lunven, derived from original work by Duy Hai Doan</p>
<p>Licensed under the Apache License, Version 2.0 (the &quot;License&quot;);<br />
you may not use this file except in compliance with the License.<br />
You may obtain a copy of the License at</p>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank">http://www.apache.org/licenses/LICENSE-2.0</a></p>
<p>Unless required by applicable law or agreed to in writing, software<br />
distributed under the License is distributed on an &quot;AS IS&quot; BASIS,<br />
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.<br />
See the License for the specific language governing permissions and<br />
limitations under the License.</p>
