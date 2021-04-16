---
title: Introduzione alla fatturazione elettronica per il Messico
description: Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per il Messico.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 2f5dd1d6bc520c9f5349c77dfcabdf2d538881ce
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5840054"
---
# <a name="get-started-with-electronic-invoicing-for-mexico"></a><span data-ttu-id="559ab-103">Introduzione alla fatturazione elettronica per il Messico</span><span class="sxs-lookup"><span data-stu-id="559ab-103">Get started with Electronic invoicing for Mexico</span></span>

[!include [banner](../includes/banner.md)]

> [!IMPORTANT]
> <span data-ttu-id="559ab-104">La fatturazione elettronica per il Messico potrebbe attualmente non supportare tutte le funzioni disponibili nel documento Comprobante Fiscal Digital por Internet (CFDI) e nella relativa integrazione incorporata in Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="559ab-104">Electronic invoicing for Mexico might not currently support all the functions that are available in the Comprobante Fiscal Digital por Internet (CFDI) document, and in the related integration that is built into Microsoft Dynamics 365 Finance or Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="559ab-105">Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per il Messico.</span><span class="sxs-lookup"><span data-stu-id="559ab-105">This topic provides information that will help you get started with Electronic invoicing for Mexico.</span></span> <span data-ttu-id="559ab-106">Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e Finance.</span><span class="sxs-lookup"><span data-stu-id="559ab-106">It guides you through the configuration steps that are country-dependent in Regulatory Configuration Services (RCS) and Finance.</span></span> <span data-ttu-id="559ab-107">Inoltre, guida l'utente attraverso i passaggi da seguire in Finance per inviare fatture CFDI tramite il servizio e spiega come esaminare i risultati dell'elaborazione e lo stato delle fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-107">It also guides you through the steps that you must follow in Finance to submit CFDI invoices through the service, and it explains how to review the processing results and the status of CFDI invoices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="559ab-108">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="559ab-108">Prerequisites</span></span>

