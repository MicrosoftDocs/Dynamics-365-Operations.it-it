---
title: Dichiarazione della ritenuta d'acconto per l'Egitto
description: In questo argomento viene descritto come configurare e generare le dichiarazioni della ritenuta d'acconto per l'Egitto.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: rhaertle
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 4e3d68ac003fabaa504ffe81b8bf2f7ff8d7538d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5839794"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a><span data-ttu-id="19490-103">Dichiarazione della ritenuta d'acconto per l'Egitto (EG-00005)</span><span class="sxs-lookup"><span data-stu-id="19490-103">Withholding tax declaration for Egypt (EG-00005)</span></span>

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a><span data-ttu-id="19490-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="19490-104">Overview</span></span>
<span data-ttu-id="19490-105">In questo argomento viene illustrato come impostare e generare la dichiarazione della ritenuta d'acconto e i moduli 41 e 11 della dichiarazione della ritenuta d'acconto per le persone giuridiche in Egitto</span><span class="sxs-lookup"><span data-stu-id="19490-105">This topic explains how to set up and generate the withholding tax declaration and the withholding tax declaration forms 41 and 11 for legal entities in Egypt</span></span> 

<span data-ttu-id="19490-106">Tutte le entità egiziane devono preparare il modulo 41 che riassume tutte le imposte trattenute dei fornitori locali e dei fornitori di servizi.</span><span class="sxs-lookup"><span data-stu-id="19490-106">All Egyptian entities must prepare the form  41 which summarizes all taxes that are retained from local suppliers and service providers.</span></span> <span data-ttu-id="19490-107">Oltre al modulo 41, deve essere generato il modulo 11 per dettagliare tutte le trattenute dei fornitori esteri.</span><span class="sxs-lookup"><span data-stu-id="19490-107">In addition to form 41, form 11 must be generated to detail all of the retained taxed from foreign providers.</span></span> 

<span data-ttu-id="19490-108">Il report **Dichiarazione della ritenuta d'acconto** in Dynamics 365 Finance include i seguenti report:</span><span class="sxs-lookup"><span data-stu-id="19490-108">The **Withholding tax declaration** report in Dynamics 365 Finance includes the following reports:</span></span>

- <span data-ttu-id="19490-109">Modulo dichiarazione n.</span><span class="sxs-lookup"><span data-stu-id="19490-109">Declaration form No.</span></span> <span data-ttu-id="19490-110">41</span><span class="sxs-lookup"><span data-stu-id="19490-110">41</span></span>
- <span data-ttu-id="19490-111">Modulo dichiarazione n.</span><span class="sxs-lookup"><span data-stu-id="19490-111">Declaration form No.</span></span> <span data-ttu-id="19490-112">11</span><span class="sxs-lookup"><span data-stu-id="19490-112">11</span></span>
    
    
## <a name="prerequisites"></a><span data-ttu-id="19490-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="19490-113">Prerequisites</span></span>
<span data-ttu-id="19490-114">L'indirizzo principale della persona giuridica deve essere in Egitto.</span><span class="sxs-lookup"><span data-stu-id="19490-114">The primary address of the legal entity must be in Egypt.</span></span>
<span data-ttu-id="19490-115">Nell'area di lavoro **Gestione funzionalità**, la seguente funzionalità deve essere abilitata:</span><span class="sxs-lookup"><span data-stu-id="19490-115">In the **Feature management** workspace, the following feature must be enabled:</span></span>

   - <span data-ttu-id="19490-116">**Ritenuta d'acconto globale**</span><span class="sxs-lookup"><span data-stu-id="19490-116">**Global withholding tax**</span></span>

