---
title: Funzione ER CONVERTCURRENCY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione CONVERTCURRENCY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
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
ms.openlocfilehash: a27fd30236a61576ab9063010ea6bc38d9cf7a1e
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4686788"
---
# <a name="convertcurrency-er-function"></a>Funzione ER CONVERTCURRENCY

[!include [banner](../includes/banner.md)]

La funzione `CONVERTCURRENCY` restituisce un valore *Reale* che rappresenta il risultato della conversione dell'importo monetario specificato dalla valuta di origine specificata nella valuta di destinazione specificata utilizzando le impostazioni della società specificata alla data specificata.

## <a name="syntax"></a>Sintassi

```vb
CONVERTCURRENCY (amount, source currency, target currency, date, company)
```

## <a name="arguments"></a>Argomenti

`amount`: *Intero* o *Intero*

Un valore numerico che rappresenta l'importo monetario che deve essere convertito.

`source currency`: *Stringa*

Il codice della valuta di origine.

`target currency`: *Stringa*

Il codice della valuta di destinazione.

`date`: *Data*

Un valore *Data* che rappresenta la data utilizzata per determinare il tasso di cambio per la conversione.

`company`: *Stringa*

Un valore *Stringa* che rappresenta il codice di una società che fornisce le impostazioni utilizzate per la conversione.

## <a name="return-values"></a>Valori restituiti

*Reale*

Il valore numerico risultante.

## <a name="example"></a>Esempio

`CONVERTCURRENCY (1, "EUR", "USD", TODAY(), "DEMF")` restituisce un equivalente di un euro in dollari statunitensi nella data della sessione corrente, in base alle impostazioni per la società **DEMF**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
