---
title: Funzione ER DATETODATETIME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione DATETODATETIME della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/04/2019
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
ms.openlocfilehash: bb90c58544eeba804cd39542cc70fab3b840af80
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746965"
---
# <a name="datetodatetime-er-function"></a>Funzione ER DATETODATETIME

[!include [banner](../includes/banner.md)]

La funzione `DATETODATETIME` restituisce un valore *DateTime* che viene convertito da un determinato valore di data a un valore di data/ora in Coordinated Universal Time (Greenwich Mean Time \[GMT\]).

## <a name="syntax"></a>Sintassi

```vb
DATETODATETIME (date)
```

## <a name="arguments"></a>Argomenti

`date`: *Data*

Un valore di data che rappresenta la data da convertire.

## <a name="return-values"></a>Valori restituiti

*Data/Ora*

Il valore di data/ora risultante.

## <a name="example-1"></a>Esempio 1

`DATETODATETIME (CompInfo. 'getCurrentDate()')` restituisce la data della sessione corrente di Microsoft Dynamics 365 Finance, 24 dicembre 2015, come **12/24/2015 12:00:00 AM**. In questo esempio, **CompInfo** è l'origine dati della creazione di report elettronici (ER) del tipo **Finance and Operations/Tabella** e fa riferimento alla tabella CompanyInfo.

## <a name="example-2"></a>Esempio 2

`DATETODATETIME (DATEVALUE ("2019-11-12T16:00:00.0000000-07:00", "O"))` restituisce il valore data/ora **11/12/2019 12:00:00 AM**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di data e ora](er-functions-category-datetime.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]