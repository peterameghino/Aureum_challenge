Azure Infrastructure as Code (IaC) - Hub-and-Spoke Network Topology

Overview

This repository contains Azure Resource Manager (ARM) templates to deploy a hub-and-spoke network architecture on Microsoft Azure as part of Aureum Technologies challenge. The architecture is designed to meet the exercise requirements for a DevOps position interview. It includes the following components:

1. Hub Virtual Network
2. Two Spoke Virtual Networks
3. VNet Peering between Hub and Spokes
4. Azure Firewall in the Hub VNet
5. Private Endpoint
6. Application Gateway with Web Application Firewall (WAF)
7. Storage Accounts for Hosting Static Websites

Description

Hub Virtual Network

- Resource Type: Microsoft.Network/virtualNetworks
- Location: [Specify the Azure region]
- Description: The Hub Virtual Network acts as the central hub for the hub-and-spoke network architecture. It contains common resources such as the Azure Firewall and the Application Gateway.

Spoke Virtual Networks

- Resource Type: Microsoft.Network/virtualNetworks
- Location: [Specify the Azure region]
- Description: Two Spoke Virtual Networks are connected to the Hub. These networks can be used to host resources specific to different regions or purposes.

VNet Peering between Hub and Spokes

- Resource Type: Microsoft.Network/virtualNetworks/virtualNetworkPeerings
- Description: This resource establishes peering connections between the Hub and each Spoke, enabling communication between them.

Azure Firewall in the Hub VNet

- Resource Type: Microsoft.Network/azureFirewalls
- Location: [Specify the Azure region]
- Description: Azure Firewall is used to control inbound and outbound traffic to and from the Hub Virtual Network. It helps secure the network and provides network-level protection.

Private Endpoint

- Resource Type: Microsoft.Network/privateEndpoints
- Location: [Specify the Azure region]
- Description: Private Endpoint enables secure access to Azure services over a private connection. You can specify the specific properties and configurations required.

Application Gateway with WAF

- Resource Type: Microsoft.Network/applicationGateways
- Location: [Specify the Azure region]
- Description: Application Gateway with Web Application Firewall (WAF) provides high availability and security for your web applications. It can route traffic to different regions and provide protection against web-based threats.

Storage Accounts for Hosting Static Websites

- Resource Type: Microsoft.Storage/storageAccounts
- Location: [Specify the Azure region]
- Description: These storage accounts are configured to host static websites. They are designed for high availability and support HTTPS traffic only.

Parameters and Variables

Parameters

- `location`: Default location for the deployment. In this case, the default value is "East US".

Variables

- `hubVNetName`: Name of the Hub VNet. In this example, it is set to "hubVNet".
- `spoke1VNetName`: Name of the first spoke VNet. In this example, it is set to "spoke1VNet".
- `spoke2VNetName`: Name of the second spoke VNet. In this example, it is set to "spoke2VNet".
- `hubToSpoke1PeeringName`: Name of the peering between the Hub and the first spoke. In this example, it is set to "hubToSpoke1Peering".
- `hubFirewallName`: Name of the firewall in the Hub. In this example, it is set to "hubFirewall".
- `privateEndpointName`: Name of the private endpoint. In this example, it is set to "private_endpoint".
- `appGatewayName`: Name of the Application Gateway with WAF. In this example, it is set to "appGatewayWaf".
- `staticWebsiteStorage1Name`: Name of the first storage account for hosting static websites. In this example, it is set to "staticWebsiteStorage1".
- `staticWebsiteStorage2Name`: Name of the second storage account for hosting static websites. In this example, it is set to "staticWebsiteStorage2".

How to Use

1. Modify the parameters in the ARM template as needed, such as the Azure region, resource names, and configurations.
2. Deploy the ARM template using Azure CLI, Azure PowerShell, or Azure Portal.
3. Monitor the deployment process for any errors or issues.

For detailed instructions on deploying this infrastructure, refer to the official Azure documentation: [Azure ARM Template Deployment](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/deploy-portal).

Important Notes

- Ensure that you have the necessary Azure permissions to create and manage these resources.
- Follow Azure best practices for security, naming conventions, and resource management.

 # Official Documentation Used

Below is a list of resources from Microsoft Azure's official documentation and other sources that were referenced for creating the YAML in this exercise:

1. [Azure Resource Manager Templates (ARM Templates)](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/): Official documentation on ARM Templates, used to describe and deploy Azure resources declaratively.
2. [Azure Virtual Network](https://docs.microsoft.com/en-us/azure/virtual-network/): Documentation covering Azure Virtual Network creation and configuration.
3. [Azure Firewall](https://docs.microsoft.com/en-us/azure/firewall/): In-depth information about Azure Firewall and how it can be used to protect Azure Virtual Networks.
4. [Azure Private Endpoint](https://docs.microsoft.com/en-us/azure/private-link/private-endpoint-overview): Documentation on Azure Private Endpoint, enabling private connectivity to Azure services.
5. [Azure Application Gateway](https://docs.microsoft.com/en-us/azure/application-gateway/): Information about Azure Application Gateway, providing load balancing and web application services.
6. [Web Application Firewall (WAF)](https://docs.microsoft.com/en-us/azure/web-application-firewall/): Details on Azure's Web Application Firewall (WAF), safeguarding web applications against threats.
7. [Static website hosting in Azure Storage](https://docs.microsoft.com/en-us/azure/storage/blobs/storage-blob-static-website): Guide on enabling static website hosting in Azure Storage accounts.
8. [Azure CLI](https://docs.microsoft.com/en-us/cli/azure/): Official documentation for the Azure Command-Line Interface (CLI) used to interact with Azure from the command line.
9. [Azure PowerShell](https://docs.microsoft.com/en-us/powershell/azure/): Information on Azure PowerShell, a tool for managing Azure services through PowerShell commands.
10. [Azure DevOps](https://docs.microsoft.com/en-us/azure/devops/): Azure DevOps documentation, which can be used to implement CI/CD practices in Azure.





