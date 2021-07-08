---
title: Introduzione alla Contabilità inventario globale
description: Questo argomento descrive come iniziare a usare la Contabilità inventario globale.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 59f9db309312bbbc88b4fa47c12c4c02f09e7c6d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301700"
---
# <a name="get-started-with-global-inventory-accounting"></a><span data-ttu-id="b2916-103">Introduzione alla Contabilità inventario globale</span><span class="sxs-lookup"><span data-stu-id="b2916-103">Get started with Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="b2916-104">Contabilità inventario globale ti consente di eseguire più contabilità di inventario nei libri contabili di Contabilità inventario globale impostati.</span><span class="sxs-lookup"><span data-stu-id="b2916-104">Global Inventory Accounting lets you do multiple inventory accountings in the Global Inventory Accounting ledgers that you've set up.</span></span> <span data-ttu-id="b2916-105">È necessario associare ogni libro contabile di Contabilità inventario globale a una *convenzione*.</span><span class="sxs-lookup"><span data-stu-id="b2916-105">You must associate each Global Inventory Accounting ledger with a *convention*.</span></span> <span data-ttu-id="b2916-106">Una convenzione è la raccolta dei seguenti tipi di principi contabili:</span><span class="sxs-lookup"><span data-stu-id="b2916-106">A convention is a collection of the following types of accounting policies:</span></span>

- <span data-ttu-id="b2916-107">Oggetto di costo</span><span class="sxs-lookup"><span data-stu-id="b2916-107">Cost object</span></span>
- <span data-ttu-id="b2916-108">Base di misura di input</span><span class="sxs-lookup"><span data-stu-id="b2916-108">Input measurement basis</span></span>
- <span data-ttu-id="b2916-109">Presupposto per flussi di costo</span><span class="sxs-lookup"><span data-stu-id="b2916-109">Cost flow assumption</span></span>
- <span data-ttu-id="b2916-110">Elemento di costo</span><span class="sxs-lookup"><span data-stu-id="b2916-110">Cost element</span></span>

> [!NOTE]
> <span data-ttu-id="b2916-111">Anche dopo aver attivato Contabilità inventario globale, è ancora possibile eseguire la contabilità di inventario in Microsoft Dynamics 365 Supply Chain Management, come di consueto.</span><span class="sxs-lookup"><span data-stu-id="b2916-111">Even after you turn on Global Inventory Accounting, you can still do inventory accounting in Microsoft Dynamics 365 Supply Chain Management in the usual way.</span></span>

<span data-ttu-id="b2916-112">Contabilità inventario globale è un componente aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="b2916-112">Global Inventory Accounting is an add-in.</span></span> <span data-ttu-id="b2916-113">Per rendere disponibili le funzionalità, è necessario installarlo da Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="b2916-113">To make its features available, you must install it from Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="b2916-114">È possibile scegliere di valutarlo in un ambiente di test prima di attivarlo per gli ambienti di produzione.</span><span class="sxs-lookup"><span data-stu-id="b2916-114">You can choose to evaluate it in a test environment before you turn it on for production environments.</span></span>

<span data-ttu-id="b2916-115">Contabilità inventario globale attualmente non supporta tutte le funzionalità di gestione dei costi integrate in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b2916-115">Global Inventory Accounting doesn't currently support all the cost management features that are built into Supply Chain Management.</span></span> <span data-ttu-id="b2916-116">Pertanto, è importante valutare se il set di funzionalità attualmente disponibile soddisfa i requisiti.</span><span class="sxs-lookup"><span data-stu-id="b2916-116">Therefore, it's important that you evaluate whether the set of features that is currently available will meet your requirements.</span></span>

## <a name="how-to-get-the-global-inventory-accounting-public-preview"></a><a name="sign-up"></a><span data-ttu-id="b2916-117">Come ottenere l'anteprima pubblica di Contabilità inventario globale</span><span class="sxs-lookup"><span data-stu-id="b2916-117">How to get the Global Inventory Accounting public preview</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2916-118">Per utilizzare Contabilità inventario globale, è necessario disporre di un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox).</span><span class="sxs-lookup"><span data-stu-id="b2916-118">To use Global Inventory Accounting, you must have an LCS-enabled high-availability environment (not a OneBox environment).</span></span> <span data-ttu-id="b2916-119">Inoltre, è necessario eseguire Supply Chain Management versione 10.0.19 o successiva.</span><span class="sxs-lookup"><span data-stu-id="b2916-119">Additionally, you must be running Supply Chain Management version 10.0.19 or later.</span></span>

