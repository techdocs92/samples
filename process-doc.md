# Technical Standard: Hardware Product Models

_Hardware Asset Management_ (_HAM) Hardware Product Models_, defines the process used to create, update, and publish hardware models in ServiceNow. This document is part of TVA’s broader asset management approach, which is defined in _TVA-SPP-12.405 – IT Asset Procurement & Management_.

A product model is a specific version or configuration of a hardware product. Product models allow you to define whether a product is tracked as an asset, a configuration item (CI), a consumable, or not tracked at all. In addition, you can define the CI and asset class to capture configuration information.

Hardware requests submitted from the service catalog (TechNow) are based on hardware models defined in ServiceNow. For more information, see _Tech Standard: HAM Request and Receive_. For information about hardware installation and retirement, see _Tech Standard: HAM Install and Retire_.

## Purpose

The primary goal of the Hardware Asset Management (HAM) process is to standardize the asset lifecycle as it pertains to requesting, procurement, receiving, installation, retirement, and disposal. This includes tracking and reporting on the data attributes relating to ownership, status, and location of hardware assets and associated maintenance contracts.

## Scope

This Tech Standard defines the process for _Maintain Hardware Product Model_, which is comprised of the following activities:

*   Analyze Product Information
*   Update Hardware Model
*   Create New Hardware Model and Substitutes
*   Complete Hardware Model
*   Create and Link Vendor Catalog Item
*   Publish Hardware Model into Catalog

## Exceptions

There are no exceptions to the processes defined in this Tech Standard.

# Standard Detail

Hardware models are specific versions of an asset used for managing and tracking assets through various ServiceNow applications, such as CMDB, procurement and service catalog. A hardware model can include one or more model categories, which define the attributes collected and maintained for an item, as well as the extension table where the item is stored.

## Maintain Hardware Product Models

The _Maintain Hardware Product Models_ process consists of the following activities:

|  | Activity | Role (TVA) | Role (ITIL) | Procedure |
| --- | --- | --- | --- | --- |
| 1 | Analyze Product Information | Hardware Asset Owner (E)ITAM Specialist, Hardware Ordering (S) | Asset AnalystProcurement Manager | Review content of product notification, such as:Report of products constrained in the supply chain.Notification of upcoming product retirement and replacement product information.Notification of the end of support for a Hardware Model (no longer supported by the vendor).Notification of the end of life for a hardware model (no longer supported by the IT organization).Notification of approved products to support hardware refresh activities.Identify newly approved products, replacement products, substitute products, products due to be retired from sales or support, and products that have reached their end-of-life in the IT environment. |
| 2 | Update Hardware Model | Hardware Asset Owner (E)ITAM Administrator, Developer (S) | Asset AnalystAsset Manager | Update the product model status for hardware models that are end-of-life, end-of-sales, or no longer supported by a vendor.Notify the Catalog Administrator of the status changes to ensure impacted catalog items are updated.Record details of substitute products on an existing hardware model.Note: The normalization process should be used to enhance this data in future releases. |
| 3 | Create New Hardware Model and Substitutes | Hardware Asset Owner (E)ITAM Administrator, Developer (S) | Asset AnalystAsset Manager | For new products that are approved for use in a production environment, create new hardware model. Key data attributes include:ManufacturerModel / model numberModel category (computer, server)Asset tracking strategy (whether an asset record is required for a specific model)Model componentsMaximo Attributes:External PO descriptionAcquisition methodModel typeEnergy Star ratingModel numberBarcodeCLINEstablish if any substitute products require association with the new hardware model, in the event that the primary model is unavailable in the supply chain or not in stock. |
| 4 | Complete Hardware Model | Hardware Asset Owner (E)ITAM Administrator, Developer (S) | Asset AnalystAsset Manager | Add data attributes to the hardware model that are required to support service and business management process activities:Warranty expiration dateRefresh scheduleFor new hardware models:Work with the Catalog Administrator to determine if the hardware model needs to be added to the hardware catalog.Determine if stock rules need to be set up for minimum/maximum levels.Determine if the new model needs to be linked with existing models.Determine if the item should only be available to select groups or individuals, and if any catalog approvers are required. |
| 5 | Create and Link Vendor Catalog Item | Hardware Asset Owner (E)Catalog Administrator (S) | Asset AnalystCatalog Administrator | Create new vendor catalog items for new products that are approved for use in a production environment. Key data attributes include:VendorProduct modelOut of stockProduct IDList priceVendor priceShort descriptionProduct catalog itemUPCActiveDescriptionRank tierDetermine if any vendor catalog items should be created and linked to the model for standard order items.On the catalog item, determine if a vendor should be selected for automatic orders. |
| 6 | Publish Hardware Model into Catalog | Hardware Asset Owner (E)Catalog Administrator (S) | Asset AnalystCatalog Administrator | Obtain information to publish the updated/completed hardware model into the Service Catalog:Customer priceDescription/imageHardware fulfillment workflowHardware model supplier |

# Compliance/Oversight

Manager, IT Asset Management

# Roles and Responsibilities

The following table shows the roles and responsibilities for the _Maintain Hardware Product Models_ process. It provides the ITIL-compliant role (Information Technology Infrastructure Library), the TVA equivalent position/role, and a list of associated responsibilities.

|  | Role (ITIL) | Role (TVA) | Responsibility |
| --- | --- | --- | --- |
| 1 | Asset Analyst | Hardware Asset Owner | Define assets and scope.Record and maintain assets in the repository.Monitor the repository for accuracy and consistency.Analyze data and create reports.Assist the ITAM Administrator with auditing and reporting.Collect and retain asset data for risk, cost assessment. |
| 2 | Asset Manager | ITAM Administrator, Developer | Manage key relationships with peer roles.Maintain data continuity within the IT asset repository, including asset models and asset records.Track and govern compliance of the process.Gather and report on process metrics.Escalate issues to the Program Manager.Support Tier 2 activities and coordinate with IT Commons, Helpdesk, and Field Support (FS). |
| 3 | Catalog Administrator | Catalog Administrator | Create and publish service catalog items.Maintain service versions and revisions.Set service price, cost adjustments, coordinate orders.Import and manage multi-level categories.Entitle users to request services.Define workflows, conditions.Attach questionnaire forms to service workflows. |
| 4 | Procurement Manager | ITAM Specialist, Hardware Ordering | Create purchase orders.Obtain and accept quotes from external vendors.Issue POs processed in an external ERP system.Provide PO information associated with maintenance contracts.Enter new vendor and company records in ServiceNow.Create credit card PO in ServiceNow, receive and create asset records, and reconcile statements in Concur system. |

# Definitions and Abbreviations

The following definitions and abbreviations are used or referenced in this document:

**Hardware Model**

A specific version or configuration of a hardware product.

**Service Catalog**

In TechNow, the Service Catalog is the user portal for requesting hardware. The products available in the service catalog are based on a hardware model. Some categories of catalog items are restricted by user group membership. Group membership may be added/removed with a different catalog item.

# References

KB00017100 – IT Financial Mgmt - ITAM Technical Standards, Purpose, and Overview

TVA-SPP-12.405 – IT Asset Procurement & Management

Tech Standard: HAM Request and Receive

Tech Standard: HAM Install and Retire

Work Instructions: 12.403, 12.402, 12.403, 12.404, 12.405, 12.406, 12.407, and 12.408

# Key Terms

Hardware Asset Management, HAM, Hardware Model
