---
title: Impostare il delimitatore del piano dei conti come univoco
description: In Dynamics 365 for Finance and Operations, non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Dopo l'aggiornamento, è necessario cambiare i valori del delimitatore.
author: ryansandness
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 8cc05772e7ee125a5ce8603c4d5f8719e8895c73
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1851773"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="dab7a-104">Impostare il delimitatore del piano dei conti come univoco</span><span class="sxs-lookup"><span data-stu-id="dab7a-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dab7a-105">In Microsoft Dynamics AX 2012, è possibile utilizzare lo stesso delimitatore per il piano dei conti e i valori delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab7a-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="dab7a-106">In Dynamics 365 for Finance and Operations, non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab7a-106">In Dynamics 365 for Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="dab7a-107">L'eventuale delimitatore duplicato può essere sostituito dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="dab7a-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="dab7a-108">Questa funzionalità è disponibile in:</span><span class="sxs-lookup"><span data-stu-id="dab7a-108">This feature is available in:</span></span>
- <span data-ttu-id="dab7a-109">Dynamics 365 for Finance and Operations versione 8.0</span><span class="sxs-lookup"><span data-stu-id="dab7a-109">Dynamics 365 for Finance and Operations version 8.0</span></span>
- <span data-ttu-id="dab7a-110">Dynamics 365 for Finance and Operations versione 7.1, KB 4094701 Non è possibile immettere le dimensioni finanziarie quando i valori delle dimensioni contengono il delimitatore del piano dei conti</span><span class="sxs-lookup"><span data-stu-id="dab7a-110">Dynamics 365 for Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="dab7a-111">Dynamics 365 for Finance and Operations versione 7.2, KB 4092967 Non è possibile scegliere un sottoprogetto come dimensione quando il formato del sottoprogetto contiene il delimitatore delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="dab7a-111">Dynamics 365 for Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="dab7a-112">Aggiornare il delimitatore</span><span class="sxs-lookup"><span data-stu-id="dab7a-112">Update delimiter</span></span>
<span data-ttu-id="dab7a-113">In presenza di un conflitto con il piano dei conti, è possibile cambiare il delimitatore del piano dei conti e il formato ID del progetto/sottoprogetto.</span><span class="sxs-lookup"><span data-stu-id="dab7a-113">If there is a conflict with the Chart of Accounts, the Chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="dab7a-114">Non è possibile cambiare alcun altro delimitatore delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab7a-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="dab7a-115">È possibile cambiare il delimitatore del piano dei conti dopo l'aggiornamento a Finance and Operations in **Parametri di contabilità generale** > **Piano dei conti e dimensioni** > **Modifica delimitatore**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-115">You can change the chart of accounts delimiter after upgrade to Finance and Operations in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="dab7a-116">Se il conflitto è presente solo con il formato ID del progetto/sottoprogetto, è possibile modificare il valore in **Parametri Gestione progetti e contabilità** > **Generale** > **Modifica formato sottoprogetto**.</span><span class="sxs-lookup"><span data-stu-id="dab7a-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="dab7a-117">Come determinare se l'ambiente richiede delimitatori aggiornati</span><span class="sxs-lookup"><span data-stu-id="dab7a-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="dab7a-118">Se i delimitatori nell'ambiente aggiornato sono in conflitto, è possibile avvertire l'instabilità quando si immettono i valori in un controllo di immissione segmentato o in un controllo di immissione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab7a-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="dab7a-119">Ciò significa che è sempre necessario utilizzare le ricerche o un menu a comparsa quando si immettono combinazioni di piano dei conti e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="dab7a-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
