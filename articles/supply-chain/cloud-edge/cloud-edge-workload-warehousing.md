---
title: Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale
description: Questo argomento fornisce informazioni sulla funzionalità che consente alle unità di scala di eseguire processi selezionati dal carico di lavoro di gestione del magazzino dell'utente.
author: perlynne
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers, SysWorkloadDuplicateRecord
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 081b6968575a8a057903d96de2833a98552ed123
ms.sourcegitcommit: a46f0bf9f58f559bbb2fa3d713ad86875770ed59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2021
ms.locfileid: "7813725"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Non tutte le funzionalità aziendali di gestione del magazzino sono completamente supportate per i magazzini che eseguono un carico di lavoro su un'unità di scala. Verificare di utilizzare solo i processi che in questo argomento vengono descritti come supportati in modo esplicito.

## <a name="warehouse-execution-on-scale-units"></a>Esecuzione nel magazzino su unità di scala

I carichi di lavoro di gestione del magazzino consentono alle unità di scala nel cloud e nella rete perimetrale di eseguire processi selezionati dalle funzionalità di gestione del magazzino.

## <a name="prerequisites"></a>Prerequisiti

È necessario disporre di un hub Dynamics 365 Supply Chain Management e di un'unità di scala distribuita con il carico di lavoro di gestione del magazzino. Per ulteriori informazioni sull'architettura e sul processo di distribuzione, vedere [Unità di scala in una topologia ibrida distribuita](cloud-edge-landing-page.md).

## <a name="how-the-warehouse-execution-workload-works-on-scale-units"></a>Come funziona il carico di lavoro di esecuzione del magazzino su unità di scala

Per i processi nel carico di lavoro di gestione del magazzino, i dati vengono sincronizzati tra l'hub e le unità di scala.

Un'unità di scala può gestire solo i dati che possiede. Il concetto di proprietà dei dati per le unità di scala consente di prevenire conflitti multimaster. Pertanto, è importante comprendere quali dati di processo sono di proprietà dell'hub e quali delle unità di scala.

A seconda dei processi aziendali, lo stesso record di dati può cambiare proprietà tra l'hub e le unità di scala. Un esempio di questo scenario è fornito nella sezione seguente.

> [!IMPORTANT]
> Alcuni dati possono essere creati sia sull'hub che sull'unità di scala. Esempi includono **Targhe** e **Numeri di batch**. La gestione dei conflitti dedicata viene fornita nel caso di uno scenario in cui lo stesso record univoco viene creato sia sull'hub che su un'unità di scala durante lo stesso ciclo di sincronizzazione. Quando ciò accade, la sincronizzazione successiva fallirà e sarà necessario accedere ad **Amministrazione del sistema > Richieste > Richieste del carico di lavoro > Record duplicati**, dove è possibile visualizzare e unire i dati.

## <a name="outbound-process-flow"></a>Flusso di elaborazione in uscita

Il processo di proprietà dei dati in uscita dipende dall'utilizzo o meno del processo di pianificazione del carico. In tutti i casi, l'hub possiede i *documenti di origine*, come ordini cliente e ordini di trasferimento, nonché il processo di allocazione degli ordini e i relativi dati di transazione dell'ordine. Tuttavia, quando si utilizza il processo di pianificazione del carico, i carichi verranno creati sull'hub e quindi inizialmente saranno di proprietà dell'hub. Come parte del processo *Rilascio in magazzino*, la proprietà dei dati di carico viene trasferita alla distribuzione dell'unità di scala dedicata, che diventerà il proprietario della successiva *Elaborazione ciclo di spedizione* (come assegnazione del lavoro, lavoro di rifornimento e creazione di lavoro su richiesta). Pertanto, gli addetti al magazzino possono elaborare le vendite in uscita e gli ordini di trasferimento solo utilizzando un'app per dispositivi mobili Warehouse Management connessa alla distribuzione che esegue il carico di lavoro dell'unità di scala specifica.

