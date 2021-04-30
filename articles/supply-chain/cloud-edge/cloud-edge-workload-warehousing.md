---
title: Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale
description: Questo argomento fornisce informazioni sulla funzionalità che consente alle unità di scala di eseguire processi selezionati dal carico di lavoro di gestione del magazzino dell'utente.
author: perlynne
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: d6dffb1ea03b8d11519087163d2837d6cfe3df4e
ms.sourcegitcommit: 639175a39da38edd13e21eeb5a1a5ca62fa44d99
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/15/2021
ms.locfileid: "5899169"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Non tutte le funzionalità aziendali di gestione del magazzino sono completamente supportate per i magazzini che eseguono un carico di lavoro su un'unità di scala. Verificare di utilizzare solo i processi che in questo argomento vengono descritti come supportati in modo esplicito.

## <a name="warehouse-execution-on-scale-units"></a>Esecuzione nel magazzino su unità di scala

Questa funzione consente alle unità di scala di eseguire processi selezionati dalle funzionalità di gestione del magazzino.

In questo argomento, le esecuzioni di gestione del magazzino in un magazzino definito come unità di scala sono conosciute come *Sistema di esecuzione nel magazzino* (*WES*, Warehouse Execution System).

## <a name="prerequisites"></a>Prerequisiti

È necessario disporre di un hub Dynamics 365 Supply Chain Management e di un'unità di scala distribuita con il carico di lavoro di gestione del magazzino. Per ulteriori informazioni sull'architettura e sul processo di distribuzione, vedere [Utilizzare unità di scala per aumentare la resilienza per i carichi di lavoro di Supply Chain Management](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Come funziona il carico di lavoro WES su unità di scala

Per i processi nel carico di lavoro di gestione del magazzino, i dati vengono sincronizzati tra l'hub e le unità di scala.

Un'unità di scala può gestire solo i dati che possiede. Il concetto di proprietà dei dati per le unità di scala consente di prevenire conflitti multimaster. Pertanto, è importante comprendere quali processi sono di proprietà dell'hub e quali delle unità di scala.

Le unità di scala possiedono i seguenti dati:

- **Dati di elaborazione ciclo** - I metodi di elaborazione ciclo selezionati vengono gestiti nell'ambito dell'elaborazione del ciclo dell'unità di scala.
- **Dati di elaborazione lavoro** - Sono supportati i seguenti tipi di elaborazione degli ordini di lavoro:

  - **Movimenti scorte** (movimento manuale e movimento per modello di lavoro)
  - **Ordini fornitore** (lavoro di stoccaggio tramite un ordine di magazzino quando gli ordini fornitore non sono associati ai carichi)
  - **Ordini cliente** (semplice lavoro di prelievo e di carico)
  - **Ordini di trasferimento** (solo in uscita con semplici operazioni di prelievo e carico)

- **Dati di ricevimento ordini di magazzino** - Questi dati vengono utilizzati solo per gli ordini fornitore rilasciati manualmente a un magazzino.
- **Dati di targa** - Le targhe possono essere create sull'hub e sull'unità di scala. È stata fornita una gestione dei conflitti dedicata. S noti che questi dati non sono specifici del magazzino.

## <a name="outbound-process-flow"></a>Flusso di elaborazione in uscita

L'hub possiede i seguenti dati:

- Tutti i documenti di origine, come ordini cliente e ordini di trasferimento
- Allocazione degli ordini ed elaborazione del carico in uscita
- Processi di rilascio in magazzino, creazione della spedizione, creazione e finalizzazione e del ciclo

Le unità di scala prevedono l'effettiva elaborazione del ciclo (come l'allocazione del lavoro, il lavoro di rifornimento e la creazione del lavoro in base alla domanda) dopo il rilascio del ciclo. Pertanto, gli addetti al magazzino possono elaborare il lavoro in uscita utilizzando un'app per dispositivi mobili Gestione magazzino connessa all'unità di scala.

![Flusso di elaborazione ciclo](./media/wes-wave-processing-ga.png "Flusso di elaborazione ciclo")

