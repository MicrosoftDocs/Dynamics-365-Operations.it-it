---
title: Funzione ER ENUMERATE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ENUMERATE della creazione di report elettronici (ER).
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
ms.openlocfilehash: f0a1c83ee869810e816b6d32ea890d172d2910e5
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916225"
---
# <span data-ttu-id="1f4df-103"><a name="ENUMERATE">Funzione ER ENUMERATE</a></span><span class="sxs-lookup"><span data-stu-id="1f4df-103"><a name="ENUMERATE">ENUMERATE ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f4df-104">La funzione `ENUMERATE` restituisce un nuovo valore *Elenco di record* costituito dai record enumerati dell'elenco specificato.</span><span class="sxs-lookup"><span data-stu-id="1f4df-104">The `ENUMERATE` function returns a new *Record list* value that consists of enumerated records of the specified list.</span></span>

## <a name="syntax"></a><span data-ttu-id="1f4df-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1f4df-105">Syntax</span></span>

```
ENUMERATE (list)
```

## <a name="arguments"></a><span data-ttu-id="1f4df-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="1f4df-106">Arguments</span></span>

<span data-ttu-id="1f4df-107">`list`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="1f4df-107">`list`: *Record list*</span></span>

<span data-ttu-id="1f4df-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="1f4df-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="1f4df-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="1f4df-109">Return values</span></span>

<span data-ttu-id="1f4df-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="1f4df-110">*Record list*</span></span>

<span data-ttu-id="1f4df-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="1f4df-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="1f4df-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="1f4df-112">Usage notes</span></span>

<span data-ttu-id="1f4df-113">L'elenco dei record enumerati restituiti espone i seguenti elementi aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="1f4df-113">The list of enumerated records that is returned exposes the following additional elements:</span></span>

- <span data-ttu-id="1f4df-114">Il record dei campi (componente **Value**)</span><span class="sxs-lookup"><span data-stu-id="1f4df-114">The record of fields (**Value** component)</span></span>
- <span data-ttu-id="1f4df-115">L'indice del record corrente (componente **Number**)</span><span class="sxs-lookup"><span data-stu-id="1f4df-115">The current record index (**Number** component)</span></span>

## <a name="example"></a><span data-ttu-id="1f4df-116">Esempio</span><span class="sxs-lookup"><span data-stu-id="1f4df-116">Example</span></span>

<span data-ttu-id="1f4df-117">Nella seguente illustrazione, un'origine dati **Enumerated** viene creata come elenco enumerato di record fornitori dall'origine dati **Vendors** che fa riferimento alla tabella VendTable.</span><span class="sxs-lookup"><span data-stu-id="1f4df-117">In the following illustration, an **Enumerated** data source is created as an enumerated list of vendor records from the **Vendors** data source that refers to the VendTable table.</span></span>

<a href="./media/picture-enumerate-datasource.jpg"><img src="./media/picture-enumerate-datasource.jpg" alt="Enumerated data source" class="alignnone wp-image-290711 size-full" width="387" height="136" /></a>

<span data-ttu-id="1f4df-118">L'illustrazione seguente mostra il formato creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="1f4df-118">The following illustration shows the Electronic reporting (ER) format.</span></span> <span data-ttu-id="1f4df-119">In questo formato, le associazioni dati vengono create per generare l'output in formato XML.</span><span class="sxs-lookup"><span data-stu-id="1f4df-119">In this format, data bindings are created to generate output in XML format.</span></span> <span data-ttu-id="1f4df-120">Questo output presenta i singoli fornitori come nodi enumerati.</span><span class="sxs-lookup"><span data-stu-id="1f4df-120">This output presents individual vendors as enumerated nodes.</span></span>

<a href="./media/picture-enumerate-format.jpg"><img src="./media/picture-enumerate-format.jpg" alt="Format that has data bindings" class="alignnone wp-image-290721 size-full" width="414" height="138" /></a>

<span data-ttu-id="1f4df-121">Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.</span><span class="sxs-lookup"><span data-stu-id="1f4df-121">The following illustration shows the result when the designed format is run.</span></span>

<a href="./media/picture-enumerate-result.jpg"><img src="./media/picture-enumerate-result.jpg" alt="Result of running the format" class="alignnone wp-image-290731 size-full" width="567" height="176" /></a>

## <a name="additional-resources"></a><span data-ttu-id="1f4df-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="1f4df-122">Additional resources</span></span>

[<span data-ttu-id="1f4df-123">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="1f4df-123">List functions</span></span>](er-functions-category-list.md)
