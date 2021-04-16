---
title: Correzioni limite di credito
description: Questo argomento descrive come impostare e aggiungere correzioni del limite di credito.
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
ms.openlocfilehash: b1669029f28cef924170b47340567af49525e1b7
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5835366"
---
# <a name="credit-limit-adjustments"></a>Correzioni limite di credito 

[!include [banner](../includes/banner.md)]

Le correzioni dei limiti di credito consentono ai gestori dei crediti di aggiornare i limiti di credito e le date di scadenza di un singolo cliente, un gruppo di clienti o di tutti i clienti mediante un processo di registrazione. È possibile aggiungere voci di correzione del limite di credito per aggiornare i clienti e i gruppi di crediti cliente, oppure è possibile utilizzarli per calcolare limiti di credito automatici. Le voci possono quindi essere esaminate, inviate per l'approvazione attraverso un flusso di lavoro e registrate negli account dei clienti.

## <a name="set-up-credit-limit-adjustments"></a>Impostare correzioni del limite di credito

È possibile creare voci nel giornale di registrazione delle correzioni dei limiti di credito nella pagina **Correzione del limite di credito**(**Gestione crediti \> Correzioni del limite di credito \> Correzioni del limite di credito**).

1. Selezionare **Nuovo**. Viene creato un nuovo gruppo di voci con un numero di correzione del limite di credito.
2. Seleziona il tipo di correzione del limite di credito:

    - Selezionare **Limite di credito** per modificare il limite di credito del cliente.
    - Selezionare **Limite di credito temporaneo** per creare un limite di credito temporaneo anziché modificare il limite di credito corrente del cliente. I limiti di credito temporanei hanno la precedenza sul limite di credito di un cliente per un periodo definito. Al termine di tale periodo, il limite di credito del cliente viene riutilizzato.
3. Immettere una descrizione. 

Se la casella di controllo **Registrato** è selezionata, i limiti di credito sono stati applicati. Il campo **Stato approvazione** indica lo stato del flusso di lavoro del giornale di registrazione. Un flusso di lavoro è facoltativo.

### <a name="add-credit-limit-adjustments"></a>Aggiungere correzioni del limite di credito

Per aggiungere manualmente correzioni del limite di credito, selezionare **Righe** e quindi procedere come descritto di seguito.

1. Per aggiungere una correzione del limite di credito per un cliente, utilizzare il menu **Correzioni cliente**. Per aggiungere un limite di credito per un gruppo di crediti cliente, selezionare **Correzioni gruppo di crediti cliente**.
2. Immettere un conto cliente per un conte cliente fattura che deve essere aggiornato con il nuovo limite di credito. Se si è selezionato **Correzioni gruppo di crediti cliente** nel passaggio 1, immettere il gruppo di crediti cliente. Non è possibile immettre un conto cliente e un ID gruppo di crediti cliente nella stessa riga del giornale di registrazione.

    Viene visualizzato il limite di credito corrente e il nome appare automaticamente.

3. Immettere il nuovo limite di credito che dovrebbe sostituire il limite di credito corrente quando viene registrata la voce del limite di credito.
4. Immettere una data per definire la nuova data di scadenza per il limite di credito del cliente. È necessario immettere una data di scadenza del limite di credito quando si crea una correzione del limite di credito.

Il campo **Stato approvazione** indica lo stato del flusso di lavoro della riga del giornale di registrazione.

Se si desidera generare automaticamente le correzioni del limite di credito, è possibile utilizzare il menu **Genera** nel riquadro azioni.
 
### <a name="add-temporary-credit-limit-adjustments"></a>Aggiungere correzioni del limite di credito temporanee

Per aggiungere manualmente correzioni del limite di credito temporanee, seguire i passi successivi per le righe del giornale di registrazione.

1. Per aggiungere una correzione del limite di credito per un cliente, utilizzare il menu **Correzioni cliente**. Per aggiungere un limite di credito per un gruppo di crediti cliente, selezionare **Correzioni gruppo di crediti cliente**.
2. Immettere un conto cliente per un conte cliente fattura che deve essere aggiornato con il nuovo limite di credito. Se si è selezionato **Correzioni gruppo di crediti cliente** nel passaggio 1, immettere il gruppo di crediti cliente. Non è possibile immettre un conto cliente e un ID gruppo di crediti cliente nella stessa riga del giornale di registrazione.

    Se esiste già un limite di credito temporaneo attivo o futuro, il limite di credito temporaneo corrente e gli intervalli di date vengono visualizzati per ciascun limite di credito temporaneo. Il nome appare automaticamente.

3. Immettere il nuovo limite di credito che dovrebbe sostituire il limite di credito corrente.
4. Nei campi **Nuovo dalla data** e **Nuovo fino alla data**, definire il periodo in cui il limite di credito avanzato è valido. È necessario immettere date di scadenza del limite di credito quando si crea un giornale di registrazione delle correzioni del limite di credito.

Il campo **Stato approvazione** indica lo stato del flusso di lavoro della riga del giornale di registrazione.

## <a name="generate-credit-limit-adjustments"></a>Generare correzioni del limite di credito

