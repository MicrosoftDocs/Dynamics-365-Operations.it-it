---
title: Panoramica delle firme elettroniche
description: Questo articolo fornisce una panoramica delle firme elettroniche e descrive come utilizzarle.
author: maertenm
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SIGParameters, SIGProcSetup, SIGReasonCode
audience: Application User
ms.reviewer: sericks
ms.custom: 13611
ms.assetid: 98dc6b79-1895-45d8-9dd1-2c8a351b58af
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 547ab10dabb6bb3f8ea41d0f80db227fc24411a3
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747713"
---
# <a name="electronic-signatures-overview"></a><span data-ttu-id="e8cb4-103">Panoramica firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="e8cb4-103">Electronic signatures overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e8cb4-104">Questo articolo fornisce una panoramica delle firme elettroniche e descrive come utilizzarle.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-104">This article provides an overview of electronic signatures and describes how they can be used.</span></span>

## <a name="what-is-an-electronic-signature"></a><span data-ttu-id="e8cb4-105">Firma elettronica</span><span class="sxs-lookup"><span data-stu-id="e8cb4-105">What is an electronic signature?</span></span>

<span data-ttu-id="e8cb4-106">Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-106">An electronic signature confirms the identity of a person who is about to start or approve a computing process.</span></span> <span data-ttu-id="e8cb4-107">In alcuni settori una firma elettronica è considerata legalmente vincolante come una firma manuale.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-107">In some industries, an electronic signature is as legally binding as a handwritten signature.</span></span>

<span data-ttu-id="e8cb4-108">Le firme elettroniche rappresentano un requisito di legge per diversi settori regolamentati, tra cui quello farmaceutico, quello alimentare e quello aerospaziale e della difesa.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-108">Electronic signatures are a regulations compliance requirement for several regulated industries, such as pharmaceuticals, food and beverage, and aerospace and defense.</span></span> <span data-ttu-id="e8cb4-109">Sono inoltre obbligatorie per la conformità alle normative incluse in 21 CFR Part 11 emanate dalla Food and Drug Administration (FDA) negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-109">They are also required for compliance with regulations in 21 CFR Part 11 that was issued by the Food and Drug Administration (FDA) in the United States.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cb4-110">Una firma elettronica in sé non equivale a una firma digitale.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-110">An electronic signature by itself isn't the same as a digital signature.</span></span> <span data-ttu-id="e8cb4-111">Una firma elettronica viene utilizzata soltanto in sostituzione di una firma manuale, mentre una firma digitale soddisfa ulteriori requisiti di sicurezza,</span><span class="sxs-lookup"><span data-stu-id="e8cb4-111">An electronic signature is just a substitute for a handwritten signature, whereas a digital signature provides additional security measures.</span></span> <span data-ttu-id="e8cb4-112">ad esempio consente di rilevare se i dati sono stati manomessi da un altro utente o processo.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-112">A digital signature can help identify whether another user or process has tampered with the data.</span></span> <span data-ttu-id="e8cb4-113">Una firma digitale può inoltre essere verificata e tale verifica non può essere rifiutata dal proprietario del certificato utilizzato per la firma dei dati.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-113">A digital signature can also be verified, and this verification can't be refuted by the owner of the certificate that was used to sign the data.</span></span> <span data-ttu-id="e8cb4-114">Come descritto più avanti, nelle firme elettroniche è incorporata la funzionalità di firma digitale.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-114">As described below, electronic signatures have built-in digital signature functionality.</span></span>

## <a name="electronic-signatures"></a><span data-ttu-id="e8cb4-115">Firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="e8cb4-115">Electronic signatures</span></span>

<span data-ttu-id="e8cb4-116">È possibile utilizzare le firme elettroniche per i processi aziendali critici.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-116">You can use electronic signatures for critical business processes.</span></span> <span data-ttu-id="e8cb4-117">In alcuni processi sono disponibili funzionalità di firma elettronica incorporate.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-117">Some processes have built-in electronic signature capabilities.</span></span> <span data-ttu-id="e8cb4-118">È inoltre possibile creare requisiti di firma personalizzati per qualsiasi tabella o campo di database.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-118">You can also create custom signature requirements for any database table and field.</span></span>

