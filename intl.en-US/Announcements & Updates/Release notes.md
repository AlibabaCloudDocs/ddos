# Release notes

This topic describes the release notes of Anti-DDoS Pro, Anti-DDoS Premium, and Anti-DDoS Origin features.

## Anti-DDoS Pro and Anti-DDoS Premium

|Release date|Feature|Description|Documentation|
|------------|-------|-----------|-------------|
|2020-08-04|Sec-Traffic Manager \>Cloud Service Interaction

|The **Cloud Service Interaction** feature allows you to configure Anti-DDoS Pro or Anti-DDoS Premium to interact with Global Accelerator instances. This feature delivers the following benefits:-   If no distributed denial-of-service \(DDoS\) attacks occur, Global Accelerator provides accelerated access.
-   If Global Accelerator suffers DDoS attacks, the feature redirects traffic to Anti-DDoS Pro or Anti-DDoS Premium for scrubbing. This reduces the impacts that DDoS attacks have on services.

|[Create a cloud service interaction rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Create a cloud service interaction rule.md)|
|2020-07-09|Protection settings|Major changes: -   Anti-DDoS Pro allows you to set the duration for IP addresses to be retained in a blacklist.
-   In the Anti-DDoS Premium console, the **Protection for Infrastructure** tab supports the **Blacklist and Whitelist \(Instance IP\)** settings, and the **Protection for Non-website Services** tab supports the **Intelligent protection** settings.

|[Configure the IP address blacklist and whitelist for an Anti-DDoS Pro or Anti-DDoS Premium instance](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Protection settings/Protection for infrastructure/Configure the IP address blacklist and whitelist for an Anti-DDoS Pro or Anti-DDoS
         Premium instance.md)[Configure intelligent protection](t79690.md#) |
|2020-06-22|Sec-MCA|The Sec-MCA feature in Anti-DDoS Premium provides protection at both Layer 4 and Layer 7. This feature accelerates network access for your service outside mainland China and protects your assets against DDoS attacks.|[Configure Anti-DDoS Premium Sec-MCA](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Configure Anti-DDoS Premium Sec-MCA.md)|
|2020-05-19|Sec-Traffic Manager \> CDN/DCDN Interaction

|Anti-DDoS Pro and Anti-DDoS Premium can interact with Dynamic Route for Content Delivery Network \(DCDN\) to scrub malicious traffic and accelerate content delivery: -   If no attacks are detected, DCDN accelerates traffic of your workloads.
-   If attacks are detected, traffic of your workloads is automatically redirected to Anti-DDoS Pro or Anti-DDoS Premium and then scrubbed.
-   After the attacks stop, traffic of your workloads is automatically redirected to Alibaba Cloud DCDN.

|[Create a CDN or DCDN interaction rule](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Create a CDN or DCDN interaction rule.md)|
|2020-04-30|Sec-Traffic Manager \> CDN Interaction

|If attacks are detected, a sandbox is enabled for CDN-accelerated domain names that integrate with Anti-DDoS Pro or Anti-DDoS Premium. Traffic is redirected to an anti-DDoS scrubbing center. This ensures the service availability.|[Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md)|
|2020-04-22|Sec-Traffic Manager \> General

|You can set the wait time of switching back in general scheduling rules. Before the wait time elapses, you can also manually switch traffic from Anti-DDoS Pro or Anti-DDoS Premium back to cloud resources.|[Overview](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Provisioning/Sec-Traffic Manager/Overview.md)|
|2020-04-01|New API operations|New API operations are provided for you to manage and integrate Anti-DDoS Pro and Anti-DDoS Premium instances.|[List of operations by function](/intl.en-US/API reference/Anti-DDoS Pro & Premium/List of operations by function.md)|
|2020-03-03|Anti-DDoS Premium interacting with Cloud Monitor|Anti-DDoS Premium allows you to view basic O&M data in Cloud Monitor. You can create and customize alert rules in the Cloud Monitor console based on your service requirements.|[Configure an alert rule for Anti-DDoS Pro or Anti-DDoS Premium](/intl.en-US/Anti-DDoS Pro & Premium User Guide/Monitoring and alerting/Create an Anti-DDoS alert rule.md)[Monitor black hole events and traffic scrubbing events on Anti-DDoS](t1847272.md#) |
|2020-02-18|Integrated console and region selection|The consoles of Anti-DDoS Pro and Anti-DDoS Premium are integrated. -   In the console, you can select **Mainland China** for Anti-DDoS Pro or **Outside Mainland China** for Anti-DDoS Premium.
-   You can access Anti-DDoS Pro and Anti-DDoS Premium in the same console. The Anti-DDoS Premium console is updated to provide a graphical user interface that is similar to that of the Anti-DDoS Pro console.

|[Differences between the features of Anti-DDoS Pro and Anti-DDoS Premium](/intl.en-US/Product Introduction on Alibaba DDoS Protection/What are Anti-DDoS Pro and Anti-DDoS Premium?.md)|

## Anti-DDoS Origin \(Basic and Enterprise\)

|Release date|Feature|Description|Documentation|
|------------|-------|-----------|-------------|
|2019-12-18|Console|A new version of the console is available, including the following updates: -   In the left-side navigation pane, **Anti-DDoS Basic** is changed to **Anti-DDoS Services**.
-   In the left-side navigation pane, the **Basic Protection** \> **Instances** page is changed to the **Assets** page. On the Assets page, the content of **DDoS Attack Protection Information** is updated.
-   In the left-side navigation pane, the **Protection Package** \> **Security Report**, **Protection Package** \> **Protection Packages**, **Protection Package** \> **Traffic Packages**, and **Protection Package** \> **Operation Logs** pages are changed to the **Anti-DDoS Origin** \> **Manage Instances** page.
-   In the left-side navigation pane, the following pages are added:
    -   **Anti-DDoS Services** \> **Anti-DDoS Pro**: directs you to the Anti-DDoS Pro console.
    -   **Anti-DDoS Services** \> **Anti-DDoS Premium**: directs you to the Anti-DDoS Premium console.
    -   **Industry-specific** \> **Game Shield**: directs you to the GameShield console.
    -   How to Choose: directs you to the topic **Scenario-specific selection of anti-DDoS solutions**.

|[Assets](/intl.en-US/Anti-DDoS Origin User Guide/Assets.md)|
|2019-12-18|Assets|The **Basic Protection** \> **Instances** page is changed to the **Assets** page. The Assets page displays the protection status of activated assets under an Alibaba Cloud account. The page provides a quick overview of security risks for your assets from DDoS attacks. On the page, you can also increase the protection capacity for a specified asset. Supported assets include Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, and elastic IP Addresses \(EIPs\).

|[Assets](/intl.en-US/Anti-DDoS Origin User Guide/Assets.md)|
|2019-12-18|Elastic protection|The preset protection threshold is changed to the elastic protection threshold. The console no longer shows a score in the **Security Credibility** field. In elastic protection mode, Anti-DDoS Origin allows you to assign an extra protection capacity for your assets based on the original basic protection capacity that is provided free of charge. The extra protection capacity assigned for an asset changes based on several factors. The factors include the number of resources that an anti-DDoS cluster consumes, available resources, historical attacks that your assets encounter, and security credits of your account.

|[Security Credibility](/intl.en-US/Legal Terms/Anti-DDoS Origin/Security Credibility.md)|