<span data-ttu-id="b2916-120">Per iscriverti all'anteprima pubblica di Contabilità inventario globale, invia il tuo ID ambiente LCS via e-mail al [Team di Contabilità inventario globale](mailto:GlobalInventoryAccounting@service.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b2916-120">To sign up for the Global Inventory Accounting public preview, send your LCS environment ID by email to the [Global Inventory Accounting team](mailto:GlobalInventoryAccounting@service.microsoft.com).</span></span> <span data-ttu-id="b2916-121">Dopo che sei stato approvato per il programma, il team ti invierà un'e-mail di follow-up che contiene una chiave beta di Contabilità inventario globale e gli endpoint del servizio.</span><span class="sxs-lookup"><span data-stu-id="b2916-121">After you're approved for the program, the team will send you a follow-up email that contains a Global Inventory Accounting beta key and your service endpoints.</span></span> <span data-ttu-id="b2916-122">Dopo aver ricevuto la chiave beta, puoi [installare il componente aggiuntivo](#install).</span><span class="sxs-lookup"><span data-stu-id="b2916-122">After you receive the beta key, you can [install the add-in](#install).</span></span>

## <a name="licensing"></a><span data-ttu-id="b2916-123">Licenze</span><span class="sxs-lookup"><span data-stu-id="b2916-123">Licensing</span></span>

<span data-ttu-id="b2916-124">Contabilità inventario globale è concesso in licenza insieme alle funzionalità standard della contabilità di magazzino disponibili per Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b2916-124">Global Inventory Accounting is licensed together with the standard features of inventory accounting that are available for Supply Chain Management.</span></span> <span data-ttu-id="b2916-125">Non è necessario acquistare una licenza aggiuntiva per utilizzare Contabilità inventario globale.</span><span class="sxs-lookup"><span data-stu-id="b2916-125">You don't have to purchase an additional license to use Global Inventory Accounting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2916-126">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b2916-126">Prerequisites</span></span>

### <a name="set-up-microsoft-power-platform-integration"></a><span data-ttu-id="b2916-127">Impostare l'integrazione con Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="b2916-127">Set up Microsoft Power Platform integration</span></span>

<span data-ttu-id="b2916-128">Prima di poter abilitare la funzionalità del componente aggiuntivo, è necessario eseguire l'integrazione con Microsoft Power Platform seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b2916-128">Before you can enable add-in functionality, you must integrate with Microsoft Power Platform by following these steps.</span></span>

1. <span data-ttu-id="b2916-129">Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.</span><span class="sxs-lookup"><span data-stu-id="b2916-129">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="b2916-130">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="b2916-130">Go to **Full details**.</span></span>
1. <span data-ttu-id="b2916-131">Nella sezione **Integrazione di Power Platform**, seleziona **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="b2916-131">In the **Power Platform Integration** section, select **Setup**.</span></span>
1. <span data-ttu-id="b2916-132">Nella finestra di dialogo **Configurazione ambiente Power Platform** seleziona la casella di controllo, quindi seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b2916-132">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="b2916-133">In genere, la configurazione richiede tra 60 e 90 minuti.</span><span class="sxs-lookup"><span data-stu-id="b2916-133">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="b2916-134">Quando la configurazione dell'ambiente Microsoft Power Platform è completata viene visualizzata la pagina con il nome del tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="b2916-134">After setup of the Microsoft Power Platform environment is completed, the page shows the name of your environment.</span></span> <span data-ttu-id="b2916-135">Inoltre, la sezione **Integrazione di Power Platform** mostra il messaggio "Configurazione dell'ambiente Power Platform completata."</span><span class="sxs-lookup"><span data-stu-id="b2916-135">Additionally, the **Power Platform Integration** section shows the statement, "Power Platform environment setup is complete."</span></span> <span data-ttu-id="b2916-136">Contabilità inventario globale non richiede un'applicazione a doppia scrittura.</span><span class="sxs-lookup"><span data-stu-id="b2916-136">Global Inventory Accounting doesn't require a dual-write application.</span></span>

