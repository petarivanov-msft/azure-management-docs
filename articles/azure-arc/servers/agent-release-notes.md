---
title: What's new with Azure Connected Machine agent
description: This article has release notes for Azure Connected Machine agent. For many of the summarized issues, there are links to more details.
ms.topic: overview
ms.date: 01/30/2025
ms.custom: references_regions
---

# What's new with Azure Connected Machine agent

The Azure Connected Machine agent receives improvements on an ongoing basis. To stay up to date with the most recent developments, this article provides you with information about:

- The latest releases
- Known issues
- Bug fixes

This page is updated monthly, so revisit it regularly. If you're looking for items older than six months, you can find them in [archive for What's new with Azure Connected Machine agent](agent-release-notes-archive.md).

> [!WARNING]
> Only Connected Machine agent versions within the last 1 year are officially supported by the product group. Customers should update to an agent version within this window. Microsoft recommends staying up to date with the latest agent version whenever possible.
> 

## Version 1.48 - January 2025

Download for [Windows](https://aka.ms/AzureConnectedMachineAgent) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Addressed a security issue related to Redirection Guard.
- Resolved a bug that caused issues during the upgrade of the RunCommand extension.
- Fixed high port usage in the Azure Arc proxy.
- Fixed an issue with the Alma Linux install script.
- Improved handling of disassociated Gateway URLs.
- Resolved an issue with disk space queries.
- Improved HIMDS behavior when IMDS data is unavailable.

### New features and enhancements

- Added support for extension telemetry.
- Updated the OpenSSL library for security enhancements.
- Improved error reporting for `azcmagent` commands.
- Increased connectivity check timeout for better reliability.
- Expanded ARM64 platform support to include RHEL 9.
- Updated the `mssqldiscovered` property to include the detection for SQL Server Integration, Analysis, and Reporting services (SSIS, SSAS, SSRS and PBIRS).
- Introduced a scheduled task that checks for agent updates on a daily basis. Currently, the update mechanism is inactive and no changes are made to your server even if a newer agent version is available. In the future, you'll be able to schedule updates of the Azure Connected Machine agent from Azure. For more information, see [Automatic agent upgrades](manage-agent.md#automatic-agent-upgrades).


## Version 1.47 - October 2024

Download for [Windows](https://download.microsoft.com/download/2/1/d/21dfb0f5-ed95-46d5-8146-ece13381056a/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Guest Configuration: Fix an issue that caused agent to become unresponsive.
- Fixed a bug to trim error messages when updating AgentStatus.

### New features and enhancements

- Code enhancement to support cloud specific endpoints in the install script.
- Addition of architecture detection to system properties.
- Addition of EndpointConnectivityInfo to AgentData.
- Expansion of ARM64 platform support for the following distributions:
    - Ubuntu 20.04, 22.04, 24.04
    - Azure Linux (CBL-Mariner) 2.0
    - Amazon Linux 2
    - Alma Linux 8

## Version 1.46 - September 2024

Download for [Windows](https://download.microsoft.com/download/6/c/0/6c0775bc-9ed7-49af-9637-79653f783062/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Fixed a bug causing the Guest Config agent to hang in extension creating state when the download of an extension package failed.
- Fixed a bug where onboarding treated conflicting errors as success.

### New features and enhancements

- Improved error messaging for scenarios with extension installation and enablement blockage in the presence of a sideloaded extension.
- Increased checks for recovery of sequence number if the previous request failed.
- Removed casing requirements when reading the proxy from the configuration file.
- Added supported for Azure Linux 3 (Mariner).
- Added initial Linux ARM64 architecture support.
- Added Gateway URL to the output of the show command.

## Version 1.45 - August 2024

Download for [Windows](https://download.microsoft.com/download/0/6/1/061e3c68-5603-4c0e-bb78-2e3fd10fef30/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Fixed an issue where EnableEnd telemetry would sometimes be sent too soon.
- Added sending a failed timed-out EnableEnd telemetry log if extension takes longer than the allowed time to complete.

### New features

- Azure Arc proxy now supports HTTP traffic.
- New proxy.bypass value 'AMA' added to support AMA VM extension proxy bypass.

## Version 1.44 - July 2024

Download for [Windows](https://download.microsoft.com/download/d/a/f/daf3cc3e-043a-430a-abae-97142323d4d7/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Fixed a bug where the service would sometimes reject reports from an upgraded extension if the previous extension was in a failed state.
- Setting OPENSSL_CNF environment at process level to override build openssl.cnf path on Windows.
- Fixed access denied errors in writing configuration files.
- Fixed SYMBIOS GUID related bug with Windows Server 2012 and Windows Server 2012 R2 [Extended Security Updates](/windows-server/get-started/extended-security-updates-overview) enabled by Azure Arc.

### New features

- Extension service enhancements: Added download/validation error details to extension report. Increased unzipped extension package size limit to 1 GB.
- Update of hardwareprofile information to support upcoming Windows Server licensing capabilities.
- Update of the error json output to include more detailed recommended actions for troubleshooting scenarios.
- Block on installation of unsupported operating systems and distribution versions. See [Supported operating systems](prerequisites.md#supported-operating-systems) for details.

> [!NOTE]
> Azure Connected Machine agent version 1.44 is the last version to officially support Debian 10, Ubuntu 16.04, and Azure Linux (CBL-Mariner) 1.0.
> 

## Version 1.43 - June 2024 

Download for [Windows](https://download.microsoft.com/download/0/7/8/078f3bb7-6a42-41f7-b9d3-9a0eb4c94df8/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Fix for OpenSSL Vulnerability for Linux (Upgrading OpenSSL version from 3.0.13 to 3.014)
- Added Server Name Indicator (SNI) to our service calls, fixing Proxy and Firewall scenarios
- Skipped lockdown policy on the downloads directory under Guest Configuration

## Version 1.42 - May 2024 (Second Release)

Download for [Windows](https://download.microsoft.com/download/9/6/0/9600825a-e532-4e50-a2d5-7f07e400afc1/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Fixed

- Extensions and machine configuration policies can be used with private endpoints again

## Version 1.41 - May 2024

Download for [Windows](https://download.microsoft.com/download/2/a/5/2a57aa86-c445-4f08-bd52-10af2b748fec/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Known issues

Customers using private endpoints with Azure Arc may encounter issues with extension management and machine configuration policies with agent version 1.41. Agent version 1.42 resolves this issue.

### New features

- Certificate-based authentication is now supported when using a service principal to connect or disconnect the agent. For more information, see [authentication options for the azcmagent CLI](azcmagent-connect.md#authentication-options).
- [azcmagent check](azcmagent-check.md) now allows you to also check for the endpoints used by the SQL Server enabled by Azure Arc extension using the new `--extensions` flag. This can help you troubleshoot networking issues for both the OS and SQL management components. You can try this out by running `azcmagent check --extensions sql --location eastus` on a server, either before or after it is connected to Azure Arc.

### Fixed

- Fixed a memory leak in the Hybrid Instance Metadata service
- Better handling when IPv6 local loopback is disabled
- Improved reliability when upgrading extensions
- Improved reliability when enforcing CPU limits on Linux extensions
- PowerShell telemetry is now disabled by default for the extension manager and policy services
- The extension manager and policy services now support OpenSSL 3
- Colors are now disabled in the onboarding progress bar when the `--no-color` flag is used
- Improved detection and reporting for Windows machines that have custom [logon as a service rights](prerequisites.md#local-user-logon-right-for-windows-systems) configured.
- Improved accuracy when obtaining system metadata on Windows:
  - VMUUID is now obtained from the Win32 API
  - Physical memory is now checked using WMI
- Fixed an issue that could prevent the region selector in the [Windows GUI installer](onboard-windows-server.md) from loading
- Fixed permissions issues that could prevent the "himds" service from accessing necessary directories on Windows

## Version 1.40 - April 2024

Download for [Windows](https://download.microsoft.com/download/2/1/0/210f77ca-e069-412b-bd94-eac02a63255d/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Known issues

The first release of the 1.40 agent may impact SQL Server enabled by Azure Arc when configured with least privileges on Windows servers. The 1.40 agent was re-released to address this problem. To check if your server is affected, run `azcmagent show` and locate the agent version number. Agent version `1.40.02664.1629` has the known issue and agent `1.40.02669.1635` fixes it. Download and install the [latest version of the agent](https://aka.ms/AzureConnectedMachineAgent) to restore functionality for SQL Server enabled by Azure Arc.

### New features

- Oracle Linux 9 is now a [supported operating system](prerequisites.md#supported-operating-systems)
- Customers no longer need to download an intermediate CA certificate for delivery of WS2012/R2 ESUs (Requires April 2024 SSU update)

### Fixed

- Improved error handling when a machine configuration policy has an invalid SAS token
- The installation script for Windows now includes a flag to suppress reboots in case any agent executables are in use during an upgrade
- Fixed an issue that could block agent installation or upgrades on Windows when the installer can't change the access control list on the agent's log directories.
- Extension package maximum download size increased to fix access to the [latest versions of the Azure Monitor Agent](/azure/azure-monitor/agents/azure-monitor-agent-extension-versions) on Azure Arc-enabled servers.

## Version 1.39 - March 2024

Download for [Windows](https://download.microsoft.com/download/1/9/f/19f44dde-2c34-4676-80d7-9fa5fc44d2a8/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### New features

- Check which extensions are installed and manually remove them with the new [azcmagent extension](azcmagent-extension.md) command group. These commands run locally on the machine and work even if a machine has lost its connection to Azure.
- You can now [customize the CPU limit](agent-overview.md#custom-resource-limits) applied to the extension manager and machine configuration policy evaluation engine. This might be helpful on small or under-powered VMs where the [default resource governance limits](agent-overview.md#agent-resource-governance) can cause extension operations to time out.

### Fixed

- Improved reliability of the run command feature with long-running commands
- Removed an unnecessary endpoint from the network connectivity check when onboarding machines via an Azure Arc resource bridge
- Improved heartbeat reliability
- Removed unnecessary dependencies

## Version 1.38 - February 2024

Download for [Windows](https://download.microsoft.com/download/4/8/f/48f69eb1-f7ce-499f-b9d3-5087f330ae79/AzureConnectedMachineAgent.msi) or [Linux](manage-agent.md#installing-a-specific-version-of-the-agent)

### Known issues

Windows machines that try and fail to upgrade to version 1.38 manually or via Microsoft Update might not roll back to the previously installed version. As a result, the machine will appear "Disconnected" and won't be manageable from Azure. A new version of 1.38 was released to Microsoft Update and the Microsoft Download Center on March 5, 2024 that resolves this issue.

If your machine was affected by this issue, you can repair the agent by downloading and installing the agent again. The agent will automatically discover the existing configuration and restore connectivity with Azure. You don't need to run `azcmagent connect`.

### New features

- AlmaLinux 9 is now a [supported operating system](prerequisites.md#supported-operating-systems)

### Fixed

- The hybrid instance metadata service (HIMDS) now listens on the IPv6 local loopback address (::1)
- Improved logging in the extension manager and policy engine
- Improved reliability when fetching the latest operating system metadata
- Reduced extension manager CPU usage

## Next steps

- Before evaluating or enabling Azure Arc-enabled servers across multiple hybrid machines, review [Connected Machine agent overview](agent-overview.md) to understand requirements, technical details about the agent, and deployment methods.
- Review the [Planning and deployment guide](plan-at-scale-deployment.md) to plan for deploying Azure Arc-enabled servers at any scale and implement centralized management and monitoring.
