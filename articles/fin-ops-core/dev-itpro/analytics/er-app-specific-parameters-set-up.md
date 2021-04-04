---
title: Impostare i parametri di un formato ER per la persona giuridica
description: In questo argomento viene descritto come impostare i parametri di un formato per la creazione di report elettronici (ER) per la persona giuridica.
author: NickSelin
manager: AnnBe
ms.date: 10/29/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: eebca6575a0b23f75baabbb91727f498de44d9cb
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5570712"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a><span data-ttu-id="7b5f9-103">Impostare i parametri di un formato ER per la persona giuridica</span><span class="sxs-lookup"><span data-stu-id="7b5f9-103">Set up the parameters of an ER format per legal entity</span></span>

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a><span data-ttu-id="7b5f9-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7b5f9-104">Prerequisites</span></span>

<span data-ttu-id="7b5f9-105">Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi descritti nell'argomento [Configurare i formati ER per utilizzare i parametri specificati per la persona giuridica](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="7b5f9-105">To complete these steps, you must first complete the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span>

<span data-ttu-id="7b5f9-106">Per completare gli esempi in questo argomento, è necessario disporre dell'accesso a Microsoft Dynamics 365 Finance (Finance) per uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-106">To complete the examples in this topic, you must have access to Microsoft Dynamics 365 Finance (Finance) for one of the following roles:</span></span>

- <span data-ttu-id="7b5f9-107">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7b5f9-107">Electronic reporting developer</span></span>
- <span data-ttu-id="7b5f9-108">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7b5f9-108">Electronic reporting functional consultant</span></span>
- <span data-ttu-id="7b5f9-109">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="7b5f9-109">System administrator</span></span>

## <a name="import-er-configurations"></a><span data-ttu-id="7b5f9-110">Importare configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="7b5f9-110">Import ER configurations</span></span>

