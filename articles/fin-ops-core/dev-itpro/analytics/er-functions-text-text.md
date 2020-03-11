---
title: Funzione ER TEXT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TEXT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: c08aca949ffc7e62009bf3f6c664d96b368f43e7
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040897"
---
# <span data-ttu-id="38c72-103"><a name="TEXT">Funzione ER TEXT</a></span><span class="sxs-lookup"><span data-stu-id="38c72-103"><a name="TEXT">TEXT ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="38c72-104">La funzione `TEXT` restituisce il numero specificato come un valore *Stringa* dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="38c72-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="38c72-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38c72-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="38c72-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="38c72-106">Arguments</span></span>

<span data-ttu-id="38c72-107">`number`: *Intero* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="38c72-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="38c72-108">Un numero che deve essere convertito in una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="38c72-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="38c72-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="38c72-109">Return values</span></span>

<span data-ttu-id="38c72-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="38c72-110">*String*</span></span>

<span data-ttu-id="38c72-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="38c72-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="38c72-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="38c72-112">Usage notes</span></span>

<span data-ttu-id="38c72-113">Per i valori di tipo *Reale*, la conversione di stringhe è limitata a due posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="38c72-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="38c72-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="38c72-114">Example</span></span>

<span data-ttu-id="38c72-115">Se le impostazioni locali server dell'istanza di Microsoft Dynamics 365 Finance sono definite come **EN-US**, `TEXT (NOW ())` restituisce la data della sessione di Finance corrente, 17 dicembre 2015, come stringa di testo **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="38c72-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="38c72-116">`TEXT (1/3)` restituisce **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="38c72-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="38c72-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="38c72-117">Additional resources</span></span>

[<span data-ttu-id="38c72-118">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="38c72-118">Text functions</span></span>](er-functions-category-text.md)
