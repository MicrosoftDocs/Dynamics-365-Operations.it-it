---
title: Definire il gruppo di risorse di produzione discreta
description: Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione.
author: sorenva
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24097cbb6f0ffae7b1b52bd3c70b7e054b3ce86c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257317"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="d4a67-103">Definire il gruppo di risorse di produzione discreta</span><span class="sxs-lookup"><span data-stu-id="d4a67-103">Define discrete manufacturing resource group</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d4a67-104">Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione.</span><span class="sxs-lookup"><span data-stu-id="d4a67-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="d4a67-105">In questa procedura viene illustrato come definire un gruppo di risorse da utilizzare nella produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="d4a67-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="d4a67-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzare i propri dati.</span><span class="sxs-lookup"><span data-stu-id="d4a67-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="d4a67-107">Fare clic su Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="d4a67-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="d4a67-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="d4a67-108">Click New.</span></span>
3. <span data-ttu-id="d4a67-109">Digitare un valore nel campo Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="d4a67-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="d4a67-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="d4a67-111">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="d4a67-112">Nel campo Unità di produzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="d4a67-113">Definisce i parametri operativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="d4a67-113">Define default operational parameters</span></span>
1. <span data-ttu-id="d4a67-114">Espandere la sezione Operazione.</span><span class="sxs-lookup"><span data-stu-id="d4a67-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="d4a67-115">Immettere un numero nel campo Percentuale scarti.</span><span class="sxs-lookup"><span data-stu-id="d4a67-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="d4a67-116">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="d4a67-117">Nel campo Categoria tempo di esecuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="d4a67-118">Nel campo Percentuale programmazione operazioni, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="d4a67-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="d4a67-119">Definisce le ore di funzionamento</span><span class="sxs-lookup"><span data-stu-id="d4a67-119">Define operating hours</span></span>
1. <span data-ttu-id="d4a67-120">Espandere la sezione Calendari.</span><span class="sxs-lookup"><span data-stu-id="d4a67-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="d4a67-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d4a67-121">Click Add.</span></span>
3. <span data-ttu-id="d4a67-122">Nel campo Calendario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="d4a67-123">Aggiunge le risorse operative</span><span class="sxs-lookup"><span data-stu-id="d4a67-123">Add operations resources</span></span>
1. <span data-ttu-id="d4a67-124">Espandere la sezione Risorse.</span><span class="sxs-lookup"><span data-stu-id="d4a67-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="d4a67-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d4a67-125">Click Add.</span></span>
3. <span data-ttu-id="d4a67-126">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="d4a67-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="d4a67-127">Click Add.</span></span>
5. <span data-ttu-id="d4a67-128">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="d4a67-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="d4a67-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d4a67-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="d4a67-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d4a67-130">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]