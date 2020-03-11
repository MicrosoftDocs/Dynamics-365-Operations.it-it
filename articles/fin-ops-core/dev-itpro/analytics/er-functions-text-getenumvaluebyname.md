---
title: Funzione ER GETENUMVALUEBYNAME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GETENUMVALUEBYNAME della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
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
ms.openlocfilehash: 87613978c149b5d41aefc58f9896424229819626
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041181"
---
# <a name="GETENUMVALUEBYNAME">Funzione ER GETENUMVALUEBYNAME</a>

[!include [banner](../includes/banner.md)]

La funzione `GETENUMVALUEBYNAME` cerca un valore specifico *Enum* nell'origine dati di enumerazione specificata utilizzando il nome dell'enumerazione specificato come un valore *Stringa*. Se viene trovato il valore *Enum*, la funzione lo restituisce. Altrimenti, la funzione restituisce il valore di enumerazione **nullo**.

## <a name="syntax"></a>Sintassi

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argomenti

`enumeration data source path`: *Enumerazione*

Il percorso valido di un'origine dati di uno dei seguenti tipi di enumerazione:

- Enumerazione di modelli di creazione di report elettronici (ER)
- Enumerazione formato ER
- Enumerazione Microsoft Dynamics 365 Finance

`enumeration value text`: *Stringa*

Un valore di stringa che rappresenta il nome di un singolo valore di enumerazione.

## <a name="return-values"></a>Valori restituiti

*Enum* nullable

Il valore di enumerazione risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Nessuna eccezione viene generata se non viene trovato un valore *Enum* utilizzando il nome del valore di enumerazione specificato come un valore *Stringa*.

## <a name="example"></a>Esempio

Nella seguente figura viene illustrata l'enumerazione **ReportDirection** introdotta in un modello dati. Tenere presente che le etichette vengono definite per i valori dell'enumerazione.

<p><a href="./media/ER-data-model-enumeration-values.PNG"><img src="./media/ER-data-model-enumeration-values.PNG" alt="Available values for a data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

La figura di seguito mostra questi dettagli:

- L'origine dati **$ Direction** è configurata in un report ER. Questa origine dati è configurata in base all'enumerazione del modello **ReportDirection**.
- L'espressione `$IsArrivals` viene progettata per l'utilizzo dell'origine dati **$Direction** basata sull'enumerazione di modello come parametro di questa funzione.
- Il valore di questa espressione di confronto è **TRUE**.

<a href="./media/ER-data-model-enumeration-usage.PNG"><img src="./media/ER-data-model-enumeration-usage.PNG" alt="Example of data model enumeration" class="alignnone wp-image-290681 size-full" width="397" height="136" /></a>

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)
