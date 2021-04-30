---
title: Calendari e pianificazione generale
description: In questo argomento viene fornita una panoramica dei calendari della supply chain e della relativa influenza sulla pianificazione generale.
author: t-benebo
ms.date: 08/19/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 7a53efb753a75916c85dc4a45a3c64872a7f5d32
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "5908373"
---
# <a name="calendars-and-master-planning"></a>Calendari e pianificazione generale

[!include [banner](../includes/banner.md)]

In questo argomento viene fornita una panoramica dei calendari della supply chain e della relativa influenza sulla pianificazione generale.  Vengono descritti i differenti calendari utilizzati nel motore di pianificazione generale, incluso il modo in cui influiscono le date di spedizione e ricevimento negli ordini pianificati. Vengono inoltre forniti suggerimenti relativi all'assegnazione, all'utilizzo e all'aggiornamento dei calendari.

## <a name="definition-of-a-calendar"></a>Definizione di un calendario

È possibile definire un calendario da utilizzare nell'organizzazione nella pagina **Amministrazione organizzazione > Impostazioni > Calendari > Calendari**. 

Ogni voce di data in un calendario può essere **aperta** o **chiusa** o **calendario di base**. L'impostazione è specificata nella colonna **Controllo** della pagina **Orari di lavoro**. Per ogni data: 
- **Aperta** - Indica che il lavoro viene eseguito il giorno selezionato. Il calendario sarà aggiornato in base al modello di orario di lavoro.
- **Chiusa** - Indica il lavoro che non viene eseguito durante il giorno. 
- **Calendario di base** - Indica che la data specifica erediterà gli orari di lavoro e lo stato aperta/chiusa dal calendario di base. Di conseguenza, quando il calendario di base viene aggiornato, il calendario selezionato ne gli orari operativi. 

Per tutte le date chiuse, la casella di controllo **Chiuso per prelievo** verrà assegnata automaticamente. Per le date aperte, è possibile selezionare manualmente l'opzione **Chiuso per prelievo**. Ciò significa che il lavoro viene eseguito in quella data, ma non la spedizione. 

## <a name="calendars-that-affect-master-planning"></a>Calendari che influiscono sulla pianificazione generale

### <a name="calendar-for-a-coverage-group"></a>Calendario per un gruppo di copertura
Un gruppo di copertura indica un set di parametri comuni utilizzati per il rifornimento degli articoli appartenenti a un determinato gruppo di copertura. 

Per aggiungere un calendario per un gruppo di copertura, accedere a **Pianificazione generale > Impostazione > Copertura > Gruppi di copertura**. Individuare il gruppo di copertura a cui si desidera assegnare il calendario e quindi selezionarlo nel campo **Calendario**.

Il gruppo di copertura può essere assegnato in varie pagine: 
    - Nella pagina **Dettagli prodotto rilasciato** di un articolo. Per visualizzare il gruppo di copertura per un articolo, passare a **Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati** e selezionare l'articolo per accedere alla pagina **Dettagli prodotti rilasciati**. È possibile visualizzare il gruppo di copertura articoli nella scheda Dettaglio **Piano**.
    - Nella pagina **Copertura articoli**. Nella pagina Dettagli prodotti rilasciati, fare clic su **Copertura articoli** per passare alla pagina della copertura articoli. Nella scheda Panoramica è possibile visualizzare differenti parametri per il rifornimento a seconda del sito, del magazzino e delle dimensioni prodotto. Il gruppo di copertura per ogni articolo verrà ereditato dal gruppo di copertura nella pagina **Dettagli prodotto rilasciato**. Questo comportamento può essere annullato utilizzando **Usa impostazioni specifiche** o **Ignora impostazioni gruppo di copertura** nella scheda **Generale**.
    - Nella pagina **Parametri di pianificazione generale**. Se un articolo non dispone di un gruppo di copertura impostato nelle pagine precedenti, la pianificazione generale utilizzerà il gruppo di copertura generale impostato sui parametri di pianificazione generale. Questa opzione è impostata in **Pianificazione generale > Impostazione > Parametri di pianificazione generale** nel campo **Gruppo di copertura generale**. 

