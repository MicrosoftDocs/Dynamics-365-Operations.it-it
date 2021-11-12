---
title: Funzione ER CHANGETIMEZONE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CHANGETIMEZONE della creazione di report elettronici (ER).
author: NickSelin
ms.date: 09/09/2021
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: AX 10.0.23
ms.openlocfilehash: 48e96cfbc19503daf6a20363c4520c765f11a249
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647941"
---
# <a name="changetimezone-er-function"></a>Funzione ER CHANGETIMEZONE

[!include [banner](../includes/banner.md)]

La funzione `CHANGETIMEZONE` restituisce un valore *[DateTime](er-formula-supported-data-types-primitive.md#datetime)* in Coordinated Universal Time (Ora di Greenwich \[GMT\]) convertito da un determinato valore di data/ora in una zona con una sola ora in un valore data/ora in un altro fuso orario.

## <a name="syntax"></a>Sintassi

```vb
CHANGETIMEZONE (datetime, base time zone, target time zone)
```

## <a name="arguments"></a>Argomenti

`datetime`: *DateTime*

Un valore di data/ora nel fuso orario Coordinated Universal Time che rappresenta il valore di data/ora da convertire.

`base time zone`: *[Stringa](er-formula-supported-data-types-primitive.md#string)*

Il nome del fuso orario a cui viene spostato un valore data/ora prima della conversione.

`target time zone`: *Stringa*

Il nome del fuso orario in cui viene convertito un valore data/ora prima durante la conversione.

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante nel fuso orario Coordinated Universal Time.

## <a name="usage-notes"></a>Note sull'utilizzo

Per specificare i fusi orari di origine e di destinazione, è possibile utilizzare i nomi dei fusi orari che sono [forniti](https://data.iana.org/time-zones/releases/) dall'[Autorità per i numeri assegnati a Internet (IANA)](https://www.iana.org/) o che sono [supportati](/windows-hardware/manufacture/desktop/default-time-zones) da Microsoft Windows.

In fase di esecuzione, l'eccezione "Fuso orario '\<time zone name\>' non esiste" viene generato se il nome fornito non viene trovato nell'elenco IANA o nel registro di Windows.

Per i fusi orari in cui viene osservata l'ora legale, la conversione considera l'offset dell'ora legale di Coordinated Universal Time. Le ultime informazioni disponibili su questo offset vengono utilizzate durante la conversione.

## <a name="example-1"></a>Esempio 1

In questo esempio vengono utilizzati i nomi dei fusi orari per Windows.

Configurare l'origine dati **DSX** del tipo **Campo calcolato**. Include l'espressione seguente.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "E. Europe Standard Time", "Hawaiian Standard Time"), "O")
)
```

Se si configura l'espressione dell'origine dati **DSY** del tipo **Campo calcolato** come `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, l'origine dati **DSX** restituisce il testo **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Questo testo mostra che la differenza di orario tra i due fusi orari forniti il 1 giugno è superiore a 24 ore. Pertanto, il valore di data/ora convertito è un giorno precedente al valore di data/ora specificato, perché il fuso orario di base è in anticipo rispetto al fuso orario di destinazione.

Se si configura l'espressione dell'origine dati **DSY** del tipo **Campo calcolato** come `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, l'origine dati **DSX** restituisce il testo **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Questo testo mostra che la differenza di orario tra i due fusi orari forniti il 1 dicembre è inferiore a 24 ore. Pertanto, il valore di data/ora convertito è uguale al valore di data/ora specificato.

> [!NOTE]
> La stessa espressione restituisce una varianza diversa tra i valori di data/ora forniti e convertiti per la stessa coppia di fusi orari perché viene osservato un diverso offset dell'ora legale di Coordinated Universal Time per i fusi orari forniti in una determinata data/ora.

## <a name="example-2"></a>Esempio 2

In questo esempio vengono utilizzati i nomi dei fusi orari IANA.

Configurare l'origine dati **DSX** del tipo **Campo calcolato**. Include l'espressione seguente.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "Europe/Athens", "US/Hawaii"), "O")
)
```

