---
title: Profili certificato definiti dall'utente per i punti vendita al dettaglio
description: Questo argomento fornisce una panoramica su come vengono utilizzati i certificati nei punti vendita al dettaglio.
author: josaw
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2020-10-09
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 0b8bf49a8eb78d0557ef105b40dd4cb5f0d24ce4
ms.sourcegitcommit: 83ec80382bfeb693d5c5949b6f65296bd50eed12
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "3973935"
---
# <a name="user-defined-certificate-profiles-for-retail-stores"></a><span data-ttu-id="5ac9f-103">Profili certificato definiti dall'utente per i punti vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="5ac9f-103">User-defined certificate profiles for retail stores</span></span>

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="5ac9f-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="5ac9f-104">Overview</span></span>

<span data-ttu-id="5ac9f-105">In questo argomento viene fornita una panoramica dei profili certificato disponibili in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-105">This topic provides an overview of the certificate profiles that are available in Microsoft Dynamics 365 Commerce.</span></span> <span data-ttu-id="5ac9f-106">Questa funzionalità estende la funzionalità [Gestire segreti per i canali di vendita al dettaglio](../dev-itpro/manage-secrets.md) aggiungendo supporto per i certificati locali.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-106">This functionality extends the [Manage secrets for retail channels](../dev-itpro/manage-secrets.md) feature by adding support for local certificates.</span></span>

<span data-ttu-id="5ac9f-107">Quando il POS viene eseguito in modalità offline, non può accedere ai certificati archiviati nell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-107">While the point of sale (POS) is running in offline mode, it can't access the certificates that are stored in the key vault.</span></span> <span data-ttu-id="5ac9f-108">Al suo posto deve essere utilizzato il certificato locale.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-108">The local certificate should be used instead.</span></span> <span data-ttu-id="5ac9f-109">Sono supportate le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="5ac9f-109">The following capabilities are supported:</span></span>

- <span data-ttu-id="5ac9f-110">Utilizzo di certificati locali in scenari di fallback dell'insieme di credenziali delle chiavi</span><span class="sxs-lookup"><span data-stu-id="5ac9f-110">Using local certificates in key vault fallback scenarios</span></span>
- <span data-ttu-id="5ac9f-111">Utilizzo di certificati locali senza un insieme di credenziali delle chiavi (ad esempio in un'installazione locale)</span><span class="sxs-lookup"><span data-stu-id="5ac9f-111">Using local certificates without a key vault (for example in an on-premises installation)</span></span>
- <span data-ttu-id="5ac9f-112">Aggiornamento graduale dei certificati, dove alcuni punti vendita e terminali utilizzano una nuova versione del certificato, ma altri punti vendita e terminali continuano a utilizzare la versione precedente</span><span class="sxs-lookup"><span data-stu-id="5ac9f-112">Gradual update of certificates, where some stores and terminals use a new version of the certificate, but other stores and terminals continue to use the previous version</span></span>

<span data-ttu-id="5ac9f-113">La funzionalità dei profili di certificato consente di specificare un certificato predefinito e impostare l'ordine in cui viene effettuata la ricerca di certificati nello stesso profilo di certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-113">The certificate profiles functionality lets you specify a default certificate and set the order that certificates in the same certificate profile are searched in.</span></span> <span data-ttu-id="5ac9f-114">Questa funzionalità fornisce anche un approccio di configurazione simile per i certificati locali e per i certificati dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-114">This functionality also provides a similar setup approach for local certificates and Key Vault certificates.</span></span> <span data-ttu-id="5ac9f-115">Puoi aggiungere impostazioni specifiche dell'azienda per i certificati, ma l'identificatore univoco interaziendale per ogni certificato può essere utilizzato nei canali di Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-115">You can add company-specific settings for certificates, but the unique cross-company identifier for each certificate can be used in the Commerce channels.</span></span>

### <a name="scenarios"></a><span data-ttu-id="5ac9f-116">Scenari</span><span class="sxs-lookup"><span data-stu-id="5ac9f-116">Scenarios</span></span>

<span data-ttu-id="5ac9f-117">La funzionalità dei profili di certificato supporta i seguenti scenari nei canali di Commerce:</span><span class="sxs-lookup"><span data-stu-id="5ac9f-117">The certificate profiles functionality supports the following scenarios in the Commerce channels:</span></span>

- <span data-ttu-id="5ac9f-118">Utilizzo di un certificato locale in scenari di fallback dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-118">Use a local certificate in key vault fallback scenarios.</span></span> <span data-ttu-id="5ac9f-119">Di seguito sono riportati alcuni esempi di scenari di fallback:</span><span class="sxs-lookup"><span data-stu-id="5ac9f-119">Here are some examples of these fallback scenarios:</span></span>

    - <span data-ttu-id="5ac9f-120">L'archivio dell'insieme di credenziali delle chiavi non è accessibile.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-120">The key vault storage isn't accessible.</span></span>
    - <span data-ttu-id="5ac9f-121">Non è stato trovato un certificato nell'archivio dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-121">A certificate isn't found in the key vault storage.</span></span>
    - <span data-ttu-id="5ac9f-122">Il POS è eseguito in modalità offline.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-122">The POS is running in offline mode.</span></span>

- <span data-ttu-id="5ac9f-123">Utilizzo di certificati locali ma senza archiviarli nell'insieme di credenziali delle chiavi (ad esempio in un'installazione locale).</span><span class="sxs-lookup"><span data-stu-id="5ac9f-123">Use local certificates, but without storing them in the key vault (for example, in an on-premises installation).</span></span>
- <span data-ttu-id="5ac9f-124">Esecuzione di un aggiornamento graduale dei certificati, dove una nuova versione del certificato viene utilizzata solo nei punti vendita o sui terminali in cui la nuova versione è già disponibile.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-124">Do a gradual update of certificates, where a new version of the certificate is used only in stores or on terminals where the new version is already available.</span></span>
- <span data-ttu-id="5ac9f-125">Utilizzo dello stesso certificato in più aziende.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-125">Use the same certificate in several companies.</span></span>

