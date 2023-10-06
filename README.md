# Add Custom Logo for Keeper Connection Manager
## Simple Logo Branding Example

<sub>This is a fork of https://github.com/Keeper-Security/kcm-branding/tree/main</sub>

<sub>(The steps below are for docker installations of KCM)</sub>

How to add your logo to KCM:
1. Download the zip file of this repository and extract everything to a folder.
2. Put your logo file as /resources/images/logo.png
3. Open /translations/en.json and put your text for the title of the webpage in place of "Custom Title"
4. (Optional) Put your favicon icons in /resources/images/ as small.png and large.png
5. From inside the folder, select all of the folders and files and create a new zip file.
6. Make sure that you are viewing file extensions, and change your zip file name and extension to kcm-branding.jar
7. Transfer the kcm-branding.jar file to your KCM server into /etc/kcm-setup/
8. In your docker-compose.yml guacamole section, under environment add USE_DEFAULT_BRANDING: "N" and in volumes right below that add the following line:
   
   &nbsp;-&nbsp;"/etc/kcm-setup/kcm-branding.jar:/etc/guacamole/extensions/kcm-branding.jar:ro"

10. Run the command sudo ./kcm-setup stop (required)
11. Run the command sudo ./kcm-setup upgrade and when prompted press Y for yes.

Complete! Now when you refresh KCM in your browser, you should see your logo on the KCM web page. To refresh the favicons press Ctrl/Cmd + F5 for a hard reload.

Additional Information:

This repo contains an example of customizing the user interface of the Keeper Connection Manager product.

This directory structure provides an example of how to apply custom branding
and HTML extension to the Keeper Connection Manager web application. This makes use
of the guac-manifest.json file to specify the resources that are being provided,
and provides examples of changing colors, fonts, and the login screen logo for
the application.

Detailed documentation is available at the link below:

https://docs.keeper.io/keeper-connection-manager/advanced-configuration/custom-branding
