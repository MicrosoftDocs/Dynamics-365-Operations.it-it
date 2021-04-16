---
title: Configurare il mapping per le colonne dello stato dell'ordine cliente
description: In questo argomento viene illustrato come configurare le colonne di stato dell'ordine cliente per la doppia scrittura.
author: dasani-madipalli
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: 9afa64df73aa17e7a15a0ee4f4529ac74bcd3c67
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750716"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-columns"></a><span data-ttu-id="3a675-103">Configurare il mapping per le colonne dello stato dell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="3a675-103">Set up the mapping for the sales order status columns</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3a675-104">Le colonne che indicano lo stato dell'ordine cliente hanno valori di enumerazione diversi in Microsoft Dynamics 365 Supply Chain Management e Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3a675-104">The columns that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="3a675-105">È necessaria una configurazione aggiuntiva per mappare queste colonne in doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="3a675-105">Additional setup is required to map these columns in dual-write.</span></span>

## <a name="columns-in-supply-chain-management"></a><span data-ttu-id="3a675-106">Colonne in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3a675-106">columns in Supply Chain Management</span></span>

<span data-ttu-id="3a675-107">In Supply Chain Management, due colonne riflettono lo stato dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3a675-107">In Supply Chain Management, two columns reflect the status of the sales order.</span></span> <span data-ttu-id="3a675-108">Le colonne che devi mappare sono **Stato** e **Stato documento**.</span><span class="sxs-lookup"><span data-stu-id="3a675-108">The columns that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="3a675-109">L'enumerazione **Stato** specifica lo stato generale dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a675-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3a675-110">Questo stato è mostrato nell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a675-110">This status is shown on the order header.</span></span>

<span data-ttu-id="3a675-111">L'enumerazione **Stato** include i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3a675-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3a675-112">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-112">Open Order</span></span>
- <span data-ttu-id="3a675-113">Consegnata</span><span class="sxs-lookup"><span data-stu-id="3a675-113">Delivered</span></span>
- <span data-ttu-id="3a675-114">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-114">Invoiced</span></span>
- <span data-ttu-id="3a675-115">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-115">Cancelled</span></span>

<span data-ttu-id="3a675-116">L'enumerazione **Stato documento** specifica il documento più recente che è stato generato per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a675-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="3a675-117">Ad esempio, se l'ordine è confermato, questo documento è una conferma dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="3a675-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="3a675-118">Se un ordine cliente viene fatturato parzialmente e la riga rimanente viene confermata, lo stato del documento rimane **Fattura**, perché la fattura viene generata in un secondo momento nel processo.</span><span class="sxs-lookup"><span data-stu-id="3a675-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="3a675-119">L'enumerazione **Stato documento** include i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="3a675-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="3a675-120">Conferma</span><span class="sxs-lookup"><span data-stu-id="3a675-120">Confirmation</span></span>
- <span data-ttu-id="3a675-121">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="3a675-121">Picking List</span></span>
- <span data-ttu-id="3a675-122">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="3a675-122">Packing Slip</span></span>
- <span data-ttu-id="3a675-123">Fattura</span><span class="sxs-lookup"><span data-stu-id="3a675-123">Invoice</span></span>

## <a name="columns-in-sales"></a><span data-ttu-id="3a675-124">colonne in Sales</span><span class="sxs-lookup"><span data-stu-id="3a675-124">columns in Sales</span></span>

<span data-ttu-id="3a675-125">In Sales, due colonne indicano lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a675-125">In Sales, two columns indicate the status of the order.</span></span> <span data-ttu-id="3a675-126">Le colonne che devi mappare sono **Stato** e **Stato elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="3a675-126">The columns that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="3a675-127">L'enumerazione **Stato** specifica lo stato generale dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="3a675-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="3a675-128">Include i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="3a675-128">It has the following values:</span></span>

- <span data-ttu-id="3a675-129">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-129">Active</span></span>
- <span data-ttu-id="3a675-130">Inviate</span><span class="sxs-lookup"><span data-stu-id="3a675-130">Submitted</span></span>
- <span data-ttu-id="3a675-131">Soddisfatto</span><span class="sxs-lookup"><span data-stu-id="3a675-131">Fulfilled</span></span>
- <span data-ttu-id="3a675-132">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-132">Invoiced</span></span>
- <span data-ttu-id="3a675-133">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-133">Cancelled</span></span>