Non appena il processo di lavoro finale colloca le scorte in un luogo di spedizione finale (Portellone), l'unità di scala segnala all'hub di aggiornare le transazioni di inventario del documento di origine in *Prelevato*. Fino a quando questo processo non viene eseguito e non viene nuovamente sincronizzato, l'inventario disponibile sul carico di lavoro dell'unità di scala sarà prenotato fisicamente a livello di magazzino ed è possibile elaborare immediatamente la conferma della spedizione in uscita senza attendere il completamento della sincronizzazione. Il successivo documento di trasporto della vendita e la fatturazione o la spedizione dell'ordine di trasferimento per il carico verranno gestiti nell'hub.

Il diagramma seguente mostra il flusso in uscita e indica dove si svolgono i singoli processi aziendali. (Selezionare il diagramma per ingrandirlo.)

[![Flusso di elaborazione in uscita.](media/wes_outbound_warehouse_processes-small.png "Flusso di elaborazione in uscita")](media/wes_outbound_warehouse_processes.png)

### <a name="outbound-processing-with-load-planning"></a>Elaborazione in uscita con pianificazione del carico

Quando si utilizza il processo di pianificazione del carico, i carichi e le spedizioni vengono creati nell'hub e la proprietà dei dati viene trasferita alle unità di scala come parte del processo *Rilascio in magazzino*, come illustrato nella figura seguente.

![Elaborazione in uscita con pianificazione del carico.](./media/wes_outbound_processing_with_load_planning.png "Elaborazione in uscita con pianificazione del carico")

### <a name="outbound-processing-without-load-planning"></a>Elaborazione in uscita senza pianificazione del carico

Quando non si utilizza il processo di pianificazione del carico, le spedizioni vengono create sulle unità di scala. Anche i carichi vengono creati sulle unità di scala come parte del processo di ciclo.

![Elaborazione in uscita senza pianificazione del carico.](./media/wes_outbound_processing_without_load_planning.png "Elaborazione in uscita senza pianificazione del carico")

## <a name="inbound-process-flow"></a>Flusso di elaborazione in entrata

L'hub possiede i seguenti dati:

- Tutti i documenti di origine, come ordini fornitore e ordini di produzione
- Elaborazione carico in entrata
- Tutti gli aggiornamenti di costi e finanziari

> [!NOTE]
> Il flusso degli ordini fornitore in entrata è concettualmente diverso dal flusso in uscita. È possibile gestire lo stesso magazzino sull'unità di scala o sull'hub a seconda che l'ordine fornitore sia stato rilasciato o meno al magazzino. Dopo aver rilasciato un ordine al magazzino, è possibile lavorare con quell'ordine solo se si è effettuato l'accesso all'unità di scala.
>
> Se si utilizza il processo di *rilascio a magazzino*, gli [*ordini di magazzino*](cloud-edge-warehouse-order.md) vengono creati e la proprietà del flusso di ricevimento correlato viene assegnata all'unità di scala. L'hub non sarà in grado di registrare il ricevimento in entrata.

Per utilizzare il processo *Rilascia in magazzino* è necessario accedere all'hub. Per l'elaborazione dell'ordine fornitore, passare a una delle pagine seguenti per eseguirlo o pianificarlo:

- **Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore > Magazzino > Azioni > Rilascio in magazzino**
- **Gestione del magazzino > Rilascio in magazzino > Rilascio automatico degli ordini cliente**

Quando si utilizza **Rilascio automatico degli ordini cliente**, è possibile selezionare righe di ordine fornitore specifiche in base a una query. Uno scenario tipico sarebbe impostare un processo batch ricorrente che rilascia tutte le righe di ordine fornitore confermate che dovrebbero arrivare il giorno successivo.

