# Terraform
This resource creates vnet peering between two azure tenants\subscriptions.

The variables below represent remote (network B) appid that has access to a remote network.
The target (network A) appid will create Azure Enterprize Application from this remote appid and assigne Network Contributor role to the target network.
The remote Enterprise Application (remote appid from tenant B) will be used to create both connections between tenants.
The Network Contributor can be removed once peering created.

  - cross_tenant_client_id  = "xxxxxxxxxx-xxxxxx-xxxxxx-xxxxxx-xxxxxxx"
  - cross_tenant_client_secret = "werwerwffwefwefwefwefwefwefwef="


