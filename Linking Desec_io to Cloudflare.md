# Linking desec.io domain to cloudflare

desec.io is a free DNS hosting service (similar to duckdns and noip) which provides free subdomains

### Creating a desec.io domain:

1. create an account at https://desec.io/domains
2. click the plus button on the top right corner and create a domain using the prefix [your domain name here no brackets].dedyn.io
Screen Shot 2022-08-10 at 7.19.29 PM![image](https://user-images.githubusercontent.com/30292597/184039406-1fd9a686-bc33-4327-ad68-936f2a5fe922.png)
3. Next toggle on show advanced settings and click the domain published date
Screen Shot 2022-08-10 at 7.22.12 PM![image](https://user-images.githubusercontent.com/30292597/184039790-2153ddd1-2b58-40d4-8cc4-e07cf92a72e5.png)
4. Change the host names to ivy.ns.cloudflare.com. and gordon.ns.cloudflare.com. (don't forget to add the period)
Screen Shot 2022-08-10 at 7.25.34 PM![image](https://user-images.githubusercontent.com/30292597/184039986-09a551d8-cc12-4c36-aa59-53a76ee78cbc.png)

#### Linking a domain to cloudflare
1. Sign up for a cloudflare account at https://dash.cloudflare.com/sign-up
2. Add a site on the portal ![image](https://user-images.githubusercontent.com/30292597/141693392-96d2261d-a584-4253-83d2-e54e0b7a254c.png)
3. Enter your domain name (ex: example.com do not use a subdomain ex: imessage.example.com) ![image](https://user-images.githubusercontent.com/30292597/141693431-a52e9e6c-b237-4426-8a57-058b332b4a6e.png)
4. Click the free plan and click continue ![image](https://user-images.githubusercontent.com/30292597/141693453-8bf7d912-a4b3-44fc-8e2b-0d86f4072323.png)
5. If you are using the domain for any other websites copy the records bellow (if your just using the domain for bb you can skip this part) ![image](https://user-images.githubusercontent.com/30292597/141693551-3e8ac824-0470-451b-bf0f-df5ea47cf85f.png)
6. Configure your domains name servers to cloudflare (example for namecheap but works with other registrars like name.com godady, etc) ![image](https://user-images.githubusercontent.com/30292597/141693587-a98f9483-3652-4a03-9bb8-1a0cf3bbf3c5.png)
7. Wait for cloudflare to validate your domain
