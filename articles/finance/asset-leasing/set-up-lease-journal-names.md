---
title: Configurare nomi di giornale di leasing
description: Questo argomento spiega come definire i nomi dei giornali di leasing. I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrati i movimenti che hanno origine in Leasing cespite.
author: moaamer
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a92461e742f1675e4cfda89e6c80c5b087ff5bfb
ms.sourcegitcommit: d715e44b92b84b1703f5915d15d403ccf17c6606
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2022
ms.locfileid: "8644899"
---
# <a name="set-up-lease-journal-names"></a>Configurare nomi di giornale di leasing

[!include [banner](../includes/banner.md)]


I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrate le transazioni di Leasing cespite. Solo i nomi di giornale di registrazione assegnati al tipo di giornale di registrazione **Leasing cespite** vengono visualizzati nei campi **Riconoscimento iniziale** e **Nome giornale di registrazione mensile** della pagina **Parametri del leasing cespite**. Solo il tipo di giornale di registrazione **registrazione fattura fornitore** può essere assegnato al campo **Nome giornale di registrazione fatture**.

Il sistema blocca la modifica di determinati campi finanziari per evitare eventuali scostamenti tra le transazioni e le pianificazioni. Alcuni campi bloccati includono: **Conto**, **Importi**, **Dimensioni finanziarie**, **Valuta** e **Tipo di transazione**. Inoltre, non sarà possibile aggiungere o eliminare righe di scrittura contabile in nessuna scrittura contabile del leasing cespiti, poiché ciò potrebbe causare scostamenti tra le pianificazioni e le transazioni.


Per configurare i nomi dei giornali di leasing, completa questi passaggi.

1. Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.
2. Nella scheda **Generale**, nel campo **Nome giornale di registrazione riconoscimento iniziale**, seleziona un giornale di registrazione. Tutte le registrazioni a giornale di riconoscimento iniziale verranno registrate in questo nome di giornale di registrazione.
3. Nel campo **Nome giornale di registrazione fatture**, seleziona un giornale di registrazione. Se l'opzione **Paga a fornitore** è impostata su **Sì** per il libro di leasing, le fatture di pagamento di leasing e spese verranno registrate in questo nome di giornale di registrazione.
4. Nel campo **Nome giornale di registrazione leasing**, seleziona un giornale di registrazione. Tutti i movimenti di ammortamento, interessi e riclassificazione a breve termine verranno registrati in questo nome giornale di registrazione. Se l'opzione **Paga a fornitore** è impostata su **No** per il libro di leasing, anche i movimenti di pagamento di leasing e spese verranno registrati in questo nome di giornale di registrazione.
5. Nel campo **Nome giornale di registrazione modifica leasing**, seleziona un giornale di registrazione. Le transazioni di rettifica leasing, cessazione e riduzione di valore verranno registrate in questo nome del giornale. Al nome del giornale selezionato non deve essere assegnato un flusso di lavoro o un'approvazione. Se il nome del giornale di registrazione di modifica leasing non è definito, le transazioni di rettifica leasing, cessazione e riduzione di valore verranno registrate nel nome del giornale selezionato nel campo **Nome del giornale di leasing**. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
