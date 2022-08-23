---
title: Funzione ER FORMATELEMENTNAME
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione FORMATELEMENTNAME della creazione di report elettronici (ER).
author: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: 1c8c319075f8f39bec963df2c88d2d8d3beace43
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275433"
---
# <a name="formatelementname-er-function"></a>Funzione ER FORMATELEMENTNAME

[!include [banner](../includes/banner.md)]

La funzione `FORMATELEMENTNAME` restituisce un valore *Stringa* che rappresenta il nome dell'elemento del formato corrente della creazione di report elettronici (ER).

## <a name="syntax"></a>Sintassi

```vb
FORMATELEMENTNAME ()
```

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Questa funzione può essere richiamata in espressioni ER configurate per le proprietà **Nome chiave dati raccolti** e **Valore chiave dati raccolti** di un componente del formato ER dal gruppo **Text** che risiede nel componente **Common\\File** in cui è attivata l'opzione **Raccogli dettagli di output**.

## <a name="example"></a>Esempio

Per ulteriori informazioni sull'utilizzo di questa funzione, fare riferimento alla guida attività [ER Utilizzare i dati dell'output del formato per il conteggio e la somma](tasks/er-format-counting-summing-1.md) che è parte del processo aziendale **Acquisire/sviluppare componenti di soluzioni/servizi IT**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni raccolta dati](er-functions-category-data-collection.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
