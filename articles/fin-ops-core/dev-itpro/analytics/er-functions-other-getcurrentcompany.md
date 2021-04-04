---
title: Funzione ER GETCURRENTCOMPANY
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione GETCURRENTCOMPANY della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
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
ms.openlocfilehash: fcb5ef2f218a85bab25f830db583343504c46e98
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567546"
---
# <a name="getcurrentcompany-er-function"></a>Funzione ER GETCURRENTCOMPANY

[!include [banner](../includes/banner.md)]

La funzione `GETCURRENTCOMPANY` restituisce un valore *Stringa* che rappresenta il codice della persona giuridica (società) a cui un utente è attualmente connesso.

## <a name="syntax"></a>Sintassi

```vb
GETCURRENTCOMPANY ()
```

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="example"></a>Esempio

`GETCURRENTCOMPANY ()` restituisce **USMF** per un utente collegato alla società **Contoso Entertainment System USA**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]