<span data-ttu-id="3a675-134">L'enumerazione **Stato di elaborazione** è stata introdotta in modo che lo stato possa essere mappato in modo più accurato con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a675-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="3a675-135">La tabella seguente mostra la mappatura di **Stato di elaborazione** in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a675-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="3a675-136">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="3a675-136">Processing Status</span></span>   | <span data-ttu-id="3a675-137">Stato in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3a675-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="3a675-138">Stato documento in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3a675-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="3a675-139">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-139">Active</span></span>              | <span data-ttu-id="3a675-140">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-140">Open Order</span></span>                        | <span data-ttu-id="3a675-141">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="3a675-141">None</span></span>                                       |
| <span data-ttu-id="3a675-142">Confermata</span><span class="sxs-lookup"><span data-stu-id="3a675-142">Confirmed</span></span>           | <span data-ttu-id="3a675-143">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-143">Open Order</span></span>                        | <span data-ttu-id="3a675-144">Conferma</span><span class="sxs-lookup"><span data-stu-id="3a675-144">Confirmation</span></span>                               |
| <span data-ttu-id="3a675-145">Prelevato</span><span class="sxs-lookup"><span data-stu-id="3a675-145">Picked</span></span>              | <span data-ttu-id="3a675-146">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-146">Open Order</span></span>                        | <span data-ttu-id="3a675-147">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="3a675-147">Picking List</span></span>                               |
| <span data-ttu-id="3a675-148">Consegnato in parte</span><span class="sxs-lookup"><span data-stu-id="3a675-148">Partially Delivered</span></span> | <span data-ttu-id="3a675-149">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-149">Open Order</span></span>                        | <span data-ttu-id="3a675-150">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="3a675-150">Packing Slip</span></span>                               |
| <span data-ttu-id="3a675-151">Consegnata</span><span class="sxs-lookup"><span data-stu-id="3a675-151">Delivered</span></span>           | <span data-ttu-id="3a675-152">Consegnata</span><span class="sxs-lookup"><span data-stu-id="3a675-152">Delivered</span></span>                         | <span data-ttu-id="3a675-153">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="3a675-153">Packing Slip</span></span>                               |
| <span data-ttu-id="3a675-154">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="3a675-154">Partially Invoiced</span></span>  | <span data-ttu-id="3a675-155">Consegnata</span><span class="sxs-lookup"><span data-stu-id="3a675-155">Delivered</span></span>                         | <span data-ttu-id="3a675-156">Fattura</span><span class="sxs-lookup"><span data-stu-id="3a675-156">Invoice</span></span>                                    |
| <span data-ttu-id="3a675-157">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-157">Invoiced</span></span>            | <span data-ttu-id="3a675-158">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-158">Invoiced</span></span>                          | <span data-ttu-id="3a675-159">Fattura</span><span class="sxs-lookup"><span data-stu-id="3a675-159">Invoice</span></span>                                    |
| <span data-ttu-id="3a675-160">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-160">Cancelled</span></span>           | <span data-ttu-id="3a675-161">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-161">Cancelled</span></span>                         | <span data-ttu-id="3a675-162">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="3a675-162">Not applicable</span></span>                             |

<span data-ttu-id="3a675-163">La tabella seguente mostra la mappatura di **Stato di elaborazione** tra Sales e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="3a675-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="3a675-164">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="3a675-164">Processing Status</span></span>   | <span data-ttu-id="3a675-165">Stato in Sales</span><span class="sxs-lookup"><span data-stu-id="3a675-165">Status in Sales</span></span> | <span data-ttu-id="3a675-166">Stato in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="3a675-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="3a675-167">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-167">Active</span></span>              | <span data-ttu-id="3a675-168">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-168">Active</span></span>          | <span data-ttu-id="3a675-169">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-169">Open Order</span></span>                        |
| <span data-ttu-id="3a675-170">Confermata</span><span class="sxs-lookup"><span data-stu-id="3a675-170">Confirmed</span></span>           | <span data-ttu-id="3a675-171">Inviate</span><span class="sxs-lookup"><span data-stu-id="3a675-171">Submitted</span></span>       | <span data-ttu-id="3a675-172">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-172">Open Order</span></span>                        |
| <span data-ttu-id="3a675-173">Prelevato</span><span class="sxs-lookup"><span data-stu-id="3a675-173">Picked</span></span>              | <span data-ttu-id="3a675-174">Inviate</span><span class="sxs-lookup"><span data-stu-id="3a675-174">Submitted</span></span>       | <span data-ttu-id="3a675-175">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-175">Open Order</span></span>                        |
| <span data-ttu-id="3a675-176">Consegnato in parte</span><span class="sxs-lookup"><span data-stu-id="3a675-176">Partially Delivered</span></span> | <span data-ttu-id="3a675-177">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-177">Active</span></span>          | <span data-ttu-id="3a675-178">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-178">Open Order</span></span>                        |
| <span data-ttu-id="3a675-179">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="3a675-179">Partially Invoiced</span></span>  | <span data-ttu-id="3a675-180">Attive</span><span class="sxs-lookup"><span data-stu-id="3a675-180">Active</span></span>          | <span data-ttu-id="3a675-181">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="3a675-181">Open Order</span></span>                        |
| <span data-ttu-id="3a675-182">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="3a675-182">Partially Invoiced</span></span>  | <span data-ttu-id="3a675-183">Soddisfatto</span><span class="sxs-lookup"><span data-stu-id="3a675-183">Fulfilled</span></span>       | <span data-ttu-id="3a675-184">Consegnata</span><span class="sxs-lookup"><span data-stu-id="3a675-184">Delivered</span></span>                         |
| <span data-ttu-id="3a675-185">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-185">Invoiced</span></span>            | <span data-ttu-id="3a675-186">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-186">Invoiced</span></span>        | <span data-ttu-id="3a675-187">Fatturate</span><span class="sxs-lookup"><span data-stu-id="3a675-187">Invoiced</span></span>                          |
| <span data-ttu-id="3a675-188">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-188">Cancelled</span></span>           | <span data-ttu-id="3a675-189">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-189">Cancelled</span></span>       | <span data-ttu-id="3a675-190">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="3a675-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="3a675-191">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="3a675-191">Setup</span></span>

