---
title: Funzione ER FA_SUM
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FA_SUM della creazione di report elettronici (ER).
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
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 03bed091350b39601edb22b5af6bda5a83af47eb
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "3041356"
---
# <a name="FA_SUM">Funzione ER FA_SUM</a>

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
