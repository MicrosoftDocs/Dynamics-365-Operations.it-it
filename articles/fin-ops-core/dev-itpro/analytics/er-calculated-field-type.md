---
title: Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato
description: In questo argomento vengono fornite informazioni su come utilizzare il tipo Campo calcolato per le origini dati ER.
author: NickSelin
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3f331401f8d191243f72961333e4f1dbe84d0be5
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/06/2019
ms.locfileid: "2771331"
---
# <a name="support-parameterized-calls-of-er-data-sources-of-the-calculated-field-type"></a><span data-ttu-id="b111c-103">Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-103">Support parameterized calls of ER data sources of the Calculated field type</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b111c-104">In questo argomento viene descritto come progettare un'origine dati ER utilizzando il tipo **Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="b111c-104">This topic explains how you can design an Electronic reporting (ER) data source by using the **Calculated field** type.</span></span> <span data-ttu-id="b111c-105">Questa origine dati può contenere un'espressione ER che, quando eseguita, può essere controllata con i valori degli argomenti dei parametri configurati in un'associazione che chiama questa origine dati.</span><span class="sxs-lookup"><span data-stu-id="b111c-105">This data source may contain an ER expression that, when executed, can be controlled by the values of the parameter arguments that are configured in a binding that calls this data source.</span></span> <span data-ttu-id="b111c-106">Mediante la configurazione delle chiamate parametrizzate di un'origine dati simile, è possibile riutilizzare una singola origine dati in molte associazioni, riducendo quindi il numero totale di origini dati che devono essere configurate nei mapping di modello ER o nei formati ER.</span><span class="sxs-lookup"><span data-stu-id="b111c-106">By configuring parameterized calls of such a data source, you can reuse a single data source in many bindings, which reduces the total number of data sources that must be configured in ER model mappings or ER formats.</span></span> <span data-ttu-id="b111c-107">Semplifica inoltre il componente ER configurato, riducendo di conseguenza i costi di manutenzione e il costo di utilizzo da parte di altri clienti.</span><span class="sxs-lookup"><span data-stu-id="b111c-107">It also simplifies the configured ER component, which reduces the maintenance costs and the cost of use by other consumers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b111c-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b111c-108">Prerequisites</span></span>
<span data-ttu-id="b111c-109">Per completare gli esempi in questo argomento, è necessario disporre del seguente accesso:</span><span class="sxs-lookup"><span data-stu-id="b111c-109">To complete the examples in this topic, you must have the following access:</span></span>

- <span data-ttu-id="b111c-110">Accesso a uno di questi ruoli:</span><span class="sxs-lookup"><span data-stu-id="b111c-110">Access to one of these roles:</span></span>

    - <span data-ttu-id="b111c-111">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b111c-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="b111c-112">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b111c-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="b111c-113">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="b111c-113">System administrator</span></span>

- <span data-ttu-id="b111c-114">Accesso ai servizi RCS (Regulatory Configuration Service) di cui è stato eseguito il provisioning per lo stesso tenant di Finance and Operations per uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="b111c-114">Access to Regulatory Configuration Services (RCS) that have been provisioned for the same tenant as Finance and Operations for one of the following roles:</span></span>

    - <span data-ttu-id="b111c-115">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b111c-115">Electronic reporting developer</span></span>
    - <span data-ttu-id="b111c-116">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="b111c-116">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="b111c-117">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="b111c-117">System administrator</span></span>

<span data-ttu-id="b111c-118">Dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684), scaricare il file compresso **Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="b111c-118">From the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684), download the zipped (compressed) file **Support parameterized calls of ER data sources of Calculated field type**.</span></span> <span data-ttu-id="b111c-119">Questo file contiene le seguenti configurazioni ER che devono essere estratte e archiviate localmente.</span><span class="sxs-lookup"><span data-stu-id="b111c-119">It contains the following ER configurations that must be extracted and stored locally.</span></span>

| <span data-ttu-id="b111c-120">**Contenuto**</span><span class="sxs-lookup"><span data-stu-id="b111c-120">**Content**</span></span>                           | <span data-ttu-id="b111c-121">**Nome file**</span><span class="sxs-lookup"><span data-stu-id="b111c-121">**File name**</span></span>                                        |
|---------------------------------------|------------------------------------------------------|
| <span data-ttu-id="b111c-122">Configurazione del modello di dati ER di esempio</span><span class="sxs-lookup"><span data-stu-id="b111c-122">Sample ER data model configuration</span></span>    | <span data-ttu-id="b111c-123">Model to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="b111c-123">Model to learn parameterized calls.version.1.xml</span></span>     |
| <span data-ttu-id="b111c-124">Configurazione dei metadati ER di esempio</span><span class="sxs-lookup"><span data-stu-id="b111c-124">Sample ER metadata configuration</span></span>      | <span data-ttu-id="b111c-125">Metadata to learn parameterized calls.version.1.xml</span><span class="sxs-lookup"><span data-stu-id="b111c-125">Metadata to learn parameterized calls.version.1.xml</span></span>  |
| <span data-ttu-id="b111c-126">Configurazione del mapping di modello ER di esempio</span><span class="sxs-lookup"><span data-stu-id="b111c-126">Sample ER model mapping configuration</span></span> | <span data-ttu-id="b111c-127">Mapping to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="b111c-127">Mapping to learn parameterized calls.version.1.1.xml</span></span> |
| <span data-ttu-id="b111c-128">Configurazione di formato ER di esempio</span><span class="sxs-lookup"><span data-stu-id="b111c-128">Sample ER format configuration</span></span>        | <span data-ttu-id="b111c-129">Format to learn parameterized calls.version.1.1.xml</span><span class="sxs-lookup"><span data-stu-id="b111c-129">Format to learn parameterized calls.version.1.1.xml</span></span>  |

