# BlueBubbles x Cloudflare Tunnels

A guide to set up cloudflare tunnels with bluebubbles from a guy that barley knows how to code :)

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

#### Setting up cloudflare tunnels with your domain 
1. in the terminal type `cloudflared tunnel create <NAME>` replace name to name of your tunnel ex bluebubbles
2. Download the following config.yml template open it text edit (or other text editors) and replace the [username] with the username of your mac server and replace the [tunnel id] with your tunnel id (if your forgot it in the terminal type `cloudflared tunnel list` and it should show up)
https://raw.githubusercontent.com/Rihcus/Bluebububbles-Cloudflare-guide/main/config.yml
3. move the config.yml file to /Users/[username]/.cloudflared 
4. in the terminal type `cloudflared tunnel run <NAME>` and a the tunnel should up and running
5. in bluebubbles settings set the proxy service to dynamic dns and enter your ![image](https://user-images.githubusercontent.com/30292597/141694946-e7fdbcdf-20ca-4263-9fcf-3c7358aa2fa8.png) <img width="889" alt="image" src="https://user-images.githubusercontent.com/30292597/141694988-605f28ed-6a36-4936-86b7-6077b4cf7e8f.png">
6. Try to connect the server using the android, desktop, or web apps to see if it works

#### Setting cloudflare to launch at boot
1. in the terminal type `sudo cloudflared service install`
2. download the `com.cloudflare.cloudflared.plist` template and replace [YOUR TUNNEL ID] to your cloudflare tunnel id without the brakets (if your forgot it in the terminal type `cloudflared tunnel list` and it should show up)
https://raw.githubusercontent.com/Rihcus/Bluebububbles-Cloudflare-guide/main/com.cloudflare.cloudflared.plist
3. copy your modified `com.cloudflare.cloudflared.plist` to /Library/LaunchDaemons if prompted to overwrite click yes
4. type in terminal `sudo launchctl start com.cloudflare.cloudflared` to start the service, cloudflare should auto start at boot now


##### Helpfull resources:
https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/install-and-setup/installation

https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/create-tunnel

https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/configuration/configuration-file

https://developers.cloudflare.com/cloudflare-one/connections/connect-apps/run-tunnel/run-as-service

https://support.apple.com/lv-lv/guide/terminal/apdc6c1077b-5d5d-4d35-9c19-60f2397b2369/mac


