---
title: Funzione ER Base64StringToContainer
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione Base64StringToContainer della creazione di report elettronici (ER).
author: kfend
ms.date: 12/14/2020
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: 10.0.17
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 96dfffc3d899f1106c6c931efb08c941f5b3c1a6
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291236"
---
# <a name="base64stringtocontainer-er-function"></a>Funzione ER Base64StringToContainer

[!include [banner](../includes/banner.md)]

La [funzione](er-formula-language.md#Functions) `BASE64STRINGTOCONTAINER` converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *[Contenitore](er-functions-category-container.md)*.

## <a name="syntax"></a>Sintassi

```vb
BASE64STRINGTOCONTAINER (input)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un'origine dati del tipo *Stringa*.

## <a name="return-values"></a>Valori restituiti

*Container*

Il valore binario ottenuto in formato BLOB (Binary Large Object).

## <a name="usage-notes"></a>Note sull'utilizzo

L'eccezione "Il parametro non è valido" viene generata se la stringa di input non fornisce un gruppo Base64 corretto di schemi di codifica da binario a testo.

## <a name="example"></a>Esempio

Definire le origini dati seguenti nel mapping di modello:

- L'origine dati **DocuTypeGroupEnum** radice del tipo *Dynamics 365 for Operations/Enumerazione* che fa riferimento all'enumerazione di applicazione **DocuTypeGroup**
- L'origine dati **Cliente** radice del tipo *Dynamics 365 for Operations/record di tabella* che fa riferimento alla tabella delle applicazioni **CustTable**
- L'origine dati **\#Media** del tipo *Campo calcolato* che si configura nel modo seguente:

    - Viene aggiunto come origine dati figlio dell'origine dati **Cliente**.
    - Contiene l'espressione `WHERE(@.'<Relations'.'<Documents', @.'<Relations'.'<Documents'.'docuType()'.TypeGroup = DocuTypeGroupEnum.Image)`.

- L'origine dati **\#MediaAsBase64String** del tipo *Campo calcolato* che si configura nel modo seguente:

    - Viene aggiunto come origine dati figlio dell'origine dati **Cliente"\#Media"**.
    - Contiene l'espressione `Customer.'#Media'.'getFileContentAsBase64String()'`.

- L'origine dati **\#BlobFomBase64** del tipo *Campo calcolato* che si configura nel modo seguente:

    - Viene aggiunto come origine dati figlio dell'origine dati **Cliente"\#Media"**.
    - Contiene l'espressione `Base64StringToContainer(Customer.'#Media'.'#MediaAsBase64String')'`.

In questo esempio, l'origine dati **\#MediaAsBase64String** codifica il contenuto binario dell'allegato multimediale corrente come testo che rappresenta un gruppo Base64 di schemi di codifica da binario a testo. L'origine dati **\#BlobFomBase64** decodifica la stringa Base64 e restituisce un valore binario in formato BLOB.

![Origini dati di esempio nella finestra di progettazione mapping modello ER.](./media/er-functions-container-base64stringtocontainer-1.png)

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni del contenitore](er-functions-category-container.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
