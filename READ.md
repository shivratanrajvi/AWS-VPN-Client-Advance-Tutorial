# AWS VPN Client - Create Directory Service

- Step 1 - Create Directory Service (authentication for VPN users) <= `YOU ARE HERE`
- Step 2 - Certificates
- Step 3 - Create VPN Endpoint
- Step 4 - Configure VPN Endpoint & Associations
- Step 5 - Download, install and test VPN Client
- Step 6 - Cleanup

# Create a simple AD instance

- Type `Directory Service` into the top searchbox and open the directory services console in a new tab.  
Or use directly open via https://console.aws.amazon.com/directoryservicev2/identity?region=us-east-1#!/directories  
- Click `Set up Directory`  
- Select `Simple AD` and click `Next`
- Choose `Small` (this is a demo, for larger deployments you might pick large, or chose alternative methods of authentication)
- Pick a `Directory DNS Name`, i'll use `corp.animals4life.org`  
- Pick a `Directory NetBIOS name`, i'll use `CORP`  
- Choose an `Administrator password`, it will need to be strong enough to meet the complexity requirements.  
- Enter the same password again in the `Confirm Password` box  
- for `Directory description - Optional` put `Directory Service for AWS Client VPN Demo`  
- Click `Next`  
- Under VPC click the dropdown and pick `A4L-VPC`  
- Under `Subnets` ideally pick `A4L-SN-PRIV-A` and `A4L-SN-PRIV-B` (but if one of those isn't available, just pick 2 of the PRIV subnets)  
- Click `Next`
- Click `Create Directory`

The directory will start provisioning, it will need to complete and move into the `Active` state before continuing to step 2

`END OF STEP1`
