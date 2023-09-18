# Custom Logo for Keeper Connection Manager
## Simple Custom Branding Example

<sub>This is a fork of https://github.com/Keeper-Security/kcm-branding/tree/main</sub>

<sub>(The steps below are for docker installations of KCM)</sub>

How to add my logo to KCM:
1. Download the zip file of this repository and extract it to a folder.
2. Put your logo file as /resources/images/logo.png
3. Open /translations/en.json and put your text for the title of the webpage (browser tab) in place of "Custom Title"
4. (Optional) Put your favicon icons in /resources/images/ as small.png and large.png
5. Select all of the folders and files and compress them into a zip file (add to archive).
6. Make sure that view > file extensions is on, and change your zip file name and extension to kcm-branding.jar
7. Transfer the kcm-branding.jar file to your KCM server into /etc/kcm-setup/
8. In your docker-compose.yml guacamole section, under environment add USE_DEFAULT_BRANDING: "N" and in volumes right below that add the following line
   - "/etc/kcm-setup/kcm-branding.jar:/etc/guacamole/extensions/kcm-branding.jar:ro"
10. ./kcm-setup stop (required)
11. ./kcm-setup upgrade
Now you should see your logo on the KCM web page.

This repo contains an example of customizing the user interface of the Keeper Connection Manager product.

This directory structure provides an example of how to apply custom branding
and HTML extension to the Keeper Connection Manager web application. This makes use
of the guac-manifest.json file to specify the resources that are being provided,
and provides examples of changing colors, fonts, and the login screen logo for
the application.

Detailed documentation is available at the link below:

https://docs.keeper.io/keeper-connection-manager/advanced-configuration/custom-branding
