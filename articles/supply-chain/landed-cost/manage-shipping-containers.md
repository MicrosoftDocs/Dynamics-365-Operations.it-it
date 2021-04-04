---
title: Gestire contenitori di spedizione
description: In questo argomento viene descritto come utilizzare i contenitori di spedizione. I contenitori di spedizione sono utilizzati per raggruppare le merci che sono raggruppate fisicamente. Sono utilizzati anche nei casi in cui i costi devono essere condivisi solo tra quelle merci, in genere perché sono raggruppate fisicamente.
author: sherry-zheng
manager: tfehr
ms.date: 12/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ITMContainersListPage, ITMContainers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-14
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: e75deb5f4acd647408e93957bb99f04f548108f6
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501344"
---
# <a name="manage-shipping-containers"></a>Gestire contenitori di spedizione

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I contenitori di spedizione sono utilizzati per raggruppare le merci che sono raggruppate fisicamente. Sono utilizzati anche nei casi in cui i costi devono essere condivisi solo tra quelle merci, in genere perché sono raggruppate fisicamente.

Per visualizzare ed elaborare le merci tramite la pagina Contenitore di spedizione, selezionare **Costo sbarcato \> Contenitori di spedizione \> Tutti i contenitori di spedizione**. La pagina **Tutti i contenitori di spedizione** mostra un elenco di tutti i contenitori di spedizione disponibili. È possibile utilizzare i pulsanti nel riquadro Azioni per creare, eliminare e utilizzare contenitori di spedizione. Selezionare un contenitore di spedizione qualsiasi nell'elenco per visualizzarne i dettagli nella pagina **Contenitori di spedizione**.

La parte superiore della pagina dei dettagli del contenitore di spedizione mostra informazioni sul contenitore di spedizione e sui costi. La sezione **Righe** mostra le registrazioni, gli articoli e gli ordini fornitore o gli ordini di trasferimento associati al contenitore.

## <a name="action-pane"></a>Riquadro azioni

Il riquadro Azioni nelle pagine **Tutti i contenitori di spedizione** e **Contenitori di spedizione** include pulsanti che consentono di utilizzare un contenitore di spedizione selezionato. Ogni pulsante esegue una singola azione. Il riquadro Azioni include anche schede, ognuna delle quali, a sua volta, fornisce una serie di pulsanti correlati. Tranne dove diversamente indicato, tutti i pulsanti e le schede descritti nelle sottosezioni seguenti sono disponibili sia nella visualizzazione elenco (ovvero, nella pagina **Tutti i contenitori di spedizione**) che nella visualizzazione dettagliata (ovvero, nella pagina **Contenitori di spedizione**).

### <a name="buttons-on-the-manage-tab"></a>Pulsanti della scheda Gestisci

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Gestisci** del riquadro Azioni.

| Pulsante | Descrizioni |
|---|---|
| Registra elenco entrate | Consente di registrare un elenco entrate o di visualizzare gli elenchi entrate prodotti per tutte le righe di ordine fornitore nel contenitore di spedizione. Se si utilizzano spedizioni con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione degli elenchi entrate. |
| Registra entrata prodotti | Consente di registrare un entrata prodotti per tutte le righe di ordine fornitore nel contenitore di spedizione. |
| Registra fattura | Consente di registrare una fattura per tutte le righe di ordine fornitore nel contenitore di spedizione. Se si utilizzano spedizioni con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione delle fatture. |
| Ordine di trasferimento spedizione | Consente di registrare una spedizione dell'ordine di trasferimento per tutte le righe di ordine di trasferimento nel contenitore di spedizione. Nella finestra di dialogo vengono visualizzate solo le righe nel contenitore di spedizione che rappresentano un tipo di ordine di trasferimento. |
| Ricevi ordine di trasferimento | Consente di registrare un ricevimento dell'ordine di trasferimento per tutte le righe di ordine di trasferimento nel contenitore di spedizione. La finestra di dialogo di ricevimento è il modo più semplice per ricevere le merci in un contenitore di spedizione o in un viaggio ed è una delle tre opzioni disponibili. È anche possibile ricevere tramite giornali di registrazione arrivi o l'elaborazione via dispositivo mobile. |
| Crea giornale di registrazione arrivi | È possibile generare un giornale di registrazione arrivi per le organizzazioni utilizzando funzionalità di magazzino avanzate. Le opzioni sono _Inizializza quantità_ (consigliata) e _Crea da merci in transito_ o _Crea da ordini fornitore_. Le ultime due opzioni dipendono dall'utilizzo o meno dell'elaborazione merci in transito. |
| Rinomina | Apre una finestra di dialogo in cui è possibile rinominare un contenitore di spedizione selezionato. |
| Cambia modello di percorso | Modificare il modello di percorso. Dopo aver modificato il modello di percorso, è possibile che sia necessario selezionare **Trova costi automatici** oppure aggiungere di nuovo i costi manualmente, poiché i costi di spedizione verranno eliminati. |
| Converti in noleggio | Consente di convertire un contenitore di spedizione selezionato in un contenitore di spedizione a noleggio. |