<span data-ttu-id="e8cb4-119">Nelle firme elettroniche è incorporata la funzionalità di firma digitale.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-119">Electronic signatures have built-in digital signature functionality.</span></span> <span data-ttu-id="e8cb4-120">Ogni utente che firma documenti deve ottenere un certificato di crittografia valido.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-120">Every user who signs documents must obtain a valid cryptographic certificate.</span></span> <span data-ttu-id="e8cb4-121">Al momento della firma di un documento, la chiave privata associata al certificato viene convalidata.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-121">When a document is signed, the private key that is associated with that certificate is validated.</span></span> <span data-ttu-id="e8cb4-122">Le informazioni relative alle firme elettroniche vengono memorizzate in un registro in modo da fornire un audit trail.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-122">Electronic signature information is recorded in a log to provide an audit trail.</span></span> <span data-ttu-id="e8cb4-123">Per impostare le firme elettroniche, vedere [Impostare le firme elettroniche](tasks/set-up-electronic-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="e8cb4-123">To set up electronic signatures, see [Set up electronic signatures](tasks/set-up-electronic-signatures.md).</span></span>

## <a name="users-who-require-access-to-electronic-signatures"></a><span data-ttu-id="e8cb4-124">Utenti che richiedono l'accesso alle firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="e8cb4-124">Users who require access to electronic signatures</span></span>

<span data-ttu-id="e8cb4-125">Tre tipi di utenti in genere richiedono l'accesso protetto alle firme elettroniche: amministratori delle firme elettroniche, firmatari e revisori delle firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-125">Three kinds of users typically require security access to electronic signatures: electronic signature administrators, signers, and electronic signature auditors.</span></span>

### <a name="electronic-signature-administrator"></a><span data-ttu-id="e8cb4-126">Amministratore delle firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="e8cb4-126">Electronic signature administrator</span></span>

<span data-ttu-id="e8cb4-127">L'amministratore delle firme elettroniche imposta i requisiti di firma, i parametri generali e gli approvatori e riceve gli avvisi quando le firme non possono essere verificate.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-127">The electronic signature administrator sets up signature requirements, general parameters, and approvers, and receives alerts when signatures can't be verified.</span></span> <span data-ttu-id="e8cb4-128">Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Responsabile IT** dispone dell'autorizzazione ad amministrare le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-128">By default, a user who belongs to the **Information technology manager** security role has permission to administer electronic signatures.</span></span>

### <a name="signer"></a><span data-ttu-id="e8cb4-129">Firmatario</span><span class="sxs-lookup"><span data-stu-id="e8cb4-129">Signer</span></span>

<span data-ttu-id="e8cb4-130">Un firmatario fornisce le firme elettroniche per i documenti e i processi per i quali sono richieste tali firme.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-130">A signer provides electronic signatures for documents and processes that require signatures.</span></span> <span data-ttu-id="e8cb4-131">Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Utente sistema** dispone dell'autorizzazione a firmare documenti elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-131">By default, a user who belongs to the **System user** security role has permission to sign documents electronically.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cb4-132">È possibile che il firmatario debba disporre di autorizzazioni aggiuntive per ottenere l'accesso ai dati correlati al documento o al processo da firmare.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-132">The signer might require additional permissions before access is granted to data that is related to the document or process that is being signed.</span></span> <span data-ttu-id="e8cb4-133">Un utente che apporta modifiche ai dati e deve quindi firmare per tali modifiche deve disporre dell'autorizzazione per la modifica dei dati.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-133">A user who changes data and must then sign for those changes must have permission to change the data.</span></span> <span data-ttu-id="e8cb4-134">Un utente firmatario per conto di un altro utente potrebbe non richiedere l'accesso ai dati.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-134">A user who signs on behalf of another user might not require access to the data.</span></span> <span data-ttu-id="e8cb4-135">Un esempio di questo tipo di utente è un supervisore che firma per le modifiche di un dipendente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-135">An example of this kind of user is a supervisor who signs for an employee's changes.</span></span>

### <a name="electronic-signature-auditor"></a><span data-ttu-id="e8cb4-136">Revisore delle firme elettroniche</span><span class="sxs-lookup"><span data-stu-id="e8cb4-136">Electronic signature auditor</span></span>

<span data-ttu-id="e8cb4-137">Il revisore delle firme elettroniche controlla il registro database e il registro di verifica delle firme disponibile nel registro database.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-137">The electronic signature auditor reviews the database log and the signature review log that is available from the database log.</span></span> <span data-ttu-id="e8cb4-138">Per impostazione predefinita, un utente che appartiene al ruolo di sicurezza **Responsabile IT** dispone dell'autorizzazione ad amministrare le firme elettroniche.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-138">By default, a user who belongs to the **Information technology manager** security role has permission to audit electronic signatures.</span></span>

<span data-ttu-id="e8cb4-139">Se si utilizza un ruolo diverso da **Responsabile IT**, assicurarsi che al ruolo siano assegnati i privilegi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8cb4-139">If you use a role other than **Information technology manager**, make sure that the role is assigned the following privileges:</span></span>

- <span data-ttu-id="e8cb4-140">Visualizza errori firma elettronica</span><span class="sxs-lookup"><span data-stu-id="e8cb4-140">View electronic signature failures</span></span>
- <span data-ttu-id="e8cb4-141">Visualizza registro database</span><span class="sxs-lookup"><span data-stu-id="e8cb4-141">View database log</span></span>

## <a name="signing-documents-electronically"></a><span data-ttu-id="e8cb4-142">Firma elettronica di documenti</span><span class="sxs-lookup"><span data-stu-id="e8cb4-142">Signing documents electronically</span></span>

### <a name="get-a-certificate"></a><span data-ttu-id="e8cb4-143">Ottenere un certificato</span><span class="sxs-lookup"><span data-stu-id="e8cb4-143">Get a certificate</span></span>

<span data-ttu-id="e8cb4-144">Per poter apporre la firma elettronica ai documenti, è necessario richiedere un certificato.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-144">Before you sign documents electronically, you must request a certificate.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cb4-145">Le funzionalità di Microsoft SQL Server sono utilizzate per creare certificati e abilitare la firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-145">Microsoft SQL Server features are used to create certificates and enable electronic signing.</span></span> <span data-ttu-id="e8cb4-146">Non è richiesto alcun certificato aggiuntivo o infrastruttura a chiave pubblica (PKI).</span><span class="sxs-lookup"><span data-stu-id="e8cb4-146">No additional certificate or public key infrastructure (PKI) is required.</span></span>

<span data-ttu-id="e8cb4-147">Per l'utente che richiede un certificato vengono create una chiave pubblica e una chiave privata.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-147">When you request a certificate, a public key and a private key are created for you.</span></span> <span data-ttu-id="e8cb4-148">La chiave privata viene crittografata mediante una password nota solo all'utente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-148">The private key is encrypted by using a password that is known only to you.</span></span> <span data-ttu-id="e8cb4-149">Al momento della firma elettronica di un documento, l'identità del firmatario viene verificata quando si immette la password.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-149">When you sign a document electronically, your identity is verified when you enter the password.</span></span>

<span data-ttu-id="e8cb4-150">Per richiedere un certificato, nella pagina **Opzioni** della scheda **Conti** , fare clic su **Ottieni certificato**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-150">To request a certificate, on the **Options** page, on the **Accounts** tab, click **Get certificate**.</span></span>

<span data-ttu-id="e8cb4-151">Immettere e confermare la password che verrà utilizzata per la firma.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-151">You must enter and confirm the password that you will use for signing.</span></span> <span data-ttu-id="e8cb4-152">La password consente la protezione della chiave privata e autorizza l'utilizzo del certificato.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-152">The password is used to protect your private key and authorize the use of your certificate.</span></span> <span data-ttu-id="e8cb4-153">La password non viene archiviata nel database e non è disponibile per altri utenti, nemmeno per l'amministratore.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-153">This password isn't stored in the database, and it isn't available to anyone else, not even to the administrator.</span></span>

<span data-ttu-id="e8cb4-154">Se si dimentica la password associata al certificato, quest'ultimo deve essere reimpostato.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-154">If you forget the password that is connected with your certificate, that certificate must be reset.</span></span> <span data-ttu-id="e8cb4-155">La reimpostazione del certificato non influisce sui documenti firmati con il certificato precedente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-155">If you reset the certificate, you don't affect documents that you signed by using the previous certificate.</span></span> <span data-ttu-id="e8cb4-156">Per reimpostare il certificato, nella pagina **Opzioni** fare clic su **Reimposta certificato**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-156">To reset the certificate, on the **Options** page, click **Reset certificate**.</span></span>

### <a name="sign-a-document-electronically"></a><span data-ttu-id="e8cb4-157">Apporre la firma elettronica a un documento</span><span class="sxs-lookup"><span data-stu-id="e8cb4-157">Sign a document electronically</span></span>

<span data-ttu-id="e8cb4-158">La pagina **Firma documento** viene visualizzata quando si apporta una modifica per la quale è richiesta una firma elettronica.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-158">The **Sign document** page is displayed when you make a change that requires an electronic signature.</span></span>

1. <span data-ttu-id="e8cb4-159">Nella pagina **Firma documento** fare clic sulla scheda **Documento** per verificare le modifiche apportate al documento.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-159">On the **Sign document** page, click the **Document** tab to review the changes to the document.</span></span>
2. <span data-ttu-id="e8cb4-160">Nella scheda **Firma** selezionare un codice motivo.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-160">On the **Signature** tab, select a reason code.</span></span>
3. <span data-ttu-id="e8cb4-161">Immettere un commento, se è richiesto un commento.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-161">Enter a comment, if a comment is required.</span></span>
4. <span data-ttu-id="e8cb4-162">Se l'ID dell'utente non viene visualizzato nel campo **Firmatario**, selezionarlo dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-162">If your user ID doesn't appear in the **Signer** field, select it in the list.</span></span>
5. <span data-ttu-id="e8cb4-163">Immettere l'ubicazione, se queste informazioni sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-163">Enter your location, if this information is required.</span></span>
6. <span data-ttu-id="e8cb4-164">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-164">Click **OK**.</span></span>

### <a name="sign-for-another-users-changes"></a><span data-ttu-id="e8cb4-165">Firma per le modifiche apportate da un altro utente</span><span class="sxs-lookup"><span data-stu-id="e8cb4-165">Sign for another user's changes</span></span>

<span data-ttu-id="e8cb4-166">Talvolta si può decidere che un utente firmi per le modifiche apportate da altri.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-166">Occasionally, you might want a user to sign for another user's changes.</span></span> <span data-ttu-id="e8cb4-167">È ad esempio possibile che un supervisore debba firmare per le modifiche apportate alle distinte base (DBA) da un dipendente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-167">For example, a supervisor might be required to sign for changes that an employee makes to a bill of materials (BOM).</span></span> <span data-ttu-id="e8cb4-168">Utilizzare questa procedura per designare un utente come firmatario per un altro utente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-168">Use this procedure to designate a user as a signer for another user.</span></span>

> [!NOTE]
> <span data-ttu-id="e8cb4-169">Quando un utente firma per una modifica apportata da un altro, la firma deve essere fornita alla workstation dell'utente autore della modifica.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-169">When one user signs for another user's change, the signature must be provided at the workstation of the user who made the change.</span></span> <span data-ttu-id="e8cb4-170">Quest'ultimo sarà in grado di salvare la modifica solo dopo che è stata fornita la firma.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-170">The user can't save the change until the signature has been provided.</span></span>

<span data-ttu-id="e8cb4-171">Per designare gli approvatori, attenersi alla procedura indicata di seguito.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-171">To designate approvers, follow these steps.</span></span>

1. <span data-ttu-id="e8cb4-172">Nella pagina **Opzioni** , nella scheda **Conti** , fare clic su **Approvatore designato**.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-172">On the **Options** page, on the **Accounts** tab, click **Designate approver**.</span></span>
2. <span data-ttu-id="e8cb4-173">Nel campo **ID utente approvatore** selezionare l'ID dell'utente che deve firmare per le modifiche apportate da un altro utente.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-173">In the **Approver user ID** field, select the ID of the user who must sign for another user's changes.</span></span>
3. <span data-ttu-id="e8cb4-174">Nel campo **ID utente per firma** selezionare l'ID dell'utente che ha apportato le modifiche per le quali è richiesta la firma.</span><span class="sxs-lookup"><span data-stu-id="e8cb4-174">In the **Sign for user ID** field, select the ID of the user whose changes must be signed for.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]