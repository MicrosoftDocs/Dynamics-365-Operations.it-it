---
title: Importare versioni aggiornate delle configurazioni ER
description: In questo argomento viene descritto come importare le versioni aggiornate delle configurazioni per la creazione di report elettronici (ER) dall'archivio globale del servizio di configurazione.
author: NickSelin
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionImport, ERWorkspace, ERSolutionRepositoryTable
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 105843
ms.assetid: dc44dea2-22ce-401e-98b9-d289e0e2825b
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.5
ms.openlocfilehash: 724048991fc8864ef72a5155af66b9c709f4b875
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893958"
---
# <a name="import-updated-versions-of-er-configurations"></a><span data-ttu-id="6e8d1-103">Importare versioni aggiornate delle configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="6e8d1-103">Import updated versions of ER configurations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6e8d1-104">Gli [archivi](general-electronic-reporting.md#Repository) per la creazione di report elettronici sono usati per condividere le [configurazioni ER](general-electronic-reporting.md#Configuration).</span><span class="sxs-lookup"><span data-stu-id="6e8d1-104">Electronic reporting (ER) [repositories](general-electronic-reporting.md#Repository) are used to share [ER configurations](general-electronic-reporting.md#Configuration).</span></span> <span data-ttu-id="6e8d1-105">Puoi [importare](download-electronic-reporting-configuration-lcs.md) configurazioni ER da diversi archivi nell'istanza di Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-105">You can [import](download-electronic-reporting-configuration-lcs.md) ER configurations from different repositories into your instance of Microsoft Dynamics 365 Finance.</span></span> <span data-ttu-id="6e8d1-106">Quando importi le configurazioni ER, i [provider di configurazione](general-electronic-reporting.md#Provider) possono pubblicare nuove [versioni](general-electronic-reporting.md#component-versioning) di archivi in modo che possano essere condivisi.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-106">When you import ER configurations, [configuration providers](general-electronic-reporting.md#Provider) can publish new [versions](general-electronic-reporting.md#component-versioning) repositories so that they can be shared.</span></span>

<span data-ttu-id="6e8d1-107">In questo argomento viene descritto come importare le versioni aggiornate delle configurazioni ER dall'archivio globale del servizio di configurazione.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-107">This topic explains how to import updated versions of ER configurations from the Global repository of the Configuration service.</span></span> <span data-ttu-id="6e8d1-108">Per ulteriori informazioni, vedere [Microsoft Dynamics 365 for Finance and Operations - Regulatory services, Servizio di configurazione](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span><span class="sxs-lookup"><span data-stu-id="6e8d1-108">For more information, see [Microsoft Dynamics 365 for Finance and Operations - Regulatory Services, Configuration service](/business-applications-release-notes/october18/dynamics365-finance-operations/regulatory-service-configuration).</span></span>

## <a name="review-the-available-updated-versions"></a><span data-ttu-id="6e8d1-109">Rivedere le versioni aggiornate disponibili</span><span class="sxs-lookup"><span data-stu-id="6e8d1-109">Review the available updated versions</span></span>

1. <span data-ttu-id="6e8d1-110">Accedi a Finance utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="6e8d1-110">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="6e8d1-111">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e8d1-111">Electronic reporting developer</span></span>
    - <span data-ttu-id="6e8d1-112">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e8d1-112">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6e8d1-113">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="6e8d1-113">System administrator</span></span>

2. <span data-ttu-id="6e8d1-114">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-114">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="6e8d1-115">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Importa aggiornamenti versioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-115">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>

    ![Pagina configurazioni Localizzazione](./media/er-download-updated-versions-global-repo1.png)

4. <span data-ttu-id="6e8d1-117">Nella finestra di dialogo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, nel campo **Modalità di esecuzione**, seleziona **Mostra solo gli aggiornamenti disponibili**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-117">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Only show available updates**.</span></span> <span data-ttu-id="6e8d1-118">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-118">Then select **OK**.</span></span> 

    ![Campo della modalità di esecuzione impostato su Mostra solo gli aggiornamenti disponibili](./media/er-download-updated-versions-global-repo2.png)

