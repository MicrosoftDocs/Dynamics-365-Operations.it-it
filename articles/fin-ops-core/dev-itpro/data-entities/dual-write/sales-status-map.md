---
title: Configurare il mapping per i campi di stato dell'ordine cliente
description: In questo argomento viene illustrato come configurare i campi di stato dell'ordine cliente per la doppia scrittura.
author: dasani-madipalli
manager: tonyafehr
ms.date: 06/25/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: damadipa
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-06-25
ms.openlocfilehash: dce4b6310e2f6d31a115302efa7fbc132799e48f
ms.sourcegitcommit: 4ba10abe5be8a21b95370cd970a622e954970984
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "3829287"
---
# <a name="set-up-the-mapping-for-the-sales-order-status-fields"></a><span data-ttu-id="ccf29-103">Configurare il mapping per i campi di stato dell'ordine cliente</span><span class="sxs-lookup"><span data-stu-id="ccf29-103">Set up the mapping for the sales order status fields</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ccf29-104">I campi che indicano lo stato dell'ordine cliente hanno valori di enumerazione diversi in Microsoft Dynamics 365 Supply Chain Management e Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="ccf29-104">The fields that indicate sales order status have different enumeration values in Microsoft Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="ccf29-105">È necessaria una configurazione aggiuntiva per mappare questi campi in doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="ccf29-105">Additional setup is required to map these fields in dual-write.</span></span>

## <a name="fields-in-supply-chain-management"></a><span data-ttu-id="ccf29-106">Campi in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ccf29-106">Fields in Supply Chain Management</span></span>

<span data-ttu-id="ccf29-107">In Supply Chain Management, due campi riflettono lo stato dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ccf29-107">In Supply Chain Management, two fields reflect the status of the sales order.</span></span> <span data-ttu-id="ccf29-108">I campi che devi mappare sono **Stato** e **Stato documento**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-108">The fields that you must map are **Status** and **Document Status**.</span></span>

<span data-ttu-id="ccf29-109">L'enumerazione **Stato** specifica lo stato generale dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ccf29-109">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="ccf29-110">Questo stato è mostrato nell'intestazione dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ccf29-110">This status is shown on the order header.</span></span>

<span data-ttu-id="ccf29-111">L'enumerazione **Stato** include i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccf29-111">The **Status** enumeration has the following values:</span></span>

- <span data-ttu-id="ccf29-112">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-112">Open Order</span></span>
- <span data-ttu-id="ccf29-113">Consegnata</span><span class="sxs-lookup"><span data-stu-id="ccf29-113">Delivered</span></span>
- <span data-ttu-id="ccf29-114">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-114">Invoiced</span></span>
- <span data-ttu-id="ccf29-115">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-115">Cancelled</span></span>

<span data-ttu-id="ccf29-116">L'enumerazione **Stato documento** specifica il documento più recente che è stato generato per l'ordine.</span><span class="sxs-lookup"><span data-stu-id="ccf29-116">The **Document Status** enumeration specifies the most recent document that was generated for the order.</span></span> <span data-ttu-id="ccf29-117">Ad esempio, se l'ordine è confermato, questo documento è una conferma dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="ccf29-117">For example, if the order is confirmed, this document is a sales order confirmation.</span></span> <span data-ttu-id="ccf29-118">Se un ordine cliente viene fatturato parzialmente e la riga rimanente viene confermata, lo stato del documento rimane **Fattura**, perché la fattura viene generata in un secondo momento nel processo.</span><span class="sxs-lookup"><span data-stu-id="ccf29-118">If a sales order is partially invoiced, and then the remaining line is confirmed, the document status remains **Invoice**, because the invoice is generated later in the process.</span></span>

<span data-ttu-id="ccf29-119">L'enumerazione **Stato documento** include i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="ccf29-119">The **Document Status** enumeration has the following values:</span></span>

- <span data-ttu-id="ccf29-120">Conferma</span><span class="sxs-lookup"><span data-stu-id="ccf29-120">Confirmation</span></span>
- <span data-ttu-id="ccf29-121">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="ccf29-121">Picking List</span></span>
- <span data-ttu-id="ccf29-122">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ccf29-122">Packing Slip</span></span>
- <span data-ttu-id="ccf29-123">Fattura</span><span class="sxs-lookup"><span data-stu-id="ccf29-123">Invoice</span></span>

## <a name="fields-in-sales"></a><span data-ttu-id="ccf29-124">Campi in Sales</span><span class="sxs-lookup"><span data-stu-id="ccf29-124">Fields in Sales</span></span>

