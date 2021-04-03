---
title: Elenco delle funzioni ER nella categoria raccolta dati
description: Questo argomento fornisce informazioni sulle funzioni di raccolta dati supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/04/2019
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
ms.openlocfilehash: ba3a1f031a4a98592081b04a4128450aeb8218ef
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5561736"
---
# <a name="list-of-er-functions-in-the-data-collection-category"></a><span data-ttu-id="e0951-103">Elenco delle funzioni ER nella categoria raccolta dati</span><span class="sxs-lookup"><span data-stu-id="e0951-103">List of ER functions in the data collection category</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e0951-104">Le funzioni di raccolta dati della creazione di report elettronici (ER) vengono utilizzate per eseguire il conteggio e la somma in un formato ER in esecuzione, in base ai dati dell'output già generati in formato **Testo** o **Xml**.</span><span class="sxs-lookup"><span data-stu-id="e0951-104">Electronic reporting (ER) data collection functions are used to do counting and summing in an ER format that is being run, based on data of the output that has already been generated in **Text** or **Xml** format.</span></span> <span data-ttu-id="e0951-105">Questo approccio viene utilizzato per migliorare le prestazioni di un formato ER in esecuzione, per immettere valori di totali in esecuzione nei documenti generati e per altri scopi.</span><span class="sxs-lookup"><span data-stu-id="e0951-105">This approach is used to help improve performance of an ER format that is run, to enter values of running totals in generated documents, and for other purposes.</span></span> <span data-ttu-id="e0951-106">Questo argomento fornisce un riepilogo di queste funzioni.</span><span class="sxs-lookup"><span data-stu-id="e0951-106">This topic provides a summary of these functions.</span></span>

## <a name="list-of-supported-functions"></a><span data-ttu-id="e0951-107">Elenco delle funzioni supportate</span><span class="sxs-lookup"><span data-stu-id="e0951-107">List of supported functions</span></span>

| <span data-ttu-id="e0951-108">Funzione</span><span class="sxs-lookup"><span data-stu-id="e0951-108">Function</span></span> | <span data-ttu-id="e0951-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e0951-109">Description</span></span> |
|----------|-------------|
| [<span data-ttu-id="e0951-110">CollectedList</span><span class="sxs-lookup"><span data-stu-id="e0951-110">CollectedList</span></span>](er-functions-datacollection-collectedlist.md) | <span data-ttu-id="e0951-111">Questa funzione restituisce un valore *Elenco di record* che contiene l'elenco di valori restituiti dalla proprietà **Valore chiave dati raccolti** degli elementi di formato e raccolti quando gli elementi di formato sono stati utilizzati per generare un documento in uscita durante l'esecuzione e ciò soddisfa le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="e0951-111">This function returns a *Record list* value that contains the list of values that were returned by the **Collected data key value** property of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="e0951-112">Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="e0951-112">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="e0951-113">CountIF</span><span class="sxs-lookup"><span data-stu-id="e0951-113">CountIF</span></span>](er-functions-datacollection-countif.md) | <span data-ttu-id="e0951-114">Questa funzione restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="e0951-114">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="e0951-115">La condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="e0951-115">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="e0951-116">CountIFs</span><span class="sxs-lookup"><span data-stu-id="e0951-116">CountIFs</span></span>](er-functions-datacollection-countifs.md) | <span data-ttu-id="e0951-117">Questa funzione restituisce un valore *Intero* che rappresenta il numero di elementi di formato raccolti quando sono stati utilizzati per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="e0951-117">This function returns an *Integer* value that represents the number of format elements that was collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="e0951-118">Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="e0951-118">Each condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="e0951-119">FormatElementName</span><span class="sxs-lookup"><span data-stu-id="e0951-119">FormatElementName</span></span>](er-functions-datacollection-formatelementname.md) | <span data-ttu-id="e0951-120">Questa funzione restituisce un valore *Stringa* che rappresenta il nome dell'elemento del formato ER corrente.</span><span class="sxs-lookup"><span data-stu-id="e0951-120">This function returns a *String* value that represents the name of the current ER format's element.</span></span> |
| [<span data-ttu-id="e0951-121">SumIF</span><span class="sxs-lookup"><span data-stu-id="e0951-121">SumIF</span></span>](er-functions-datacollection-sumif.md) | <span data-ttu-id="e0951-122">Questa funzione restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati elementi di formato per generare un documento in uscita durante l'esecuzione del formato e che soddisfano la condizione specificata.</span><span class="sxs-lookup"><span data-stu-id="e0951-122">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified condition.</span></span> <span data-ttu-id="e0951-123">La condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="e0951-123">The condition consists of a key range and a key value.</span></span> |
| [<span data-ttu-id="e0951-124">SumIFs</span><span class="sxs-lookup"><span data-stu-id="e0951-124">SumIFs</span></span>](er-functions-datacollection-sumifs.md) | <span data-ttu-id="e0951-125">Questa funzione restituisce un valore *Reale* che rappresenta la somma dei valori restituiti da associazioni di elementi di formato e raccolti quando sono stati utilizzati elementi di formato per generare un documento in uscita durante l'esecuzione del formato e che soddisfano le condizioni specificate.</span><span class="sxs-lookup"><span data-stu-id="e0951-125">This function returns a *Real* value that represents the sum of values that were returned by bindings of format elements and collected when the format elements were used to generate an outbound document during the format run, and that satisfies the specified conditions.</span></span> <span data-ttu-id="e0951-126">Ogni condizione è costituita da un intervallo di chiavi e un valore chiave.</span><span class="sxs-lookup"><span data-stu-id="e0951-126">Each condition consists of a key range and a key value.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="e0951-127">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="e0951-127">Additional resources</span></span>

[<span data-ttu-id="e0951-128">Panoramica sui report elettronici</span><span class="sxs-lookup"><span data-stu-id="e0951-128">Electronic Reporting overview</span></span>](general-electronic-reporting.md)

[<span data-ttu-id="e0951-129">Designer formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="e0951-129">Formula designer in Electronic reporting</span></span>](general-electronic-reporting-formula-designer.md)

[<span data-ttu-id="e0951-130">Linguaggio della formula nella creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="e0951-130">Electronic reporting formula language</span></span>](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]