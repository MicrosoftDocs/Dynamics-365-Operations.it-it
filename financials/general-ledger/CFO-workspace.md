---
title: Aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario
description: "In questo argomento viene descritto come aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario, in modo da utilizzarle per la contabilità generale e i report relativi al budget."
author: aolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.2.0
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 05fd7ce5293b3a300aabc073a6e492c5804d1897
ms.contentlocale: it-it
ms.lasthandoff: 08/03/2017

---

# <a name="add-financial-dimensions-to-the-cfo-workspace"></a><span data-ttu-id="0ce3a-103">Aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario</span><span class="sxs-lookup"><span data-stu-id="0ce3a-103">Add financial dimensions to the CFO workspace</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0ce3a-104">In questo argomento viene descritto come aggiungere dimensioni finanziarie all'area di lavoro Responsabile finanziario, in modo da utilizzarle per la contabilità generale e i report relativi al budget.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-104">This topic explains how to add financial dimensions to the Chief Financial Officer (CFO) workspace, so that they can be used for the ledger and budget reports.</span></span> <span data-ttu-id="0ce3a-105">L'area di lavoro Responsabile finanziario include la scheda **Panoramica** e la scheda **Finanziario**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-105">The CFO workspace has an **Overview** tab and a **Financial** tab.</span></span> <span data-ttu-id="0ce3a-106">I report in queste due schede sono supportati da due misure: LedgerActivityMeasure e BudgetActivityMeasure.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-106">The reports on these two tabs are backed by two measures: LedgerActivityMeasure and BudgetActivityMeasure.</span></span> <span data-ttu-id="0ce3a-107">L'aggiornamento di luglio 2017 di Microsoft Dynamics 365 for Finance and Operations, Enterprise edition include una relazione tra queste due misure e l'entità DimensionCombinationEntity.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-107">In Microsoft Dynamics 365 for Finance and Operations, Enterprise edition July 2017 update, there is a relation between those two measures and the DimensionCombinationEntity entity.</span></span> <span data-ttu-id="0ce3a-108">È quindi possibile selezionare le dimensioni.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-108">Therefore, you can select dimensions.</span></span>

1. <span data-ttu-id="0ce3a-109">In Finance and Operations, nella pagina **Archivio entità**, aggiornare le misure **LedgerActivityMeasure** e **BudgetActivityMeasure**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-109">In Finance and Operations, on the **Entity Store** page, update the **LedgerActivityMeasure** and the **BudgetActivityMeasure** measures.</span></span>
2. <span data-ttu-id="0ce3a-110">In Microsoft Visual Studio, aprire Application Explorer e cercare **LedgerCFO**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-110">In Microsoft Visual Studio, open Application Explorer, and search for **LedgerCFO**.</span></span>
3. <span data-ttu-id="0ce3a-111">In **Risorse**, aprire **LedgerCFOWorkspacePBIX**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-111">Under **Resources**, open **LedgerCFOWorkspacePBIX**.</span></span>
4. <span data-ttu-id="0ce3a-112">Quando la risorsa viene aperta in Microsoft Power BI Desktop, selezionare **Recupera dati**, quindi **Database SQL Server** e infine **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-112">When the resource opens in Microsoft Power BI desktop, select **Get Data**, select **SQL Server database**, and then select **Connect**.</span></span>
5. <span data-ttu-id="0ce3a-113">Immettere il nome del server e **AxDW** come database.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-113">Enter the server name, and enter **AxDW** as the database.</span></span> <span data-ttu-id="0ce3a-114">Selezionare **DirectQuery** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-114">Select **DirectQuery**, and then select **OK**.</span></span>
6. <span data-ttu-id="0ce3a-115">Cercare e selezionare **LedgerActivityMeasure\_DimensionCombination** e quindi selezionare **Carica**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-115">Search for and select **LedgerActivityMeasure\_DimensionCombination**, and then select **Load**.</span></span>

    > [!TIP]
    > <span data-ttu-id="0ce3a-116">Nell'elenco **Campi**, rinominare la tabella **Dimensioni finanziarie** per un'agevole identificazione.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-116">In the **Fields** list, rename the table **Financial dimensions**, so that it's easy to identify.</span></span>

7. <span data-ttu-id="0ce3a-117">Selezionare **Gestisci relazioni** e quindi selezionare **Nuova**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-117">Select **Manage Relationships**, and then select **New**.</span></span>
8. <span data-ttu-id="0ce3a-118">Nel primo campo, selezionare **Attività di contabilità generale** e quindi selezionare **LedgerDimension**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-118">In the first field, select **General Ledger Activities**, and then select **LedgerDimension**.</span></span>
9. <span data-ttu-id="0ce3a-119">Nel secondo campo, selezionare **LedgerActivityMeasure\_DimensionCombination** (o **Dimensioni finanziarie** se la tabella è stata rinominata).</span><span class="sxs-lookup"><span data-stu-id="0ce3a-119">In the second field, select **LedgerActivityMeasure\_DimensionCombination** (or **Financial dimensions** if you renamed the table).</span></span> <span data-ttu-id="0ce3a-120">Selezionare l'intestazione **DimensionCombinationRECID**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-120">Select the  **DimensionCombinationRECID** header.</span></span>
10. <span data-ttu-id="0ce3a-121">Nel campo **Cardinalità**, selezionare **Molti a uno**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-121">In the **Cardinality** field, select **Many to One**.</span></span>
11. <span data-ttu-id="0ce3a-122">Impostare **Direzione filtro incrociato** su **Singola**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-122">Change the **Cross filter direction** value to **Single**.</span></span>
12. <span data-ttu-id="0ce3a-123">Selezionare **Imposta come relazione attiva** e **Considera integrità referenziale**, selezionare **OK** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-123">Select both **Make this relationship active** and **Assume referential integrity**, select **OK**, and then select **Close**.</span></span>

    <span data-ttu-id="0ce3a-124">[![Creare una relazione](./media/Create-relationship.png)](./media/Create-relationship.png)</span><span class="sxs-lookup"><span data-stu-id="0ce3a-124">[![Create a relationship](./media/Create-relationship.png)](./media/Create-relationship.png)</span></span>

13. <span data-ttu-id="0ce3a-125">Nell'elenco **Campi**, dovrebbe essere visualizzate la tabella e le dimensioni finanziarie disponibili.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-125">In the **Fields** list, you should see the table and the available financial dimensions.</span></span> <span data-ttu-id="0ce3a-126">Trascinare le dimensioni finanziarie desiderate nei filtri a livello di report.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-126">Drag the financial dimensions that you want to the report-level filters.</span></span>
14. <span data-ttu-id="0ce3a-127">Salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-127">Save your changes.</span></span>
15. <span data-ttu-id="0ce3a-128">Nella struttura a oggetti applicativi (AOT), fare clic con il pulsante destro del mouse sul progetto e scegliere **Sincronizza**.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-128">In the Application Object Tree (AOT), right-click your project, and then select **Synchronize**.</span></span>
16. <span data-ttu-id="0ce3a-129">Generare il progetto, quindi aprire l'applicazione per visualizzare i risultati.</span><span class="sxs-lookup"><span data-stu-id="0ce3a-129">Build your project, and then open the application to view the results.</span></span>

    <span data-ttu-id="0ce3a-130">[![Area di lavoro completata](./media/workspace.png)](./media/workspace.png)</span><span class="sxs-lookup"><span data-stu-id="0ce3a-130">[![Completed workspace](./media/workspace.png)](./media/workspace.png)</span></span>