## <a name="inbound-process-flow"></a>Flusso di elaborazione in entrata

L'hub possiede i seguenti dati:

- Tutti i documenti di origine, come ordini fornitore e ordini di reso vendite
- Elaborazione carico in entrata
- Tutti gli aggiornamenti di costi e finanziari

> [!NOTE]
> Il flusso degli ordini fornitore in entrata è concettualmente diverso dal flusso in uscita. È possibile gestire lo stesso magazzino sull'unità di scala o sull'hub a seconda che l'ordine fornitore sia stato rilasciato o meno al magazzino. Dopo aver rilasciato un ordine al magazzino, puoi lavorare con quell'ordine solo se hai effettuato l'accesso all'unità di scala.

Se si utilizza il processo di *rilascio a magazzino*, gli [*ordini di magazzino*](cloud-edge-warehouse-order.md) vengono creati e la proprietà del flusso di ricevimento correlato viene assegnata all'unità di scala. L'hub non sarà in grado di registrare il ricevimento in entrata.

Per utilizzare il processo *Rilascia in magazzino* è necessario accedere all'hub. Passare a una delle pagine seguenti per eseguirlo o pianificarlo:

- **Approvvigionamento > Ordini fornitore > Tutti gli ordini fornitore > Magazzino > Azioni > Rilascio in magazzino**
- **Gestione del magazzino > Rilascio in magazzino > Rilascio automatico degli ordini cliente**

Quando si utilizza **Rilascio automatico degli ordini cliente**, è possibile selezionare righe di ordine fornitore specifiche in base a una query. Uno scenario tipico sarebbe impostare un processo batch ricorrente che rilascia tutte le righe di ordine fornitore confermate che dovrebbero arrivare il giorno successivo.

L'addetto al magazzino può eseguire il processo di ricevimento utilizzando un'app per dispositivi mobili Gestione magazzino connessa all'unità di scala. I dati vengono quindi registrati dall'unità di scala e indicati rispetto all'ordine di magazzino in entrata. Anche la creazione e l'elaborazione dello stoccaggio successivo saranno gestite dall'unità di scala.

Se non utilizzi il processo *rilascio in magazzino* e pertanto non utilizzi *ordini di magazzino*, l'hub può elaborare il ricevimento in magazzino e l'elaborazione del lavoro indipendentemente dalle unità di scala.

![Flusso di elaborazione in entrata](./media/wes-inbound-ga.png "Flusso di elaborazione in entrata")

## <a name="supported-processes-and-roles"></a>Processi e ruoli supportati

Non tutti i processi di gestione del magazzino sono supportati in un carico di lavoro WES su un'unità di scala. Pertanto, si consiglia di assegnare ruoli che corrispondono alla funzionalità disponibile per ogni utente.

Per facilitare questo processo, un ruolo di esempio denominato *Responsabile magazzino per il carico di lavoro* è incluso nei dati di esempio in **Amministrazione sistema \> Sicurezza \> Configurazione sicurezza**. Lo scopo di questo ruolo è consentire ai responsabili del magazzino di accedere al WES sull'unità di scala. Il ruolo concede l'accesso alle pagine rilevanti nel contesto di un carico di lavoro ospitato su un'unità di scala.

I ruoli utente su un'unità di scala vengono assegnati come parte della sincronizzazione iniziale dei dati dall'hub all'unità di scala.

Per modificare i ruoli assegnati a un utente, andare ad **Amministrazione sistema \> Sicurezza \> Assegna utenti a ruoli**. Agli utenti che agiscono come responsabili di magazzino solo su unità di scala deve essere assegnato solo il ruolo *Responsabile magazzino per il carico di lavoro*. Questo approccio garantirà che tali utenti abbiano accesso solo alle funzionalità supportate. Rimuovere tutti gli altri ruoli assegnati a tali utenti.

