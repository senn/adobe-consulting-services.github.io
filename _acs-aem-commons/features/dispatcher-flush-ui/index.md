---
layout: acs-aem-commons_feature
title: Dispatcher Flush UI
description: The convenience of flushing by yourself
date: 2013-10-02
redirect_from: /acs-aem-commons/features/dispatcher-flush-ui.html
feature-tags: administration standard
tags: aemcs-incompatible
initial-release: 1.2.0
---

## Purpose

Allow AEM authors (or "super authors") to flush parts of the dispatcher cache manually without the involvement of IT Operations.

## How to Use

* Log in to AEM Author
* Navigate to Tools
* Under the `acs-commmons` folder, create a folder named "dispatcher-flush" (NOTE: As of 1.6.0, this folder is created automatically)
* Under the `dispatcher-flush` folder, create a new Page of Template type "Dispatcher Flush"
	* Note: After v1.2.0, Dispatcher Flush templates creation will be limited to:
		* /etc/acs-commons/dispatcher-flush
		* /etc/dispatcher-flush
		* /etc/replication
![image](images/new-page.png)
* Give the page a logical naming ("Brand X Site" or "Brand Y Site")
* Open the page and edit the component
![image](images/dialog.png)
	* Add all the paths you would like to flush for the particular site
	* Select the "flush type"
	  * `Invalidate Cache` touches .stat files invalidating the cache
	  * `Delete Cache` deletes the files from Dispatcher
* Verify that all the expected Dispatcher Flush Agents are listed below the configuration and the paths are correct.
![image](images/dispatcher-flush-ui.png)
* Press the "Flush Paths" button
	* If the "Flush Paths" button does not appear something is wrong with the configuration or no Flush Agents are available.
    * Note: Resource-Only flush agents are NOT supported.
* The page will refresh indicating the successful status of your Flush request
* If there are problems, review the Dispatcher Flush Agent Logs

**Note: This requires Dispatcher Flush Replication Agents to be setup on Author. If your Dispatcher Flush agents reside on Publish, you will need to setup a parallel set on AEM Author with the setting of "Ignore Default"**

![image](images/replication-agent-config-ignore-default.png)      