### <a name="buttons-on-the-general-tab"></a>Pulsanti della scheda Generale

Nella seguente tabella sono descritti i pulsanti disponibili nella scheda **Generale** del riquadro Azioni.

| Pulsante | Descrizioni |
|---|---|
| Elenco entrate | Consente di registrare un elenco entrate per tutte le righe di ordine fornitore nel contenitore di spedizione. In caso di viaggi con più società, per ogni società viene aperta una nuova finestra di dialogo per la registrazione degli elenchi entrate. |
| Entrata prodotti | Visualizza il record dell'entrata prodotti, se utilizzato. Il processo di entrata prodotti verrà utilizzato solo se le merci non utilizzano la funzionalità Merci in transito. |
| Arrivo articoli | Visualizza il giornale di registrazione arrivi articoli per il contenitore di spedizione, se tale giornale di registrazione viene utilizzato. |
| Scali | Gli scali sono utilizzati per identificare parti distinte di un viaggio. I lead time possono essere associati a ciascuno scalo per facilitare la tracciabilità della spedizione. Per ulteriori informazioni, vedere [Configurare percorsi con più scali](multi-leg-journey-setup.md). |
| Tracciabilità | Visualizza o aggiorna la tracciabilità della spedizione. |
| Ordini merci in transito | È possibile aprire la pagina **Merci in transito** direttamente dal contenitore. Tale pagina mostra i record delle merci in transito solo per il contenitore di spedizione selezionato. |

## <a name="header-view"></a>Visualizzazione intestazione

Per aprire la visualizzazione **Intestazione**, aprire un contenitore di spedizione, quindi selezionare la scheda **Intestazione** in alto a destra nell'intestazione del contenitore di spedizione.

### <a name="settings-on-the-general-fasttab"></a>Impostazioni nella Scheda dettaglio Generale

La tabella seguente descrive le impostazioni disponibili nella Scheda dettaglio **Generale** della visualizzazione **Intestazione** di un contenitore di spedizione.

