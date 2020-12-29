---
title: Funzione ER ALLITEMS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione ALLITEMS della creazione di report elettronici (ER).
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
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 15ab88512e49b51dbefa19056c3e1846715dcadb
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687770"
---
# <a name="allitems-er-function"></a><span data-ttu-id="fa931-103">Funzione ER ALLITEMS</span><span class="sxs-lookup"><span data-stu-id="fa931-103">ALLITEMS ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fa931-104">La funzione `ALLITEMS` viene eseguita come una selezione in memoria e restituisce un nuovo valore bidimensionale *Elenco di record* come un elenco di record che rappresenta tutti gli elementi che corrispondono al percorso specificato.</span><span class="sxs-lookup"><span data-stu-id="fa931-104">The `ALLITEMS` function runs as an in-memory selection and returns a new flattened *Record list* value as a list of records that represents all items that match the specified path.</span></span>

## <a name="syntax"></a><span data-ttu-id="fa931-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fa931-105">Syntax</span></span>

```vb
ALLITEMS (path)
```

## <a name="arguments"></a><span data-ttu-id="fa931-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="fa931-106">Arguments</span></span>

<span data-ttu-id="fa931-107">`path`: *Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fa931-107">`path`: *Record list*</span></span>

<span data-ttu-id="fa931-108">Il percorso valido di un'origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fa931-108">The valid path of a data source of the *Record list* data type.</span></span>

## <a name="return-values"></a><span data-ttu-id="fa931-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="fa931-109">Return values</span></span>

<span data-ttu-id="fa931-110">*Elenco di record*</span><span class="sxs-lookup"><span data-stu-id="fa931-110">*Record list*</span></span>

<span data-ttu-id="fa931-111">L'elenco risultante di record.</span><span class="sxs-lookup"><span data-stu-id="fa931-111">The resulting list of records.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="fa931-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="fa931-112">Usage notes</span></span>

<span data-ttu-id="fa931-113">Il percorso deve essere definito come percorso di un'origine dati valido in un elemento di origine dati del tipo di dati *Elenco di record*.</span><span class="sxs-lookup"><span data-stu-id="fa931-113">The path must be defined as a valid data source path of a data source element of the *Record list* data type.</span></span> <span data-ttu-id="fa931-114">Gli elementi di dati come stringa del percorso e la data devono generare un errore in fase di progettazione nel generatore di espressioni ER.</span><span class="sxs-lookup"><span data-stu-id="fa931-114">Data elements such as the path string and date should raise an error in the Electronic reporting (ER) expression builder at design time.</span></span>

<span data-ttu-id="fa931-115">Non è consigliabile utilizzare questa funzione per origini dati transazionali che potrebbero contenere un grande volume di dati.</span><span class="sxs-lookup"><span data-stu-id="fa931-115">We don't recommend that you use this function for transactional data sources that might contain a large volume of data.</span></span> <span data-ttu-id="fa931-116">Considerare invece l'utilizzo della funzione [ALLTEMSQUERY ](er-functions-list-allitemsquery.md).</span><span class="sxs-lookup"><span data-stu-id="fa931-116">Instead, consider using the [ALLTEMSQUERY](er-functions-list-allitemsquery.md) function.</span></span>

## <a name="example-1"></a><span data-ttu-id="fa931-117">Esempio 1</span><span class="sxs-lookup"><span data-stu-id="fa931-117">Example 1</span></span>

<span data-ttu-id="fa931-118">Se si immette `SPLIT("abcdef" , 2)`come origine dati **DS**, l'espressione `COUNT( ALLITEMS (DS))` restituisce **3**.</span><span class="sxs-lookup"><span data-stu-id="fa931-118">If you enter `SPLIT("abcdef" , 2)` as data source **DS**, the expression `COUNT( ALLITEMS (DS))` returns **3**.</span></span>

## <a name="example-2"></a><span data-ttu-id="fa931-119">Esempio 2</span><span class="sxs-lookup"><span data-stu-id="fa931-119">Example 2</span></span>

<span data-ttu-id="fa931-120">Se si immette **Vend** come origine dati del tipo di dati *Elenco di record* che fa riferimento alla tabella dell'applicazione VendTable, l'espressione `ALLITEMS (Vend.'<Relations'.ContactPerson)` restituisce un elenco bidimensionale di record che ha struttura della tabella **ContactPerson** e contiene tutti i contatti a cui è possibile accedere utilizzando la relazione **ContactPerson.ContactForParty == VendTable.Party**, disponibile per tutti i fornitori dalla tabella fornitori di riferimento.</span><span class="sxs-lookup"><span data-stu-id="fa931-120">If you enter **Vend** as the data source of the *Record list* data type that refers to the VendTable application table, the expression `ALLITEMS (Vend.'<Relations'.ContactPerson)` returns a flattened list of records that has the **ContactPerson** table structure and contains all contact persons that can be accessed by using the **ContactPerson.ContactForParty == VendTable.Party** relation, and that is available for all vendors from the referenced vendor table.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa931-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="fa931-121">Additional resources</span></span>

[<span data-ttu-id="fa931-122">Funzioni di elenco</span><span class="sxs-lookup"><span data-stu-id="fa931-122">List functions</span></span>](er-functions-category-list.md)
