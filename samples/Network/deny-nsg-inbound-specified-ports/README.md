# Denies NSG rule changes that allow all inbound traffic

Denies the creation of network security group rules that allow inbound traffic on specified ports

## Try on Portal

[![Deploy to Azure](http://azuredeploy.net/deploybutton.png)](https://portal.azure.com/#blade/Microsoft_Azure_Policy/CreatePolicyDefinitionBlade/uri/https%3A%2F%2Fraw.githubusercontent.com%2FAzure%2Fazure-policy%2Fmaster%2Fsamples%2FNetwork%2Fdeny-nsg-inbound-allow-all%2Fazurepolicy.json)

## Try with PowerShell

````powershell
$definition = New-AzureRmPolicyDefinition -Name "deny-nsg-inbound-allow-all" -DisplayName "Denies NSG rule changes that allow all inbound traffic" -description "Denies people from changing NSG rules that allow all inbound traffic" -Policy 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Network/deny-nsg-inbound-allow-all/azurepolicy.rules.json' -Mode All
$definition
$assignment = New-AzureRMPolicyAssignment -Name <assignmentname> -Scope <scope> -PolicyDefinition $definition
$assignment 
````

## Try with CLI

````cli

az policy definition create --name 'deny-nsg-inbound-allow-all' --display-name 'Denies NSG rule changes that allow all inbound traffic' --description 'Denies people from changing NSG rules that allow all inbound traffic' --rules 'https://raw.githubusercontent.com/Azure/azure-policy/master/samples/Network/deny-nsg-inbound-allow-all/azurepolicy.rules.json' --mode All

az policy assignment create --name <assignmentname> --scope <scope> --policy "deny-nsg-inbound-allow-all" 

````
