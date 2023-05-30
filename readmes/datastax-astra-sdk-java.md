<h1><a class="anchor" aria-hidden="true" id="astra-software-development-kit"> </a>Astra Software Development Kit</h1>
<p><a href="http://www.apache.org/licenses/LICENSE-2.0" target="_blank"><img src="https://img.shields.io/hexpm/l/plug.svg" alt="License Apache2" /></a><br />
<a href="https://maven-badges.herokuapp.com/maven-central/com.datastax.astra/astra-sdk/" target="_blank"><img src="https://maven-badges.herokuapp.com/maven-central/com.datastax.astra/astra-sdk/badge.svg" alt="Maven Central" /></a></p>
<h2><a class="anchor" aria-hidden="true" id="overview"> </a>Overview</h2>
<p>This SDK <em>(Software Development Kit)</em> makes it easy to call Stargate and/or Astra services using idiomatic Java APIs.</p>
<ul>
<li>
<p><strong>The Stargate SDK</strong> works with both Stargate standalone installations and Stargate deployed in Astra. With standalone Stargate deployments you will initialize the framework with the class <code>StargateClient</code> and provide a list of nodes (IP). To start locally please follow <a href="https://github.com/datastax/astra-sdk-java/wiki/Stargate-SDK-Quickstart" target="_blank">Stargate SDK quickstart</a> guide. The nodes will run in Docker.</p>
</li>
<li>
<p><strong>The Astra SDK</strong> reuses the previous library and setup the connection to work with AstraDB cloud-based service. You work with the class <code>AstraClient</code> (that configure <code>StargateClient</code> for you). As you can see on the figure below the <code>AstraClient</code> handles not only Stargate Apis but also Astra Devops Api and Apache Pulsar. To get started follow the <a href="https://github.com/datastax/astra-sdk-java/wiki/Astra-SDK-Quickstart" target="_blank">Astra SDK quickstart</a> guide.</p>
</li>
<li>
<p><strong>The Astra Spring Boot Starter</strong>: Imported in a Spring Boot application, it configures both <code>Astra SDK</code> and <code>Spring Data Cassandra</code> to work with AstraDB. Configuration is read in <code>application.yaml</code>. The starter will initialize any beans you would need (<code>AstraClient</code>, <code>CqlSession</code>, <code>StargateClient</code>. To get started follow the <a href="https://github.com/datastax/astra-sdk-java/wiki/Spring-Boot-Starter-Quickstart" target="_blank">Astra Spring Boot Starter QuickStart</a> guide.</p>
</li>
</ul>
<h2><a class="anchor" aria-hidden="true" id="what-s-next"> </a>What's NEXT ?</h2>
<ol>
<li><a href="https://github.com/datastax/astra-sdk-java/wiki/Stargate-SDK-Quickstart" target="_blank">QuickStart for Stargate</a></li>
<li><a href="https://github.com/datastax/astra-sdk-java/wiki/Astra-SDK-Quickstart" target="_blank">QuickStart for Astra</a></li>
<li><a href="https://github.com/datastax/astra-sdk-java/wiki/Spring-Boot-Starter-Quickstart" target="_blank">QuickStart for Astra Spring Boot Starter</a></li>
</ol>
