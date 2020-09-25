---
title: Tipo di destinazione archivio ER
description: In questo argomento vengono fornite informazioni su come configurare una destinazione archivio per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.
author: NickSelin
manager: AnnBe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: DocuType, ERSolutionTable, ERFormatDestinationTable
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8797a68507a5116c6adbf1f2d805838fa507958c
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745587"
---
# <a name="archive-destination"></a><span data-ttu-id="9c6bb-103">Destinazione archivio</span><span class="sxs-lookup"><span data-stu-id="9c6bb-103">Archive destination</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9c6bb-104">È possibile configurare una destinazione archivio per ogni componente CARTELLA o FILE di un formato ER configurato per generare documenti in uscita.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-104">You can configure an archive destination for each FOLDER or FILE component of an Electronic reporting (ER) format that is configured to generate outbound documents.</span></span> <span data-ttu-id="9c6bb-105">In base all'impostazione di destinazione, un documento generato viene archiviato come allegato di un record dell'elenco di processi ER.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-105">Based on the destination setting, a generated document is stored as an attachment of a record of the ER jobs list.</span></span>

<span data-ttu-id="9c6bb-106">È possibile utilizzare questa opzione per inviare il documento generato a una cartella di Microsoft SharePoint o Archiviazione di Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-106">You can use this option to send the generated document to a Microsoft SharePoint folder or Microsoft Azure Storage.</span></span> <span data-ttu-id="9c6bb-107">Impostare **Abilitato** su **Sì** per inviare l'output a una destinazione definita dal tipo di documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-107">Set **Enabled** to **Yes** to send output to a destination that is defined by the selected document type.</span></span> <span data-ttu-id="9c6bb-108">Solo tipi di documento in cui il gruppo è impostato su **File** sono disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-108">Only document types where the group is set to **File** are available for selection.</span></span> <span data-ttu-id="9c6bb-109">I [tipi](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) di documento vengono definiti in **Amministrazione organizzazione** \> **Gestione documenti** \> **Tipi di documento**.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-109">You define document [types](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) at **Organization administration** \> **Document management** \> **Document types**.</span></span> <span data-ttu-id="9c6bb-110">La configurazione per le destinazioni ER è lo stessa della configurazione del sistema di gestione documenti.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-110">The configuration for ER destinations is the same as the configuration for the document management system.</span></span>

<span data-ttu-id="9c6bb-111">[![Pagina Tipi di documento](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span><span class="sxs-lookup"><span data-stu-id="9c6bb-111">[![Document types page](./media/ER_Destinations-SharePointDocuType.png)](./media/ER_Destinations-SharePointDocuType.png)</span></span>

<span data-ttu-id="9c6bb-112">Il percorso posizione determina dove viene salvato il file.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-112">The location determines where the file is saved.</span></span> <span data-ttu-id="9c6bb-113">Una volta abilitata la destinazione **Archivio**, i risultati possono essere salvati nell'archivio processi.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-113">After the **Archive** destination is enabled, the results can be saved in the Job archive.</span></span> <span data-ttu-id="9c6bb-114">È possibile visualizzare i risultati in **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Processi archiviati di creazione report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-114">You can view the results at **Organization administration** \> **Electronic reporting** \> **Electronic reporting archived jobs**.</span></span>

> [!NOTE]
> <span data-ttu-id="9c6bb-115">Selezionare un tipo di documento per l'archivio processi selezionando **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici** \> **Parametri per la creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-115">Select a document type for the Job archive by navigating to **Organization administration** \> **Workspaces** \> **Electronic reporting** \> **Electronic reporting parameters**.</span></span> <span data-ttu-id="9c6bb-116">Per ulteriori informazioni, vedere [Configurare il framework di report elettronici (ER)](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span><span class="sxs-lookup"><span data-stu-id="9c6bb-116">For more information, [Configure the Electronic reporting (ER) framework](electronic-reporting-er-configure-parameters.md#prerequisites-for-er-setup).</span></span>

## <a name="sharepoint"></a><span data-ttu-id="9c6bb-117">SharePoint</span><span class="sxs-lookup"><span data-stu-id="9c6bb-117">SharePoint</span></span>

<span data-ttu-id="9c6bb-118">È possibile salvare un file in una cartella designata di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-118">You can save a file in a designated SharePoint folder.</span></span> <span data-ttu-id="9c6bb-119">Per definire il server di SharePoint predefinito selezionare **Amministrazione organizzazione** \> **Gestione documenti** \> **Parametri di gestione documenti**.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-119">To define the default SharePoint server, go to **Organization administration** \> **Document management** \> **Document management parameters**.</span></span> <span data-ttu-id="9c6bb-120">Nella scheda **SharePoint** configurare la cartella di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-120">On the **SharePoint** tab, configure the SharePoint folder.</span></span> <span data-ttu-id="9c6bb-121">Quindi, è possibile selezionarla come cartella in cui verrà salvato l'output ER.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-121">Then, you can select it as the folder where the ER output will be saved.</span></span> <span data-ttu-id="9c6bb-122">La posizione **SharePoint** deve essere selezionata in questo tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-122">The **SharePoint** location must be selected in this document type.</span></span>

<span data-ttu-id="9c6bb-123">[![Selezione di una cartella SharePoint](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span><span class="sxs-lookup"><span data-stu-id="9c6bb-123">[![Selecting a SharePoint folder](./media/ER_Destinations-SharePointDocuTypeLocation.png)](./media/ER_Destinations-SharePointDocuTypeLocation.png)</span></span>

## <a name="azure-storage"></a><span data-ttu-id="9c6bb-124">Archiviazione di Azure</span><span class="sxs-lookup"><span data-stu-id="9c6bb-124">Azure Storage</span></span>

<span data-ttu-id="9c6bb-125">Quando il percorso del tipo di documento è impostato su **Archiviazione di Azure**, è possibile salvare un file in Archiviazione di Azure.</span><span class="sxs-lookup"><span data-stu-id="9c6bb-125">When the document type location is set to **Azure storage**, you can save a file to Azure Storage.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9c6bb-126">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9c6bb-126">Additional resources</span></span>

- [<span data-ttu-id="9c6bb-127">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="9c6bb-127">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="9c6bb-128">Destinazioni dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="9c6bb-128">Electronic reporting (ER) destinations</span></span>](electronic-reporting-destinations.md)
- [<span data-ttu-id="9c6bb-129">Configurare la gestione dei documenti</span><span class="sxs-lookup"><span data-stu-id="9c6bb-129">Configure document management</span></span>](../../fin-ops/organization-administration/configure-document-management.md)