5. <span data-ttu-id="6e8d1-120">Rivedi i messaggi che ricevi.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-120">Review the messages that you receive.</span></span> <span data-ttu-id="6e8d1-121">Questi messaggi forniscono le seguenti informazioni sulle configurazioni ER nell'istanza di Finance corrente e su come si confrontano con il contenuto dell'archivio globale:</span><span class="sxs-lookup"><span data-stu-id="6e8d1-121">These messages provide the following information about the ER configurations in the current Finance instance and how they compare to the content of the Global repository:</span></span>

    - <span data-ttu-id="6e8d1-122">Il numero totale di configurazioni ER</span><span class="sxs-lookup"><span data-stu-id="6e8d1-122">The total number of ER configurations</span></span>
    - <span data-ttu-id="6e8d1-123">Configurazioni ER che non sono presenti nell'archivio globale</span><span class="sxs-lookup"><span data-stu-id="6e8d1-123">ER configurations that aren't present in the Global repository</span></span>
    - <span data-ttu-id="6e8d1-124">Configurazioni ER per le quali l'ultima versione è già disponibile nell'istanza Finance corrente (per visualizzare l'elenco completo di queste configurazioni ER, seleziona il collegamento **Dettagli messaggio**.)</span><span class="sxs-lookup"><span data-stu-id="6e8d1-124">ER configurations for which the latest version is already available in the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Dettagli messaggio e messaggio "Le ultime versioni delle seguenti configurazioni sono già importate"](./media/er-download-updated-versions-global-repo3.png)

    - <span data-ttu-id="6e8d1-126">Configurazioni ER per le quali l'ultima versione è già disponibile nell'archivio globale e che possono essere importate nell'istanza Finance corrente (per visualizzare l'elenco completo di queste configurazioni ER, seleziona il collegamento **Dettagli messaggio**.)</span><span class="sxs-lookup"><span data-stu-id="6e8d1-126">ER configurations for which the latest version is available in the Global repository and can be imported into the current Finance instance (To view the full list of these ER configurations, select the **Message details** link.)</span></span>

        ![Messaggio "Aggiornamenti disponibili" e dettagli del messaggio](./media/er-download-updated-versions-global-repo4.png)

## <a name="import-available-updated-versions"></a><span data-ttu-id="6e8d1-128">Importare le versioni aggiornate disponibili</span><span class="sxs-lookup"><span data-stu-id="6e8d1-128">Import available updated versions</span></span>

1. <span data-ttu-id="6e8d1-129">Accedi a Finance utilizzando uno dei seguenti ruoli:</span><span class="sxs-lookup"><span data-stu-id="6e8d1-129">Sign in to Finance by using one of the following roles:</span></span>

    - <span data-ttu-id="6e8d1-130">Sviluppatore per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e8d1-130">Electronic reporting developer</span></span>
    - <span data-ttu-id="6e8d1-131">Consulente funzionale per la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e8d1-131">Electronic reporting functional consultant</span></span>
    - <span data-ttu-id="6e8d1-132">Amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="6e8d1-132">System administrator</span></span>

2. <span data-ttu-id="6e8d1-133">Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-133">Go to **Organization administration** \> **Workspaces** \> **Electronic reporting**.</span></span>
3. <span data-ttu-id="6e8d1-134">Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Importa aggiornamenti versioni di configurazione**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-134">On the **Localization configurations** page, in the **Related links** section, select **Import configurations versions updates**.</span></span>
4. <span data-ttu-id="6e8d1-135">Nella finestra di dialogo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, nel campo **Modalità di esecuzione**, seleziona **Importa gli ultimi aggiornamenti** per importare le ultime versioni delle configurazioni ER dall'archivio globale nell'istanza Finance corrente.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-135">In the **Import electronic reporting configurations versions updates** dialog box, in the **Run mode** field, select **Import latest updates** to import the latest versions of ER configurations from the Global repository into the current Finance instance.</span></span>
5. <span data-ttu-id="6e8d1-136">Per pianificare un processo batch per l'importazione, nella Scheda dettaglio **Esegui in background**, imposta l'opzione **Elaborazione in batch** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-136">To schedule a batch job for the import, on the **Run in the background** FastTab, set the **Batch processing** option to **Yes**.</span></span> <span data-ttu-id="6e8d1-137">Se vuoi ripetere periodicamente l'importazione, configura la ricorrenza richiesta.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-137">If you want to repeat the import periodically, configure the required recurrence.</span></span>

    ![Campo della modalità di esecuzione impostato su Importa gli ultimi aggiornamenti](./media/er-download-updated-versions-global-repo5.png)

