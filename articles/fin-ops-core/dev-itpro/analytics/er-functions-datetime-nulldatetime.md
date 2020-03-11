---
title: Funzione ER NULLDATETIME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NULLDATETIME della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: 3cd4c152d4e220a2f6315265ed5e44d148134279
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042261"
---
# <span data-ttu-id="9b5ca-103"><a name="NULLDATETIME">Funzione ER NULLDATETIME</a></span><span class="sxs-lookup"><span data-stu-id="9b5ca-103"><a name="NULLDATETIME">NULLDATETIME ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b5ca-104">La funzione `NULLDATETIME` restituisce un valore *DateTime* che rappresenta il valore data/ora **null** (1 gennaio 1900) in Coordinated Universal Time (Ora di Greenwich \[GMT\]).</span><span class="sxs-lookup"><span data-stu-id="9b5ca-104">The `NULLDATETIME` function returns a *DateTime* value that represents the **null** date/time value (January 1, 1900) in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).</span></span>

## <a name="syntax"></a><span data-ttu-id="9b5ca-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9b5ca-105">Syntax</span></span>

```vb
NULLDATETIME ()
```

## <a name="return-values"></a><span data-ttu-id="9b5ca-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="9b5ca-106">Return values</span></span>

<span data-ttu-id="9b5ca-107">*Data/Ora*</span><span class="sxs-lookup"><span data-stu-id="9b5ca-107">*DateTime*</span></span>

<span data-ttu-id="9b5ca-108">Il valore di data/ora risultante.</span><span class="sxs-lookup"><span data-stu-id="9b5ca-108">The resulting date/time value.</span></span>

## <a name="example"></a><span data-ttu-id="9b5ca-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="9b5ca-109">Example</span></span>

<span data-ttu-id="9b5ca-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` restituisce il valore della stringa **1900-01-01T00:00:00.0000000+00:00** quando viene richiamato durante un processo avviato da un utente dell'applicazione che ha il valore del fuso orario **(GMT) Coordinated Universal Time** nella sezione **Preferenze di lingua e paese**.</span><span class="sxs-lookup"><span data-stu-id="9b5ca-110">`DATETIMEFORMAT( NULLDATETIME(), "O")` returns the string value **1900-01-01T00:00:00.0000000+00:00** when it's called during a process that was initiated by an application user who has the time zone value **(GMT) Coordinated Universal Time** in the **Language and country/region preferences** section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9b5ca-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="9b5ca-111">Additional resources</span></span>

[<span data-ttu-id="9b5ca-112">Funzioni di data e ora</span><span class="sxs-lookup"><span data-stu-id="9b5ca-112">Date and time functions</span></span>](er-functions-category-datetime.md)