<span data-ttu-id="19490-117">Per ulteriori informazioni su come abilitare le funzionalità, vedere [Panoramica della gestione funzionalità.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="19490-117">For more information about how to enable features, see [Feature management overview.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)</span></span>

1. <span data-ttu-id="19490-118">Selezionare **Imposta** > **Impostazione** > **Parametri** > **Parametri di contabilità generale** e quindi nella scheda **Ritenuta d'acconto** impostare l'opzione **Attiva ritenuta d'acconto globale** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="19490-118">Go to **Tax** > **Setup** > **Parameters** > **General ledger parameters**, and on the **Withholding tax** tab, set **Enable global withholding tax** to **Yes**.</span></span>
2. <span data-ttu-id="19490-119">Nell'area di lavoro **Creazione di report elettronici**, importare i seguente formati di Creazione di report elettronici dal repository:</span><span class="sxs-lookup"><span data-stu-id="19490-119">In the **Electronic reporting** workspace, import the following Electronic reporting formats from the repository:</span></span>

    - <span data-ttu-id="19490-120">Excel di dichiarazione RIT (EG)</span><span class="sxs-lookup"><span data-stu-id="19490-120">WHT Declaration Excel (EG)</span></span>

    > [!NOTE]
    > <span data-ttu-id="19490-121">Il formato sopra è basato sul **Modello di dichiarazione fiscale** e utilizza il **Mapping del modello di dichiarazione fiscale**.</span><span class="sxs-lookup"><span data-stu-id="19490-121">The format above is based on the **Tax declaration model** and uses the **Tax declaration model mapping**.</span></span> <span data-ttu-id="19490-122">Questa configurazione aggiuntiva viene importata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="19490-122">This additional configuration is automatically imported.</span></span>

<span data-ttu-id="19490-123">Per ulteriori informazioni su come importare le configurazioni per la creazione di report elettronici, vedere [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="19490-123">For more information about how to import Electronic reporting configurations, see [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

## <a name="download-electronic-reporting-configurations"></a><span data-ttu-id="19490-124">Scaricare configurazioni per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="19490-124">Download Electronic reporting configurations</span></span>

<span data-ttu-id="19490-125">L'implementazione dei moduli di dichiarazione RIT per l'Egitto si basa sulle configurazioni per la creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="19490-125">The implementation of the WHT declaration forms for Egypt is based on Electronic reporting (ER) configurations.</span></span> <span data-ttu-id="19490-126">Per ulteriori informazioni sulle funzionalità e sui concetti di creazione di report configurabili, vedere [Creazione di report elettronici](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span><span class="sxs-lookup"><span data-stu-id="19490-126">For more information about the capabilities and concepts of configurable reporting, see [Electronic reporting](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).</span></span>

<span data-ttu-id="19490-127">Per gli ambienti di produzione e test di accettazione dell'utente (UAT), seguire le istruzioni nell'argomento [Scaricare le configurazioni per la creazione di report elettronici da Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span><span class="sxs-lookup"><span data-stu-id="19490-127">For production and user acceptance testing (UAT) environments, follow the instructions in the topic, [Download Electronic reporting configurations from Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).</span></span>

<span data-ttu-id="19490-128">Per generare le dichiarazioni della ritenuta d'acconto in una persona giuridica egiziana, è necessario caricare le seguenti configurazioni:</span><span class="sxs-lookup"><span data-stu-id="19490-128">To generate the Withholding declarations in an Egyptian legal entity, you need to upload the following configurations:</span></span>

- <span data-ttu-id="19490-129">Tax declaration model.version.82.xml o una versione successiva</span><span class="sxs-lookup"><span data-stu-id="19490-129">Tax declaration model.version.82.xml or later version</span></span>
- <span data-ttu-id="19490-130">Tax declaration model mapping.version.82.133.xml o versione successiva</span><span class="sxs-lookup"><span data-stu-id="19490-130">Tax declaration model mapping.version.82.133.xml or a later version</span></span>
- <span data-ttu-id="19490-131">WHT Declaration Excel (EG).version.82.21 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="19490-131">WHT Declaration Excel (EG).version.82.21  or a later version</span></span>

<span data-ttu-id="19490-132">Dopo aver completato il download delle configurazioni ER da Lifecycle Services (LCS) o dal repository globale, completare i seguenti passaggi.</span><span class="sxs-lookup"><span data-stu-id="19490-132">After you finish downloading the ER configurations from Lifecycle Services (LCS) or the global repository, complete the following steps.</span></span>

1. <span data-ttu-id="19490-133">Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="19490-133">Go to the **Electronic reporting** workspace and select the **Reporting configurations** tile.</span></span>
1. <span data-ttu-id="19490-134">Nella pagina **Configurazioni**, nel riquadro Azioni, selezionare **Exchange > Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="19490-134">On the **Configurations** page, on the Action Pane, select **Exchange > Load from XML file**.</span></span>
1. <span data-ttu-id="19490-135">Caricare tutti i file nell'ordine in cui sono elencati nei punti precedenti.</span><span class="sxs-lookup"><span data-stu-id="19490-135">Upload all the files in the order in which they are listed in the previous bullets.</span></span> <span data-ttu-id="19490-136">Dopo che tutte le configurazioni sono state caricate, l'albero di configurazione deve essere presente in Finance.</span><span class="sxs-lookup"><span data-stu-id="19490-136">After all of the configurations are uploaded, the configuration tree should be present in Finance.</span></span>

## <a name="set-up-application-specific-parameters"></a><span data-ttu-id="19490-137">Configurare parametri specifici dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="19490-137">Set up application-specific parameters</span></span>

<span data-ttu-id="19490-138">I parametri specifici dell'applicazione consentono agli utenti di stabilire i criteri di classificazione e calcolo delle transazioni fiscali in ogni riga di un report generato a seconda della configurazione del **gruppo di articoli di ritenuta d'acconto** o altri criteri stabiliti nella definizione di ricerca.</span><span class="sxs-lookup"><span data-stu-id="19490-138">The application-specific parameters option lets users establish the criteria of how the tax transactions will be classified and calculated in each line of a generated report depending on the configuration of **withholding tax item group** or other criteria established in the definition of lookup.</span></span>

<span data-ttu-id="19490-139">Il modulo 41 della dichiarazione della ritenuta d'acconto include una colonna specifica in cui la transazione della ritenuta di acconto deve essere classificata in base alla classificazione dell'ufficio tributario denominata **Tipo di codice sconto**.</span><span class="sxs-lookup"><span data-stu-id="19490-139">Withholding declaration form 41 includes a specific column where the withholding tax transaction must be classified in accordance with the tax authority classification named **Discount code type**.</span></span> <span data-ttu-id="19490-140">Anziché includere queste nuove classificazioni come nuovi dati di immissione quando le transazioni vengono registrate, le classificazioni saranno determinate in base alle diverse ricerche introdotte in **Configurazioni** > **Configurare parametri specifici dell'applicazione** > **Impostazioni** per soddisfare i requisiti dei report di ritenuta d'acconto per l'Egitto.</span><span class="sxs-lookup"><span data-stu-id="19490-140">Instead of including these new classifications as new entry data when the transactions are posted, the classifications will be determined based on the different lookups introduced in **Configurations** > **Set up application-specific parameters** > **Setup** to meet the requirements of withholding reports for Egypt.</span></span> 

<span data-ttu-id="19490-141">La configurazione seguente viene utilizzata per classificare le transazioni nel report Modulo 41 dichiarazione ritenuta d'acconto:</span><span class="sxs-lookup"><span data-stu-id="19490-141">The following configuration is used to classify the transactions in the Withholding declaration form 41 report:</span></span>

- <span data-ttu-id="19490-142">**DiscountTaxTypeLookup**-> Colonna n. 18</span><span class="sxs-lookup"><span data-stu-id="19490-142">**DiscountTaxTypeLookup**-> Column No 18</span></span> 

<span data-ttu-id="19490-143">Completare i passaggi seguenti per impostare le differenti ricerche utilizzate per generare i report sulla dichiarazione della ritenuta d'acconto e sui libri correlati.</span><span class="sxs-lookup"><span data-stu-id="19490-143">Complete the following steps to set up the different lookups used to generate the WHT declaration and related books reports.</span></span> 

1. <span data-ttu-id="19490-144">Nell'area di lavoro **Creazione di report elettronici**, selezionare **Configurazioni** > **Impostazione** per impostare le regole per identificare come le transazioni sono classificate nel report sulla dichiarazione della ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="19490-144">In the **Electronic reporting** workspace, select **Configurations** > **Setup** to set up the rules to identify how transactions are classified in the WHT declaration report.</span></span> 
2. <span data-ttu-id="19490-145">Selezionare la versione corrente e nella Scheda dettaglio **Ricerche** selezionare il nome della ricerca.</span><span class="sxs-lookup"><span data-stu-id="19490-145">Select the current version, and on the **Lookups** FastTab, select the lookup name.</span></span> <span data-ttu-id="19490-146">Ad esempio, **DiscountTaxTypeLookup**.</span><span class="sxs-lookup"><span data-stu-id="19490-146">For example, **DiscountTaxTypeLookup**.</span></span> <span data-ttu-id="19490-147">Questa ricerca identifica l'elenco di tipi di sconto richiesti dall'ufficio tributario.</span><span class="sxs-lookup"><span data-stu-id="19490-147">This lookup identifies the list of discount types required by the tax authority.</span></span>
3. <span data-ttu-id="19490-148">Nella Scheda dettaglio **Condizioni**, selezionare **Aggiungi** e nella nuova riga nella colonna **Risultato della ricerca** selezionare la riga correlata che rappresenta la classificazione nella **Colonna 18**.</span><span class="sxs-lookup"><span data-stu-id="19490-148">On the **Conditions** FastTab, select **Add** and in the new line in the **Lookup result** column, select the related line that represents the classification in the **Column 18**.</span></span>
4. <span data-ttu-id="19490-149">Nella colonna **Gruppo di articoli ritenuta d'acconto** selezionare il codice correlato utilizzato per identificare la classificazione.</span><span class="sxs-lookup"><span data-stu-id="19490-149">In the **Withholding tax item group** column, select the related code that's used to identify the classification.</span></span> <span data-ttu-id="19490-150">Ad esempio, **Sconto consentito**.</span><span class="sxs-lookup"><span data-stu-id="19490-150">For example, **Allowed discount**.</span></span>  
5. <span data-ttu-id="19490-151">Ripetere i passaggi 3 e 4 per tutte le ricerche disponibili.</span><span class="sxs-lookup"><span data-stu-id="19490-151">Repeat steps 3 and 4 for all available lookups.</span></span>
6. <span data-ttu-id="19490-152">Selezionare di nuovo **Aggiungi** per includere la riga di registrazione finale e nella colonna **Risultato della ricerca**, selezionare **Non applicabile**.</span><span class="sxs-lookup"><span data-stu-id="19490-152">Select **Add** again to include the final record line, and in the **Lookup result** column, select **Not applicable**.</span></span> 
7. <span data-ttu-id="19490-153">Nelle colonne rimanenti, selezionare **Non vuoto**.</span><span class="sxs-lookup"><span data-stu-id="19490-153">In the remaining columns, select **Not blank**.</span></span> 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a><span data-ttu-id="19490-154">Impostazione dei parametri di Contabilità generale</span><span class="sxs-lookup"><span data-stu-id="19490-154">Set up General ledger parameters</span></span>

<span data-ttu-id="19490-155">Per generare i report sul modulo della dichiarazione della ritenuta d'acconto in Microsoft Excel, definire un formato ER nella pagina **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="19490-155">To generate the WHT declaration form reports in Microsoft Excel, define an ER format on the **General ledger parameters** page.</span></span>

1. <span data-ttu-id="19490-156">Selezionare **Imposta** > **Impostazione** > **Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="19490-156">Go to **Tax** > **Setup** > **General ledger parameters**.</span></span>
2. <span data-ttu-id="19490-157">Nella scheda **Ritenuta d'acconto**, nel campo **Mapping formato declarazione ritenuta d'acconto**, selezionare **Excel di dichiarazione RIT (EG)**.</span><span class="sxs-lookup"><span data-stu-id="19490-157">On the **Withholding tax** tab, in the **WHT declaration format mapping** field, select **WHT Declaration Excel (EG)**.</span></span> <span data-ttu-id="19490-158">Se si lascia il campo vuoto, il report sull'IVA standard verrà generato in formato SSRS.</span><span class="sxs-lookup"><span data-stu-id="19490-158">If you leave the field blank, the standard sales tax report will be generated in SSRS format.</span></span>


![Modulo di dichiarazione](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a><span data-ttu-id="19490-160">Genera i moduli della dichiarazione della ritenuta d'acconto</span><span class="sxs-lookup"><span data-stu-id="19490-160">Generate the Withholding declaration forms</span></span>
<span data-ttu-id="19490-161">Il processo di preparazione e di invio di un modulo di dichiarazione della ritenuta d'acconto per un periodo specifico si basa sulle transazioni di ritenuta d'acconto registrate durante il processo di liquidazione e registrazione dell'imposta di pagamento.</span><span class="sxs-lookup"><span data-stu-id="19490-161">The process of preparing and submitting a Withholding declaration form for a specific period is based on the withholding tax transactions posted during the settle and post payment tax job.</span></span> <span data-ttu-id="19490-162">Per ulteriori informazioni sulla ritenuta d'acconto globale, vedere [Ritenuta d'acconto globale](../general-ledger/global-withholding-tax-overview.md).</span><span class="sxs-lookup"><span data-stu-id="19490-162">For more information about global withholding tax, see [Global withholding tax](../general-ledger/global-withholding-tax-overview.md).</span></span>

<span data-ttu-id="19490-163">Completare i seguenti passaggi per generare il report sulla dichiarazione IVA:</span><span class="sxs-lookup"><span data-stu-id="19490-163">Complete the following steps to generate the tax declaration report.</span></span>

1. <span data-ttu-id="19490-164">Selezionare **Imposta** > **Dichiarazioni** > **Ritenuta d'acconto** > \**Pagamento ritenuta d'acconto*.</span><span class="sxs-lookup"><span data-stu-id="19490-164">Go to **Tax** > **Declarations** > **Withholding tax** > \**Withholding tax payment*.</span></span>
2. <span data-ttu-id="19490-165">Selezionare il periodo di liquidazione, quindi selezionare la data di inizio per il report.</span><span class="sxs-lookup"><span data-stu-id="19490-165">Select the settlement period and then select the from date for the report.</span></span> 
3. <span data-ttu-id="19490-166">Immettere la data della transazione e quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="19490-166">Enter the transaction date and then select **OK**.</span></span>
4. <span data-ttu-id="19490-167">Nella finestra di dialogo visualizzata, selezionare uno o più dei tipi di modulo **Modulo n. 41**, **Modulo n. 11** o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="19490-167">In the dialog box that opens, select one or more of the form types \*\*Form No 41 \*\*, **Form No 11**, or **None**.</span></span> <span data-ttu-id="19490-168">Se si seleziona **Nessuno**, viene generato il report standard.</span><span class="sxs-lookup"><span data-stu-id="19490-168">If you select **None**, the standard report is generated.</span></span> 
5. <span data-ttu-id="19490-169">Selezionare la lingua.</span><span class="sxs-lookup"><span data-stu-id="19490-169">Select the language.</span></span> <span data-ttu-id="19490-170">Tutti i report vengono tradotti in **en-us** e **ar-eg**.</span><span class="sxs-lookup"><span data-stu-id="19490-170">All reports are translated in **en-us** and **ar-eg**.</span></span>
6. <span data-ttu-id="19490-171">Immettere la filiale e il nome della banca presso la quale verrà effettuato il pagamento dell'imposta.</span><span class="sxs-lookup"><span data-stu-id="19490-171">Enter the branch and name of the bank where the tax payment will be paid.</span></span>
7. <span data-ttu-id="19490-172">Selezionare il tipo di attività e immettere i numeri di assegno e documento.</span><span class="sxs-lookup"><span data-stu-id="19490-172">Select the business type and then enter the check and document numbers.</span></span> 
8. <span data-ttu-id="19490-173">Immettere il tipo di entità.</span><span class="sxs-lookup"><span data-stu-id="19490-173">Enter the entity type.</span></span> 
9. <span data-ttu-id="19490-174">Immettere il nome della persona registrata per assegnare il modulo e selezionare **OK** per confermare la generazione del report.</span><span class="sxs-lookup"><span data-stu-id="19490-174">Enter the name of person registered to assign the form and select **OK** to confirm the report generation.</span></span> 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