<span data-ttu-id="559ab-109">Prima di completare i passaggi in questo argomento, è necessario completare i passaggi in [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="559ab-109">Before you complete the steps in this topic, you must complete the steps in [Get started with Electronic invoicing](e-invoicing-get-started.md).</span></span>

## <a name="rcs-setup"></a><span data-ttu-id="559ab-110">Impostazioni RCS</span><span class="sxs-lookup"><span data-stu-id="559ab-110">RCS setup</span></span>

<span data-ttu-id="559ab-111">Durante la configurazione RCS, completerai queste attività:</span><span class="sxs-lookup"><span data-stu-id="559ab-111">During the RCS setup, you will complete these tasks:</span></span>

1. <span data-ttu-id="559ab-112">Importa la funzionalità per la fatturazione elettronica per l'elaborazione delle fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-112">Import the e-Invoicing feature for processing CFDI invoices.</span></span>
2. <span data-ttu-id="559ab-113">Rivedi le configurazioni di formato necessarie per generare, inviare e ricevere risposte sulle fatture CFDI e per inviare e ricevere risposte sull'annullamento.</span><span class="sxs-lookup"><span data-stu-id="559ab-113">Review the format configurations that are required to generate, submit, and receive responses about CFDI invoices, and to submit and receive responses about cancellation.</span></span>
3. <span data-ttu-id="559ab-114">Configura gli eventi che supportano gli scenari di invio delle fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-114">Configure the events that support the CFDI invoice submission scenarios.</span></span>
4. <span data-ttu-id="559ab-115">Pubblica la funzionalità per la fatturazione elettronica per le fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-115">Publish the e-Invoicing feature for CFDI invoices.</span></span>

> [!NOTE]
> <span data-ttu-id="559ab-116">"La funzionalità per la fatturazione elettronica" è il nome generico della risorsa configurata e pubblicata per utilizzare il server della fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="559ab-116">"The e-Invoicing feature" is the generic name for the resource that is configured and published to consume the Electronic invoicing server.</span></span> <span data-ttu-id="559ab-117">In questo caso, le fatture CFDI (MX) rappresentano la funzionalità per la fatturazione elettronica che configurerai.</span><span class="sxs-lookup"><span data-stu-id="559ab-117">In this case, CFDI invoices (MX) are the e-Invoicing feature that you will set up.</span></span>

## <a name="import-the-e-invoicing-feature"></a><span data-ttu-id="559ab-118">Importare la funzionalità per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-118">Import the e-Invoicing feature</span></span>

1. <span data-ttu-id="559ab-119">Accedi al tuo account RCS.</span><span class="sxs-lookup"><span data-stu-id="559ab-119">Sign in to your RCS account.</span></span>
2. <span data-ttu-id="559ab-120">Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.</span><span class="sxs-lookup"><span data-stu-id="559ab-120">In the **Globalization features** workspace, in the **Features** section, select the **e-Invoicing** tile.</span></span>
3. <span data-ttu-id="559ab-121">Nella pagina **Funzionalità di fatturazione elettronica**, seleziona **Importa** per importare la funzionalità **Fatture CFDI (MX)** dal repository globale.</span><span class="sxs-lookup"><span data-stu-id="559ab-121">On the **e-Invoicing Features** page, select **Import** to import the **CFDI invoices (MX)** feature from the Global repository.</span></span>

    > [!NOTE]
    > <span data-ttu-id="559ab-122">Se non vedi la funzionalità nell'elenco, seleziona **Sincronizza** e quindi ripeti il passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="559ab-122">If you don't see the feature in the list, select **Synchronize**, and then repeat step 3.</span></span>

![Importazione della funzionalità per le fatture CFDI (MX)](media/e-Invoicing-services-get-started-MEX-Select-Import-CFDI-feature.png)

<span data-ttu-id="559ab-124">Quando importi la funzionalità **Fatture CFDI (MX)** dal repository globale, vengono importate anche tutte le impostazioni delle funzionalità, comprese le configurazioni e le azioni.</span><span class="sxs-lookup"><span data-stu-id="559ab-124">When you import the **CFDI invoices (MX)** feature from the Global repository, all the feature settings, including configurations and actions, are also imported.</span></span>

### <a name="create-a-new-version-of-the-cfdi-invoices-mx-feature"></a><span data-ttu-id="559ab-125">Creare una nuova versione della funzionalità Fatture CFDI (MX)</span><span class="sxs-lookup"><span data-stu-id="559ab-125">Create a new version of the CFDI invoices (MX) feature</span></span>

<span data-ttu-id="559ab-126">È possibile creare una nuova versione se, ad esempio, gli URL devono essere aggiornati.</span><span class="sxs-lookup"><span data-stu-id="559ab-126">You can create a new version if, for example, URLs must be updated.</span></span> <span data-ttu-id="559ab-127">Per ulteriori informazioni, vedi [Fatturazione elettronica CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span><span class="sxs-lookup"><span data-stu-id="559ab-127">For more information, see [E-invoicing CFDI](tasks/mx-00010-e-invoicing-cfdi.md).</span></span>

- <span data-ttu-id="559ab-128">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="559ab-128">On the **e-Invoicing Features** page, on the **Versions** tab, select **New**.</span></span>

![Aggiunta di una nuova versione della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Select-New-e-Invoicing-feature.png)

### <a name="update-the-configuration-version"></a><span data-ttu-id="559ab-130">Aggiornare la versione della configurazione</span><span class="sxs-lookup"><span data-stu-id="559ab-130">Update the configuration version</span></span>

1. <span data-ttu-id="559ab-131">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi** o **Elimina** per gestire le versioni di configurazione (configurazioni formato di file ER).</span><span class="sxs-lookup"><span data-stu-id="559ab-131">On the **e-Invoicing Features** page, on the **Configurations** tab, select **Add** or **Delete** to manage the configuration versions (ER file format configurations).</span></span>

    ![Gestione delle configurazioni della funzionalità per la fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Configurations.png)

    <span data-ttu-id="559ab-133">Quando crei una nuova versione, tutte le configurazioni vengono ereditate dall'ultima versione pubblicata.</span><span class="sxs-lookup"><span data-stu-id="559ab-133">When you create a new version, all configurations are inherited from the last published version.</span></span> <span data-ttu-id="559ab-134">Per elaborare le fatture CFDI, sono necessarie le seguenti configurazioni:</span><span class="sxs-lookup"><span data-stu-id="559ab-134">To process CFDI invoices, the following configurations are required:</span></span>

    - <span data-ttu-id="559ab-135">Fattura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="559ab-135">CFDI invoice (BusinessDocumentService)</span></span>
    - <span data-ttu-id="559ab-136">Importazione del messaggio di risposta CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-136">CFDI response message import</span></span>
    - <span data-ttu-id="559ab-137">Importazione del registro errori CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-137">CFDI error log import</span></span>
    - <span data-ttu-id="559ab-138">Richiesta di annullamento CFDI (MX) (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="559ab-138">CFDI cancelation request (MX) (BusinessDocumentService)</span></span>
    - <span data-ttu-id="559ab-139">Fattura CFDI (BusinessDocumentService)</span><span class="sxs-lookup"><span data-stu-id="559ab-139">CFDI invoice (BusinessDocumentService)</span></span>

2. <span data-ttu-id="559ab-140">Nell'elenco, seleziona una versione di configurazione, quindi seleziona **Modifica** o **Visualizza** per aprire la pagina **Progettazione formati**, dove puoi modificare o visualizzare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="559ab-140">In the list, select a configuration version, and then select **Edit** or **View** to open the **Format designer** page, where you can edit or view the configuration.</span></span>

    ![Apertura della pagina Progettazione formati](media/e-Invoicing-services-get-started-MEX-Configuration-ER-format-designer.png)

3. <span data-ttu-id="559ab-142">Utilizza la pagina **Progettazione formati** per modificare e visualizzare le configurazioni dei file in formato ER.</span><span class="sxs-lookup"><span data-stu-id="559ab-142">Use the **Format designer** page to edit and view the ER format file configurations.</span></span> <span data-ttu-id="559ab-143">Per ulteriori informazioni, vedi [Creare configurazioni di creazione di report elettronici (ER)](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="559ab-143">For more information, see [Create electronic document configurations](../../dev-itpro/analytics/electronic-reporting-configuration.md).</span></span>

    ![Pagina Progettazione formati](media/e-Invoicing-services-get-started-MEX-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a><span data-ttu-id="559ab-145">Gestire le configurazioni della funzionalità di fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-145">Manage the e-Invoicing feature setups</span></span>

- <span data-ttu-id="559ab-146">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, seleziona **Aggiungi**, **Elimina** o **Modifica** per gestire le configurazioni della funzionalità di fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="559ab-146">On the **e-Invoicing Features** page, on the **Setups** tab, select **Add**, **Delete**, or **Edit** to manage the e-Invoicing feature setups.</span></span>

![Gestione delle configurazioni della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Manage-e-Invoicing-feature-Setup.png)

<span data-ttu-id="559ab-148">Per inviare fatture CFDI per l'autorizzazione (generare il file XML, inviare il file XML ed elaborare la risposta), è richiesta la configurazione della funzionalità **Fattura di vendita**.</span><span class="sxs-lookup"><span data-stu-id="559ab-148">To submit CFDI invoices for authorization (generate the XML file, submit the XML file, and process the response), the **Sales invoice** feature setup is required.</span></span>

<span data-ttu-id="559ab-149">Per inviare l'annullamento della fattura CFDI, sono obbligatorie le configurazioni delle funzionalità **Annullamento** e **Annulla**.</span><span class="sxs-lookup"><span data-stu-id="559ab-149">To submit CFDI invoice cancellation, the **Cancellation** and **Cancel** feature setups are required.</span></span>

### <a name="configure-the-sales-invoice-feature-setup"></a><span data-ttu-id="559ab-150">Configurare l'impostazione della funzionalità Fattura di vendita</span><span class="sxs-lookup"><span data-stu-id="559ab-150">Configure the Sales invoice feature setup</span></span>

1. <span data-ttu-id="559ab-151">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Configurazioni**, nella colonna **Configurazione funzionalità**, seleziona **Fattura di vendita**.</span><span class="sxs-lookup"><span data-stu-id="559ab-151">On the **e-Invoicing Features** page, on the **Setups** tab, in the **Feature setup** column, select **Sales invoice**.</span></span>
2. <span data-ttu-id="559ab-152">Seleziona **Modifica** per configurare le azioni, le regole di applicabilità e le variabili.</span><span class="sxs-lookup"><span data-stu-id="559ab-152">Select **Edit** to configure the actions, applicability rules, and variables.</span></span>

    ![Modifica della configurazione della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Edit-e-Invoicing-feature-setup.png)

3. <span data-ttu-id="559ab-154">Nella pagina **Configurazione versioni funzionalità**, seleziona la scheda **Azioni** per gestire l'elenco delle azioni.</span><span class="sxs-lookup"><span data-stu-id="559ab-154">On the **Feature version setup** page, select the **Actions** tab to manage the list of actions.</span></span> <span data-ttu-id="559ab-155">Le azioni definiscono un elenco di operazioni che devono essere eseguite in ordine sequenziale per completare l'intera esecuzione dell'evento.</span><span class="sxs-lookup"><span data-stu-id="559ab-155">Actions define a list of operations that must be run in sequential order to accomplish full execution of the event.</span></span>

    ![Scheda Azioni](media/e-Invoicing-services-get-started-MEX-Select-Actions.png)

    | <span data-ttu-id="559ab-157">ID azione</span><span class="sxs-lookup"><span data-stu-id="559ab-157">Action ID</span></span> | <span data-ttu-id="559ab-158">Azione</span><span class="sxs-lookup"><span data-stu-id="559ab-158">Action</span></span>                   | <span data-ttu-id="559ab-159">Nome azione</span><span class="sxs-lookup"><span data-stu-id="559ab-159">Action name</span></span>                                  | <span data-ttu-id="559ab-160">Descrizione azione</span><span class="sxs-lookup"><span data-stu-id="559ab-160">Action description</span></span>                                          |
    |-----------|--------------------------|----------------------------------------------|-------------------------------------------------------------|
    | <span data-ttu-id="559ab-161">1</span><span class="sxs-lookup"><span data-stu-id="559ab-161">1</span></span>         | <span data-ttu-id="559ab-162">Trasforma documento</span><span class="sxs-lookup"><span data-stu-id="559ab-162">Transform document</span></span>       | <span data-ttu-id="559ab-163">Generare la fattura elettronica CFDI senza firma digitale</span><span class="sxs-lookup"><span data-stu-id="559ab-163">Generate CFDI E-Invoice without digital sign</span></span> | <span data-ttu-id="559ab-164">Genera la fattura elettronica CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-164">Generate the CFDI e-invoice.</span></span>                                |
    | <span data-ttu-id="559ab-165">2</span><span class="sxs-lookup"><span data-stu-id="559ab-165">2</span></span>         | <span data-ttu-id="559ab-166">Firma documento</span><span class="sxs-lookup"><span data-stu-id="559ab-166">Sign document</span></span>            | <span data-ttu-id="559ab-167">Firma digitale</span><span class="sxs-lookup"><span data-stu-id="559ab-167">Digital sign</span></span>                                 | <span data-ttu-id="559ab-168">Firma digitalmente la fattura elettronica per l'invio.</span><span class="sxs-lookup"><span data-stu-id="559ab-168">Digitally sign the e-invoice for submission.</span></span>                |
    | <span data-ttu-id="559ab-169">3</span><span class="sxs-lookup"><span data-stu-id="559ab-169">3</span></span>         | <span data-ttu-id="559ab-170">Chiama servizio PAC messicano</span><span class="sxs-lookup"><span data-stu-id="559ab-170">Call Mexican PAC service</span></span> | <span data-ttu-id="559ab-171">Inviare la fattura elettronica CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-171">Submit CFDI E-Invoice</span></span>                        | <span data-ttu-id="559ab-172">Il client Windows Communication Foundation (WCF) invia la fattura elettronica CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-172">The Windows Communication Foundation (WCF) client submits the CFDI e-invoice.</span></span> |
    | <span data-ttu-id="559ab-173">4</span><span class="sxs-lookup"><span data-stu-id="559ab-173">4</span></span>         | <span data-ttu-id="559ab-174">Elabora risposta</span><span class="sxs-lookup"><span data-stu-id="559ab-174">Process response</span></span>         | <span data-ttu-id="559ab-175">Analizzare la risposta del servizio Web</span><span class="sxs-lookup"><span data-stu-id="559ab-175">Analyze web service response</span></span>                 | <span data-ttu-id="559ab-176">Analizza la risposta del servizio Web e restituisci il registro degli errori.</span><span class="sxs-lookup"><span data-stu-id="559ab-176">Analyze the web service response, and return the error log.</span></span> |

### <a name="set-up-the-url-for-mexican-pac-web-services"></a><span data-ttu-id="559ab-177">Configurare l'URL per i servizi Web PAC messicano</span><span class="sxs-lookup"><span data-stu-id="559ab-177">Set up the URL for Mexican PAC web services</span></span> 

1. <span data-ttu-id="559ab-178">Nella pagina **Configurazione versione funzionalità**, nella scheda **Azioni**, nella Scheda dettaglio **Azioni**, seleziona **Chiama servizio PAC messicano**.</span><span class="sxs-lookup"><span data-stu-id="559ab-178">On the **Feature version setup** page, on the **Actions** tab, on the **Actions** FastTab, select **Call Mexican PAC service**.</span></span>
2. <span data-ttu-id="559ab-179">Nella Scheda dettaglio **Parametri**, nel campo **Indirizzo URL**, immetti l'URL del servizio Web per l'invio della fattura CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-179">On the **Parameters** FastTab, in the **URL address** field, enter the URL of the web service for CFDI invoice submission.</span></span>

> [!NOTE]
> <span data-ttu-id="559ab-180">Utilizza gli stessi passaggi per aggiornare l'URL per l'azione **Chiama servizio PAC messicano** per le configurazioni delle funzionalità **Annulla** e **Richiesta di annullamento**.</span><span class="sxs-lookup"><span data-stu-id="559ab-180">Use the same steps to update the URL for **Call Mexican PAC service** action for the **Cancel** and **Cancelation request** feature setups.</span></span>

## <a name="assign-the-draft-version-to-an-e-invoicing-environment"></a><span data-ttu-id="559ab-181">Assegnare la versione Bozza a un ambiente di fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-181">Assign the Draft version to an e-Invoicing environment</span></span>

1. <span data-ttu-id="559ab-182">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Ambienti**, seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="559ab-182">On the **e-Invoicing Features** page, on the **Environments** tab, select **Enable**.</span></span>
2. <span data-ttu-id="559ab-183">Nel campo **Ambiente**, seleziona l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="559ab-183">In the **Environment** field, select the environment.</span></span>
3. <span data-ttu-id="559ab-184">Nel campo **Valido da**, seleziona la data in cui il nuovo ambiente dovrebbe diventare effettivo.</span><span class="sxs-lookup"><span data-stu-id="559ab-184">In the **Effective from** field, select the date when the environment should become effective.</span></span>
3. <span data-ttu-id="559ab-185">Seleziona **Abilita**.</span><span class="sxs-lookup"><span data-stu-id="559ab-185">Select **Enable**.</span></span>

![Abilitazione di un ambiente di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Enable-e-Invoicing-Environment.png)

## <a name="change-the-version-status-to-completed"></a><span data-ttu-id="559ab-187">Modificare lo stato della versione in Completato</span><span class="sxs-lookup"><span data-stu-id="559ab-187">Change the version status to Completed</span></span>

1. <span data-ttu-id="559ab-188">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona la versione della funzionalità di fatturazione elettronica con stato **Bozza**.</span><span class="sxs-lookup"><span data-stu-id="559ab-188">On the **e-Invoicing Features** page, on the **Versions** tab, select the version of the e-Invoicing feature that has a status of **Draft**.</span></span>
2. <span data-ttu-id="559ab-189">Selezionare **Cambia stato \> Completa**.</span><span class="sxs-lookup"><span data-stu-id="559ab-189">Select **Change status \> Complete**.</span></span>

## <a name="change-the-version-status-to-published"></a><span data-ttu-id="559ab-190">Modificare lo stato della versione in Pubblicato</span><span class="sxs-lookup"><span data-stu-id="559ab-190">Change the version status to Published</span></span>

- <span data-ttu-id="559ab-191">Nella pagina **Funzionalità di fatturazione elettronica**, nella scheda **Versioni**, seleziona **Cambia stato \> Pubblica**.</span><span class="sxs-lookup"><span data-stu-id="559ab-191">On the **e-Invoicing Features** page, on the **Versions** tab, select **Change status \> Publish**.</span></span>

## <a name="publish-the-e-invoicing-feature"></a><span data-ttu-id="559ab-192">Pubblicare la funzionalità per la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-192">Publish the e-Invoicing feature</span></span>

1. <span data-ttu-id="559ab-193">Nella pagina **Funzionalità di fatturazione elettronica**, seleziona la scheda **Versioni** per gestire lo stato della funzionalità **Fatture CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="559ab-193">On the **e-Invoicing Features** page, select the **Versions** tab to manage the status of the **CFDI invoices (MX)** feature.</span></span>
2. <span data-ttu-id="559ab-194">Seleziona **Cambia stato** per modificare lo stato della funzionalità.</span><span class="sxs-lookup"><span data-stu-id="559ab-194">Select **Change status** to change the status of the feature.</span></span>

![Modifica dello stato della funzionalità di fatturazione elettronica](media/e-Invoicing-services-get-started-MEX-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing--integration-in-finance"></a><span data-ttu-id="559ab-196">Configurare l'integrazione della fatturazione elettronica in Finance</span><span class="sxs-lookup"><span data-stu-id="559ab-196">Set up Electronic invoicing  integration in Finance</span></span>

<span data-ttu-id="559ab-197">Per configurare la fatturazione elettronica in Finance, completerai queste attività:</span><span class="sxs-lookup"><span data-stu-id="559ab-197">To set up Electronic invoicing in Finance, you will complete these tasks:</span></span>

1. <span data-ttu-id="559ab-198">Importa il modello di dati ER, il mapping del modello di dati ER e i formati richiesti per le fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-198">Import the ER data model, the ER data model mapping, and the formats that are required for CFDI invoices.</span></span>
2. <span data-ttu-id="559ab-199">Configura i tipi di risposta per l'aggiornamento delle fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-199">Configure response types for updating the CFDI invoices.</span></span> <span data-ttu-id="559ab-200">Questi tipi di risposta vengono utilizzati per la risposta dal server PAC (provider di certificazione autorizzato).</span><span class="sxs-lookup"><span data-stu-id="559ab-200">These response types are used for the response from the authorized certification provider (PAC) server.</span></span>

### <a name="import-the-er-data-model-er-data-model-mapping-and-context-configurations-for-cfdi-invoices"></a><span data-ttu-id="559ab-201">Importare il modello di dati ER, il mapping del modello di dati ER e le configurazioni del contesto per le fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-201">Import the ER data model, ER data model mapping, and context configurations for CFDI invoices</span></span>

1. <span data-ttu-id="559ab-202">Accedi a Finance.</span><span class="sxs-lookup"><span data-stu-id="559ab-202">Sign in to Finance.</span></span>
2. <span data-ttu-id="559ab-203">Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="559ab-203">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span> <span data-ttu-id="559ab-204">Assicurati che questo provider di configurazione sia impostato su **Attivo**.</span><span class="sxs-lookup"><span data-stu-id="559ab-204">Make sure that this configuration provider is set to **Active**.</span></span> <span data-ttu-id="559ab-205">Per ulteriori informazioni su come impostare un provider su **Attivo**, vedi [Creare provider di configurazioni e contrassegnarli come attivi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span><span class="sxs-lookup"><span data-stu-id="559ab-205">For information about how to set a provider to **Active**, see [Create configuration providers and mark them as active](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/analytics/tasks/er-configuration-provider-mark-it-active-2016-11).</span></span>
3. <span data-ttu-id="559ab-206">Selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="559ab-206">Select **Repositories**.</span></span>
4. <span data-ttu-id="559ab-207">Seleziona **Risorsa globale \> Apri**.</span><span class="sxs-lookup"><span data-stu-id="559ab-207">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="559ab-208">Importa **Modello di fattura**, **Mapping modello di fattura**, **Formato fattura CFDI (MX)**, **Formato di richiesta annullamento fattura CFDI (MX)** e **Formato di annullamento della fattura CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="559ab-208">Import **Invoice model**, **Invoice model mapping**, **CFDI invoice format (MX)**, **CFDI invoice cancelation request format (MX)**, and **CFDI invoice cancel format (MX)**.</span></span>

### <a name="turn-on-the-feature-for-processing-cfdi-invoices"></a><span data-ttu-id="559ab-209">Attivare la funzionalità per l'elaborazione delle fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-209">Turn on the feature for processing CFDI invoices</span></span>

1. <span data-ttu-id="559ab-210">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="559ab-210">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="559ab-211">Nella scheda **Funzionalità**, seleziona la casella di controllo **Abilita** nelle righe per i riferimenti alle funzionalità **MX-00010** e **MX-00016**.</span><span class="sxs-lookup"><span data-stu-id="559ab-211">On the **Features** tab, select the **Enable** check box in the rows for feature references **MX-00010** and **MX-00016**.</span></span>

![Attivazione delle funzionalità per l'elaborazione delle fatture CFDI](media/e-Invoicing-services-get-started-MEX-Enable-CFDI-feature.png)

### <a name="import-er-configurations-and-set-up-the-response-types-for-updating-cfdi-invoices"></a><span data-ttu-id="559ab-213">Importare le configurazioni ER e configurare i tipi di risposta per l'aggiornamento delle fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-213">Import ER configurations and set up the response types for updating CFDI invoices</span></span>

#### <a name="import-er-configurations"></a><span data-ttu-id="559ab-214">Importare configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="559ab-214">Import ER configurations</span></span>

1. <span data-ttu-id="559ab-215">Nell'area di lavoro **Creazione di report elettronici**, nella sezione **Provider di configurazione**, seleziona il riquadro **Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="559ab-215">In the **Electronic reporting** workspace, in the **Configuration providers** section, select the **Microsoft** title.</span></span>
3. <span data-ttu-id="559ab-216">Selezionare **Archivi**.</span><span class="sxs-lookup"><span data-stu-id="559ab-216">Select **Repositories**.</span></span>
4. <span data-ttu-id="559ab-217">Seleziona **Risorsa globale \> Apri**.</span><span class="sxs-lookup"><span data-stu-id="559ab-217">Select **Global resource \> Open**.</span></span>
5. <span data-ttu-id="559ab-218">Importa **Modello di messaggio di risposta**, **Importazione registro errori CFDI (MX)** e **Importazione messaggi di risposta CFDI (MX)**.</span><span class="sxs-lookup"><span data-stu-id="559ab-218">Import **Response message model**, **CFDI error log import (MX)**, and **CFDI response message import (MX)**.</span></span>

#### <a name="set-up-the-response-types"></a><span data-ttu-id="559ab-219">Configurare i tipi di risposta</span><span class="sxs-lookup"><span data-stu-id="559ab-219">Set up the response types</span></span>

1. <span data-ttu-id="559ab-220">Vai a **Amministrazione organizzazione \> Impostazione \> Parametri documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="559ab-220">Go to **Organization administration \> Setup \> Electronic document parameters**.</span></span>
2. <span data-ttu-id="559ab-221">Nella scheda **Documento elettronico**, seleziona **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="559ab-221">On the **Electronic document** tab, select **Add**.</span></span>
3. <span data-ttu-id="559ab-222">Immetti il giornale di registrazione fatture cliente e quindi nel campo **Nome tabella** seleziona la fattura del progetto.</span><span class="sxs-lookup"><span data-stu-id="559ab-222">Enter the customer invoice journal, and then, in the **Table name** field, select the project invoice.</span></span>
4. <span data-ttu-id="559ab-223">Per ogni tabella, definisci un contesto di documento correlato:</span><span class="sxs-lookup"><span data-stu-id="559ab-223">For each table, define a related document context:</span></span>

    - <span data-ttu-id="559ab-224">Per **Giornale di registrazione fatture cliente**, immetti **Contesto della fattura cliente**.</span><span class="sxs-lookup"><span data-stu-id="559ab-224">For **Customer invoice journal**, enter **Customer invoice context**.</span></span>
    - <span data-ttu-id="559ab-225">Per **Fattura di progetto**, immetti **Contesto della fattura di progetto**.</span><span class="sxs-lookup"><span data-stu-id="559ab-225">For **Project invoice**, enter **Project invoice context**.</span></span>

4. <span data-ttu-id="559ab-226">Seleziona **Tipi di risposta** per configurare i tipi di risposta che possono essere restituiti dalla fatturazione elettronica e inclusi in un giornale di registrazione fatture cliente o in una fattura di progetto.</span><span class="sxs-lookup"><span data-stu-id="559ab-226">Select **Response types** to configure the response types that can be returned from Electronic invoicing and included in a customer invoice journal or project invoice.</span></span>
5. <span data-ttu-id="559ab-227">Seleziona **Nuovo**, quindi nel campo **Tipo di risposta**, seleziona **Risposta**.</span><span class="sxs-lookup"><span data-stu-id="559ab-227">Select **New**, and then, in the **Response type** field, select **Response**.</span></span>
6. <span data-ttu-id="559ab-228">Nel campo **Stato invio**, seleziona **In sospeso**.</span><span class="sxs-lookup"><span data-stu-id="559ab-228">In the **Submission status** field, select **Pending**.</span></span>
7. <span data-ttu-id="559ab-229">Nel campo **Mapping modello**, seleziona **Formato di importazione dei messaggi di risposta: mapping del modello dal messaggio di risposta**.</span><span class="sxs-lookup"><span data-stu-id="559ab-229">In the **Model mapping** field, select **Response message import format – Model mapping from response message**.</span></span>
8. <span data-ttu-id="559ab-230">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="559ab-230">Select **Save**.</span></span>
9. <span data-ttu-id="559ab-231">Seleziona **Nuovo**, quindi nel campo **Tipo di risposta**, seleziona **ResponseData**.</span><span class="sxs-lookup"><span data-stu-id="559ab-231">Select **New**, and then, in the **Response type** field, select **ResponseData**.</span></span>
10. <span data-ttu-id="559ab-232">Nel campo **Stato invio**, seleziona **In sospeso**.</span><span class="sxs-lookup"><span data-stu-id="559ab-232">In the **Submission status** field, select **Pending**.</span></span>
11. <span data-ttu-id="559ab-233">Nel campo **Mapping modello**, seleziona **Formato di importazione dei dati di risposta CFDI (dettagli) - Importazione dei dati di risposta**.</span><span class="sxs-lookup"><span data-stu-id="559ab-233">In the **Model mapping** field, select **CFDI response data import format (details) – Response data import**.</span></span>
12. <span data-ttu-id="559ab-234">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="559ab-234">Select **Save**.</span></span>

## <a name="process-electronic-invoices-in-finance"></a><span data-ttu-id="559ab-235">Elaborazione di fatture elettroniche in Finance</span><span class="sxs-lookup"><span data-stu-id="559ab-235">Process electronic invoices in Finance</span></span> 

<span data-ttu-id="559ab-236">Durante l'elaborazione delle fatture CFDI in Finance tramite la fatturazione elettronica, è possibile eseguire le seguenti attività:</span><span class="sxs-lookup"><span data-stu-id="559ab-236">During the processing of CFDI invoices in Finance through Electronic invoicing, you can perform the following tasks:</span></span>

- <span data-ttu-id="559ab-237">Inviare le fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-237">Submit CFDI invoices.</span></span>
- <span data-ttu-id="559ab-238">Visualizzare i log di esecuzione dell'invio.</span><span class="sxs-lookup"><span data-stu-id="559ab-238">View the submission execution logs.</span></span>
- <span data-ttu-id="559ab-239">Inviare l'annullamento di una fattura CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-239">Submit the cancellation of a CFDI invoice.</span></span>

### <a name="submit-cfdi-invoices"></a><span data-ttu-id="559ab-240">Inviare le fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-240">Submit CFDI invoices</span></span>

<span data-ttu-id="559ab-241">Dopo aver attivato la funzionalità **Integrazione della fatturazione elettronica configurabile**, il processo **Esporta/Importa fattura elettronica** (**Contabilità clienti \>Fatture \> Fatture elettroniche**) per l'invio di fatture CFDI non possono più essere utilizzati.</span><span class="sxs-lookup"><span data-stu-id="559ab-241">After you turn on the **Configurable Electronic invoicing integration** feature, the **Export/Import electronic invoice** process (**Accounts receivable \> Invoices \> E-invoices**) for submitting CFDI invoices can no longer be used.</span></span> <span data-ttu-id="559ab-242">È sostituito da un nuovo processo denominato **Invia documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-242">It's replaced by a new process that is named **Submit electronic documents**.</span></span>

> [!NOTE]
> <span data-ttu-id="559ab-243">Prima di utilizzare il nuovo processo **Invia documenti elettronici**, verifica che la configurazione obbligatoria per le fatture elettroniche messicane sia stata completata.</span><span class="sxs-lookup"><span data-stu-id="559ab-243">Before you use the new **Submit electronic documents** process, verify that the setup that is required for Mexican e-invoices was completed.</span></span> <span data-ttu-id="559ab-244">Per altre informazioni, vedi [Versione layout CFDI 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span><span class="sxs-lookup"><span data-stu-id="559ab-244">For more information, see [CFDI layout version 3.3](https://docs.microsoft.com/dynamics365/finance/localizations/latam-mex-cfdi-3-3).</span></span>

1. <span data-ttu-id="559ab-245">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Invia documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-245">Go to **Organization administration \> Periodic \> Electronic documents \> Submit electronic documents**.</span></span>
2. <span data-ttu-id="559ab-246">Per il primo invio di qualsiasi documento, imposta sempre l'opzione **Invia di nuovo i documenti** su **No**.</span><span class="sxs-lookup"><span data-stu-id="559ab-246">For the first submission of any document, always set the **Resubmit documents** option to **No**.</span></span> <span data-ttu-id="559ab-247">Se devi inviare nuovamente un documento tramite il servizio, imposta questa opzione su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="559ab-247">If you must resubmit a document through the service, set this option to **Yes**.</span></span>
3. <span data-ttu-id="559ab-248">Nella Scheda dettaglio **Record da includere**, seleziona **Filtra** per aprire la finestra di dialogo **Richiesta** in cui è possibile creare una query per selezionare i documenti da inviare.</span><span class="sxs-lookup"><span data-stu-id="559ab-248">On the **Records to include** FastTab, select **Filter** to open the **Inquiry** dialog box, where you can build a query to select documents for submission.</span></span>

![Invio di un documento CFDI](media/e-Invoicing-services-get-started-MEX-Submit-CFDI-document.png)

> [!NOTE]
> <span data-ttu-id="559ab-250">Durante il tuo primo tentativo di inviare un documento tramite il servizio, ti verrà chiesto di confermare la connessione con la fatturazione elettronica.</span><span class="sxs-lookup"><span data-stu-id="559ab-250">During your first attempt to submit a document through the service, you will be prompted to confirm the connection with Electronic invoicing.</span></span> <span data-ttu-id="559ab-251">Seleziona **Fai clic qui per connetterti al servizio di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-251">Select **Click here to connect to Electronic Document Submission Service**.</span></span>

### <a name="view-submission-logs"></a><span data-ttu-id="559ab-252">Visualizzare i registri di invio</span><span class="sxs-lookup"><span data-stu-id="559ab-252">View submission logs</span></span>

<span data-ttu-id="559ab-253">È possibile visualizzare i registri di invio per tutti i documenti inviati o per un solo documento inviato.</span><span class="sxs-lookup"><span data-stu-id="559ab-253">You can view the submission logs for all submitted documents or for just one submitted document.</span></span>

#### <a name="view-all-submission-logs"></a><span data-ttu-id="559ab-254">Visualizzare tutti i registri di invio</span><span class="sxs-lookup"><span data-stu-id="559ab-254">View all submission logs</span></span>

<span data-ttu-id="559ab-255">Dopo aver attivato la funzionalità **Integrazione della fatturazione elettronica configurabile**, è disponibile una nuova pagina che consente di completare il processo di invio del documento.</span><span class="sxs-lookup"><span data-stu-id="559ab-255">After you turn on the **Configurable Electronic invoicing integration** feature, a new page is available that lets you follow up on the document submission process.</span></span> <span data-ttu-id="559ab-256">È possibile utilizzare questa pagina per visualizzare i registri di invio per tutti i documenti inviati.</span><span class="sxs-lookup"><span data-stu-id="559ab-256">You can use this page to view the submission logs for all submitted documents.</span></span>

1. <span data-ttu-id="559ab-257">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-257">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="559ab-258">Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** per filtrare i documenti elettronici obbligatori.</span><span class="sxs-lookup"><span data-stu-id="559ab-258">In the **Document type** field, select **Customer invoice journal** to filter for the required electronic documents.</span></span>

    ![Selezione di un tipo di documento per visualizzare i registri di invio](media/e-Invoicing-services-get-started-MEX-Select-document-type-for-viewing-submission-log.png)

3. <span data-ttu-id="559ab-260">Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.</span><span class="sxs-lookup"><span data-stu-id="559ab-260">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visualizzazione dei dettagli del registro di invio](media/e-Invoicing-services-get-started-MEX-View-submission-log-details.png)

<span data-ttu-id="559ab-262">Le informazioni nei registri di invio sono suddivise in tre Schede dettaglio:</span><span class="sxs-lookup"><span data-stu-id="559ab-262">The information in the submission logs is divided among three FastTabs:</span></span>

- <span data-ttu-id="559ab-263">**Azioni di elaborazione**: questa Scheda dettaglio mostra il registro di esecuzione delle azioni configurate nella versione della funzionalità configurata in RCS.</span><span class="sxs-lookup"><span data-stu-id="559ab-263">**Processing actions** – This FastTab shows the execution log for the actions that are configured in the feature version that was set up in RCS.</span></span> <span data-ttu-id="559ab-264">La colonna **Stato** mostra se l'azione è stata eseguita correttamente.</span><span class="sxs-lookup"><span data-stu-id="559ab-264">The **Status** column shows whether the action was successfully run.</span></span>
- <span data-ttu-id="559ab-265">**File di azione**: questa Scheda dettaglio mostra i file intermedi che sono stati generati durante l'esecuzione delle azioni.</span><span class="sxs-lookup"><span data-stu-id="559ab-265">**Action files** – This FastTab shows the intermediate files that were generated during execution of the actions.</span></span> <span data-ttu-id="559ab-266">Puoi selezionare **Visualizza** per scaricare e visualizzare il file.</span><span class="sxs-lookup"><span data-stu-id="559ab-266">You can select **View** to download and view the file.</span></span>
- <span data-ttu-id="559ab-267">**Registro azioni di elaborazione**: questa scheda dettaglio mostra i risultati della comunicazione tra la fatturazione elettronica e il servizio Web di destinazione.</span><span class="sxs-lookup"><span data-stu-id="559ab-267">**Processing action log** – This FastTab shows the results of the communication between Electronic invoicing and the target web service.</span></span> <span data-ttu-id="559ab-268">Mostra anche ciò che è stato restituito dall'elaborazione del servizio Web.</span><span class="sxs-lookup"><span data-stu-id="559ab-268">It also shows what was returned by the processing from the web service.</span></span> <span data-ttu-id="559ab-269">La colonna **Codice di errore** mostra il codice di reso che è stato restituito dal servizio Web di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="559ab-269">The **Error code** column shows the return code that was returned by the authorization web service.</span></span>

<span data-ttu-id="559ab-270">Quando la fattura CFDI inviata viene autorizzata, il suo stato viene aggiornato su **Approvata**.</span><span class="sxs-lookup"><span data-stu-id="559ab-270">When the submitted CFDI invoice is authorized, its status is updated to **Approved**.</span></span>

#### <a name="view-submission-logs-from-cfdi-invoices"></a><span data-ttu-id="559ab-271">Visualizzare i registri di invio dalle fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-271">View submission logs from CFDI invoices</span></span>

<span data-ttu-id="559ab-272">Dopo aver attivato la funzionalità **Integrazione della fatturazione elettronica configurabile** puoi anche visualizzare i registri di invio dalle fatture CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-272">After you turn on the **ConfigurableElectronic invoicing integration** feature, you can also view the submission logs from CFDI invoices.</span></span>

1. <span data-ttu-id="559ab-273">Passa a **Contabilità clienti \> Richieste di informazioni e report \> CFDI (fatture elettroniche)**.</span><span class="sxs-lookup"><span data-stu-id="559ab-273">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="559ab-274">Seleziona una fattura CFDI inviata dopo l'attivazione della funzionalità **Integrazione della fatturazione elettronica configurabile**.</span><span class="sxs-lookup"><span data-stu-id="559ab-274">Select a CFDI invoice that was submitted after the **Configurable Electronic invoicing integration** feature was turned on.</span></span>
3. <span data-ttu-id="559ab-275">Nel riquadro azioni, nella scheda **Cronologia**, seleziona **Registro documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-275">On the Action Pane, on the **History** tab, select **Electronic document log**.</span></span>

![Visualizzazione dei registri di invio dalle fatture CFDI](media/e-Invoicing-services-get-started-MEX-View-submission-log-from-CFDI-invoice.png)

> [!NOTE]
> <span data-ttu-id="559ab-277">Per le fatture CFDI presentate prima dell'attivazione della funzionalità **Integrazione della fatturazione elettronica configurabile**, è disponibile il pulsante **Cronologia**.</span><span class="sxs-lookup"><span data-stu-id="559ab-277">For CFDI invoices that were submitted before the **Configurable Electronic invoicing integration** feature was turned on, the **History** button is available.</span></span> <span data-ttu-id="559ab-278">Il pulsante **Cronologia** non è disponibile per le fatture CFDI inviate dopo l'attivazione della funzionalità **Integrazione della fatturazione elettronica configurabile**.</span><span class="sxs-lookup"><span data-stu-id="559ab-278">The **History** button isn't available for CFDI invoices that were submitted after the **Configurable Electronic invoicing integration** feature was turned on.</span></span>

### <a name="submit-cancellation-of-cfdi-invoices"></a><span data-ttu-id="559ab-279">Inviare l'annullamento delle fatture CFDI</span><span class="sxs-lookup"><span data-stu-id="559ab-279">Submit cancellation of CFDI invoices</span></span>

<span data-ttu-id="559ab-280">Dopo aver attivato la funzionalità **Integrazione della fatturazione elettronica configurabile**, il vecchio processo per l'annullamento delle fatture CFDI non può più essere utilizzato.</span><span class="sxs-lookup"><span data-stu-id="559ab-280">After you turn on the **Configurable Electronic invoicing integration** feature, the old process for canceling CFDI invoices can no longer be used.</span></span> <span data-ttu-id="559ab-281">Viene sostituito da un nuovo processo di annullamento incorporato nella pagina **Registro di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-281">It's replaced by a new cancellation process that is embedded on the **Electronic document submission log** page.</span></span>

1. <span data-ttu-id="559ab-282">Passa a **Contabilità clienti \> Richieste di informazioni e report \> CFDI (fatture elettroniche)**.</span><span class="sxs-lookup"><span data-stu-id="559ab-282">Go to **Accounts receivable \> Inquiries and reports \> CFDI (electronic invoices)**.</span></span>
2. <span data-ttu-id="559ab-283">Se la fattura CFDI ha uno stato **Approvato**, seleziona **Funzioni \> Annulla CFDI**.</span><span class="sxs-lookup"><span data-stu-id="559ab-283">If the CFDI invoice has a status of **Approved**, select **Functions \> Cancel CFDI**.</span></span>
3. <span data-ttu-id="559ab-284">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-284">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
4. <span data-ttu-id="559ab-285">Seleziona la fattura CFDI, quindi seleziona **Funzioni \> Invia comunicazioni correlate**.</span><span class="sxs-lookup"><span data-stu-id="559ab-285">Select the CFDI invoice, and then select **Functions \> Send related submissions**.</span></span>
5. <span data-ttu-id="559ab-286">Immetti una descrizione per l'invio correlato, quindi seleziona **OK**.</span><span class="sxs-lookup"><span data-stu-id="559ab-286">Enter a description for the related submission, and then select **OK**.</span></span>

#### <a name="view-cancellation-submission-logs"></a><span data-ttu-id="559ab-287">Visualizzare tutti i registri di annullamento</span><span class="sxs-lookup"><span data-stu-id="559ab-287">View cancellation submission logs</span></span>

1. <span data-ttu-id="559ab-288">Vai a **Amministrazione organizzazione \> Periodico \> Documenti elettronici \> Registro di invio documenti elettronici**.</span><span class="sxs-lookup"><span data-stu-id="559ab-288">Go to **Organization administration \> Periodic \> Electronic documents \> Electronic document submission log**.</span></span>
2. <span data-ttu-id="559ab-289">Nel campo **Tipo di documento**, seleziona **Giornale di registrazione fatture cliente** per filtrare solo i documenti del giornale di registrazione delle fatture cliente.</span><span class="sxs-lookup"><span data-stu-id="559ab-289">In the **Document type** field, select **Customer invoice journal** to filter for customer invoice journal documents only.</span></span>
3. <span data-ttu-id="559ab-290">Seleziona la fattura CFDI e quindi, nel riquadro azioni, seleziona **Richieste di informazioni \> Invio correlato**.</span><span class="sxs-lookup"><span data-stu-id="559ab-290">Select the CFDI invoice, and then, on the Action Pane, select **Inquiries \> Related submission**.</span></span>

    <span data-ttu-id="559ab-291">La pagina **Invii correlati** mostra tutti gli invii correlati e il loro stato di invio per una determinata fattura CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-291">The **Related submissions** page shows all related submissions, and their submission status, for a given CFDI invoice.</span></span> <span data-ttu-id="559ab-292">Nella figura seguente, la prima riga rappresenta l'invio che ha richiesto l'approvazione della fattura CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-292">In the following illustration, the first line represents the submission that requested approval of the CFDI invoice.</span></span> <span data-ttu-id="559ab-293">La seconda riga rappresenta l'invio che ha annullato la fattura CFDI.</span><span class="sxs-lookup"><span data-stu-id="559ab-293">The second line represents the submission that canceled that CFDI invoice.</span></span>

    ![Visualizzazione di tutti i registri di annullamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log.png)

4. <span data-ttu-id="559ab-295">Nel riquadro azioni seleziona **Richieste \> Dettagli invio** per visualizzare i dettagli dei log di esecuzione dell'invio.</span><span class="sxs-lookup"><span data-stu-id="559ab-295">On the Action Pane, select **Inquiries \> Submission details** to view the details of the submission execution logs.</span></span>

    ![Visualizzazione dei dettaglio del registro di invio annullamento](media/e-Invoicing-services-get-started-MEX-View-cancellation-submission-log-details.png)

## <a name="privacy-notice"></a><span data-ttu-id="559ab-297">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="559ab-297">Privacy notice</span></span>
<span data-ttu-id="559ab-298">L'abilitazione della funzionalità **CFDI - Fattura elettronica messicana (MX)** potrebbe richiedere l'invio di dati limitati, che includono l'ID di registrazione fiscale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="559ab-298">Enabling the **CFDI Mexican electronic invoice (MX)** feature may require sending limited data, which includes the organization tax registration ID.</span></span> <span data-ttu-id="559ab-299">Questo verrà trasmesso ad agenzie di terze parti autorizzate dall'autorità fiscale allo scopo di inviare fatture elettroniche a questa autorità fiscale nel formato predefinito richiesto per l'integrazione con il servizio Web del governo.</span><span class="sxs-lookup"><span data-stu-id="559ab-299">This will be transmitted to third-party agencies authorized by the tax authority for purposes of sending electronic invoices to this tax authority in the predefined format required for integration with the government’s web service.</span></span> <span data-ttu-id="559ab-300">Un amministratore può abilitare e disabilitare la funzionalità **CFDI - Fattura elettronica messicana (MX)** selezionando **Amministrazione organizzazione \> Impostazione \> Parametri del documento elettronico**.</span><span class="sxs-lookup"><span data-stu-id="559ab-300">An administrator can enable and disable the **CFDI Mexican electronic invoice (MX)** feature by navigating to **Organization administration \> Setup \> Electronic document parameters**.</span></span> <span data-ttu-id="559ab-301">Selezionare la scheda **Funzionalità**, selezionare le righe contenenti la funzionalità **CFDI - Fattura elettronica messicana (MX)**, quindi effettuare la selezione appropriata.</span><span class="sxs-lookup"><span data-stu-id="559ab-301">Select the **Features** tab, select the rows containing the **CFDI Mexican electronic invoice (MX)** feature, and then make the appropriate selection.</span></span> <span data-ttu-id="559ab-302">I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132).</span><span class="sxs-lookup"><span data-stu-id="559ab-302">Data imported from these external systems into this Dynamics 365 online service are subject to our [privacy statement](https://go.microsoft.com/fwlink/?LinkId=512132).</span></span> <span data-ttu-id="559ab-303">Consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.</span><span class="sxs-lookup"><span data-stu-id="559ab-303">Consult the Privacy notice sections in country-specific feature documentation for more information.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="559ab-304">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="559ab-304">Additional resources</span></span>

- [<span data-ttu-id="559ab-305">Panoramica della fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-305">Electronic invoicing overview</span></span>](e-invoicing-service-overview.md)
- [<span data-ttu-id="559ab-306">Introduzione alla fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-306">Get started with Electronic invoicing</span></span>](e-invoicing-get-started.md)
- [<span data-ttu-id="559ab-307">Impostare la fatturazione elettronica</span><span class="sxs-lookup"><span data-stu-id="559ab-307">Set up Electronic invoicing</span></span>](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
