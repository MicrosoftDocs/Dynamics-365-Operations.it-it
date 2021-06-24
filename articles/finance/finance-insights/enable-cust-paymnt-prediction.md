---
title: Abilitare le previsioni di pagamento del cliente (anteprima)
description: Questo argomento spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Finance Insights.
author: ShivamPandey-msft
ms.date: 06/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: ae957f592ad9a1237817fec5d4172295f9a53020
ms.sourcegitcommit: 655b0e16c7aef6182cd58bc816b901470e1bb2ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "6222588"
---
# <a name="enable-customer-payment-predictions-preview"></a><span data-ttu-id="6aab7-103">Abilitare le previsioni di pagamento del cliente (anteprima)</span><span class="sxs-lookup"><span data-stu-id="6aab7-103">Enable customer payment predictions (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="6aab7-104">Questo argomento spiega come attivare e configurare la funzionalità Previsioni di pagamento del cliente in Finance Insights.</span><span class="sxs-lookup"><span data-stu-id="6aab7-104">This topic explains how to turn on and configure the Customer payment predictions feature in Finance insights.</span></span> <span data-ttu-id="6aab7-105">Puoi attivare la funzionalità nell'area di lavoro **Gestione funzionalità** e immettere le impostazioni di configurazione nella pagina **Parametri di Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-105">You turn on the feature in the **Feature management** workspace and enter configuration settings on the **Financial insights parameters** page.</span></span> <span data-ttu-id="6aab7-106">Questo argomento include anche informazioni che possono aiutarti a utilizzare efficacemente la funzionalità.</span><span class="sxs-lookup"><span data-stu-id="6aab7-106">This topic also includes information that can help you effectively use the feature.</span></span>

> [!NOTE]
> <span data-ttu-id="6aab7-107">Prima di completare i passaggi seguenti, assicurati di completare i passaggi prerequisiti nell'argomento [Configurare Finance Insights](configure-for-fin-insites.md).</span><span class="sxs-lookup"><span data-stu-id="6aab7-107">Before you complete the following steps, be sure to complete the prerequisite steps in the [Configure for Finance insights](configure-for-fin-insites.md) topic.</span></span>