Agli utenti che agiscono come responsabili di magazzino nell'hub e nelle unità di scala deve essere assegnato il ruolo *Addetto magazzino*. Tenere presente che questo ruolo concede agli addetti al magazzino l'accesso a funzionalità (come l'elaborazione degli ordini di trasferimento) presenti nell'interfaccia utente, ma non attualmente supportate sulle unità di scala.

## <a name="supported-wes-processes"></a>Processi WES supportati

I seguenti processi di esecuzione del magazzino possono essere abilitati per un carico di lavoro WES su un'unità di scala:

- Metodi di ciclo selezionati per ordini cliente e trasferimento (allocazione, rifornimento della domanda, containerizzazione, creazione di lavoro e stampa di etichette del ciclo)
- Elaborazione del lavoro di magazzino a fronte di ordini di vendite e trasferimento utilizzando l'app per dispositivi mobili Gestione magazzino (incluso il lavoro di rifornimento)
- Esecuzione di query sulle scorte disponibili utilizzando l'app per dispositivi mobili Gestione magazzino
- Creazione ed esecuzione di movimenti di inventario utilizzando l'app per dispositivi mobili Gestione magazzino
- Registrazione di ordini fornitore ed esecuzione del lavoro di stoccaggio utilizzando l'app per dispositivi mobili Gestione magazzino

I seguenti tipi di ordine di lavoro sono attualmente supportati per i carichi di lavoro WES su distribuzioni di unità di scala:

- Gestione ordini cliente
- Uscita di trasferimento
- Rifornimento
- Movimento scorte
- Ordini fornitore (collegati a ordini di magazzino)

Nessun altro tipo di lavoro di magazzino o di elaborazione dei documenti di origine è al momento supportato sulle unità di scala. Ad esempio, per un carico di lavoro WES su un'unità di scala, non è possibile eseguire un processo di ricevimento di ordini di trasferimento (ricevuta di trasferimento) o lavoro di conteggio del ciclo di elaborazione.

> [!NOTE]
> I pulsanti e le voci di menu del dispositivo mobile per le funzionalità non supportate non vengono visualizzati nell'_app per dispositivi mobili Gestione magazzino_ quando è connesso a una distribuzione di unità di scala.

> [!WARNING]
> Quando si esegue un carico di lavoro su un'unità di scala, non è possibile eseguire processi non supportati per il magazzino specifico nell'hub. Le tabelle fornite più avanti in questo argomento documentano le funzionalità supportate.
>
> I tipi di lavoro di magazzino selezionati possono essere creati sia sull'hub che sulle unità di scala, ma possono essere gestiti solo dall'hub proprietario o dall'unità di scala (la distribuzione che ha creato i dati).
>
> Anche quando un processo specifico è supportato da un'unità di scala, tenere presente che tutti i dati necessari potrebbero non essere sincronizzati dall'hub all'unità di scala o dall'unità di scala all'hub, il che rischia di provocare un'elaborazione imprevista del sistema. Esempi sono:
> 
> - Se si utilizza una query della direttiva di ubicazione che unisce un record della tabella dati che esiste solo nella distribuzione dell'hub.
> - Se utilizzi lo stato della posizione e/o le funzionalità di carico volumetrico della posizione. Questi dati non verranno sincronizzati tra le distribuzioni e quindi funzioneranno solo quando si aggiorna l'inventario delle posizioni disponibile su una delle distribuzioni.

La seguente funzionalità di gestione del magazzino non è attualmente supportata per i carichi di lavoro per le unità di scala:

- Elaborazione in ingresso di righe ordine fornitore assegnate a un carico
- Elaborazione in entrata di ordini fornitore per un progetto
- Elaborazione in entrata e in uscita per gli articoli che hanno dimensioni di tracciabilità attive **Proprietario** e/o **Numero di serie**
- Elaborazione dell'inventario con un valore di stato di blocco
- Modifica di uno stato di inventario durante qualsiasi processo di movimento del lavoro
- Prenotazione delle dimensioni a livello di magazzino flessibili impegnate nell'ordine
- Utilizzo della funzionalità *Stato ubicazione magazzino* (i dati non vengono sincronizzati tra le distribuzioni)
- Utilizzo della funzionalità *Posizionamento targa ubicazione*
- Utilizzo di *Filtri di prodotto* e *Gruppi di filtri di prodotto*, tra cui l'impostazione **Numero di giorni per combinare i batch**
- Integrazione con la gestione della qualità
- Elaborazione con articoli a peso variabile
- Elaborazione con articoli abilitati solo per Gestione trasporto
- Elaborazione con scorte disponibili negative
- Elaborazione del lavoro di magazzino con tipi di lavoro personalizzati
- Elaborazione del lavoro di magazzino con note di spedizione
- Elaborazione del lavoro di magazzino con attivazione della soglia di conteggio ciclo
- Elaborazione del lavoro di magazzino con movimentazione dei materiali/Warehouse Automation
- Utilizzo dell'immagine dei dati master del prodotto (ad esempio, sull'app per dispositivi mobili Gestione magazzino)