## <a name="set-up-certificate-profiles"></a><span data-ttu-id="5ac9f-126">Impostare profili di certificato</span><span class="sxs-lookup"><span data-stu-id="5ac9f-126">Set up certificate profiles</span></span>

<span data-ttu-id="5ac9f-127">La seguente procedura spiega come impostare profili di certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-127">The following procedure explains how to set up certificate profiles.</span></span> <span data-ttu-id="5ac9f-128">Prima di utilizzare i profili di certificato nei canali di Commerce, segui questi passaggi per configurare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-128">Before you use certificate profiles in the Commerce channels, follow these steps to configure the settings.</span></span>

1. <span data-ttu-id="5ac9f-129">Nell'area di lavoro **Gestione funzionalità**, attiva la funzionalità **Profili di certificato definiti dall'utente per punti vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-129">In the **Feature management** workspace, turn on the **User-defined certificate profiles for retail stores** feature.</span></span>
2. <span data-ttu-id="5ac9f-130">Accedi a **Amministrazione sistema \> Imposta \> Profili certificato**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-130">Go to **System administration \> Setup \> Certificate profiles**.</span></span>
3. <span data-ttu-id="5ac9f-131">Crea un record e impostane i campi **Profilo certificato**, **Nome** e **Descrizione**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-131">Create a record, and set the **Certificate profile**, **Name**, and **Description** fields for it.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ac9f-132">Il profilo certificato è un identificatore univoco di un certificato in tutte le società e componenti di Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-132">The certificate profile is a unique identifier of a certificate across all companies and Commerce components.</span></span>

3. <span data-ttu-id="5ac9f-133">Nella scheda **Persone giuridiche**, aggiungi una riga e selezionare la persona giuridica (azienda) per la quale deve essere utilizzato il profilo di certificato corrente.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-133">On the **Legal entities** tab, add a line, and select the legal entity (company) that the current certificate profile should be used for.</span></span> <span data-ttu-id="5ac9f-134">Se il profilo di certificato deve essere utilizzato per più persone giuridiche, ripeti questo passaggio per aggiungere una riga per ciascuna persona giuridica aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-134">If the certificate profile should be used for multiple legal entities, repeat this step to add a line for each additional legal entity.</span></span>
4. <span data-ttu-id="5ac9f-135">Seleziona **Impostazioni** per aprire la pagina **Impostazioni del profilo certificato**, in cui puoi immettere impostazioni specifiche dell'azienda per il profilo di certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-135">Select **Settings** to open the **Certificate profile settings** page, where you can enter company-specific settings for the certificate profile.</span></span>

