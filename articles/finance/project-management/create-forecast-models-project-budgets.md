---
title: Creare modelli previsionali per budget di progetto
description: Questo argomento descrive come creare un modello previsionale per i budget residui.
author: RadhikaRS
manager: AnnBe
ms.date: 04/24/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 07e540f23a668b40a54906a67d87552fe991825a
ms.sourcegitcommit: 5de75c61c33e57c813944f1ab6100aceb020d432
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "3321781"
---
# <a name="create-forecast-models-for-project-budgets"></a><span data-ttu-id="a8c3b-103">Creare modelli previsionali per budget di progetto</span><span class="sxs-lookup"><span data-stu-id="a8c3b-103">Create forecast models for project budgets</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a8c3b-104">Questo argomento descrive come creare un modello previsionale per i budget residui.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-104">This topic describes how to create a forecast model for remaining budgets.</span></span> <span data-ttu-id="a8c3b-105">In un progetto soggetto al controllo del budget vengono utilizzati due tipi di budget: originale e residuo.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-105">A project that is subject to budget control uses two types of budgets: original and remaining.</span></span> <span data-ttu-id="a8c3b-106">Quando si crea un budget di progetto, è necessario specificare i modelli previsionali di budget originale e residuo creati nella pagina **Modelli previsionali**.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-106">When you create a project budget, you must specify the original and remaining budget forecast models that were created in the **Forecast models** page.</span></span> <span data-ttu-id="a8c3b-107">I budget di progetto basati su modelli specifici vengono creati quando si esegue il commit del budget di progetto.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-107">Project budgets based on the specified models are created when you commit the project budget.</span></span>

> [!NOTE]
> <span data-ttu-id="a8c3b-108">Un modello previsionale utilizzato per il controllo del budget non può avere un sottomodello né può essere utilizzato come sottomodello.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-108">A forecast model that is used for budget control can’t have a submodel or be used as a submodel.</span></span>

1. <span data-ttu-id="a8c3b-109">Selezionare **Gestione progetti e contabilità** > **Imposta** > **Previsioni**  > **Modelli previsionali**.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-109">Select **Project management and accounting** > **Setup** > **Forecasts**  > **Forecast models**.</span></span>
2. <span data-ttu-id="a8c3b-110">Seleziona **Nuovo** per creare un nuovo modello previsionale, quindi immettere un numero di ID modello e un nome per il nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-110">Select **New** to create a new forecast model, and then enter a model ID number and name for the new model.</span></span> 
3. <span data-ttu-id="a8c3b-111">Impostare l'opzione **Arrestato** su **Sì** per impedire eventuali modifiche alle righe di previsione per il modello previsionale.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-111">Set the **Stopped** option to **Yes** to prevent any changes to the forecast lines for the forecast model.</span></span> 
4. <span data-ttu-id="a8c3b-112">Se dalle righe di previsione a cui è associalo il modello dovranno essere generate previsioni di cassa nella contabilità generale, impostare **Includere in previsioni di cassa** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-112">If the forecast lines that the model is associated with should generate cash flow forecasts in the general ledger, set **Include in Cash flow forecasts** to **Yes.**</span></span> 
5. <span data-ttu-id="a8c3b-113">Per utilizzare la data del progetto come data della fattura, impostare **Data fattura prevista** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-113">To use the project date as the invoice date, set **Forecast Invoice date** to **Yes**.</span></span> 
6. <span data-ttu-id="a8c3b-114">Nel campo **Tipo di budget** selezionare uno dei seguenti tipi di modelli:</span><span class="sxs-lookup"><span data-stu-id="a8c3b-114">In the **Budget type** field, select one of the following model types:</span></span>

   - <span data-ttu-id="a8c3b-115">**Budget originale**: utilizzare gli importi del budget originale di cui viene eseguito il commit quando viene creato e approvato il budget iniziale.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-115">**Original budget**: Use the original budget amounts that are committed when the initial budget is created and approved.</span></span>
   - <span data-ttu-id="a8c3b-116">**Budget residuo**: utilizzare questo tipo di modello per gli importi del budget residuo durante la vita utile del progetto.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-116">**Remaining budget**: Use the remaining budget amounts during the life of the project.</span></span> <span data-ttu-id="a8c3b-117">I saldi in questo modello previsionale vengono ridotti in base alle transazioni effettive e aumentati o diminuiti in base alle revisioni del budget.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-117">The balances in this forecast model are reduced by actual transactions and increased or decreased by budget revisions.</span></span>
   - <span data-ttu-id="a8c3b-118">**Riportabile in avanti**: utilizzare gli importi del budget riportabile in avanti per il progetto.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-118">**Carry-forward**: Use the carry-forward budget amounts for the project.</span></span> <span data-ttu-id="a8c3b-119">Riportabile in avanti è un processo facoltativo e può essere eseguito per trasferire gli importi di budget inutilizzati da un anno fiscale a un altro.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-119">Carry-forward is an optional process that can be run to transfer unused budget amounts from one fiscal year to another.</span></span>

7. <span data-ttu-id="a8c3b-120">Impostare le seguenti opzioni come richiesto:</span><span class="sxs-lookup"><span data-stu-id="a8c3b-120">Set the following options as required:</span></span>

   - <span data-ttu-id="a8c3b-121">Abilitare **Data fattura prevista** per utilizzare la data del progetto come data della fattura.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-121">Enable **Forecast invoice date** to use the project date as the invoice date.</span></span>
   - <span data-ttu-id="a8c3b-122">Abilitare **Previsioni con WIP** per eseguire le previsioni in base ai WIP (Work-in-Progress), quindi selezionare il tipo di WIP.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-122">Enable **Forecast with WIP** to forecast based on work in progress (WIP), and then select the type of WIP.</span></span> 
   - <span data-ttu-id="a8c3b-123">È possibile mantenere il valore predefinito **Tipo di budget** come **Nessuno** o inserire un nuovo tipo.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-123">You can keep the default **Budget type** as **None** or enter a new type.</span></span> <span data-ttu-id="a8c3b-124">Il tipo di budget non può essere modificato dopo aver modificato un record.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-124">The budget type can't be changed after you change a record.</span></span>     
    > [!NOTE]
    > <span data-ttu-id="a8c3b-125">Se si modifica il tipo di budget predefinito, tutte le altre opzioni non saranno disponibili per gli aggiornamenti e non è possibile riutilizzare questo modello previsionale.</span><span class="sxs-lookup"><span data-stu-id="a8c3b-125">If you change the default budget type, all other options will become unavailable for updates, and you can't reuse this forecast model.</span></span> 
   


 

