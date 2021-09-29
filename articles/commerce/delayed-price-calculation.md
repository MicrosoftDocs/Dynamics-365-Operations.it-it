---
title: Ritardare il calcolo del prezzo esatto e dello sconto per prestazioni migliori
description: Questo argomento descrive la capacità di calcolo differito del prezzo disponibile in Microsoft Dynamics 365 Commerce POS e servizio clienti.
author: boycezhu
ms.date: 09/09/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: boycez
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 8c4264c3a4c71e6aab0e1ef8d7d8cfffad065a46
ms.sourcegitcommit: 7a2001e4d01b252f5231d94b50945fd31562b2bc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/15/2021
ms.locfileid: "7488365"
---
# <a name="delay-exact-price-and-discount-calculation-for-improved-performance"></a>Ritardare il calcolo del prezzo esatto e dello sconto per prestazioni migliori

[!include [banner](includes/banner.md)]

Questo argomento descrive la capacità di calcolo differito del prezzo disponibile in Microsoft Dynamics 365 Commerce POS e servizio clienti.

Dynamics 365 Commerce supporta la creazione di sconti multiriga che vengono applicati quando vengono combinate più righe di vendita di un ordine cliente o di un'offerta di vendita. Questi sconti includono sconti combinati, soglia e quantità.

Ogni volta che viene aggiunta una nuova riga a un ordine, il motore di determinazione del prezzo di Commerce valuta l'intero carrello per determinare se uno di questi sconti multiriga può essere applicato. A causa di questo ricalcolo, l'aggiunta di nuove righe può influire sulle prestazioni man mano che un ordine cliente cresce.

Tuttavia, le aziende business-to-business (B2B) e alcune aziende business-to-consumer (B2C) hanno spesso ordini di grandi dimensioni. Pertanto, può richiedere molto tempo attendere che il motore di determinazione dei prezzi venga ricalcolato dopo che ogni articolo viene aggiunto al carrello. Inoltre, per ordini di grandi dimensioni, di solito non è molto importante che il prezzo esatto e lo sconto vengano mostrati ogni volta che un articolo viene aggiunto al carrello. È più importante che gli utenti siano in grado di aggiungere articoli rapidamente. La capacità di ritardare il calcolo del prezzo esatto e dello sconto fino a quando un utente non lo richiede o non viene finalizzato un ordine può migliorare significativamente le prestazioni. Può anche ridurre il tempo necessario per completare l'ordine.

La capacità di ritardare il calcolo del prezzo esatto e dello sconto è disponibile da tempo in POS. A partire dalla versione 10.0.22 di Commerce, è disponibile anche per il servizio clienti.

## <a name="enable-delayed-price-and-discount-calculation-for-pos"></a>Abilitare il calcolo del prezzo ritardato e dello sconto per POS

Per abilitare il calcolo del prezzo ritardato e dello sconto per POS, segui questi passaggi.

1. In Commerce headquarters, vai al profilo di funzionalità associato al negozio fisico.
1. Nella scheda dettaglio **Quantità** abilita la configurazione **Calcola manualmente sconti su più articoli**.
1. Apri la finestra di progettazione del layout dello schermo per i registri in cui deve essere abilitato il calcolo ritardato.
1. Aggiungi un pulsante per l'operazione **Calcola totale** alla griglia dei pulsanti desiderata.
1. Esegui i processi **1070** e **1090**.

Ora, quando gli articoli vengono aggiunti a una transazione, gli sconti multiriga non vengono calcolati a meno che il cassiere non selezioni il pulsante **Calcola totale**. Dopo aver selezionato **Calcola totale** per una transazione, verranno sempre calcolati gli sconti multiriga. Il cassiere non dovrà selezionare nuovamente il pulsante, anche se vengono aggiunti altri articoli al carrello. Il sistema non consentirà al cassiere di acquisire il pagamento fino a quando non seleziona **Calcola totale**.

## <a name="enable-delayed-price-and-discount-calculation-for-call-center"></a>Abilitare il calcolo del prezzo ritardato e dello sconto per servizio clienti

Per abilitare il calcolo del prezzo ritardato e dello sconto per servizio clienti, segui questi passaggi.

1. In Commerce headquarters, vai a **Aree di lavoro \> Gestione funzionalità**.
1. Abilita la funzionalità **Impedisci calcolo non intenzionale dei prezzi per ordini commerciali**. Questa funzione è un prerequisito per la capacità di calcolo differito del prezzo e dello sconto.

    > [!NOTE]
    > Per le nuove implementazioni, la funzionalità **Impedisci calcolo non intenzionale dei prezzi per ordini commerciali** è abilitata per impostazione predefinita.

1. Vai a **Parametri di commercio \> Prezzi e sconti**.
1. Nella sezione **Varie** abilita la configurazione **Calcola manualmente prezzi e sconti su più righe**.

Ora, quando un ordine cliente o un'offerta di vendita viene creato o modificato nel servizio clienti, il calcolo del prezzo esatto e dello sconto verranno ritardati. Il motore di determinazione del prezzo prenderà in considerazione solo la riga di vendita che viene aggiunta o modificata e ignorerà tutte le altre righe di vendita. L'importo netto per un articolo include il calcolo del prezzo e degli sconti semplici (percentuale di sconto o importo di sconto su un singolo articolo). Tuttavia, non verranno applicati sconti combinati, soglia e quantità. Gli utenti del servizio clienti che desiderano visualizzare il prezzo esatto, inclusi tutti gli sconti, possono selezionare uno dei tre pulsanti: **Ricalcola**, **Totali**, o **Completa**.

> [!NOTE]
> Per gli ordini del servizio clienti, il sistema mostra un messaggio di avviso per ricordare all'utente che deve selezionare il pulsante **Ricalcola**, **Totali**, o **Completa** per il calcolo esatto del prezzo e dello sconto. Per ordini in cui il pulsante **Completa** è disponibile, non c'è modo per l'utente del servizio clienti di omettere il calcolo dekl prezzo esatto e dello sconto, perché deve selezionare **Completa** per completare l'acquisizione dell'ordine. Per ordini in cui il pulsante **Completa** non è disponibile, non c'è alcuna azione che indichi il completamento dell'acquisizione dell'ordine. Pertanto, l'utente del servizio clienti è responsabile della selezione di **Ricalcola** o **Totali** prima di completare l'acquisizione dell'ordine.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
