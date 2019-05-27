---
title: Definire il gruppo di risorse di produzione discreta
description: Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione.
author: sorenva
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 50733e34bbf14ae2cade6822105da4d8c2120d7d
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1556390"
---
# <a name="define-discrete-manufacturing-resource-group"></a><span data-ttu-id="1d100-103">Definire il gruppo di risorse di produzione discreta</span><span class="sxs-lookup"><span data-stu-id="1d100-103">Define discrete manufacturing resource group</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1d100-104">Un gruppo di risorse è un set di risorse operative che in genere corrisponde all'organizzazione fisica delle celle di lavoro, definito dalle righe gialle nello shop floor di produzione.</span><span class="sxs-lookup"><span data-stu-id="1d100-104">A resource group is a set of operations resources that typically correspond to the physical organization of work cells, defined by yellow lines on the production shop floor.</span></span> <span data-ttu-id="1d100-105">In questa procedura viene illustrato come definire un gruppo di risorse da utilizzare nella produzione discreta.</span><span class="sxs-lookup"><span data-stu-id="1d100-105">This procedure shows you how to define a ressource group for use in discrete production.</span></span> <span data-ttu-id="1d100-106">È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure utilizzare i propri dati.</span><span class="sxs-lookup"><span data-stu-id="1d100-106">You can walk through this procedure in demo data company USMF, or use your own data.</span></span>

1. <span data-ttu-id="1d100-107">Fare clic su Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="1d100-107">Go to Resource groups.</span></span>
2. <span data-ttu-id="1d100-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="1d100-108">Click New.</span></span>
3. <span data-ttu-id="1d100-109">Digitare un valore nel campo Gruppo di risorse.</span><span class="sxs-lookup"><span data-stu-id="1d100-109">In the Resource group field, type a value.</span></span>
4. <span data-ttu-id="1d100-110">Nel campo Descrizione digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-110">In the Description field, type a value.</span></span>
5. <span data-ttu-id="1d100-111">Nel campo Sito immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-111">In the Site field, enter or select a value.</span></span>
6. <span data-ttu-id="1d100-112">Nel campo Unità di produzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-112">In the Production unit field, enter or select a value.</span></span>

## <a name="define-default-operational-parameters"></a><span data-ttu-id="1d100-113">Definisce i parametri operativi predefiniti</span><span class="sxs-lookup"><span data-stu-id="1d100-113">Define default operational parameters</span></span>
1. <span data-ttu-id="1d100-114">Espandere la sezione Operazione.</span><span class="sxs-lookup"><span data-stu-id="1d100-114">Expand the Operation section.</span></span>
2. <span data-ttu-id="1d100-115">Immettere un numero nel campo Percentuale scarti.</span><span class="sxs-lookup"><span data-stu-id="1d100-115">In the Scrap percentage field, enter a number.</span></span>
3. <span data-ttu-id="1d100-116">Nel campo Categoria tempo di attrezzaggio immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-116">In the Setup category field, enter or select a value.</span></span>
4. <span data-ttu-id="1d100-117">Nel campo Categoria tempo di esecuzione immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-117">In the Run time category field, enter or select a value.</span></span>
5. <span data-ttu-id="1d100-118">Nel campo Percentuale programmazione operazioni, immettere un numero.</span><span class="sxs-lookup"><span data-stu-id="1d100-118">In the Operations scheduling percentage field, enter a number.</span></span>

## <a name="define-operating-hours"></a><span data-ttu-id="1d100-119">Definisce le ore di funzionamento</span><span class="sxs-lookup"><span data-stu-id="1d100-119">Define operating hours</span></span>
1. <span data-ttu-id="1d100-120">Espandere la sezione Calendari.</span><span class="sxs-lookup"><span data-stu-id="1d100-120">Expand the Calendars section.</span></span>
2. <span data-ttu-id="1d100-121">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1d100-121">Click Add.</span></span>
3. <span data-ttu-id="1d100-122">Nel campo Calendario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-122">In the Calendar field, enter or select a value.</span></span>

## <a name="add-operations-resources"></a><span data-ttu-id="1d100-123">Aggiunge le risorse operative</span><span class="sxs-lookup"><span data-stu-id="1d100-123">Add operations resources</span></span>
1. <span data-ttu-id="1d100-124">Espandere la sezione Risorse.</span><span class="sxs-lookup"><span data-stu-id="1d100-124">Expand the Resources section.</span></span>
2. <span data-ttu-id="1d100-125">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1d100-125">Click Add.</span></span>
3. <span data-ttu-id="1d100-126">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-126">In the Resource field, enter or select a value.</span></span>
4. <span data-ttu-id="1d100-127">Scegliere Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="1d100-127">Click Add.</span></span>
5. <span data-ttu-id="1d100-128">Nel campo Risorsa immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="1d100-128">In the Resource field, enter or select a value.</span></span>
6. <span data-ttu-id="1d100-129">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="1d100-129">In the list, find and select the desired record.</span></span>
7. <span data-ttu-id="1d100-130">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="1d100-130">In the list, click the link in the selected row.</span></span>

