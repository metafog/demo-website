<div align="center">
<img src="https://planetr.io/img/logo-github.png"></img>
</div>

# Planetr Demo: demo-website
Run a Webserver with a dummy website on Planetr decentralised cloud.

## Install and run Planetr Gateway on your computer

Follow the [Get Started](https://planetr.io/getstarted.html) to install and run the Planetr gateway node. This can be done on your laptop, desktop or any cloud machine.

## Deploy and run the demo docker image on Planetr decentralized cloud

Ensure that planetr gateway is running on your computer. 

```
$ planetr dcu-ps
```

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
## Docker Build (If in case)
```
docker build -t demo-website .
```
