---
title: Creare un progetto di integrazione dei dati (anteprima)
description: Questo argomento spiega come creare un progetto di integrazione dei dati.
author: ShivamPandey-msft
ms.date: 07/24/2020
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 9ecf6ef7b7f052ebbb1201dcd04a7431f5b72ce5
ms.sourcegitcommit: b64c52d85aa6f110f3b1959a5521637dd8631b5b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/07/2021
ms.locfileid: "5867449"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="f2cd4-103">Creare un progetto di integrazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="f2cd4-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="f2cd4-104">Questo argomento spiega come creare un progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="f2cd4-105">Accedere a Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="f2cd4-106">Vai a **Aree di lavoro \> Gestione dati** e seleziona **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="f2cd4-107">Attendi che tutte le entità di dati siano state aggiornate prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="f2cd4-108">Apri il [portale di Power Apps](https://make.powerapps.com/) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="f2cd4-109">Seleziona l'ambiente appropriato.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="f2cd4-110">Nel riquadro di spostamento sinistro, seleziona **Dati \> Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="f2cd4-111">Connettiti alle istanze appropriate dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="f2cd4-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f2cd4-112">Dynamics 365</span></span>
        - <span data-ttu-id="f2cd4-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="f2cd4-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="f2cd4-114">Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="f2cd4-115">Seleziona **Integrazione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="f2cd4-116">Seleziona **Set di connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="f2cd4-117">Seleziona **Nuovo set di connessioni**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="f2cd4-118">Immetti un nome per la connessione.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="f2cd4-119">Seleziona le connessioni appropriate per i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="f2cd4-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="f2cd4-120">Dynamics 365</span></span>
        - <span data-ttu-id="f2cd4-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="f2cd4-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="f2cd4-122">Seleziona il mapping dell'organizzazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="f2cd4-123">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-123">Select **Create**.</span></span>

5. <span data-ttu-id="f2cd4-124">Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="f2cd4-125">Crea progetti di integrazione dati per i seguenti modelli utilizzando il set di connessione appena creato:</span><span class="sxs-lookup"><span data-stu-id="f2cd4-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="f2cd4-126">Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="f2cd4-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="f2cd4-127">Se si utilizza la versione 10.0.17 o successiva, è necessario utilizzare il modello denominato Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17+).</span><span class="sxs-lookup"><span data-stu-id="f2cd4-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="f2cd4-128">Risultati delle serie temporali del flusso di cassa (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="f2cd4-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="f2cd4-129">Risultati delle serie temporali del budget (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="f2cd4-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="f2cd4-130">Imposta la pianificazione appropriata per ogni progetto.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="f2cd4-131">Se non vedi le entità richieste in CDS, vai a **Credito e riscossioni > Imposta> Informazioni finanziarie dettagliate > Parametri delle informazioni dettagliate finanziarie**, abilita la funzionalità Previsioni di pagamento del cliente e fai clic sul pulsante **Crea modello di previsione**.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="f2cd4-132">Quando la distribuzione del modello di intelligenza artificiale è completata (riuscita o non riuscita), le entità CDS necessarie per creare l'integrazione verranno distribuite in CDS.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

## <a name="privacy-notice"></a><span data-ttu-id="f2cd4-133">Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="f2cd4-133">Privacy notice</span></span>

<span data-ttu-id="f2cd4-134">Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.</span><span class="sxs-lookup"><span data-stu-id="f2cd4-134">Previews (1) might use less privacy and fewer security measures than the Dynamics 365 Finance and Operations service, (2) aren't included in the service level agreement (SLA) for this service, (3) should not be used to process personal data or other data that is subject to legal or regulatory compliance requirements, and (4) have limited support.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