> [!WARNING]
> Alcune funzionalità di magazzino non saranno disponibili per i magazzini che eseguono i carichi di lavoro di gestione del magazzino su un'unità di scala e inoltre non sono supportate sull'hub o sul carico di lavoro dell'unità di scala.
> 
> Altre funzionalità possono essere elaborate su entrambi, ma richiederanno un uso attento in alcuni scenari, ad esempio quando le scorte disponibili vengono aggiornato per lo stesso magazzino sia sull'hub che sull'unità di scala a causa del processo di aggiornamento asincrono dei dati.
> 
> Funzionalità specifiche (come *bloccare il lavoro*) che sono supportati sia sull'hub che sulle unità di scala saranno supportati solo per il proprietario dei dati.

### <a name="outbound-supported-only-for-sales-and-transfer-orders"></a>In uscita (opzione supportata solo per ordini cliente e di trasferimento)

La tabella seguente mostra quali funzionalità in uscita sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

| Elaborazione                                                      | Hub | Carico di lavoro WES su un'unità di scala |
|--------------------------------------------------------------|-----|------------------------------|
| Elaborazione documenti di origine                                   | Sì | Nessuno |
| Elaborazione del carico e della gestione trasporto                | Sì | Nessuno |
| Rilascia in magazzino                                         | Sì | Nessuno |
| Cross-docking pianificato                                        | Nessuno  | Nessuno |
| Consolidamento spedizioni                                       | Sì | Nessuno |
| Elaborazione ciclo di spedizione                                     | Sì, ma solo l'inizializzazione e la finalizzazione dello stato del ciclo vengono gestite nell'hub. Ciò significa che solo l'elaborazione degli ordini cliente e di trasferimento in uscita possono essere gestite dall'unità di scala.|<p>No, l'inizializzazione e la finalizzazione vengono gestite dall'hub e la funzionalità **Allestimento del carico e ordinamento** non è supportata<p><b>Nota:</b> l'accesso all'hub è necessario per finalizzare lo stato del ciclo come parte dell'elaborazione del ciclo.</p> |
| Mantenere le spedizioni per ciclo                                  | Sì | Nessuno |
| Elaborazione del lavoro di magazzino (inclusa la stampa della targa)        | Nessuno  | <p>Sì, ma solo per le funzionalità supportate sopra menzionate. |
| Prelievo cluster                                              | Nessuno  | Sì|
| Elaborazione manuale dell'imballaggio, inclusa l'elaborazione del lavoro "Prelievo contenitore imballato"                                           | Nessuno <P>Alcune elaborazioni possono essere eseguite dopo un processo di prelievo iniziale gestito da un'unità di scala, ma non consigliato a causa delle seguenti operazioni bloccate.</p>  | Nessuno  |
| Rimuovi contenitore da gruppo                        | Nessuno  | Nessuno                           |
| Elaborazione ordinamento in uscita                                  | Nessuno  | Nessuno |
| Stampa di documenti relativi al carico                           | Sì | Nessuno |
| Polizza di carico e generazione di ASN                            | Sì | Nessuno |
| Conferma della spedizione                    | Sì  | Nessuno |
| Conferma della spedizione con "Conferma e trasferisci"                    | Nessuno  | Nessuno |
| Elaborazione di fatturazione e documento di trasporto                | Sì | Nessuno |
| Prelievo breve (ordini cliente e di trasferimento)                    | Nessuno  | Nessuno |
| Prelievo eccessivo (ordini cliente e di trasferimento)                     | Nessuno  | Nessuno |
| Modifica delle sedi di lavoro (ordini cliente e di trasferimento)         | Nessuno  | Sì|
| Lavoro completo (ordini cliente e di trasferimento)                    | Nessuno  | Sì|
| Stampa report di lavoro                                            | Sì | Nessuno |
| Etichetta ondata                                                   | Nessuno  | Sì|
| Divisione lavoro                                                   | Nessuno  | Sì|
| Elaborazione del lavoro: gestito da "Caricamento di trasporto"            | Nessuno  | Nessuno |
| Riduci quantità prelevata                                       | Nessuno  | Nessuno |
| Storna lavoro                                                 | Nessuno  | Nessuno |
| Inverti conferma spedizione                                | Sì | Nessuno |

