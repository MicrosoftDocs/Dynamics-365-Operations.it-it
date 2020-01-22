---
title: Funzione ER EMPTYLIST
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione EMPTYLIST della creazione di report elettronici (ER).
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
ms.openlocfilehash: a60bc948ff6223b6e3acccd0ba40bf64f238aac2
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2917398"
---
# <span data-ttu-id="05b74-103"><a name="EMPTYLIST">Funzione ER EMPTYLIST</a></span><span class="sxs-lookup"><span data-stu-id="05b74-103"><a name="EMPTYLIST">EMPTYLIST ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05b74-104">La funzione `EMPTYLIST` restituisce un valore *Elenco di record* vuoto utilizzando l'elenco specificato come origine della struttura elenco.</span><span class="sxs-lookup"><span data-stu-id="05b74-104">The `EMPTYLIST` function returns an empty *Record list* value by using the specified list as a source for the list structure.</span></span>

## <a name="syntax"></a><span data-ttu-id="05b74-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="05b74-105">Syntax</span></span>

```
EMPTYLIST (list)
```

## <a name="arguments"></a><span data-ttu-id="05b74-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="05b74-106">Arguments</span></span>

<span data-ttu-id="05b74-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="05b74-107">`list`: *Record list*</span></span>

<span data-ttu-id="05b74-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="05b74-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="05b74-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="05b74-109">Return values</span></span>

<span data-ttu-id="05b74-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="05b74-110">*Record list*</span></span>

<span data-ttu-id="05b74-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="05b74-111">The resulting list of records.</span></span>

## <a name="example"></a><span data-ttu-id="05b74-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="05b74-112">Example</span></span>

<span data-ttu-id="05b74-113">`EMPTYLIST (SPLIT ("abc", 1))` restituisce un nuovo elenco vuoto con la stessa struttura dell'elenco restituito dalla funzione `SPLIT` utilizzata.</span><span class="sxs-lookup"><span data-stu-id="05b74-113">`EMPTYLIST (SPLIT ("abc", 1))` returns a new empty list that has the same structure as the list that is returned by the `SPLIT` function that is used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="05b74-114">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="05b74-114">Additional resources</span></span>

[<span data-ttu-id="05b74-115">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="05b74-115">List functions</span></span>](er-functions-category-list.md)