1.  <span data-ttu-id="7b5f9-111">Accedere all'ambiente.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-111">Sign in to your environment.</span></span>
2.  <span data-ttu-id="7b5f9-112">Nel dashboard predefinito, selezionare **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-112">On the default dashboard, select **Electronic reporting**.</span></span>
3.  <span data-ttu-id="7b5f9-113">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-113">Select **Reporting configurations**.</span></span>
4.  <span data-ttu-id="7b5f9-114">Importare, nell'istanza di Finance corrente, le configurazioni esportate da Regulatory Configuration Services (RCS) per completare i passaggi indicati nell'argomento [Configurare i formati ER per utilizzare i parametri specificati per la persona giuridica](er-app-specific-parameters-configure-format.md).</span><span class="sxs-lookup"><span data-stu-id="7b5f9-114">Import, into the current instance of Finance, the configurations that you exported from Regulatory Configuration Services (RCS) while you were completing the steps in the [Configure ER formats to use parameters that are specified per legal entity](er-app-specific-parameters-configure-format.md) topic.</span></span> <span data-ttu-id="7b5f9-115">Seguire questi passaggi per ogni configurazione di creazione di report elettronici (ER), nel seguente ordine: modello di dati, mapping di modello e formati.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-115">Follow these steps for each Electronic reporting (ER) configuration, in the following order: data model, model mapping, and formats.</span></span>

    1. <span data-ttu-id="7b5f9-116">Selezionare **Scambia \> Carica da file XML**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-116">Select **Exchange \> Load from XML file**.</span></span>
    2. <span data-ttu-id="7b5f9-117">Selezionare **Sfoglia** per selezionare il file per la configurazione ER necessaria in formato XML.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-117">Select **Browse** to select the file for the required ER configuration in XML format.</span></span>
    3. <span data-ttu-id="7b5f9-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-118">Select **OK**.</span></span>
    
    <span data-ttu-id="7b5f9-119">Nella seguente figura sono riportate le configurazioni che si dovranno avere al termine del passaggio.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-119">The following illustration shows the configurations that you must have when you've finished.</span></span>

    ![Pagina delle configurazioni ER](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a><span data-ttu-id="7b5f9-121">Impostare i parametri per la società DEMF</span><span class="sxs-lookup"><span data-stu-id="7b5f9-121">Set up parameters for the DEMF company</span></span>

<span data-ttu-id="7b5f9-122">È possibile utilizzare il framework ER per impostare i parametri specifici dell'applicazione per un formato ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-122">You can use the ER framework to set up application-specific parameters for an ER format.</span></span>

1.  <span data-ttu-id="7b5f9-123">Selezionare la persona giuridica **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-123">Select the **DEMF** legal entity.</span></span>
2.  <span data-ttu-id="7b5f9-124">Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-124">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
3.  <span data-ttu-id="7b5f9-125">Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-125">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm.PNG)
    
    <span data-ttu-id="7b5f9-127">Nella pagina **Parametri specifici dell'applicazione**, è possibile configurare le regole per l'origine dati **Selettore** del formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-127">On the **Application specific parameters** page, you can configure the rules for the **Selector** data source of the **Format to learn how to lookup LE data** format.</span></span>
    
    <span data-ttu-id="7b5f9-128">Se il formato di ER di base contiene più origini dati di tipo **Ricerca**, è necessario selezionare l'origine dati desiderata nella Scheda dettaglio **Ricerche** prima di iniziare a configurare il set di regole per l'origine dati.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-128">If the base ER format will contain several data sources of the **Lookup** type, you must select the desired data source on the **Lookups** FastTab before you can start to configure the set of rules for the data source.</span></span>
    
    <span data-ttu-id="7b5f9-129">Per ciascuna origine dati, è possibile configurare regole separate per ogni versione del formato di ER selezionato.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-129">For each data source, you can configure separate rules for each version of the selected ER format.</span></span>
    
    <span data-ttu-id="7b5f9-130">L'intero set di regole per tutte le origini dati di ricerca disponibili nella versione selezionata del formato di ER di base costituisce i parametri specifici dell'applicazione per il formato di ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-130">The whole set of rules for all lookup data sources that are available in the selected version of the base ER format makes up the application-specific parameters for the ER format.</span></span>

4.  <span data-ttu-id="7b5f9-131">Selezionare la versione **1.1.1** del formato di ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-131">Select version **1.1.1** of the ER format.</span></span>
5.  <span data-ttu-id="7b5f9-132">Nella Scheda dettaglio **Condizioni** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-132">On the **Conditions** FastTab, select **Add**.</span></span>
6.  <span data-ttu-id="7b5f9-133">Nel campo **Codice** del nuovo record selezionare la freccia a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-133">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="7b5f9-134">La ricerca presenta l'elenco dei codici imposta per la selezione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-134">The lookup presents the list of tax codes for selection.</span></span> <span data-ttu-id="7b5f9-135">Questo elenco viene restituito dall'origine dati **Model.Data.Tax** che è stata configurata nel formato di ER di base.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-135">This list is returned by the **Model.Data.Tax** data source that has been configured in the base ER format.</span></span> <span data-ttu-id="7b5f9-136">Poiché l'origine dati contiene il campo **Nome**, immettere il nome di ogni codice imposta visualizzato nella ricerca.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-136">Because this data source contains the **Name** field, the name of each tax code appears in the lookup.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  <span data-ttu-id="7b5f9-138">Selezionare il codice imposta **VAT19**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-138">Select the **VAT19** tax code.</span></span>
8.  <span data-ttu-id="7b5f9-139">Nel campo **Risultato della ricerca** del nuovo record selezionare la freccia a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-139">In the **Lookup result** field of the new record, select the drop-down arrow to open the lookup.</span></span> <span data-ttu-id="7b5f9-140">La ricerca presenta l'elenco dei valori dell'enumerazione di formato TaxationLevel per la selezione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-140">The lookup presents the list of values for the TaxationLevel format enumeration for selection.</span></span>

    <span data-ttu-id="7b5f9-141">Si noti che, se il tedesco è selezionato come la lingua preferita dell'utente attualmente collegato, le etichette dei valori della ricerca saranno in tedesco, a condizione che siano state tradotte nel formato di ER di base.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-141">Note that, if German is selected as the preferred language of the user that you're signed in as, the labels of the values in the lookup will be in German, provided that they have been translated in the base ER format.</span></span> <span data-ttu-id="7b5f9-142">Inoltre, se l'etichetta di un'origine dati di ricerca è stata tradotta, l'etichetta verrà visualizzata nella lingua preferita dall'utente nella scheda **Ricerche**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-142">Additionally, if the label of a lookup data source has been translated, that label will appear in the user's preferred language on the **Lookups** tab.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  <span data-ttu-id="7b5f9-144">Selezionare il valore **Tassazione regolare**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-144">Select the **Regular taxation** value.</span></span>

    <span data-ttu-id="7b5f9-145">Aggiungendo questo record, si definisce la seguente regola: ogni volta che viene richiesta l'origine dati di ricerca **Selector** e il codice imposta **VAT19** viene passato come argomento, **Tassazione regolare** sarà restituito come livello fiscale richiesto.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-145">By adding this record, you define the following rule: Whenever the **Selector** lookup data source is requested, and the **VAT19** tax code is passed as an argument, **Regular taxation** will be returned as the requested taxation level.</span></span>

10. <span data-ttu-id="7b5f9-146">Selezionare **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-146">Select **Add**, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-147">Nel campo **Codice** selezionare il codice imposta **InVAT19**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-147">In the **Code** field, select the **InVAT19** tax code.</span></span>
    2. <span data-ttu-id="7b5f9-148">Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione regolare**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-148">In the **Lookup result** field, select the **Regular taxation** value.</span></span>
    
11. <span data-ttu-id="7b5f9-149">Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-149">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-150">Nel campo **Codice** selezionare il codice imposta **VAT7**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-150">In the **Code** field, select the **VAT7** tax code.</span></span>
    2. <span data-ttu-id="7b5f9-151">Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione ridotta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-151">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
12. <span data-ttu-id="7b5f9-152">Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-152">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-153">Nel campo **Codice** selezionare il codice imposta **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-153">In the **Code** field, select the **InVAT7** tax code.</span></span>
    2. <span data-ttu-id="7b5f9-154">Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione ridotta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-154">In the **Lookup result** field, select the **Reduced taxation** value.</span></span>
    
13. <span data-ttu-id="7b5f9-155">Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-155">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-156">Nel campo **Codice** selezionare il codice imposta **THIRD**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-156">In the **Code** field, select the **THIRD** tax code.</span></span>
    2. <span data-ttu-id="7b5f9-157">Nel campo **Risultato della ricerca**, selezionare il valore **Nessuna tassazione**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-157">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
14. <span data-ttu-id="7b5f9-158">Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-158">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-159">Nel campo **Codice** selezionare il codice imposta **InVAT0**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-159">In the **Code** field, select the **InVAT0** tax code.</span></span>
    2. <span data-ttu-id="7b5f9-160">Nel campo **Risultato della ricerca**, selezionare il valore **Nessuna tassazione**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-160">In the **Lookup result** field, select the **No taxation** value.</span></span>
    
15. <span data-ttu-id="7b5f9-161">Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="7b5f9-161">Select **Add** again, and then follow these steps:</span></span>

    1. <span data-ttu-id="7b5f9-162">Nel campo **Codice**, selezionare l'opzione **\*Non vuoto\***.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-162">In the **Code** field, select the **\*Not blank\*** option.</span></span>
    2. <span data-ttu-id="7b5f9-163">Nel campo **Risultato della ricerca**, selezionare il valore **Altro**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-163">In the **Lookup result** field, select the **Other** value.</span></span>
    
    <span data-ttu-id="7b5f9-164">Aggiungendo questo record, si definisce la seguente regola: ogni volta che il codice imposta che viene passato come argomento non soddisfa nessuna delle regole precedenti, l'origine dati di ricerca restituirà **Altro** come livello di tassazione richiesto.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-164">By adding this last record, you define the following rule: Whenever the tax code that is passed as an argument doesn't satisfy any of the previous rules, the lookup data source will return **Other** as the requested taxation level.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. <span data-ttu-id="7b5f9-166">Nel campo **Stato** selezionare **Completato**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-166">In the **State** field, select **Completed**.</span></span>

    <span data-ttu-id="7b5f9-167">Quando si esegue una versione di formato di ER con stato **Completato** o **Condiviso**, il set di regole deve essere nello stato **Completato**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-167">When you run an ER format version that has a status of either **Completed** or **Shared**, this set of rules must be in the **Completed** state.</span></span> <span data-ttu-id="7b5f9-168">In caso contrario, l'esecuzione del formato di ER di base viene interrotta quando il formato tenta di caricare i dati del set di regole mentre l'origine dati di ricerca **Selettore** è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-168">Otherwise, execution of the base ER format will be interrupted when the format tries to load data from this set of rules while the **Selector** lookup data source is being run.</span></span>
    
    <span data-ttu-id="7b5f9-169">Quando si esegue una versione di formato di ER con stato **Bozza**, il formato di ER di base può accedere a questo set di regole, indipendentemente dallo stato.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-169">When you run an ER format version that has a status of **Draft**, the base ER format can access this set of rules, regardless of its state.</span></span>
    
17. <span data-ttu-id="7b5f9-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-170">Select **Save**.</span></span>
18. <span data-ttu-id="7b5f9-171">Chiudere la pagina **Parametri specifici dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-171">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-demf-company"></a><span data-ttu-id="7b5f9-172">Eseguire il formato di ER nella società DEMF</span><span class="sxs-lookup"><span data-stu-id="7b5f9-172">Run the ER format in the DEMF company</span></span>

1.  <span data-ttu-id="7b5f9-173">Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-173">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="7b5f9-174">Nel Riquadro azioni selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-174">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="7b5f9-175">Nella finestra di dialogo visualizzata, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-175">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="7b5f9-176">Scaricare il rendiconto generato e memorizzarlo in locale.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-176">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="7b5f9-177">Nel rendiconto generato, notare che il riepilogo del codice imposta **InVAT7** è nel livello **Ridotta** e i riepiloghi dei codici imposta **InVA19** e **VAT19** sono stati inseriti nel livello **Regolare**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-177">In the generated statement, notice that the summary of the **InVAT7** tax code has been put on the **Reduced** level, and the summaries of the **VAT19** and **InVA19** tax codes have been put on the **Regular** level.</span></span> <span data-ttu-id="7b5f9-178">Questo comportamento dipende dalla configurazione nel set di regole dipendenti dalla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-178">This behavior is determined by the configuration in the legal entity–dependent set of rules.</span></span>
    
5.  <span data-ttu-id="7b5f9-179">Passare a **Imposta \> Imposte indirette \> IVA \> Codici IVA**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-179">Go to **Tax \> Indirect taxes \> Sales tax \> Sales tax codes**.</span></span>
6.  <span data-ttu-id="7b5f9-180">Selezionare il codice imposta **InVAT7**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-180">Select the **InVAT7** tax code.</span></span>
7.  <span data-ttu-id="7b5f9-181">Nel riquadro azioni, nella scheda **Codice IVA**, nel gruppo **Richieste di informazioni**, selezionare **IVA registrata** per visualizzare le informazioni sul valore di imposta e sull'aliquota di imposta applicata per codice IVA.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-181">On the Action Pane, on the **Sales tax code** tab, in the **Inquiries** group, select **Posted sales tax** to view information about the tax value and applied tax rate per tax code.</span></span>

    ![Pagina IVA registrata](./media/GER-AppSpecParms-Statement.PNG)

8.  <span data-ttu-id="7b5f9-183">Chiudere la pagina IVA registrata.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-183">Close the Posted sales tax page.</span></span>

## <a name="set-up-parameters-for-the-usmf-company"></a><span data-ttu-id="7b5f9-184">Impostare i parametri per la società USMF</span><span class="sxs-lookup"><span data-stu-id="7b5f9-184">Set up parameters for the USMF company</span></span>

1.  <span data-ttu-id="7b5f9-185">Selezionare la persona giuridica **USMF**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-185">Select the **USMF** legal entity.</span></span>
2.  <span data-ttu-id="7b5f9-186">Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-186">Go to **Organization administration \> Electronic reporting \> Configurations**.</span></span>
3.  <span data-ttu-id="7b5f9-187">Nella struttura di configurazioni, espandere la voce **Modello per ottenere chiamate parametrizzate**, espandere **Formato per ottenere chiamate parametrizzate** e selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-187">In the configurations tree, expand the **Model to learn parameterized calls** item, expand the **Format to learn parameterized calls** item, and select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="7b5f9-188">Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-188">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="7b5f9-189">Selezionare la versione **1.1.1** del formato di ER selezionato.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-189">Select version **1.1.1** of the selected ER format.</span></span>
6.  <span data-ttu-id="7b5f9-190">Nella Scheda dettaglio **Condizioni** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-190">On the **Conditions** FastTab, select **Add**.</span></span>
7.  <span data-ttu-id="7b5f9-191">Nel campo **Codice** del nuovo record selezionare la freccia a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-191">In the **Code** field of the new record, select the drop-down arrow to open the lookup.</span></span>

    <span data-ttu-id="7b5f9-192">La ricerca ora presenta l'elenco dei codici imposta per l'imposta della società **USMF** per la selezione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-192">The lookup now presents the list of tax codes for the **USMF** company tax for selection.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  <span data-ttu-id="7b5f9-194">Selezionare il codice imposta **ESENTE**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-194">Select the **EXEMPT** tax code.</span></span>
9.  <span data-ttu-id="7b5f9-195">Nel campo **Risultato della ricerca** del nuovo record, selezionare il valore **Nessuna tassazione**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-195">In the **Lookup resul** t field of the new record, select the **No taxation** value.</span></span>
10. <span data-ttu-id="7b5f9-196">Selezionare **Aggiungi** nuovamente.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-196">Select **Add** again.</span></span>
11. <span data-ttu-id="7b5f9-197">Nel campo **Codice** del nuovo record, selezionare l'opzione **\*Non vuoto\***.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-197">In the **Code** field of the new record, select the **\*Not blank\*** option.</span></span>
12. <span data-ttu-id="7b5f9-198">Nel campo **Risultato della ricerca** del nuovo record, selezionare il valore **Tassazione regolare**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-198">In the **Lookup result** field of the new record, select the **Regular taxation** value.</span></span>
13. <span data-ttu-id="7b5f9-199">Nel campo **Stato** selezionare **Completato**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-199">In the **State** field, select **Completed**.</span></span>
14. <span data-ttu-id="7b5f9-200">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-200">Select **Save**.</span></span>

    ![Pagina Parametri specifici dell'applicazione ER](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. <span data-ttu-id="7b5f9-202">Chiudere la pagina **Parametri specifici dell'applicazione**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-202">Close the **Application specific parameters** page.</span></span>

## <a name="run-the-er-format-in-the-usmf-company"></a><span data-ttu-id="7b5f9-203">Eseguire il formato di ER nella società USMF</span><span class="sxs-lookup"><span data-stu-id="7b5f9-203">Run the ER format in the USMF company</span></span>

1.  <span data-ttu-id="7b5f9-204">Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-204">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
2.  <span data-ttu-id="7b5f9-205">Nel Riquadro azioni selezionare **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-205">On the Action Pane, select **Run**.</span></span>
3.  <span data-ttu-id="7b5f9-206">Nella finestra di dialogo visualizzata, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-206">In the dialog box that appears, select **OK**.</span></span>
4.  <span data-ttu-id="7b5f9-207">Scaricare il rendiconto generato e memorizzarlo in locale.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-207">Download the statement that is generated and store it locally.</span></span>

    <span data-ttu-id="7b5f9-208">Nel rendiconto generato, notare che è stato riutilizzato lo stesso formato di ER per una persona giuridica diversa, senza effettuare modifiche al formato di ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-208">In the generated statement, notice that you've now reused the same ER format for a different legal entity, but without making any adjustments to the ER format.</span></span>

## <a name="reuse-legal-entitydependent-parameters"></a><span data-ttu-id="7b5f9-209">Riutilizzo dei parametri dipendenti dalla persona giuridica</span><span class="sxs-lookup"><span data-stu-id="7b5f9-209">Reuse legal entity–dependent parameters</span></span>

### <a name="export-parameters"></a><span data-ttu-id="7b5f9-210">Esportare parametri</span><span class="sxs-lookup"><span data-stu-id="7b5f9-210">Export parameters</span></span>

1.  <span data-ttu-id="7b5f9-211">Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-211">Go to **Organization administration \> Workspaces \> Electronic reporting**.</span></span>
2.  <span data-ttu-id="7b5f9-212">Selezionare **Configurazioni report**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-212">Select **Reporting configurations**.</span></span>
3.  <span data-ttu-id="7b5f9-213">Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-213">In the configurations tree, select the **Format to learn how to lookup LE data** format.</span></span>
4.  <span data-ttu-id="7b5f9-214">Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-214">On the Action Pane, on the **Configurations** tab, in the **Application specific parameters** group, select **Setup**.</span></span>
5.  <span data-ttu-id="7b5f9-215">Selezionare la versione **1.1.1** del formato di ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-215">Select version **1.1.1** of the ER format.</span></span>
6.  <span data-ttu-id="7b5f9-216">Nel riquadro azioni, selezionare **Esporta**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-216">On the Action Pane, select **Export**.</span></span>
7.  <span data-ttu-id="7b5f9-217">Scaricare il file generato e memorizzarlo in locale.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-217">Download the file that is generated and store it locally.</span></span>

    <span data-ttu-id="7b5f9-218">Il set configurato dei parametri specifici dell'applicazione è stato esportato come file XML.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-218">The configured set of application-specific parameters has now been exported as an XML file.</span></span>

### <a name="import-parameters"></a><span data-ttu-id="7b5f9-219">Importare parametri</span><span class="sxs-lookup"><span data-stu-id="7b5f9-219">Import parameters</span></span>

1.  <span data-ttu-id="7b5f9-220">Selezionare la versione **1.1.2** del formato di ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-220">Select version **1.1.2** of the ER format.</span></span>
2.  <span data-ttu-id="7b5f9-221">Nel riquadro azioni, selezionare **Importa**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-221">On the Action Pane, select **Import**.</span></span>
3.  <span data-ttu-id="7b5f9-222">Selezionare **Sì** per confermare che si desidera sostituire i parametri specifici dell'applicazione esistenti per questa versione di formato.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-222">Select **Yes** to confirm that you want to override the existing application-specific parameters for this format version.</span></span>
4.  <span data-ttu-id="7b5f9-223">Selezionare **Sfoglia** per individuare il file contenente i parametri specifici dell'applicazione esportati per la versione **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-223">Select **Browse** to find the file that contains the exported application-specific parameters for version **1.1.1**.</span></span>
5.  <span data-ttu-id="7b5f9-224">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-224">Select **OK**.</span></span>

    <span data-ttu-id="7b5f9-225">Versione **1.1.2** del formato di ER ora con gli stessi parametri specifici dell'applicazione originariamente configurati per la versione **1.1.1**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-225">Version **1.1.2** of the ER format now has the same application-specific parameters that you originally configured for version **1.1.1**.</span></span>
    
    <span data-ttu-id="7b5f9-226">Si noti che i parametri specifici dell'applicazione di un formato di ER sono dipendenti dalla persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-226">Note that the application-specific parameters of an ER format are legal entity–dependent.</span></span> <span data-ttu-id="7b5f9-227">Per riutilizzare i parametri specifici dell'applicazione configurati per una persona giuridica in una persona giuridica diversa, è necessario esportarli mentre si è collegati alla prima persona giuridica e quindi importarli dopo aver effettuato l'accesso all'altra persona giuridica.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-227">To reuse the application-specific parameters that were configured for one legal entity in a different legal entity, you must export them while you're signed in to the first legal entity and then import them after you sign in to the other legal entity.</span></span>

    <span data-ttu-id="7b5f9-228">È inoltre possibile utilizzare questo approccio per trasferire i parametri specifici di un'applicazione relativi al formato ER originariamente configurati in un'istanza di Finance in un'altra istanza di Finance.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-228">You can also use this approach to transfer an ER format related application-specific parameters that were originally configured in one instance of Finance to another instance of Finance.</span></span>

    <span data-ttu-id="7b5f9-229">Tenere presente che se si configurano i parametri specifici dell'applicazione per una versione di un formato ER e si importa una versione superiore dello stesso formato nell'istanza di Finance corrente, i parametri specifici dell'applicazione esistenti non verranno applicati per la versione importata.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-229">Be aware that if you configure application-specific parameters for one version of an ER format and import a higher version of the same format into the current Finance instance, the existing application-specific parameters won't be applied for the imported version.</span></span>
    
    <span data-ttu-id="7b5f9-230">Inoltre, tenere presente che, quando si seleziona un file per l'importazione, la struttura dei parametri specifici dell'applicazione in quel file viene confrontata con la struttura dell'origine dati corrispondente del tipo **Ricerca** nel formato ER selezionato per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-230">Also be aware that, when you select a file for import, the structure of the application-specific parameters in that file is compared with the structure of the corresponding data source of the **Lookup** type in the ER format that is selected for import.</span></span> <span data-ttu-id="7b5f9-231">L'importazione viene eseguita quando la struttura di ciascun parametro specifico dell'applicazione corrisponde alla struttura dell'origine dati corrispondente nel formato ER selezionato per l'importazione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-231">The import is done when the structure of each application-specific parameter matches the structure of the corresponding data source in the ER format that is selected for import.</span></span> <span data-ttu-id="7b5f9-232">Se le strutture non corrispondono, viene visualizzato un messaggio di avviso che informa che non è possibile eseguire l'importazione.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-232">If the structures don't match, you receive a warning message that states that the import can't be done.</span></span> <span data-ttu-id="7b5f9-233">Se si forza l'esecuzione dell'importazione, i parametri specifici dell'applicazione esistenti per il formato ER selezionato verranno cancellati e sarà necessario configurarli dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-233">If you force the import to be done, the existing application-specific parameters for the selected ER format will be cleaned up, and you must set them up from the beginning.</span></span>

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a><span data-ttu-id="7b5f9-234">Relazione tra parametri specifici dell'applicazione e un formato ER</span><span class="sxs-lookup"><span data-stu-id="7b5f9-234">Relationship between application-specific parameters and an ER format</span></span>

<span data-ttu-id="7b5f9-235">La relazione tra un formato ER e i parametri specifici dell'applicazione è stabilita dal codice identificativo univoco indipendente dall'istanza del formato ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-235">The relationship between an ER format and its application-specific parameters is established by the ER format's instance-independent unique identification code.</span></span> <span data-ttu-id="7b5f9-236">Pertanto, quando si rimuove un formato ER da Finance, i parametri specifici dell'applicazione configurati per il formato ER vengono mantenuti nell'istanza corrente di Finance.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-236">Therefore, when you remove an ER format from Finance, the application-specific parameters that are configured for the ER format are kept in the current instance of Finance.</span></span> <span data-ttu-id="7b5f9-237">È possibile accedervi ogni volta che il formato ER di base viene reimportato in questa istanza di Finance.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-237">They can be accessed whenever the base ER format is reimported into this instance of Finance.</span></span>

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a><span data-ttu-id="7b5f9-238">Accedere ai parametri specifici dell'applicazione utilizzando il framework ER</span><span class="sxs-lookup"><span data-stu-id="7b5f9-238">Access application-specific parameters by using the ER framework</span></span>

<span data-ttu-id="7b5f9-239">Nell'esempio precedente, è stato effettuato l'accesso ai parametri specifici dell'applicazione di un formato ER utilizzando il framework ER.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-239">In the preceding example, you have accessed application-specific parameters of an ER format by using the ER framework.</span></span> <span data-ttu-id="7b5f9-240">Questo approccio non consente di limitare l'accesso ai parametri specifici dell'applicazione di un formato ER specifico.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-240">This approach doesn't let you restrict access to the application-specific parameters of a specific ER format.</span></span> <span data-ttu-id="7b5f9-241">Se è necessario applicare tali restrizioni, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-241">If you must apply such restrictions, follow these steps.</span></span> 

1.  <span data-ttu-id="7b5f9-242">Riutilizzare la voce di menu esistente **ERSolutionAppSpecificParametersDesigner** oppure implementare la propria voce di menu **ERSolutionAppSpecificParametersDesigner**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-242">Either reuse an existing **ERSolutionAppSpecificParametersDesigner** menu item, or implement your own **ERSolutionAppSpecificParametersDesigner** menu item.</span></span>

    ![Pagina Visual Studio](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  <span data-ttu-id="7b5f9-244">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-244">Follow one of these steps:</span></span>

    1.  <span data-ttu-id="7b5f9-245">Creare un nuovo pulsante voce di menu e collegarlo al record corrispondente dalla tabella **ERSolutionTable** impostando la proprietà **Origine dati** su **ERSolutionTable**.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-245">Create a new menu item button, and link it to the corresponding record from the **ERSolutionTable** table by setting its **Data Source** property to **ERSolutionTable**.</span></span>
    
        ![Pagina Visual Studio](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  <span data-ttu-id="7b5f9-247">Creare un pulsante semplice ed eseguire l'override del metodo **selezionato** come illustrato nell'esempio riportato di seguito.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-247">Create a simple button, and override the **Clicked** method as shown in the following example.</span></span>
    
        <span data-ttu-id="7b5f9-248">Utilizzando questo metodo, è possibile specificare un ID univoco della soluzione (definito tramite il valore **GUID** ) per consentire l'accesso ai parametri specifici dell'applicazione di un solo formato specifico di ER e delle copie discendenti che ne derivano.</span><span class="sxs-lookup"><span data-stu-id="7b5f9-248">By using this approach, you can specify a unique solution ID (defined via the **GUID** value) to allow access to the application-specific parameters of only a specific ER format and descendant copies that have been derived from it.</span></span>
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a><span data-ttu-id="7b5f9-249">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7b5f9-249">Additional resources</span></span>

[<span data-ttu-id="7b5f9-250">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="7b5f9-250">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="7b5f9-251">Configurare i formati di ER per utilizzare i parametri specifici per la persona giuridica</span><span class="sxs-lookup"><span data-stu-id="7b5f9-251">Configure ER formats to use parameters that are specified per legal entity</span></span>](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]