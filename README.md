*******************************************************************************<br>
<br>
<b>PROJECT NAME:&emsp;&emsp;&emsp;&emsp;&nbsp;Azure Service Retirements<br>
CREATED BY:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;THEANGRYTECH-GIT<br>
REPO:&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[([Azure Service Retirements](https://github.com/theangrytech-git/azure-service-retirements))]<br><br>
DESCRIPTION:</b>&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;This PowerShell script queries Azure Service Health to identify<br>
Service Retirement and end-of-life notifications affecting an Azure subscription.<br>
It extracts impact, region, and timeline details and generates a clear HTML report to <br>
help teams proactively plan and avoid disruption from retiring Azure services.<br>
<br>
It will highlight any Services due to retire within:<br>
365 days - treated as Informational<br>
90 days until retirement - treated as Medium Priority<br>
30 days until retirement - treated as High Priority<br>
<br>
The report will highlight what Feature/Service is due for Retirement (ie Support for TLS 1.0/1.1)<br>
and will provide a list of what the affected Resource Names are, what Resource Group they are in,<br>
what Subscription they are in, as well as how many days are left until the Feature/Service is retired.<br>

The report can either be run locally on your desktop, or as an Azure Runbook.<br>
<br>
<b>Serivce_Retirement_Locally_Run </b> - Allows you to run it locally from your Desktop using Powershell,<br>
to generate a report which will be emailed to you. Can be run at any point.<br>
You will need to change Lines 19-33 to match your Sendgrid API, Email Addresses, and Subcription details<br>
You can also change the 'Look Ahead' days on Lines 28-30 if you want longer/shorter reporting periods.<br>
<br>
<b>Serivce_Retirement_Azure_Runbook </b> - Can be added as an Azure Runbook, to run on a schedule within a<br>
Azure Automation Account.<br>
You will need to create the Automation Variables from Lines 19-32 and provide your Sendgrid API, Email addresses, and Subcription details<br>
*******************************************************************************<br>
<br>
<b>NOTES:</b><br>
This will require the following to run:<br><br>
<b>Service Principal</b> - needs Reader Permissions on the Subscription<br>
<b>SendGrid API Key</b> - Used to send the email to the recipent. You can use an Azure-based<br>
solution like Azure Communication Services, or an Azure Function with SMTP. But I have<br>
a Sendgrid API so that's what I've built this around.<br>

*******************************************************************************<br>
<br>
This will create a single report that will report on any Services/Features that may retire within 365 days (Or as soon as reported by MS/Azure)<br>
and provides a one-stop report of any Resources that will be impacted by the Retirements from Azure.<br><br>
It's recommended that this report is run once a month, so you have a monthly report for any Clients/Projects that require it, as well<br>
as your Operations Teams.<br>
*******************************************************************************<br>
<b>Screenshots</b><br>
*******************************************************************************<br>
<br>
Here's some screenshots of the report, with some details omitted for security purposes:<br>
<br>
![Azure Advisor Categories](Images/retirements.jpg)
<br>
*Figure 1: List of Service Retirements, running in a test subscription*<br>