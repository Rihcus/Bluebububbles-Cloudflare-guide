# BlueBubbles x Cloudflare Tunnels

## Method 1 Setup Cloudflare and Bluebubbles without a domain

Pros:

- Minimal setup required

Cons:

- Like ngrok the url will change per cloudflare tunnel session
- Lack of auto start
- You will need to manually update they dynamic dns url for cloudflare tunnel each time it changes (for now)

### Steps:

1. Install home-brew: https://brew.sh/  
2. Install cloud flared by pasting the following command in the terminal: `brew install cloudflare/cloudflare/cloudflared ` 
3. Run the following command in a terminal `cloudflared tunnel --url localhost:1234 ` 
4. In bluebubbles server settings set the proxy service to dynamic dns and input the url given by Cloudflare in the terminal (something like try Cloudflare) (example:  https://various-bleeding-earnings-lap.trycloudflare.com/) 

## Method 2 Setup Cloudflare and Bluebubbles with a domain

Pros:

- Static url and no need to update dynamic dns in bluebubbles server
- Auto start at boot
- You can configure a custom landing page to block unwanted connections to your server (in addition to the default one in bb)

Cons:

- You need a domain to link to cloudflare (subdomain services like duckpins and noip won't work)
- Setup is a tad bit more complicated



----- Work in progress ------