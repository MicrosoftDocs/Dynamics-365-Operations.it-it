---
title: Progettare configurazioni ER per sopprimere i caratteri BOM nei file generati
description: In questo argomento viene illustrato come configurare un formato di report elettronico (ER) per generare report che sopprimono i caratteri BOM (byte order mark).
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9260db2edab75c9876ddf5af99bee4ff174c64e1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5568975"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a><span data-ttu-id="138e3-103">Progettare configurazioni ER per sopprimere i caratteri BOM nei file generati</span><span class="sxs-lookup"><span data-stu-id="138e3-103">Design ER configurations to suppress BOM characters in generated files</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="138e3-104">È possibile progettare una [soluzione](er-quick-start1-new-solution.md) di [report elettronici (ER)](general-electronic-reporting.md) per generare documenti in uscita in formato.</span><span class="sxs-lookup"><span data-stu-id="138e3-104">You can design an [Electronic reporting (ER)](general-electronic-reporting.md) [solution](er-quick-start1-new-solution.md) to generate outgoing documents.</span></span> <span data-ttu-id="138e3-105">Per generare i documenti come file di testo o XML, la soluzione deve includere una [configurazione](general-electronic-reporting.md#Configuration) ER che contiene un componente di [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.</span><span class="sxs-lookup"><span data-stu-id="138e3-105">To generate the documents as text or XML files, the solution must include an ER [configuration](general-electronic-reporting.md#Configuration) that contains an ER [format](general-electronic-reporting.md#FormatComponentOutbound) component.</span></span> <span data-ttu-id="138e3-106">Per specificare la [codifica dei caratteri](https://docs.microsoft.com/windows/win32/intl/character-sets) che rappresenta il set di caratteri nei file generati, il formato ER deve contenere l'elemento di formato **Comune\\File**.</span><span class="sxs-lookup"><span data-stu-id="138e3-106">To specify the [character encoding](https://docs.microsoft.com/windows/win32/intl/character-sets) that represents the set of characters in generated files, the ER format must contain the **Common\\File** format element.</span></span> <span data-ttu-id="138e3-107">Per configurare il componente formato ER, apri la versione [bozza](general-electronic-reporting.md#component-versioning) della configurazione ER creata nella finestra di progettazione del formato ER e aggiungi l'elemento **Comune\\File**.</span><span class="sxs-lookup"><span data-stu-id="138e3-107">To configure the ER format component, open the [draft](general-electronic-reporting.md#component-versioning) version of the ER configuration in the ER format designer, and add the **Common\\File** element.</span></span> <span data-ttu-id="138e3-108">Nel campo **Codifica**, specificare la codifica dei file in uscita che vengono generati in fase di esecuzione utilizzando questo componente.</span><span class="sxs-lookup"><span data-stu-id="138e3-108">In the **Encoding** field, specify the encoding of outbound files that are generated at runtime by using this component.</span></span>

> [!NOTE]
> <span data-ttu-id="138e3-109">Se il formato contiene un nome di codifica errato, viene generato un errore quando si salvano le modifiche alle impostazioni del formato.</span><span class="sxs-lookup"><span data-stu-id="138e3-109">If the format contains an incorrect encoding name, an error is thrown when you save your changes to the format's settings.</span></span>

![Aggiunta di un elemento radice nella pagina Progettazione formati](./media/er-suppress-bom-characters-image1.gif)

