---
title: Funzione ER TABLENAME2ID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TABLENAME2ID della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a68a8e1f4afa378ab446eae12bc90cdb3aba8b19
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681160"
---
# <a name="tablename2id-er-function"></a><span data-ttu-id="343db-103">Funzione ER TABLENAME2ID</span><span class="sxs-lookup"><span data-stu-id="343db-103">TABLENAME2ID ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="343db-104">La funzione `TABLENAME2ID` restituisce una rappresentazione numerica dell'ID tabella per il nome tabella specificato come valore *Intero*.</span><span class="sxs-lookup"><span data-stu-id="343db-104">The `TABLENAME2ID` function returns a numeric representation of the table ID for the specified table name as an *Integer* value.</span></span>

## <a name="syntax"></a><span data-ttu-id="343db-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="343db-105">Syntax</span></span>

```vb
TABLENAME2ID (text)
```

## <a name="arguments"></a><span data-ttu-id="343db-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="343db-106">Arguments</span></span>

<span data-ttu-id="343db-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="343db-107">`text`: *String*</span></span>

<span data-ttu-id="343db-108">Un valore di testo che rappresenta un nome di tabella valido.</span><span class="sxs-lookup"><span data-stu-id="343db-108">A text value that represents a valid table name.</span></span>

## <a name="return-values"></a><span data-ttu-id="343db-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="343db-109">Return values</span></span>

<span data-ttu-id="343db-110">*Intero*</span><span class="sxs-lookup"><span data-stu-id="343db-110">*Integer*</span></span>

<span data-ttu-id="343db-111">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="343db-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="343db-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="343db-112">Usage notes</span></span>

<span data-ttu-id="343db-113">L'esecuzione di questa funzione può avere risultati diversi in diverse istanze di Microsoft Dynamics 365 Finance, anche se viene utilizzato lo stesso nome di società.</span><span class="sxs-lookup"><span data-stu-id="343db-113">Execution of this function can have different results in different instances of Microsoft Dynamics 365 Finance, even if the same company name is used.</span></span>

## <a name="example"></a><span data-ttu-id="343db-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="343db-114">Example</span></span>

<span data-ttu-id="343db-115">`TABLENAME2ID ("Intrastat")` restituisce **1510**.</span><span class="sxs-lookup"><span data-stu-id="343db-115">`TABLENAME2ID ("Intrastat")` returns **1510**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="343db-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="343db-116">Additional resources</span></span>

[<span data-ttu-id="343db-117">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="343db-117">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
