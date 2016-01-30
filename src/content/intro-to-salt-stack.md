---
Title: Introduction to Salt Stack
Date: 2010-12-03 10:20
Modified: 2010-12-05 19:30
Category: Python
Tags: python,intro
Slug: intro-to-salt
Authors: Ramaseshan
Summary: SaltStack is a configuration state management tool, for managing large scale infrasctructure.
Template: revealjs
Theme: simple
Intro: name
Contact: contact
Transition: concave
---

    ## Our Goal
    - Understand Some Server Challenges Facing Teams
    - Basic introduction to Salt about what it does
    - Live demo on how it can help solve common problems
    - Get you excited to go try out & learn more about salt

    ----

    ## Disclaimer

    - Welcome to the aggravating world of Murphy's Law.
    - Not the web guy. Mostly on systems and storage.
    - Not in war with, Ansible or Chef or Puppet etc.
    - SaltStack is my first configuration management tool, and never had a need to explore other frameworks.


    ====

    ## Why do we need an "Infrastructure Management Tool" ?

    ----

    <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/happy-dev.gif"/></div>
    <h3>You're a Happy Developer</h3>

    ----

    <div style="padding:0 0 50px -30px;"><img src="theme/img/salt/gifs/team.gif"/></div>
    <h3>You're Part of a <br/>Small Team of Devs</h3>

    ----

    <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/new-website.gif"/></div>
    <h3>You Have a New Website</h3>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div><i class="fa fa-cloud" style="font-size:50px;"></i></div>
    </div>
    <h3>On a small cloud server</h3>

    ----

        <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/traffic.gif"/></div>
        <h3>You Start Getting Lots of Users ...</h3>

    ----

    <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/fire.gif" style="width:490px; height:366px;"/></div>
    <h3>... and you need to quickly scale.</h3>

    ----

        <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/boss.gif" style="min-width:500px;"/></div>
        <h3>You ask your boss to hire a sys admin.</h3>
        <h2 class="fragment" style="">"We don't have the budget!"</h2>

    ----

        <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/who-is-devop.gif"/></div>
        <h3>So your team decides to ask:</h3>
        <h4 class="serif">who can run operations?</h4>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
        </div>
    </div>
    <h3>... and you start deploying more servers ...</h3>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
        </div>
    </div>
    <h3>... and some more ...</h3>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
        </div>
    </div>
    <h3>... and maybe just a few more ...</h3>

    ----

    <h2>Until it is a giant mess!</h2>

    ----

    <div style="padding:0 0 50px 0;"><img src="theme/img/salt/gifs/angry-panda.gif" style="min-width:500px;"/></div>
    <h3>Scenario: John gets Fired</h3>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px; color:#f08080;"></i>
        </div>
    </div>
    <h2>You have a dozen servers</h2><h3>He has SSH keys on half of them.</h3>

    ----

    <div style="padding:0 0 50px 0; font-size: 80px;">
        <div>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i><br/>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
            <i class="fa fa-cloud" style="font-size:50px;"></i>
        </div>
    </div>
    <h3>How are you going to ensure you've </h3><h3> revoked his access everywhere?</h3>

    ====

    <h1>The Problem:</h1>
    <h2>Ad-Hoc Server Management</h2>

    ----

    <h2><i class="fa fa-cloud"></i> The Cloud</h2>
    <p class="serif">Problem: It's Easy!</p>
    <ul>
        <li class="fragment">Doesn't Require a Sys Admin</li>
        <li class="fragment">Simple to deploy many servers</li>
        <li class="fragment">But complex to solve large scaling issues</li>
        <li class="fragment">Long-term management requires<br /> fore-thought & planning</li>
    </ul>

    ----

    <h2><i class="fa fa-user"></i> The Developer</h2>
    <p class="serif">Problem: Lack of Ops Experience</p>
    <ul>
        <li class="fragment">Can relatively easily setup a production environment</li>
        <li class="fragment">Typically doesn't know how to manage many servers long-term</li>
        <li class="fragment">Busy programming, last priority is "sysadmin stuff"</li>
    </ul>

    ----

    <h2><i class="fa fa-briefcase"></i> The Business</h2>
    <p class="serif">Problem: Lack of Money</p>
    <ul>
        <li class="fragment">Hard to justify a "Sys Admin"<br />when devs can do "okay" job.</li>
        <li class="fragment">Usually hit scaling problems<br /> before profitability</li>
    </ul>

    ====

        <h1>The Solution:</h1>
        <h2>Developers need to think like Ops</h2>

    ----

        <h2>DevOps</h2>
        <blockquote>We've been putting more dev into ops, but we need to put more ops into dev. Ops is a state of mind.
            <cite>Theo Schlossnagle <br/> CEO, OmniTI</cite>
        </blockquote>

    ----

        <h2>Need to Apply Best Practices</h2>
        <h2>For Server Environments</h2>
        <ul>
            <li>Source Control for Configuration</li>
            <li>Ensure Servers are Configured The Same</li>
            <li>Automate Upgrades, Changes, & new Deployments</li>
        </ul>

    ----

        <h2>Introducing</h2><h2>Configuration Management</h2>
        <h4 class="serif">Programmatic Approach<br/> for Configuring Servers</h4>

    ----

        <h2>What Can Configuration <br/>Management Do?</h2>
        <ul>
            <li>Manage Packages</li>
            <li>Manage Services</li>
            <li>Manage Configuration</li>
            <li>Manage Files</li>
            <li>Manage Users</li>
        </ul>

    ----

        <h2>Popular Tools</h2>
        <ul>
            <li>Puppet</li>
            <li>Chef</li>
            <li>Ansible</li>
        </ul>

    ====

        <h1>So what is salt?</h1>
        <h4 class="serif">and how is it going</h4><h4 class="serif"> to help with my problems?</h4>

    ----

        <h2>What Is Salt</h2>
        <blockquote style="font-size: 24px;">SaltStack takes a new approach to infrastructure management by developing software that is easy enough to get running in minutes, scalable enough to manage tens of thousands of servers, and fast enough to communicate with them in seconds. SaltStack delivers a dynamic infrastructure communication bus used for orchestration, remote execution, configuration management and much more.
            <cite>About SaltStack, SaltStack.org</cite>
        </blockquote>

    ----

        <h2>A Different Approach</h2>
        <p>Salt is a simple system that focuses on two things:</p>
        <ul>
            <li>Scalable, Fast Communication (Flow)</li>
            <li>Quickly get information / data from a server (State)</li>
        </ul>

    ----

        <h2>Salt Basics</h2>
        <ul>
            <li>Minions connect to Master via ZeroMQ</li>
            <li>Minions authenticate with master via AES (pub/priv) keys</li>
            <li>Master can send module commands to minions to execute</li>
            <li>Execution is in parallel</li>
            <li>Modules are just python modules</li>
        </ul>

    ----

        <h2>What does this give us?</h2>
        <ul>
            <li>Extremely Scalable (~10k Minions per Server)</li>
            <li>Great Flexibility (just write a python module for new functionality)</li>
            <li>Simple, Avoids Complexity</li>
            <li>Great Building Blocks for Automation</li>
        </ul>

    ----

        <h2>Built On Top of Salt</h2>
        <ul>
            <li>Configuration Management</li>
            <li>Remote Execution</li>
            <li>VM / Cloud Management</li>
        </ul>

    ----

        <h2>New / Upcoming Functionality</h2>
        <ul>
            <li>Monitoring</li>
        </ul>

    ----

        <h2>100% Open Source</h2>
        <ul>
            <li><em>Everything</em> is open source! Apache License</li>
            <li>No "watered-down" community edition</li>
            <li>8th Most Unique Contributors on GitHub in 2012</li>
            <li>Extremely Open & Friendly Community</li>
        </ul>

    ====  

        <h1>Installing Salt</h1>
        <h3>Its so easy even I can do it</h3>

    ----

        <h2>Basic Salt Setup</h2>
        <div style="padding:0 0 50px 0;"><img class="diagram" src="theme/img/salt/img/diagram-basic.png"/></div>

    ----

    ## Top level components

    - Master
    - Minion
    - States (Top File)
    - Grains
    - Pillar
    - Modules

    ====

    <h2>Setting Up The Master</h2>
    <ul>
      <li>Install salt-master via Salt Bootstrap, Pip, Apt, Yum, Source, etc</li>
      <li>Edit Configuration (i.e. /etc/salt/master)
    </ul>

    ----

    <ul>
      <li>File Roots
      <code><pre>
        file_roots:
        base:
        - /srv/salt
      </pre></code>
      </li>
      <li>Pillar Roots
        <code><pre>
            pillar_roots:
            base:
            - /srv/pillar
      </pre></code>
          </li>
          <li>Restart salt-master (i.e. /etc/init.d/salt-master restart)</li>
    </ul>

    ====

      <h2>Setting Up The Minions</h2>
      <ul>
          <li>Install salt-minion via Salt Bootstrap, Pip, Apt, Yum, Source, etc</li>
          <li>Set FQDN on the server (OR set ID Manually in Config)</li>
          <li>Edit Configuration (i.e. /etc/salt/minion)</li>
          <li>Restart Minion</li>
      </ul>

    ----

    <ul>
      <li>Set Master Server
        <code><pre>
            master: master.saltdemo.com
        </pre></code>
      </li>
      <li>Pillar Roots
          <code><pre>
            pillar_roots:
            base:
            - /srv/pillar
          </pre></code>
      </li>
    </ul>

    ====

    ## Modules :

    Python function with a return statement.Used for one time execution
    - Salt  '*' test.ping
    - Salt '*' cmd.run 'ls'
    - Salt '*' disk.usage
    - salt '*' pkg.install cowsay
    - salt '*' network.interfaces
    - salt '*' saltutil.sync_modules

    ====

    ## Grains

    Grains are static information SaltStack collects about the underlying managed system.
    - Salt '*' grains.ls
    - salt -E 'minion[0-9]' test.ping
    - salt -G 'os:Ubuntu' test.ping
    - salt -C '@os:Fedora and minion* or S@192.168.50.*' test.ping

    ====

    ## Pillars

    Static information stored by the users.
    - Confidential information such as DB username, Password etc
    - /etc/salt/grains
    - Eg :
      <code><pre>
      - devel
      - staging
      </pre></code>
    - salt '*' salttuil.refresh_pillar

    ----

    ## Example

    Top.sls<br/><br/>
    <code> <pre>
      Base:
        'staging':
          staging.sls
    </pre>
    </code>

    ====

    ## States

    - A reusable declaration that configures a specific part of a system.
    <code><pre>
    /srv/salt/top.sls
    install_network_packages:
      pkg.installed:
        - pkgs:
          - rsync
          - lftp
          - curl
    </pre></code>

    - salt '*' state.highstate

    ----

    ## Difference between modules and States

    ====

    ## Lets see it in action.
