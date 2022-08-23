---
title: Funzione ER QRCODE
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione QRCODE della creazione di report elettronici (ER).
author: kfend
ms.date: 12/10/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287190"
---
# <a name="qrcode-er-function"></a>Funzione ER QRCODE

[!include [banner](../includes/banner.md)]

La funzione `QRCODE` restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario.

## <a name="syntax"></a>Sintassi

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore *Stringa* che rappresenta il testo originale.

## <a name="return-values"></a>Valori restituiti

*Contenitore*

Il flusso binario risultante.

## <a name="example"></a>Esempio

È possibile configurare un formato creazione di report elettronici (ER) per generare un documento in uscita nel formato Microsoft Office (cartelle di lavoro Excel o documenti Word) utilizzando un modello predefinito. Questo modello può contenere un oggetto **Immagine** (cartella di lavoro Excel) o **Controllo contenuto immagine** (documento Word) come segnaposto per un'immagine di codice QR. È necessario aggiungere al formato ER configurato un elemento **Cella** che verrà utilizzato per riempire questo segnaposto. Per specificare quali informazioni verranno archiviate in un codice QR, è necessario definire un'associazione per questo elemento **Cella**. Ad esempio, è possibile configurare tale associazione in modo che contenga la seguente espressione:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

Quando si esegue il formato ER configurato, il valore di testo del campo **LabelText** dell'origine dati **model.ListOfShelfLabels** verrà utilizzato per generare un'immagine del codice QR. Questa immagine sostituirà un segnaposto dell'immagine del codice QR nel modello di documento usato per generare un documento in uscita. Quando questa immagine del documento generato viene letta tramite scanner, restituisce il testo che è stato preso dal campo **LabelText** dell'origine dati **model.ListOfShelfLabels**. Per ulteriori informazioni, vedere [Incorporare immagini e forme nei documenti generati utilizzando ER](electronic-reporting-embed-images-shapes.md)

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
