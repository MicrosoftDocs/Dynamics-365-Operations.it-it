---
title: Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni
description: In questo argomento viene descritto come modificare e controllare le transazioni di ordini online e ordini cliente asincroni in Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.openlocfilehash: 0fee5ef7ad61e9581e7b2797bb1bd26b1a48ddbd
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5221776"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="93eb4-103">Modificare e controllare le transazioni di ordini online e di ordini cliente asincroni</span><span class="sxs-lookup"><span data-stu-id="93eb4-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="93eb4-104">In questo argomento viene descritto come modificare e controllare le transazioni di ordini online e ordini cliente asincroni in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="93eb4-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="93eb4-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="93eb4-105">Overview</span></span>

<span data-ttu-id="93eb4-106">Tra le versioni 10.0.5 e 10.0.6 di Commerce è stato aggiunto il supporto per la modifica delle transazioni cash-and-carry (come vendite e resi) e transazioni di gestione di cassa (come l'immissione del fondo cassa e la rimozione del metodo di pagamento).</span><span class="sxs-lookup"><span data-stu-id="93eb4-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="93eb4-107">In Commerce versione 10.0.7 è stato aggiunto il supporto per la modifica delle transazioni degli ordini online e delle transazioni degli ordini cliente asincroni.</span><span class="sxs-lookup"><span data-stu-id="93eb4-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="93eb4-108">Modificare e controllare le transazioni degli ordini</span><span class="sxs-lookup"><span data-stu-id="93eb4-108">Edit and audit order transactions</span></span>

<span data-ttu-id="93eb4-109">Per modificare e controllare le transazioni di ordini in Commerce Headquarters, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="93eb4-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="93eb4-110">Installare [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="93eb4-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="93eb4-111">Nella pagina **Parametri di vendita al dettaglio**, nella scheda **Ordini cliente**, nella Scheda dettaglio **Ordine**, specificare un codice sospensione per **Codice sospensione per errori di sincronizzazione dell'ordine**.</span><span class="sxs-lookup"><span data-stu-id="93eb4-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="93eb4-112">Aprire l'area di lavoro **Dati finanziari punto vendita**.</span><span class="sxs-lookup"><span data-stu-id="93eb4-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="93eb4-113">I riquadri **Errori di sincronizzazione ordini online** ed **Errori di sincronizzazione ordini cliente** forniscono una visualizzazione prefiltrata della pagina delle transazioni di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="93eb4-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="93eb4-114">Ciascuno mostra i record delle transazioni che non hanno completato la sincronizzazione per il tipo di ordine corrispondente.</span><span class="sxs-lookup"><span data-stu-id="93eb4-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="93eb4-115">Aprire la pagina **Errori di sincronizzazione ordini online** o la pagina **Errori di sincronizzazione ordini cliente**.</span><span class="sxs-lookup"><span data-stu-id="93eb4-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="93eb4-116">Selezionare un record per visualizzare i dettagli dell'errore di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="93eb4-117">La Scheda dettaglio **Stato sincronizzazione** fornisce i seguenti dettagli sull'errore:</span><span class="sxs-lookup"><span data-stu-id="93eb4-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="93eb4-118">Stato ordine in sospeso</span><span class="sxs-lookup"><span data-stu-id="93eb4-118">Pending order status</span></span>
    - <span data-ttu-id="93eb4-119">Dettagli errori ordini</span><span class="sxs-lookup"><span data-stu-id="93eb4-119">Order error details</span></span>
    - <span data-ttu-id="93eb4-120">Data e ora modifica</span><span class="sxs-lookup"><span data-stu-id="93eb4-120">Modified date and time</span></span>
    - <span data-ttu-id="93eb4-121">Conteggio tentativi</span><span class="sxs-lookup"><span data-stu-id="93eb4-121">Retry count</span></span>

1. <span data-ttu-id="93eb4-122">Se i dettagli sull'errore indicano che il record deve essere corretto, selezionare **Componente aggiuntivo per Office** e quindi selezionare **Modifica transazione selezionata**.</span><span class="sxs-lookup"><span data-stu-id="93eb4-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="93eb4-123">Viene aperto un file Excel che mostra i dettagli della transazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="93eb4-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="93eb4-124">Se la transazione che viene modificata è una transazione di ordine online, il file Excel contiene i seguenti fogli di lavoro:</span><span class="sxs-lookup"><span data-stu-id="93eb4-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="93eb4-125">**Transazione**: questo foglio di lavoro contiene i dettagli dell'intestazione per la transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-126">**Transazione di vendita**: questo foglio di lavoro contiene i dettagli delle righe per la transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-127">**Transazioni di pagamento**: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="93eb4-128">**Transazioni di sconto**: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-129">**Transazioni fiscali**: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-130">**Transazioni spese**: questo foglio di lavoro contiene i dati relativi alle spese della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="93eb4-131">Se la transazione che viene modificata è una transazione di ordine cliente asincrono, il file Excel contiene i seguenti fogli di lavoro:</span><span class="sxs-lookup"><span data-stu-id="93eb4-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="93eb4-132">**Righe**: questo foglio di lavoro contiene i dettagli delle righe e dell'intestazione per la transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-133">**Pagamenti**: questo foglio di lavoro contiene i dettagli delle righe di pagamento della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="93eb4-134">**Sconti**: questo foglio di lavoro contiene i dettagli relativi agli sconti della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-135">**Imposte**: questo foglio di lavoro contiene i dettagli relativi alle imposte della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="93eb4-136">**Spese**: questo foglio di lavoro contiene i dati relativi alle spese della transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="93eb4-137">Nel file Excel, nel campo **Stato ordine in sospeso**, immetti **Modifica** e quindi pubblica la modifica.</span><span class="sxs-lookup"><span data-stu-id="93eb4-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="93eb4-138">In questo modo, impedisci che il processo **Sincronizza ordine** in esecuzione in modalità batch ignori questo record durante l'elaborazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="93eb4-139">Nel file di Excel, modificare i campi appropriati, quindi caricare i dati nuovamente in Commerce Headquarters utilizzando la funzionalità di pubblicazione del componente aggiuntivo Dynamics Excel.</span><span class="sxs-lookup"><span data-stu-id="93eb4-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="93eb4-140">Una volta pubblicati i dati, le modifiche si rifletteranno nel sistema.</span><span class="sxs-lookup"><span data-stu-id="93eb4-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="93eb4-141">Durante la pubblicazione non viene effettuata alcuna convalida delle modifiche apportate dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="93eb4-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="93eb4-142">È possibile visualizzare un audit trail completo delle modifiche selezionando **Visualizza audit trail** nell'intestazione **Transazione di vendita al dettaglio** per le modifiche a livello di intestazione e nella sezione e nel record pertinenti nella pagina della transazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="93eb4-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="93eb4-143">Ad esempio, tutte le modifiche relative alle righe di vendita verranno visualizzate nella pagina **Transazioni di vendita**, mentre tutte le modifiche relative ai pagamenti verranno visualizzate nella pagina **Transazioni di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="93eb4-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="93eb4-144">I seguenti dettagli del controllo vengono mantenuti per le modifiche:</span><span class="sxs-lookup"><span data-stu-id="93eb4-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="93eb4-145">Data e ora modifica</span><span class="sxs-lookup"><span data-stu-id="93eb4-145">Modified date and time</span></span>
    - <span data-ttu-id="93eb4-146">Campo</span><span class="sxs-lookup"><span data-stu-id="93eb4-146">Field</span></span>
    - <span data-ttu-id="93eb4-147">Valore precedente</span><span class="sxs-lookup"><span data-stu-id="93eb4-147">Old value</span></span>
    - <span data-ttu-id="93eb4-148">Nuovo valore</span><span class="sxs-lookup"><span data-stu-id="93eb4-148">New value</span></span>
    - <span data-ttu-id="93eb4-149">Autore modifica</span><span class="sxs-lookup"><span data-stu-id="93eb4-149">Modified by</span></span>

1. <span data-ttu-id="93eb4-150">Dopo aver apportato e pubblicato le modifiche, selezionare **Sincronizza ordine** per avviare immediatamente il processo di sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="93eb4-151">In alternativa, è possibile attendere che il processo di sincronizzazione in esecuzione in modalità batch elabori la transazione.</span><span class="sxs-lookup"><span data-stu-id="93eb4-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="93eb4-152">Per impostazione predefinita, dopo che gli ordini sono stati sincronizzati, vengono messi in uno stato di sospensione, in base al codice di sospensione definito nei parametri di Commerce.</span><span class="sxs-lookup"><span data-stu-id="93eb4-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="93eb4-153">La sospensione sugli ordini deve essere rimossa prima che gli ordini possano essere ulteriormente elaborati per l'evasione o altre operazioni.</span><span class="sxs-lookup"><span data-stu-id="93eb4-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93eb4-154">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="93eb4-154">Additional resources</span></span>

[<span data-ttu-id="93eb4-155">Modificare e controllare le transazioni di cash-and-carry e di gestione di cassa</span><span class="sxs-lookup"><span data-stu-id="93eb4-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="93eb4-156">Modificare le dimensioni finanziarie per le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="93eb4-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="93eb4-157">Creare una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="93eb4-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="93eb4-158">Aggiungere campi a una cartella di lavoro di Excel per modificare le transazioni di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="93eb4-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]