6. <span data-ttu-id="6e8d1-139">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-139">Select **OK**.</span></span>
7. <span data-ttu-id="6e8d1-140">Per sapere quali versioni di configurazione sono state importate, segui uno di questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="6e8d1-140">To learn what configuration versions have been imported, follow one of these steps:</span></span>

    - <span data-ttu-id="6e8d1-141">Se esegui l'importazione in modo interattivo anziché utilizzare un processo batch, rivedi i messaggi ricevuti.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-141">If you run the import interactively instead of using a batch job, review the messages that you receive.</span></span>

        ![Messaggi ricevuti durante un'esecuzione di importazione interattiva](./media/er-download-updated-versions-global-repo6.png)

    - <span data-ttu-id="6e8d1-143">Se esegui l'importazione in modalità batch, attieniti alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="6e8d1-143">If you run the import in batch mode, follow these steps:</span></span>

        1. <span data-ttu-id="6e8d1-144">Vai a **Elementi comuni** \> **Richieste di informazioni** \> **Processi batch** \> **Processi batch personali**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-144">Go to **Common** \> **Inquiries** \> **Batch jobs** \> **My batch jobs**.</span></span>
        2. <span data-ttu-id="6e8d1-145">Trova e seleziona il processo **Importa aggiornamenti versioni delle configurazioni per la creazione di report elettronici**, quindi, nel riquadro azioni, nella scheda **Processo in batch**, seleziona **Cronologia dei processi batch** per visualizzare la cronologia dei processi.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-145">Find and select the **Import electronic reporting configurations versions updates** job, and then, on the Action Pane, on the **Batch job** tab, select **Batch job history** to view the job history.</span></span>
        3. <span data-ttu-id="6e8d1-146">Nella pagina **Cronologia dei processi batch**, seleziona **Registro**.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-146">On the **Batch job history** page, select **Log**.</span></span> <span data-ttu-id="6e8d1-147">Quindi, nel messaggio che ricevi, seleziona il collegamento **Dettagli messaggio** per visualizzare il registro del processo.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-147">Then, in the message that you receive, select the **Message details** link to view the job log.</span></span>

        ![Registro del processo](./media/er-download-updated-versions-global-repo7.png)

> [!IMPORTANT]
> <span data-ttu-id="6e8d1-149">Non è consigliabile pianificare un processo batch ricorrente per importare le versioni aggiornate delle configurazioni ER direttamente dall'archivio globale in un ambiente di produzione, poiché le versioni importate saranno immediatamente disponibili per l'uso.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-149">We don't recommend that you schedule a recurring batch job to import updated versions of ER configurations directly from the Global repository into a production environment, because the imported versions will immediately be available for use.</span></span> <span data-ttu-id="6e8d1-150">Utilizza invece questo approccio per distribuire le versioni delle configurazioni ER in un ambiente sandbox.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-150">Instead, use this approach to deploy versions of ER configurations to a sandbox environment.</span></span> <span data-ttu-id="6e8d1-151">Possono quindi essere valutate nell'ambiente sandbox prima di essere distribuite in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="6e8d1-151">They can then be evaluated in the sandbox environment before they are deployed to a production environment.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6e8d1-152">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6e8d1-152">Additional resources</span></span>

- [<span data-ttu-id="6e8d1-153">Panoramica dei report elettronici</span><span class="sxs-lookup"><span data-stu-id="6e8d1-153">Electronic reporting (ER) overview</span></span>](general-electronic-reporting.md)
- [<span data-ttu-id="6e8d1-154">Scaricare configurazioni ER dall'archivio globale del servizio di configurazione</span><span class="sxs-lookup"><span data-stu-id="6e8d1-154">Download ER configurations from the Global repository of Configuration service</span></span>](er-download-configurations-global-repo.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]