<span data-ttu-id="ccf29-125">In Sales, due campi indicano lo stato dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ccf29-125">In Sales, two fields indicate the status of the order.</span></span> <span data-ttu-id="ccf29-126">I campi che devi mappare sono **Stato** e **Stato elaborazione**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-126">The fields that you must map are **Status** and **Processing Status**.</span></span>

<span data-ttu-id="ccf29-127">L'enumerazione **Stato** specifica lo stato generale dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="ccf29-127">The **Status** enumeration specifies the overall status of the order.</span></span> <span data-ttu-id="ccf29-128">Include i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccf29-128">It has the following values:</span></span>

- <span data-ttu-id="ccf29-129">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-129">Active</span></span>
- <span data-ttu-id="ccf29-130">Inviate</span><span class="sxs-lookup"><span data-stu-id="ccf29-130">Submitted</span></span>
- <span data-ttu-id="ccf29-131">Soddisfatto</span><span class="sxs-lookup"><span data-stu-id="ccf29-131">Fulfilled</span></span>
- <span data-ttu-id="ccf29-132">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-132">Invoiced</span></span>
- <span data-ttu-id="ccf29-133">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-133">Cancelled</span></span>

<span data-ttu-id="ccf29-134">L'enumerazione **Stato di elaborazione** è stata introdotta in modo che lo stato possa essere mappato in modo più accurato con Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ccf29-134">The **Processing Status** enumeration was introduced so that the status can be mapped more accurately with Supply Chain Management.</span></span>

<span data-ttu-id="ccf29-135">La tabella seguente mostra la mappatura di **Stato di elaborazione** in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ccf29-135">The following table shows the mapping of **Processing Status** in Supply Chain Management.</span></span>

| <span data-ttu-id="ccf29-136">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="ccf29-136">Processing Status</span></span>   | <span data-ttu-id="ccf29-137">Stato in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ccf29-137">Status in Supply Chain Management</span></span> | <span data-ttu-id="ccf29-138">Stato documento in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ccf29-138">Document Status in Supply Chain Management</span></span> |
|---------------------|-----------------------------------|--------------------------------------------|
| <span data-ttu-id="ccf29-139">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-139">Active</span></span>              | <span data-ttu-id="ccf29-140">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-140">Open Order</span></span>                        | <span data-ttu-id="ccf29-141">Nessuna priorità</span><span class="sxs-lookup"><span data-stu-id="ccf29-141">None</span></span>                                       |
| <span data-ttu-id="ccf29-142">Confermata</span><span class="sxs-lookup"><span data-stu-id="ccf29-142">Confirmed</span></span>           | <span data-ttu-id="ccf29-143">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-143">Open Order</span></span>                        | <span data-ttu-id="ccf29-144">Conferma</span><span class="sxs-lookup"><span data-stu-id="ccf29-144">Confirmation</span></span>                               |
| <span data-ttu-id="ccf29-145">Prelevato</span><span class="sxs-lookup"><span data-stu-id="ccf29-145">Picked</span></span>              | <span data-ttu-id="ccf29-146">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-146">Open Order</span></span>                        | <span data-ttu-id="ccf29-147">Distinta di prelievo</span><span class="sxs-lookup"><span data-stu-id="ccf29-147">Picking List</span></span>                               |
| <span data-ttu-id="ccf29-148">Consegnato in parte</span><span class="sxs-lookup"><span data-stu-id="ccf29-148">Partially Delivered</span></span> | <span data-ttu-id="ccf29-149">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-149">Open Order</span></span>                        | <span data-ttu-id="ccf29-150">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ccf29-150">Packing Slip</span></span>                               |
| <span data-ttu-id="ccf29-151">Consegnata</span><span class="sxs-lookup"><span data-stu-id="ccf29-151">Delivered</span></span>           | <span data-ttu-id="ccf29-152">Consegnata</span><span class="sxs-lookup"><span data-stu-id="ccf29-152">Delivered</span></span>                         | <span data-ttu-id="ccf29-153">Documento di trasporto</span><span class="sxs-lookup"><span data-stu-id="ccf29-153">Packing Slip</span></span>                               |
| <span data-ttu-id="ccf29-154">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="ccf29-154">Partially Invoiced</span></span>  | <span data-ttu-id="ccf29-155">Consegnata</span><span class="sxs-lookup"><span data-stu-id="ccf29-155">Delivered</span></span>                         | <span data-ttu-id="ccf29-156">Fattura</span><span class="sxs-lookup"><span data-stu-id="ccf29-156">Invoice</span></span>                                    |
| <span data-ttu-id="ccf29-157">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-157">Invoiced</span></span>            | <span data-ttu-id="ccf29-158">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-158">Invoiced</span></span>                          | <span data-ttu-id="ccf29-159">Fattura</span><span class="sxs-lookup"><span data-stu-id="ccf29-159">Invoice</span></span>                                    |
| <span data-ttu-id="ccf29-160">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-160">Cancelled</span></span>           | <span data-ttu-id="ccf29-161">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-161">Cancelled</span></span>                         | <span data-ttu-id="ccf29-162">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="ccf29-162">Not applicable</span></span>                             |

