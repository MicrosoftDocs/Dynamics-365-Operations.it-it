---
title: Attività periodiche di gestione dei crediti
description: In questo argomento vengono descritte le attività periodiche che sono una parte necessaria del processo di gestione dei limiti di credito per i clienti.
author: mikefalkner
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5e5d1ad7b0b151d67bd96513e9ce0c82c172a601
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835294"
---
# <a name="periodic-credit-management-tasks"></a>Attività periodiche di gestione crediti

[!include [banner](../includes/banner.md)]

In questo argomento vengono descritte le attività periodiche che sono una parte necessaria del processo di gestione dei limiti di credito per i clienti.

## <a name="update-risk-scores"></a>Aggiorna punteggi di rischio

Man mano che le aziende evolvono e le circostanze cambiano, anche i rischi di credito per un determinato cliente possono cambiare. Per aiutare a mantenere i limiti di credito appropriati per i clienti, è necessario rivedere periodicamente i criteri per ogni punteggio di rischio e aggiornare i punteggi per ogni cliente. È possibile aggiornare i seguenti punteggi utilizzando la pagina **Aggiorna punteggi di rischio** (**Credito e riscossioni \> Attività periodiche \> Gestione crediti \> Aggiorna punteggi di rischio**). Vengono inoltre elaborati tutti i calcoli definiti dall'utente.

- **Numero medio di giorni per pagamento** - Questo punteggio è il numero medio di giorni che un cliente impiega per pagare le fatture.
- **Cliente da** - Questo punteggio è il numero di anni in cui un cliente è stato cliente dell'organizzazione.
- **In attività da** - Questo punteggio indica il numero di anni di attività di un cliente. Utilizza il valore del campo **Inizio attività** nella pagina **Clienti**.
- **Tempo medio di incasso** - Questo punteggio si basa sul saldo della contabilità clienti, sui ricavi delle vendite e sul numero di giorni per il precedente periodo di 12 mesi.
- **Saldo medio** - Questo punteggio si basa sul saldo della contabilità clienti per il precedente periodo di 12 mesi.
- **Gruppo di gestione crediti**, **Stato conto** e **Paese** - Questi punteggi utilizzano le informazioni del cliente.

## <a name="update-customer-balance-statistics"></a>Aggiornare le statistiche del saldo clienti

È possibile eseguire il processo **Aggiorna statistiche saldo clienti** per aggiornare il calcolo delle statistiche del saldo visualizzato nella pagina **Richiesta informazioni su statistiche del saldo**. Queste informazioni vengono utilizzate per calcolare i punteggi di rischio e i valori visualizzati nei Dettagli informazioni sulle statistiche del credito nella pagina **Cliente**.

Quando si esegue il processo, aggiorna le statistiche sul saldo clienti per un singolo cliente. Per impostare un processo batch allo scopo di eseguire il processo per più clienti, è possibile utilizzare la pagina **Calcola statistiche saldo** (**Gestione crediti \> Attività periodiche \> Calcola statistiche saldo**).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]