<span data-ttu-id="138e3-111">Se specifichi **UTF-8**, **UTF-16** o **UTF-32** come codifica, l'opzione **Elimina caratteri BOM** l'opzione diventa disponibile.</span><span class="sxs-lookup"><span data-stu-id="138e3-111">If you specify **UTF-8**, **UTF-16**, or **UTF-32** as the encoding, the **Suppress BOM characters** option becomes available.</span></span> <span data-ttu-id="138e3-112">Imposta questa opzione su **Sì** per eliminare i [caratteri byte order mark (BOM)](https://docs.microsoft.com/globalization/encoding/byte-order-mark) nei file in uscita che vengono generati in fase di esecuzione quando viene eseguito il formato ER modificabile.</span><span class="sxs-lookup"><span data-stu-id="138e3-112">Set this option to **Yes** to suppress [byte order mark (BOM) characters](https://docs.microsoft.com/globalization/encoding/byte-order-mark) in outbound files that are generated at runtime when the editable ER format is run.</span></span>

> [!NOTE]
> <span data-ttu-id="138e3-113">Se si lascia vuoto il campo **Codifica**, viene utilizzata la codifica **UTF-8** predefinita.</span><span class="sxs-lookup"><span data-stu-id="138e3-113">If you leave the **Encoding** field blank, the default **UTF-8** encoding is used.</span></span>

![Impostazione dell'opzione Sopprimi caratteri BOM nella pagina Progettazione formato](./media/er-suppress-bom-characters-image2.gif)

<span data-ttu-id="138e3-115">Per rivedere la funzionalità in fase di esecuzione, completare la procedura appropriata.</span><span class="sxs-lookup"><span data-stu-id="138e3-115">To review the functionality at runtime, complete the appropriate procedure.</span></span> <span data-ttu-id="138e3-116">Ad esempio, completare i passaggi nell'argomento [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md).</span><span class="sxs-lookup"><span data-stu-id="138e3-116">For example, complete the steps in the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic.</span></span> <span data-ttu-id="138e3-117">Dopo aver completato i passaggi nella sezione [Modificare il formato in modo che il calcolo sia basato sull'output generato](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) di quell'argomento, segui questi passaggi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="138e3-117">After you've completed the steps in the [Modify the format so that the calculation is based on generated output](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) section of that topic, follow these additional steps.</span></span>

1. <span data-ttu-id="138e3-118">Specifica la codifica UTF:</span><span class="sxs-lookup"><span data-stu-id="138e3-118">Specify the UTF encoding:</span></span>

    1. <span data-ttu-id="138e3-119">Seleziona l'elemento **Report** del tipo **Comune\\File**.</span><span class="sxs-lookup"><span data-stu-id="138e3-119">Select the **Report** element of the **Common\\File** type.</span></span>
    2. <span data-ttu-id="138e3-120">Nel campo **Codifica**, specificare la codifica **UTF-8**.</span><span class="sxs-lookup"><span data-stu-id="138e3-120">In the **Encoding** field, specify the **UTF-8** encoding.</span></span>

2. <span data-ttu-id="138e3-121">Genera un file XML che includa un carattere BOM:</span><span class="sxs-lookup"><span data-stu-id="138e3-121">Generate an XML file that includes a BOM character:</span></span>

    1. <span data-ttu-id="138e3-122">Imposta l'opzione **Sopprimi caratteri BOM** su **No** per includere caratteri BOM nei file XML generati.</span><span class="sxs-lookup"><span data-stu-id="138e3-122">Set the **Suppress BOM characters** option to **No** to include BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="138e3-123">Completa i passaggi nella sezione [Posticipare l'esecuzione dell'elemento XML di riepilogo in modo che venga utilizzato il totale calcolato](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) dell'argomento [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md) e salva il file generato come **SampleXmlReport.xml**.</span><span class="sxs-lookup"><span data-stu-id="138e3-123">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport.xml**.</span></span>

3. <span data-ttu-id="138e3-124">Genera un file XML che non includa un carattere BOM:</span><span class="sxs-lookup"><span data-stu-id="138e3-124">Generate an XML file that doesn't include a BOM character:</span></span>

    1. <span data-ttu-id="138e3-125">Imposta l'opzione **Sopprimi caratteri BOM** su **Sì** per sopprimere i caratteri BOM nei file XML generati.</span><span class="sxs-lookup"><span data-stu-id="138e3-125">Set the **Suppress BOM characters** option to **Yes** to suppress BOM characters in generated XML files.</span></span>
    2. <span data-ttu-id="138e3-126">Completa i passaggi nella sezione [Posticipare l'esecuzione dell'elemento XML di riepilogo in modo che venga utilizzato il totale calcolato](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) dell'argomento [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md) e salva il file generato come **SampleXmlReport (1).xml**.</span><span class="sxs-lookup"><span data-stu-id="138e3-126">Complete the steps in the [Defer the execution of the summary XML element so that the calculated total is used](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) section of the [Defer the execution of XML elements in ER formats](er-defer-xml-element.md) topic, and save the generated file as **SampleXmlReport (1).xml**.</span></span>

4. <span data-ttu-id="138e3-127">In un'utilità di confronto file, confronta i file generati.</span><span class="sxs-lookup"><span data-stu-id="138e3-127">In a file comparison utility, compare the generated files.</span></span>

    <span data-ttu-id="138e3-128">La prima differenza che noterai è nell'intestazione del file.</span><span class="sxs-lookup"><span data-stu-id="138e3-128">The first difference that you will notice is in the file header.</span></span> <span data-ttu-id="138e3-129">Il file SampleXmlReport.xml contiene un carattere BOM, mentre il file SampleXmlReport (1) .xml no.</span><span class="sxs-lookup"><span data-stu-id="138e3-129">The SampleXmlReport.xml file contains a BOM character, where the SampleXmlReport (1).xml file doesn't.</span></span>

    ![Confronto dei file generati utilizzando un'utilità di confronto file](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a><span data-ttu-id="138e3-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="138e3-131">See also</span></span>

- [<span data-ttu-id="138e3-132">Differire l'esecuzione di elementi XML in formati ER</span><span class="sxs-lookup"><span data-stu-id="138e3-132">Defer the execution of XML elements in ER formats</span></span>](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]