<span data-ttu-id="ccf29-163">La tabella seguente mostra la mappatura di **Stato di elaborazione** tra Sales e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ccf29-163">The following table shows the mapping of **Processing Status** between Sales and Supply Chain Management.</span></span>

| <span data-ttu-id="ccf29-164">Stato di elaborazione</span><span class="sxs-lookup"><span data-stu-id="ccf29-164">Processing Status</span></span>   | <span data-ttu-id="ccf29-165">Stato in Sales</span><span class="sxs-lookup"><span data-stu-id="ccf29-165">Status in Sales</span></span> | <span data-ttu-id="ccf29-166">Stato in Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="ccf29-166">Status in Supply Chain Management</span></span> |
|---------------------|-----------------|-----------------------------------|
| <span data-ttu-id="ccf29-167">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-167">Active</span></span>              | <span data-ttu-id="ccf29-168">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-168">Active</span></span>          | <span data-ttu-id="ccf29-169">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-169">Open Order</span></span>                        |
| <span data-ttu-id="ccf29-170">Confermata</span><span class="sxs-lookup"><span data-stu-id="ccf29-170">Confirmed</span></span>           | <span data-ttu-id="ccf29-171">Inviate</span><span class="sxs-lookup"><span data-stu-id="ccf29-171">Submitted</span></span>       | <span data-ttu-id="ccf29-172">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-172">Open Order</span></span>                        |
| <span data-ttu-id="ccf29-173">Prelevato</span><span class="sxs-lookup"><span data-stu-id="ccf29-173">Picked</span></span>              | <span data-ttu-id="ccf29-174">Inviate</span><span class="sxs-lookup"><span data-stu-id="ccf29-174">Submitted</span></span>       | <span data-ttu-id="ccf29-175">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-175">Open Order</span></span>                        |
| <span data-ttu-id="ccf29-176">Consegnato in parte</span><span class="sxs-lookup"><span data-stu-id="ccf29-176">Partially Delivered</span></span> | <span data-ttu-id="ccf29-177">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-177">Active</span></span>          | <span data-ttu-id="ccf29-178">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-178">Open Order</span></span>                        |
| <span data-ttu-id="ccf29-179">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="ccf29-179">Partially Invoiced</span></span>  | <span data-ttu-id="ccf29-180">Attive</span><span class="sxs-lookup"><span data-stu-id="ccf29-180">Active</span></span>          | <span data-ttu-id="ccf29-181">Ordine aperto</span><span class="sxs-lookup"><span data-stu-id="ccf29-181">Open Order</span></span>                        |
| <span data-ttu-id="ccf29-182">Parzialmente fatturato</span><span class="sxs-lookup"><span data-stu-id="ccf29-182">Partially Invoiced</span></span>  | <span data-ttu-id="ccf29-183">Soddisfatto</span><span class="sxs-lookup"><span data-stu-id="ccf29-183">Fulfilled</span></span>       | <span data-ttu-id="ccf29-184">Consegnata</span><span class="sxs-lookup"><span data-stu-id="ccf29-184">Delivered</span></span>                         |
| <span data-ttu-id="ccf29-185">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-185">Invoiced</span></span>            | <span data-ttu-id="ccf29-186">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-186">Invoiced</span></span>        | <span data-ttu-id="ccf29-187">Fatturate</span><span class="sxs-lookup"><span data-stu-id="ccf29-187">Invoiced</span></span>                          |
| <span data-ttu-id="ccf29-188">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-188">Cancelled</span></span>           | <span data-ttu-id="ccf29-189">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-189">Cancelled</span></span>       | <span data-ttu-id="ccf29-190">Operazione annullata</span><span class="sxs-lookup"><span data-stu-id="ccf29-190">Cancelled</span></span>                         |

## <a name="setup"></a><span data-ttu-id="ccf29-191">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="ccf29-191">Setup</span></span>

<span data-ttu-id="ccf29-192">Per configurare il mapping per i campi di stato dell'ordine cliente, è necessario abilitare gli attributi **IsSOPIntegrationEnabled** e **isIntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-192">To set up the mapping for the sales order status fields, you must enable the **IsSOPIntegrationEnabled** and **isIntegrationUser** attributes.</span></span>

<span data-ttu-id="ccf29-193">Per abilitare l'attributo **IsSOPIntegrationEnabled**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="ccf29-193">To enable the **IsSOPIntegrationEnabled** attribute, follow these steps.</span></span>