### <a name="certificate-profile-settings"></a><span data-ttu-id="5ac9f-136">Impostazioni del profilo di certificato</span><span class="sxs-lookup"><span data-stu-id="5ac9f-136">Certificate profile settings</span></span>

<span data-ttu-id="5ac9f-137">Quando selezioni **Impostazioni** per le righe del profilo di certificato, viene visualizzata la pagina **Impostazioni del profilo certificato**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-137">When you select **Settings** for certificate profile lines, the **Certificate profile settings** page appears.</span></span> <span data-ttu-id="5ac9f-138">Questa pagina consente di specificare quali certificati possono essere utilizzati quando il profilo di certificato corrente viene chiamato nei canali di Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-138">This page lets you specify which certificates can be used when the current certificate profile is called in the Commerce channels.</span></span> <span data-ttu-id="5ac9f-139">È inoltre possibile specificare l'ordine in cui deve essere eseguita la ricerca di certificati.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-139">You can also specify the order that certificates should be searched in.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac9f-140">Il campo **Priorità** viene impostato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-140">The **Priority** field is automatically set.</span></span> <span data-ttu-id="5ac9f-141">Il valore **1** rappresenta la priorità massima.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-141">A value of **1** represents the highest priority.</span></span> <span data-ttu-id="5ac9f-142">Quando viene aggiunta una nuova riga nella pagina **Impostazioni del profilo certificato**, la priorità di tale riga è impostata su un numero che è uno in più rispetto alla priorità della riga precedente.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-142">When a new line is added on the **Certificate profile settings** page, its priority is set to a number that is one more than the priority of the previous line.</span></span> <span data-ttu-id="5ac9f-143">Per modificare la priorità di una riga specifica, seleziona la riga, quindi seleziona **Sposta su** per aumentare la priorità o **Sposta giù** per diminuire la priorità.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-143">To change the priority of a specific line, select the line, and then select either **Move up** to increase the priority or **Move down** to decrease the priority.</span></span>

<span data-ttu-id="5ac9f-144">Quando aggiungi una nuova riga alla pagina **Impostazioni del profilo certificato**, imposta i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="5ac9f-144">When you add a new line to the **Certificate profile settings** page, set the following fields:</span></span>

- <span data-ttu-id="5ac9f-145">**Tipo di ubicazione** - Seleziona l'ubicazione in cui è archiviato il certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-145">**Location type** – Select the location where the certificate is stored.</span></span> <span data-ttu-id="5ac9f-146">Questo campo ha due possibili valori: **Certificato locale** e **Insieme di credenziali delle chiavi**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-146">This field has two possible values: **Local certificate** and **Key Vault**.</span></span>
- <span data-ttu-id="5ac9f-147">**Certificato insieme di credenziali delle chiavi** - Questo campo è obbligatorio se si imposta il campo **Tipo di ubicazione** su **Insieme di credenziali delle chiavi**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-147">**Key Vault certificate** – This field is required if you set the **Location type** field to **Key Vault**.</span></span> <span data-ttu-id="5ac9f-148">Utilizzalo per specificare un segreto del certificato dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-148">Use it to specify a Key Vault certificate secret.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ac9f-149">Prima di utilizzare un certificato dell'insieme di credenziali delle chiavi nei profili di certificato, assicurati di caricare un certificato nell'archivio dell'insieme di credenziali delle chiavi e segui le istruzioni in [Configurazione del client Azure Key Vault](https://docs.microsoft.com/dynamics365/finance/localizations/setting-up-azure-key-vault-client).</span><span class="sxs-lookup"><span data-stu-id="5ac9f-149">Before you use a Key Vault certificate in certificate profiles, be sure to upload a certificate to the key vault storage, and follow the instructions in [Set up the Azure Key Vault client](https://docs.microsoft.com/dynamics365/finance/localizations/setting-up-azure-key-vault-client).</span></span>

