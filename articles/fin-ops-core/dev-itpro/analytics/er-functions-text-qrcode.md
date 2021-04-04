---
title: Funzione ER QRCODE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione QRCODE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: 92665936decc87b29f2fabb346f4d16745d0a30b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562663"
---
# <a name="qrcode-er-function"></a><span data-ttu-id="0ca1e-103">Funzione ER QRCODE</span><span class="sxs-lookup"><span data-stu-id="0ca1e-103">QRCODE ER function</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ca1e-104">La funzione `QRCODE` restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-104">The `QRCODE` function returns a *Container* value that presents the Quick Response code (QR code) image for the specified string in binary format.</span></span>

## <a name="syntax"></a><span data-ttu-id="0ca1e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0ca1e-105">Syntax</span></span>

```vb
QRCODE (text)
```

## <a name="arguments"></a><span data-ttu-id="0ca1e-106">Argomenti</span><span class="sxs-lookup"><span data-stu-id="0ca1e-106">Arguments</span></span>

<span data-ttu-id="0ca1e-107">`text`: *Stringa*</span><span class="sxs-lookup"><span data-stu-id="0ca1e-107">`text`: *String*</span></span>

<span data-ttu-id="0ca1e-108">Un valore *Stringa* che rappresenta il testo originale.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-108">A *String* value that represents the original text.</span></span>

## <a name="return-values"></a><span data-ttu-id="0ca1e-109">Valori restituiti</span><span class="sxs-lookup"><span data-stu-id="0ca1e-109">Return values</span></span>

<span data-ttu-id="0ca1e-110">*Contenitore*</span><span class="sxs-lookup"><span data-stu-id="0ca1e-110">*Container*</span></span>

<span data-ttu-id="0ca1e-111">Il flusso binario risultante.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-111">The resulting binary stream.</span></span>

## <a name="example"></a><span data-ttu-id="0ca1e-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="0ca1e-112">Example</span></span>

<span data-ttu-id="0ca1e-113">È possibile configurare un formato creazione di report elettronici (ER) per generare un documento in uscita nel formato Microsoft Office (cartelle di lavoro Excel o documenti Word) utilizzando un modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-113">You can configure an Electronic reporting (ER) format to generate an outbound document in Microsoft Office format (Excel workbooks or Word documents) by using a predefined template.</span></span> <span data-ttu-id="0ca1e-114">Questo modello può contenere un oggetto **Immagine** (cartella di lavoro Excel) o **Controllo contenuto immagine** (documento Word) come segnaposto per un'immagine di codice QR.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-114">This template may contain a **Picture** object (Excel workbook) or a **Picture Content Control** (Word document) as a placeholder for a QR code image.</span></span> <span data-ttu-id="0ca1e-115">È necessario aggiungere al formato ER configurato un elemento **Cella** che verrà utilizzato per riempire questo segnaposto.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-115">You need to add to the configured ER format a **Cell** element that will be used to fill this placeholder in.</span></span> <span data-ttu-id="0ca1e-116">Per specificare quali informazioni verranno archiviate in un codice QR, è necessario definire un'associazione per questo elemento **Cella**.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-116">To specify what information will be stored in a QR code, you need to define a binding for this **Cell** element.</span></span> <span data-ttu-id="0ca1e-117">Ad esempio, è possibile configurare tale associazione in modo che contenga la seguente espressione:</span><span class="sxs-lookup"><span data-stu-id="0ca1e-117">For example, you can configure such binding as containing the following expression:</span></span>

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

<span data-ttu-id="0ca1e-118">Quando si esegue il formato ER configurato, il valore di testo del campo **LabelText** dell'origine dati **model.ListOfShelfLabels** verrà utilizzato per generare un'immagine del codice QR.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-118">When you run the configured ER format, the text value of the **LabelText** field of the **model.ListOfShelfLabels** data source will be used to generate a QR code image.</span></span> <span data-ttu-id="0ca1e-119">Questa immagine sostituirà un segnaposto dell'immagine del codice QR nel modello di documento usato per generare un documento in uscita.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-119">This image will replace a QR code image placeholder in the document template using to generate an outbound document.</span></span> <span data-ttu-id="0ca1e-120">Quando questa immagine del documento generato viene letta tramite scanner, restituisce il testo che è stato preso dal campo **LabelText** dell'origine dati **model.ListOfShelfLabels**.</span><span class="sxs-lookup"><span data-stu-id="0ca1e-120">When this image of the generated document is scanned, it returns the text that was taken from the **LabelText** field of the **model.ListOfShelfLabels** data source.</span></span> <span data-ttu-id="0ca1e-121">Per ulteriori informazioni, vedere [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)</span><span class="sxs-lookup"><span data-stu-id="0ca1e-121">For more information, see [Embed images and shapes in documents that you generate by using ER](electronic-reporting-embed-images-shapes.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0ca1e-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0ca1e-122">Additional resources</span></span>

[<span data-ttu-id="0ca1e-123">Funzioni di testo</span><span class="sxs-lookup"><span data-stu-id="0ca1e-123">Text functions</span></span>](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]