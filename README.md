# skyminer-info

## 02-06-2018

- The whitelist is on-going, if you are in the process of building a miner do so ASAP to get a better spot in the queue for the whitelist.
- Whitelist participants will be contacted via the email you submitted in your application, the emails will be sent next week with a small delay between official miners and DIY. All submitted applications will receive responses, check your emails regularly. 
- Keep your nodes up and running if you want to be eligible for rewards, you need 75% uptime in June.
- If your public keys changed because you encountered issues then submit another application with your updated keys, your application is identified by your submitted email address and your earliest application counts, you don't give up your spot if you submit another application. 
- Updating personal information in the application will be possible ~ a week after you got the emails. 
- Currently, it's not possible to see your uptime statistics, this feature might be introduced later on.
- The uptime of all submitted public keys is added together and will result in your monthly uptime. Make sure to check regularly if your nodes are live and restart them if necessary. Restarting the miner will not change your public keys!
- Please save your submitted public keys, this will make things easier for us because in case of a reflash you don't have to update your public keys, you can just update the file on the pi with your stored public keys. The file that stores your public keys is called keys.json and is located in .skywire/node/keys.json (in the official images the .skywire folder is in /usr/local/.skywire/go/bin/.skywire/node/keys.json, if it's not in there check your home directory ~/.skywire/node/keys.json)
- A couple people reported that their node app's crashed, we are aware of this issue. Until there is a fix for this you are advised to restart the node with a cronjob every 12/24h to make sure you get the demanded uptime of 75%. Example for the official images, add this to crontab -e '0 0,12 * * * /etc/rebuild.sh restart' would restart the node process every 12h at midnight and noon.
- Last but not least a couple explanations about the discussion about exit nodes. As of now the only app in the Skywire network is the node app (of which you can see the app key in your manager). The node app autostarts if you kill it your node becomes useless for the network and your uptime won't be measured. The connection to the discovery is currently being established by this node app, if you turn it down there is no way for us to measure your uptime; don't get fooled if you want to validate this by checking discovery.skycoin.net:8001, there is a cache that will mimic a live connection. An off/on switch for the node app is WIP and i personally hope that it will be ready very soon, however, there is no ETA for this. As part of the on/off switch comes the separation of the connection to the discovery server from the node app. This will give you the option to turn off the exit node. Until then you have the option to 
- setup VPN tunneling for the traffic of the miner using a third-party VPN 
- restrict website access by changing the DNS service that's used by the Skyminer to prevent people accessing illegal content
- same as above but configured in the router with DNSMasq, OpenWRT required
- setup a proxy server on 1 pi that whitelists website access and blacklists all other by default (squid for example). You'd      need to set this pi as the only default gateway for the other nodes.