- <span data-ttu-id="5ac9f-150">**Nome punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-150">**Store name** – This field is optional and is available only if you set the **Location type** field to **Local certificate**.</span></span> <span data-ttu-id="5ac9f-151">Usalo per specificare un nome di punto vendita predefinito che deve essere usato per cercare certificati locali.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-151">Use it to specify a default store name that should be used to search local certificates.</span></span>
- <span data-ttu-id="5ac9f-152">**Ubicazione punto vendita** - Questo campo è facoltativo ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-152">**Store location** – This field is optional and is available only if you set the **Location type** field to **Local certificate**.</span></span> <span data-ttu-id="5ac9f-153">Usalo per specificare un'ubicazione di punto vendita predefinita che deve essere usata per cercare certificati locali.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-153">Use it to specify a default store location that should be used to search local certificates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5ac9f-154">Il nome e l'ubicazione del punto vendita predefiniti vengono aggiunti per semplificare il processo di ricerca dei certificati locali nel runtime di Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-154">The default store name and store location are added to simplify the process of searching local certificates in the Commerce runtime.</span></span> <span data-ttu-id="5ac9f-155">X509StoreProvider ha un elenco di cartelle in cui sono archiviati i certificati.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-155">X509StoreProvider has a list of folders where certificates are stored.</span></span> <span data-ttu-id="5ac9f-156">Se il nome e l'ubicazione del punto vendita predefiniti non sono specificati, X509StoreProvider prova a trovare un certificato nelle altre cartelle del relativo elenco.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-156">If the default store name and the default store location aren't specified, X509StoreProvider tries to find a certificate in the other folders on its list.</span></span>

- <span data-ttu-id="5ac9f-157">**Identificazione personale** - Questo campo è obbligatorio ed è disponibile solo se imposti il campo **Tipo di ubicazione** su **Certificato locale**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-157">**Thumbprint** – This field is required and available only if you set the **Location type** field to **Local certificate**.</span></span> <span data-ttu-id="5ac9f-158">Usalo per specificare l'identificazione personale del certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-158">Use it to specify the certificate thumbprint.</span></span>
- <span data-ttu-id="5ac9f-159">**Commenti** - Questo campo è facoltativo e consente agli utenti di immettere note.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-159">**Comments** – This field is optional and lets users enter notes.</span></span>

### <a name="workflow-searching-certificates-in-the-commerce-runtime"></a><span data-ttu-id="5ac9f-160">Flusso di lavoro: ricerca di certificati nel runtime di Commerce</span><span class="sxs-lookup"><span data-stu-id="5ac9f-160">Workflow: Searching certificates in the Commerce runtime</span></span>

<span data-ttu-id="5ac9f-161">Di seguito è riportato il flusso di lavoro di base utilizzato per cercare un certificato quando un profilo di certificato viene chiamato nel runtime di Commerce.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-161">Here is the basic workflow that is used to search for a certificate when a certificate profile is called in the Commerce runtime.</span></span>

1. <span data-ttu-id="5ac9f-162">Il sistema identifica se il profilo di certificato ha impostazioni specifiche dell'azienda per la persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-162">The system identifies whether the certificate profile has company-specific settings for the current legal entity.</span></span>
1. <span data-ttu-id="5ac9f-163">Il sistema tenta di trovare il certificato utilizzando i valori nella pagina **Impostazioni del profilo certificato** per la riga in cui il campo **Priorità** è impostato su **1**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-163">The system tries to find the certificate by using the values on the **Certificate profile settings** page for the line where the **Priority** field is set to **1**.</span></span>

    - <span data-ttu-id="5ac9f-164">Se il campo **Tipo di ubicazione** è impostato su **Insieme di credenziali delle chiavi**, il valore di **Segreto del certificato insieme di credenziali delle chiavi** viene utilizzato per cercare il certificato nella pagina **Parametri insieme di credenziali delle chiavi**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-164">If the **Location type** field is set to **Key Vault**, the value of the **Key Vault certificate secret** field is used to search for the certificate on the **Key vault parameters** page.</span></span> <span data-ttu-id="5ac9f-165">Il certificato viene quindi cercato nell'archivio dell'insieme di credenziali delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-165">The certificate is then searched for in the key vault storage.</span></span>
    - <span data-ttu-id="5ac9f-166">Se il campo **Tipo di ubicazione** è impostato su **Certificato locale**, X509StoreProvider cerca dapprima il certificato utilizzando il nome e l'ubicazione del punto vendita predefiniti, se questi parametri sono specificati.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-166">If the **Location type** field is set to **Local certificate**, X509StoreProvider first searches for the certificate by using the default store name and store location, if these parameters are specified.</span></span> <span data-ttu-id="5ac9f-167">Quindi cerca in tutte le altre cartelle nel relativo elenco di cartelle.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-167">It then searches in all other folders on its list of folders.</span></span>

