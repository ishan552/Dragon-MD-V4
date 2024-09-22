## Deploy on VPS or PC.
- You need to Install git,ffmpeg,curl,nodejs,yarn with pm2 
   1. Install git ffmpeg curl 
      ```
       sudo apt -y update &&  sudo apt -y upgrade 
       sudo apt -y install git ffmpeg curl
      ```
   2. Install nodejs 
      ```
      sudo apt -y remove nodejs
      curl -fsSl https://deb.nodesource.com/setup_lts.x | sudo bash - && sudo apt -y install nodejs
      ```

   3. Install yarn
      ```
      curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add - 
      echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
      sudo apt -y update && sudo apt -y install yarn
      ```

   4. Install pm2
      ```
      sudo yarn global add pm2
      ```

   5. Clone Repo and install required packages
      ```
      git clone https://github.com/SamPandey001/Secktor-Md
      cd Secktor-Md
      yarn install --network-concurrency 1
      ```

   6. Create an env file for ENV. 
      ```
      touch config.env
      nano config.env
      ```
      copy paste lines below.

      ```
      OWNER_NUMBER="94715922193"
      MONGODB_URI="mongodb://ulsb6hxfew3xlguryqlc:nu5Eeqd7FrTXcJGBl3j@by4znukyat7lyrwcthpb-mongodb.services.clever-cloud.com:2153/by4znukyat7lyrwcthpb"
      SESSION_ID = "DragonMD;;;eyJub2lzZUtleSI6eyJwcml2YXRlIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiZ0xxKzd4VUhXcFQ4S1ZRci9iNFpiUkZveVVzVGRmRDZBNUF4SkczQzhGcz0ifSwicHVibGljIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiaDhUNXl4T05tdVhvbWdTYnZoRVhxL2NrNWcrZ1owQ0hUa3ZMVWJleGFCUT0ifX0sInNpZ25lZElkZW50aXR5S2V5Ijp7InByaXZhdGUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJxTW9VUkNsNEpMbE5RZW43WHVBMmJ2MzVDdHZvTytJSEJtbzFXTVoyaGxJPSJ9LCJwdWJsaWMiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJKY1U0MHVoSGZld0Fyd3h5Y3l2RTErZldaS3czR1dWbXRLT0tORVkxdmpnPSJ9fSwic2lnbmVkUHJlS2V5Ijp7ImtleVBhaXIiOnsicHJpdmF0ZSI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6IjZPWjRydVhpL3J5djBZWjF4WjhaOWF5WklRS1BJUVBEOTJ5ZVpHdnZUV289In0sInB1YmxpYyI6eyJ0eXBlIjoiQnVmZmVyIiwiZGF0YSI6Ii9aNzgyeGZPWi9vNFlubGhmMm5hcmQrWUhETWc5VzlWSkJubk5BL0djMzQ9In19LCJzaWduYXR1cmUiOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJxQXhKeU9XYTNYQnJqb3VUVmJtT0tNaHE5Yjcxb2RzZmVTQ1VCTURHdCsrSktEQ205Z0NpRUo0TW8zYmgyT29TeXNsN2hWc2M1L09vYVlPSVByZkdqdz09In0sImtleUlkIjoxfSwicmVnaXN0cmF0aW9uSWQiOjExMywiYWR2U2VjcmV0S2V5IjoiVXFCNm5OdFJnN2I1MHkydGttdGhCOEJueHo3ZWhoeDRtQkM3dktsZSthYz0iLCJwcm9jZXNzZWRIaXN0b3J5TWVzc2FnZXMiOltdLCJuZXh0UHJlS2V5SWQiOjMxLCJmaXJzdFVudXBsb2FkZWRQcmVLZXlJZCI6MzEsImFjY291bnRTeW5jQ291bnRlciI6MCwiYWNjb3VudFNldHRpbmdzIjp7InVuYXJjaGl2ZUNoYXRzIjpmYWxzZX0sImRldmljZUlkIjoiQml4cjNFMlhUZ0daWWQtb3A3VG5IUSIsInBob25lSWQiOiIzNWFhYzFiYy04YzgyLTRkZmUtYWI5Zi1lNGExNmI4YmQ4OTgiLCJpZGVudGl0eUlkIjp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiR2FXL2pDbzdiV1Q5TTREYnJzQjU4MHdvOWFBPSJ9LCJyZWdpc3RlcmVkIjpmYWxzZSwiYmFja3VwVG9rZW4iOnsidHlwZSI6IkJ1ZmZlciIsImRhdGEiOiJBcXpiSVhTdkgxbWxPNUcrRFNZQ2tPV3g4QjA9In0sInJlZ2lzdHJhdGlvbiI6e30sImFjY291bnQiOnsiZGV0YWlscyI6IkNKR0Fzc01DRU9mUXZyY0dHQU1nQUNnQSIsImFjY291bnRTaWduYXR1cmVLZXkiOiJVc0xNMHFNQTdsQ0R1V2lVVUIrL29yUy84YlhoUXBVbHJnd0huQzRNSVZBPSIsImFjY291bnRTaWduYXR1cmUiOiJvUTMwWjBxUlVkY0cvWEtnR0lSTTNUdUpEaHE0aStLU2RPZXR5a2tDYjNsYkRoM3hOSzdHNkpDb1NHMlVjU2dJa1pzSHVpNzQ4bWFwclk1TTZoWnFBUT09IiwiZGV2aWNlU2lnbmF0dXJlIjoiaEdyZEg1Mm1sL2lSOGRUWU9SNXJTbEt2NEQrZ25rcHFZaHB0bGlESzd4bEJhdnRHS0VRcGhsK1ZWcDZwYWlDSVNxUHNPWk9CRVpyTjRHWm5DTFhtZ2c9PSJ9LCJtZSI6eyJpZCI6Ijk0NzE1OTIyMTkzOjQyQHMud2hhdHNhcHAubmV0IiwibmFtZSI6IuqngcuH8J2ZvPCdmbDhtYjhtZjPic6x6qeC4peBIn0sInNpZ25hbElkZW50aXRpZXMiOlt7ImlkZW50aWZpZXIiOnsibmFtZSI6Ijk0NzE1OTIyMTkzOjQyQHMud2hhdHNhcHAubmV0IiwiZGV2aWNlSWQiOjB9LCJpZGVudGlmaWVyS2V5Ijp7InR5cGUiOiJCdWZmZXIiLCJkYXRhIjoiQlZMQ3pOS2pBTzVRZzdsb2xGQWZ2Nkswdi9HMTRVS1ZKYTRNQjV3dURDRlEifX1dLCJwbGF0Zm9ybSI6InNtYmEiLCJsYXN0QWNjb3VudFN5bmNUaW1lc3RhbXAiOjE3MjY5ODIyNTJ9"
      THUMB_IMAGE = "https://raw.githubusercontent.com/SecktorBot/Brandimages/main/logos/SocialLogo%201.png"
      port = 5000
      email = "sam@secktor.live"
      global_url = "instagram.com"
      OWNER_NAME = "SamPandey001"
      AUTO_REACTION = false
      FAKE_COUNTRY_CODE = 92
      READ_MESSAGE = false
      PREFIX = .
      WARN_COUNT = 3
      DISABLE_PM = false
      ANTI_BAD_WORD = "fuck"
      LEVEL_UP_MESSAGE= true
      WELCOME_MESSAGE =  "*Hi,* @user \n*Welcome in* @gname \n*Member count* : @count th"
      THEME= SECKTOR
      WORKTYPE = public
      PACK_INFO = "Sam;Pandey"
      ANTILINK_VALUES = "chat.whatsapp.com"
      
      ```
      ctrl + o and ctrl + x, To save and exit

   7. start and stop bot

      To start bot ``` npm start ```,
      To stop bot ``` npm stop ```
