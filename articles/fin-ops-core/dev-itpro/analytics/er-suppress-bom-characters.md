---
title: Progettare configurazioni ER per sopprimere i caratteri BOM nei file generati
description: In questo articolo viene illustrato come configurare un formato di report elettronico (ER) per generare report che sopprimono i caratteri BOM (byte order mark).
author: kfend
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2018-01-01
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: EROperationDesigner
ms.openlocfilehash: a2ea132b51f2f451fbe81a9c7869bea84bf4017a
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324021"
---
# <a name="design-er-configurations-to-suppress-bom-characters-in-generated-files"></a>Progettare configurazioni ER per sopprimere i caratteri BOM nei file generati

[!include [banner](../includes/banner.md)]

È possibile progettare una [soluzione](er-quick-start1-new-solution.md) di [report elettronici (ER)](general-electronic-reporting.md) per generare documenti in uscita in formato. Per generare i documenti come file di testo o XML, la soluzione deve includere una [configurazione](general-electronic-reporting.md#Configuration) ER che contiene un componente di formato ER. Per specificare la [codifica dei caratteri](/windows/win32/intl/character-sets) che rappresenta il set di caratteri nei file generati, il formato ER deve contenere l'elemento di formato **Comune\\File**. Per configurare il componente di formato ER, apri la versione bozza della configurazione ER nella finestra di progettazione del formato ER e aggiungi l'elemento **Comune\\File**. Nel campo **Codifica**, specificare la codifica dei file in uscita che vengono generati in fase di esecuzione utilizzando questo componente.

> [!NOTE]
> Se il formato contiene un nome di codifica errato, viene generato un errore quando si salvano le modifiche alle impostazioni del formato.

![Aggiunta di un elemento radice nella finestra di progettazione Formato.](./media/er-suppress-bom-characters-image1.gif)

Se specifichi **UTF-8**, **UTF-16** o **UTF-32** come codifica, l'opzione **Elimina caratteri BOM** l'opzione diventa disponibile. Imposta questa opzione su **Sì** per eliminare i [caratteri byte order mark (BOM)](/globalization/encoding/byte-order-mark) nei file in uscita che vengono generati in fase di esecuzione quando viene eseguito il formato ER modificabile.

> [!NOTE]
> Se si lascia vuoto il campo **Codifica**, viene utilizzata la codifica **UTF-8** predefinita.

![Impostazione dell'opzione Sopprimi caratteri BOM nella finestra di progettazione Formato.](./media/er-suppress-bom-characters-image2.gif)

Per rivedere la funzionalità in fase di esecuzione, completare la procedura appropriata. Ad esempio, completa i passaggi nell'articolo [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md). Dopo aver completato i passaggi nella sezione [Modificare il formato in modo che il calcolo sia basato sull'output generato](er-defer-xml-element.md#modify-the-format-so-that-the-calculation-is-based-on-generated-output) di quell'articolo, segui questi passaggi aggiuntivi.

1. Specifica la codifica UTF:

    1. Seleziona l'elemento **Report** del tipo **Comune\\File**.
    2. Nel campo **Codifica**, specificare la codifica **UTF-8**.

2. Genera un file XML che includa un carattere BOM:

    1. Imposta l'opzione **Sopprimi caratteri BOM** su **No** per includere caratteri BOM nei file XML generati.
    2. Completa i passaggi nella sezione [Posticipare l'esecuzione dell'elemento XML di riepilogo in modo che venga utilizzato il totale calcolato](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) dell'articolo [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md) e salva il file generato come **SampleXmlReport.xml**.

3. Genera un file XML che non includa un carattere BOM:

    1. Imposta l'opzione **Sopprimi caratteri BOM** su **Sì** per sopprimere i caratteri BOM nei file XML generati.
    2. Completa i passaggi nella sezione [Posticipare l'esecuzione dell'elemento XML di riepilogo in modo che venga utilizzato il totale calcolato](er-defer-xml-element.md#defer-the-execution-of-the-summary-xml-element-so-that-the-calculated-total-is-used) dell'articolo [Posticipa l'esecuzione di elementi XML nei formati ER](er-defer-xml-element.md) e salva il file generato come **SampleXmlReport (1).xml**.

4. In un'utilità di confronto file, confronta i file generati.

    La prima differenza che noterai è nell'intestazione del file. Il file SampleXmlReport.xml contiene un carattere BOM, mentre il file SampleXmlReport (1) .xml no.

    ![Confronto dei file generati utilizzando un'utilità di confronto file.](./media/er-suppress-bom-characters-image3.png)

## <a name="see-also"></a>Vedere anche

- [Differire l'esecuzione di elementi XML in formati ER](er-defer-xml-element.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
