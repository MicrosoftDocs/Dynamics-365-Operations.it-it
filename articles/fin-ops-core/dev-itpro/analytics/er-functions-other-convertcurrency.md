---
title: Funzione ER CONVERTCURRENCY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONVERTCURRENCY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: 1d0c168e07252f7c423271bc808f3fca3834077f
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041517"
---
# <span data-ttu-id="75189-103"><a name="CONVERTCURRENCY">Funzione ER CONVERTCURRENCY</a></span><span class="sxs-lookup"><span data-stu-id="75189-103"><a name="CONVERTCURRENCY">CONVERTCURRENCY ER function</a></span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="75189-104">La funzione `CONVERTCURRENCY` restituisce un valore *Reale* che rappresenta il risultato della conversione dell'importo monetario specificato dalla valuta di origine specificata nella valuta di destinazione specificata utilizzando le impostazioni della società specificata alla data specificata.</span><span class="sxs-lookup"><span data-stu-id="75189-104">The `CONVERTCURRENCY` function returns a *Real* value that represents the result of converting the specified monetary amount from the specified source currency to the specified target currency by using the settings of the specified company on the specified date.</span></span>

## <a name="syntax"></a><span data-ttu-id="75189-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="75189-105">Syntax</span></span>

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a><span data-ttu-id="75189-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="75189-106">Arguments</span></span>

<span data-ttu-id="75189-107">`amount`: *Intero* o *Intero*</span><span class="sxs-lookup"><span data-stu-id="75189-107">`amount`: *Integer* or *Real*</span></span>

<span data-ttu-id="75189-108">Un valore numerico che rappresenta l'importo monetario che deve essere convertito.</span><span class="sxs-lookup"><span data-stu-id="75189-108">A numeric value that represents the monetary amount that must be converted.</span></span>

<span data-ttu-id="75189-109">`source currency`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="75189-109">`source currency`: *String*</span></span>

<span data-ttu-id="75189-110">Il codice della valuta di origine.</span><span class="sxs-lookup"><span data-stu-id="75189-110">The code of the source currency.</span></span>

<span data-ttu-id="75189-111">`target currency`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="75189-111">`target currency`: *String*</span></span>

<span data-ttu-id="75189-112">Il codice della valuta di destinazione.</span><span class="sxs-lookup"><span data-stu-id="75189-112">The code of the target currency.</span></span>

<span data-ttu-id="75189-113">`date`: *Data*</span><span class="sxs-lookup"><span data-stu-id="75189-113">`date`: *Date*</span></span>

<span data-ttu-id="75189-114">Un valore *Data* che rappresenta la data utilizzata per determinare il tasso di cambio per la conversione.</span><span class="sxs-lookup"><span data-stu-id="75189-114">A *Date* value that represents the date that is used to determine the exchange rate for the conversion.</span></span>

<span data-ttu-id="75189-115">`company`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="75189-115">`company`: *String*</span></span>

<span data-ttu-id="75189-116">Un valore *Stringa* che rappresenta il codice di una società che fornisce le impostazioni utilizzate per la conversione.</span><span class="sxs-lookup"><span data-stu-id="75189-116">A *String* value that represents the code of a company that supplies the settings that are used for the conversion.</span></span>

## <a name="return-values"></a><span data-ttu-id="75189-117">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="75189-117">Return values</span></span>

<span data-ttu-id="75189-118">*Reale*</span><span class="sxs-lookup"><span data-stu-id="75189-118">*Real*</span></span>

<span data-ttu-id="75189-119">Il valore numerico risultante.</span><span class="sxs-lookup"><span data-stu-id="75189-119">The resulting numeric value.</span></span>

## <a name="example"></a><span data-ttu-id="75189-120">Esempio</span><span class="sxs-lookup"><span data-stu-id="75189-120">Example</span></span>

<span data-ttu-id="75189-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` restituisce un equivalente di un euro in dollari statunitensi nella data della sessione corrente, in base alle impostazioni per la società **DEMF**.</span><span class="sxs-lookup"><span data-stu-id="75189-121">`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` returns the equivalent of one euro in US dollars on the current session date, based on settings for the **DEMF** company.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="75189-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="75189-122">Additional resources</span></span>

[<span data-ttu-id="75189-123">Altre funzioni (specifiche del dominio aziendale)</span><span class="sxs-lookup"><span data-stu-id="75189-123">Other (business domain–specific) functions</span></span>](er-functions-category-other.md)
