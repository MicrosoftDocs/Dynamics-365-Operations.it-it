---
title: Impostare il delimitatore del piano dei conti come univoco
description: In questo argomento viene descritto perché non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni. Dopo l'aggiornamento, è necessario cambiare i valori del delimitatore.
author: panolte
manager: AnnBe
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 72965e9c6182bdac123feb1bc5cc4b82d91cd588
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020106"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="04199-104">Impostare il delimitatore del piano dei conti come univoco</span><span class="sxs-lookup"><span data-stu-id="04199-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="04199-105">In Microsoft Dynamics AX 2012, è possibile utilizzare lo stesso delimitatore per il piano dei conti e i valori delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04199-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="04199-106">Nelle versioni correnti di Finance and Operations, non è possibile avere lo stesso delimitatore per il piano dei conti e i valori delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04199-106">In current versions of Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="04199-107">L'eventuale delimitatore duplicato può essere sostituito dopo l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="04199-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="04199-108">Questa funzionalità è disponibile nelle seguenti versioni:</span><span class="sxs-lookup"><span data-stu-id="04199-108">This feature is available in the following versions:</span></span>
- <span data-ttu-id="04199-109">Finance and Operations versione 8.0</span><span class="sxs-lookup"><span data-stu-id="04199-109">Finance and Operations version 8.0</span></span>
- <span data-ttu-id="04199-110">Finance and Operations versione 7.1, KB 4094701 Non è possibile immettere le dimensioni finanziarie quando i valori delle dimensioni contengono il delimitatore del piano dei conti</span><span class="sxs-lookup"><span data-stu-id="04199-110">Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="04199-111">Finance and Operations versione 7.2, KB 4092967 Non è possibile scegliere un sottoprogetto come dimensione quando il formato del sottoprogetto contiene il delimitatore delle dimensioni</span><span class="sxs-lookup"><span data-stu-id="04199-111">Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="04199-112">Aggiornare il delimitatore</span><span class="sxs-lookup"><span data-stu-id="04199-112">Update delimiter</span></span>
<span data-ttu-id="04199-113">In presenza di un conflitto con il piano dei conti, è possibile cambiare il delimitatore del piano dei conti e il formato ID del progetto/sottoprogetto.</span><span class="sxs-lookup"><span data-stu-id="04199-113">If there is a conflict with the chart of accounts, the chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="04199-114">Non è possibile cambiare alcun altro delimitatore delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04199-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="04199-115">È possibile cambiare il delimitatore del piano dei conti dopo l'aggiornamento in **Parametri di contabilità generale** > **Piano dei conti e dimensioni** > **Modifica delimitatore**.</span><span class="sxs-lookup"><span data-stu-id="04199-115">You can change the chart of accounts delimiter after upgrade in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="04199-116">Se il conflitto è presente solo con il formato ID del progetto/sottoprogetto, è possibile modificare il valore in **Parametri Gestione progetti e contabilità** > **Generale** > **Modifica formato sottoprogetto**.</span><span class="sxs-lookup"><span data-stu-id="04199-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="04199-117">Come determinare se l'ambiente richiede delimitatori aggiornati</span><span class="sxs-lookup"><span data-stu-id="04199-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="04199-118">Se i delimitatori nell'ambiente aggiornato sono in conflitto, è possibile avvertire l'instabilità quando si immettono i valori in un controllo di immissione segmentato o in un controllo di immissione delle dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04199-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="04199-119">Ciò significa che è sempre necessario utilizzare le ricerche o un menu a comparsa quando si immettono combinazioni di piano dei conti e dimensioni.</span><span class="sxs-lookup"><span data-stu-id="04199-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>