### <a name="calendar-for-a-vendor"></a>Calendario per un fornitore
Per indicare i giorni lavorativi di un fornitore, è possibile assegnare un calendario acquisti al fornitore nella pagina **Impostazioni predefinite ordine fornitore** per un fornitore. 

Per impostare un calendario per un fornitore, è necessario creare il calendario in **In Amministrazione organizzazione > Calendari > Calendari**. Quando il calendario viene creato, è necessario assegnarlo al fornitore. Passare a **Contabilità fornitori > Fornitori > Tutti i fornitori** e selezionare il fornitore a cui si desidera assegnare il calendario. Quindi, nella pagina del fornitore nella scheda Dettaglio **Impostazioni predefinite ordine fornitore** assegnare il nuovo calendario acquisti utilizzando il menu a discesa. 

Il calendario per un fornitore indica i giorni in cui il fornitore accetta l'ordine fornitore e le date in cui consegna gli ordini alla società. Di conseguenza, le date degli ordini fornitore per il fornitore con un calendario acquisti saranno date definite come aperte nel calendario. Le date di consegna per tali ordini saranno inoltre in giorni di apertura e quindi influenzeranno il lead time dell'articolo acquistato. 

#### <a name="define-the-lead-time-for-a-purchased-item"></a>Definire il lead time per un articolo acquistato.

Per specificare il lead time di acquisto (e se solo i giorni lavorativi devono essere considerati) per un articolo, è necessario passare alla pagina delle impostazioni di ordine predefinite in **Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati** e selezionare **Impostazioni ordine predefinite**. 

> [!Note]
> I **giorni lavorativi** nel lead time di acquisto indica i giorni lavorativi del fornitore. Ad esempio, un calendario per la consegna soltanto il martedì con un lead time di 10 giorni e la casella di controllo dei giorni lavorativi selezionata indica che sono necessarie 10 settimane (10 martedì) per la consegna dell'articolo.
Quindi, nella maggior parte non si consiglia di selezionare i giorni lavorativi per i lead time dell'ordine fornitore.

#### <a name="define-lead-times-from-the-trade-agreements-page"></a>Definire i lead time nella pagina degli accordi commerciali

La pianificazione generale può essere impostata per includere tutti gli accordi commerciali per i fornitori. Gli accordi commerciali sono prezzi fissi o accordi su sconti impostati per uno o più clienti o fornitori per la vendita o l'acquisto di singoli o più prodotti. Passare a **Pianificazione generale > Impostazione > Parametri di pianificazione generale** e nella scheda **Ordini pianificati** e **Trova accordi commerciali** per includere gli accordi commerciali durante la pianificazione. La pianificazione generale può selezionare il fornitore con il **lead time minimo** o il **prezzo unitario minimo**.

### <a name="calendar-for-a-warehouse"></a>Calendario per un magazzino
È possibile assegnare un calendario a un magazzino per indicare le date aperte per il ricevimento e la spedizione. Se nessun calendario è stato assegnato a un magazzino, si presuppone che sia aperto tutti i giorni. 

> [!Note]
> L'assegnazione di un calendario a un magazzino di transito non ha alcun impatto. I magazzini di transito sono utilizzati per il supporto degli ordini di trasferimento. Le date applicabili di spedizione o ricevimento per gli ordini sono definite dai giorni aperti nel magazzino "Da" e nel magazzino "A", e la modalità di consegna del calendario.

#### <a name="closed-for-pickup-policy"></a>Criteri Chiuso per prelievo
Per indicare che un magazzino è aperto per il ricevimento ma che il prelievo non è consentito, è possibile utilizzare **Criteri Chiuso per prelievo** nel calendario del magazzino. Ciò vale anche per i prelievi dei clienti. 

### <a name="transport-calendar"></a>Calendario di spedizione 
Per indicare le date disponibili per la spedizione degli ordini di trasferimento da un **magazzino origine**, è possibile assegnare un **calendario di spedizione**. È possibile impostare un calendario di spedizione per modalità di consegna o per modalità di consegna e magazzino di origine. Il calendario di spedizione è impostato in **Vendite e marketing > Impostazioni > Distribuzione > Modi di consegna**. Selezionare una modalità di consegna e fare clic sul pulsante **Calendario di spedizione**.

