---
title: DBA modello
description: Una distinta base (DBA) modello fornisce un elenco standardizzato di componenti relativi a un oggetto sui quali vengono eseguiti regolarmente interventi di assistenza.
author: ShylaThompson
manager: tfehr
ms.date: 09/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88e732f64b389acafee23427594225dfacda71cc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431101"
---
# <a name="template-boms"></a><span data-ttu-id="fa0ca-103">DBA modello</span><span class="sxs-lookup"><span data-stu-id="fa0ca-103">Template BOMs</span></span>    

[!include [banner](../includes/banner.md)]


<span data-ttu-id="fa0ca-104">Una distinta base (DBA) modello è un elenco standardizzato di componenti relativi a un oggetto sui quali vengono eseguiti regolarmente interventi di assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-104">A template bill of materials (BOM) provides you with a standardized list of components for service objects that are serviced regularly.</span></span> <span data-ttu-id="fa0ca-105">I componenti inclusi nella DBA modello rappresentano i singoli sottocomponenti dell'oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-105">The components that are listed in the template BOM represent the individual subcomponents of the service object.</span></span> <span data-ttu-id="fa0ca-106">Applicando una DBA modello a un oggetto assistenza, è possibile mantenere un record dei sottocomponenti che sono stati sostituiti nell'oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-106">By applying a template BOM to a service object, you can keep a record of the subcomponents that have been replaced on the service object.</span></span>

<span data-ttu-id="fa0ca-107">Per applicare un DBA modello a un contratto di assistenza o un ordine di assistenza è necessario collegarla a una relazione di oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-107">To apply a template BOM to a service agreement or a service order, you attach it to a service object relation.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fa0ca-108">È possibile utilizzare solo una DBA modello con un oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-108">You can apply only one template BOM to a service object.</span></span></P>

## <a name="create-a-template-bom"></a><span data-ttu-id="fa0ca-109">Creare una DBA modello</span><span class="sxs-lookup"><span data-stu-id="fa0ca-109">Create a template BOM</span></span>

<span data-ttu-id="fa0ca-110">Nella tabella seguente vengono fornite informazioni sui vari metodi utilizzabili per creare una DBA modello.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-110">The following table contains information about the various methods that you can use to create a template BOM.</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="fa0ca-111">Metodo</span><span class="sxs-lookup"><span data-stu-id="fa0ca-111">Method</span></span></p></th>
<th><p><span data-ttu-id="fa0ca-112">Descrizioni</span><span class="sxs-lookup"><span data-stu-id="fa0ca-112">Description</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0ca-113">Produzione</span><span class="sxs-lookup"><span data-stu-id="fa0ca-113">Production</span></span></p></td>
<td><p><span data-ttu-id="fa0ca-114">La DBA modello è basata su un ordine di produzione.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-114">The template BOM is based on a production order.</span></span> <span data-ttu-id="fa0ca-115">Questa opzione è applicabile solo se si opera in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-115">This option is applicable only if you operate in a production environment.</span></span> <span data-ttu-id="fa0ca-116">Questa opzione è applicabile solo se si opera in un ambiente di produzione e consente di disporre sempre di un elenco aggiornato e dettagliato dei componenti che costituiscono un articolo.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-116">The benefit is that you have a current, detailed listing of the components that make up an item.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ca-117">Articolo BOM</span><span class="sxs-lookup"><span data-stu-id="fa0ca-117">Item BOM</span></span></p></td>
<td><p><span data-ttu-id="fa0ca-118">La DBA modello è basata su una DBA articolo.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-118">The template BOM is based on an item BOM.</span></span> <span data-ttu-id="fa0ca-119">La DBA articolo, a differenza della DBA di produzione, è un elenco statico dei componenti che costituiscono un articolo.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-119">The item BOM, unlike the production BOM, is a static list of the components that make up an item.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0ca-120">Modello esistente</span><span class="sxs-lookup"><span data-stu-id="fa0ca-120">Existing template</span></span></p></td>
<td><p><span data-ttu-id="fa0ca-121">Il modello è basato su una DBA modello esistente.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-121">The template is based on an existing template BOM.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ca-122">Manuale</span><span class="sxs-lookup"><span data-stu-id="fa0ca-122">Manual</span></span></p></td>
<td><p><span data-ttu-id="fa0ca-123">Se si sa quali pezzi di ricambio vengono in genere sostituiti in un oggetto assistenza, è possibile creare la DBA modello manualmente.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-123">If you know what spare parts are typically replaced on a service object, you can create your template BOM manually.</span></span> <span data-ttu-id="fa0ca-124">Questo metodo contribuisce a garantire che i componenti inclusi nel modello riflettano gli effettivi fabbisogni del luogo di lavoro.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-124">This method helps make sure that the components that are included in the template reflect the actual requirements of your workplace.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="apply-the-template-bom-to-a-service-agreement-or-service-order"></a><span data-ttu-id="fa0ca-125">Applicazione della DBA modello a un contratto di assistenza o a un ordine di assistenza</span><span class="sxs-lookup"><span data-stu-id="fa0ca-125">Apply the template BOM to a service agreement or service order</span></span>

