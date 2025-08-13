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
 <p>first we will create a gre tunnel. This tunneling protocol doesnt 
 encrypt the trafic but does allow for multicast. The source is the 
 outside interface on R1 and the destination is the outside ip of
 router R3.</p>
<br />
<br />
Create ikev2 proposal<br/>
<img src="images/created ikev2 proposal.PNG" height="80%" width="80%"/>
<p>The proposal sets the perameters for the isakemp tunnel. This tunnel 
 uses asyncronus encryption for a strong connection so we can transport
 the syncronus keys safely.</p>
<br />
<br />
Create keyring<br/>
<img src="images/created ikev2 keyring.PNG"  height="80%" width="80%"/>
<p>the keyring acts like a repository for our authentication methods here we
are using preshared keys.</p>
<br />
<br />
Create ikev2 policy<br/>
<img src="images/created ikev2 policy.PNG" height="80%" width="80%" />
<p>Next we must match the proposal to an ikev2 policy.</p>
<br />
<br />
Create ikev2 profile <br/>
<img src="images/created ikev2 profile.PNG" height="80%" width="80%" />
<P>The ikev2 profile is a list that the tunnel can use for configurations
such as matching addresses for the endpoints authentications methods</P>
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
  Ping pc on other network <br/>
 <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
<br />
<br />
    use command () to check if packets are being encrypted <br/>
  <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
<br />
<br />
  packet capture <br/>
  <img src="images/pings are encasulated in gre tunnel.PNG" height="80%" width="80%" />
<br />
<br />

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
