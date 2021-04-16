---
title: Funzione ER TEXT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TEXT della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 0694480f5d6892d13fe0c0d9ad191cdf2332dfec
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746101"
---
# <a name="text-er-function"></a><span data-ttu-id="13cde-103">Funzione ER TEXT</span><span class="sxs-lookup"><span data-stu-id="13cde-103">TEXT ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="13cde-104">La funzione `TEXT` restituisce il numero specificato come un valore *Stringa* dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="13cde-104">The `TEXT` function returns the specified number as a *String* value after it has been converted to a text string that is formatted according to the server locale settings of the current application instance.</span></span>

## <a name="syntax"></a><span data-ttu-id="13cde-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13cde-105">Syntax</span></span>

```vb
TEXT (number)
```

## <a name="arguments"></a><span data-ttu-id="13cde-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="13cde-106">Arguments</span></span>

<span data-ttu-id="13cde-107">`number`: *Intero* o *Reale*</span><span class="sxs-lookup"><span data-stu-id="13cde-107">`number`: *Integer* or *Real*</span></span>

<span data-ttu-id="13cde-108">Un numero che deve essere convertito in una stringa di testo.</span><span class="sxs-lookup"><span data-stu-id="13cde-108">A number that must be converted to a text string.</span></span>

## <a name="return-values"></a><span data-ttu-id="13cde-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="13cde-109">Return values</span></span>

<span data-ttu-id="13cde-110">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="13cde-110">*String*</span></span>

<span data-ttu-id="13cde-111">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="13cde-111">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="13cde-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="13cde-112">Usage notes</span></span>

<span data-ttu-id="13cde-113">Per i valori di tipo *Reale*, la conversione di stringhe è limitata a due posizioni decimali.</span><span class="sxs-lookup"><span data-stu-id="13cde-113">For values of the *Real* type, the string conversion is limited to two decimal places.</span></span>

## <a name="example"></a><span data-ttu-id="13cde-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="13cde-114">Example</span></span>

<span data-ttu-id="13cde-115">Se le impostazioni locali server dell'istanza di Microsoft Dynamics 365 Finance sono definite come **EN-US**, `TEXT (NOW ())` restituisce la data della sessione di Finance corrente, 17 dicembre 2015, come stringa di testo **"12/17/2015 07:59:23 AM"**.</span><span class="sxs-lookup"><span data-stu-id="13cde-115">If the server locale of the Microsoft Dynamics 365 Finance instance is defined as **EN-US**, `TEXT (NOW ())` returns the current Finance session date, December 17, 2015, as the text string **"12/17/2015 07:59:23 AM"**.</span></span> <span data-ttu-id="13cde-116">`TEXT (1/3)` restituisce **"0.33"**.</span><span class="sxs-lookup"><span data-stu-id="13cde-116">`TEXT (1/3)` returns **"0.33"**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13cde-117">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="13cde-117">Additional resources</span></span>

[<span data-ttu-id="13cde-118">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="13cde-118">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]