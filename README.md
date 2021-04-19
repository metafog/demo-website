# demo-website
Run a Webserver with a static dummy website on Planetr

## Docker usage on local machine 
```
docker run -p 9001:3000 -d planetrio/demo-website
```
Visit http://localhost:9001/

## Deploy and run the same docker image on Planetr decentralized cloud

[Install and run](https://planetr.io/getstarted.html) the Planetr gateway node

Create and run a decentralized compute unit (DCU) on Planetr network

```
$ planetr dcu-run -p 9001:3000 planetrio/demo-website g.micro
INSTANCE ID STATUS TYPE IMAGE NAME PORTS CREATED AT
c1tafjn2hraq06kud0bg Pending g.micro planetrio/demo-website 9001:3000 2021-04-17T14:48:06.568676+05:30
```

Please wait for the status to become 'Running'

```
$ planetr dcu-ps
INSTANCE ID STATUS TYPE IMAGE NAME PORTS CREATED AT
c1tafjn2hraq06kud0bg Running g.micro planetrio/demo-website 9001:3000 2021-04-17T14:48:06.568676+05:30
```

Now visit https://localhost:9001/ in a browser to access the demo website which is served by the docker image running in a remote node

Delete the DCU.
```
$ planetr dcu-rm c1tafjn2hraq06kud0bg
INSTANCE ID STATUS TYPE IMAGE NAME PORTS CREATED AT
c1tafjn2hraq06kud0bg Deleting g.micro planetrio/demo-website 9001:3000 2021-04-17T14:48:06.568676+05:30
```

Check status again.

```
$ planetr dcu-ps
INSTANCE ID STATUS TYPE IMAGE NAME PORTS CREATED AT
```
