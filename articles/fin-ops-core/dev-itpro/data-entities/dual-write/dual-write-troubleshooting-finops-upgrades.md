---
title: Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations
description: Questo argomento fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c76b35ed3af766f42484a118a4a0407d969b5240
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683601"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="a99bd-103">Risoluzione dei problemi relativi agli aggiornamenti delle app Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a99bd-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="a99bd-104">In questo argomento vengono fornite informazioni sulla risoluzione dei problemi di integrazione della doppia scrittura tra le app Finance and Operations e Dataverse.</span><span class="sxs-lookup"><span data-stu-id="a99bd-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="a99bd-105">In particolare, fornisce informazioni che possono aiutarti a risolvere i problemi relativi agli aggiornamenti delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a99bd-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a99bd-106">Alcuni problemi che questo argomento tratta potrebbero richiedere il ruolo di amministratore di sistema o le credenziali di amministratore del tenant Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="a99bd-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="a99bd-107">La sezione per ogni problema spiega se sono richiesti ruolo o credenziali specifici.</span><span class="sxs-lookup"><span data-stu-id="a99bd-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="a99bd-108">Errori di sincronizzazione del database</span><span class="sxs-lookup"><span data-stu-id="a99bd-108">Database synchronization errors</span></span>

<span data-ttu-id="a99bd-109">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="a99bd-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="a99bd-110">È possibile che venga visualizzato un messaggio di errore simile al seguente esempio quando si tenta di utilizzare l'entità **DualWriteProjectConfiguration** per aggiornare un'app Finance and Operations al Platform update 30.</span><span class="sxs-lookup"><span data-stu-id="a99bd-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="a99bd-111">Per risolvere il problema, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="a99bd-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="a99bd-112">Accedere alla macchina virtuale (VM) per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a99bd-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="a99bd-113">Aprire Visual Studio come amministratore e aprire Application Object Tree (AOT).</span><span class="sxs-lookup"><span data-stu-id="a99bd-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="a99bd-114">Cercare **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="a99bd-115">In AOT, fare clic con il tasto destro su **DualWriteProjectConfiguration** e selezionare **Aggiungi a nuovo progetto**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="a99bd-116">Selezionare **OK** per creare il nuovo progetto con le opzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="a99bd-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="a99bd-117">In Esplora soluzioni, fare clic con il tasto destro su **Proprietà progetto** e impostare **Sincronizza database su build** su **True**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="a99bd-118">Compilare il progetto e verificare che la compilazione abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="a99bd-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="a99bd-119">Nel menu **Dynamics 365**, selezionare **Sincronizza database**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="a99bd-120">Selezionare **Sincronizza** per eseguire una sincronizzazione completa del database.</span><span class="sxs-lookup"><span data-stu-id="a99bd-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="a99bd-121">Una volta che la sincronizzazione completa del database ha esito positivo, rieseguire il passaggio di sincronizzazione del database in Microsoft Dynamics Lifecycle Services (LCS) e utilizzare gli script di aggiornamento manuale come applicabile, in modo da poter procedere con l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="a99bd-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="a99bd-122">Problema di campi di entità mancanti sulle mappe</span><span class="sxs-lookup"><span data-stu-id="a99bd-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="a99bd-123">**Ruolo richiesto per risolvere il problema:** amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="a99bd-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="a99bd-124">Nella pagina **Doppia scrittura** è possibile che venga visualizzato un messaggio di errore simile al seguente esempio:</span><span class="sxs-lookup"><span data-stu-id="a99bd-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="a99bd-125">*Campo di origine mancante \<field name\> nello schema.*</span><span class="sxs-lookup"><span data-stu-id="a99bd-125">*Missing source field \<field name\> in the schema.*</span></span>

![Esempio del messaggio di errore del campo di origine mancante](media/error_missing_field.png)

<span data-ttu-id="a99bd-127">Per risolvere il problema, seguire innanzitutto questi passaggi per assicurarsi che i campi siano nell'entità.</span><span class="sxs-lookup"><span data-stu-id="a99bd-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="a99bd-128">Accedere alla macchina virtuale per l'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a99bd-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="a99bd-129">Andare a **Aree di lavoro \> Gestione dei dati**, selezionare il riquadro **Parametri framework** e quindi nella scheda **Impostazioni tabella**, selezionare **Aggiorna elenco entità** per aggiornare le tabelle.</span><span class="sxs-lookup"><span data-stu-id="a99bd-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Table settings** tab, select **Refresh entity list** to refresh the tables.</span></span>
3. <span data-ttu-id="a99bd-130">Andare a **Aree di lavoro \> Gestione dei dati**, selezionare la scheda **Tabelle dati** e assicurarsi che l'entità sia elencata.</span><span class="sxs-lookup"><span data-stu-id="a99bd-130">Go to **Workspaces \> Data management**, select the **Data tables** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="a99bd-131">Se l'entità non è elencata, accedere alla macchina virtuale per l'app Finance and Operations e assicurarsi che l'entità sia disponibile.</span><span class="sxs-lookup"><span data-stu-id="a99bd-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="a99bd-132">Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a99bd-132">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="a99bd-133">Selezionare **Aggiorna elenco entità** per completare automaticamente i campi nei mapping della tabella.</span><span class="sxs-lookup"><span data-stu-id="a99bd-133">Select **Refresh entity list** to automatically fill the fields in the table mappings.</span></span>

<span data-ttu-id="a99bd-134">Se il problema persiste, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="a99bd-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a99bd-135">Questi passaggi guidano l'utente attraverso il processo di eliminazione di un'entità e quindi l'aggiunta di una nuova.</span><span class="sxs-lookup"><span data-stu-id="a99bd-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="a99bd-136">Per evitare problemi, assicurarsi di seguire esattamente i passaggi.</span><span class="sxs-lookup"><span data-stu-id="a99bd-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="a99bd-137">Nell'app Finance and Operations, andare a **Aree di lavoro \> Gestione dei dati** e selezionare il riquadro **Tabelle dati**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data tables** tile.</span></span>
2. <span data-ttu-id="a99bd-138">Trovare l'entità in cui manca l'attributo.</span><span class="sxs-lookup"><span data-stu-id="a99bd-138">Find the entity that is missing the attribute.</span></span> <span data-ttu-id="a99bd-139">Fare clic su **Modifica mapping di destinazione** nella barra degli strumenti.</span><span class="sxs-lookup"><span data-stu-id="a99bd-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="a99bd-140">Nel riquadro **Mappa gestione temporanea a destinazione**, fare clic si **Genera mapping**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="a99bd-141">Aprire la pagina **Mapping della tabella** dalla pagina **Doppia scrittura** nell'app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a99bd-141">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="a99bd-142">Se l'attributo non viene popolato automaticamente sulla mappa, aggiungerlo manualmente facendo clic sul pulsante **Aggiungi attributo** e quindi su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="a99bd-143">Selezionare la mappa e fare clic su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="a99bd-143">Select the map and click **Run**.</span></span>
