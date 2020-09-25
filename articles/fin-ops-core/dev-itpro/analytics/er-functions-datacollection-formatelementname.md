---
title: Funzione ER FORMATELEMENTNAME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FORMATELEMENTNAME della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e8be55d9a90e841d64288b0c618c0012912ddbab
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3745635"
---
# <a name="formatelementname-er-function"></a><span data-ttu-id="6eb8f-103">Funzione ER FORMATELEMENTNAME</span><span class="sxs-lookup"><span data-stu-id="6eb8f-103">FORMATELEMENTNAME ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6eb8f-104">La funzione `FORMATELEMENTNAME` restituisce un valore *Stringa* che rappresenta il nome dell'elemento del formato corrente della creazione di report elettronici (ER).</span><span class="sxs-lookup"><span data-stu-id="6eb8f-104">The `FORMATELEMENTNAME` function returns a *String* value that represents the name of the current Electronic reporting (ER) format's element.</span></span>

## <a name="syntax"></a><span data-ttu-id="6eb8f-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6eb8f-105">Syntax</span></span>

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a><span data-ttu-id="6eb8f-106">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="6eb8f-106">Return values</span></span>

<span data-ttu-id="6eb8f-107">*Stringa*</span><span class="sxs-lookup"><span data-stu-id="6eb8f-107">*String*</span></span>

<span data-ttu-id="6eb8f-108">Il valore di testo risultante.</span><span class="sxs-lookup"><span data-stu-id="6eb8f-108">The resulting text value.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="6eb8f-109">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="6eb8f-109">Usage notes</span></span>

<span data-ttu-id="6eb8f-110">Questa funzione può essere richiamata in espressioni ER configurate per le proprietà **Nome chiave dati raccolti** e **Valore chiave dati raccolti** di un componente del formato ER dal gruppo **Text** che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.</span><span class="sxs-lookup"><span data-stu-id="6eb8f-110">This function can be called in ER expressions that were configured for the **Collected data key name** and **Collected data key value** properties of an ER format component from the **Text** group that resides under the **Common\\File** component where the **Collect output details** option is turned on.</span></span>

## <a name="example"></a><span data-ttu-id="6eb8f-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="6eb8f-111">Example</span></span>

<span data-ttu-id="6eb8f-112">Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.</span><span class="sxs-lookup"><span data-stu-id="6eb8f-112">For more information about how to use this function, see the [ER Use data of format output for counting and summing](tasks/er-format-counting-summing-1.md) task guide, which is part of the **Acquire/Develop IT service/solution components** business process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6eb8f-113">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="6eb8f-113">Additional resources</span></span>

[<span data-ttu-id="6eb8f-114">Funzioni raccolta dati</span><span class="sxs-lookup"><span data-stu-id="6eb8f-114">Data collection functions</span></span>](er-functions-category-data-collection.md)