Se si configura l'espressione dell'origine dati **DSY** del tipo **Campo calcolato** come `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, l'origine dati **DSX** restituisce il testo **2021-06-01T12:55:00.0000000+00:00 -> 2021-05-31T23:55:00.0000000+00:00**. Questo testo mostra che la differenza di orario tra i due fusi orari forniti il 1 giugno è superiore a 24 ore. Pertanto, il valore di data/ora convertito è un giorno precedente al valore di data/ora specificato, perché il fuso orario di base è in anticipo rispetto al fuso orario di destinazione.

Se si configura l'espressione dell'origine dati **DSY** del tipo **Campo calcolato** come `DATETIMEVALUE ("01-Dec-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, l'origine dati **DSX** restituisce il testo **2021-12-01T12:55:00.0000000+00:00 -> 2021-12-01T00:55:00.0000000+00:00**. Questo testo mostra che la differenza di orario tra i due fusi orari forniti il 1 dicembre è inferiore a 24 ore. Pertanto, il valore di data/ora convertito è uguale al valore di data/ora specificato.

## <a name="example-3"></a>Esempio 3

Configurare l'origine dati **DSX** del tipo **Campo calcolato**. Include l'espressione seguente.

```vb
CONCATENATE(
    DATETIMEFORMAT( DSY, "O"), 
    " -> ", 
    DATETIMEFORMAT( CHANGETIMEZONE(DSY, "US/Hawaii", "Europe/Athens"), "O")
)
```

Se si configura l'espressione dell'origine dati **DSY** del tipo **Campo calcolato** come `DATETIMEVALUE ("01-Jun-2021 12:55:00", "dd-MMM-yyyy HH:mm:ss", "EN")`, l'origine dati **DSX** restituisce il testo **2021-06-01T12:55:00.0000000+00:00 -> 2021-06-02T01:55:00.0000000+00:00**. Questo testo mostra che la differenza di orario tra i due fusi orari forniti il 1 giugno è superiore a 24 ore. Pertanto, il valore di data/ora convertito è un giorno successivo al valore di data/ora specificato, perché il fuso orario di destinazione è in anticipo rispetto al fuso orario di base.

## <a name="example-4"></a>Esempio 4

Potresti ricevere un timestamp di data/ora da una origine esterna come testo che non contiene informazioni sul fuso orario. Tuttavia, potresti conoscere il fuso orario in cui opera l'origine. Ad esempio, ricevi il timestamp di data/ora **01/12/2021 12:55:00** da un servizio operato in Spagna. Per salvare correttamente questo valore di data/ora nel database, completare la seguente conversione:

- Configura l'origine dei dati **DSY** del tipo **Campo calcolato** per convertire un timestamp di data/ora dal testo al valore di data/ora di Coordinated Universal Time.

    `DATETIMEVALUE ("01/12/2021 12:55:00", "dd/MM/yyyy HH:mm:ss", "ES")`

- Configura l'origine dati **DSX** del tipo **Campo calcolato** per spostare il valore di data/ora convertito in Coordinated Universal Time come valore di data/ora del fuso orario dell'origine esterna.

    `CHANGETIMEZONE(DSY, "Romance Standard Time", "GMT Standard Time")`

> [!NOTE]
> Quando usi la funzione `CHANGETIMEZONE` per la conversione di data/ora, tieni presente che qualsiasi valore di data/ora viene memorizzato nel database come valore nel fuso orario Coordinated Universal Time. Prima che questo valore possa essere presentato nelle pagine dell'applicazione, viene trasformato. La trasformazione considera il fuso orario che è [set](../../fin-ops/organization-administration/tasks/set-users-preferred-time-zone.md) come zona preferita per l'utente dell'applicazione attualmente connesso.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
