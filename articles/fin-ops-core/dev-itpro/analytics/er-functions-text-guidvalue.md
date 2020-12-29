---
title: Funzione ER GUIDVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GUIDVALUE della creazione di report elettronici (ER).
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
ms.openlocfilehash: eb6f301cf7a39208aa23337401a9684fb5b3a73d
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685956"
---
# <a name="guidvalue-er-function"></a><span data-ttu-id="6246b-103">Funzione ER GUIDVALUE</span><span class="sxs-lookup"><span data-stu-id="6246b-103">GUIDVALUE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6246b-104">La funzione `GUIDVALUE` converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*.</span><span class="sxs-lookup"><span data-stu-id="6246b-104">The `GUIDVALUE` function converts the specified input of the *String* type to a data item of the *GUID* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="6246b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6246b-105">Syntax</span></span>

```vb
GUIDVALUE (input)
```

## <a name="arguments"></a><span data-ttu-id="6246b-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="6246b-106">Arguments</span></span>

<span data-ttu-id="6246b-107">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="6246b-107">`input`: *String*</span></span>

<span data-ttu-id="6246b-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="6246b-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="6246b-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="6246b-109">Return values</span></span>

<span data-ttu-id="6246b-110">*GUID*</span><span class="sxs-lookup"><span data-stu-id="6246b-110">*GUID*</span></span>

<span data-ttu-id="6246b-111">Il valore dell'identificatore univoco globale (GUID) risultante.</span><span class="sxs-lookup"><span data-stu-id="6246b-111">The resulting globally unique identifier (GUID) value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6246b-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="6246b-112">Usage notes</span></span>

<span data-ttu-id="6246b-113">Per impostare una conversione nella direzione opposta (ovvero convertire l'input specificato del tipo di dati *GUID* in un elemento dati di tipo *Stringa*), è possibile usare la funzione [TEXT](er-functions-text-text.md).</span><span class="sxs-lookup"><span data-stu-id="6246b-113">To do a conversion in the opposite direction (that is, to convert specified input of the *GUID* data type to a data item of the *String* data type), you can use the [TEXT](er-functions-text-text.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="6246b-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="6246b-114">Example</span></span>

<span data-ttu-id="6246b-115">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="6246b-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="6246b-116">Un'origine dati **myID** del tipo *Campo calcolato* che contiene l'espressione `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span><span class="sxs-lookup"><span data-stu-id="6246b-116">A **myID** data source of the *Calculated field* type that contains the expression `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`</span></span>
- <span data-ttu-id="6246b-117">Un'origine dati **Users** del tipo *Record di tabella* che fa riferimento alla tabella UserInfo</span><span class="sxs-lookup"><span data-stu-id="6246b-117">A **Users** data source of the *Table records* type that refers to the UserInfo table</span></span>

<span data-ttu-id="6246b-118">È quindi possibile utilizzare un'espressione come `FILTER (Users, Users.objectId = myID)` per filtrare la tabella UserInfo in base al campo **objectId** del tipo di dati *GUID*.</span><span class="sxs-lookup"><span data-stu-id="6246b-118">You can then use an expression such as `FILTER (Users, Users.objectId = myID)` to filter the UserInfo table by the **objectId** field of the *GUID* data type.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6246b-119">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6246b-119">Additional resources</span></span>

[<span data-ttu-id="6246b-120">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="6246b-120">Text functions</span></span>](er-functions-category-text.md)