| Campo | Descrizione |
|---|---|
| Contenitore di spedizione | Il nome del contenitore di spedizione. |
| Viaggio | Il viaggio associato al contenitore di spedizione. |
| Tipo di contenitore di spedizione | Immettere il tipo di contenitore di spedizione. Questo campo deve essere impostato. È possibile utilizzarlo per determinare il costo del trasporto, ad esempio selezionando il costo automatico associato al tipo di contenitore di spedizione. |
| Imbarcazione | Immettere o selezionare l'imbarcazione. Se l'imbarcazione non è elencata come valore, è possibile inserire l'ID imbarcazione come testo libero. In tal caso, la tabella principale non viene aggiornata di modo che l'ID imbarcazione possa essere selezionato in questo campo in un secondo momento. Per ulteriori informazioni, vedere [Imbarcazioni](shipping-information-setup.md#vessels). |
| Tipo di unità | I tipi di unità sono utilizzati come mezzo aggiuntivo per raggruppare e identificare i contenitori di spedizione. Vengono visualizzati e selezionati nella pagina del contenitore di spedizione. Per ulteriori informazioni, vedere [Impostare tipi di unità](shipping-container-setup.md#unit-types). |
| Tipo di refrigerazione | I tipi di refrigerazione sono utilizzati come mezzo aggiuntivo per raggruppare e identificare i contenitori di spedizione, in genere contenitori refrigerati. Vengono visualizzati e selezionati nella pagina del contenitore di spedizione. Per ulteriori informazioni, vedere [Impostare tipi di refrigerazione](shipping-container-setup.md#refrigeration-types). |
| Misura | Questo campo consente di specificare una misura nel modulo **Costo sbarcato**. Le misure sono spesso utilizzate dalle organizzazioni che non conoscono il volume o il peso individuale delle merci, ma che richiedono una ripartizione più accurata di quella mediante le opzioni Importo e Quantità. Lo spedizioniere fornirà il peso in chilogrammi o la misura cubica, a livello di articolo o di ordine fornitore. Può essere aggiornato automaticamente se il parametro è selezionato, oppure può essere immesso manualmente. |
| Unità di misura | L'unità di misura che si applica al valore nel campo **Misura**. |
| Peso effettivo | È possibile registrare il peso effettivo del cartone o del contenitore. Questo valore può essere utilizzato per la verifica rispetto al peso massimo consentito nella configurazione di un contenitore di spedizione. |
| Numero di cartoni | Il numero di cartoni viene aggiornato automaticamente se il parametro è selezionato. |
| Descrizione delle merci | È possibile selezionare una descrizione delle merci nell'intestazione del contenitore di spedizione o della registrazione. Viene utilizzato per identificare un viaggio, un contenitore di spedizione o una registrazione di merci. Per ulteriori informazioni, vedere [Descrizione delle merci](shipping-information-setup.md#description-of-goods). |
| Lettera di vettura aerea/polizza di carico | È possibile specificare la lettera di vettura aerea o la polizza di carico per il contenitore di spedizione. |
| Note | Ulteriori informazioni correlate al contenitore di spedizione. |
| A rendere | Un valore che indica se il contenitore di spedizione può essere restituito dopo il viaggio. |
| Stato viaggio | Lo stato del percorso associato al contenitore di spedizione. |
| Stato ordine fornitore | Lo stato dell'ordine fornitore associato al contenitore di spedizione. |

### <a name="settings-on-the-delivery-fasttab"></a>Impostazioni nella Scheda dettaglio Consegna

La tabella seguente descrive le impostazioni disponibili nella Scheda dettaglio **Consegna** della visualizzazione **Intestazione** di un contenitore di spedizione.

| Campo | Descrizione |
|---|---|
| Data e ora creazione | La data e l'ora di creazione del contenitore. |
| Data franco fabbrica | Questa data viene solitamente fornita alla fabbrica/al fornitore per indicare la data prevista alla quale le merci devono essere spedite. Quando si collabora con una fabbrica in Asia, questa data è spesso richiesta al posto della data prevista di ricevimento delle merci (al contrario, per una consegna locale, è richiesta la data prevista di ricevimento delle merci). Questo campo può essere compilato dalle righe di ordine fornitore nell'elenco di contenitori di spedizione. Il valore può anche essere immesso manualmente qui. |
| Data di spedizione | Questa data può essere stampata sul documento dell'ordine fornitore. Di solito informa la fabbrica/il fornitore sulla data entro la quale le merci devono essere consegnate al porto. Questo campo è fornito solo a scopo informativo. Non è utilizzato per stimare la data di consegna prevista delle merci nel contenitore di spedizione. Questo campo può essere impostato in modo che venga aggiornato automaticamente quando viene aggiornata la pagina di controllo della tracciabilità. |
| Data ingresso punto vendita | La prima data in cui le merci degli ordini fornitore collegati al viaggio saranno disponibili per la vendita.|
| Data di consegna stimata | Di solito, la data in cui le merci devono arrivare al magazzino. Questo campo è fornito solo a scopo informativo. Non viene utilizzata per calcolare la pianificazione generale nelle righe di ordine fornitore nel contenitore di spedizione. La data di consegna prevista nelle righe di ordine fornitore viene aggiornata tramite il controllo della tracciabilità. Questo campo può essere impostato in modo che venga aggiornato quando viene aggiornata la pagina di controllo della tracciabilità. |
| Data di partenza | In genere, la data in cui l'aereo o l'imbarcazione lascia effettivamente il porto all'estero. |
| Data/ora di arrivo stimata al porto di spedizione | La data di arrivo prevista al porto di destinazione. |
| Documenti originali ricevuti | Facoltativo: aggiorna la data in cui sono stati ricevuti i documenti originali. |
| Broker consigliato | Facoltativo: aggiorna la data in cui il broker è stato consigliato. |
| Polizza di carico originale inviata | Facoltativo: aggiorna la data in cui è stata inviata la polizza di carico originale. |
| Merci rilasciate | Facoltativo: aggiorna la data in cui le merci sono state rilasciate. |
| Appuntamento cliente | Facoltativo: aggiorna la data dell'appuntamento con il cliente. |
| Consegnato al magazzino | Facoltativo: aggiorna la data in cui le merci sono state consegnate al magazzino. |
| Data di verifica | Facoltativo: aggiorna la data di verifica. |
| Istruzioni di consegna | Facoltativo: aggiorna la data delle istruzioni di consegna. |
| Porto di origine | Il porto da cui verranno spediti gli articoli. |
| Porto di destinazione | Il porto a cui verranno spediti gli articoli. |
| Spedizioniere locale | Questo campo è fornito solo a scopo informativo. Lo spedizioniere locale deve essere selezionabile nella tabella dei fornitori. |
| Data trasporto locale | Immettere la data per la quale è prenotato il trasporto locale. Questo campo può aiutare il magazzino a eseguire la pianificazione. |
| Ora trasporto locale | Immettere la fascia oraria. Questo campo può aiutare il magazzino a eseguire la pianificazione. |
| Modello di percorso | Il modello di percorso specificato per il viaggio. Il modello di percorso fornisce i dettagli dei porti di origine e di destinazione e i lead time associati al controllo della tracciabilità del contenitore di spedizione. |

### <a name="settings-on-the-other-fasttab"></a>Impostazioni nella Scheda dettaglio Altro

La tabella seguente descrive le impostazioni disponibili nella Scheda dettaglio **Altro** della visualizzazione **Intestazione** di un contenitore di spedizione.

| Campo | Descrizione |
|---|---|
| Noleggio | Un valore che indica se il contenitore di spedizione è un contenitore di spedizione a noleggio. I costi di noleggio potrebbero essere associati ai contenitori a noleggio. |
| Convertito in noleggio | Un valore che indica se il contenitore di spedizione è stato convertito in un contenitore di spedizione a noleggio. I costi di noleggio potrebbero essere associati ai contenitori a noleggio. |
| Viaggio originale | Indica se il contenitore di spedizione è stato spostato in un nuovo viaggio, ovvero il viaggio originale. |
| Utilizzato | Consente di indicare se è stato utilizzato un contenitore di spedizione a noleggio. Viene fornita solo a scopo informativo. |
| Data di carico prevista | La data prevista del caricamento delle merci nel contenitore di spedizione. |
| Numero di serie | Immettere il numero di serie che la propria azienda utilizza internamente per il contenitore di spedizione. |
| Numero di serie della società di spedizione | Immettere il numero di serie fornito dalla società di spedizione o dall'agente per il contenitore di spedizione. |
| Data di applicazione certificato di esame | La data in cui è stato richiesto un esame per il contenitore di spedizione. |
| Data di ricevimento certificato di esame | La data in cui è stato ricevuto un certificato di esame. |
| Data di scadenza certificato di esame | La data di scadenza del certificato di esame. |
| Numero certificato di esame | Il numero del certificato emesso dopo l'esecuzione di un esame. |

## <a name="lines-view"></a>Visualizzazione Righe

Per aprire la visualizzazione **Righe**, aprire un contenitore di spedizione, quindi selezionare la scheda **Righe** in alto a destra nell'intestazione del contenitore di spedizione.

### <a name="information-on-the-shipping-container-fasttab"></a>Informazioni sulla Scheda dettaglio Contenitore di spedizione

La Scheda dettaglio **Contenitore di spedizione** nella visualizzazione **Righe** mostra le informazioni sulla registrazione. La maggior parte di queste informazioni appare anche nella visualizzazione **Intestazione**, come descritto in precedenza in questo argomento.

### <a name="information-and-buttons-on-the-lines-fasttab"></a>Informazioni e pulsanti nella Scheda dettaglio Righe

La Scheda dettaglio **Righe** nella visualizzazione **Righe** mostra i dettagli su ciascuna riga di ordine fornitore completa o parziale inclusa nel contenitore di spedizione corrente.

Nella seguente tabella vengono descritti i pulsanti disponibili nella Scheda dettaglio **Righe** della visualizzazione **Righe**.

| Pulsante | Descrizione |
|---|---|
| Rimuovi | Consente di rimuovere la riga di ordine fornitore selezionata dal viaggio. |
| Magazzino \> Transazioni | Consente di visualizzare le transazioni di magazzino per la riga di ordine fornitore selezionata. Da notare che se si utilizzano merci in transito, vengono visualizzati anche l'ordine originale e gli ordini merci in transito. |
| Magazzino \> Visualizza dimensioni | Apre una finestra di dialogo in cui è possibile selezionare le dimensioni inventariali disponibili per le transazioni visualizzate. |
| Aggiornamento | Aggiorna le informazioni relative a importo, peso o volume della riga di ordine fornitore selezionata. |

### <a name="information-on-the-lines-details-fasttab"></a>Informazioni sulla Scheda dettaglio Dettagli righe

La Scheda dettaglio **Dettagli righe** nella visualizzazione **Righe** mostra informazioni sulla riga di ordine fornitore correntemente selezionata nella Scheda dettaglio **Righe**.
