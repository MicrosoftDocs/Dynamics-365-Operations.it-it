---
title: Tipo di destinazione archivio ER
description: Questo argomento fornisce informazioni su come configurare una destinazione di archivio per ogni componente FOLDER o FILE di un formato di creazione di report elettronici (ER).
author: NickSelin
ms.date: 11/30/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 079eda04fcc41fc637419a83452db10b89ed1ab9
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5894030"
---
# <a name="archive-er-destination-type"></a><span data-ttu-id="7b34c-103">Tipo di destinazione archivio ER</span><span class="sxs-lookup"><span data-stu-id="7b34c-103">Archive ER destination type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7b34c-104">È possibile configurare una destinazione archivio per ogni componente **Cartella** o **File** di un formato ER configurato per generare documenti in uscita.</span><span class="sxs-lookup"><span data-stu-id="7b34c-104">You can configure an archive destination for each **Folder** or **File** component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="7b34c-105">In base all'impostazione di destinazione, un documento generato viene archiviato come allegato di un record dell'elenco di processi ER.</span><span class="sxs-lookup"><span data-stu-id="7b34c-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span> <span data-ttu-id="7b34c-106">Per visualizzare i risultati, andare su **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi di creazione report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7b34c-106">To view the results, go to **Organization administration** \> **Electronic reporting** \> **Electronic reporting jobs**.</span></span>

<span data-ttu-id="7b34c-107">È possibile utilizzare questa opzione per inviare il documento generato a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7b34c-107">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="7b34c-108">Impostare **Abilitato** su **Sì** per inviare l'output a una destinazione definita dal tipo di documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="7b34c-108">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="7b34c-109">Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="7b34c-109">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="7b34c-110">I [tipi](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) di documento vengono definiti in **Amministrazione organizzazione** \> **Gestione documenti** \> **Tipi di documento**.</span><span class="sxs-lookup"><span data-stu-id="7b34c-110">You define document [types](../../fin-ops/organization-administration/configure-document-management.md#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="7b34c-111">La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="7b34c-111">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="7b34c-112">[![Pagina Tipi di documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="7b34c-112">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="7b34c-113">Il percorso posizione determina dove viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="7b34c-113">The location determines where the file is saved.</span></span> <span data-ttu-id="7b34c-114">Una volta abilitata la destinazione **Archivio**, i risultati possono essere salvati nell'archivio processi.</span><span class="sxs-lookup"><span data-stu-id="7b34c-114">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="7b34c-115">È possibile visualizzare i risultati in **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi archiviati di creazione report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7b34c-115">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="7b34c-116">Selezionare un tipo di documento per l'archivio processi selezionando **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** \> **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7b34c-116">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="7b34c-117">Per ulteriori informazioni, vedere [Configurare il framework di report elettronici (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="7b34c-117">For more information, see [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="7b34c-118">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b34c-118">SharePoint</span></span>

<span data-ttu-id="7b34c-119">È possibile salvare un file in una cartella designata di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b34c-119">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="7b34c-120">Per definire il server di SharePoint predefinito selezionare **Amministrazione organizzazione** \> **Gestione documenti** \> **Parametri di gestione documenti**.</span><span class="sxs-lookup"><span data-stu-id="7b34c-120">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="7b34c-121">Nella scheda **SharePoint** configurare la cartella di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="7b34c-121">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="7b34c-122">Quindi, è possibile selezionarla come cartella in cui verrà salvato l'output ER.</span><span class="sxs-lookup"><span data-stu-id="7b34c-122">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="7b34c-123">La posizione **SharePoint** deve essere selezionata in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="7b34c-123">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="7b34c-124">[![Selezione di una cartella SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="7b34c-124">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="7b34c-125">Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="7b34c-125">Azure Storage</span></span>

<span data-ttu-id="7b34c-126">Quando il percorso del tipo di documento è impostato su **Archiviazione di Azure**, è possibile salvare un file in Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="7b34c-126">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

> [!NOTE] 
> <span data-ttu-id="7b34c-127">Il framework ER archivia in modo permanente i file nell'archiviazione BLOB di Azure a differenza del Framework di gestione dei dati che applica i criteri di conservazione di sette giorni per i documenti che devono essere elaborati.</span><span class="sxs-lookup"><span data-stu-id="7b34c-127">The ER framework permanently stores files in Azure Blob storage unlike the Data management framework that applies the seven-day retention policy for documents that must be processed.</span></span> <span data-ttu-id="7b34c-128">Per ulteriori informazioni, vedere [API per ottenere lo stato del messaggio](../data-entities/recurring-integrations.md#api-for-getting-message-status) e [API di controllo dello stato](../data-entities/data-management-api.md#status-check-api).</span><span class="sxs-lookup"><span data-stu-id="7b34c-128">For more information, see [API for getting message status](../data-entities/recurring-integrations.md#api-for-getting-message-status) and [Status check API](../data-entities/data-management-api.md#status-check-api).</span></span> <span data-ttu-id="7b34c-129">I file correlati a ER verranno archiviati nell'archivio BLOB di Azure come allegati dei record della tabella dell'applicazione per tutto il tempo necessario.</span><span class="sxs-lookup"><span data-stu-id="7b34c-129">The ER-related files will be stored in Azure Blob storage as attachments of application table records as long as necessary.</span></span> <span data-ttu-id="7b34c-130">Un singolo file verrà eliminato dall'archiviazione BLOB di Azure insieme al record della tabella dell'applicazione a cui era allegato il file.</span><span class="sxs-lookup"><span data-stu-id="7b34c-130">A single file will be deleted from Azure Blob storage along with the application table record that this file was attached to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7b34c-131">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b34c-131">Additional resources</span></span>

- [<span data-ttu-id="7b34c-132">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="7b34c-132">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="7b34c-133">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="7b34c-133">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="7b34c-134">Configurare la gestione dei documenti</span><span class="sxs-lookup"><span data-stu-id="7b34c-134">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]