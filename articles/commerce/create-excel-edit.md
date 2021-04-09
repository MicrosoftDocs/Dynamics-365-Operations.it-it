---
title: Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio
description: In questo argomento viene descritto come creare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: a2d41dd0470a4abae1a8238be8f1549fb094a026
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795741"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="d9f11-103">Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d9f11-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="d9f11-104">In questo argomento viene descritto come creare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d9f11-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d9f11-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="d9f11-105">Overview</span></span>

<span data-ttu-id="d9f11-106">Esiste un modello Excel predefinito a cui i clienti possono accedere da diverse parti del sistema e utilizzare per modificare e controllare le transazioni di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="d9f11-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="d9f11-107">Tuttavia, i clienti possono anche creare una cartella di lavoro Excel personalizzata per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="d9f11-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="d9f11-108">Creare e configurare una cartella di lavoro di Excel</span><span class="sxs-lookup"><span data-stu-id="d9f11-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="d9f11-109">Per creare e configurare una cartella di lavoro di Excel in modo da poter modificare le transazioni di vendita al dettaglio, effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="d9f11-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="d9f11-110">Aprire Excel e creare una cartella di lavoro vuota.</span><span class="sxs-lookup"><span data-stu-id="d9f11-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="d9f11-111">Nella scheda **Inserisci**, selezionare **Miei componenti aggiuntivi**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="d9f11-112">Nel riquadro di destra, selezionare il collegamento **Aggiungi informazioni sul server**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="d9f11-113">Immettere l'URL del server e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="d9f11-114">Se si riceve un messaggio di errore "Nessuna registrazione applet trovata", seguire questi passaggi per risolvere il problema:</span><span class="sxs-lookup"><span data-stu-id="d9f11-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="d9f11-115">In Commerce, passare a **Amministrazione sistema \> Imposta \> Parametri app di Office**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="d9f11-116">Nella Scheda dettaglio **Parametri app**, selezionare **Inizializza parametri app**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="d9f11-117">Nella finestra del messaggio di conferma, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="d9f11-118">Nella Scheda dettaglio **Applet registrati**, selezionare **Inizializza registrazione applet**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="d9f11-119">Ripetere i tre passaggi precedenti secondo le specifiche esigenze.</span><span class="sxs-lookup"><span data-stu-id="d9f11-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="d9f11-120">Selezionare **Progettazione** e quindi selezionare **Aggiungi tabella**.</span><span class="sxs-lookup"><span data-stu-id="d9f11-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="d9f11-121">In base ai dati che devono essere modificati, selezionare le entità che devono essere aggiunte alla cartella di lavoro di Excel per la modifica.</span><span class="sxs-lookup"><span data-stu-id="d9f11-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="d9f11-122">Utilizzare la tabella seguente come riferimento.</span><span class="sxs-lookup"><span data-stu-id="d9f11-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="d9f11-123">Tipo di transazione</span><span class="sxs-lookup"><span data-stu-id="d9f11-123">Transaction type</span></span> | <span data-ttu-id="d9f11-124">Entità di dati da utilizzare</span><span class="sxs-lookup"><span data-stu-id="d9f11-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="d9f11-125">Transazioni cash-and-carry, ordini online, ordini cliente asincroni, offerte cliente asincrone</span><span class="sxs-lookup"><span data-stu-id="d9f11-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="d9f11-126">Transazione (verificabile), Transazione di vendita (verificabile), Transazioni di pagamento (verificabili), Transazioni fiscali (verificabili), Transazioni di sconto (verificabili), Transazioni di addebito (verificabili)</span><span class="sxs-lookup"><span data-stu-id="d9f11-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="d9f11-127">Deposito bancario</span><span class="sxs-lookup"><span data-stu-id="d9f11-127">Bank drop</span></span> | <span data-ttu-id="d9f11-128">Transazione (verificabile), Transazioni di metodo di pagamento bancario (verificabile)</span><span class="sxs-lookup"><span data-stu-id="d9f11-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="d9f11-129">Deposito in cassaforte</span><span class="sxs-lookup"><span data-stu-id="d9f11-129">Safe drop</span></span> | <span data-ttu-id="d9f11-130">Transazione (verificabile), Transazioni di pagamento in cassaforte (verificabile)</span><span class="sxs-lookup"><span data-stu-id="d9f11-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="d9f11-131">Riepilogo incassi</span><span class="sxs-lookup"><span data-stu-id="d9f11-131">Tender declaration</span></span> | <span data-ttu-id="d9f11-132">Transazione (verificabile), Transazioni di riepilogo incassi (verificabile)</span><span class="sxs-lookup"><span data-stu-id="d9f11-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="d9f11-133">Ricavi, Spese</span><span class="sxs-lookup"><span data-stu-id="d9f11-133">Income, Expense</span></span> | <span data-ttu-id="d9f11-134">Transazione (verificabile), Transazioni ricavi/spese (verificabili), Transazioni di pagamento (verificabili)</span><span class="sxs-lookup"><span data-stu-id="d9f11-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="d9f11-135">Dichiara importo iniziale, Rimozione metodo di pagamento, Transazione fondo di cassa, Metodo di pagamento con resto, Fattura di pagamento, Deposito sul conto cliente</span><span class="sxs-lookup"><span data-stu-id="d9f11-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="d9f11-136">Transazione (verificabile), Transazioni di pagamento (verificabile)</span><span class="sxs-lookup"><span data-stu-id="d9f11-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="d9f11-137">È importante aggiungere una sola entità di dati a ciascuna cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="d9f11-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="d9f11-138">Inoltre, tutti i campi contrassegnati dal simbolo della chiave devono essere aggiunti alla cartella di lavoro pertinente.</span><span class="sxs-lookup"><span data-stu-id="d9f11-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="d9f11-139">Dopo aver configurato la cartella di lavoro, applicare i filtri richiesti.</span><span class="sxs-lookup"><span data-stu-id="d9f11-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="d9f11-140">Assicurati di applicare gli stessi filtri a tutti i fogli di lavoro nel file.</span><span class="sxs-lookup"><span data-stu-id="d9f11-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="d9f11-141">Evitare di caricare grandi quantità di dati nel file Excel.</span><span class="sxs-lookup"><span data-stu-id="d9f11-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="d9f11-142">In caso contrario, le prestazioni potrebbero risentirne ed Excel e il sistema potrebbero essere più lenti.</span><span class="sxs-lookup"><span data-stu-id="d9f11-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="d9f11-143">È consigliabile utilizzare sempre "Azienda" e "Numero rendiconto" o "Numero transazione" come filtri per il file.</span><span class="sxs-lookup"><span data-stu-id="d9f11-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="d9f11-144">Dopo aver configurato i filtri, selezionare **Aggiorna** per caricare i dati.</span><span class="sxs-lookup"><span data-stu-id="d9f11-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="d9f11-145">Modificare i dati richiesti e quindi pubblicarli.</span><span class="sxs-lookup"><span data-stu-id="d9f11-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="d9f11-146">Se il pulsante **Pubblica** non è disponibile, alcuni campi chiave probabilmente non sono stati aggiunti alla cartella di lavoro di Excel.</span><span class="sxs-lookup"><span data-stu-id="d9f11-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d9f11-147">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d9f11-147">Additional resources</span></span>

[<span data-ttu-id="d9f11-148">Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa</span><span class="sxs-lookup"><span data-stu-id="d9f11-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="d9f11-149">Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni</span><span class="sxs-lookup"><span data-stu-id="d9f11-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="d9f11-150">Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d9f11-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="d9f11-151">Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d9f11-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]