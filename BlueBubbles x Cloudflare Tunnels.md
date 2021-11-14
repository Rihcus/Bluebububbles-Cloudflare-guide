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

## Method 2 Setup Cloudflare and Bluebubbles with a domain (this part is work in progress.....)

Pros:

- Static url and no need to update dynamic dns in bluebubbles server
- Auto start at boot
- You can configure a custom landing page to block unwanted connections to your server (in addition to the default one in bb)

Cons:

- You need a domain to link to cloudflare (subdomain services like duckpins and noip won't work)
- Setup is a tad bit more complicated



### Steps:

***Follow the steps in method 1 as they installation will be used in method 2***

#### Linking a domain to cloudflare
1. Sign up for a cloudflare account at https://dash.cloudflare.com/sign-up
2. Add a site on the portal ![image](https://user-images.githubusercontent.com/30292597/141693392-96d2261d-a584-4253-83d2-e54e0b7a254c.png)
3. Enter your domain name (ex: example.com do not use a subdomain ex: imessage.example.com) ![image](https://user-images.githubusercontent.com/30292597/141693431-a52e9e6c-b237-4426-8a57-058b332b4a6e.png)
4. Click the free plan and click continue ![image](https://user-images.githubusercontent.com/30292597/141693453-8bf7d912-a4b3-44fc-8e2b-0d86f4072323.png)
5. If you are using the domain for any other websites copy the records bellow (if your just using the domain for bb you can skip this part) ![image](https://user-images.githubusercontent.com/30292597/141693551-3e8ac824-0470-451b-bf0f-df5ea47cf85f.png)
6. Configure your domains name servers to cloudflare (example for namecheap but works with other registrars like name.com godady, etc) ![image](https://user-images.githubusercontent.com/30292597/141693587-a98f9483-3652-4a03-9bb8-1a0cf3bbf3c5.png)
7. Wait for cloudflare to validate your domain