Una riga può essere creata per ogni magazzino e modalità di consegna dove il calendario viene aggiunto nella colonna **Calendario di spedizione**. La riga specificherà il calendario di spedizione che verrà applicato quando le merci vengono spedite dal magazzino utilizzando la modalità di consegna specificata. Per applicare un calendario di spedizione a tutte le spedizioni utilizzando una determinata modalità di consegna, una riga può essere creata senza specificare il magazzino.  Avrà un impatto su tutte le spedizioni che utilizzano la modalità di consegna specificata, indipendentemente dal magazzino. 

Se non viene assegnato alcun calendario di spedizione, si presuppone che tutti i giorni siano aperti per la spedizione.

### <a name="calendar-for-a-customer"></a>Calendario per un cliente
Per indicare le date in cui un cliente può accettare le consegne, è possibile assegnare un calendario di ricevimento al cliente. Se nessun calendario viene assegnato a un cliente, si presuppone che il cliente può ricevere ordini tutti i giorni. Ciò modificherà la data di ricevimento nelle righe di'ordine cliente. Se si seleziona una data nelle righe di ordine cliente che non è "aperta" nel calendario cliente, il sistema indicherà che la data di ricevimento non è valida. 

Tenere presente che è possibile includere un solo calendario per cliente. Se è necessario includere un calendario per ogni indirizzo diverso per un cliente, è possibile creare un cliente per indirizzo e quindi assegnare il rispettivo calendario. 

La data di ricevimento richiesta nelle righe di ordine cliente è determinata dal calendario cliente e dal metodo di controllo della data di consegna. Per ulteriori informazioni su come calcolare la data di consegna meno recente, vedere [Promesse ordine.](/dynamics365/unified-operations/supply-chain/sales-marketing/delivery-dates-available-promise-calculations)

### <a name="shipping-calendar-for-a-legal-entity"></a>Calendario di spedizione per una persona giuridica
Per indicare le date in cui una persona giuridica può spedire merci, è possibile impostare un calendario di spedizione in **Amministrazione organizzazione > Organizzazioni > Persone giuridiche**. Selezionare la persona giuridica e aggiungere il calendario nella scheda **Commercio estero e logistica** nel campo **Calendario di spedizione**. Il calendario di spedizione verrà utilizzato come origine dei valori predefiniti per tutti i calendari di magazzino nella persona giuridica. 

## <a name="how-calendars-affect-dates-in-planning"></a>Come i calendari influiscono sulle date nella pianificazione

### <a name="order-date-of-a-planned-purchase-order"></a>Data ordine di un ordine fornitore pianificato 
La data ordine in un ordine fornitore pianificato indica la data in cui l'ordine viene effettuato. Sarà aperta una data nel calendario del fornitore che nel calendario del gruppo di copertura. A volte, i fornitori hanno bisogno di un margine di sicurezza tra il momento in cui ricevono l'ordine fornitore e quello in cui sono pronti a spedire le merci. Queste date vengono indicate nei margini di sicurezza del fornitore. Tuttavia, se l'articolo acquistato viene assegnato a un gruppo di copertura con margini di sicurezza, tali margini sostituiranno quelli del fornitore.

### <a name="delivery-date-of-a-planned-purchase-order"></a>Data di consegna di un ordine fornitore pianificato
La data di ricevimento di un acquisto indica la data in cui si riceveranno le merci. Sarà una data aperta nel calendario. Il calendario che verrà preso in considerazione per indicare in quali giorni è possibile ricevere degli ordini fornitore possono essere ricevuti è uno dei calendari elencati di seguito, a partire da quello con la priorità più alta: 
1. Calendario del fornitore
1. Calendario del gruppo di copertura
1. Calendario di magazzino per il magazzino ricevente

Si noti che il calendario del gruppo di copertura può essere impostato in pagine differenti e arà la priorità nel seguente ordine:
1. Gruppo di copertura articoli nella pagina **Copertura articoli**
1. Gruppo di copertura articoli nella pagina **Dettagli prodotti rilasciati**
1. Gruppo di copertura articoli predefinito in **Parametri di pianificazione generale**