1. <span data-ttu-id="6aab7-108">Utilizza le informazioni dalla pagina dell'ambiente in Microsoft Dynamics Lifecycle Services (LCS) per connetterti all'istanza primaria di Azure SQL per quell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="6aab7-108">Use information from the environment page in Microsoft Dynamics Lifecycle Services (LCS) to connect to the primary instance of Azure SQL for that environment.</span></span> <span data-ttu-id="6aab7-109">Esegui il seguente comando Transact-SQL (T-SQL) per attivare le versioni temporanee dell'ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="6aab7-109">Run the following Transact-SQL (T-SQL) command to turn on flights for the sandbox environment.</span></span> <span data-ttu-id="6aab7-110">Potrebbe essere necessario attivare l'accesso per il tuo indirizzo IP in LCS prima di poterti connettere in remoto a Application Object Server \[AOS\].</span><span class="sxs-lookup"><span data-stu-id="6aab7-110">(You might have to turn on access for your IP address in LCS before you can connect remotely to Application Object Server \[AOS\].)</span></span>

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('PayPredEnableFeature', 1)`

    > [!NOTE]
    > <span data-ttu-id="6aab7-111">Ignora questo passaggio se stai usando la versione 10.0.20 o successiva o una distribuzione di Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="6aab7-111">Skip this step if you're using version 10.0.20 or later, or if you're using a Service Fabric deployment.</span></span> <span data-ttu-id="6aab7-112">Il team di Finance Insights dovrebbe aver già attivato la versione di anteprima per te.</span><span class="sxs-lookup"><span data-stu-id="6aab7-112">The Finance insights team should already have turned on the flight for you.</span></span> <span data-ttu-id="6aab7-113">Se non vedi la funzionalità nell'area di lavoro **Gestione funzionalità** o se si verificano problemi quando tenti di attivarle, contatta <fiap@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="6aab7-113">If you don't see the feature in the **Feature management** workspace, or if you experience issues when you try to turn it on, contact <fiap@microsoft.com>.</span></span> 

2. <span data-ttu-id="6aab7-114">Attiva la funzionalità Informazioni sui pagamenti del cliente:</span><span class="sxs-lookup"><span data-stu-id="6aab7-114">Turn on the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="6aab7-115">Vai a **Amministrazione sistema \> Aree di lavoro \> Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-115">Go to **System administration \> Workspaces \> Feature management**.</span></span>
    2. <span data-ttu-id="6aab7-116">Trova la funzionalità denominata **Informazioni sui pagamenti dei clienti (anteprima)**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-116">Find the feature that is named **Customer payment insights (preview)**.</span></span>
    3. <span data-ttu-id="6aab7-117">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-117">Select **Enable now**.</span></span>

    <span data-ttu-id="6aab7-118">La funzione Informazioni sui pagamenti del cliente è ora attivata e pronta per essere configurata.</span><span class="sxs-lookup"><span data-stu-id="6aab7-118">The Customer payment insights feature is now turned on and ready to be configured.</span></span>

3. <span data-ttu-id="6aab7-119">Configura la funzionalità Informazioni sui pagamenti del cliente:</span><span class="sxs-lookup"><span data-stu-id="6aab7-119">Configure the Customer payment insights feature:</span></span>

    1. <span data-ttu-id="6aab7-120">Vai a **Credito e riscossioni \> Imposta \> Finance Insights \> Parametri di Finance Insights**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-120">Go to **Credit and collections \> Setup \> Finance insights \> Finance insights parameters**.</span></span>

        <span data-ttu-id="6aab7-121">[![Pagina dei parametri di Finance Insights prima della configurazione della funzione](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span><span class="sxs-lookup"><span data-stu-id="6aab7-121">[![Financial insights parameters page before the feature is configured](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)</span></span>

    2. <span data-ttu-id="6aab7-122">Nella pagina **Parametri di Finance Insights**, nella scheda **Informazioni dettagliate sui pagamenti dei clienti**, seleziona il collegamento **Visualizza i campi dati utilizzati nel modello di previsione** per aprire la pagina **Campi dati per il modello di previsione**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-122">On the **Financial insights parameters** page, on the **Customer payment insights** tab, select the **View the data fields used in the prediction model** link to open the **Data fields for prediction model** page.</span></span> <span data-ttu-id="6aab7-123">Qui puoi visualizzare l'elenco predefinito dei campi utilizzati per creare il modello di previsione dell'intelligenza artificiale (AI) per le previsioni di pagamento dei clienti.</span><span class="sxs-lookup"><span data-stu-id="6aab7-123">There, you can view the default list of fields that are used to create the artificial intelligence (AI) prediction model for customer payment predictions.</span></span>

        <span data-ttu-id="6aab7-124">Per utilizzare l'elenco di campi predefinito per creare il modello di previsione, chiudi la pagina **Campi dati per il modello di previsione**, quindi nella pagina **Parametri di Finance Insights**, imposta l'opzione **Abilita funzionalità** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-124">To use the default list of fields to create the prediction model, close the **Data fields for prediction model** page, and then, on the **Financial insights parameters** page, set the **Enable feature** option to **Yes**.</span></span>

    3. <span data-ttu-id="6aab7-125">Specifica il periodo di transazione "molto in ritardo" per definire cosa significa il bucket di previsione **Molto tardi** per la tua azienda.</span><span class="sxs-lookup"><span data-stu-id="6aab7-125">Specify the "very late" transaction period to define what the **Very late** prediction bucket means for your business.</span></span>

        <span data-ttu-id="6aab7-126">Per ogni fattura aperta, il sistema prevede la probabilità di pagamento in tre bucket: **Puntuale**, **In ritardo** e **Molto in ritardo**.</span><span class="sxs-lookup"><span data-stu-id="6aab7-126">For each open invoice, the system predicts the probability of payment in three buckets: **On time**, **Late**, and **Very late**.</span></span>

        - <span data-ttu-id="6aab7-127">**Puntuale**: questo bucket include i pagamenti che si prevede verranno pagati entro la data di scadenza della transazione.</span><span class="sxs-lookup"><span data-stu-id="6aab7-127">**On time** – This bucket includes payments that are predicted to be paid on or before the transaction due date.</span></span>
        - <span data-ttu-id="6aab7-128">**In ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo la data di scadenza della transazione ma prima dell'inizio del periodo di transazione "molto in ritardo".</span><span class="sxs-lookup"><span data-stu-id="6aab7-128">**Late** – This bucket includes payments that are predicted to be paid after the transaction due date but before the start of the "very late" transaction period.</span></span>
        - <span data-ttu-id="6aab7-129">**Molto in ritardo**: questo bucket include i pagamenti che si prevede verranno pagati dopo l'inizio del periodo di transazione "molto in ritardo".</span><span class="sxs-lookup"><span data-stu-id="6aab7-129">**Very late** – This bucket includes payments that are predicted to be paid after the start of the "very late" transaction period.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6aab7-130">Se modifichi il periodo di transazione "molto in ritardo" e selezioni **Modifica la soglia di ritardo** dopo che il modello di previsione IA per i pagamenti dei clienti è stato creato, il modello di previsione esistente viene eliminato e viene creato un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="6aab7-130">If you change the "very late" transaction period and select **Change late threshold** after the AI prediction model for customer payments has been created, the existing prediction model is deleted, and a new model is created.</span></span> <span data-ttu-id="6aab7-131">Il nuovo modello di previsione sposterà le transazioni nel periodo "molto in ritardo" in base alle impostazioni immesse per definirlo.</span><span class="sxs-lookup"><span data-stu-id="6aab7-131">The new prediction model will move transactions into the "very late" period, based on the settings that were entered to define it.</span></span>

    4. <span data-ttu-id="6aab7-132">Dopo aver finito di definire il periodo di transazione "molto in ritardo", seleziona **Crea modello di previsione** per creare il modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="6aab7-132">After you've finished defining the "very late" transaction period, select **Create prediction model** to create the prediction model.</span></span> <span data-ttu-id="6aab7-133">La sezione **Modello di previsione** nella pagina **Parametri di Finance Insights** mostra lo stato del modello di previsione.</span><span class="sxs-lookup"><span data-stu-id="6aab7-133">The **Prediction model** section on the **Financial insights parameters** page shows the status of the prediction model.</span></span>

        > [!NOTE]
        > <span data-ttu-id="6aab7-134">In qualsiasi momento durante la creazione del modello di previsione, puoi selezionare **Reimposta la creazione del modello** per riavviare il processo.</span><span class="sxs-lookup"><span data-stu-id="6aab7-134">At any time while the prediction model is being created, you can select **Reset model creation** to restart the process.</span></span>

    <span data-ttu-id="6aab7-135">La funzionalità è ora configurata è pronta per essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="6aab7-135">The feature has now been configured and is ready to be used.</span></span>

<span data-ttu-id="6aab7-136">Dopo che la funzionalità è stata attivata e configurata e il modello di previsione è stato creato e funziona, la sezione **Modello di previsione** della pagina **Parametri di Finance Insights** mostra la precisione del modello, come visualizzato nell'illustrazione seguente.</span><span class="sxs-lookup"><span data-stu-id="6aab7-136">After the feature has been turned on and configured, and the prediction model has been created and is working, the **Prediction model** section of the **Financial insights parameters** page shows the accuracy of the model, as shown in the following illustration.</span></span>

<span data-ttu-id="6aab7-137">[![Precisione del modello di previsione nella pagina Parametri di Finance Insights](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span><span class="sxs-lookup"><span data-stu-id="6aab7-137">[![Accuracy of the prediction model on the Financial insights parameters page](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)</span></span>

## <a name="release-details"></a><span data-ttu-id="6aab7-138">Dettagli del rilascio</span><span class="sxs-lookup"><span data-stu-id="6aab7-138">Release details</span></span>

<span data-ttu-id="6aab7-139">È disponibile un'anteprima pubblica di Informazioni dettagliate finanziarie per le distribuzioni di valutazione negli Stati Uniti, in Europa e nel Regno Unito.</span><span class="sxs-lookup"><span data-stu-id="6aab7-139">Finance insights public preview is available for trial deployments in the United States of America, Europe, and the United Kingdom.</span></span> <span data-ttu-id="6aab7-140">Microsoft sta aggiungendo in modo incrementale il supporto per più aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="6aab7-140">Microsoft is incrementally adding support for more regions.</span></span>

<span data-ttu-id="6aab7-141">Le funzionalità di anteprima pubblica possono e devono essere attivate solo negli ambienti sandbox di livello 2.</span><span class="sxs-lookup"><span data-stu-id="6aab7-141">Public preview features can and should be turned on only in Tier-2 sandbox environments.</span></span> <span data-ttu-id="6aab7-142">I modelli di configurazione e intelligenza artificiale creati in un ambiente sandbox non possono essere migrati in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="6aab7-142">Setup and AI models that are created in a sandbox environment can't be migrated to a production environment.</span></span> <span data-ttu-id="6aab7-143">Per ulteriori informazioni, vedi [Condizioni integrative per le versioni di anteprima di Microsoft Dynamics 365](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).</span><span class="sxs-lookup"><span data-stu-id="6aab7-143">For more information, see [Supplemental Terms of Use for Microsoft Dynamics 365 Previews](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
