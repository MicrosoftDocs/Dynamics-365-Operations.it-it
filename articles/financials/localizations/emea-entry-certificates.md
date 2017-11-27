---
title: Certificati di entrata UE
description: Vengono fornite le informazioni sui certificati di entrata dell'Unione Europea (UE).
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustEntryCertificateJour_W, CustParameters, CustTable, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 11464
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: mrolecki
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6e066bd2adbb9f27f3b0850ca25978d0777590d2
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="eu-entry-certificates"></a><span data-ttu-id="b8aab-103">Certificati di entrata UE</span><span class="sxs-lookup"><span data-stu-id="b8aab-103">EU entry certificates</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="b8aab-104">Vengono fornite le informazioni sui certificati di entrata dell'Unione Europea (UE).</span><span class="sxs-lookup"><span data-stu-id="b8aab-104">This article provides information about European Union (EU) entry certificates.</span></span>

<span data-ttu-id="b8aab-105">È possibile completare le seguenti attività per un certificato di entrata UE (Unione Europea):</span><span class="sxs-lookup"><span data-stu-id="b8aab-105">You can complete the following tasks for a European Union (EU) entry certificate:</span></span>

-   <span data-ttu-id="b8aab-106">Creare ed emettere un certificato di entrata UE insieme a un documento di trasporto o una fattura cliente per la consegna di articoli o servizi ai paesi UE.</span><span class="sxs-lookup"><span data-stu-id="b8aab-106">Create and issue an EU entry certificate together with a packing slip or customer invoice for the delivery of items or services to EU countries/regions.</span></span>
-   <span data-ttu-id="b8aab-107">Ricevere il certificato di entrata UE assegnato da un cliente UE.</span><span class="sxs-lookup"><span data-stu-id="b8aab-107">Receive the EU entry certificate that is signed by an EU customer.</span></span>
-   <span data-ttu-id="b8aab-108">Caricare il certificato di entrata UE ricevuto dal cliente o da un fornitore di terze parti responsabile della consegna di articoli al cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-108">Upload the signed EU entry certificate that is received either from the customer or from a third party who is responsible for delivering items to the customer.</span></span>
-   <span data-ttu-id="b8aab-109">Associare il certificato di entrata UE caricato con una fattura cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-109">Associate the uploaded EU entry certificate with a customer invoice.</span></span>
-   <span data-ttu-id="b8aab-110">Aggiornare lo stato del certificato di entrata UE caricato.</span><span class="sxs-lookup"><span data-stu-id="b8aab-110">Update the status of the uploaded EU entry certificate.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b8aab-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b8aab-111">Prerequisites</span></span>
<span data-ttu-id="b8aab-112">Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="b8aab-112">The following table shows the prerequisites that must be in place before you start.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8aab-113">Categoria</span><span class="sxs-lookup"><span data-stu-id="b8aab-113">Category</span></span></th>
<th><span data-ttu-id="b8aab-114">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="b8aab-114">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b8aab-115">Paese</span><span class="sxs-lookup"><span data-stu-id="b8aab-115">Country/region</span></span></td>
<td><span data-ttu-id="b8aab-116">L'indirizzo principale della persona giuridica deve essere uno stato membro UE.</span><span class="sxs-lookup"><span data-stu-id="b8aab-116">The primary address of the legal entity must be in a EU member state.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b8aab-117">Operazioni di configurazione correlate</span><span class="sxs-lookup"><span data-stu-id="b8aab-117">Related set up tasks</span></span></td>
<td><ul>
<li><span data-ttu-id="b8aab-118">Nella pagina <strong>Parametri contabilità clienti</strong> selezionare le opzioni <strong>Abilita gestione certificati di entrata</strong> e <strong>Abilita rilascio certificato di entrata</strong>.</span><span class="sxs-lookup"><span data-stu-id="b8aab-118">On the <strong>Accounts receivable parameters</strong> page, select the <strong>Enable entry certificate management</strong> and <strong>Enable entry certificate issuing</strong> options.</span></span></li>
<li><span data-ttu-id="b8aab-119">Nella pagina <strong>Clienti</strong> nella Scheda dettaglio <strong>Fattura e consegna</strong>, selezionare l'opzione <strong>Certificato di entrata obbligatorio</strong> per indicare che un certificato di entrata UE è obbligatorio per il cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-119">On the <strong>Customers</strong> page, on the <strong>Invoice and delivery</strong> FastTab, select the <strong>Entry certificate required</strong> option to indicate that an EU entry certificate is mandatory for the customer.</span></span> <span data-ttu-id="b8aab-120">Selezionare l'opzione <strong>Rilascia certificato di entrata</strong> per rilasciare un certificato di entrata UE della persona giuridica al cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-120">Select the <strong>Issue entry certificate</strong> option to issue an EU entry certificate of the legal entity to the customer.</span></span></li>
<li><span data-ttu-id="b8aab-121">Nella pagina <strong>Parametri contabilità clienti</strong> selezionare un codice di sequenza numerica per il riferimento <strong>Certificato di entrata</strong>.</span><span class="sxs-lookup"><span data-stu-id="b8aab-121">On the <strong>Accounts receivable parameters</strong> page, select a number sequence code for the <strong>Entry certificate</strong> reference.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b8aab-122">Transazioni correlate</span><span class="sxs-lookup"><span data-stu-id="b8aab-122">Related transactions</span></span></td>
<td><ul>
<li><span data-ttu-id="b8aab-123">Creare un conto cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-123">Create a customer account.</span></span></li>
<li><span data-ttu-id="b8aab-124">Creare un ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-124">Create a sales order.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="creating-registering-and-uploading-an-eu-entry-certificate"></a><span data-ttu-id="b8aab-125">Creazione, registrazione e caricamento di un certificato di entrata UE</span><span class="sxs-lookup"><span data-stu-id="b8aab-125">Creating, registering, and uploading an EU entry certificate</span></span>
<span data-ttu-id="b8aab-126">È possibile creare un certificato di entrata UE automaticamente o manualmente.</span><span class="sxs-lookup"><span data-stu-id="b8aab-126">You can create an EU entry certificate automatically or manually.</span></span> <span data-ttu-id="b8aab-127">Un certificato di entrata UE viene creato e stampato automaticamente quando si registra un documento di trasporto o una fattura per un cliente utilizzando la pagina **Registrazione documento di trasporto** o la pagina **Registrazione fattura**.</span><span class="sxs-lookup"><span data-stu-id="b8aab-127">An EU entry certificate is created and printed automatically when you post a packing slip or invoice for a customer by using the **Packing slip posting** page or the **Posting invoice** page.</span></span> <span data-ttu-id="b8aab-128">Per creare o ristampare manualmente un certificato di entrata UE per una fattura cliente, utilizzare la pagina **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="b8aab-128">To manually create or reprint an EU entry certificate for a customer invoice, use the **Invoice journal** page.</span></span> <span data-ttu-id="b8aab-129">Inoltre, è possibile utilizzare la pagina **Giornale di registrazione certificati di entrata** per immettere i dettagli relativi a un certificato di entrata UE emesso da una terza parte.</span><span class="sxs-lookup"><span data-stu-id="b8aab-129">Additionally, you can use the **Entry certificate journal** page to enter details about an EU entry certificate that is issued by a third party.</span></span>

