---
title: Impostazioni di storno per giornali di registrazione e righe
description: In questo articolo viene illustrato il motivo per cui un movimento di storno immesso in un giornale di registrazione generale potrebbe non essere incluso nella transazione registrata.
author: kweekley
ms.date: 04/29/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-5-05
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e36a3ea1736e4d7f60a5a6ce588ad3e66c950c14
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899844"
---
# <a name="reverse-settings-on-journals-and-lines"></a>Impostazioni di storno per giornali di registrazione e righe

[!include [banner](../includes/banner.md)]

In questo articolo viene illustrato il motivo per cui un movimento di storno immesso in un giornale di registrazione generale potrebbe non essere incluso nella transazione registrata.  

## <a name="symptom"></a>Sintomo

Un giornale di registrazione generale include una registrazione di storno e una data di storno. Quando il giornale di registrazione viene contabilizzato, i giustificativi non vengono stornati. Perché succede questo?

## <a name="resolution"></a>Risoluzione

Quando il giornale di registrazione viene contabilizzato, il processo di storno esamina solo le impostazioni **Inserimento di storno** e **Data storno** nella sezione **Righe** del giustificativo. Questo approccio consente a un giornale di includere i giustificativi contrassegnati per lo storno ed escludere gli altri.

I valori del giornale di registrazione vengono utilizzati solo come valori predefiniti durante l'aggiunta di *nuove* righe. La modifica dei valori nel giornale di registrazione non influisce sulle righe esistenti. In questo esempio, le righe del giustificativo sono state inserite per prime. Quando si immette il dettaglio della riga prima di designare il giornale di registrazione come storno, la designazione come inserimento di storno e data di storno non viene applicata a nessuna riga esistente.

La modifica dell'inserimento di storno o della data di storno su una riga esistente viene propagata ad altre righe nello stesso giustificativo. Per ottimizzare le prestazioni, la griglia non viene aggiornata dopo la propagazione delle modifiche ad altre righe. È possibile visualizzare i valori modificati aggiornando la griglia.


