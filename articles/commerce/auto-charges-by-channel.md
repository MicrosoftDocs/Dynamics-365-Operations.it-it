---
title: Abilitare e configurare addebiti automatici per canale
description: Questo argomento spiega come abilitare e configurare le spese automatiche per canale in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 1be07c754e563298d82f6ca54f09ae3aa9118602
ms.sourcegitcommit: 4e9b3746790355f9f72bbfddc099c4065a49ad63
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/30/2020
ms.locfileid: "3175425"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="54993-103">Abilitare e configurare addebiti automatici per canale</span><span class="sxs-lookup"><span data-stu-id="54993-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="54993-104">Questo argomento spiega come abilitare e configurare le spese automatiche per canale in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="54993-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="54993-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="54993-105">Overview</span></span>

<span data-ttu-id="54993-106">È possibile avere scenari in cui le spese per il riciclaggio o altre spese devono essere applicate a un gruppo di prodotti venduti in tutti o in alcuni punti vendita in uno stato specifico (ad esempio, California).</span><span class="sxs-lookup"><span data-stu-id="54993-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="54993-107">La funzione **Abilita filtro spese automatiche per canale** in Commerce consente di specificare le spese automatiche per canale (ad esempio, un canale tradizionale specifico).</span><span class="sxs-lookup"><span data-stu-id="54993-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="54993-108">Questa funzionalità è disponibile in Dynamics 365 Commerce versione 10.0.10 e successiva.</span><span class="sxs-lookup"><span data-stu-id="54993-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="54993-109">Per abilitare e configurare le spese automatiche per canale, è necessario completare le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="54993-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="54993-110">Attivare la funzionalità **Abilita filtro spese automatiche per canale**.</span><span class="sxs-lookup"><span data-stu-id="54993-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="54993-111">Configurare lo scopo della gerarchia organizzativa.</span><span class="sxs-lookup"><span data-stu-id="54993-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="54993-112">Definire le spese automatiche per canale.</span><span class="sxs-lookup"><span data-stu-id="54993-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="54993-113">La funzionalità **Abilita filtro spese automatiche per canale** funziona solo se è attiva anche la funzione di spese automatiche avanzate.</span><span class="sxs-lookup"><span data-stu-id="54993-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="54993-114">Per informazioni su come attivare la funzione di spese automatiche avanzate, vedere [Spese automatiche avanzate omnicanale](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="54993-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="54993-115">Attivare la funzionalità Abilita filtro spese automatiche per canale</span><span class="sxs-lookup"><span data-stu-id="54993-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="54993-116">Per abilitare le spese automatiche per canale in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="54993-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="54993-117">Passare in **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="54993-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="54993-118">Nella scheda **Non abilitato**, nell'elenco **Nome della funzione**, trovare e selezionare **Abilita filtro spese automatiche per canale**.</span><span class="sxs-lookup"><span data-stu-id="54993-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="54993-119">Nell'angolo in basso a destra, selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="54993-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="54993-120">Dopo che la funzione è stata attivata, verrà visualizzata nell'elenco nella scheda **Tutte**.</span><span class="sxs-lookup"><span data-stu-id="54993-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="54993-121">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="54993-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="54993-122">Nel riquadro a sinistra, trovare e selezionare il processo **1110** (**Configurazione globale**).</span><span class="sxs-lookup"><span data-stu-id="54993-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="54993-123">Nel riquadro azioni selezionare **Esegui ora** per propagare le modifiche alla configurazione.</span><span class="sxs-lookup"><span data-stu-id="54993-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="54993-124">Se si disattiva la funzionalità **Abilita filtro spese automatiche per canale** dopo averla già utilizzata, il campo **Relazione canale di vendita al dettaglio** sotto **Spese automatiche** non verrà più visualizzato e si perderanno tutte le configurazioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="54993-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="54993-125">Se la rimozione delle configurazioni **Relazione canale di vendita al dettaglio** causa la duplicazione delle regole delle spese automatiche, il tentativo di disattivare la funzione non riesce.</span><span class="sxs-lookup"><span data-stu-id="54993-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="54993-126">Prima di disattivare la funzione, assicurarsi di rivedere tutte le regole delle spese automatiche e apportare le modifiche necessarie.</span><span class="sxs-lookup"><span data-stu-id="54993-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="54993-127">Configurare lo scopo della gerarchia organizzativa</span><span class="sxs-lookup"><span data-stu-id="54993-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="54993-128">Un nuovo scopo della gerarchia organizzativa denominato **Spese automatiche vendita al dettaglio** è stato creato per gestire la gerarchia delle spese automatiche per canale.</span><span class="sxs-lookup"><span data-stu-id="54993-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="54993-129">Per assegnare una gerarchia predefinita a uno scopo della gerarchia dell'organizzazione in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="54993-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="54993-130">Andare in **Amministrazione organizzazione \> Organizzazioni \> Scopi gerarchia organizzativa**.</span><span class="sxs-lookup"><span data-stu-id="54993-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="54993-131">Nel riquadro a sinistra selezionare **Spese automatiche vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="54993-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="54993-132">In **Gerarchie assegnate**, selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="54993-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="54993-133">Nella finestra di dialogo **Gerarchie organizzative** selezionare una gerarchia organizzativa (ad esempio, **Punti vendita al dettaglio per area geografica**), quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="54993-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="54993-134">In **Gerarchie assegnate**, selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="54993-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="54993-135">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="54993-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="54993-136">Nel riquadro a sinistra, trovare e selezionare il processo **1040** (**Prodotti**).</span><span class="sxs-lookup"><span data-stu-id="54993-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="54993-137">Nel riquadro azioni selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="54993-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="54993-138">Ripetere i due passaggi precedenti per eseguire i processi **1070** (**Configurazione del canale**) e **1110** (**Configurazione globale**).</span><span class="sxs-lookup"><span data-stu-id="54993-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Configurazione dello scopo della gerarchia organizzativa per le spese automatiche vendita al dettaglio](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="54993-140">Definire le spese automatiche per canale</span><span class="sxs-lookup"><span data-stu-id="54993-140">Define auto charges by channel</span></span>

<span data-ttu-id="54993-141">Dopo aver attivato la funzionalità **Abilita filtro spese automatiche per canale** e configurato lo scopo della gerarchia organizzativa **Spese automatiche vendita al dettaglio**, le spese automatiche per canale possono essere definite a livello di intestazione dell'ordine o a livello di riga dell'ordine.</span><span class="sxs-lookup"><span data-stu-id="54993-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="54993-142">Per definire le spese automatiche per canale in Commerce, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="54993-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="54993-143">Accedere a **Contabilità clienti \> Impostazione spese \> Spese automatiche**.</span><span class="sxs-lookup"><span data-stu-id="54993-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="54993-144">Nel riquadro a sinistra, nel campo **Livello**, selezionare **Intestazione** o **Riga**, a seconda delle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="54993-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="54993-145">Nel campo **Codice canale di vendita al dettaglio**, selezionare il codice canale appropriato (ad esempio, **Tabella** o **Gruppo**).</span><span class="sxs-lookup"><span data-stu-id="54993-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="54993-146">Se l'impostazione predefinita **Tutti** è utilizzata, le regole di addebito vengono applicate a tutti i canali.</span><span class="sxs-lookup"><span data-stu-id="54993-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="54993-147">Se si seleziona **Gruppo**, assicurarsi che venga creato un gruppo di spese per i canali di vendita al dettaglio in **Retail e Commerce \> Impostazione canale \> Spese \> Gruppi di spese canale di vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="54993-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="54993-148">Se si seleziona **Tabella**, è possibile selezionare un canale specifico (ad esempio, **San Francisco**) nel campo **Relazione canale di vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="54993-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="54993-149">Selezionare **Retail e Commerce \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**.</span><span class="sxs-lookup"><span data-stu-id="54993-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="54993-150">Nel riquadro a sinistra, trovare e selezionare il processo **1040** (**Prodotti**).</span><span class="sxs-lookup"><span data-stu-id="54993-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="54993-151">Nel riquadro azioni selezionare **Esegui adesso**.</span><span class="sxs-lookup"><span data-stu-id="54993-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="54993-152">Ripetere i due passaggi precedenti per eseguire i processi **1070** (**Configurazione del canale**) e **1110** (**Configurazione globale**).</span><span class="sxs-lookup"><span data-stu-id="54993-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Spese automatiche definite per canale](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="54993-154">Scenario di esempio</span><span class="sxs-lookup"><span data-stu-id="54993-154">Example scenario</span></span>

<span data-ttu-id="54993-155">L'esempio seguente descrive i passaggi necessari per configurare un prodotto in modo che le spese per il riciclaggio vengano addebitati quando il prodotto viene venduto attraverso un canale fisico San Francisco.</span><span class="sxs-lookup"><span data-stu-id="54993-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="54993-156">L'esempio mostra anche come vengono visualizzate le spese automatiche nell'applicazione Commerce POS (POS).</span><span class="sxs-lookup"><span data-stu-id="54993-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="54993-157">L'organizzazione definisce un codice di spesa denominato **RECYCLE**, come mostrato nella seguente illustrazione.</span><span class="sxs-lookup"><span data-stu-id="54993-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Codice di addebito RECYCLE](media/Auto-charges-charge-code.png)

<span data-ttu-id="54993-159">Una spesa automatica è creata a livello di riga.</span><span class="sxs-lookup"><span data-stu-id="54993-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="54993-160">Ha la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="54993-160">It has the following configuration:</span></span>

- <span data-ttu-id="54993-161">Il campo **Codice conto** è impostato su **Tutto**.</span><span class="sxs-lookup"><span data-stu-id="54993-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="54993-162">Il campo **Codice articolo** è impostato su **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="54993-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="54993-163">Il campo **Relazione articolo** è impostato sull'ID prodotto **91001**.</span><span class="sxs-lookup"><span data-stu-id="54993-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="54993-164">Il campo **Codice modalità di consegna** è impostato su **Tutto**.</span><span class="sxs-lookup"><span data-stu-id="54993-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="54993-165">Il campo **Codice canale di vendita al dettaglio** è impostato su **Tabella**.</span><span class="sxs-lookup"><span data-stu-id="54993-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="54993-166">La campo **Relazione canale di vendita al dettaglio** è impostato sul punto vendita **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="54993-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="54993-167">Viene creata una riga di spese automatiche.</span><span class="sxs-lookup"><span data-stu-id="54993-167">An auto charges line is created.</span></span> <span data-ttu-id="54993-168">Ha la seguente configurazione:</span><span class="sxs-lookup"><span data-stu-id="54993-168">It has the following configuration:</span></span>

- <span data-ttu-id="54993-169">Il campo **Valuta** è impostato su **USD**.</span><span class="sxs-lookup"><span data-stu-id="54993-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="54993-170">Il campo **Codice spese** è impostato su **RECYCLE**.</span><span class="sxs-lookup"><span data-stu-id="54993-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="54993-171">Il campo **Categoria** è impostato su **Fisso**.</span><span class="sxs-lookup"><span data-stu-id="54993-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="54993-172">Il campo **Spese** è impostato su **$ 6,25**.</span><span class="sxs-lookup"><span data-stu-id="54993-172">The **Charges** field is set to **$6.25**.</span></span>

![Configurazione delle spese automatiche a livello di riga e della riga di spese automatiche](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="54993-174">Nell'applicazione POS, un ordine cliente viene creato nel canale del punto vendita **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="54993-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="54993-175">La riga **Spese** mostra le spese per il riciclaggio di **$ 6,25**.</span><span class="sxs-lookup"><span data-stu-id="54993-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="54993-176">Selezionando **Opzioni di transazione \> Spese \> Gestisci spese** nell'applicazione POS, è possibile visualizzare il codice di addebito e la descrizione per le spese per il riciclaggio.</span><span class="sxs-lookup"><span data-stu-id="54993-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Spese per il riciclaggio nell'applicazione POS](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="54993-178">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="54993-178">Additional resources</span></span>

[<span data-ttu-id="54993-179">Addebiti automatici avanzati omnicanale</span><span class="sxs-lookup"><span data-stu-id="54993-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="54993-180">Spese intestazione con ripartizione proporzionale in righe di vendita corrispondenti</span><span class="sxs-lookup"><span data-stu-id="54993-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)
