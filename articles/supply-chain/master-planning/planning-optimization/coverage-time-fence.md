---
title: Intervalli temporali di copertura
description: Questo articolo descrive come configurare gli intervalli temporali di copertura quando si utilizza Ottimizzazione pianificazione. Un intervallo temporale di copertura indica l'orizzonte e il limite di pianificazione.
author: t-benebo
ms.date: 01/18/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqPlanSched
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-18
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: ebd59e05d2ae227f24e7dae6fae3634aab026c5a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8847935"
---
# <a name="coverage-time-fences"></a>Intervalli temporali di copertura

[!include [banner](../../includes/banner.md)]

Questo articolo descrive come configurare gli *intervalli temporali di copertura* quando si utilizza Ottimizzazione pianificazione. I responsabili della pianificazione possono definire l'orizzonte di pianificazione (l'intervallo temporale di copertura in giorni) ed escludere la domanda e l'offerta che superano tale orizzonte. Pertanto, gli intervalli temporali di copertura aiutano a prevenire i "disturbi" causati da suggerimenti di domanda a cui non è necessario reagire per mesi. Gli esempi includono la previsione del prossimo anno e gli ordini dei clienti che vengono effettuati ben oltre il normale lead time.

Un intervallo temporale di copertura è il numero di giorni dopo la data odierna (o, più precisamente, la data in cui si esegue la pianificazione) in cui la domanda e l'offerta sono escluse. Per evitare ritardi, è necessario assicurarsi che l'intervallo temporale di copertura sia più lungo del lead time totale. Il valore di sistema predefinito è 100 giorni.

È possibile specificare un intervallo temporale di copertura a ciascuno dei seguenti livelli:

- **Gruppo di copertura**: è possibile impostare un intervallo temporale di copertura predefinito per ciascun gruppo di copertura.
- **Copertura articoli**: è possibile sovrascrivere l'intervallo temporale di copertura ereditato dal gruppo di copertura assegnato a un articolo.
- **Piano generale**: è possibile sovrascrivere gli intervalli temporali di copertura ereditati dal gruppo di copertura e le impostazioni di copertura degli articoli.

Le sezioni seguenti spiegano come specificare un gruppo di copertura a ciascun livello.

## <a name="set-a-coverage-time-fence-for-a-coverage-group"></a>Impostare un intervallo temporale di copertura per un gruppo di copertura

Quando si specifica un intervallo temporale di copertura per un gruppo di copertura, l'impostazione si applica a tutti gli articoli (prodotti) che appartengono a quel gruppo. Tuttavia, è possibile sovrascrivere l'impostazione per articoli specifici o piani generali specifici.

Per specificare un intervallo temporale di copertura per un gruppo di copertura, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Copertura \> Gruppi di copertura**.
1. Selezionare un gruppo di copertura esistente nell'elenco o creare un nuovo gruppo di copertura.
1. Nella Scheda dettaglio **Generale**, impostare il campo **Intervallo temporale di copertura (giorni)** sul numero di giorni che si desidera utilizzare come intervallo temporale di copertura per il gruppo di copertura.

## <a name="set-a-coverage-time-fence-for-a-specific-item"></a>Impostare un intervallo temporale di copertura per un articolo specifico

Ogni articolo (prodotto) appartiene a un gruppo di copertura. Se nessun gruppo di copertura è assegnato esplicitamente a un articolo, viene applicato un gruppo di copertura predefinito. Ogni elemento eredita un intervallo temporale di copertura dal proprio gruppo di copertura. Tuttavia, puoi sostituire questo intervallo temporale per articoli specifici in base alle tue esigenze.

