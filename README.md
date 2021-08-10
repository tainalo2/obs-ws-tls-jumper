# OBS WS TLS JUMPER
Control OBS from a server with TLS encryption with a simple webpage.

# Summary
  - Prerequesites
  - Technical explanation
  - Installation
    - Nodered import
    - OBS Docking
  - Test
  - Credit

# Prerequesites
  - A nodered server (free low code GUI for NodeJS server) https://nodered.org/
  - A TLS/SSL encryption on your nodered server (you can see my method here : https://github.com/tainalo2/reverse-proxy-with-auto-SSL-certificate-distribution-TRAEFIK-DOCKER-COMPOSE-OVH-LET-S-ENCRYPT- )
  - OBS with obs-websocket plugin : https://github.com/Palakis/obs-websocket

# Technical explanation
OBS Websocket does not suport WSS (WS with encryption). It's dangerous to have communication with OBS out of your network without encryption and certainly with port-forwarding on your router. Imagin a random hacker get control on your OBS !
So, we will create a webpage that will connect to server with encryption, and a localhost ws to OBS.
And we will dock this webpage in OBS, so it will transfer secure communication from server to OBS by encrypting connections out from your local network to the server.

# Installation
  - Nodered import
   - Copy the content of the git file : "nodered_flow.json"
   - In nodered dashboard go to options and "Import"
   - Paste the file content and click "Import"
  - OBS Docking
   - In OBS go to "Display" > "Docks" > "personal internet docks..." > create a new dock with URL : https://YOUR_NODERED_SERVER/obs-jumper
   - Let this dock open everytime
  - Test
    - in your Node-red server, modify node "Set scene" by replacing "scene name" parameter by one of your scene name
    - Deploy, open node "TEST" and click "inject now" (only since node red 2.0)
    - If it's work your OBS have transit to the scene you entered

# Credit
Create by tainalo2 : french streamer on twitch every week day from 07H to 09H (Paris hours)
All my links here : https://linktr.ee/tainalo2
