---
title: Impostazione dei parametri di Gestione crediti
description: Questo argomento descrive le opzioni che è possibile utilizzare per configurare Gestione crediti e soddisfare i requisiti della propria azienda.
author: mikefalkner
manager: AnnBe
ms.date: 08/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0b25bbeb270f33d1d158de2091ab86e7e98be98a
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976549"
---
# <a name="credit-management-parameters-setup"></a>Impostazione dei parametri di Gestione crediti

[!include [banner](../includes/banner.md)]

Questo argomento descrive le opzioni che è possibile utilizzare per configurare Gestione crediti e soddisfare i requisiti della propria azienda. Per iniziare a utilizzare le funzionalità Gestione crediti, impostare i parametri nella pagina **Parametri credito e riscossioni** (**Credito e riscossioni \> Impostazione \> Parametri credito e riscossioni**).

## <a name="credit-parameters"></a>Parametri per crediti

Sono disponibili quattro schede dettaglio nella sezione **Credito** in cui è possibile modificare i parametri di Gestione crediti: **Sospensioni credito**, **Checkpoint gestione crediti**, **Statistiche gestione crediti** e **Limiti di credito**. Le seguenti sezioni descrivono le impostazioni disponibili in ogni scheda dettaglio.

### <a name="credit-holds"></a>Blocchi credito

- Impostare l'opzione **Consenti modifica del valore ordine cliente dopo il rilascio della sospensione dell'ordine** su **No** per richiedere che le regole di registrazione vengano nuovamente controllate se il valore dell'ordine cliente (prezzo esteso) è stato aumentato dal momento in cui l'ordine cliente è stato rilasciato dall'elenco di sospensioni. .
- Nel campo **Motivi per ordini annullati**, selezionare il motivo del rilascio che verrà utilizzato per impostazione predefinita quando un ordine cliente in attesa della gestione del credito viene annullato.
- Impostare l'opzione **Verifica limite di credito di gruppi di crediti cliente** su **Sì** per controllare il limite di credito di un gruppo di crediti cliente quando il cliente in un ordine cliente appartiene a un gruppo di crediti cliente. Il limite di credito per il gruppo verrà verificato e quindi, se è sufficiente, verrà verificato il limite di credito per il cliente.
- Impostare l'opzione **Verifica limite di credito quando vengono aumentati i termini di pagamento** su **Sì** per controllare la classificazione dei termini di pagamento e determinare se i termini di pagamento nell'ordine cliente differiscono dai termini di pagamento predefiniti per il cliente. Se i nuovi termini di pagamento hanno una classificazione superiore rispetto ai termini di pagamento originali, l'ordine viene messo in attesa per la gestione del credito.
- Impostare l'opzione **Verifica limite di credito quando viene aumentato uno sconto per liquidazione** su **Sì** per controllare la classificazione dello sconto per classificazione e determinare se lo sconto di cassa nell'ordine cliente differisce dallo sconto di cassa predefinito per il cliente. Se il nuovo sconto di cassa ha una classificazione superiore rispetto allo sconto di cassa originale, l'ordine viene messo in attesa per la gestione del credito.
- Nel campo **Motivo del rilascio di ordini modificati**, selezionare il motivo di rilascio che verrà utilizzato per impostazione predefinita quando gli ordini modificati vengono automaticamente rilasciati dalla sospensione per la gestione del credito.
- Impostare l'opzione **Ignora regola di blocco limite di credito scaduto quando la data di scadenza è vuota** su **Sì** per controllare il comportamento della regola **Limite di credito scaduto**. Impostare l'opzione su **No** per bloccare un ordine quando la data di scadenza è vuota.
- In Gestione magazzino, i carichi possono essere creati al momento della registrazione dell'ordine cliente. Impostare l'opzione **Rimuovi righe di carico bloccate** su **No** per mantenere le righe dell'ordine cliente sul carico quando un ordine cliente è in attesa del credito. Il carico non può essere elaborato quando l'ordine cliente è in attesa. Impostare l'opzione su **Sì** per rimuovere le righe dell'ordine cliente dal carico quando un ordine cliente è in attesa del credito. Il carico può quindi essere elaborato.
- Gli ordini cliente possono essere automaticamente rilasciati dalla verifica della gestione del credito. Nel campo **Motivo per rilasciare automaticamente**, selezionare il motivo del rilascio che verrà utilizzato per impostazione predefinita quando gli ordini cliente vengono rilasciati automaticamente.
- Gli ordini cliente possono essere automaticamente rilasciati dalla verifica della gestione del credito. Nel campo **Rilascio automatico**, selezionare **Senza registrazione** per rilasciare la sospensione di un ordine. È necessario eseguire manualmente il processo che ha messo l'ordine in attesa. Selezionare **Con registrazione** per registrare l'ordine utilizzando lo stesso processo di registrazione eseguito quando l'ordine cliente è stato messo in attesa.

### <a name="credit-management-checkpoint"></a>Checkpoint di gestione crediti

