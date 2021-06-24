---
title: Creare un progetto di integrazione dei dati (anteprima)
description: Questo argomento spiega come creare un progetto di integrazione dei dati.
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 59f85c64ea7b1f539a245e08b76bd6a34797b0ca
ms.sourcegitcommit: ebcd9019cbb88a7f2afd9e701812e222566fd43d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "6186470"
---
# <a name="create-a-data-integrator-project-preview"></a><span data-ttu-id="e4d90-103">Creare un progetto di integrazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="e4d90-103">Create a data integrator project (preview)</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="e4d90-104">Questo argomento spiega come creare un progetto di integrazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="e4d90-104">This topic explains how to create a data integrator project.</span></span>

1. <span data-ttu-id="e4d90-105">Accedere a Microsoft Dynamics 365 Finance.</span><span class="sxs-lookup"><span data-stu-id="e4d90-105">Sign in to Microsoft Dynamics 365 Finance.</span></span>
2. <span data-ttu-id="e4d90-106">Vai a **Aree di lavoro \> Gestione dati** e seleziona **Entità di dati**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-106">Go to **Workspaces \> Data management**, and select **Data entities**.</span></span> <span data-ttu-id="e4d90-107">Attendi che tutte le entità di dati siano state aggiornate prima di passare alla fase successiva.</span><span class="sxs-lookup"><span data-stu-id="e4d90-107">Wait until all the data entities have been refreshed before you move on to the next step.</span></span>
3. <span data-ttu-id="e4d90-108">Apri il [portale di Power Apps](https://make.powerapps.com/) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="e4d90-108">Open the [Power Apps portal](https://make.powerapps.com/), and follow these steps:</span></span>

    1. <span data-ttu-id="e4d90-109">Seleziona l'ambiente appropriato.</span><span class="sxs-lookup"><span data-stu-id="e4d90-109">Select the appropriate environment.</span></span>
    2. <span data-ttu-id="e4d90-110">Nel riquadro di spostamento sinistro, seleziona **Dati \> Connessioni**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-110">In the left navigation pane, select **Data \> Connections**.</span></span>
    3. <span data-ttu-id="e4d90-111">Connettiti alle istanze appropriate dei seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="e4d90-111">Connect to appropriate instances of the following items:</span></span>

        - <span data-ttu-id="e4d90-112">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4d90-112">Dynamics 365</span></span>
        - <span data-ttu-id="e4d90-113">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="e4d90-113">Dynamics 365 for Fin & Ops</span></span>

4. <span data-ttu-id="e4d90-114">Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="e4d90-114">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>

    1. <span data-ttu-id="e4d90-115">Seleziona **Integrazione dei dati**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-115">Select **Data Integrator**.</span></span>
    2. <span data-ttu-id="e4d90-116">Seleziona **Set di connessioni**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-116">Select **Connection sets**.</span></span>
    3. <span data-ttu-id="e4d90-117">Seleziona **Nuovo set di connessioni**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-117">Select **New connection set**.</span></span>
    4. <span data-ttu-id="e4d90-118">Immetti un nome per la connessione.</span><span class="sxs-lookup"><span data-stu-id="e4d90-118">Enter a name for the connection.</span></span>
    5. <span data-ttu-id="e4d90-119">Seleziona le connessioni appropriate per i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="e4d90-119">Select the appropriate connections for the following items:</span></span>

        - <span data-ttu-id="e4d90-120">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e4d90-120">Dynamics 365</span></span>
        - <span data-ttu-id="e4d90-121">Dynamics 365 for Fin & Ops</span><span class="sxs-lookup"><span data-stu-id="e4d90-121">Dynamics 365 for Fin & Ops</span></span>

    6. <span data-ttu-id="e4d90-122">Seleziona il mapping dell'organizzazione appropriata.</span><span class="sxs-lookup"><span data-stu-id="e4d90-122">Select the appropriate organization mapping.</span></span>
    7. <span data-ttu-id="e4d90-123">Selezionare **Crea**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-123">Select **Create**.</span></span>

5. <span data-ttu-id="e4d90-124">Apri gli [ambienti di Power Apps](https://admin.powerapps.com/environments) e segui questi passaggi:</span><span class="sxs-lookup"><span data-stu-id="e4d90-124">Open the [Power Apps environments](https://admin.powerapps.com/environments), and follow these steps:</span></span>  

    1. <span data-ttu-id="e4d90-125">Crea progetti di integrazione dati per i seguenti modelli utilizzando il set di connessione appena creato:</span><span class="sxs-lookup"><span data-stu-id="e4d90-125">Create data integration projects for the following templates by using the connection set that you just created:</span></span>

        - <span data-ttu-id="e4d90-126">Risultati delle informazioni dettagliate sui pagamenti dei clienti (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e4d90-126">Customer payment insights results (CDS to Fin and Ops)</span></span>
            - <span data-ttu-id="e4d90-127">Se si utilizza la versione 10.0.17 o successiva, è necessario utilizzare il modello denominato Risultato delle analisi di pagamenti cliente (da CDS a Fin and Ops 10.0.17+).</span><span class="sxs-lookup"><span data-stu-id="e4d90-127">If you are using version 10.0.17 or later, you need to use the template named, Customer payment insights result (CDS to Fin and Ops 10.0.17+).</span></span>
        - <span data-ttu-id="e4d90-128">Risultati delle serie temporali del flusso di cassa (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e4d90-128">Cash flow time series results (CDS to Fin and Ops)</span></span>
        - <span data-ttu-id="e4d90-129">Risultati delle serie temporali del budget (da CDS a Fin and Ops)</span><span class="sxs-lookup"><span data-stu-id="e4d90-129">Budget time series results (CDS to Fin and Ops)</span></span>

    2. <span data-ttu-id="e4d90-130">Imposta la pianificazione appropriata per ogni progetto.</span><span class="sxs-lookup"><span data-stu-id="e4d90-130">Set the appropriate scheduling for each project.</span></span>

> [!NOTE]
> <span data-ttu-id="e4d90-131">Se non vedi le entità richieste in CDS, vai a **Credito e riscossioni > Imposta > Finance Insights > Parametri di Finance Insights**, abilita la funzionalità Previsioni di pagamento del cliente e fai clic sul pulsante **Crea modello di previsione**.</span><span class="sxs-lookup"><span data-stu-id="e4d90-131">If you do not see the required entities in CDS, please go to **Credit and collections > Setup > Finance Insights > Finance insights parameters**, enable Customer payment predictions feature and click on **Create prediction model** button.</span></span> <span data-ttu-id="e4d90-132">Quando la distribuzione del modello di intelligenza artificiale è completata (riuscita o non riuscita), le entità CDS necessarie per creare l'integrazione verranno distribuite in CDS.</span><span class="sxs-lookup"><span data-stu-id="e4d90-132">When the deployment of AI model is completed (successful or failed), the CDS entities needed to create integration will be deployed in CDS.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
