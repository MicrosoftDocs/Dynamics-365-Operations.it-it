---
title: Funzione ER Base64StringToContainer
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione Base64StringToContainer della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/14/2020
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
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 6fd08d9a2522bdf497b1926c884a4583065d9f19
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754376"
---
# <a name="base64stringtocontainer-er-function"></a><span data-ttu-id="a08ec-103">Funzione ER Base64StringToContainer</span><span class="sxs-lookup"><span data-stu-id="a08ec-103">Base64StringToContainer ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a08ec-104">La [funzione](er-formula-language.md#functions) `BASE64STRINGTOCONTAINER` converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *[Contenitore](er-functions-category-container.md)*.</span><span class="sxs-lookup"><span data-stu-id="a08ec-104">The `BASE64STRINGTOCONTAINER` [function](er-formula-language.md#functions) converts the specified input of the *String* type to a data item of the *[Container](er-functions-category-container.md)* type.</span></span>

## <a name="syntax"></a><span data-ttu-id="a08ec-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a08ec-105">Syntax</span></span>

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a><span data-ttu-id="a08ec-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a08ec-106">Arguments</span></span>

<span data-ttu-id="a08ec-107">`input`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="a08ec-107">`input`: *String*</span></span>

<span data-ttu-id="a08ec-108">Il percorso valido di un'origine dati del tipo *Stringa*.</span><span class="sxs-lookup"><span data-stu-id="a08ec-108">The valid path of a data source of the *String* type.</span></span>

## <a name="return-values"></a><span data-ttu-id="a08ec-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="a08ec-109">Return values</span></span>

<span data-ttu-id="a08ec-110">*Container*</span><span class="sxs-lookup"><span data-stu-id="a08ec-110">*Container*</span></span>

<span data-ttu-id="a08ec-111">Il valore binario ottenuto in formato BLOB (Binary Large Object).</span><span class="sxs-lookup"><span data-stu-id="a08ec-111">The resulting binary value in binary large object (BLOB) format.</span></span>

## <a name="usage-notes"></a><span data-ttu-id="a08ec-112">Note sull'utilizzo</span><span class="sxs-lookup"><span data-stu-id="a08ec-112">Usage notes</span></span>

<span data-ttu-id="a08ec-113">L'eccezione "Il parametro non è valido" viene generata se la stringa di input non fornisce un gruppo Base64 corretto di schemi di codifica da binario a testo.</span><span class="sxs-lookup"><span data-stu-id="a08ec-113">The "Parameter is not valid" exception is thrown if the input string doesn't provide a correct Base64 group of binary-to-text encoding schemes.</span></span>

## <a name="example"></a><span data-ttu-id="a08ec-114">Esempio</span><span class="sxs-lookup"><span data-stu-id="a08ec-114">Example</span></span>

<span data-ttu-id="a08ec-115">Definire le origini dati seguenti nel mapping di modello:</span><span class="sxs-lookup"><span data-stu-id="a08ec-115">You define the following data sources in your model mapping:</span></span>

- <span data-ttu-id="a08ec-116">L'origine dati **DocuTypeGroupEnum** radice del tipo *Dynamics 365 for Operations/Enumerazione* che fa riferimento all'enumerazione di applicazione **DocuTypeGroup**</span><span class="sxs-lookup"><span data-stu-id="a08ec-116">The root **DocuTypeGroupEnum** data source of the *Dynamics 365 for Operations / Enumeration* type that refers to the **DocuTypeGroup** application enumeration</span></span>
- <span data-ttu-id="a08ec-117">L'origine dati **Cliente** radice del tipo *Dynamics 365 for Operations/record di tabella* che fa riferimento alla tabella delle applicazioni **CustTable**</span><span class="sxs-lookup"><span data-stu-id="a08ec-117">The root **Customer** data source of the *Dynamics 365 for Operations / Table records* type that refers to the **CustTable** application table</span></span>
- <span data-ttu-id="a08ec-118">L'origine dati **\#Media** del tipo *Campo calcolato* che si configura nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a08ec-118">The **\#Media** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="a08ec-119">Viene aggiunto come origine dati figlio dell'origine dati **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="a08ec-119">It's added as a child data source of the **Customer** data source.</span></span>
    - <span data-ttu-id="a08ec-120">Contiene l'espressione `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span><span class="sxs-lookup"><span data-stu-id="a08ec-120">It contains the expression `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.</span></span>

- <span data-ttu-id="a08ec-121">L'origine dati **\#MediaAsBase64String** del tipo *Campo calcolato* che si configura nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a08ec-121">The **\#MediaAsBase64String** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="a08ec-122">Viene aggiunto come origine dati figlio dell'origine dati **Cliente"\#Media"**.</span><span class="sxs-lookup"><span data-stu-id="a08ec-122">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="a08ec-123">Contiene l'espressione `Customer.'#Media'.'getFileContentAsBase64String()'`.</span><span class="sxs-lookup"><span data-stu-id="a08ec-123">It contains the expression `Customer.'#Media'.'getFileContentAsBase64String()'`.</span></span>

- <span data-ttu-id="a08ec-124">L'origine dati **\#BlobFomBase64** del tipo *Campo calcolato* che si configura nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="a08ec-124">The **\#BlobFomBase64** data source of the *Calculated field* type that is configured in the following way:</span></span>

    - <span data-ttu-id="a08ec-125">Viene aggiunto come origine dati figlio dell'origine dati **Cliente"\#Media"**.</span><span class="sxs-lookup"><span data-stu-id="a08ec-125">It's added as a child data source of the **Customer.'\#Media'** data source.</span></span>
    - <span data-ttu-id="a08ec-126">Contiene l'espressione `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span><span class="sxs-lookup"><span data-stu-id="a08ec-126">It contains the expression `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.</span></span>

<span data-ttu-id="a08ec-127">In questo esempio, l'origine dati **\#MediaAsBase64String** codifica il contenuto binario dell'allegato multimediale corrente come testo che rappresenta un gruppo Base64 di schemi di codifica da binario a testo.</span><span class="sxs-lookup"><span data-stu-id="a08ec-127">In this example, the **\#MediaAsBase64String** data source encodes the binary content of the current media attachment as text that represents a Base64 group of binary-to-text encoding schemes.</span></span> <span data-ttu-id="a08ec-128">L'origine dati **\#BlobFomBase64** decodifica la stringa Base64 e restituisce un valore binario in formato BLOB.</span><span class="sxs-lookup"><span data-stu-id="a08ec-128">The **\#BlobFomBase64** data source decodes the Base64 string and returns a binary value in BLOB format.</span></span>

![Origini dati di esempio nella pagina di progettazione del mapping del modello ER](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a><span data-ttu-id="a08ec-130">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="a08ec-130">Additional resources</span></span>

[<span data-ttu-id="a08ec-131">Funzioni contenitore</span><span class="sxs-lookup"><span data-stu-id="a08ec-131">Container functions</span></span>](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]