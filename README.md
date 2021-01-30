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
<ol>
  <li>In the Ansible Playbook i.e., <b>main.yml</b>, the concept of <b>notify-handlers</b> is used for making HTTPD restart service <b>idempotent</b> i.e., as soon as any changes is detected in the HTTPD configuration file , the task specified in the handler executes and thereby HTTPD <b>restarts</b>.</li>
  <li>Some additional functionalities includes allowance of HTTPD port number specified through the Firewall, using the <b>firewalld</b> module in Ansible. Also, <b>Document Root</b> and <b>Port Number</b> could be modified as per requirement.</li>
  <li>In the Variable File i.e., <b>vars.yml</b>, tha value of <b>Mount Directory</b>, <b>Document Root</b> and <b>HTTPD Port Number</b> is specified to make the playbook more dynamic.</li>
  <li><b>Template file</b> or <b>Jinja2</b> template i.e., <b>localconf.conf.j2</b> is created for HTTPD's configuration file.</li>
  <li>Test Page is created and could be modified as per requirement.</li> 
  <li>It should be noted that if the output of "<b>getenforce</b>" command is <b>Enforcing</b>, it would prevent the service restart due to any change, thereby it is advisable to use "<b>setenforce 0</b>" to change the output to <b>Permissive</b>.</li>
</ol><br>

<h3>Execution & Output</h3>
<ul>
  <li><b>Case I</b> : No changes in the <b>HTTPD's configuration file</b></li><br>
  
  ![Execution_Case1](https://cdn-images-1.medium.com/max/1000/1*826PZ1ixDwIePlYusi_y2A.gif)<br>
  
  ![Output_Case1](https://cdn-images-1.medium.com/max/1000/1*9akO8xHjRvhbPCK-PraxNQ.png)<br><br>
  
  <li><b>Case II</b> : Change in <b>HTTPD's configuration file</b> i.e., Port Number is changed from <b>8080</b> to <b>8081</b></li><br>
  
  ![Execution_Case2](https://cdn-images-1.medium.com/max/1000/1*pXyd69YXd7CHbg0N_K8ydw.gif)<br>
  
  ![Output_Case2](https://cdn-images-1.medium.com/max/1000/1*_8hI7ZKv5w2BtdlY_sye4A.png)<br>
  
</ul><br>

<h2>Thank You :smiley:<h2>
 <h3>LinkedIn Profile</h3>
 https://www.linkedin.com/in/satyam-singh-95a266182
