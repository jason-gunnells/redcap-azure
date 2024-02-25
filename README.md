# ARM Template for REDCap automated deployment in Azure

A simple way to deploy REDCap into an Azure environment.

## Quick Start

Description | Link
--- | ---
Deploy REDCap in Azure | <a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Ftdannecy%2Fredcap-azure%2Fmaster%2Fazuredeploy.json" target="_blank"><img src="http://azuredeploy.net/deploybutton.png"/></a>

## Details

This template automates the deployment of the REDCap solution into Azure using managed PaaS resources.

This ARM template deploys the following:

* Azure App Service and Web App
* Azure DB for MySQL Flexible
* Azure Storage Account

During configuration, you must supply your REDCap Community site credentials. The deployment automation will use this information to pull the latest copy of the REDCap source from the community site. These values will be stored within the Azure App Service as configuration settings. Once your deployment has succeeded, you should navigate to your Azure App Service resource and delete or empty out the values so that they aren't stored here.

## Changelog

February 25, 2024

* Simplified the deployment folder, removing Terraform and other artifacts.
* Upgraded Sendmail to version 33 to support TLS 1.2 (required for O365 setup).
* Changed DB service to Azure DB for MySQL Flexible, as Single Server is being discontinued.
* Tweaks to `cron` service WebJob.
