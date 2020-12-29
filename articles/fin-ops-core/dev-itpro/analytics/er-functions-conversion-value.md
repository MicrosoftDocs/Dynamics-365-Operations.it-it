---
title: Funzione ER VALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione VALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 56b32a802674725347ab496d3a09b99c8f04446d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681210"
---
# <a name="value-er-function"></a><span data-ttu-id="df0a0-103">Funzione ER VALUE</span><span class="sxs-lookup"><span data-stu-id="df0a0-103">VALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="df0a0-104">La funzione `VALUE` restituisce un valore *Reale* che viene convertito dalla stringa specificata.</span><span class="sxs-lookup"><span data-stu-id="df0a0-104">The `VALUE` function returns a *Real* value that is converted from the specified string.</span></span>

## <a name="syntax"></a><span data-ttu-id="df0a0-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="df0a0-105">Syntax</span></span>

```vb
VALUE (text)
```

## <a name="arguments"></a><span data-ttu-id="df0a0-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="df0a0-106">Arguments</span></span>

<span data-ttu-id="df0a0-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="df0a0-107">`text`: *String*</span></span>

<span data-ttu-id="df0a0-108">Un valore stringa che deve essere convertito in un valore numerico.</span><span class="sxs-lookup"><span data-stu-id="df0a0-108">A string value that must be converted to a numeric value.</span></span>

## <a name="return-values"></a><span data-ttu-id="df0a0-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="df0a0-109">Return values</span></span>

<span data-ttu-id="df0a0-110">*Reale*</span><span class="sxs-lookup"><span data-stu-id="df0a0-110">*Real*</span></span>

<span data-ttu-id="df0a0-111">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="df0a0-111">The resulting numeric value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="df0a0-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="df0a0-112">Usage notes</span></span>

<span data-ttu-id="df0a0-113">Le virgole e i caratteri punto (). vengono considerati separatori decimali e un trattino iniziale (-) viene utilizzato come negativo.</span><span class="sxs-lookup"><span data-stu-id="df0a0-113">Commas and dot characters (.) are considered decimal separators, and a leading hyphen (-) is used as a negative sign.</span></span> <span data-ttu-id="df0a0-114">Viene generata un'eccezione in fase di runtime se la stringa specificata contiene altri caratteri non numerici.</span><span class="sxs-lookup"><span data-stu-id="df0a0-114">An exception is thrown at runtime if the specified string contains other non-numeric characters.</span></span>

## <a name="example-1"></a><span data-ttu-id="df0a0-115">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="df0a0-115">Example 1</span></span>

<span data-ttu-id="df0a0-116">`VALUE ("1 234,56")` genera un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="df0a0-116">`VALUE ("1 234,56")` throws an exception.</span></span>

## <a name="example-2"></a><span data-ttu-id="df0a0-117">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="df0a0-117">Example 2</span></span>

<span data-ttu-id="df0a0-118">`VALUE ("1234,56")` restituisce **1234.56**.</span><span class="sxs-lookup"><span data-stu-id="df0a0-118">`VALUE ("1234,56")` returns **1234.56**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df0a0-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="df0a0-119">Additional resources</span></span>

[<span data-ttu-id="df0a0-120">Funzioni di conversione di tipo</span><span class="sxs-lookup"><span data-stu-id="df0a0-120">Type conversion functions</span></span>](er-functions-category-type-conversion.md)
