---
title: Elenco delle funzioni ER nella categoria data e ora
description: Questo articolo fornisce informazioni sulle funzioni di data e ora supportate nella creazione di report elettronici (ER).
author: kfend
ms.date: 09/09/2021
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
ms.openlocfilehash: d77f41e10d927a9aae06b9ba0fc58ca237c071cd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9291326"
---
# <a name="list-of-er-functions-in-the-date-and-time-category"></a>Elenco delle funzioni ER nella categoria data e ora

[!include [banner](../includes/banner.md)]

Le funzioni di data e ora della creazione di report elettronici (ER) possono essere utilizzate per estrarre informazioni dai valori di data e ora e per eseguire operazioni su di essi. Questo articolo fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione | Descrizione |
|----------|-------------|
| [AddDays](er-functions-datetime-adddays.md) | Questa funzione restituisce un valore *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* che è il numero specificato di giorni prima o dopo una data di inizio specificata. |
| [ChangeTimeZone](er-functions-datetime-changetimezone.md) | Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore di data/ora in un fuso orario a un valore di data/ ora in un altro fuso orario. |
| [DateFormat](er-functions-datetime-dateformat.md) | Questa funzione restituisce un valore *[Stringa](er-formula-supported-data-types-primitive.md#string)* che presenta un valore specifico di data come testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente. |
| [DateTimeFormat](er-functions-datetime-datetimeformat.md) | Questa funzione restituisce un valore *Stringa* che presenta un valore specifico di data/ora come testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente. |
| [DateTimeValue](er-functions-datetime-datetimevalue.md) | Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data/ora. |
| [DateToDateTime](er-functions-datetime-datetodatetime.md) | Questa funzione restituisce un valore *DateTime* che viene convertito da un determinato valore di data a un valore di data / ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]). |
| [DateValue](er-functions-datetime-datevalue.md) | Questa funzione restituisce un valore *[Data](er-formula-supported-data-types-primitive.md#date)* che viene convertito da un determinato valore di testo nel formato specificato e nelle impostazioni cultura specificate facoltativamente in un valore data. |
| [DayOfYear](er-functions-datetime-dayofyear.md) | La funzione restituisce un valore *[Intero](er-formula-supported-data-types-primitive.md#integer)* che è la rappresentazione del numero di giorni tra l'1 gennaio e la data specificata. |
| [Giorni](er-functions-datetime-days.md) | Restituisce un valore *Intero* che è la rappresentazione del numero di giorni tra una data specificata e una seconda data specificata. |
| [Now](er-functions-datetime-now.md) | Questa funzione restituisce un valore *DateTime* che rappresenta la data e l'ora correnti del server delle applicazioni. |
| [NullDate](er-functions-datetime-nulldate.md) | Questa funzione restituisce un valore *Data* che rappresenta la data **null** (1 gennaio 1900). |
| [NullDateTime](er-functions-datetime-nulldatetime.md) | Questa funzione restituisce un valore *DateTime* che rappresenta il valore **null** data/ora (1 gennaio 1900) in Coordinated Universal Time. |
| [SessionNow](er-functions-datetime-sessionnow.md) | Questa funzione restituisce un valore *DateTime* che rappresenta la data e l'ora correnti della sessione dell'applicazione. |
| [SessionToday](er-functions-datetime-sessiontoday.md) | Questa funzione restituisce un valore *Data* che rappresenta la data corrente della sessione dell'applicazione. |
| [Oggi](er-functions-datetime-today.md) | Questa funzione restituisce un valore *Data* che rappresenta la data corrente del server applicazioni. |
| [WeekNum](er-functions-datetime-weeknum.md) | Questa funzione restituisce un valore *Intero* che rappresenta la settimana dell'anno. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