Per specificare un intervallo temporale di copertura per un articolo specifico, attenersi alla seguente procedura.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare un prodotto nella griglia.
1. Nella scheda **Pianifica** del riquadro azione, nel gruppo **Copertura**, seleziona **Copertura articoli**.
1. Nella pagina **Copertura articoli**, nella scheda **Panoramica**, selezionare o creare una riga per il sito in cui si desidera impostare un intervallo temporale di copertura.
1. Selezionare la scheda **Generale** per aprire le impostazioni per il sito selezionato.
1. Selezionare la casella di controllo **Ignora impostazioni gruppo di copertura**.
1. Impostare il campo **Intervallo temporale di copertura (giorni)** sul numero di giorni che si desidera utilizzare come intervallo temporale di copertura per l'articolo.

## <a name="set-a-coverage-time-fence-for-a-specific-master-plan"></a>Impostare un intervallo temporale di copertura per un piano generale specifico

È possibile specificare un intervallo temporale di copertura a livello di piano generale. In questo modo, si definisce il numero di giorni coperti dal calcolo della pianificazione generale per un piano generale. Questa impostazione sostituisce qualsiasi impostazione del tempo di copertura definita per ciascun articolo e gruppo di copertura rilevanti.

Per specificare un intervallo temporale di copertura per un piano generale specifico, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare un piano generale esistente nell'elenco o creane uno nuovo.
1. Nella Scheda dettaglio **Intervalli temporali in giorni**, impostare l'opzione **Copertura** su *Sì*. Quindi, nel campo sotto l'opzione, immettere il numero di giorni che si desidera utilizzare come intervallo temporale di copertura per il piano generale.

## <a name="considerations-for-coverage-time-fences"></a>Considerazioni per gli intervalli temporali di copertura

Durante la configurazione degli intervalli temporali di copertura, tenere a mente i seguenti punti:

- Gli intervalli temporali di copertura influenzano solo i dati di input per la pianificazione generale. Se si verificano ritardi, gli ordini pianificati ottenuto potrebbero avere una data successiva alla data odierna più l'intervallo temporale di copertura.
- Gli intervalli temporali di copertura sono specificati in giorni di calendario. I calendari che utilizzano i giorni lavorativi non influiranno sul calcolo dell'intervallo temporale. Ad esempio, una settimana è sempre considerata di sette giorni, anche se i fine settimana sono impostati come giorni di chiusura nel calendario dell'orario di lavoro.
- Le transazioni di fabbisogno non verranno generate per alcuna domanda e offerta che non rientra nell'intervallo temporale di copertura.
- Se l'offerta e la domanda approvate non rientrano nell'intervallo temporale di copertura, non verranno caricate nel motore. Pertanto, non attiverà alcun rifornimento e i ritardi non verranno calcolati. Tuttavia, questa domanda e offerta non dovrebbero essere cancellate dal sistema.
- Le variazioni nelle quantità di scorte di sicurezza (dalle chiavi minime) verranno ignorate se non rientrano nell'intervallo temporale di copertura.
- La domanda interaziendale verrà ignorata se la data di spedizione richiesta calcolata non rientra nell'intervallo temporale di copertura. Si noti che, per la pianificazione generale incorporata, la domanda interaziendale non è limitata dall'intervallo temporale di copertura.
- Le previsioni della domanda verranno ignorate se la data del budget non è compresa nell'intervallo temporale di copertura. Si noti che, per la pianificazione generale incorporata, le previsioni della domanda non sono limitate dall'intervallo temporale di copertura.
- Ottimizzazione pianificazione riconosce il fuso orario. Considera il fuso orario nei siti di domanda e offerta e l'ora dell'esecuzione della pianificazione. Ad esempio, la pianificazione generale viene attivata alle 11:00 del 15 ottobre da un sito in Danimarca (fuso orario GMT+1) e viene utilizzato un intervallo temporale di copertura di dieci giorni. In questo caso, l'offerta e la domanda da un sito a Seattle (fuso orario GMT-8) sono incluse fino alle 2:00 del 25 ottobre (= dieci giorni di 24 ore dopo l'attivazione della pianificazione generale, meno la differenza di fuso orario di nove ore). Si noti che il motore di pianificazione generale integrato considera solo la data dell'intervallo temporale. Pertanto, il risultato può differire.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]