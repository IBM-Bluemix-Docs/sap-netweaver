---

copyright:
  years: 2017, 2020
lastupdated: "2020-04-17"

keywords: SAP NetWeaver, {{site.data.keyword.cloud_notm}}, {{site.data.keyword.Db2_on_Cloud_short}}, FAQs, VLAN, application server, SAP Certified, high availability, highly available

subcollection: sap-netweaver

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:external: target="_blank" .external}
{:faq: data-hd-content-type='faq'}
{:pre: .pre}
{:table: .aria-labeledby="caption"}

# FAQs: SAP on IBM Cloud
{: #faqs}

## Do I need DB2 to run SAP NetWeaver on {{site.data.keyword.cloud_notm}}?
{: faq}

Check [SAP Note 2414097](https://launchpad.support.sap.com/#/notes/2414097){: external} regularly and also reference [SAP Product Availability Matrix](https://support.sap.com/en/release-upgrade-maintenance.html#section_1969201630){: external}. Be aware of the provided operating system in the SAP Note, because different sets of service packs are required by your database.

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

Currently, we don't have a direct link for SAP software downloads. You download the distribution DVDs just like you do today for an on-premise deployment.