1. <span data-ttu-id="5ac9f-168">Se il certificato non viene trovato, il processo viene ripetuto per la riga in cui il campo **Priorità** è impostato su **2** e così via.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-168">If the certificate isn't found, the process is repeated for the line where the **Priority** field is set to **2**, and so on.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac9f-169">Se il profilo di certificato non ha impostazioni per la persona giuridica corrente o se la ricerca del certificato non ha fornito un esito positivo per tutte le righe nella pagina **Impostazioni del profilo certificato**, il certificato non viene trovato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-169">If the certificate profile has no settings for the current legal entity, or if the certificate search is unsuccessful for all lines on the **Certificate profile settings** page, the certificate isn't found.</span></span>

#### <a name="caching-the-results-of-certificate-searches"></a><span data-ttu-id="5ac9f-170">Memorizzazione nella cache dei risultati delle ricerche di certificati</span><span class="sxs-lookup"><span data-stu-id="5ac9f-170">Caching the results of certificate searches</span></span>

<span data-ttu-id="5ac9f-171">I risultati delle ricerche di certificati vengono memorizzati nella cache.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-171">The results of certificate searches are cached.</span></span> <span data-ttu-id="5ac9f-172">Il tempo di scadenza predefinito per una cache è un'ora.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-172">The default expiration time for a cache is one hour.</span></span> <span data-ttu-id="5ac9f-173">Tuttavia, questo tempo può essere personalizzato e può essere impostato su un valore massimo di 24 ore.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-173">However, this time can be customized and can be set to a maximum value of 24 hours.</span></span>

### <a name="gradual-update"></a><span data-ttu-id="5ac9f-174">Aggiornamento graduale</span><span class="sxs-lookup"><span data-stu-id="5ac9f-174">Gradual update</span></span>

<span data-ttu-id="5ac9f-175">Se viene introdotta una nuova versione del certificato, ma non può essere aggiornata in tutti i punti vendita contemporaneamente, la funzionalità dei profili di certificato abilita l'aggiornamento graduale del certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-175">If a new version of the certificate is introduced, but it can't be updated in all stores at the same time, the certificate profiles functionality enables the certificate to be updated gradually.</span></span>

1. <span data-ttu-id="5ac9f-176">Trova un profilo di certificato e la riga da aggiornare, quindi seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-176">Find a certificate profile and the line that should be updated, and then select **Settings**.</span></span>
1. <span data-ttu-id="5ac9f-177">Aggiungi una riga e specifica le impostazioni relative all'ultima versione del certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-177">Add a line, and specify settings that are related to the latest version of the certificate.</span></span>
1. <span data-ttu-id="5ac9f-178">Aumenta il valore **Priorità** della nuova riga.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-178">Increase the **Priority** value of the new line.</span></span> <span data-ttu-id="5ac9f-179">Usa il pulsante **Sposta su** per spostare la riga in modo che si trovi sopra la riga della versione precedente dello stesso certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-179">Use the **Move up** button to move the line so that it's above the line for the previous version of the same certificate.</span></span>

> [!NOTE]
> <span data-ttu-id="5ac9f-180">Nel runtime di Commerce, verrà chiamata dapprima la nuova versione del certificato.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-180">In the Commerce runtime, the new version of the certificate will be called first.</span></span> <span data-ttu-id="5ac9f-181">Se il certificato non è stato ancora aggiornato in un punto vendita specifico o su un terminale specifico, verrà chiamata la versione precedente.</span><span class="sxs-lookup"><span data-stu-id="5ac9f-181">If the certificate hasn't yet been updated in a specific store or on a specific terminal, the previous version will be called.</span></span>