<span data-ttu-id="fa0ca-126">La DBA modello può essere applicata a un contratto di assistenza, un ordine di assistenza o entrambi.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-126">You can apply a template BOM to a service agreement, a service order, or both.</span></span> <span data-ttu-id="fa0ca-127">Il contratto di assistenza riguarda in genere una relazione a lungo termine con un cliente.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-127">The service agreement usually covers a long-term relationship with a customer.</span></span> <span data-ttu-id="fa0ca-128">Lo storico delle sostituzioni registrato nella DBA assistenza rappresenta un insieme di dati utili ai fini del contratto di assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-128">The history of replacements that is recorded in the service BOM is useful data to have for the service agreement.</span></span>

<span data-ttu-id="fa0ca-129">È inoltre possibile applicare una DBA modello a un ordine di assistenza per registrare lo storico dell'assistenza eseguita su un oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-129">You can also apply a template BOM to a service order to record the history of the service that has been performed on a service object.</span></span>

## <a name="copy-the-history-of-a-service-bom"></a><span data-ttu-id="fa0ca-130">Copia dello storico di una DBA assistenza</span><span class="sxs-lookup"><span data-stu-id="fa0ca-130">Copy the history of a service BOM</span></span>

<span data-ttu-id="fa0ca-131">È possibile copiare lo storico di una riga di DBA assistenza da un contratto di assistenza a un altro.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-131">You can copy the history of a service BOM line from one service agreement to another service agreement.</span></span> <span data-ttu-id="fa0ca-132">Copiando lo storico assistenza tra i contratti di assistenza è possibile mantenere il record delle sostituzioni per un articolo.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-132">By copying the service history between service agreements, you can preserve the record of replacements for an item.</span></span>

<span data-ttu-id="fa0ca-133">**Esempio**</span><span class="sxs-lookup"><span data-stu-id="fa0ca-133">**Example**</span></span>

<span data-ttu-id="fa0ca-134">È stato impostato un contratto di assistenza triennale per l'automobile di un cliente.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-134">You have set up a three-year service agreement for a customer's car.</span></span> <span data-ttu-id="fa0ca-135">Durante tale periodo, il cliente si abitua al buon servizio fornito dalla società.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-135">During that period, the customer becomes accustomed to the good service that the company provides.</span></span> <span data-ttu-id="fa0ca-136">Di conseguenza, alla scadenza del contratto il cliente desidera impostarne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-136">Therefore, after the agreement expires, the customer wants to set up a new one.</span></span> <span data-ttu-id="fa0ca-137">A questo punto è possibile negoziare un contratto più favorevole per la società.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-137">You are now able to negotiate a more favorable agreement for the company.</span></span> <span data-ttu-id="fa0ca-138">Poiché il record dei componenti sostituiti può rivelarsi utile in futuro, lo storico della DBA assistenza viene copiato nel nuovo contratto.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-138">Because the record of replaced components might be useful in the future, you copy the history of the service BOM to the new agreement.</span></span>

## <a name="modify-the-template-bom"></a><span data-ttu-id="fa0ca-139">Modifica delle DBA modello</span><span class="sxs-lookup"><span data-stu-id="fa0ca-139">Modify the template BOM</span></span>

<span data-ttu-id="fa0ca-140">Se la DBA modello non è stata collegata a un oggetto assistenza, è possibile modificarla o eliminare righe al suo interno.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-140">If a template BOM has not been attached to a service object, you can modify or delete lines in it.</span></span> <span data-ttu-id="fa0ca-141">Una volta che la DBA modello è stata collegata a un oggetto assistenza, è possibile modificare solo la versione locale della DBA.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-141">After the template BOM is attached to a service object, you can modify only the local version of the BOM.</span></span> <span data-ttu-id="fa0ca-142">Per duplicare l'impostazione di una versione locale della DBA modello, è possibile creare una nuova DBA modello in base alla versione locale.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-142">If you want to duplicate the setup of a local version of a template BOM, you can create a new template BOM based on the local version.</span></span> <span data-ttu-id="fa0ca-143">Per ulteriori informazioni, consultare [Modificare una DBA assistenza](modify-service-bom.md).</span><span class="sxs-lookup"><span data-stu-id="fa0ca-143">For more information, see [Modify a Service BOM](modify-service-bom.md).</span></span>

<span data-ttu-id="fa0ca-144">Se si sostituisce un articolo incluso nella DBA, è possibile registrare la sostituzione nella riga DBA in Designer DBA.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-144">If you replace an item in the BOM, you can register the replacement on the BOM line in the BOM designer.</span></span> <span data-ttu-id="fa0ca-145">Facoltativamente, è possibile creare una riga di ordine di assistenza per l'oggetto di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-145">Optionally, you can create a service order line for the replacement object.</span></span> <span data-ttu-id="fa0ca-146">Se viene creata una riga di ordine di assistenza, è possibile fatturare l'articolo di sostituzione.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-146">If you create a service order line, you can invoice the replacement item.</span></span> <span data-ttu-id="fa0ca-147">Se non si crea una riga di ordine di assistenza per una sostituzione, la registrazione della sostituzione viene mantenuta per tenere traccia dello storico dell'oggetto assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-147">If you do not create a service order line for a replacement, the replacement registration is kept to track the history of the service object.</span></span>