### <a name="shipping-date-of-a-planned-transfer-order"></a>Data di spedizione di un ordine di trasferimento pianificato
Quando si crea un ordine di trasferimento tra due magazzini, la data di spedizione e la data di ricevimento sono incluse nell'intestazione dell'ordine di trasferimento, insieme al magazzino "Da" e il magazzino "A". La differenza tra queste due date è il tempo di trasporto previsto (in giorni) tra i magazzini.

La data di spedizione di un ordine di trasferimento pianificato indica la data in cui le merci sono spedite dal magazzino "Da". I calendari utilizzati per specificare la data di spedizione disponibile sono elencati per priorità: 
1. Calendario di magazzino del magazzino "Da"
1. Calendario del gruppo di copertura (vedere l'ordine fallback per questo calendario sopra) Se è presente un calendario di magazzino impostato, la data di spedizione sarà una data aperta nel calendario. Se non è disponibile un calendario di magazzino impostato, verrà utilizzato il calendario del gruppo di copertura. 

### <a name="receipt-date-of-a-planned-transfer-order"></a>Data di ricevimento di un ordine di trasferimento pianificato
La data di ricevimento di un ordine di trasferimento indica la data in cui le merci vengono ricevute nel magazzino "A".

I calendari utilizzati per specificare la data di ricevimento sono quelli elencati per priorità: 
1. Calendario del gruppo di copertura 
1. Calendario di magazzino del magazzino "A" Se è presente un calendario di copertura impostato, la data di ricezione sarà una data aperta nel calendario. Se non è disponibile un calendario del gruppo di copertura impostato, verrà utilizzato il calendario di magazzino. 

Quando si trovano le date di spedizione e ricevimento per il trasferimento pianificato, anche i margini stabiliti dall'utente per la spedizione e il ricevimento verranno presi in considerazione. 

## <a name="using-calendars-in-master-planning"></a>Utilizzo di calendari nella pianificazione generale

### <a name="assignment-of-scm-calendars"></a>Assegnazione di calendari SCM
È importante impostare i calendari per identificare i giorni lavorativi della società. La migliore implementazione è di impostare un calendario per ogni elemento con giorni lavorativi differenti. In altre parole, tutti i calendari esterni (cliente, fornitore) e tutti quelli interni (magazzino, gruppo di copertura e modalità di consegna) relativi alla società.

### <a name="recommendation-on-warehouse-calendars"></a>Suggerimento sui calendari di magazzino
Si consiglia di utilizzare un calendario per magazzino per includere solo le modifiche specifiche che influiscono sul magazzino. Ad esempio, due o più magazzini potrebbero avere gli stessi giorni lavorativi ma criteri di prelievo differenti. In tal caso, un calendario per ognuno dei magazzini con i rispettivi criteri di prelievo è la migliore implementazione per il sistema per includere le migliori date per ordini fornitore, di trasferimento e di produzione pianificati. Se nessun calendario di magazzino è impostato, il calendario per la persona giuridica può essere utilizzato come origine dei valori predefiniti per il calendario di magazzino. 

### <a name="recommendation-of-coverage-group-calendars"></a>Suggerimento sui calendari del gruppo di copertura
Per quanto riguarda il calendario del gruppo di copertura, è importante considerare che è presente un comportamento di sostituzione in relazione alle date di ricevimento nella pianificazione generale. Di conseguenza, si consiglia di utilizzarlo con attenzione. In particolare, è utile nel caso in cui il rifornimento deve essere eseguito in specifici giorni della settimana. 

### <a name="updating-scm-related-calendars"></a>Aggiornamento dei calendari correlati a SCM
Sebbene sia importante che tutti i calendari rilevanti siano assegnati nella rispettiva posizione (fornitore, cliente, magazzino, modalità di consegna o gruppo di copertura), aggiornarli è altrettanto importante affinché riflettano le modifiche. Il sistema definirà le date degli ordini di produzione, trasferimento, fornitore e cliente in base alla combinazione dei calendari assegnati. È consigliabile chiarire chi è responsabile dell'assegnazione e dell'aggiornamento dei calendari nelle relative aree corrispondenti. Nel caso di scomposizione o di qualsiasi altra modifica inusuale nei giorni lavorativi, è essenziale aggiornare i calendari in base a tale modifica. Tutte le attività che dipendono dai calendari, ad esempio la pianificazione generale e la programmazione della produzione, devono essere ripetute dopo l'aggiornamento dei calendari. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]