È possibile impostare il tempo che viene utilizzato per controllare gli ordini cliente per problemi relativi al credito. La scheda dettaglio **Checkpoint gestione crediti** identifica i processi di registrazione dei documenti che includono l'elaborazione delle regole di gestione dei crediti. È inoltre possibile controllare le regole di credito mentre si effettua una registrazione pro-forma o una registrazione completa dell'ordine cliente. Selezionare le caselle di controllo per definire i processi di registrazione che dovrebbero mettere in attesa un ordine se viene riscontrato un problema dopo l'elaborazione delle regole di blocco della gestione dei crediti.

È inoltre possibile definire il numero di giorni di tolleranza prima che le regole di credito vengano ricontrollate. Sebbene sia possibile specificare che le regole di gestione dei crediti siano verificate al momento della registrazione, le regole non verranno controllate per il numero di giorni di tolleranza specificato. Ad esempio, si conferma un ordine cliente il giorno 1 e si specificano due giorni di tolleranza per la fase di conferma. In questo caso, le regole di credito non verranno verificate nella fase di registrazione successiva (ad esempio, creazione di un documento di trasporto o fatturazione dell'ordine) fino al giorno 4. Il giorno 4 o successivamente, le regole verranno ricontrollate quando si verifica la registrazione e il numero di giorni di tolleranza verrà modificato nel valore specificato per il checkpoint di registrazione successivo.

Se non si specifica il numero di giorni di tolleranza, le regole di credito verranno verificate a ogni fase di registrazione impostata per l'esecuzione delle regole di gestione dei crediti. Se si rilascia l'ordine cliente senza registrazione e si esegue nuovamente la stessa fase di elaborazione dell'ordine, le regole di credito verranno nuovamente controllate. Ad esempio, un ordine viene messo in attesa dopo una conferma e lo si rilascia con o senza registrazione. In questo caso, l'ordine verrà nuovamente messo in attesa se viene confermato di nuovo. Utilizzare i giorni di tolleranza se l'ordine deve passare alla fase di elaborazione successiva senza essere messo di nuovo in attesa.

È possibile specificare i giorni di tolleranza per alcuni checkpoint di registrazione, ma non per altri. È necessario impostare tutti i checkpoint di registrazione di modo che abbiano o meno giorni di tolleranza.

- Selezionare la casella di controllo **Registrazione** per eseguire le regole di gestione di crediti quando viene eseguito il checkpoint di registrazione visualizzato nella riga. Se non si seleziona la casella di controllo, le regole verranno verificate una sola volta durante l'intero processo di registrazione.
- Se si seleziona la casella di controllo **Registrazione**, specificare il numero di giorni di tolleranza che devono trascorrere prima che le regole di blocco vengano nuovamente controllate. Non è possibile aggiungere giorni di tolleranza se la casella di controllo **Registrazione** è deselezionata.
- Selezionare la casella di controllo **Proforma** per eseguire le regole di gestione di crediti quando viene eseguito il checkpoint di registrazione proforma visualizzato sulla riga. Nella maggior parte dei casi, il campo **Registrazione** è impostato su **No** nella finestra di dialogo che appare quando viene registrato un ordine cliente.
- Se si seleziona la casella di controllo **Registrazione**, specificare il numero di giorni di tolleranza che devono trascorrere prima che le regole di blocco vengano nuovamente controllate. Non è possibile aggiungere giorni di tolleranza se la casella di controllo **Registrazione** è deselezionata.

### <a name="credit-management-statistics"></a>Statistiche gestione crediti

Diverse statistiche sulla gestione dei crediti sono incluse nella scheda dettaglio **Statistiche sulla gestione di crediti cliente** nella pagina **Cliente**. È necessario specificare diversi valori richiesti per calcolare tali statistiche. Immettere il numero di mesi utilizzato per calcolare i seguenti valori nella scheda dettaglio **Statistiche sulla gestione di crediti cliente**:

1. Tempo medio di incasso 1
2. Tempo medio di incasso 2
3. Saldo medio 1
4. Saldo medio 2
5. % limite di credito medio
6. % esposizione media

### <a name="credit-limits"></a>Limiti di credito

- In Gestione crediti, il limite di credito cliente viene mostrato nella valuta del cliente. È necessario definire il tipo di tasso di cambio per il limite di credito nella valuta del cliente. Nel campo **Tipo di tasso di cambio limite di credito**, selezionare il tipo di tasso di cambio da utilizzare per convertire il limite di credito primario in limite di credito del cliente.
- Impostare l'opzione **Consenti modifica manuale dei limiti di credito** su **No** per impedire agli utenti di modificare i limiti di credito nella pagina **Cliente**. Se questa opzione è impostata su **No**, le modifiche al limite di credito di un cliente possono essere effettuate solo registrando le transazioni di correzione del limite di credito.

### <a name="number-sequences-and-shared-number-sequence-parameters"></a>Sequenze numeriche e parametri di sequenza numerica condivisi

Per elaborare le correzioni del limite di credito si deve disporre di un ID giornale di registrazione. È necessario aggiungere il numero di correzione del limite di credito che deve essere utilizzato per generare l'ID giornale di registrazione.
