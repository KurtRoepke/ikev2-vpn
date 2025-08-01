<h1> Ikev2 site to site vpn configuration</h1>

 

<h2>Description</h2>
 In this project i created two autonomous networks symulating a wan then i connected those autonomous networks using an ikev2 vpn. Next i created a transform set to map the configuration to a GRE tunnel.
<br />


<h2></h2>

<h2>Environments and programs used </h2>

- <b>Cisco CML 2.8</b> 

- <b>Cisco cli</b>

- <b>Ubuntu terminal</b>

<h2>Program walk-through:</h2>

<p align="center">
Create Gre tunnel <br/>
<img src= "images/created ger tunnel 1.PNG" height="80%" width="80%"/>
<br />
<br />
Create ikev2 proposal<br/>
<img src="images/created ikev2 proposal.PNG" height="80%" width="80%"/>
<br />
<br />
Create keyring<br/>
<img src="images/created ikev2 keyring.PNG"  height="80%" width="80%"/>
<br />
<br />
Create ikev2 policy<br/>
<img src="images/created ikev2 policy.PNG" height="80%" width="80%" />
<br />
<br />
Create ikev2 profile <br/>
<img src="images/created ikev2 profile.PNG" height="80%" width="80%" />
<br />
<br />
Create transform set<br/>
<img src="images/created transform set.PNG" height="80%" width="80%" />
<br />
<br />
 Create ipsec profile<br/>
 <img src="images/created ipsec profile.PNG" height="80%" width="80%" />
<br />
<br />
 Map ipsec profile to gre tunnel<br/>
 <img src="images/liked ipsec profile to tunnel1.PNG" height="80%" width="80%" />
<br />
<br />
     <br/>
 <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
<br />
<br />
     <br/>
  <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
<br />
<br />
  <img src="images/pings are encasulated in gre tunnel.PNG" height="80%" width="80%" />
<br />
<br />
Observe the wiped disk:  <br/>
<img src=/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
