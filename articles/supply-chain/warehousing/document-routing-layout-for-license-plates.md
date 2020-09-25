---
title: Layout della distribuzione del documento per le etichette della targa
description: Questo argomento descrive come utilizzare i metodi di formattazione per stampare i valori sulle etichette.
author: perlynne
manager: tfehr
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: Release 10.0.10
ms.openlocfilehash: 9af077022ab0759534d2c1da5f39997712e6a354
ms.sourcegitcommit: 965fa733be068dc37f482d02ebbcd77f2c3d0a45
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "3763457"
---
# <a name="document-routing-layout-for-license-plate-labels"></a><span data-ttu-id="5fb2a-103">Layout della distribuzione del documento per le etichette della targa</span><span class="sxs-lookup"><span data-stu-id="5fb2a-103">Document routing layout for license plate labels</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5fb2a-104">Il layout di distribuzione del documento definisce il layout delle etichette della targa e dei dati che vi vengono stampati.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-104">The document routing layout defines the layout of license plate labels, and the data that is printed on them.</span></span> <span data-ttu-id="5fb2a-105">Configurare i punti di attivazione della stampa quando si impostano le voci di menu del dispositivo mobile e i modelli di lavoro.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-105">You configure the printing trigger points when you set up mobile device menu items and work templates.</span></span>

<span data-ttu-id="5fb2a-106">In uno scenario tipico, gli addetti al ricevimento del magazzino stampano le etichette della targa immediatamente dopo aver registrato il contenuto dei pallet che arrivano nell'area di ricevimento.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-106">In a typical scenario, warehouse receiving clerks print license plate labels immediately after they record the contents of pallets that arrive in the receiving area.</span></span> <span data-ttu-id="5fb2a-107">Le etichette fisiche vengono applicate ai pallet.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-107">The physical labels are applied to the pallets.</span></span> <span data-ttu-id="5fb2a-108">Possono quindi essere utilizzati per la convalida come parte del processo di stoccaggio che segue e delle operazioni di prelievo in uscita future.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-108">They can then be used for validation as part of the put-away process that follows and future outbound picking operations.</span></span>

<span data-ttu-id="5fb2a-109">È possibile stampare etichette molto complesse, a condizione che il dispositivo di stampa sia in grado di interpretare il testo che viene inviato.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-109">You can print highly complex labels, provided that the printing device can interpret the text that is sent to it.</span></span> <span data-ttu-id="5fb2a-110">Ad esempio, un layout Zebra Programming Language (ZPL) che include un codice a barre potrebbe assomigliare al seguente esempio.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-110">For example, a Zebra Programming Language (ZPL) layout that includes a bar code might resemble the following example.</span></span>

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

<span data-ttu-id="5fb2a-111">Come parte del processo di stampa delle etichette, il testo `$LicensePlateId$` in questo esempio verrà sostituito con un valore di dati.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-111">As part of the label printing process, the text `$LicensePlateId$` in this example will be replaced with a data value.</span></span>

<span data-ttu-id="5fb2a-112">Per vedere i valori che verranno stampati, andare a **Gestione magazzino \> Richieste di informazioni e report \> Etichette della targa**.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-112">To see the values that will be printed, go to **Warehouse management \> Inquiries and reports \> License plate labels**.</span></span>

<span data-ttu-id="5fb2a-113">Diversi strumenti di generazione di etichette ampiamente disponibili possono aiutare a formattare il testo per il layout dell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-113">Several widely available label generation tools can help you format the text for the label layout.</span></span> <span data-ttu-id="5fb2a-114">Molti di questi strumenti supportano il formato `$FieldName$`.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-114">Many of these tools support the `$FieldName$` format.</span></span> <span data-ttu-id="5fb2a-115">Inoltre, Microsoft Dynamics 365 Supply Chain Management utilizza una logica di formattazione speciale come parte della mappatura dei campi per il layout della distribuzione del documento.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-115">In addition, Microsoft Dynamics 365 Supply Chain Management uses special formatting logic as part of the field mapping for the document routing layout.</span></span>

## <a name="custom-number-formats"></a><span data-ttu-id="5fb2a-116">Formati numerici personalizzati</span><span class="sxs-lookup"><span data-stu-id="5fb2a-116">Custom number formats</span></span>

<span data-ttu-id="5fb2a-117">È possibile personalizzare la formattazione dei valori dei campi numerici che vengono stampati utilizzando i codici che hanno il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-117">You can customize the formatting of numerical field values that are printed by using codes that have the following format.</span></span>

```dos
$FieldName:FormatString$
```

