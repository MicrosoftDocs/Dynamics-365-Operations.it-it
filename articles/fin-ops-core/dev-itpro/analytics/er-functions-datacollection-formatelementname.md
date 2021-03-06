---
title: Funzione ER FORMATELEMENTNAME
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FORMATELEMENTNAME della creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/05/2019
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
ms.openlocfilehash: f716fe779903b4e9142b7959d868256f2d84c624
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755230"
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