---
title: Funzione ER DATETIMEFORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETIMEFORMAT della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/03/2019
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
ms.openlocfilehash: 98919f40751a77465ae26acbd46af4396c588b13
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916409"
---
# <a name="DATETIMEFORMAT">Funzione ER DATETIMEFORMAT</a>

[!include [banner](../includes/banner.md)]

La funzione `DATETIMEFORMAT` restituisce un valore *Stringa* che presenta un valore specifico di data/ora come testo nel formato specificato e nelle impostazioni [cultura](https://docs.microsoft.com/bingmaps/rest-services/common-parameters-and-types/supported-culture-codes) specificate facoltativamente. Per informazioni sui formati supportati, vedere [standard](https://msdn.microsoft.com/library/az4se3k1(v=vs.110).aspx) e [personalizzato](https://msdn.microsoft.com/library/8kb3ddd4(v=vs.110).aspx).

## <a name="syntax-1"></a>Sintassi 1

```
DATETIMEFORMAT (datetime, format)
```

## <a name="syntax-2"></a>Sintassi 2

```
DATETIMEFORMAT (datetime, format, culture)
```

## <a name="arguments"></a>Argomenti

`datetime`: *DateTime*

Un valore di data/ora che rappresenta la data e l'ora da formattare.

`format`: *Stringa*

Formato della stringa di output.

`culture`: *Stringa*

La cultura da utilizzare per la formattazione.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di stringa risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Quando la cultura non è definita come argomento della funzione richiamata, il valore di `culture` è definito dal contesto di chiamata. Ad esempio, se la funzione `DATETIMEFORMAT` viene richiamata utilizzando la sintassi 1 in un formato creazione di report elettronici (ER) per un elemento **FILE** che è configurato per utilizzare la cultura tedesca, la conversione verrà effettuata utilizzando la cultura tedesca. Il valore `culture` predefinito è **EN-US**.

Quando la funzione `DATETIMEFORMAT` converte un determinato valore data/ora, considera l'impostazione del fuso orario dell'utente dell'applicazione che esegue il formato ER da cui viene richiamata la funzione nel contesto.

## <a name="example-1"></a>Esempio 1

`DATETIMEFORMAT (NOW(), "dd-MM-yyyy")` restituisce il valore data/ora del server di applicazioni, 24 dicembre 2015, come **"24-12-2015"**, in base al formato personalizzato specificato.

## <a name="example-2"></a>Esempio 2

`DATETIMEFORMAT (SESSIONNOW(), "d", "DE")` restituisce la data/ora della sessione dell'applicazione corrente, il 24 dicembre 2015, come **"24.12.2015"**, basata sulla cultura tedesca selezionata e sul formato specificato.

## <a name="example-3"></a>Esempio 3

`DATETIMEFORMAT (DATETIMEVALUE( "2019-11-12T09:00:00.0000000-07:00", "O"), "O")` restituisce il valore della stringa **2019-11-12T08:00:00.0000000-08:00** quando viene richiamato durante un processo avviato da un utente dell'applicazione che ha il valore del fuso orario **(GMT-08: 00) Pacific Time (Stati Uniti e Canada)** nella sezione **Preferenze di lingua e paese**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)