<span data-ttu-id="5fb2a-118">Di seguito è riportata una spiegazione di questo formato:</span><span class="sxs-lookup"><span data-stu-id="5fb2a-118">Here is an explanation of this format:</span></span>

- <span data-ttu-id="5fb2a-119">`FieldName` è il nome del campo dati (ad esempio **Quantità**).</span><span class="sxs-lookup"><span data-stu-id="5fb2a-119">`FieldName` is the name of the data field (such as **Qty**).</span></span>
- <span data-ttu-id="5fb2a-120">`FormatString` definisce come devono essere stampati i dati.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-120">`FormatString` defines how the data must be printed.</span></span>

<span data-ttu-id="5fb2a-121">I seguenti esempi mostrano come personalizzare il campo della quantità di lavoro (**Quantità**):</span><span class="sxs-lookup"><span data-stu-id="5fb2a-121">The following examples show how you can customize the work quantity (**Qty**) field:</span></span>

- <span data-ttu-id="5fb2a-122">Per mostrare sempre quattro cifre (usando zeri come segnaposto) utilizzare `$Qty:0000$`.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-122">To always show four digits (by using zeros as placeholders), use `$Qty:0000$`.</span></span> <span data-ttu-id="5fb2a-123">Ad esempio, se la quantità è 10, l'etichetta mostrerà "0010".</span><span class="sxs-lookup"><span data-stu-id="5fb2a-123">For example, if the quantity is 10, the label will show "0010."</span></span>
- <span data-ttu-id="5fb2a-124">Per mostrare sempre due cifre decimali, utilizzare `$Qty:0.00$`.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-124">To always show two decimal places, use `$Qty:0.00$`.</span></span> <span data-ttu-id="5fb2a-125">Ad esempio, se la quantità è 10, l'etichetta mostrerà "10.00".</span><span class="sxs-lookup"><span data-stu-id="5fb2a-125">For example, if the quantity is 10, the label will show "10.00."</span></span>

<span data-ttu-id="5fb2a-126">Per l'elenco completo delle stringhe di formato numerico disponibili, vedere [Stringhe di formato numerico personalizzate](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span><span class="sxs-lookup"><span data-stu-id="5fb2a-126">For a complete list of the available number format strings, see [Custom numeric format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-numeric-format-strings).</span></span>

## <a name="custom-string-formats"></a><span data-ttu-id="5fb2a-127">Formati di stringa personalizzati</span><span class="sxs-lookup"><span data-stu-id="5fb2a-127">Custom string formats</span></span>

<span data-ttu-id="5fb2a-128">È possibile rimuovere i primi caratteri di una stringa utilizzando il campo e il codice di formato seguenti.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-128">You can remove the first characters of a string by using the following field and format code.</span></span>

```dos
$FieldName:#..$
```

<span data-ttu-id="5fb2a-129">`#` specifica il numero di caratteri da ignorare.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-129">Here, `#` specifies the number of characters to skip.</span></span> <span data-ttu-id="5fb2a-130">Ad esempio, per stampare un numero di targa Serial Shipping Container Code (SSCC) che non include i primi due caratteri, utilizzare `$LicensePlateId:2..$`.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-130">For example, to print a Serial Shipping Container Code (SSCC) license plate number that doesn't include the first two characters, use `$LicensePlateId:2..$`.</span></span> <span data-ttu-id="5fb2a-131">In questo caso, il numero di targa 0011111111111222221 verrà stampato come "11111111111222221".</span><span class="sxs-lookup"><span data-stu-id="5fb2a-131">In this case, the license plate number 0011111111111222221 will be printed as "11111111111222221."</span></span>

## <a name="custom-datetime-formats"></a><span data-ttu-id="5fb2a-132">Formati di data/ora personalizzati</span><span class="sxs-lookup"><span data-stu-id="5fb2a-132">Custom date/time formats</span></span>

<span data-ttu-id="5fb2a-133">L'esempio seguente mostra come è possibile controllare il formato utilizzato per stampare le date.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-133">The following example shows how you can control the format that is used to print dates.</span></span>

```dos
$PrintedDate:dd-MM-yyyy$
```

<span data-ttu-id="5fb2a-134">In questo esempio, la data del 30 aprile 2020 verrà stampata come "30-04-2020".</span><span class="sxs-lookup"><span data-stu-id="5fb2a-134">In this example, the date April 30, 2020, will be printed as "30-04-2020."</span></span>

<span data-ttu-id="5fb2a-135">Per l'elenco completo dei formati data/ora disponibili, vedere [Stringhe di formato data/ora personalizzate](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span><span class="sxs-lookup"><span data-stu-id="5fb2a-135">For a complete list of the available date/time formats, see [Custom date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>

