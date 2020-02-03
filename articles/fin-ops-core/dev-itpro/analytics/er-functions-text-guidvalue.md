---
title: Funzione ER GUIDVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GUIDVALUE della creazione di report elettronici (ER).
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
ms.openlocfilehash: be5e8e7625d0226c9eb59efd3217fce7b8eba086
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2915696"
---
# <a name="GUIDVALUE">Funzione ER GUIDVALUE</a>

[!include [banner](../includes/banner.md)]

La funzione `GUIDVALUE` converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*.

## <a name="syntax"></a>Sintassi

```
GUIDVALUE (input)
```

## <a name="arguments"></a>Argomenti

`input`: *Stringa*

Il percorso valido di un'origine dati del tipo *Stringa*.

## <a name="return-values"></a>Valori restituiti

*GUID*

Il valore dell'identificatore univoco globale (GUID) risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Per impostare una conversione nella direzione opposta (ovvero convertire l'input specificato del tipo di dati *GUID* in un elemento dati di tipo *Stringa*), è possibile usare la funzione [TEXT](er-functions-text-text.md).

## <a name="example"></a>Esempio

Definire le origini dati seguenti nel mapping di modello:

- Un'origine dati **myID** del tipo *Campo calcolato* che contiene l'espressione `GUIDVALUE ("AF5CCDAC-F728-4609-8C8B- A4B30B0C0AA0")`
- Un'origine dati **Users** del tipo *Record di tabella* che fa riferimento alla tabella UserInfo

È quindi possibile utilizzare un'espressione come `FILTER (Users, Users.objectId = myID)` per filtrare la tabella UserInfo in base al campo **objectId** del tipo di dati *GUID*.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)