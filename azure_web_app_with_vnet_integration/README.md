# Terraform
This resource creates azure:
- Network
- Network gateway with P2P configuration:
-- web app certificate;
-- p2p configuration
- App service plan
- Web app:
-- network integration
-- GoDaddy CNAME and SSL binding
-- IP restrinction

The Azure network gateway module creates a gateway, app service plan, and web app. The PowerShell script exports newly created by web app certificate (it happens automatically every time once you create first web app, i didn't get chance to test this with self-created certificate).
Script add the certificate to azure gateway, the additional resource produces output with VPN package url that used by web app script, that performs vnet integration.




