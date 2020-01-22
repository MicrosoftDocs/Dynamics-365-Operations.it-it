---
title: Elenco delle funzioni ER della categoria testo
description: Questo argomento fornisce informazioni sulle funzioni di testo supportate nella creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/05/2019
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
ms.openlocfilehash: f519d242fe74196b0d12bdc9df4f1b4b0e585752
ms.sourcegitcommit: 36857283d70664742c8c04f426b231c42daf4ceb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/20/2019
ms.locfileid: "2916616"
---
# <a name="list-of-er-functions-of-the-text-category"></a>Elenco delle funzioni ER della categoria testo

[!include [banner](../includes/banner.md)]

Le funzioni di testo della creazione di report elettronici (ER) possono essere utilizzate per eseguire operazioni sulle origini dati del tipo di dati *Stringa*. Questo argomento fornisce un riepilogo di queste funzioni.

## <a name="list-of-supported-functions"></a>Elenco delle funzioni supportate

| Funzione | Descrizione |
|----------|-------------|
| [Char](er-functions-text-char.md) | Questa funzione restituisce un valore *Stringa* che presenta un singolo carattere a cui si fa riferimento mediante il numero Unicode specificato. |
| [Concatena](er-functions-text-concatenate.md) | Questa funzione restituisce tutte le stringhe di testo specificate come valore *Stringa* dopo che sono stati uniti in una stringa. |
| [Formato](er-functions-text-format.md) | Questa funzione restituisce la stringa specificata come un valore *Stringa* dopo che è stata formattata sostituendo tutte le occorrenze di **%N** con l'argomento *N*-esimo. |
| [GetEnumValueByName](er-functions-text-getenumvaluebyname.md) | Questa funzione cerca un valore *Enum* specifico nell'origine dati di enumerazione specificata utilizzando il nome dell'enumerazione specificato come un valore *Stringa*. Se viene trovato il valore *Enum*, la funzione lo restituisce. |
| [GuidValue](er-functions-text-guidvalue.md) | Questa funzione converte l'input specificato del tipo *Stringa* in un elemento dati del tipo *GUID*. |
| [JsonValue](er-functions-text-jsonvalue.md) | Questa funzione analizza i dati nel formato JSON (JavaScript Object Notation) accessibile nel percorso specificato ed estrae un valore scalare basato sull'ID specifico. Quindi restituisce il valore scalare estratto come valore *Stringa*. |
| [Sinistra](er-functions-text-left.md) | Questa funzione restituisce un valore *Stringa* che presenta il numero specificato di caratteri dall'inizio della stringa specificata. |
| [Len](er-functions-text-len.md) | Questa funzione restituisce un valore *Intero* che presenta il numero specificato di caratteri nella stringa specificata. |
| [Lower](er-functions-text-lower.md) | Questa funzione restituisce la stringa di testo specificata come un valore *Stringa* dopo che è stato convertito in lettere minuscole. |
| [Mid](er-functions-text-mid.md) | Questa funzione restituisce un valore *Stringa* che presenta il numero specificato di caratteri della stringa specificata all'inizio della posizione specificata. |
| [NumberFormat](er-functions-text-numberformat.md) | Questa funzione restituisce un valore *Stringa* che presenta il numero specificato nel formato specificato e nelle impostazioni cultura specificate facoltativamente. |
| [NumeralsToText](er-functions-text-numeralstotext.md) | Questa funzione restituisce il numero specificato come un valore *Stringa* dopo che è stato enunciato (ovvero convertito in stringhe di testo) nella lingua specificata. |
| [PadLeft](er-functions-text-padleft.md) | Questa funzione restituisce un valore *Stringa* della lunghezza specificata in cui l'inizio della stringa specificata viene riempita con una o più istanze dei caratteri specificati. |
| [QrCode](er-functions-text-qrcode.md) | Questa funzione restituisce un valore *Contenitore* che presenta l'immagine del codice QR (Quick Response Code) per la stringa specificata in formato binario. |
| [Sostituisci](er-functions-text-replace.md) | Questa funzione restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa. |
| [Destra](er-functions-text-right.md) | Questa funzione restituisce un valore *Stringa* che presenta il numero specificato di caratteri alla fine della stringa specificata. |
| [Testo](er-functions-text-text.md) | Questa funzione restituisce il numero specificato come un valore *Stringa* dopo che è stato convertito in stringa di testo formattata in base alle impostazioni locali del server dell'istanza corrente dell'applicazione. |
| [Traduci](er-functions-text-translate.md) | Questa funzione restituisce la stringa di testo specificata come un valore *Stringa* dopo che tutta o parte di essa è stata sostituita con un'altra stringa. |
| [Trim](er-functions-text-trim.md) | Questa funzione restituisce la stringa di testo specificata come un valore *Stringa* dopo il troncamento degli spazi iniziali e finali e la rimozione di più spazi tra le parole. |
| [Upper](er-functions-text-upper.md) | Questa funzione restituisce la stringa di testo specificata come un valore *Stringa* dopo che è stato convertito in lettere maiuscole. |

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica sui report elettronici](general-electronic-reporting.md)

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