## <a name="sign-in-to-your-rcs-instance"></a><span data-ttu-id="b111c-130">Accedere all'istanza RCS</span><span class="sxs-lookup"><span data-stu-id="b111c-130">Sign in to your RCS instance</span></span>
<span data-ttu-id="b111c-131">In questo esempio si creerà una configurazione per la società di esempio Litware, Inc. Innanzitutto, in RCS, completare i passaggi nella procedura [Creare fornitori di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="b111c-131">In this example, you will create a configuration for the sample company, Litware, Inc. First, in RCS, you must complete the steps in the [Create configuration providers and mark them as active](tasks/er-configuration-provider-mark-it-active-2016-11.md) procedure:</span></span>

1. <span data-ttu-id="b111c-132">Nel dashboard predefinito, selezionare **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="b111c-132">On the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="b111c-133">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="b111c-133">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="b111c-134">Importare le configurazioni scaricate in RCS nel seguente ordine: modello di dati, metadati, mapping di modello, formato.</span><span class="sxs-lookup"><span data-stu-id="b111c-134">Import the downloaded configurations to RCS in the following sequence: data model, metadata, model mapping, format.</span></span> <span data-ttu-id="b111c-135">Completare i passaggi seguenti per ogni configurazione ER:</span><span class="sxs-lookup"><span data-stu-id="b111c-135">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="b111c-136">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="b111c-136">Select **Exchange.**</span></span>
    2. <span data-ttu-id="b111c-137">Selezionare **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="b111c-137">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="b111c-138">Selezionare **Sfoglia** quindi selezionare la configurazione ER necessaria in formato XML.</span><span class="sxs-lookup"><span data-stu-id="b111c-138">Select **Browse**, and then select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="b111c-139">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-139">Select **OK.**</span></span>

## <a name="review-the-provided-er-solution"></a><span data-ttu-id="b111c-140">Esaminare la soluzione ER fornita</span><span class="sxs-lookup"><span data-stu-id="b111c-140">Review the provided ER solution</span></span>

### <a name="review-model-mapping"></a><span data-ttu-id="b111c-141">Esaminare il modello di mapping</span><span class="sxs-lookup"><span data-stu-id="b111c-141">Review model mapping</span></span>

1. <span data-ttu-id="b111c-142">Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-142">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="b111c-143">Selezionare **Mapping per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-143">Select **Mapping to learn parameterized calls**.</span></span>
3. <span data-ttu-id="b111c-144">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-144">Select **Designer**.</span></span>
4. <span data-ttu-id="b111c-145">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-145">Select **Designer**.</span></span>  
   
    <span data-ttu-id="b111c-146">Questo mapping di modello ER esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b111c-146">This ER model mapping is designed to do the following:</span></span>

    - <span data-ttu-id="b111c-147">Recuperare l'elenco di codici imposta (origine dati **Imposta**) presenti nella tabella **TaxTable**.</span><span class="sxs-lookup"><span data-stu-id="b111c-147">Fetch the list of tax codes (**Tax** data source) residing in the **TaxTable** table.</span></span>
    - <span data-ttu-id="b111c-148">Recuperare l'elenco di transazioni fiscali (origine dati **Trans**) presenti nella tabella **TaxTrans**.</span><span class="sxs-lookup"><span data-stu-id="b111c-148">Fetch the list of tax transactions (**Trans** data source) residing in the **TaxTrans** table:</span></span>
    
        - <span data-ttu-id="b111c-149">Raggruppare l'elenco di transazioni recuperate (origine dati **Gr**) per codice imposta.</span><span class="sxs-lookup"><span data-stu-id="b111c-149">Group the list of fetched transactions (**Gr** data source) by tax code.</span></span>
        - <span data-ttu-id="b111c-150">Calcolare le transazioni raggruppate in base ai valori aggregati per codice imposta:</span><span class="sxs-lookup"><span data-stu-id="b111c-150">Calculate for grouped transactions following aggregated values per tax code:</span></span>

            - <span data-ttu-id="b111c-151">Somma dei valori di imposta di base.</span><span class="sxs-lookup"><span data-stu-id="b111c-151">Sum of tax base values.</span></span>
            - <span data-ttu-id="b111c-152">Somma dei valori di imposta.</span><span class="sxs-lookup"><span data-stu-id="b111c-152">Sum of tax values.</span></span>
            - <span data-ttu-id="b111c-153">Valore minimo dell'aliquota fiscale applicata.</span><span class="sxs-lookup"><span data-stu-id="b111c-153">Minimum value of applied tax rate.</span></span>

    <span data-ttu-id="b111c-154">Il mapping di modello in questa configurazione implementa il modello di dati di base per qualsiasi formato ER creato per questo modello ed eseguito in Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b111c-154">The model mapping in this configuration implements the base data model for any of the ER formats created for this model and executed in Finance and Operations.</span></span> <span data-ttu-id="b111c-155">Di conseguenza, il contenuto delle origini dati **Imposta** e **Gr** viene esposto per i formati ER, ad esempio origini dati astratte.</span><span class="sxs-lookup"><span data-stu-id="b111c-155">As a result, the content of the **Tax** and **Gr** data sources is exposed for ER formats such as abstract data sources.</span></span>

    ![Pagina Progettazione mapping modello con le origini dati Imposta e Gr](media/er-calculated-field-type-01.png)

5.  <span data-ttu-id="b111c-157">Chiudere la pagina **Progettazione mapping modello**.</span><span class="sxs-lookup"><span data-stu-id="b111c-157">Close the **Model mapping designer** page.</span></span>
6.  <span data-ttu-id="b111c-158">Chiudere la pagina **Mapping modello**.</span><span class="sxs-lookup"><span data-stu-id="b111c-158">Close the **Model mapping** page.</span></span>

### <a name="review-format"></a><span data-ttu-id="b111c-159">Esaminare il formato</span><span class="sxs-lookup"><span data-stu-id="b111c-159">Review format</span></span>

1. <span data-ttu-id="b111c-160">Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-160">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="b111c-161">Selezionare **Formato per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-161">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="b111c-162">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-162">Select **Designer**.</span></span> <span data-ttu-id="b111c-163">Questo formato ER esegue le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b111c-163">This ER format is designed to do the following:</span></span>

    - <span data-ttu-id="b111c-164">Generare una dichiarazione fiscale in formato XML.</span><span class="sxs-lookup"><span data-stu-id="b111c-164">Generate a tax statement in XML format.</span></span>
    - <span data-ttu-id="b111c-165">Presentare i seguenti livelli di tassazione nella dichiarazione fiscale: Normale, Ridotto e Nessuno.</span><span class="sxs-lookup"><span data-stu-id="b111c-165">Present the following levels of taxation in the tax statement: regular, reduced, and none.</span></span>
    - <span data-ttu-id="b111c-166">Presentare molteplici dettagli a ogni livello di tassazione, avendo un numero differente di dettagli in ogni livello.</span><span class="sxs-lookup"><span data-stu-id="b111c-166">Present multiple details at each taxation level, having a different number of details in each level.</span></span>

    ![Pagina Progettazione formati](media/er-calculated-field-type-02.png)

4. <span data-ttu-id="b111c-168">Selezionare **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="b111c-168">Select **Mapping**.</span></span>
5. <span data-ttu-id="b111c-169">Espandere gli elementi **Modello**, **Dati** e **Riepilogo**.</span><span class="sxs-lookup"><span data-stu-id="b111c-169">Expand the **Model**, **Data,** and **Summary** items.</span></span> 

    <span data-ttu-id="b111c-170">Il campo calcolato **Model.Data.Summary.Level** contiene l'espressione che restituisce il codice del livello di tassazione (**Normale**, **Ridotto**, **Nessuno** o **Altro**) come valore di testo per qualsiasi codice imposta che è possibile recuperare dall'origine dati **Model.Data.Summary** in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="b111c-170">The calculated field **Model.Data.Summary.Level** contains the expression that returns the code of the taxation level (**Regular**, **Reduced**, **None,** or **Other**) as a text value for any tax code that can be retrieved from the **Model.Data.Summary** data source at run time.</span></span>

    ![Pagina Progettazione formati con dettagli del modello di dati Modello per ottenere chiamate parametrizzate](media/er-calculated-field-type-03.png)

6. <span data-ttu-id="b111c-172">Espandere l'elemento **Model**.**Data2**.</span><span class="sxs-lookup"><span data-stu-id="b111c-172">Expand the **Model**.**Data2** item.</span></span>
7. <span data-ttu-id="b111c-173">Espandere l'elemento **Model**.**Data2Data2.Summary2**.</span><span class="sxs-lookup"><span data-stu-id="b111c-173">Expand the **Model**.**Data2.Summary2** item.</span></span>
   
    <span data-ttu-id="b111c-174">L'origine dati **Model**.**Data2.Summary2** è configurata per raggruppare i dettagli delle transazioni dell'origine dati **Model.Data.Summary** per livello di tassazione (restituito dal campo calcolato **Model.Data.Summary.Level** ) e calcolare le aggregazioni.</span><span class="sxs-lookup"><span data-stu-id="b111c-174">The **Model**.**Data2.Summary2** data source is configured to group the **Model.Data.Summary** data source transaction details by taxation level (returned by the **Model.Data.Summary.Level** calculated field) and compute the aggregations.</span></span>

    ![Pagina Progettazione formati con i dettagli dell'origine dati Model.Data2.Summary2](media/er-calculated-field-type-04.png)

8. <span data-ttu-id="b111c-176">Esaminare i campi calcolati. **Model**.**Data2.Level1**, **Model**.**Data2.Level2** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="b111c-176">Review the calculated fields **Model**.**Data2.Level1**, **Model**.**Data2.Level2**, and **Model**.**Data2.Level3.**</span></span> <span data-ttu-id="b111c-177">Questi campi calcolati sono utilizzati per filtrare l'elenco di record **Model**.**Data2.Summary2** e restituire solo i record che rappresentano un particolare livello di tassazione.</span><span class="sxs-lookup"><span data-stu-id="b111c-177">These calculated fields are used to filter the **Model**.**Data2.Summary2** records list and return only records that represent a particular taxation level.</span></span>
9. <span data-ttu-id="b111c-178">Chiudere la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="b111c-178">Close the **Format designer** page.</span></span>

## <a name="create-a-derived-format"></a><span data-ttu-id="b111c-179">Creare un formato derivato</span><span class="sxs-lookup"><span data-stu-id="b111c-179">Create a derived format</span></span>
<span data-ttu-id="b111c-180">È possibile migliorare il formato fornito aggiungendo un campo calcolato per filtrare il livello di tassazione necessario anziché utilizzare i tre campi esistenti: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** e **Model**.**Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="b111c-180">You can improve the provided format by adding one calculated field to filter the required taxation level instead of using the existing three fields: **Model**.**Data2.Level1**, **Model**.**Data2.Level2,** and **Model**.**Data2.Level3**.</span></span> <span data-ttu-id="b111c-181">Il livello di tassazione necessario può essere specificato nella posizione in cui questo nuovo campo calcolato verrà chiamato.</span><span class="sxs-lookup"><span data-stu-id="b111c-181">The required taxation level can be specified in the location where this new calculated field will be called.</span></span>

1. <span data-ttu-id="b111c-182">Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-182">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="b111c-183">Selezionare **Formato per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-183">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="b111c-184">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-184">Select **Create configuration**.</span></span>
4. <span data-ttu-id="b111c-185">Selezionare **Deriva da nome: Formato per ottenere chiamate parametrizzate, Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="b111c-185">Select **Derive from Name: Format to learn parameterized calls, Microsoft**.</span></span>
5. <span data-ttu-id="b111c-186">Nel campo **Nome**, immettere **Formato per ottenere chiamate parametrizzate (personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="b111c-186">In the **Name** field, enter **Format to learn parameterized calls (custom)**.</span></span>
6. <span data-ttu-id="b111c-187">Selezionare **Crea configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-187">Select **Create configuration.**</span></span>

## <a name="configure-a-parameterized-calculated-field-that-returns-a-list-of-records"></a><span data-ttu-id="b111c-188">Configurare un campo calcolato parametrizzato che restituisce un elenco di record</span><span class="sxs-lookup"><span data-stu-id="b111c-188">Configure a parameterized calculated field that returns a list of records</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="b111c-189">Aggiungere un nuovo campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-189">Start adding a new calculated field</span></span>

1. <span data-ttu-id="b111c-190">Selezionare **Progettazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-190">Select **Designer**.</span></span>
2. <span data-ttu-id="b111c-191">Selezionare **Espandi/Comprimi** per espandere tutti gli elementi di formato.</span><span class="sxs-lookup"><span data-stu-id="b111c-191">Select **Expand/collapse** to expand all format items.</span></span>
3. <span data-ttu-id="b111c-192">Selezionare **Mapping**.</span><span class="sxs-lookup"><span data-stu-id="b111c-192">Select **Mapping**.</span></span>
4. <span data-ttu-id="b111c-193">Espandere l'elemento **Model**.</span><span class="sxs-lookup"><span data-stu-id="b111c-193">Expand the **Model** item.</span></span>
5. <span data-ttu-id="b111c-194">Selezionare l'elemento **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="b111c-194">Select the **Model.Data2** item.</span></span>
6. <span data-ttu-id="b111c-195">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b111c-195">Select **Add**.</span></span>
7. <span data-ttu-id="b111c-196">Selezionare **Funzioni\\Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="b111c-196">Select **Functions\\Calculated field**.</span></span>
8. <span data-ttu-id="b111c-197">Nel campo **Nome** immettere **Livelli**.</span><span class="sxs-lookup"><span data-stu-id="b111c-197">In the **Name** field, enter **Levels**.</span></span>
9. <span data-ttu-id="b111c-198">Selezionare **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="b111c-198">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="b111c-199">Definire un parametro per aggiungere un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-199">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="b111c-200">Selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="b111c-200">Select **Parameters**.</span></span>
2. <span data-ttu-id="b111c-201">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b111c-201">Select **New**.</span></span>
3. <span data-ttu-id="b111c-202">Nel campo **Nome**, immettere **Livello di tassazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-202">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="b111c-203">Nel campo **Tipo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-203">In the **Type** field, select **String**.</span></span>

    <span data-ttu-id="b111c-204">Solo i tipi di dati primitivi possono essere utilizzati per specificare il tipo di argomento del parametro.</span><span class="sxs-lookup"><span data-stu-id="b111c-204">Only primitive data types can be used to specify the type of the parameter’s argument.</span></span> <span data-ttu-id="b111c-205">Di conseguenza, i tipi **Elenco di record**, **Record** e **Enum** non sono utilizzabili per tale scopo.</span><span class="sxs-lookup"><span data-stu-id="b111c-205">Therefore, **Record list**, **Record**, and **Enum** types cannot be used for this purpose.</span></span>

    <span data-ttu-id="b111c-206">Il numero massimo di parametri che è possibile specificare per un singolo campo calcolato è 8.</span><span class="sxs-lookup"><span data-stu-id="b111c-206">The maximum number of parameters that can be specified for a single calculated field is 8.</span></span>

    ![Elenco delle origini dati dei parametri](media/er-calculated-field-type-05.png)

5. <span data-ttu-id="b111c-208">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-208">Select **OK**.</span></span>

<span data-ttu-id="b111c-209">Aggiungendo questo parametro, si specifica la condizione necessaria per chiamare questo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="b111c-209">By adding this parameter, you specify the condition that must be in place to call this calculated field.</span></span> <span data-ttu-id="b111c-210">Quando si chiama questo campo calcolato, è necessario specificare l'argomento del parametro **Livello di tassazione** come valore con formato **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-210">When you call this calculated field, you need to specify the argument of the **Taxation Level** parameter as a value with **String** format.</span></span>

   <span data-ttu-id="b111c-211">Assicurarsi di definire i parametri solo per quei campi calcolati che si trovano in un contenitore ( **Elenco record**, **Record** o **Contenitore**).</span><span class="sxs-lookup"><span data-stu-id="b111c-211">Make sure that you define parameters only for those calculated fields that reside in a container (either **Record list**, **Record**, or **Container**).</span></span>

   <span data-ttu-id="b111c-212">Il parametro configurato è disponibile nell'elenco delle origini dati per questo campo calcolato.</span><span class="sxs-lookup"><span data-stu-id="b111c-212">The configured parameter is available in the list of data sources for this calculated field.</span></span> <span data-ttu-id="b111c-213">È possibile aggiungere il parametro all'espressione configurata selezionando **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b111c-213">You can add the parameter to the configured expression by selecting **Add data source**.</span></span>

   ![Campi dell'origine dati](media/er-calculated-field-type-06.png)

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="b111c-215">Definire un'espressione per aggiungere un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-215">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="b111c-216">Nel campo **Formula'**, immettere:</span><span class="sxs-lookup"><span data-stu-id="b111c-216">In the **Formula** field, enter:</span></span> 

    <span data-ttu-id="b111c-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span><span class="sxs-lookup"><span data-stu-id="b111c-217">**WHERE(\@.Summary2, \@.Summary2.grouped.Level =**</span></span>
    
2. <span data-ttu-id="b111c-218">Selezionare il parametro **Livello di tassazione** nell'elenco delle origini dati.</span><span class="sxs-lookup"><span data-stu-id="b111c-218">Select the **Taxation Level** parameter in the list of data sources.</span></span>
3. <span data-ttu-id="b111c-219">Selezionare **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b111c-219">Select **Add data source**.</span></span>
4. <span data-ttu-id="b111c-220">Nel campo **Formula**, finalizzare l'espressione come segue:</span><span class="sxs-lookup"><span data-stu-id="b111c-220">In the **Formula** field, finalize the expression as:</span></span>  

    <span data-ttu-id="b111c-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Livello di tassazione')**</span><span class="sxs-lookup"><span data-stu-id="b111c-221">**WHERE(\@.Summary2, \@.Summary2.grouped.Level = 'Taxation Level')**</span></span>

5. <span data-ttu-id="b111c-222">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b111c-222">Select **Save**.</span></span>

    ![Informazioni sui campi dell'origine dati](media/er-calculated-field-type-07.png)

6. <span data-ttu-id="b111c-224">Chiudere la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="b111c-224">Close the **Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="b111c-225">Completare l'aggiunta di un nuovo campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-225">Finish adding a new calculated field</span></span>

- <span data-ttu-id="b111c-226">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-226">Select **OK**.</span></span>

<span data-ttu-id="b111c-227">Nella pagina **Progettazione formati**, il campo calcolato parametrizzato configurato **Livelli** richiede un argomento **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-227">On the **Format designer** page, the configured parameterized calculated field **Levels** requires a **String** argument.</span></span>

![Elenco espanso dei livelli del campo calcolato](media/er-calculated-field-type-08.png)

### <a name="use-the-configured-calculated-field-for-binding-format-elements"></a><span data-ttu-id="b111c-229">Utilizzare il campo calcolato configurato per associare elementi di formato</span><span class="sxs-lookup"><span data-stu-id="b111c-229">Use the configured calculated field for binding format elements</span></span>

1. <span data-ttu-id="b111c-230">Selezionare **Model.Data2.Levels** per selezionare il campo calcolato configurato.</span><span class="sxs-lookup"><span data-stu-id="b111c-230">Select **Model.Data2.Levels** to select the configured calculated field.</span></span>
2. <span data-ttu-id="b111c-231">Selezionare l'elemento di formato **Statement.Taxation.Regular**.</span><span class="sxs-lookup"><span data-stu-id="b111c-231">Select the **Statement.Taxation.Regular** format element.</span></span>
3. <span data-ttu-id="b111c-232">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-232">Select **Bind**.</span></span>
4. <span data-ttu-id="b111c-233">Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level1**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati dell'elemento di formato selezionato.</span><span class="sxs-lookup"><span data-stu-id="b111c-233">Select **Yes** to confirm the replacement of the currently used data source, **Level1**, by the new data source, **Levels**, in all nested format elements of the selected format element.</span></span>

    <span data-ttu-id="b111c-234">L'associazione applicata è stata generata come chiamata del campo calcolato parametrizzato.</span><span class="sxs-lookup"><span data-stu-id="b111c-234">Applied binding has been built as a call of the parameterized calculated field.</span></span> <span data-ttu-id="b111c-235">Per impostazione predefinita, il nome dell'elemento di formato associato viene utilizzato come argomento per il campo calcolato parametrizzato nelle seguenti condizioni:</span><span class="sxs-lookup"><span data-stu-id="b111c-235">By default, the name of the bound format element is used as an argument for parameterized calculated field under the following conditions:</span></span>

      - <span data-ttu-id="b111c-236">Il campo calcolato è configurato per utilizzare un singolo parametro.</span><span class="sxs-lookup"><span data-stu-id="b111c-236">The calculated field is configured to use a single parameter.</span></span>
      - <span data-ttu-id="b111c-237">Il tipo di dati di questo parametro è definito come **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-237">The data type of this parameter is defined as **String**.</span></span>

    <span data-ttu-id="b111c-238">Quando il nome dell'elemento di formato associato è vuoto, il nome dell'origine dati di questo elemento viene utilizzato nell'associazione applicata.</span><span class="sxs-lookup"><span data-stu-id="b111c-238">When the name of the bound format element is blank, the data source name of this element is used in applied binding.</span></span>

5. <span data-ttu-id="b111c-239">Selezionare l'elemento di formato **Statement.Taxation.Reduced**.</span><span class="sxs-lookup"><span data-stu-id="b111c-239">Select the **Statement.Taxation.Reduced** format element.</span></span>
6. <span data-ttu-id="b111c-240">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-240">Select **Bind**.</span></span>
7. <span data-ttu-id="b111c-241">Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level2**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati sotto l'elemento di formato selezionato.</span><span class="sxs-lookup"><span data-stu-id="b111c-241">Select **Yes** to confirm the replacement of the currently used data source, **Level2**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>
8. <span data-ttu-id="b111c-242">Selezionare l'elemento di formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="b111c-242">Select the **Statement.Taxation.None** format element.</span></span>
9. <span data-ttu-id="b111c-243">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-243">Select **Bind**.</span></span>
10. <span data-ttu-id="b111c-244">Selezionare **Sì** per confermare la sostituzione dell'origine dati attualmente utilizzata, **Level3**, con la nuova origine dati, **Livelli**, in tutti gli elementi di formato nidificati sotto l'elemento di formato selezionato.</span><span class="sxs-lookup"><span data-stu-id="b111c-244">Select **Yes** to confirm the replacement of the currently used data source, **Level3**, by the new data source, **Levels**, in all nested format elements under the selected format element.</span></span>

   <span data-ttu-id="b111c-245">Quando si specifica l'argomento del campo calcolato parametrizzato per l'elemento XML che rappresenta il livello di tassazione (ad esempio **Model.Data2.Levels("Ridotto")** come valore di testo), non è necessario effettuare la stessa operazione per gli attributi XML nidificati: le relative associazioni erediteranno automaticamente il valore dell'argomento definito nel livello principale (**Model.Data2.Levels.aggregated.Base**, non **Model.Data2.Levels("Reduced").aggregated.Base**).</span><span class="sxs-lookup"><span data-stu-id="b111c-245">When you specify the argument of the parameterized calculated field for the XML element representing taxation level (for example, **Model.Data2.Levels("Reduced")** as a text value), you don’t need to do the same for nested XML attributes—their bindings will automatically inherit the value of the argument defined on the parent level (**Model.Data2.Levels.aggregated.Base**, not **Model.Data2.Levels("Reduced").aggregated.Base**).</span></span>

<span data-ttu-id="b111c-246">Le chiamate ricorrenti di qualsiasi campo calcolato parametrizzato non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b111c-246">Recurrent calls of any parameterized calculated field are not supported.</span></span>

<span data-ttu-id="b111c-247">È possibile selezionare **Modifica formula** e modificare l'argomento applicato per impostazione predefinita del campo calcolato parametrizzato nell'associazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="b111c-247">You can select **Edit formula**, and change the applied-by-default argument of the parameterized calculated field in the selected binding.</span></span> <span data-ttu-id="b111c-248">Se questo argomento non è presente, può causare errori in fase di esecuzione: gli utenti vengono informati di tale situazione quando il formato corrente viene convalidato.</span><span class="sxs-lookup"><span data-stu-id="b111c-248">If this argument is missing, it can cause errors at run time — users are informed about such a situation when the current format is validated.</span></span>

![Notifica dell'avviso di convalida](media/er-calculated-field-type-10.png)

## <a name="configure-a-parameterized-calculated-field-to-return-a-record"></a><span data-ttu-id="b111c-250">Configurare un campo calcolato parametrizzato per restituire un record</span><span class="sxs-lookup"><span data-stu-id="b111c-250">Configure a parameterized calculated field to return a record</span></span>
<span data-ttu-id="b111c-251">Quando un campo calcolato parametrizzato restituisce un record, è necessario supportare l'associazione di singoli campi di tale record con elementi di formato.</span><span class="sxs-lookup"><span data-stu-id="b111c-251">When a parameterized calculated field returns a record, you need to support binding of individual fields of this record to format elements.</span></span> <span data-ttu-id="b111c-252">In tali casi un'associazione padre contenente il valore di un argomento per chiamare un campo calcolato parametrizzato non sarà disponibile; questo valore deve essere definito nell'associazione del campo di un singolo record.</span><span class="sxs-lookup"><span data-stu-id="b111c-252">In such cases there will be no parent binding that contains the value of an argument to call a parameterized calculated field — this value must be defined in the binding of a single record’s field.</span></span>

### <a name="start-adding-a-new-calculated-field"></a><span data-ttu-id="b111c-253">Aggiungere un nuovo campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-253">Start adding a new calculated field</span></span>

1. <span data-ttu-id="b111c-254">Selezionare l'elemento **Model.Data2**.</span><span class="sxs-lookup"><span data-stu-id="b111c-254">Select the **Model.Data2** item.</span></span>
2. <span data-ttu-id="b111c-255">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="b111c-255">Select **Add**.</span></span>
3. <span data-ttu-id="b111c-256">Selezionare **Funzioni\\Campo calcolato**.</span><span class="sxs-lookup"><span data-stu-id="b111c-256">Select **Functions\\Calculated field**.</span></span>
4. <span data-ttu-id="b111c-257">Nel campo **Nome** immettere **LevelRecord**.</span><span class="sxs-lookup"><span data-stu-id="b111c-257">In the **Name** field, enter **LevelRecord**.</span></span>
5. <span data-ttu-id="b111c-258">Selezionare **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="b111c-258">Select **Edit formula**.</span></span>

### <a name="define-a-parameter-for-adding-a-calculated-field"></a><span data-ttu-id="b111c-259">Definire un parametro per aggiungere un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-259">Define a parameter for adding a calculated field</span></span>

1. <span data-ttu-id="b111c-260">Selezionare **Parametri**.</span><span class="sxs-lookup"><span data-stu-id="b111c-260">Select **Parameters**.</span></span>
2. <span data-ttu-id="b111c-261">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b111c-261">Select **New**.</span></span>
3. <span data-ttu-id="b111c-262">Nel campo **Nome**, immettere **Livello di tassazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-262">In the **Name** field, enter **Taxation Level**.</span></span>
4. <span data-ttu-id="b111c-263">Nel campo **Tipo** selezionare **Stringa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-263">In the **Type** field, select **String**.</span></span>
5. <span data-ttu-id="b111c-264">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-264">Select **OK**.</span></span>

### <a name="define-an-expression-for-adding-a-calculated-field"></a><span data-ttu-id="b111c-265">Definire un'espressione per aggiungere un campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-265">Define an expression for adding a calculated field</span></span>

1. <span data-ttu-id="b111c-266">Nel campo **Formula**, immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="b111c-266">In the **Formula** field, enter the following:</span></span>  
    
    <span data-ttu-id="b111c-267">**FIRSTORNULL(\@.Levels(**</span><span class="sxs-lookup"><span data-stu-id="b111c-267">**FIRSTORNULL(\@.Levels(**</span></span>

2. <span data-ttu-id="b111c-268">Selezionare il parametro **Livello di tassazione**.</span><span class="sxs-lookup"><span data-stu-id="b111c-268">Select the **Taxation Level** parameter.</span></span>
3. <span data-ttu-id="b111c-269">Selezionare **Aggiungi origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b111c-269">Select **Add data source**.</span></span>
4. <span data-ttu-id="b111c-270">Nel campo **Formula**, aggiungere **'Livello di tassazione'))** a quanto immesso nel passaggio 1 per ottenere l'espressione finale:</span><span class="sxs-lookup"><span data-stu-id="b111c-270">In the **Formula** field, append **'Taxation Level'))** to what you entered in Step 1 to finalize the expression to:</span></span>  
    
    <span data-ttu-id="b111c-271">**FIRSTORNULL(\@.Levels('Livello di tassazione'))**</span><span class="sxs-lookup"><span data-stu-id="b111c-271">**FIRSTORNULL(\@.Levels('Taxation Level'))**</span></span>

5. <span data-ttu-id="b111c-272">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b111c-272">Select **Save**.</span></span>
6. <span data-ttu-id="b111c-273">Chiudere la pagina **Designer formula**.</span><span class="sxs-lookup"><span data-stu-id="b111c-273">Close **the Formula designer** page.</span></span>

### <a name="finish-adding-a-new-calculated-field"></a><span data-ttu-id="b111c-274">Completare l'aggiunta di un nuovo campo calcolato</span><span class="sxs-lookup"><span data-stu-id="b111c-274">Finish adding a new calculated field</span></span>

-   <span data-ttu-id="b111c-275">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-275">Select **OK**.</span></span>

### <a name="use-the-configured-calculated-field-to-bind-format-elements"></a><span data-ttu-id="b111c-276">Utilizzare il campo calcolato configurato per associare elementi di formato</span><span class="sxs-lookup"><span data-stu-id="b111c-276">Use the configured calculated field to bind format elements</span></span>

1. <span data-ttu-id="b111c-277">Espandere **Model.Data2.LevelRecord** per selezionare il campo calcolato configurato.</span><span class="sxs-lookup"><span data-stu-id="b111c-277">Expand **Model.Data2.LevelRecord** to select the configured calculated field.</span></span>
2. <span data-ttu-id="b111c-278">Espandere il contenitore **Model.Data2.LevelRecord.aggregated** del campo calcolato configurato.</span><span class="sxs-lookup"><span data-stu-id="b111c-278">Expand the **Model.Data2.LevelRecord.aggregated** container of the configured calculated field.</span></span>
3. <span data-ttu-id="b111c-279">Selezionare il campo **Model.Data2.LevelRecord.aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="b111c-279">Select the **Model.Data2.LevelRecord.aggregated.Base** field.</span></span>
4. <span data-ttu-id="b111c-280">Selezionare l'elemento di formato **Statement.Taxation.None**.</span><span class="sxs-lookup"><span data-stu-id="b111c-280">Select the **Statement.Taxation.None** format element.</span></span>
5. <span data-ttu-id="b111c-281">Selezionare **Separa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-281">Select **Unbind**.</span></span>
6. <span data-ttu-id="b111c-282">Selezionare l'elemento di formato **Statement.Taxation.None.Base**.</span><span class="sxs-lookup"><span data-stu-id="b111c-282">Select the **Statement.Taxation.None.Base** format element.</span></span>
7. <span data-ttu-id="b111c-283">Selezionare **Associa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-283">Select **Bind**.</span></span>
8. <span data-ttu-id="b111c-284">Selezionare **Modifica formula**.</span><span class="sxs-lookup"><span data-stu-id="b111c-284">Select **Edit formula**.</span></span>
9. <span data-ttu-id="b111c-285">Modificare l'espressione in **Model.Data2.LevelRecord("Nessuno").aggregated.Base**.</span><span class="sxs-lookup"><span data-stu-id="b111c-285">Change the expression to **Model.Data2.LevelRecord("None").aggregated.Base**.</span></span>

![Espressione aggiornata](media/er-calculated-field-type-11.png)

## <a name="remove-calculated-fields-that-are-not-used"></a><span data-ttu-id="b111c-287">Rimuovere i campi calcolati non utilizzati</span><span class="sxs-lookup"><span data-stu-id="b111c-287">Remove calculated fields that are not used</span></span>

1. <span data-ttu-id="b111c-288">Selezionare **Model.Data2.Level1**.</span><span class="sxs-lookup"><span data-stu-id="b111c-288">Select **Model.Data2.Level1**.</span></span>
2. <span data-ttu-id="b111c-289">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b111c-289">Select **Delete**.</span></span>
3. <span data-ttu-id="b111c-290">Selezionare **Model.Data2.Level2**.</span><span class="sxs-lookup"><span data-stu-id="b111c-290">Select **Model.Data2.Level2**.</span></span>
4. <span data-ttu-id="b111c-291">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b111c-291">Select **Delete**.</span></span>
5. <span data-ttu-id="b111c-292">Selezionare **Model.Data2.Level3**.</span><span class="sxs-lookup"><span data-stu-id="b111c-292">Select **Model.Data2.Level3**.</span></span>
6. <span data-ttu-id="b111c-293">Selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b111c-293">Select **Delete**.</span></span>
7. <span data-ttu-id="b111c-294">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b111c-294">Select **Save**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b111c-295">Lo stesso campo calcolato **Model.Data2.Levels** è stato utilizzato più volte in associazioni di formato.</span><span class="sxs-lookup"><span data-stu-id="b111c-295">You reused the same calculated field **Model.Data2.Levels** several times in format bindings.</span></span> <span data-ttu-id="b111c-296">È molto più semplice utilizzare e gestire un singolo campo calcolato anziché ripetere tale procedura per più campi simili.</span><span class="sxs-lookup"><span data-stu-id="b111c-296">It is much easier to use and maintain a single calculated field instead of doing this for multiple similar fields.</span></span>

8. <span data-ttu-id="b111c-297">Chiudere la pagina **Progettazione formati**.</span><span class="sxs-lookup"><span data-stu-id="b111c-297">Close the **Format designer** page.</span></span>

## <a name="complete-adjusted-version-of-a-derived-format"></a><span data-ttu-id="b111c-298">Completare la versione rettificata di un formato derivato</span><span class="sxs-lookup"><span data-stu-id="b111c-298">Complete adjusted version of a derived format</span></span>

1. <span data-ttu-id="b111c-299">Nella Scheda dettaglio **Versioni**, selezionare **Cambia stato**.</span><span class="sxs-lookup"><span data-stu-id="b111c-299">In the **Versions** FastTab, select **Change status**.</span></span>
2. <span data-ttu-id="b111c-300">Selezionare **Completa**.</span><span class="sxs-lookup"><span data-stu-id="b111c-300">Select **Complete**.</span></span>

## <a name="export-completed-version-of-a-derived-format"></a><span data-ttu-id="b111c-301">Esportare la versione completata di un formato derivato</span><span class="sxs-lookup"><span data-stu-id="b111c-301">Export completed version of a derived format</span></span>

1. <span data-ttu-id="b111c-302">Selezionare il formato **Formato per ottenere chiamate parametrizzate (personalizzato)** nella struttura delle configurazioni.</span><span class="sxs-lookup"><span data-stu-id="b111c-302">Select **Format to learn parameterized calls (custom)** format in the configurations tree.</span></span>
2. <span data-ttu-id="b111c-303">Nella Scheda dettaglio **Versioni**, selezionare la versione 1.1.1 completata.</span><span class="sxs-lookup"><span data-stu-id="b111c-303">In the **Versions** FastTab, select the completed version 1.1.1.</span></span>
3. <span data-ttu-id="b111c-304">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="b111c-304">Select **Exchange**.</span></span>
4. <span data-ttu-id="b111c-305">Selezionare **Esporta come file XML**.</span><span class="sxs-lookup"><span data-stu-id="b111c-305">Select **Export as XML file**.</span></span>
5. <span data-ttu-id="b111c-306">Archiviare la configurazione scaricata localmente in formato XML.</span><span class="sxs-lookup"><span data-stu-id="b111c-306">Store the downloaded configuration locally, in XML format.</span></span>

## <a name="test-er-formats"></a><span data-ttu-id="b111c-307">Verificare i formati ER</span><span class="sxs-lookup"><span data-stu-id="b111c-307">Test ER formats</span></span> 
<span data-ttu-id="b111c-308">È possibile eseguire formati ER iniziali e migliorati per assicurarsi che i campi calcolati parametrizzati configurati funzionino correttamente.</span><span class="sxs-lookup"><span data-stu-id="b111c-308">You can run the initial and improved ER formats to make sure that configured parameterized calculated fields work properly.</span></span>

### <a name="import-er-configurations"></a><span data-ttu-id="b111c-309">Importare configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="b111c-309">Import ER configurations</span></span>
<span data-ttu-id="b111c-310">È possibile importare le configurazioni esaminate da RCS utilizzando il repository ER del tipo **RCS**.</span><span class="sxs-lookup"><span data-stu-id="b111c-310">You can import reviewed configurations from RCS by using the ER repository of the **RCS** type.</span></span> <span data-ttu-id="b111c-311">Se si è già letta la procedura nell'argomento [Importare configurazioni di creazione di report elettronici da Regulatory Configuration Services](rcs-download-configurations.md), utilizzare il repository ER configurato per importare le configurazioni descritte in precedenza in questo argomento nel proprio ambiente.</span><span class="sxs-lookup"><span data-stu-id="b111c-311">If you already went through the steps in the topic, [Import Electronic reporting (ER) configurations from Regulatory Configuration Services (RCS)](rcs-download-configurations.md), use the configured ER repository to import configurations discussed earlier in this topic to your environment.</span></span> <span data-ttu-id="b111c-312">In caso contrario, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b111c-312">Otherwise, follow these steps:</span></span>

1. <span data-ttu-id="b111c-313">Selezionare la società **DEMF** e nel dashboard predefinito selezionare **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="b111c-313">Select the **DEMF** company and on the default dashboard, select **Electronic reporting**.</span></span>
2. <span data-ttu-id="b111c-314">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="b111c-314">Select **Reporting configurations**.</span></span>
3. <span data-ttu-id="b111c-315">Importare le configurazioni dall'Area download Microsoft nel seguente ordine: modello di dati, mapping di modello, formato.</span><span class="sxs-lookup"><span data-stu-id="b111c-315">Import the configurations from Microsoft Download Center in the following sequence: data model, model mapping, format.</span></span> <span data-ttu-id="b111c-316">Completare i passaggi seguenti per ogni configurazione ER:</span><span class="sxs-lookup"><span data-stu-id="b111c-316">Complete the following steps for each ER configuration:</span></span>

    1. <span data-ttu-id="b111c-317">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="b111c-317">Select **Exchange.**</span></span>
    2. <span data-ttu-id="b111c-318">Selezionare **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="b111c-318">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="b111c-319">Selezionare **Sfoglia** per selezionare la configurazione ER necessaria in formato XML.</span><span class="sxs-lookup"><span data-stu-id="b111c-319">Select **Browse** to select the required ER configuration in XML format.</span></span>
    4. <span data-ttu-id="b111c-320">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-320">Select **OK**.</span></span>

4. <span data-ttu-id="b111c-321">Importare la versione 1.1.1 completata del formato **Formato per ottenere chiamate parametrizzate (personalizzato)** che è stata esportata da RCS:</span><span class="sxs-lookup"><span data-stu-id="b111c-321">Import the exported from RCS completed version 1.1.1 of the **Format to learn parameterized calls (custom)** format:</span></span>

    1. <span data-ttu-id="b111c-322">Selezionare **Scambia**.</span><span class="sxs-lookup"><span data-stu-id="b111c-322">Select **Exchange.**</span></span>
    2. <span data-ttu-id="b111c-323">Selezionare **Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="b111c-323">Select **Load from XML file**.</span></span>
    3. <span data-ttu-id="b111c-324">Selezionare **Sfoglia** per selezionare il file **Formato per ottenere chiamate parametrizzate (personalizzato)** in formato XML archiviato localmente.</span><span class="sxs-lookup"><span data-stu-id="b111c-324">Select **Browse** to select the locally stored **Format to learn parameterized calls (custom)** file in XML format.</span></span>
    4. <span data-ttu-id="b111c-325">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b111c-325">Select **OK**.</span></span>

### <a name="run-er-formats"></a><span data-ttu-id="b111c-326">Eseguire formati ER</span><span class="sxs-lookup"><span data-stu-id="b111c-326">Run ER formats</span></span>

1. <span data-ttu-id="b111c-327">Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-327">In the configuration tree, expand the content of the **Model to learn parameterized calls** item.</span></span>
2. <span data-ttu-id="b111c-328">Selezionare **Formato per ottenere chiamate parametrizzate**.</span><span class="sxs-lookup"><span data-stu-id="b111c-328">Select **Format to learn parameterized calls**.</span></span>
3. <span data-ttu-id="b111c-329">Selezionare **Esegui** nella barra multifunzione superiore.</span><span class="sxs-lookup"><span data-stu-id="b111c-329">Select **Run** on the top-most ribbon.</span></span>
4. <span data-ttu-id="b111c-330">Salvare l'output generato localmente.</span><span class="sxs-lookup"><span data-stu-id="b111c-330">Save the locally generated output.</span></span>
5. <span data-ttu-id="b111c-331">Selezionare l'elemento **Formato per ottenere chiamate parametrizzate (personalizzato)**.</span><span class="sxs-lookup"><span data-stu-id="b111c-331">Select the **Format to learn parameterized calls (custom)** item.</span></span>
6. <span data-ttu-id="b111c-332">Selezionare **Esegui** nella barra multifunzione superiore.</span><span class="sxs-lookup"><span data-stu-id="b111c-332">Select **Run** on the top-most ribbon.</span></span>
7. <span data-ttu-id="b111c-333">Salvare l'output generato localmente.</span><span class="sxs-lookup"><span data-stu-id="b111c-333">Save the generated output locally.</span></span> 
8. <span data-ttu-id="b111c-334">Confrontare il contenuto degli output generati.</span><span class="sxs-lookup"><span data-stu-id="b111c-334">Compare the contents of the generated outputs.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b111c-335">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b111c-335">Additional resources</span></span>
[<span data-ttu-id="b111c-336">Designer formula nella creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="b111c-336">Formula designer in Electronic reporting (ER)</span></span>](general-electronic-reporting-formula-designer.md)
