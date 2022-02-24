---
title: Elenco delle funzioni ER nella categoria conversione del tipo
description: Questo argomento fornisce informazioni sulle funzioni di conversione supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: eb2d4ab3434a563e907f6540809888cd3f671c1a
ms.sourcegitcommit: fcc4596eeadac5dfe9a3242afa49b9b1c0c96575
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2020
ms.locfileid: "4740810"
---
# <a name="list-of-er-functions-in-the-type-conversion-category"></a>Elenco delle funzioni ER nella categoria conversione del tipo

[!include [banner](../includes/banner.md)]

Le funzioni di conversione del tipo creazione di report elettronici (ER) possono essere utilizzate per convertire valori tra tipi. Questo argomento fornisce un riepilogo di queste funzioni.

## <a name="type-conversion-functions"></a>Funzioni di conversione di tipo

| Funzione | Descrizione |
|----------|-------------|
| [Int64Value](er-functions-conversion-int64value.md)   | Questa funzione restituisce un valore *Int64* che rappresenta la stringa specificata. |
| [IntValue](er-functions-conversion-intvalue.md)       | Questa funzione restituisce un valore *Int* che rappresenta la stringa specificata. |
| [NumberValue](er-functions-conversion-numbervalue.md) | Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*. Durante la conversione, vengono considerati i separatori di raggruppamento decimali e numerici specificati. |
| [Valore](er-functions-conversion-value.md)             | Questa funzione restituisce un valore *Reale* che viene convertito dal valore specificato *Stringa*. |

## <a name="type-conversion-functions-in-the-container-category"></a>Funzioni di conversione di tipo nella categoria contenitore

La tabella seguente descrive le funzioni di conversione di tipo nella categoria [contenitore](er-functions-category-container.md).

| Funzione | descrizione |
|----------|-------------|
| [Base64StringToContainer](er-functions-container-base64stringtocontainer.md) | Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *Contenitore*. |

## <a name="type-conversion-functions-in-the-date-and-time-category"></a>Funzioni di conversione di tipo nella categoria data e ora

La tabella seguente descrive le funzioni di conversione di tipo nella [categoria data e ora](er-functions-category-datetime.md).

| Funzione | Descrizione |
|----------|-------------|
| [DateTimeValue](er-functions-datetime-datetimevalue.md)   | Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data/ora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore *Data* a un valore di data/ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md)           | Questa funzione restituisce un valore *Data* che viene convertito da un determinato valore *Stringa* nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data. |

## <a name="type-conversion-functions-in-the-list-category"></a>Funzioni di conversione di tipo nella categoria elenco

La tabella seguente descrive le funzioni di conversione di tipo nella [categoria elenco](er-functions-category-list.md).

| Funzione | Descrizione |
|----------|-------------|
| [Elenco](er-functions-list-list.md)                 | Questa funzione restituisce un valore *Elenco di record* come un nuovo elenco creato dagli argomenti specificati del tipo *Contenitore (record)*. |
| [ListOfFields](er-functions-list-listoffields.md) | Questa funzione restituisce un valore *Elenco di record* creato in base alla struttura di un determinato argomento del tipo *Enumerazione* o *Contenitore (record)*. |
| [Dividi](er-functions-list-split.md)               | Questa funzione divide il valore *Stringa* in sottostringhe e restituisce il risultato come nuovo valore *Elenco di record*. |
| [StringJoin](er-functions-list-stringjoin.md)     | Restituisce un valore *Stringa* costituito da valori concatenati del campo specificato dal valore *Elenco di record* specificato. I valori possono essere separati dal delimitatore specificato. |

## <a name="type-conversion-functions-in-the-text-category"></a>Funzioni di conversione di tipo nella categoria testo

La tabella seguente descrive le funzioni di conversione di tipo nella [categoria testo](er-functions-category-text.md).

| Funzione | Descrizione |
|----------|-------------|
| [Char](er-functions-text-char.md)                 | Questa funzione restituisce un valore *Stringa* che rappresenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato. |
| [GuidValue](er-functions-text-guidvalue.md)       | Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*. |
| [NumberFormat](er-functions-text-numberformat.md) | Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato nel formato specificato e nelle impostazioni cultura specificate facoltativamente. |
| [QrCode](er-functions-text-qrcode.md)             | Questa funzione restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario. |
| [Testo](er-functions-text-text.md)                 | Questa funzione restituisce un valore *Stringa* che rappresenta il numero specificato dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