### <a name="inbound"></a>In entrata

La tabella seguente mostra quali funzionalità in entrata sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

| Elaborazione                                                          | Hub | Carico di lavoro WES su un'unità di scala<BR>*(Gli articoli contrassegnati con "Sì" si applicano solo agli ordini di magazzino)*</p> |
|------------------------------------------------------------------|-----|----------------------------------------------------------------------------------|
| Elaborazione&nbsp;documenti&nbsp;di origine                                       | Sì | Nessuno |
| Elaborazione del carico e della gestione trasporto                    | Sì | Nessuno |
| Conferma della spedizione in entrata                                            | Sì | Nessuno |
| Rilascio ordine fornitore al magazzino (elaborazione ordine di magazzino) | Sì | Nessuno |
| Annullamento di righe ordine di magazzino<p>Notare che questo è supportato solo quando non è avvenuta alcuna registrazione sulla riga</p>          | Sì | Nessuno |
| Ricevimento e stoccaggio articolo ordine acquisto                       | <p>Sì,&nbsp;quando&nbsp;non&nbsp;è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, quando un ordine fornitore non fa parte di un <i>carico</i></p> |
| Ricevimento e stoccaggio riga ordine acquisto                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, quando un ordine fornitore non fa parte di un <i>carico</i></p></p> |
| Ricevimento e stoccaggio ordine di reso                               | Sì | Nessuno |
| Ricevimento e stoccaggio targa mista                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricezione articoli di carico                                             | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento e stoccaggio targa                              | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento e stoccaggio articolo ordine di trasferimento                        | Sì | Nessuno |
| Ricevimento e stoccaggio riga ordine di trasferimento                        | Sì | Nessuno |
| Annulla lavoro (in entrata)                                              | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, ma solo quando l'opzione <b>Annulla registrazione entrata quando si annulla il lavoro</b> (nella pagina <b>Parametri di gestione magazzino</b>) viene deselezionata</p> |
| Elaborazione ricevimento prodotto ordine fornitore                          | Sì | Nessuno |
| Ricevimento degli ordini fornitore con limite minimo di fornitura                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Sì, ma solo effettuando una richiesta di cancellazione dall'hub |
| Ricevimento degli ordini fornitore con limite massimo di fornitura                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Sì  |
| Ricevimento con creazione di lavoro *Cross docking*                   | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento con creazione di lavoro *Ordine di controllo qualità*                  | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento con creazione di lavoro *Campionamento di articoli di qualità*          | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento con creazione di lavoro *Qualità nel controllo qualità*       | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento con creazione ordine di controllo qualità                            | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Elaborazione del lavoro: gestito da *Stoccaggio cluster*                             | Sì | Nessuno |
| Elaborazione del lavoro con *Prelievo in difetto*                                           | Sì | Nessuno |
| Caricamento targa                                           | Sì | Nessuno |

### <a name="warehouse-operations-and-exception-handing"></a>Operazioni di magazzino e gestione delle eccezioni

La tabella seguente mostra le operazioni di magazzino e le funzionalità di gestione delle eccezioni supportate e il punto in cui sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala nel cloud e nella rete perimetrale.

