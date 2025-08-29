  
<h1> Ikev2 site to site vpn configuration</h1>
   
<h2>Description</h2>
  In this project, I created two autonomous networks simulating a WAN, and then I connected those autonomous networks using an IKEv2 VPN. Next, I created a transform set to map the configuration to a GRE tunnel.
<br />

<h2>Environments and programs used </h2>

- <b>Cisco CML 2.8</b> 

- <b>Cisco cli</b>

- <b>Ubuntu terminal</b>

<h2>Program walk-through:</h2>
<p align="center">
Create Gre tunnel <br/>
<img src= "images/created ger tunnel 1.PNG" height="80%" width="80%"/>
  <br />
 First, we will create a GRE tunnel. This tunneling protocol doesn't 
 encrypt the traffic but does allow for multicast. The source is the 
 outside interface on R1, and the destination is the outside IP of
 router R3.<br />
<br />
<br />
Create ikev2 proposal<br/>
<img src="images/created ikev2 proposal.PNG" height="80%" width="80%"/>
  <br />
The proposal sets the parameters for the Isakemp tunnel. This tunnel 
 uses asynchronous encryption for a strong connection, so we can transport
 The synchronous keys safely.br />
<br />
<br />
Create keyring<br/>
<img src="images/created ikev2 keyring.PNG"  height="80%" width="80%"/>
  <br />
The keyring acts like a repository for our authentication methods. Here we
We are using preshared keys.<br />
<br />
<br />
Create ikev2 policy<br/>
<img src="images/created ikev2 policy.PNG" height="80%" width="80%" />
  <br />
Next, we must match the proposal to an IKEv2 policy.<br />
<br />
<br />
Create ikev2 profile <br/>
<img src="images/created ikev2 profile.PNG" height="80%" width="80%" />
  <br />
The IKEv2 profile is a list that the tunnel can use for configurations
such as matching addresses for the endpoints' authentication methods 
And this is where you add the keyring to the configuration.<br />
<br />
<br />
Create transform set<br/>
<img src="images/created transform set.PNG" height="80%" width="80%" />
  <br />
 Next, we will create an IPsec transform set. This contains the security
algorithms that will be used to form the IPSec tunnel.<br />
<br />
<br />
 Create ipsec profile<br/>
 <img src="images/created ipsec profile.PNG" height="80%" width="80%" />
  <br />
 The next step is to create an IPSec profile. This acts as a repository to store
 configurations for the IPsec tunnel and also where we add the transform set.<br />
<br />
<br />
 Map ipsec profile to gre tunnel<br/>
 <img src="images/liked ipsec profile to tunnel1.PNG" height="80%" width="80%" />
  <br />
 Finally, we link the IPsec profile to the GRE tunnel, so you get the security
 of IPsec, but the multicast from the GRE tunnel.<br />
<br />
<br />
  Ping pc on other network <br/>
 <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
  <br />
  text<br />
<br />
<br />
    use command "show crypto ipsec sa | in peer|pkts|ident" to check if packets are being encrypted <br/>
  <img src="images/packets being sent through vpn.PNG" height="80%" width="80%" />
  <br />
  To ensure the vpn is being used use the command "show crypto ipsec sa | in peer|pkts|ident"
  to ensure the packet count is increasing.<br />
<br />
<br />
  packet capture <br/>
  <img src="images/pings are encasulated in gre tunnel.PNG" height="80%" width="80%" />
  <br />
  Here, we can see from a packet capture that the GRE tunnel is being used.<br />
<br />
<br />
  <p/>
<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>

