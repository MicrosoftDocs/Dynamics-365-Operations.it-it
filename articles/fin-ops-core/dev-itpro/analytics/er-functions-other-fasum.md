---
title: Funzione ER FA_SUM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FA_SUM della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: d6f380e384e591e7417cfa40c73f9be6575fb0f6
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5744297"
---
# <a name="fa_sum-er-function"></a>Funzione ER FA_SUM

[!include [banner](../includes/banner.md)]

La funzione `FA_SUM` restituisce un valore *Contenitore (record)* costituito dai dati per gli importi cespiti per l'articolo dei cespiti specificato, il codice del modello di valore e il periodo di date.

## <a name="syntax"></a>Sintassi

```vb
FA_SUM (fixed asset code, value model code, start date, end date)
```

## <a name="arguments"></a>Argomenti

`fixed asset code`: *Stringa*

Un valore *Stringa* che rappresenta il codice di un articolo dei cespiti per il quale viene calcolato il saldo.

`value model code`: *Stringa*

Un valore *Stringa* che rappresenta il codice di un modello di valore per il quale viene calcolato il saldo.

`start date`: *Data*

Un valore *Data* che rappresenta la data di inizio di un periodo per il quale sono calcolati gli importi cespiti.

`end date`: *Data*

Un valore *Data* che rappresenta la data di fine di un periodo per il quale sono calcolati gli importi cespiti.

## <a name="return-values"></a>Valori restituiti

*Contenitore (record)*

Il valore del record risultante.

## <a name="example"></a>Esempio

`FA_SUM ("COMP-000001", "Current", Date1, Date2)` restituisce il contenitore di dati per il cespite **COMP-000001** che è stato preparato per il modello di valore **corrente** e per un periodo da **Date1** a **Date2**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]