1. <span data-ttu-id="ccf29-194">In un browser, passa a `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span><span class="sxs-lookup"><span data-stu-id="ccf29-194">In a browser, go to `https://<test-name>.crm.dynamics.com/api/data/v9.0/organizations`.</span></span> <span data-ttu-id="ccf29-195">Sostituisci **\<test-name\>** con il collegamento della tua azienda in Sales.</span><span class="sxs-lookup"><span data-stu-id="ccf29-195">Replace **\<test-name\>** with your company's link to Sales.</span></span>
2. <span data-ttu-id="ccf29-196">Nella pagina che viene aperta, trova **organizationid** e prendi nota del valore.</span><span class="sxs-lookup"><span data-stu-id="ccf29-196">On the page that is opened, find **organizationid**, and make a note of the value.</span></span>

    ![Ricerca di organizationid](media/sales-map-orgid.png)

3. <span data-ttu-id="ccf29-198">In Sales, apri la console del browser ed esegui il seguente script.</span><span class="sxs-lookup"><span data-stu-id="ccf29-198">In Sales, open the browser console, and run following script.</span></span> <span data-ttu-id="ccf29-199">Utilizza il valore **organizationid** del passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="ccf29-199">Use the **organizationid** value from step 2.</span></span>

    ```javascript
    Xrm.WebApi.updateRecord("organization",
    "d9a7c5f7-acbf-4aa9-86e8-a891c43f748c", {"issopintegrationenabled" :
    true}).then(
        function success(result) {
            console.log("Account updated");
            // perform operations on record update
        },
        function (error) {
            console.log(error.message);
            // handle error conditions
        }
    );
    ```

    ![Codice JavaScript nella console del browser](media/sales-map-script.png)

4. <span data-ttu-id="ccf29-201">Verifica che **IsSOPIntegrationEnabled** sia impostato su **true**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-201">Verify that **IsSOPIntegrationEnabled** is set to **true**.</span></span> <span data-ttu-id="ccf29-202">Utilizza l'URL del passaggio 1 per controllare il valore.</span><span class="sxs-lookup"><span data-stu-id="ccf29-202">Use the URL from step 1 to check the value.</span></span>

    ![IsSOPIntegrationEnabled impostato su true](media/sales-map-integration-enabled.png)

<span data-ttu-id="ccf29-204">Per abilitare l'attributo **isIntegrationUser**, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="ccf29-204">To enable the **isIntegrationUser** attribute, follow these steps.</span></span>

1. <span data-ttu-id="ccf29-205">In Sales, vai a **Impostazione \> Personalizzazione \> Personalizza il sistema**, seleziona **Entità utente** e quindi apri **Modulo \> Utente**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-205">In Sales, go to **Setting \> Customization \> Customize the System**, select **User entity**, and then open **Form \> User**.</span></span>

    ![Apertura del modulo utente](media/sales-map-user.png)

2. <span data-ttu-id="ccf29-207">In Esplora campi, trova **Modalità utente integrazione** e fai doppio clic su di esso per aggiungerlo al modulo.</span><span class="sxs-lookup"><span data-stu-id="ccf29-207">In Field Explorer, find **Integration user mode**, and double-click it to add it to the form.</span></span> <span data-ttu-id="ccf29-208">Salva le modifiche.</span><span class="sxs-lookup"><span data-stu-id="ccf29-208">Save your change.</span></span>

    ![Aggiunta del campo Modalità utente integrazione al modulo](media/sales-map-field-explorer.png)

3. <span data-ttu-id="ccf29-210">In Sales, vai a **Impostazione \> Sicurezza \> Utenti** e cambia la visualizzazione da **Utenti abilitati** a **Utenti dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-210">In Sales, go to **Setting \> Security \> Users**, and change the view from **Enabled Users** to **Application Users**.</span></span>

    ![Modifica della visualizzazione da Utenti abilitati a Utenti dell'applicazione](media/sales-map-enabled-users.png)

4. <span data-ttu-id="ccf29-212">Seleziona le due voci per **DualWrite IntegrationUser**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-212">Select the two entries for **DualWrite IntegrationUser**.</span></span>

    ![Elenco di utenti dell'applicazione](media/sales-map-user-mode.png)

5. <span data-ttu-id="ccf29-214">Cambi il valore del campo **Modalità utente integrazione** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="ccf29-214">Change the value of the **Integration user mode** field to **Yes**.</span></span>

    ![Modifica del valore del campo Modalità utente integrazione](media/sales-map-user-mode-yes.png)

<span data-ttu-id="ccf29-216">I tuoi ordini cliente sono ora mappati.</span><span class="sxs-lookup"><span data-stu-id="ccf29-216">Your sales orders are now mapped.</span></span>