L'addetto al magazzino può eseguire il processo di ricevimento utilizzando un'app per dispositivi mobili Gestione magazzino connessa all'unità di scala. I dati vengono quindi registrati dall'unità di scala e indicati rispetto all'ordine di magazzino in entrata. Anche la creazione e l'elaborazione dello stoccaggio successivo saranno gestite dall'unità di scala.

Se non utilizzi il processo *rilascio in magazzino* e pertanto non utilizzi *ordini di magazzino*, l'hub può elaborare il ricevimento in magazzino e l'elaborazione del lavoro indipendentemente dalle unità di scala.

![Flusso di elaborazione in entrata.](./media/wes-inbound-ga.png "Flusso di elaborazione in entrata")

Quando un lavoratore esegue la registrazione in entrata utilizzando un processo di ricezione dell'app per dispositivi mobili Warehouse Management rispetto all'unità di scala, viene registrato un ricevimento rispetto all'ordine di magazzino correlato, che viene archiviato nell'unità di scala. Il carico di lavoro dell'unità di scala segnalerà quindi all'hub di aggiornare le relative transazioni della riga dell'ordine fornitore in *Registrato*. Al termine, sarà possibile eseguire un'entrata prodotti dell'ordine fornitore sull'hub.

Il diagramma seguente mostra il flusso in entrata e indica dove si svolgono i singoli processi aziendali. (Selezionare il diagramma per ingrandirlo.)

[![Flusso di elaborazione in entrata](media/wes_inbound_warehouse_processes-small.png "Flusso di elaborazione in entrata")](media/wes_inbound_warehouse_processes.png)

## <a name="supported-processes-and-roles"></a>Processi e ruoli supportati

Non tutti i processi di gestione del magazzino sono supportati in un carico di lavoro di esecuzione del magazzino su un'unità di scala. Pertanto, si consiglia di assegnare ruoli che corrispondono alla funzionalità disponibile per ogni utente.

Per facilitare questo processo, un ruolo di esempio denominato *Responsabile magazzino per il carico di lavoro* è incluso nei dati di esempio in **Amministrazione sistema \> Sicurezza \> Configurazione sicurezza**. Lo scopo di questo ruolo è consentire ai responsabili del magazzino di accedere al carico di lavoro di esecuzione del magazzino sull'unità di scala. Il ruolo concede l'accesso alle pagine rilevanti nel contesto di un carico di lavoro ospitato su un'unità di scala.

I ruoli utente su un'unità di scala vengono assegnati come parte della sincronizzazione iniziale dei dati dall'hub all'unità di scala.

Per modificare i ruoli assegnati a un utente, andare ad **Amministrazione sistema \> Sicurezza \> Assegna utenti a ruoli**. Agli utenti che agiscono come responsabili di magazzino solo su unità di scala deve essere assegnato solo il ruolo *Responsabile magazzino per il carico di lavoro*. Questo approccio garantirà che tali utenti abbiano accesso solo alle funzionalità supportate. Rimuovere tutti gli altri ruoli assegnati a tali utenti.