## <a name="change-how-information-on-the-bom-line-is-displayed"></a><span data-ttu-id="fa0ca-148">Modifica della modalità di visualizzazione delle informazioni nella riga DBA</span><span class="sxs-lookup"><span data-stu-id="fa0ca-148">Change how information on the BOM line is displayed</span></span>

<span data-ttu-id="fa0ca-149">È possibile modificare il modo in cui le informazioni sulla riga DBA vengono visualizzate per tutte le DBA modello e assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-149">You can change the way that information on the BOM line is displayed for all template and service BOMs.</span></span> <span data-ttu-id="fa0ca-150">Le modifiche vengono applicate a tutte le DBA modello e assistenza,</span><span class="sxs-lookup"><span data-stu-id="fa0ca-150">The changes are applied to all template BOMs and service BOMs.</span></span> <span data-ttu-id="fa0ca-151">incluse quelle collegate agli oggetti assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-151">This includes those that are attached to service objects.</span></span>

## <a name="set-up-number-sequences-for-template-boms"></a><span data-ttu-id="fa0ca-152">Impostazione di sequenze numeriche per le DBA modello</span><span class="sxs-lookup"><span data-stu-id="fa0ca-152">Set up number sequences for template BOMs</span></span>

<span data-ttu-id="fa0ca-153">Per utilizzare le DBA modello, è necessario impostare due sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-153">To use template BOMs, you must set up two number sequences.</span></span> <span data-ttu-id="fa0ca-154">Impostare una sequenza numerica per la DBA modello e una per il numero di riga dello storico DBA.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-154">Set up one number sequence for the template BOM and one for the BOM history line number.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fa0ca-155">Le sequenze numeriche vengono utilizzate per allocare gli identificatori ai record che li richiedono.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-155">Number sequences are used to allocate identifiers to records that require them.</span></span> <span data-ttu-id="fa0ca-156">Prima di poter assegnare una sequenza numerica a una DBA modello o a un numero di riga dello storico DBA, è necessario impostare i codici delle sequenze numeriche.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-156">Before you can assign a number sequence to a template BOM or a BOM history line number, you must set up number sequences codes.</span></span></P>


## <a name="set-up-number-sequences"></a><span data-ttu-id="fa0ca-157">Imposta sequenze numeriche</span><span class="sxs-lookup"><span data-stu-id="fa0ca-157">Set up number sequences</span></span>

1.  <span data-ttu-id="fa0ca-158">Nella pagina elenco **Sequenze numeriche** creare le sequenze numeriche per le DBA modello e il numero di riga dello storico DBA.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-158">On the **Number sequences** list page, create number sequences for template BOMs and the BOM history line number.</span></span> 

2.  <span data-ttu-id="fa0ca-159">Fare clic su **Gestione assistenza** \> **Impostazione** \> **Parametri di gestione assistenza**.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-159">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

3.  <span data-ttu-id="fa0ca-160">Fare clic su **Sequenze numeriche**, quindi selezionare un codice di sequenza numerica per i riferimenti alle sequenze numeriche creati nel modulo **Sequenze numeriche** .</span><span class="sxs-lookup"><span data-stu-id="fa0ca-160">Click **Number sequences**, and then select a number sequence code for the number sequence references that you created in the **Number sequences** form.</span></span>

4.  <span data-ttu-id="fa0ca-161">Chiudere il modulo per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-161">Close the form to save your changes.</span></span>


> [!NOTE]
> <P><span data-ttu-id="fa0ca-162">Il numero di riga dello storico DBA viene utilizzato dal sistema per associare le transazioni nello storico DBA a un contratto o un ordine di assistenza.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-162">The BOM history line number is used by the system to associate the transactions in the BOM history with a service agreement or service order.</span></span> <span data-ttu-id="fa0ca-163">Il numero non viene visualizzato nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="fa0ca-163">The number is not displayed in the user interface.</span></span></P>



## <a name="see-also"></a><span data-ttu-id="fa0ca-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fa0ca-164">See also</span></span>

[<span data-ttu-id="fa0ca-165">Creare una DBA modello</span><span class="sxs-lookup"><span data-stu-id="fa0ca-165">Create a template BOM</span></span>](create-template-bom.md)

[<span data-ttu-id="fa0ca-166">Gestire le DBA modello per le relazioni di oggetti</span><span class="sxs-lookup"><span data-stu-id="fa0ca-166">Manage template BOMs on object relations</span></span>](manage-template-boms-on-object-relations.md)

[<span data-ttu-id="fa0ca-167">Modificare una DBA assistenza</span><span class="sxs-lookup"><span data-stu-id="fa0ca-167">Modify a Service BOM</span></span>](modify-service-bom.md)

 


