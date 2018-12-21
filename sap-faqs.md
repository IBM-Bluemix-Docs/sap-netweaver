---



copyright:
  years: 2017, 2018
lastupdated: "2018-12-21"


---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# FAQs: SAP on IBM Cloud
{: #faqs}

## Do I need DB2 to run SAP NetWeaver on {{site.data.keyword.cloud_notm}}?
{: faq}

Check [SAP Note 2414097 ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://launchpad.support.sap.com/#/notes/2414097){: new_window} regularly and also reference [SAP Product Availability Matrix ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://apps.support.sap.com/sap/support/pam){: new_window}. Be aware of the provided operating system in the SAP Note, because different sets of service packs are required by your database.

## Why was {{site.data.keyword.Db2_on_Cloud_short}} chosen for certification for {{site.data.keyword.cloud_notm}}?
{: faq}

Because {{site.data.keyword.Db2_on_Cloud_long_notm}} is an {{site.data.keyword.IBM_notm}} product and {{site.data.keyword.cloud_notm}} is part of {{site.data.keyword.IBM_notm}} it was chosen for our certification..

## Can I split my distributed SAP environment between different data centers?
{: faq}

For a distributed SAP installation, it is best to have all nodes in the same data center and VLAN segment. Deviations from this can yield latency and timeouts, which would render your SAP system unresponsive.

## Can I achieve SAP high availability as defined by SAP architecture?
{: faq}

The only supported high availability architecture is the scaling of application servers. Currently, there is no hardware enabled for high availability support.

## Can I download the SAP distribution software directly from {{site.data.keyword.cloud_notm}}?
{: faq}

Currently, we are not offering a direct link with the [SAP Service Marketplace ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://websmp201.sap-ag.de/){: new_window}. Therefore, you should download the distribution DVDs just like you do today for an on-premise deployment.
