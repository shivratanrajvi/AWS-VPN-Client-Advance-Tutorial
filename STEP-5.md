- Step 1 - Create Directory Service (authentication for VPN users) 
- Step 2 - Certificates 
- Step 3 - Create VPN Endpoint 
- Step 4 - Configure VPN Endpoint & Associations 
- Step 5 - Download, install and test VPN Client <= `YOU ARE HERE`
- Step 6 - Cleanup

**Please make sure the Directory Service created in the previous step is in an `Active` state.**  
**Please make sure you have created and imported the server certificate from step 2 before starting step3** 
**Please make sure the VPN endpoint has been created in the previous step** 
**Please make sure the VPN endpoint has been associated with the A4L VPC in the previous step**

# Download the ClientVPN Application & Config

- From the `Client VPN Endpoints` area of the VPC console, select the `A4L Client VPN` endpoint. 
- Click `Download Client Configuration`, Click `Download` and save the file.  
- Go to https://aws.amazon.com/vpn/client-vpn-download/ and download the client for your operating system
- Install the VPN Application
- Start the application
- Go to manage profiles
- add a profile
- load the profile you downloaded (client configuration) - use `A4L` for Displayname  

# Connect

- Connect to A4L VPN
- enter the `Administrator` username and password you chose in step 1 for the Directory Service
- once connected open a terminal and `ping DIRECTORY_SERVICE_IP_ADDRESS' (you can get this from the DS Console)

Notice it doesn't work ? once more step, and thats authorizations

# Authorize

- From the Client VPN Console https://console.aws.amazon.com/vpc/home?region=us-east-1#ClientVPNEndpoints:sort=status.code select the A4L VPN Endpoint  
- Click the `Authorization` tab and click `Authorize Ingress`  
- For `Destination network to enable` enter `10.16.0.0/16`  
- For `Grant access to` check `Allow access to all users`  
- Click `Add Authorization Rule`
- open a terminal and `ping DIRECTORY_SERVICE_IP_ADDRESS' (you can get this from the DS Console)
- notice how this works? you are now connected.
- Browse to the Private IP Address of `CATWEB` instance using `http` (not https) this also should work.



