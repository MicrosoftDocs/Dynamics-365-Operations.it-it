---
title: Funzione ER FIRST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FIRST della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4d10abcf15b93961bd2ba4aec22914825d9ac38c
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042092"
---
# <span data-ttu-id="7a433-103"><a name="FIRST">Funzione ER FIRST</a></span><span class="sxs-lookup"><span data-stu-id="7a433-103"><a name="FIRST">FIRST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="7a433-104">La funzione `FIRST` restituisce il primo record dell'elenco specificato come un valore *Contenitore (record)*, se tale elenco non è vuoto.</span><span class="sxs-lookup"><span data-stu-id="7a433-104">The `FIRST` function returns the first record of the specified list as a *Container (record)* value, if that list isn't empty.</span></span> <span data-ttu-id="7a433-105">Se l'elenco è vuoto, questa funzione genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="7a433-105">If the list is empty, this function throws an exception.</span></span>

## <a name="syntax"></a><span data-ttu-id="7a433-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7a433-106">Syntax</span></span>

```vb
FIRST (list)
```

## <a name="arguments"></a><span data-ttu-id="7a433-107">Argomenti</span><span class="sxs-lookup"><span data-stu-id="7a433-107">Arguments</span></span>

<span data-ttu-id="7a433-108">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="7a433-108">`list`: *Record list*</span></span>

<span data-ttu-id="7a433-109">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="7a433-109">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="7a433-110">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="7a433-110">Return values</span></span>

<span data-ttu-id="7a433-111">*Contenitore (record)*</span><span class="sxs-lookup"><span data-stu-id="7a433-111">*Container (record)*</span></span>

<span data-ttu-id="7a433-112">Il valore del record risultante.</span><span class="sxs-lookup"><span data-stu-id="7a433-112">The resulting record value.</span></span>

## <a name="example-1"></a><span data-ttu-id="7a433-113">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="7a433-113">Example 1</span></span>

<span data-ttu-id="7a433-114">L'espressione `FIRST(SPLIT("ABC",1)).Value` restituisce il valore del testo **"A"**.</span><span class="sxs-lookup"><span data-stu-id="7a433-114">The expression `FIRST(SPLIT("ABC",1)).Value` returns the text value **"A"**.</span></span>

## <a name="example-2"></a><span data-ttu-id="7a433-115">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="7a433-115">Example 2</span></span>

<span data-ttu-id="7a433-116">L'espressione `FIRST(SPLIT("",1)).Value` genera un'eccezione in fase di runtime.</span><span class="sxs-lookup"><span data-stu-id="7a433-116">The expression `FIRST(SPLIT("",1)).Value` throws an exception at runtime.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7a433-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7a433-117">Additional resources</span></span>

[<span data-ttu-id="7a433-118">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="7a433-118">List functions</span></span>](er-functions-category-list.md)