### <a name="creating-an-eu-entry-certificate-automatically-or-manually"></a><span data-ttu-id="b8aab-130">Creazione di un certificato di entrata UE automaticamente o manualmente</span><span class="sxs-lookup"><span data-stu-id="b8aab-130">Creating an EU entry certificate automatically or manually</span></span>

<span data-ttu-id="b8aab-131">È possibile creare un certificato di entrata UE automaticamente utilizzando un documento di trasporto nella pagina **Tutti gli ordini cliente** o tramite una fattura nella pagina **Ordine cliente**.</span><span class="sxs-lookup"><span data-stu-id="b8aab-131">You can create an EU entry certificate automatically by using a packing slip on the **All sales orders** page or by using an invoice on the **Sales order** page.</span></span> <span data-ttu-id="b8aab-132">Per creare manualmente un certificato di entrata UE, è possibile utilizzare una fattura nella pagina **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="b8aab-132">To manually create an EU entry certificate, you can use an invoice on the **Invoice journal** page.</span></span> <span data-ttu-id="b8aab-133">È tuttavia necessario modificare lo stato del certificato della fattura prima di creare manualmente un certificato di entrata UE.</span><span class="sxs-lookup"><span data-stu-id="b8aab-133">However, you must change the certification status of the invoice before you manually create an EU entry certificate.</span></span>

### <a name="registering-an-eu-entry-certificate"></a><span data-ttu-id="b8aab-134">Registrazione di un certificato di entrata UE</span><span class="sxs-lookup"><span data-stu-id="b8aab-134">Registering an EU entry certificate</span></span>

<span data-ttu-id="b8aab-135">Se è necessaria la registrazione, è possibile utilizzare la pagina **Giornale di registrazione certificati di entrata** per registrare un certificato di entrata UE emesso da una terza parte.</span><span class="sxs-lookup"><span data-stu-id="b8aab-135">If registration is required, you can use the **Entry certificate journal** page to register an EU entry certificate that is issued by a third party.</span></span>