<span data-ttu-id="3a675-192">Per configurare il mapping per le colonne di stato dell'ordine cliente, è necessario abilitare gli attributi **IsSOPIntegrationEnabled** e **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="3a675-192">To set up the mapping for the sales order status columns, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="3a675-193">Per abilitare l'attributo **IsSOPIntegrationEnabled**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="3a675-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3a675-194">In un browser, passa a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="3a675-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="3a675-195">Sostituisci **\<test-name\>** con il collegamento della tua azienda in Sales.</span><span class="sxs-lookup"><span data-stu-id="3a675-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="3a675-196">Nella pagina che viene aperta, trova **organizationid** e prendi nota del valore.</span><span class="sxs-lookup"><span data-stu-id="3a675-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Ricerca di organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="3a675-198">In Sales, apri la console del browser ed esegui il seguente script.</span><span class="sxs-lookup"><span data-stu-id="3a675-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="3a675-199">Utilizza il valore **organizationid** del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="3a675-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on row update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Codice JavaScript nella console del browser](media/sales-map-script.png)

4. <span data-ttu-id="3a675-201">Verifica che **IsSOPIntegrationEnabled** sia impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="3a675-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="3a675-202">Utilizza l'URL del passaggio 1 per controllare il valore.</span><span class="sxs-lookup"><span data-stu-id="3a675-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled impostato su true](media/sales-map-integration-enabled.png)

<span data-ttu-id="3a675-204">Per abilitare l'attributo **isIntegrationUser**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="3a675-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="3a675-205">In Sales, vai a **Impostazione \> Personalizzazione \> Personalizza il sistema**, seleziona **Tabella utente** e quindi apri **Modulo \> Utente**.</span><span class="sxs-lookup"><span data-stu-id="3a675-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User table**, and then open **Form \> User**.</span></span>

    ![Apertura del modulo utente](media/sales-map-user.png)

2. <span data-ttu-id="3a675-207">In Esplora campi, trova **Modalità utente integrazione** e fai doppio clic su di esso per aggiungerlo al modulo.</span><span class="sxs-lookup"><span data-stu-id="3a675-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="3a675-208">Salva le modifiche.</span><span class="sxs-lookup"><span data-stu-id="3a675-208">Save your change.</span></span>

    ![Aggiunta della colonna Modalità utente integrazione al modulo](media/sales-map-field-explorer.png)

3. <span data-ttu-id="3a675-210">In Sales, vai a **Impostazione \> Sicurezza \> Utenti** e cambia la visualizzazione da **Utenti abilitati** a **Utenti dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="3a675-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Modifica della visualizzazione da Utenti abilitati a Utenti dell'applicazione](media/sales-map-enabled-users.png)

4. <span data-ttu-id="3a675-212">Seleziona le due voci per **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="3a675-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Elenco di utenti dell'applicazione](media/sales-map-user-mode.png)

5. <span data-ttu-id="3a675-214">Cambi il valore della colonna **Modalità utente integrazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="3a675-214">Change the value of the **Integration user mode** column to **Yes**.</span></span>

    ![Modifica del valore della colonna Modalità utente integrazione](media/sales-map-user-mode-yes.png)

<span data-ttu-id="3a675-216">I tuoi ordini cliente sono ora mappati.</span><span class="sxs-lookup"><span data-stu-id="3a675-216">Your sales orders are now mapped.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]