## <a name="print-individual-lines-from-multiline-data"></a><span data-ttu-id="5fb2a-136">Stampa di singole righe da dati multiriga</span><span class="sxs-lookup"><span data-stu-id="5fb2a-136">Print individual lines from multiline data</span></span>

<span data-ttu-id="5fb2a-137">Se un campo dati contiene più righe (ovvero righe separate da interruzioni di riga) è possibile stampare una singola riga utilizzando il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-137">If a data field contains multiple lines (that is, lines that are separated by line breaks), you can print an individual line by using the following format.</span></span>

```dos
$FieldName[#]$
```

<span data-ttu-id="5fb2a-138">`#` è il numero di riga che si desidera stampare.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-138">Here, `#` is the line number that you want to print.</span></span> <span data-ttu-id="5fb2a-139">(Usare 1 per la prima riga.)</span><span class="sxs-lookup"><span data-stu-id="5fb2a-139">(Use 1 for the first line.)</span></span>

<span data-ttu-id="5fb2a-140">Ad esempio, il sistema ha un campo `AdditionalAddress` che memorizza il seguente indirizzo multiriga:</span><span class="sxs-lookup"><span data-stu-id="5fb2a-140">For example, your system has an `AdditionalAddress` field that stores the following multiline address:</span></span>

<span data-ttu-id="5fb2a-141">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-141">Contoso Inc.</span></span>  
<span data-ttu-id="5fb2a-142">123 Street Name</span><span class="sxs-lookup"><span data-stu-id="5fb2a-142">123 Street Name</span></span>  
<span data-ttu-id="5fb2a-143">Some City, Some State</span><span class="sxs-lookup"><span data-stu-id="5fb2a-143">Some City, Some State</span></span>

<span data-ttu-id="5fb2a-144">È possibile stampare questo indirizzo, una riga alla volta, utilizzando i seguenti codici.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-144">You can print this address, one line at a time, by using the following codes.</span></span>

| <span data-ttu-id="5fb2a-145">Codice</span><span class="sxs-lookup"><span data-stu-id="5fb2a-145">Code</span></span> | <span data-ttu-id="5fb2a-146">Testo stampato</span><span class="sxs-lookup"><span data-stu-id="5fb2a-146">Text that is printed</span></span> |
|---|---|
| `$AdditionalAddress[1]$` | <span data-ttu-id="5fb2a-147">Contoso Inc.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-147">Contoso Inc.</span></span> |
| `$AdditionalAddress[2]$` | <span data-ttu-id="5fb2a-148">123 Street Name</span><span class="sxs-lookup"><span data-stu-id="5fb2a-148">123 Street Name</span></span> |
| `$AdditionalAddress[3]$` | <span data-ttu-id="5fb2a-149">Some City, Some State</span><span class="sxs-lookup"><span data-stu-id="5fb2a-149">Some City, Some State</span></span> |

## <a name="print-and-format-from-a-display-method"></a><span data-ttu-id="5fb2a-150">Stampa e formattazione da un metodo di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="5fb2a-150">Print and format from a display method</span></span>

<span data-ttu-id="5fb2a-151">È possibile stampare da un metodo di visualizzazione utilizzando il seguente formato.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-151">You can print from a display method by using the following format.</span></span>

```dos
$DisplayMethod()$
```

<span data-ttu-id="5fb2a-152">È possibile combinare questo formato con altri tipi descritti in precedenza in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-152">You can combine this format with other types that were described earlier in this topic.</span></span> <span data-ttu-id="5fb2a-153">Ad esempio, è disponibile un metodo di visualizzazione chiamato `DisplayListOfItemsNumbers()` e si desidera stampare il primo numero di articolo di questo metodo.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-153">For example, you have a display method that is named `DisplayListOfItemsNumbers()`, and you want to print the first item number of this method.</span></span> <span data-ttu-id="5fb2a-154">In questo caso, è possibile utilizzare il seguente codice.</span><span class="sxs-lookup"><span data-stu-id="5fb2a-154">In this case, you can use the following code.</span></span>

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a><span data-ttu-id="5fb2a-155">Ulteriori informazioni sulla stampa delle etichette</span><span class="sxs-lookup"><span data-stu-id="5fb2a-155">More information about how to print labels</span></span>

<span data-ttu-id="5fb2a-156">Per ulteriori informazioni su come impostare e stampare le etichette, vedere [Abilitare la stampa dell'etichetta della targa](tasks/license-plate-label-printing.md).</span><span class="sxs-lookup"><span data-stu-id="5fb2a-156">For more information about how to set up and print labels, see [Enable license plate label printing](tasks/license-plate-label-printing.md).</span></span>