<span data-ttu-id="b2916-137">Per ulteriori informazioni, vedere [Configurare dopo la distribuzione dell'ambiente](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span><span class="sxs-lookup"><span data-stu-id="b2916-137">For more information, see [Set up after environment deployment](../../fin-ops-core/dev-itpro/power-platform/overview.md#set-up-after-environment-deployment).</span></span>

### <a name="set-up-dataverse"></a><span data-ttu-id="b2916-138">Configurare Dataverse</span><span class="sxs-lookup"><span data-stu-id="b2916-138">Set up Dataverse</span></span>

<span data-ttu-id="b2916-139">Prima di configurare Dataverse, aggiungi i principi del servizio Contabilità inventario globale al tuo tenant seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b2916-139">Before you set up Dataverse, add the Global Inventory Accounting service principles to your tenant by following these steps.</span></span>

1. <span data-ttu-id="b2916-140">Installare il modulo Azure AD per Windows PowerShell v2 come descritto in [Installare Azure Active Directory PowerShell per Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="b2916-140">Install Azure AD Module for Windows PowerShell v2 as described in [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
1. <span data-ttu-id="b2916-141">Eseguire il comando PowerShell seguente.</span><span class="sxs-lookup"><span data-stu-id="b2916-141">Run the following PowerShell command.</span></span>

    ```powershell
    Connect-AzureAD # (open a sign in window and sign in as a tenant user)

    New-AzureADServicePrincipal -AppId "7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9" -DisplayName "d365-scm-costaccountingservice"

    New-AzureADServicePrincipal -AppId "5f58fc56-0202-49a8-ac9e-0946b049718b" -DisplayName "d365-scm-operationdataservice"
    ```

<span data-ttu-id="b2916-142">Quindi, crea gli utenti dell'applicazione per Contabilità inventario globale in Dataverse seguendo questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b2916-142">Next, create application users for Global Inventory Accounting in Dataverse by following these steps.</span></span>

1. <span data-ttu-id="b2916-143">Aprire l'URL del proprio ambiente Dataverse.</span><span class="sxs-lookup"><span data-stu-id="b2916-143">Open the URL of your Dataverse environment.</span></span>
1. <span data-ttu-id="b2916-144">Selezionare **Impostazioni avanzate \> Sistema \> Sicurezza \> Utenti** e creare un utente applicazione.</span><span class="sxs-lookup"><span data-stu-id="b2916-144">Go to **Advanced Setting \> System \> Security \> Users**, and create an application user.</span></span> <span data-ttu-id="b2916-145">Utilizza il campo **Visualizza** per cambiare la visualizzazione della pagina in *Utenti applicazione*.</span><span class="sxs-lookup"><span data-stu-id="b2916-145">Use the **View** field to change the page view to *Application users*.</span></span>
1. <span data-ttu-id="b2916-146">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b2916-146">Select **New**.</span></span>
1. <span data-ttu-id="b2916-147">Impostare il campo **ID applicazione** su *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span><span class="sxs-lookup"><span data-stu-id="b2916-147">Set the **Application ID** field to *7a1dd80f-c961-4a67-a2f5-d6a5d2f52cf9*.</span></span>
1. <span data-ttu-id="b2916-148">Selezionare **Assegna ruolo** e quindi selezionare *Amministratore di sistema*.</span><span class="sxs-lookup"><span data-stu-id="b2916-148">Select **Assign Role**, and then select *System Administrator*.</span></span> <span data-ttu-id="b2916-149">Se è presente un ruolo denominato *Utente Common Data Service*, selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="b2916-149">If there is a role that is named *Common Data Service User*, select it too.</span></span>
1. <span data-ttu-id="b2916-150">Ripeti i passaggi precedenti, ma imposta il campo **ID applicazione** su *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span><span class="sxs-lookup"><span data-stu-id="b2916-150">Repeat the preceding steps, but set the **Application ID** field to *5f58fc56-0202-49a8-ac9e-0946b049718b*.</span></span>

<span data-ttu-id="b2916-151">Per ulteriori informazioni, vedere [Creare un utente applicazione](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span><span class="sxs-lookup"><span data-stu-id="b2916-151">For more information, see [Create an application user](/power-platform/admin/create-users-assign-online-security-roles#create-an-application-user).</span></span>

<span data-ttu-id="b2916-152">Se la lingua predefinita dell'installazione di Dataverse non è inglese, segui questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="b2916-152">If the default language of your Dataverse installation isn't English, follow these steps.</span></span>

1. <span data-ttu-id="b2916-153">Vai a **Impostazioni avanzate \> Amministrazione \> Lingue**.</span><span class="sxs-lookup"><span data-stu-id="b2916-153">Go to **Advanced Setting \> Administration \> Languages**.</span></span>
1. <span data-ttu-id="b2916-154">Seleziona *Inglese* (*LanguageCode=1033*) e seleziona **Applica**.</span><span class="sxs-lookup"><span data-stu-id="b2916-154">Select *English* (*LanguageCode=1033*), and then select **Apply**.</span></span>

## <a name="install-the-add-in"></a><a name="install"></a><span data-ttu-id="b2916-155">Installare il componente aggiuntivo</span><span class="sxs-lookup"><span data-stu-id="b2916-155">Install the add-in</span></span>

<span data-ttu-id="b2916-156">Segui questi passaggi per installare il componente aggiuntivo in modo da poter utilizzare Contabilità inventario globale.</span><span class="sxs-lookup"><span data-stu-id="b2916-156">Follow these steps to install the add-in so that you can use Global Inventory Accounting.</span></span>

1. <span data-ttu-id="b2916-157">[Iscriviti](#sign-up) per l'anteprima pubblica di Contabilità inventario globale.</span><span class="sxs-lookup"><span data-stu-id="b2916-157">[Sign up](#sign-up) for the Global Inventory Accounting public preview.</span></span>
1. <span data-ttu-id="b2916-158">Accedere a [LCS](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="b2916-158">Sign in to [LCS](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="b2916-159">Accedere a **Gestione funzionalità di anteprima**.</span><span class="sxs-lookup"><span data-stu-id="b2916-159">Go to **Preview feature management**.</span></span>
1. <span data-ttu-id="b2916-160">Selezionare il segno più (**+**).</span><span class="sxs-lookup"><span data-stu-id="b2916-160">Select the plus sign (**+**).</span></span>
1. <span data-ttu-id="b2916-161">Nel campo **Codice**, inserisci la chiave beta del componente aggiuntivo Contabilità inventario globale.</span><span class="sxs-lookup"><span data-stu-id="b2916-161">In the **Code** field, enter your add-in beta key for Global Inventory Accounting.</span></span> <span data-ttu-id="b2916-162">Dovresti aver ricevuto la tua chiave beta via e-mail quando ti sei registrato.</span><span class="sxs-lookup"><span data-stu-id="b2916-162">(You should have received your beta key by email when you signed up.)</span></span>
1. <span data-ttu-id="b2916-163">Selezionare **Sblocca**.</span><span class="sxs-lookup"><span data-stu-id="b2916-163">Select **Unblock**.</span></span>
1. <span data-ttu-id="b2916-164">Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.</span><span class="sxs-lookup"><span data-stu-id="b2916-164">Open the LCS environment where you want to add the service.</span></span>
1. <span data-ttu-id="b2916-165">Andare a **Dettagli completi**.</span><span class="sxs-lookup"><span data-stu-id="b2916-165">Go to **Full details**.</span></span>
1. <span data-ttu-id="b2916-166">Vai a **Integrazione di Power Platform** e seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b2916-166">Go to **Power Platform Integration**, and select **Setup**.</span></span>
1. <span data-ttu-id="b2916-167">Nella finestra di dialogo **Configurazione ambiente Power Platform** seleziona la casella di controllo, quindi seleziona **Impostazioni**.</span><span class="sxs-lookup"><span data-stu-id="b2916-167">In the **Power platform environment setup** dialog box, select the checkbox, and then select **Setup**.</span></span> <span data-ttu-id="b2916-168">In genere, la configurazione richiede tra 60 e 90 minuti.</span><span class="sxs-lookup"><span data-stu-id="b2916-168">Typically, setup takes between 60 and 90 minutes.</span></span>
1. <span data-ttu-id="b2916-169">Dopo l'installazione dell'ambiente Microsoft Power Platform, nella scheda dettaglio **Componenti aggiuntivi ambiente** seleziona **Installa un nuovo componente aggiuntivo**.</span><span class="sxs-lookup"><span data-stu-id="b2916-169">After setup of the Microsoft Power Platform environment is completed, on the **Environment add-ins** FastTab, select **Install a new add-in**.</span></span>
1. <span data-ttu-id="b2916-170">Seleziona **Contabilità inventario globale**.</span><span class="sxs-lookup"><span data-stu-id="b2916-170">Select **Global inventory accounting**.</span></span>
1. <span data-ttu-id="b2916-171">Seguire la guida all'installazione e accettare le condizioni.</span><span class="sxs-lookup"><span data-stu-id="b2916-171">Follow the installation guide, and agree to the terms and conditions.</span></span>
1. <span data-ttu-id="b2916-172">Seleziona **Installa**.</span><span class="sxs-lookup"><span data-stu-id="b2916-172">Select **Install**.</span></span>
1. <span data-ttu-id="b2916-173">Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** viene indicato che Contabilità inventario globale è stato installato.</span><span class="sxs-lookup"><span data-stu-id="b2916-173">On the **Environment add-ins** FastTab, you should see that Global Inventory Accounting is being installed.</span></span> <span data-ttu-id="b2916-174">Dopo alcuni minuti, lo stato cambia da *Installazione in corso* in *Installato*.</span><span class="sxs-lookup"><span data-stu-id="b2916-174">After a few minutes, the status should change from *Installing* to *Installed*.</span></span> <span data-ttu-id="b2916-175">Potrebbe essere necessario aggiornare la pagina per vedere questa modifica. A quel punto, Contabilità inventario globale è pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="b2916-175">(You might have to refresh the page to see this change.) At that point, Global Inventory Accounting is ready to use.</span></span>

## <a name="set-up-the-integration"></a><span data-ttu-id="b2916-176">Impostare l'integrazione</span><span class="sxs-lookup"><span data-stu-id="b2916-176">Set up the integration</span></span>

<span data-ttu-id="b2916-177">Segui questi passaggi per impostare l'integrazione tra Contabilità inventario globale e Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b2916-177">Follow these steps to set up the integration between Global Inventory Accounting and Supply Chain Management.</span></span>

1. <span data-ttu-id="b2916-178">Accedere a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b2916-178">Sign in to Supply Chain Management.</span></span>
1. <span data-ttu-id="b2916-179">Vai a **Amministrazione sistema \> Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b2916-179">Go to **System administration \> Feature Management**.</span></span>
1. <span data-ttu-id="b2916-180">Selezionare **Controlla aggiornamenti**.</span><span class="sxs-lookup"><span data-stu-id="b2916-180">Select **Check for updates**.</span></span>
1. <span data-ttu-id="b2916-181">Nella scheda **Tutti** cerca la funzione denominata *Contabilità inventario globale*.</span><span class="sxs-lookup"><span data-stu-id="b2916-181">On the **All** tab, search for the feature that is named *Global inventory accounting*.</span></span>
1. <span data-ttu-id="b2916-182">Selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="b2916-182">Select **Enable now**.</span></span>
1. <span data-ttu-id="b2916-183">Vai a **Contabilità inventario globale \> Impostazioni \> Parametri contabilità inventario globale \> Parametri integrazione**.</span><span class="sxs-lookup"><span data-stu-id="b2916-183">Go to **Global inventory accounting \> Setup \> Global inventory accounting parameters \> Integrations parameters**.</span></span>
1. <span data-ttu-id="b2916-184">Nei campi **Endpoint servizio dati** e **Endpoint contabilità inventario globale** inserisci gli URL dall'e-mail che il team di contabilità inventario globale ha inviato quando ti sei registrato per l'anteprima.</span><span class="sxs-lookup"><span data-stu-id="b2916-184">In the **Data service endpoint** and **Global inventory accounting endpoint** fields, enter the URLs from the email that the Global Inventory Accounting team sent when you signed up for the preview.</span></span>

<span data-ttu-id="b2916-185">Contabilità inventario globale è ora pronto per l'uso.</span><span class="sxs-lookup"><span data-stu-id="b2916-185">Global Inventory Accounting is now ready to use.</span></span>
