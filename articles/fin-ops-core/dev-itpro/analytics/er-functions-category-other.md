---
title: Elenco delle funzioni ER nella categoria specifica del dominio aziendale
description: Questo argomento fornisce informazioni sulle funzioni specifiche del dominio aziendale supportate nella creazione di report elettronici (ER).
author: NickSelin
ms.date: 12/12/2019
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
ms.openlocfilehash: a3d2055be7a755e35d0e88230e19038cf2d02ccc
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748017"
---
# <a name="list-of-er-functions-in-the-business-domainspecific-category"></a>Elenco delle funzioni ER nella categoria specifica del dominio aziendale

[!include [banner](../includes/banner.md)]

Le funzioni specifiche del dominio della creazione di report elettronici (ER) possono essere utilizzate per eseguire calcoli e richieste di accesso ai dati specifici per l'implementazione di Microsoft Dynamics 365 Finance. Questo argomento fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione| Descrizione |
|---------|-------------|
| [CH_Bank_Mod_10](er-functions-other-chbankmode10.md) | Questa funzione restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD10, basato sulle cifre del numero di fattura specificato. |
| [CN_GBT_AdditionalDimensionID](er-functions-other-cngbtadditionaldimensionid.md) | Questa funzione restituisce un valore *Stringa* che rappresenta un singolo ID dimensione finanziaria preso dalla stringa specificata. La stringa specificata presenta tutte le dimensioni come un elenco di ID separato da virgole. |
| [ConvertCurrency](er-functions-other-convertcurrency.md) | Questa funzione restituisce un valore *Reale* che rappresenta il risultato della conversione dell'importo monetario specificato dalla valuta di origine specificata nella valuta di destinazione specificata utilizzando le impostazioni della società specificata alla data specificata. |
| [CurCredRef](er-functions-other-curcredref.md) | Questa funzione restituisce un valore *Stringa* che rappresenta un riferimento creditore basato sulle cifre del numero di fattura specificato. |
| [FA_Balance](er-functions-other-fabalance.md) | Questa funzione restituisce un valore *Contenitore (record)* costituito dai dati per il saldo cespiti per l'articolo dei cespiti specificato, il codice del modello di valore, l'anno di dichiarazione e la data di dichiarazione. |
| [FA_Sum](er-functions-other-fasum.md) | Questa funzione restituisce un valore *Contenitore (record)* costituito dai dati per gli importi cespiti per l'articolo dei cespiti specificato, il codice del modello di valore e il periodo di date. |
| [GetCurrentCompany](er-functions-other-getcurrentcompany.md) | Questa funzione restituisce un valore *Stringa* che rappresenta il codice della persona giuridica (società) a cui un utente è attualmente connesso. |
| [ISOCredRef](er-functions-other-isocredref.md) | Questa funzione restituisce un valore *Stringa* che rappresenta un riferimento creditore International Organization for Standardization (ISO), in base alle cifre e ai simboli alfabetici del numero di fattura specificato. |
| [IsValidCharacterISO7064](er-functions-other-isvalidchariso7064.md) | Questa funzione restituisce un valore *Booleano* **TRUE** quando la stringa specificata rappresenta un numero di conto bancario internazionale (IBAN) valido. In caso contrario, restituisce il valore *Booleano* **FALSE**. |
| [Mod_97](er-functions-other-mod97.md) | Questa funzione restituisce un valore *Stringa* che rappresenta un riferimento creditore come espressione MOD97, basato sulle cifre del numero di fattura specificato. |
| [NumSeqValue](er-functions-other-numseqvalue.md) | Questa funzione restituisce un valore *Stringa* che rappresenta il nuovo valore generato di una sequenza numerica, in base alla sequenza numerica, all'ambito e all'ID ambito specificati. L'ID ambito equivale al codice società fornito dal contesto in cui viene eseguito il formato (ER). |
| [RoundAmount](er-functions-other-roundamount.md) | Questa funzione restituisce un valore *Reale* che rappresenta il risultato dell'arrotondamento dell'importo specificato al numero specificato di posizioni decimali in base alla regola di arrotondamento specificata. |
| [TableName2ID](er-functions-other-tablename2id.md) | Questa funzione restituisce una rappresentazione numerica dell'ID tabella per il nome tabella specificato come valore *Intero*. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]