### <a name="uploading-a-received-eu-entry-certificate"></a><span data-ttu-id="b8aab-136">Caricamento di un certificato di entrata UE ricevuto</span><span class="sxs-lookup"><span data-stu-id="b8aab-136">Uploading a received EU entry certificate</span></span>

<span data-ttu-id="b8aab-137">Utilizzare la pagina **Allegati** per caricare un certificato di entrata UE ricevuto firmato da un cliente UE.</span><span class="sxs-lookup"><span data-stu-id="b8aab-137">Use the **Attachments** page to upload a received EU entry certificate that is signed by an EU customer.</span></span> <span data-ttu-id="b8aab-138">Dopo aver caricato il certificato, è possibile associarlo a una fattura come prova della consegna di articoli.</span><span class="sxs-lookup"><span data-stu-id="b8aab-138">After the certificate is uploaded, you can associate it with an invoice as proof that the items were delivered.</span></span> <span data-ttu-id="b8aab-139">La prova è obbligatoria se è necessario emettere una fattura che non include l'imposta sul valore aggiunto (IVA) e verrà utilizzata durante il controllo.</span><span class="sxs-lookup"><span data-stu-id="b8aab-139">This proof is required if you must issue an invoice that doesn't include value-added tax (VAT), and it's also used during auditing.</span></span>

### <a name="optional-updating-the-certification-status-and-printing-status-of-an-invoice"></a><span data-ttu-id="b8aab-140">Facoltativo: aggiornamento dello stato del certificato e dello stato di stampa di una fattura</span><span class="sxs-lookup"><span data-stu-id="b8aab-140">Optional: Updating the certification status and printing status of an invoice</span></span>

<span data-ttu-id="b8aab-141">È possibile aggiornare lo stato del certificato di entrata e lo stato di stampa di una fattura cliente utilizzando la pagina **Giornale di registrazione fatture**.</span><span class="sxs-lookup"><span data-stu-id="b8aab-141">You can update the entry certification status and printing status of a customer invoice by using the **Invoice journal** page.</span></span>

## <a name="technical-information-for-system-administrators"></a><span data-ttu-id="b8aab-142">Informazioni tecniche per gli amministratori di sistema</span><span class="sxs-lookup"><span data-stu-id="b8aab-142">Technical information for system administrators</span></span>
<span data-ttu-id="b8aab-143">Se non si ha accesso alle pagine utilizzate per completare questa attività, contattare l'amministratore di sistema e fornire le informazioni indicate nella tabella che segue.</span><span class="sxs-lookup"><span data-stu-id="b8aab-143">If you don't have access to the pages that are used to complete this task, contact your system administrator, and provide the information that is shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b8aab-144">Categoria</span><span class="sxs-lookup"><span data-stu-id="b8aab-144">Category</span></span></th>
<th><span data-ttu-id="b8aab-145">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="b8aab-145">Prerequisite</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b8aab-146">Ruoli di sicurezza e compiti</span><span class="sxs-lookup"><span data-stu-id="b8aab-146">Security roles and duties</span></span></td>
<td><span data-ttu-id="b8aab-147">Per creare e impostare i certificati di entrata UE per articoli o servizi, è necessario essere membri di un ruolo di sicurezza che include le funzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b8aab-147">To set up and create EU entry certificates for items or services, you must be a member of a security role that includes the following duties:</span></span>
<ul>
<li><span data-ttu-id="b8aab-148"><strong>Addetto alla contabilità clienti</strong> (CustInvoiceAccountsReceivableClerk)</span><span class="sxs-lookup"><span data-stu-id="b8aab-148"><strong>Accounts receivable clerk</strong> (CustInvoiceAccountsReceivableClerk)</span></span></li>
<li><span data-ttu-id="b8aab-149"><strong>Rappresentante assistenza clienti</strong> (TradeCustomerServiceRepresentative)</span><span class="sxs-lookup"><span data-stu-id="b8aab-149"><strong>Customer service representative</strong> (TradeCustomerServiceRepresentative)</span></span></li>
<li><span data-ttu-id="b8aab-150"><strong>Addetto vendite</strong> (TradeSalesClerk)</span><span class="sxs-lookup"><span data-stu-id="b8aab-150"><strong>Sales clerk</strong> (TradeSalesClerk)</span></span></li>
<li><span data-ttu-id="b8aab-151"><strong>Addetto spedizione</strong> (InventShippingClerk)</span><span class="sxs-lookup"><span data-stu-id="b8aab-151"><strong>Shipping clerk</strong> (InventShippingClerk)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>