Agli utenti che agiscono come responsabili di magazzino nell'hub e nelle unità di scala deve essere assegnato il ruolo *Addetto magazzino*. Tenere presente che questo ruolo concede agli addetti al magazzino l'accesso a funzionalità (come l'elaborazione degli ordini di trasferimento) presenti nell'interfaccia utente, ma non attualmente supportate sulle unità di scala.

### <a name="supported-warehouse-execution-processes"></a>Processi di esecuzione del magazzino supportati

I seguenti processi di esecuzione del magazzino possono essere abilitati per un carico di lavoro di esecuzione del magazzino su un'unità di scala:

- Metodi di ciclo selezionati per ordini cliente e di trasferimento (convalida, creazione del carico, allocazione, rifornimento della domanda, containerizzazione, creazione di lavoro e stampa di etichette del ciclo)

- Elaborazione del lavoro di magazzino a fronte di ordini di vendite e trasferimento utilizzando l'app di magazzino (incluso il lavoro di rifornimento)
- Esecuzione di query sulle scorte disponibili utilizzando l'app di magazzino
- Creazione ed esecuzione di movimenti di inventario utilizzando l'app di magazzino
- Creazione ed elaborazione del lavoro di conteggio ciclo utilizzando l'app di magazzino
- Creazione di rettifiche magazzino utilizzando l'app di magazzino
- Registrazione di ordini fornitore ed esecuzione del lavoro di stoccaggio utilizzando l'app di magazzino

I seguenti tipi di lavoro possono essere creati su un'unità di scala e possono quindi essere elaborati come parte di un carico di lavoro di gestione del magazzino:

- **Movimenti inventario** - Movimento manuale e movimento per modello di lavoro.
- **Conteggio ciclo** - Incluso un processo di approvazione/rifiuto della discrepanza nell'ambito delle operazioni di conteggio.
- **Ordini fornitore** - Lavoro di stoccaggio tramite un ordine di magazzino quando gli ordini fornitore non sono associati ai carichi.
- **Ordini cliente** - Semplice lavoro di prelievo e di carico.
- **Uscita di trasferimento** - Prelievo e carico semplici.
- **Rifornimento** - Non include le materie prime per la produzione.
- **Stoccaggio prodotti finiti** - Dopo il processo di produzione dichiarato come finito.
- **Stoccaggio co-prodotti e sottoprodotti** - Dopo il processo di produzione dichiarato come finito.

Nessun altro tipo di lavoro di magazzino o di elaborazione dei documenti di origine è al momento supportato sulle unità di scala. Ad esempio, per un carico di lavoro di esecuzione del magazzino su un'unità di scala, non è possibile eseguire un processo di ricevimento di ordini di trasferimento (ricevuta di trasferimento). Al contrario, l'elaborazione deve avvenire nell'istanza dell'hub.

> [!NOTE]
> I pulsanti e le voci di menu del dispositivo mobile per le funzionalità non supportate non vengono visualizzati nell'_app per dispositivi mobili Gestione magazzino_ quando è connesso a una distribuzione di unità di scala.
> 
> Quando si esegue un carico di lavoro su un'unità di scala, non è possibile eseguire processi non supportati per il magazzino specifico nell'hub. Le tabelle fornite più avanti in questo argomento documentano le funzionalità supportate.
>
> I tipi di lavoro di magazzino selezionati possono essere creati sia sull'hub che sulle unità di scala, ma possono essere gestiti solo dall'hub proprietario o dall'unità di scala (la distribuzione che ha creato i dati).
>
> Anche quando un processo specifico è supportato da un'unità di scala, tenere presente che tutti i dati necessari potrebbero non essere sincronizzati dall'hub all'unità di scala o dall'unità di scala all'hub, il che rischia di provocare un'elaborazione imprevista del sistema. Esempi di questo scenario includono:
> 
> - Se si utilizza una query della direttiva di ubicazione che unisce un record della tabella dati che esiste solo nella distribuzione dell'hub.
> - Se utilizzi lo stato della posizione e/o le funzionalità di carico volumetrico della posizione. Questi dati non verranno sincronizzati tra le distribuzioni e quindi funzioneranno solo quando si aggiorna l'inventario delle posizioni disponibile su una delle distribuzioni.

La seguente funzionalità di gestione del magazzino non è attualmente supportata per i carichi di lavoro per le unità di scala:

- Elaborazione in ingresso di righe ordine fornitore assegnate a un carico.
- Elaborazione in entrata di ordini fornitore per un progetto.
- Gestione dei costi sbarcati, utilizzo dei percorsi e monitoraggio delle merci in transito.
- Elaborazione in entrata e in uscita per gli articoli che hanno dimensioni di tracciabilità attive **Proprietario** e/o **Numero di serie**.
- Elaborazione dell'inventario con un valore di stato di blocco.
- Modifica di uno stato di inventario durante qualsiasi processo di movimento del lavoro.
- Prenotazione delle dimensioni a livello di magazzino flessibili impegnate nell'ordine.
- Utilizzo della funzionalità *Stato ubicazione magazzino* (i dati non vengono sincronizzati tra le distribuzioni).
- Utilizzo della funzionalità *Posizionamento targa ubicazione*.
- Utilizzo di *Filtri di prodotto* e *Gruppi di filtri di prodotto*, tra cui l'impostazione **Numero di giorni per combinare i batch**.
- Integrazione con la gestione della qualità.
- Elaborazione con articoli a peso variabile.
- Elaborazione con articoli abilitati solo per Gestione trasporto.
- Elaborazione con scorte disponibili negative.
- Elaborazione del lavoro di magazzino con note di spedizione.
- Elaborazione del lavoro di magazzino con movimentazione dei materiali/Warehouse Automation.
- Immagini rappresentazione generale prodotto (ad esempio, sull'app per dispositivi mobili Warehouse Management).
- Condivisione dati interaziendali per prodotti.

> [!WARNING]
> Alcune funzionalità di magazzino non saranno disponibili per i magazzini che eseguono i carichi di lavoro di gestione del magazzino su un'unità di scala e inoltre non sono supportate sull'hub o sul carico di lavoro dell'unità di scala.
> 
> Altre funzionalità possono essere elaborate su entrambi, ma richiederanno un uso attento in alcuni scenari, ad esempio quando le scorte disponibili vengono aggiornato per lo stesso magazzino sia sull'hub che sull'unità di scala a causa del processo di aggiornamento asincrono dei dati.
> 
> Funzionalità specifiche (come *bloccare il lavoro*), che sono supportate sia sull'hub che sulle unità di scala, saranno supportate solo per il proprietario dei dati.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>In uscita (opzione supportata solo per ordini cliente e di trasferimento)

La tabella seguente mostra quali funzionalità in uscita sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

| Elaborazione                                                      | Hub | Carico di lavoro di esecuzione del magazzino su un'unità di scala |
|--------------------------------------------------------------|-----|------------------------------|
| Elaborazione documenti di origine                                   | Sì | No |
| Elaborazione del carico e della gestione trasporto                | Sì, ma solo i processi di pianificazione del carico. L'elaborazione della gestione dei trasporti non è supportata  | No |
| Rilascia in magazzino                                         | Sì | No |
| Cross-docking pianificato                                        | No  | No |
| Consolidamento spedizioni                                       | Sì, quando si utilizza la pianificazione del carico | Sì |
| Elaborazione ciclo di spedizione                                     | No  |Sì, tranne **Allestimento del carico e ordinamento** |
| Mantenere le spedizioni per ciclo                                  | No  | Sì|
| Elaborazione del lavoro di magazzino (inclusa la stampa della targa)        | No  | Sì, ma solo per le funzionalità supportate menzionate in precedenza |
| Prelievo cluster                                              | No  | Sì|
| Elaborazione manuale dell'imballaggio, inclusa l'elaborazione del lavoro "Prelievo contenitore imballato" | No <P>Alcune elaborazioni possono essere eseguite dopo un processo di prelievo iniziale gestito da un'unità di scala, ma non consigliato a causa delle seguenti operazioni bloccate.</p>  | No |
| Rimuovi contenitore da gruppo                                  | No  | No |
| Elaborazione ordinamento in uscita                                  | No  | No |
| Stampa di documenti relativi al carico                           | Sì | Sì|
| Polizza di carico e generazione di ASN                            | No  | Sì|
| Conferma della spedizione                                             | No  | Sì|
| Conferma della spedizione con "Conferma e trasferisci"            | No  | No |
| Elaborazione di fatturazione e documento di trasporto                        | Sì | No |
| Prelievo breve (ordini cliente e di trasferimento)                    | No  | Sì, senza rimuovere le prenotazioni per i documenti di origine|
| Prelievo eccessivo (ordini cliente e di trasferimento)                     | No  | Sì|
| Modifica delle sedi di lavoro (ordini cliente e di trasferimento)         | No  | Sì|
| Lavoro completo (ordini cliente e di trasferimento)                    | No  | Sì|
| Stampa report di lavoro                                            | Sì | Sì|
| Etichetta ondata                                                   | No  | Sì|
| Divisione lavoro                                                   | No  | Sì|
| Elaborazione del lavoro: gestito da "Caricamento di trasporto"            | No  | No |
| Riduci quantità prelevata                                       | No  | No |
| Storna lavoro                                                 | No  | No |
| Inverti conferma spedizione                                | No  | Sì|

### <a name="inbound"></a>In entrata

La tabella seguente mostra quali funzionalità in entrata sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

| Elaborazione                                                          | Hub | Carico di lavoro di esecuzione del magazzino su un'unità di scala<BR>*(Gli articoli contrassegnati con "Sì" si applicano solo agli ordini di magazzino)* |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Elaborazione&nbsp;documenti&nbsp;di origine                             | Sì | No |
| Elaborazione del carico e della gestione trasporto                    | Sì | No |
| Costo sbarcato e ricezione delle merci in transito                       | Sì | No |
| Conferma della spedizione in entrata                                    | Sì | No |
| Rilascio ordine fornitore al magazzino (elaborazione ordine di magazzino) | Sì | No |
| Annullamento di righe ordine di magazzino<p>Notare che questo è supportato solo quando non è avvenuta alcuna registrazione sulla riga</p> | Sì | No |
| Ricevimento e stoccaggio articolo ordine acquisto                       | <p>Sì,&nbsp;quando&nbsp;non&nbsp;è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, quando un ordine fornitore non fa parte di un <i>carico</i></p> |
| Ricevimento e stoccaggio riga ordine acquisto                       | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, quando un ordine fornitore non fa parte di un <i>carico</i></p></p> |
| Ricevimento e stoccaggio ordine di reso                              | Sì | No |
| Ricevimento e stoccaggio targa mista                       | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Sì |
| Ricezione articoli di carico                                              | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento e stoccaggio targa                             | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento e stoccaggio articolo ordine di trasferimento                       | Sì | No |
| Ricevimento e stoccaggio riga ordine di trasferimento                       | Sì | No |
| Annulla lavoro (in entrata)                                            | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, ma solo quando l'opzione <b>Annulla registrazione entrata quando si annulla il lavoro</b> (nella pagina <b>Parametri di gestione magazzino</b>) viene deselezionata</p> |
| Elaborazione ricevimento prodotto ordine fornitore                        | Sì | No |
| Ricevimento degli ordini fornitore con limite minimo di fornitura                      | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Sì, ma solo effettuando una richiesta di cancellazione dall'hub |
| Ricevimento degli ordini fornitore con limite massimo di fornitura                       | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Sì  |
| Ricevimento con creazione di lavoro *Cross docking*                 | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento con creazione di lavoro *Ordine di controllo qualità*                  | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento con creazione di lavoro *Campionamento di articoli di qualità*          | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento con creazione di lavoro *Qualità nel controllo qualità*       | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Ricevimento con creazione ordine di controllo qualità                            | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | No |
| Elaborazione del lavoro: gestito da *Stoccaggio cluster*                 | Sì | No |
| Elaborazione del lavoro con *Prelievo in difetto*                               | Sì | No |
| Caricamento targa                                           | Sì | Sì |

### <a name="warehouse-operations-and-exception-handing"></a>Operazioni di magazzino e gestione delle eccezioni

La tabella seguente mostra le operazioni di magazzino e le funzionalità di gestione delle eccezioni supportate e il punto in cui sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala nel cloud e nella rete perimetrale.

| Elaborazione                                            | Hub | Carico di lavoro di esecuzione del magazzino su un'unità di scala |
|----------------------------------------------------|-----|------------------------------|
| Richiesta di informazioni sulla targa                              | Sì | Sì                          |
| Richiesta informazioni sull'articolo                                       | Sì | Sì                          |
| Richiesta di informazioni sull'ubicazione                                   | Sì | Sì                          |
| Modifica magazzino                                   | Sì | Sì                          |
| Movimento                                           | Sì | Sì                          |
| Movimento per modello                               | Sì | Sì                          |
| Trasferimento di magazzino                                 | Sì | No                           |
| Creare un ordine di trasferimento dall'app di magazzino           | Sì | No                           |
| Rettifica (in ingresso/uscita)                                | Sì | Sì, ma non per lo scenario di rettifica in cui la prenotazione dell'inventario deve essere rimossa utilizzando l'impostazione **Rimuovi prenotazioni** sui tipi di rettifica inventario</p>                           |
| Modifica stato magazzino                            | Sì | No                           |
| Conteggio ciclo ed elaborazione di discrepanza conteggio | Sì | Sì                           |
| Ristampa etichetta (stampa della targa)             | Sì | Sì                          |
| Compilazioni targa                                | Sì | No                           |
| Suddivisioni targa                                | Sì | No                           |
| Imballa in targhe nidificate                                | Sì | No                           |
| Check-in conducente                                    | Sì | No                           |
| Check-out conducente                                   | Sì | No                           |
| Codice di modifica smaltimento batch                      | Sì | Sì                          |
| Visualizza elenco lavori aperti                             | Sì | Sì                          |
| Consolida targhe                         | Sì | No                           |
| Elaborazione del rifornimento soglia min/max e di zona| Sì <p>Il consiglio è di non includere le stesse ubicazioni come parte delle query</p>| Sì                          |
| Elaborazione di rifornimento per assegnazione                  | Sì  | Sì<p>Notare che la configurazione deve essere eseguita sull'unità di scala</p>                           |
| Blocco e sblocco del lavoro                             | Sì | Sì                          |
| Cambia utente                                        | Sì | Sì                          |
| Modifica pool di lavoro nel lavoro                           | Sì | Sì                          |
| Annulla lavoro                                        | Sì | Sì                          |

### <a name="production"></a>Produzione

La tabella seguente riepiloga gli scenari di gestione del magazzino attualmente supportati sui carichi di lavoro dell'unità di scala.

| Elaborazione | Hub | Carico di lavoro di esecuzione del magazzino su un'unità di scala |
|---------|-----|------------------------------|
| Stoccaggio prodotti finiti e dichiarati finiti | Sì | Sì |
| Stoccaggio co-prodotti e sottoprodotti | Sì | Sì |
| Avvia ordine di produzione | Sì | Sì |
| <p>Tutti gli altri processi di gestione del magazzino correlati alla produzione, inclusi:</p><li>Rilascia in magazzino</li><li>Elaborazione di ciclo della produzione</li><li>Prelievo materie prime</li><li>Stoccaggio kanban</li><li>Prelievo kanban</li><li>Scarti di produzione</li><li>Ultimo pallet produzione</li><li>Registra consumo materiali</li><li>Svuota kanban</li></ul> | Sì | No |
| Rifornimento di materie prime | No | No |

## <a name="maintaining-scale-units-for-warehouse-execution"></a>Gestione delle unità di scala per l'esecuzione del magazzino

Diversi processi batch vengono eseguiti sia sull'hub che sulle unità di scala.

Nella distribuzione hub, è possibile gestire manualmente i processi batch. È possibile gestire i processi batch seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro di back-office**:

- Processore messaggi unità di scala a hub
- Registra entrate ordine di origine
- Completamento ordini di magazzino

Nel carico di lavoro nelle unità di scala, è possibile gestire i processi batch seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro**:

- Elaborare record di tabelle ciclo
- Hub di magazzino per processore messaggi unità di scala
- Elabora richieste aggiornamento quantità per righe ordine di magazzino

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