È anche possibile correggere automaticamente i limiti di credito. Nel riquadro azioni, selezionare **Genera**, quindi selezionare una delle opzioni seguenti:

- Da cliente esistente
- Da gruppo di crediti cliente esistente
- Limiti di credito automatici

### <a name="from-existing-customer"></a>Da cliente esistente

È possibile creare righe del giornale di registrazione da clienti esistenti. Quando si seleziona **Genera \> Da cliente esistente**, viene visualizzata una finestra di dialogo in cui è possibile specificare i criteri per la selezione dei clienti e il calcolo dei nuovi limiti.

1. Immettere un valore di correzione per aggiungere o sottrarre un importo dal limite di credito. Immettere un valore negativo per ridurre il limite di credito corrente o un valore positivo per aumentarlo.
2. Nel campo **Tipo di valore**, selezionare come utilizzare il valore immesso nel passaggio 1 per calcolare il nuovo limite di credito:

    - Selezionare **Valore fisso** per modificare il limite di credito di un importo.
    - Selezionare **Percentuale** per modificare il limite di credito di una percentuale.

3. Immettere un valore utilizzato per arrotondare il limite di credito calcolato. Ad esempio, immettere **10,00** per arrotondare il limite di credito alle unità di valuta 10,00 più vicina.
4. Impostare il campo **Tipo di arrotondamento** per specificare se il resto deve essere arrotondato per eccesso o per difetto.
5. Selezionare il metodo utilizzato per rettificare le date.

    - Se si seleziona **Assoluto**, è possibile inserire date che definiscono l'intervallo di date per i limiti di credito.
    - Se si seleziona **Relativo**, è possibile inserire date di offset per l'intervallo. L'intervallo di date corrente per il limite di credito verrà rettificato dall'offset.

6. Utilizzare la scheda dettaglio **Record da includere** per filtrare l'elenco dei clienti inclusi. Se non si includono filtri, le voci del limite di credito verranno generate per tutti i clienti.
7. Selezionare **OK** per creare le voci di correzione del limite di credito.

### <a name="from-existing-customer-credit-group"></a>Da gruppo di crediti cliente esistente

È possibile creare righe del giornale di registrazione da gruppi di crediti cliente. Quando si seleziona **Genera \> Da gruppo di crediti cliente esistente**, viene visualizzata una finestra di dialogo in cui è possibile specificare i criteri per la selezione di gruppi di crediti cliente e il calcolo dei nuovi limiti. I criteri sono gli stessi criteri utilizzati per creare righe del giornale di registrazione da clienti esistenti. Vedere i passaggi nella sezione precedente.

### <a name="automatic-credit-limits"></a>Limiti di credito automatici

È possibile creare limiti di credito automatici per definire e aggiornare i limiti di credito dei clienti. I limiti di credito automatici vengono creati per un gruppo di rischio e si basano su valori specifici utilizzati nei gruppi di punteggi. È possibile utilizzare questi limiti di credito automatici per generare voci di limiti di credito. Se un cliente è stato assegnato a uno specifico gruppo di rischio e le informazioni sul credito del cliente corrispondono ai criteri per un limite di credito automatico, viene creata una voce di correzione del limite di credito.

#### <a name="create-automatic-credit-limits"></a>Creare limiti di credito automatici

I limiti di credito automatici vengono creati utilizzando correzioni dei limiti di credito. Quando si seleziona **Genera \> Limiti di credito automatici**, viene visualizzata una finestra di dialogo in cui è possibile impostare una data di scadenza per i nuovi limiti di credito che verranno creati in base ai gruppi di rischio a cui sono assegnati i clienti. Al termine, selezionare **OK** per creare le righe di correzione del limite di credito.

### <a name="post-adjustments"></a>Registrare le correzioni

Dopo aver creato le righe di correzione del limite di credito, è possibile utilizzare il pulsante **Registra** nel riquadro azioni per registrare le voci e aggiornare i limiti di credito del cliente. Tuttavia, se è stato impostato un flusso di lavoro, è necessario **Flusso di lavoro \> Invia** nel riquadro azioni per inviare il giornale di registrazione per l'approvazione.

### <a name="credit-limit-adjustments-workflows"></a>Flussi di lavoro Correzioni del limite di credito

I flussi di lavoro **Correzioni del limite di credito** possono essere utilizzati per inviare correzioni del limite di credito mediante un processo di approvazione del flusso di lavoro. È possibile creare due flussi di lavoro nella pagina **Flusso di lavoro gestione crediti** (**Gestione crediti \> Impostazione \> Flusso di lavoro gestione crediti**):

- **Correzioni del limite di credito** - Questo flusso di lavoro può essere utilizzato per approvare le voci a livello di intestazione.
- **Riga correzioni del limite di credito** - Questo flusso di lavoro può essere utilizzato per approvare le voci di correzione di modo che le voci possano essere approvate da persone diverse, in base ai criteri nel flusso di lavoro.

> [!NOTE]
> Quando si crea il flusso di lavoro **Correzioni del limite di credito**, è possibile configurarlo di modo che le correzioni siano registrate automaticamente dopo l'approvazione delle righe. Includere l'attività **Registra giornale automaticamente** nel flusso di lavoro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]