# Microsoft Office 365 Monitoring

LogicMonitor offers monitoring for Microsoft Office 365 by default. You can monitor the state of your Office 365 deployment, as well as the underlying services and license usage.

## Requirements

*   You must be an administrator of an active Microsoft Azure account to grant admin consent for API permissions.
*   Add an app registration and subscription details in Azure. For more information, see [Adding Your Azure Environment to LogicMonitor](https://www.logicmonitor.com/support/lm-cloud/getting-started-lm-cloud/2b-adding-azure-environment-logicmonitor).
*   Install the [Office 365 LogicModules](https://www.logicmonitor.com/support/monitoring/applications-databases/microsoft-office-365-monitoring#h-office-365-logicmodules).

## Adding API Permissions to your App Registration

1.  In Azure, navigate to **App registrations** and select the app registration that is set up for LogicMonitor. If it has not been set up, follow the steps in [Adding Your Azure Environment to LogicMonitor](https://www.logicmonitor.com/support/lm-cloud/getting-started-lm-cloud/2b-adding-azure-environment-logicmonitor).
2.  From the app registration’s Overview page, select **API permissions** and then select **Add a permission**.
3.  On the **Request API permissions** page, select **Microsoft Graph**.
4.  Select **Application permissions**, and then add the following:
    *   User.Read.All
    *   Reports.Read.All
    *   Organization.Read.All
    *   Directory.Read.All
    *   ServiceHealth.Read.All
    *   CallRecords.Read.All
5.  Select **Add permissions**.
6.  Select **Grant admin consent** for each permission.

**Note:** You must be an administrator to grant admin consent. For more information, see [Introduction to Permissions and Consent](https://learn.microsoft.com/en-us/azure/active-directory/develop/permissions-consent-overview).

## Adding Office 365 to LogicMonitor

Microsoft Office 365 is added to LogicMonitor as a SaaS resource. The SaaS Monitoring wizard takes you through the all of the steps, and you can test authentication before adding Office 365 to your resources. Use your Microsoft Azure account to configure the application permissions and integration settings. 

1.  In LogicMonitor, navigate to **Resources** and select **Add** > **Cloud Account**.
2.  Select **Office 365** > **Add**.
3.  On the **Name** page, enter a **Name** and **Description** for the Office 365 account. These fields determine how the resource is displayed throughout your LogicMonitor environment.
4.  Enter a **Parent Group** to add this resource to an existing group. The default value is **root**.
5.  Enter **Properties** (key-value pair) by typing a **Name** and **Value**. You can also select from a list of existing properties. Select **Next**.
6.  On the **Permissions** page, enter the permissions that you collected while [Adding Your Azure Environment to LogicMonitor](https://www.logicmonitor.com/support/lm-cloud/getting-started-lm-cloud/2b-adding-azure-environment-logicmonitor).
    *   User ID: The **Application (client) ID** in Azure.
    *   Tenant ID: The **Directory (tenant) ID** in Azure.
    *   Secret Key: The **Value** in Azure.
7.  Select **Test Permissions** to authenticate.
8.  Select **Add Service** to add the new resource to LogicMonitor.
9.  Select **View Resource** to view the Office 365 SaaS resource in LogicMonitor.

### Office 365 LogicModules

The following modules are available for Office 365 SaaS integration. For more information, see [Installing Modules and Packages](https://www.logicmonitor.com/support/modules-installing).

| Name | Type | Description |
| --- | --- | --- |
| Microsoft_Office365_Subscriptions | DataSource | Monitors Office 365 subscriptions. |
| Microsoft_Office365_ServiceHealth | DataSource | Monitors Office 365 service health. |
| Microsoft_Office365_Teams_Device_Usage | DataSource | Monitors the last seven days of Microsoft Teams device usage by the number of users. |
| Microsoft_Office365_Teams_Activity | DataSource | Monitors the last seven days of Microsoft Teams activity. |
| Microsoft_Office365_OneDriveFileCount | DataSource | Monitors OneDrive total and active files, as well as the time since the report was last updated. |
| Microsoft_Office365_OneDriveAccounts | DataSource | Monitors the number of Active and Total accounts on OneDrive. |
| Microsoft_Office365_OneDriveStorage | DataSource | Monitors OneDrive total storage used. |
| Microsoft_Office365_EmailActivity | DataSource | Monitors Outlook total and rate counts for read, received, and sent emails. |
| Microsoft_Office365_EmailAppUsage | DataSource | Monitors usage by application or Office version. |
| Microsoft_Office365_UserCount | DataSource | Monitors individual Office365 services and their associated user activity. |
| Microsoft_Office365_SharepointSiteDetails | DataSource | Monitors the overall status of the SharePoint site.Note: Microsoft has removed identifiable user information such as usernames, groups, and sites from all their SharePoint usage reports. If you want to monitor SharePoint site details, you’ll need to make configuration changes to your Microsoft 365 settings to display the user information. For more information, see Show user details in the reports. |
| Microsoft_Office365_SharepointStorage | DataSource | Monitors SharePoint site storage. |
| Microsoft_Office365_Skype_DeviceUsage | DataSource | Monitors Skype usage by device type. |
| Microsoft_Office365_Skype_PeerActivityMinutes | DataSource | Monitors Microsoft 365 Skype for Business user activity by minutes for video and audio. |
| Microsoft_Office365_Skype_PeerActivity | DataSource | Displays Skype for business peer-to-peer activity counts. |
| Microsoft_Office365_MailboxQuotaStatus | DataSource | Monitors the number of Mailboxes in different quota states. |
| Microsoft_Office365_MailboxUsageDetail | DataSource | Fetches details about mailbox usage. |
| Microsoft_Office365_Yammer_Device_Usage | DataSource | Monitors Yammer usage by device type. |
| Office365_SharepointOnline_TenantConfig | ConfigSource | Captures SharePoint Online organization-level tenant config. |
| Office365_ExchangeOnline_Users | ConfigSource | Monitors Exchange users in your organization. |
| Office365_ExchangeOnline_TransportConfig | ConfigSource | Monitors Exchange organization-wide transport configuration settings. |
| Office365_ExchangeOnline_Organization | ConfigSource | Monitors Exchange organization config. |
| Office365_ExchangeOnline_OWAMailboxPolicy | ConfigSource | Monitors Exchange Outlook on the web mailbox policies in the organization. |
| Office365_ExchangeOnline_MobileDevices | ConfigSource | Monitors Exchange mobile device config for identification, configuration, and status information for each mobile device. |
| Office365_ExchangeOnline_MobileDeviceMailboxPolicy | ConfigSource | Monitors Exchange mobile device mailbox policy config. |
| Office365_ExchangeOnline_ManagementRoles | ConfigSource | Monitors the Exchange management role objects in your organization |
| Office365_ExchangeOnline_Mailboxes | ConfigSource | Monitors the Exchange mailbox configs. |
| Office365_ExchangeOnline_Groups | ConfigSource | Monitors the config group objects. Returns security groups, mail-enabled security groups, distribution groups, and role groups. |

### Microsoft Teams QoS DataSource

LogicMonitor’s MS Teams QoS (Quality of Service) DataSource monitors audio, video, and screen share metrics from MS Teams call records, which are made available by Microsoft. These metrics help identify MS Teams calls that are not performant, and which aspects of the calls are problematic. To use the MS Teams QoS DataSource, you must enable the Microsoft Graph permission CallRecords.Read.All in Microsoft Azure.

## QoS Metrics and Reporting

QoS metrics are reported only for calls that have ended.

*   Microsoft reports a maximum latency of 60 minutes after a call ends before metrics may be made available. However, this period may be as short as 15 to 20 minutes.
*   Microsoft reports data for calls through the MS Teams app only — not from the browser.
*   By default, LogicMonitor reports QoS metrics every five minutes. The Poll Now feature in LogicMonitor (Datapoint > Raw Data) shows metrics for the last scheduled call.

### Microsoft callRecord API

LogicMonitor uses Microsoft’s callRecord API to gather all QoS related data for recently-ended calls. The data is collected and processed, and performance metrics are reported to LogicMonitor. For example, you could collect data on the maximum audio jitter across all available segments of a call. For more information, see [Get callRecord](https://learn.microsoft.com/en-us/graph/api/callrecords-callrecord-get?view=graph-rest-1.0&tabs=http) from the Microsoft documentation.

### Audio, Video, and Sharing Metrics

The following metric types are monitored:

*   Audio stream
*   Video stream
*   App sharing or video-based screen sharing stream

### Audio Stream Metrics

| Name | Description |
| --- | --- |
| audioAverageJitter | Average audio jitter |
| audioAveragePacketLossRate | Average audio packet loss rate |
| audioAverageRoundTripTime | Average audio round-trip time |
| audioCalleeNetworkBandwidthLowEventRatio | Callee network bandwidth low event ratio |
| audioCalleeNetworkDelayEventRatio | Callee network delay low event ratio |
| audioCalleeNetworkLinkSpeed | Audio link speed for callee network in bits per second |
| audioCalleeNetworkReceivedQualityEventRatio | Callee network received quality event ratio |
| audioCalleeNetworkSentQualityEventRatio | Callee network sent quality event ratio |
| audioCallerNetworkBandwidthLowEventRatio | Caller network bandwidth low event ratio |
| audioCallerNetworkDelayEventRatio | Caller network delay event ratio |
| audioCallerNetworkLinkSpeed | Audio link speed for caller network in bits per second |
| audioCallerNetworkReceivedQualityEventRatio | Caller network received quality event ratio |
| audioCallerNetworkSentQualityEventRatio | Caller network sent quality event ratio |
| audioMaxJitter | Maximum audio jitter |
| audioMaxPacketLossRate | Maximum packet loss rate for audio stream |
| audioMaxRoundTripTime | Audio maximum round-trip time |
| audioPacketUtilization | Number of Real-Time Transport Protocol (RTP) audio packets sent in the session |
| averageAudioNetworkJitter | Average audio network jitter |
| maxAudioNetworkJitter | Maximum audio network jitter |

### Video Stream Metrics

| Name | Description |
| --- | --- |
| videoAverageAudioNetworkJitter | Average audio network jitter in video stream |
| videoAverageJitter | Average video jitter |
| videoAveragePacketLossRate | Average video packet loss rate |
| videoAverageReceivedFrameRate | Average video received frame rate |
| videoAverageRoundTripTime | Average video round-trip time |
| videoAverageVideoFrameLossPercentage | Average video frame loss percentage |
| videoAverageVideoFrameRate | Average video frame rate |
| videoCalleeNetworkBandwidthLowEventRatio | Callee network bandwidth low event ratio |
| videoCalleeNetworkDelayEventRatio | Callee network delay event ratio |
| videoCalleeNetworkLinkSpeed | Callee network link speed |
| videoCalleeNetworkReceivedQualityEventRatio | Callee network received quality event ratio |
| videoCalleeNetworkSentQualityEventRatio | Callee network sent quality event ratio |
| videoCallerNetworkBandwidthLowEventRatio | Caller network bandwidth low event ratio |
| videoCallerNetworkDelayEventRatio | Caller network delay event ratio |
| videoCallerNetworkLinkSpeed | Caller network link speed |
| videoCallerNetworkReceivedQualityEventRatio | Caller network received quality event ratio |
| videoCallerNetworkSentQualityEventRatio | Caller network sent quality event ratio |
| videoLowFrameRateRatio | Video low frame rate ratio |
| videoMaxAudioNetworkJitter | Maximum audio network jitter in video stream |
| videoMaxJitter | Video maximum jitter |
| videoMaxPacketLossRate | Maximum packet loss rate for video stream |
| videoMaxRoundTripTime | Video maximum round trip time |
| videoPacketUtilization | Number of Real-Time Transport Protocol (RTP) video packets sent in the session |

### App Sharing or Video-Based Screen Sharing Stream Metrics

| Name | Description (Application Sharing) |
| --- | --- |
| applicationSharingVideoAverageReceivedFrameRate | Video average received frame rate |
| applicationSharingVideoAverageVideoFrameRate | Video average frame rate |
| applicationSharingVideoCalleeNetworkBandwidthLowEventRatio | Callee network bandwidth low event ratio for video |
| applicationSharingVideoCalleeNetworkDelayEventRatio | Callee network delay event ratio for video |
| applicationSharingVideoCalleeNetworkLinkSpeed | Callee network link speed for video |
| applicationSharingVideoCalleeNetworkReceivedQualityEventRatio | Callee network received quality event ratio for video |
| applicationSharingVideoCalleeNetworkSentQualityEventRatio | Callee network sent quality event ratio for video |
| applicationSharingVideoCallerNetworkBandwidthLowEventRatio | Caller network bandwidth low event ratio for video |
| applicationSharingVideoCallerNetworkDelayEventRatio | Caller network delay event ratio for video |
| applicationSharingVideoCallerNetworkLinkSpeed | Caller network link speed for video |
| applicationSharingVideoCallerNetworkReceivedQualityEventRatio | Caller network received quality event ratio for video |
| applicationSharingVideoCallerNetworkSentQualityEventRatio | Caller network sent quality event ratio for video |