| Elaborazione                                            | Hub | Carico di lavoro WES su un'unità di scala |
|----------------------------------------------------|-----|------------------------------|
| Richiesta di informazioni sulla targa                              | Sì | Sì                          |
| Richiesta informazioni sull'articolo                                       | Sì | Sì                          |
| Richiesta di informazioni sull'ubicazione                                   | Sì | Sì                          |
| Modifica magazzino                                   | Sì | Sì                          |
| Movimento                                           | Sì | Sì                          |
| Movimento per modello                               | Sì | Sì                          |
| Trasferimento di magazzino                                 | Sì | Nessuno                           |
| Creare ordini di trasferimento dall'app per dispositivi mobili Gestione magazzino           | Sì | Nessuno                           |
| Rettifica (in ingresso/uscita)                                | Sì | Nessuno                           |
| Modifica stato magazzino                            | Sì | Nessuno                           |
| Conteggio ciclo ed elaborazione di discrepanza conteggio | Sì | Nessuno                           |
| Ristampa etichetta (stampa della targa)             | Sì | Sì                          |
| Compilazioni targa                                | Sì | Nessuno                           |
| Suddivisioni targa                                | Sì | Nessuno                           |
| Imballa in targhe nidificate                                | Sì | Nessuno                           |
| Check-in conducente                                    | Sì | Nessuno                           |
| Check-out conducente                                   | Sì | Nessuno                           |
| Codice di modifica smaltimento batch                      | Sì | Sì                          |
| Visualizza elenco lavori aperti                             | Sì | Sì                          |
| Consolida targhe                         | Sì | Nessuno                           |
| Elaborazione del rifornimento soglia min/max e di zona| Sì <p>Il consiglio è di non includere le stesse ubicazioni come parte delle query</p>| Sì                          |
| Elaborazione di rifornimento per assegnazione                  | Sì  | Sì<p>Notare che la configurazione deve essere eseguita sull'unità di scala</p>                           |
| Blocco e sblocco del lavoro                             | Sì | Sì                          |
| Cambia utente                                        | Sì | Sì                          |
| Modifica pool di lavoro nel lavoro                           | Sì | Sì                          |
| Annulla lavoro                                        | Sì | Sì                          |


### <a name="production"></a>Produzione

Gli scenari di produzione della gestione del magazzino non sono attualmente supportati sui carichi di lavoro dell'unità di scala, come indicato nella tabella seguente.

| Elaborazione | Hub | Carico di lavoro WES su un'unità di scala |
|---------|-----|------------------------------|
| <p>Tutti i processi di gestione del magazzino correlati alla produzione. Di seguito sono riportati alcuni esempi.</p><li>Rilascia in magazzino</li><li>Elaborazione di ciclo della produzione</li><li>Prelievo materie prime</li><li>Stoccaggio prodotti finiti e dichiarati finiti</li><li>Stoccaggio co-prodotti e sottoprodotti</li><li>Stoccaggio kanban</li><li>Prelievo kanban</li><li>Avvia ordine di produzione</li><li>Scarti di produzione</li><li>Ultimo pallet produzione</li><li>Registra consumo materiali</li><li>Svuota kanban</li></ul> | Sì | Nessuno |

## <a name="maintaining-scale-units-for-wes"></a>Gestione delle unità di scala per WES

Diversi processi batch vengono eseguiti sia sull'hub che sulle unità di scala.

Nella distribuzione hub, è possibile gestire manualmente i processi batch. È possibile gestire i processi batch seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro di back-office**:

- Elabora eventi di aggiornamento stato lavoro
- Processore messaggi unità di scala a hub
- Registra entrate ordine di origine
- Completamento ordini di magazzino
- Elabora risposte aggiornamento quantità per righe ordine di magazzino

Nel carico di lavoro nelle unità di scala, è possibile gestire i processi batch seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro**:

- Elaborare record di tabelle ciclo
- Hub di magazzino per processore messaggi unità di scala
- Elabora richieste aggiornamento quantità per righe ordine di magazzino

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
