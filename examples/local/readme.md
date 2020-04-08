# How to setup a local instanz of traefik on windows

## Local Domain
**Step 1: generate a development domain**

Add your desired domain to ``C:\Windows\System32\drivers\etc\hosts`` like this:

```
127.0.0.1 localhost
::1 localhost
127.0.0.1 domain.test #your test domain
```

Alternativ if you want to do step and add portmapping use any adress in space 127.x.x.x

```
127.0.0.1 localhost
::1 localhost
127.100.100.100 domain.test #your test domain
```

*Note: your editor has to be started with administrator rights.*

**Step 2 (optional): add portmapping**

This step is optional, but i don`t want to map to port 80 or 443 on my computer. So I will use a free port like 
8080 and 8443.

```
interface portproxy add v4tov4 listenport=80 listenaddress=127.100.100.100 connectport=8080 connectaddress=127.0.0.1
```

Now you can go to your domain.test and your request will be forwarded to localhost:8080.

*Note: your console has to be started with administrator rights.*

**Step 3: Traefik Config**

ToDo

**Step 4 (optional): enable https**

ToDo

# Attribution
windows dns based on this answer: https://stackoverflow.com/a/36646749/10101463