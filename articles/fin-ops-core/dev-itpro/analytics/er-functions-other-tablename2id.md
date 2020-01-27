---
title: Funzione ER TABLENAME2ID
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione TABLENAME2ID della creazione di report elettronici (ER).
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
ms.openlocfilehash: 77d889f75f38b3c07855a96bf65f1456ac2f42e2
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915811"
---
# <a name="TABLENAME2ID">Funzione ER TABLENAME2ID</a>

[!include [banner](../includes/banner.md)]

La funzione `TABLENAME2ID` restituisce una rappresentazione numerica dell'ID tabella per il nome tabella specificato come valore *Intero*.

## <a name="syntax"></a>Sintassi

```
TABLENAME2ID (text)
```

## <a name="arguments"></a>Argomenti

`text`: *Stringa*

Un valore di testo che rappresenta un nome di tabella valido.

## <a name="return-values"></a>Valori restituiti

*Intero*

Il valore numerico risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

L'esecuzione di questa funzione può avere risultati diversi in diverse istanze di Microsoft Dynamics 365 Finance, anche se viene utilizzato lo stesso nome di società.

## <a name="example"></a>Esempio

`TABLENAME2ID ("Intrastat")` restituisce **1510**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
