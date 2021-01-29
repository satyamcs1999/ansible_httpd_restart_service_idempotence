__<h1>How to make HTTPD restart service idempotent in nature</h1>__

![Ansible_HTTPD](https://cdn-images-1.medium.com/max/1000/1*J5C5a3-LEKQ927CkClTqLA.jpeg)<br>

<h2> Content </h2>
<h4><ul>
<li><i>About Ansible</i></li>
<li><i>About Apache HTTPD Webserver</i></li> 
<li><i>Project Understanding</i></li> 
</ul></h4><br>

<h2>About Ansible</h2>
<h3>What is Ansible ?</h3>
<i><b>Ansible</b> is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.</i>

<h3>Why use Ansible ?</h3>
<h4><ol>
<li>
  Simple
  <ul>
    <li><i>Human readable automation</i></li>
    <li><i>No special coding skills needed</i></li>
    <li><i>Tasks executed in order</i></li>
    <li><i>Get productive quickly</i></li>
  </ul>
</li><br>
<li>
  Powerful
  <ul>
    <li><i>App deployment</i></li>
    <li><i>Configuration management</i></li>
    <li><i>Workflow orchestration</i></li>
    <li><i>Orchestrate the app lifecycle</i></li>
  </ul>
</li><br>
<li>
  Agentless
  <ul>
    <li><i>Agentless architecture</i></li>
    <li><i>Uses OpenSSH and WinRM</i></li>
    <li><i>No agents to exploit or update</i></li>
    <li><i>Predictable, reliable and secure</i></li>
  </ul>
</li><br>
</ol></h4>
For Ansible Documentation, visit the link mentioned below:<br>
https://docs.ansible.com/

<h2>About Apache HTTPD Webserver</h2>
<ul>
  <li>The <b>Apache HTTP Server</b>, colloquially called <b>Apache</b>, is a free and open-source cross-platform web server software, released under the terms of <b>Apache License 2.0</b>.</li>
  <li>Apache is developed and maintained by an open community of developers under the auspices of the <b>Apache Software Foundation</b>.</li>
  <li>The vast majority of Apache HTTP Server instances run on a Linux distribution, but current versions also run on Microsoft Windows, OpenVMS and a wide variety of Unix-like systems.</li>
</ul>

For Apache HTTPD Documentation, visit the link mentioned below:<br>
https://httpd.apache.org/docs/

<h2>Project Understanding</h2>
<p>The main purpose of this README, as you can understand from the title itself , is to make restart service of HTTPD Webserver idempotent in nature</p>

<p>Let's understand the version of software required</p>
<h3>Versions</h3>
<ul>
  <li><b>HTTPD</b>: 2.4.37</li>
  <li><b>Ansible</b>: 2.9.11</li>
</ul><br>

<h3>Some Important Points To Be Noted:point_left:</h3>


