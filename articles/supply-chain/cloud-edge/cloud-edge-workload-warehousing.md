---
title: Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale
description: Questo argomento fornisce informazioni sulla funzionalità che consente alle unità di scala di eseguire processi selezionati dal carico di lavoro di gestione del magazzino dell'utente.
author: perlynne
manager: tfeyr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, SysSecRolesEditUsers
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: perlynne
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 4ac76ad5cd88c35ac312b8e73d942a692f35c8aa
ms.sourcegitcommit: 8eefb4e14ae0ea27769ab2cecca747755560efa3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "4516814"
---
# <a name="warehouse-management-workloads-for-cloud-and-edge-scale-units"></a>Carichi di lavoro di gestione del magazzino per unità di scala nel cloud e nella rete perimetrale

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Non tutte le funzionalità aziendali sono completamente supportate nell'anteprima pubblica quando vengono utilizzate le unità di scala del carico di lavoro. Verificare di utilizzare solo i processi che in questo argomento vengono descritti come supportati in modo esplicito.

## <a name="warehouse-execution-on-scale-units"></a>Esecuzione nel magazzino su unità di scala

Questa funzione consente alle unità di scala di eseguire processi selezionati dalle funzionalità di gestione del magazzino. Le unità di scala nel cloud eseguono i propri carichi di lavoro nel cloud utilizzando la capacità di elaborazione dedicata nell'area di Microsoft Azure dell'utente selezionata. Per le unità di scala nella rete perimetrale, è possibile eseguire alcuni carichi di lavoro in modo indipendente in locale, anche mentre le unità di scala sono temporaneamente disconnesse dal cloud.

In questo argomento, le esecuzioni di gestione del magazzino in un magazzino definito come unità di scala sono conosciute come *Sistema di esecuzione nel magazzino* (*WES*, Warehouse Execution System).

## <a name="prerequisites"></a>Prerequisiti

È necessario disporre di un hub Dynamics 365 Supply Chain Management e di un'unità di scala distribuita con il carico di lavoro di gestione del magazzino. Per ulteriori informazioni sull'architettura e sul processo di distribuzione, vedere [Unità di scala nel cloud e nella rete perimetrale per i carichi di lavoro di gestione della produzione e del magazzino](cloud-edge-landing-page.md).

## <a name="how-the-wes-workload-works-on-scale-units"></a>Come funziona il carico di lavoro WES su unità di scala

Per i processi nel carico di lavoro di gestione del magazzino, i dati vengono sincronizzati tra l'hub e le unità di scala.

Un'unità di scala può gestire solo i dati che possiede. Il concetto di proprietà dei dati per le unità di scala consente di prevenire conflitti multimaster. Pertanto, è importante comprendere quali processi sono di proprietà dell'hub e quali delle unità di scala.

Le unità di scala possiedono i seguenti dati:

- **Dati di elaborazione ciclo** - I metodi di elaborazione ciclo selezionati vengono gestiti nell'ambito dell'elaborazione del ciclo dell'unità di scala.
- **Dati di elaborazione lavoro** - Sono supportati i seguenti tipi di elaborazione degli ordini di lavoro:

    - Movimenti scorte (movimento manuale e movimento per modello di lavoro)
    - Ordini fornitore (lavoro di stoccaggio tramite un ordine di magazzino)
    - Ordini cliente (semplice lavoro di prelievo e di carico)

- **Dati di ricevimento ordini di magazzino** - Questi dati vengono utilizzati solo per gli ordini fornitore rilasciati manualmente a un magazzino.
- **Dati di targa** - Le targhe possono essere create sull'hub e sull'unità di scala. È stata fornita una gestione dei conflitti dedicata. S noti che questi dati non sono specifici del magazzino.

## <a name="outbound-process-flow"></a>Flusso di elaborazione in uscita

L'hub possiede i seguenti dati:

- Tutti i documenti di origine, come ordini cliente e ordini di trasferimento
- Allocazione degli ordini ed elaborazione del carico in uscita
- Processi di rilascio in magazzino e di creazione della spedizione e del ciclo

Le unità di scala prevedono l'effettiva elaborazione del ciclo (come l'allocazione del lavoro, il lavoro di rifornimento e la creazione del lavoro in base alla domanda) dopo il rilascio del ciclo. Pertanto, gli addetti al magazzino possono elaborare il lavoro in uscita utilizzando un'app di magazzino connessa all'unità di scala.

![Flusso di elaborazione ciclo](./media/wes_wave_processing_flow.png "Flusso di elaborazione ciclo")

## <a name="inbound-process-flow"></a>Flusso di elaborazione in entrata

L'hub possiede i seguenti dati:

- Tutti i documenti di origine, come ordini fornitore e ordini di reso vendite
- Elaborazione carico in entrata

> [!NOTE]
> Il flusso di ordini fornitore in entrata è concettualmente diverso dal flusso in uscita, in cui l'unità di scala che esegue l'elaborazione dipende dal fatto che l'ordine sia stato rilasciato a un magazzino.

Se si utilizza il processo di *rilascio a magazzino*, gli ordini di magazzino vengono creati e la proprietà del flusso di ricevimento correlato viene assegnata all'unità di scala. L'hub non sarà in grado di registrare il ricevimento in entrata.

L'addetto al magazzino può eseguire il processo di ricevimento utilizzando un'app di magazzino connessa all'unità di scala. I dati vengono quindi registrati dall'unità di scala e indicati rispetto all'ordine di magazzino in entrata. Anche la creazione e l'elaborazione dello stoccaggio successivo saranno gestite dall'unità di scala.

Se non utilizzi il processo *rilascio in magazzino* e pertanto non utilizzi *ordini di magazzino*, l'hub può elaborare il ricevimento in magazzino e l'elaborazione del lavoro indipendentemente dalle unità di scala.

![Flusso di elaborazione in entrata](./media/wes_Inbound_flow.png "Flusso di elaborazione in entrata")

## <a name="supported-processes-and-roles"></a>Processi e ruoli supportati

Non tutti i processi di gestione del magazzino sono supportati in un carico di lavoro WES su un'unità di scala. Pertanto, si consiglia di assegnare ruoli che corrispondono alla funzionalità disponibile per ogni utente.

Per facilitare questo processo, un ruolo di esempio denominato *Responsabile magazzino per il carico di lavoro* è incluso nei dati di esempio in **Amministrazione sistema \> Sicurezza \> Configurazione sicurezza**. Lo scopo di questo ruolo è consentire ai responsabili del magazzino di accedere al WES sull'unità di scala. Il ruolo concede l'accesso alle pagine rilevanti nel contesto di un carico di lavoro ospitato su un'unità di scala.

I ruoli utente su un'unità di scala vengono assegnati come parte della sincronizzazione iniziale dei dati dall'hub all'unità di scala.

Per modificare i ruoli assegnati a un utente, andare ad **Amministrazione sistema \> Sicurezza \> Assegna utenti a ruoli** sul'unità di scala. Agli utenti che agiscono come responsabili di magazzino solo su unità di scala deve essere assegnato solo il ruolo *Responsabile magazzino per il carico di lavoro*. Questo approccio garantirà che tali utenti abbiano accesso solo alle funzionalità supportate. Rimuovere tutti gli altri ruoli assegnati a tali utenti.

Agli utenti che agiscono come responsabili di magazzino nell'hub e nelle unità di scala deve essere assegnato il ruolo *Addetto magazzino*. Tenere presente che questo ruolo concede agli addetti al magazzino l'accesso a funzionalità (come l'elaborazione degli ordini di trasferimento) presenti nell'interfaccia utente, ma non attualmente supportate sulle unità di scala.

## <a name="supported-wes-processes"></a>Processi WES supportati

I seguenti processi di esecuzione del magazzino possono essere abilitati per un carico di lavoro WES su un'unità di scala:

- Metodi di ciclo selezionati per gli ordini cliente e il rifornimento della domanda
- Esecuzione di ordini di lavoro da ordini cliente e rifornimento della domanda utilizzando l'app di magazzino
- Esecuzione di query sulle scorte disponibili utilizzando l'app di magazzino
- Creazione ed esecuzione di movimenti di inventario utilizzando l'app di magazzino
- Registrazione di ordini fornitore ed esecuzione del lavoro di stoccaggio utilizzando l'app di magazzino

I seguenti tipi di ordine di lavoro sono attualmente supportati per i carichi di lavoro WES su distribuzioni di unità di scala:

- Gestione ordini cliente
- Rifornimento
- Movimento scorte
- Ordini fornitore collegati a ordini di magazzino

Nessun'altra elaborazione dei documenti di origine è attualmente supportata su unità di scala. Ad esempio, per un carico di lavoro WES su un'unità di scala, non è possibile eseguire le seguenti azioni:

- Rilasciare un ordine di trasferimento.
- Elaborare le operazioni di prelievo e spedizione dal magazzino in uscita.

> [!IMPORTANT]
> Se si utilizza un carico di lavoro su un'unità di scala, non è possibile eseguire processi non supportati per il magazzino specifico nell'hub.

La seguente funzionalità di gestione del magazzino non è attualmente supportata sulle unità di scala:

- Elaborazione in entrata e in uscita per gli articoli che hanno dimensioni di tracciabilità attive (come le dimensioni del batch o del numero di serie)
- Elaborazione delle modifiche allo stato dell'inventario
- Elaborazione dell'inventario con un valore di stato di blocco
- Integrazione con la gestione della qualità
- Integrazione con la produzione
- Elaborazione degli articoli a peso variabile
- Elaborazione di consegne in eccesso e in difetto
- Elaborazione delle scorte disponibili negative

### <a name="outbound-supported-only-for-sales-orders-and-demand-replenishment"></a>In uscita (opzione supportata solo per ordini cliente e rifornimento della domanda)

La tabella seguente mostra quali funzionalità in uscita sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

> [!WARNING]
> Poiché è supportata solo l'elaborazione degli ordini cliente, l'elaborazione della gestione del magazzino in uscita non può essere utilizzata per gli ordini di trasferimento.
>
> Alcune funzionalità di magazzino non saranno disponibili nei magazzini che eseguono i carichi di lavoro di gestione del magazzino in un'unità di scala.

| Elaborazione                                                      | Hub | Carico di lavoro WES su un'unità di scala |
|--------------------------------------------------------------|-----|------------------------------|
| Elaborazione documenti di origine                                   | Sì | Nessuno |
| Elaborazione del carico e della gestione trasporto                | Sì | Nessuno |
| Rilascia in magazzino                                         | Sì | Nessuno |
| Consolidamento spedizioni                                       | Nessuno  | Nessuno |
| Cross-docking (lavoro di prelievo)                                 | Nessuno  | Nessuno |
| Elaborazione ciclo di spedizione                                     | No, ma la finalizzazione dello stato del ciclo viene gestita nell'hub |<p>Sì, ma le funzionalità seguenti non sono supportate:</p><ul><li>Creazione di lavori paralleli</li><li>Allestimento del carico e ordinamento</li><li>Containerizzazione</li><li>Stampa di etichette ciclo</li></li></ul><p><b>Nota:</b> l'accesso all'hub è necessario per finalizzare lo stato del ciclo come parte dell'elaborazione del ciclo.</p> |
| Elaborazione del lavoro di magazzino (inclusa la stampa della targa)     | Nessuno  | <p>Sì, ma solo per le seguenti funzionalità:</p><ul><li>Prelievo vendite (senza l'utilizzo di dimensioni di tracciabilità attive)</li><li>Caricamento vendite (senza l'utilizzo di dimensioni di tracciabilità attive)</li></ul> |
| Prelievo cluster                                              | Nessuno  | Nessuno |
| Elaborazione imballaggio                                           | Nessuno  | Nessuno |
| Elaborazione ordinamento in uscita                                  | Nessuno  | Nessuno |
| Stampa di documenti relativi al carico                           | Sì | Nessuno |
| Polizza di carico e generazione di ASN                            | Sì | Nessuno |
| Conferma della spedizione ed elaborazione dei documenti di trasporto                | Sì | Nessuno |
| Prelievo breve (ordini cliente)                                 | Nessuno  | Nessuno |
| Annullamento lavoro                                            | Nessuno  | Nessuno |
| Modifica delle sedi di lavoro (ordini cliente)                      | Nessuno  | Nessuno |
| Lavoro completo (ordini cliente)                                 | Nessuno  | Nessuno |
| Blocco e sblocco del lavoro                                       | Nessuno  | Nessuno |
| Cambia utente                                                  | Nessuno  | Nessuno |
| Stampa report di lavoro                                            | Nessuno  | Nessuno |
| Etichetta ondata                                                   | Nessuno  | Nessuno |
| Storna lavoro                                                 | Nessuno  | Nessuno |

### <a name="inbound"></a>In entrata

La tabella seguente mostra quali funzionalità in entrata sono supportate e dove sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala cloud e edge.

| Elaborazione                                                          | Hub | Carico di lavoro WES su un'unità di scala |
|------------------------------------------------------------------|-----|------------------------------|
| Elaborazione&nbsp;documenti&nbsp;di origine                                       | Sì | Nessuno |
| Elaborazione del carico e della gestione trasporto                    | Sì | Nessuno |
| Conferma della spedizione                                            | Sì | Nessuno |
| Rilascio ordine fornitore al magazzino (elaborazione ordine di magazzino) | Sì | Nessuno |
| Ricevimento e stoccaggio articolo ordine acquisto                        | <p>Sì,&nbsp;quando&nbsp;non&nbsp;è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, quando è presente un ordine di magazzino e quando un ordine fornitore non fa parte di un <i>carico</i>. Tuttavia, è necessario utilizzare due voci di menu del dispositivo mobile, una per il ricevimento (<i>Ricevimento articolo ordine acquisto</i>) e un'altra, con l'opzione <b> Utilizza lavoro esistente</b> abilitata, per elaborare lo stoccaggio.</p><p>No, quando non è presente un ordine di magazzino.</p> |
| Ricevimento e stoccaggio riga ordine acquisto                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento e stoccaggio ordine di reso                               | Sì | Nessuno |
| Ricevimento e stoccaggio targa mista                        | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricezione articoli di carico                                              | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento e stoccaggio targa                              | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |
| Ricevimento e stoccaggio articolo ordine di trasferimento                        | Sì | Nessuno |
| Ricevimento e stoccaggio riga ordine di trasferimento                        | Sì | Nessuno |
| Annullamento lavoro                                                | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | <p>Sì, ma l'opzione <b>Annulla registrazione entrata quando si annulla il lavoro</b> (nella pagina <b>Parametri di gestione magazzino</b>) non è supportata.</p> |
| Elaborazione ricevimento prodotto ordine fornitore                        | Sì | Nessuno |
| Creazione di lavoro cross-docking come parte del ricevimento                 | <p>Sì, quando non è presente un ordine di magazzino</p><p>No, quando è presente un ordine di magazzino</p> | Nessuno |

### <a name="warehouse-operations-and-exception-handing"></a>Operazioni di magazzino e gestione delle eccezioni

La tabella seguente mostra le operazioni di magazzino e le funzionalità di gestione delle eccezioni supportate e il punto in cui sono supportate quando i carichi di lavoro di gestione del magazzino vengono utilizzati in unità di scala nel cloud e nella rete perimetrale.

| Elaborazione                                            | Hub | Carico di lavoro WES su un'unità di scala |
|----------------------------------------------------|-----|------------------------------|
| Richiesta di informazioni sulla targa                              | Sì | Sì                          |
| Richiesta informazioni sull'articolo                                       | Sì | Sì                          |
| Richiesta di informazioni sull'ubicazione                                   | Sì | Sì                          |
| Modifica magazzino                                   | Sì | Sì                          |
| Movimento                                           | Nessuno  | Sì                          |
| Movimento per modello                               | Nessuno  | Sì                          |
| Rettifica (in ingresso/uscita)                                | Sì | Nessuno                           |
| Conteggio ciclo ed elaborazione di discrepanza conteggio | Sì | Nessuno                           |
| Ristampa etichetta (stampa della targa)             | Sì | Nessuno                           |
| Compilazioni targa                                | Sì | Nessuno                           |
| Suddivisioni targa                                | Sì | Nessuno                           |
| Check-in conducente                                    | Sì | Nessuno                           |
| Check-out conducente                                   | Sì | Nessuno                           |
| Codice di modifica smaltimento batch                      | Sì | Nessuno                           |
| Visualizza elenco lavori aperti                             | Sì | Nessuno                           |
| Consolida targhe                         | Nessuno  | Nessuno                           |
| Rimuovi contenitore da gruppo                        | Nessuno  | Nessuno                           |
| Annulla lavoro                                        | Nessuno  | Nessuno                           |
| Elaborazione di rifornimento minimo/massimo                   | Nessuno  | Nessuno                           |
| Elaborazione di rifornimento per assegnazione                  | Nessuno  | Nessuno                           |

### <a name="production"></a>Produzione

L'integrazione della gestione del magazzino per gli scenari di produzione non è attualmente supportata, come indicato nella tabella seguente.

| Elaborazione | Hub | Carico di lavoro WES su un'unità di scala |
|---------|-----|------------------------------|
| <p>Tutti i processi di gestione del magazzino correlati alla produzione. Di seguito sono riportati alcuni esempi.</p><li>Rilascia in magazzino</li><li>Elaborazione di ciclo della produzione</li><li>Prelievo materie prime</li><li>Stoccaggio prodotti finiti</li><li>Stoccaggio co-prodotti e sottoprodotti</li><li>Stoccaggio kanban</li><li>Prelievo kanban</li><li>Avvia ordine di produzione</li><li>Scarti di produzione</li><li>Ultimo pallet produzione</li><li>Registra consumo materiali</li><li>Svuota kanban</li></ul> | Nessuno | Nessuno |

## <a name="maintaining-scale-units-for-wes"></a>Gestione delle unità di scala per WES

Diversi processi batch vengono eseguiti sia sull'hub che sulle unità di scala.

Nella distribuzione hub, è possibile gestire manualmente i processi batch. È possibile gestire i tre processi seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro di back-office**:

- Elabora eventi di aggiornamento stato lavoro
- Elabora eventi di trasferimento del controllo di esecuzione ondata
- Registra entrate ordine di origine

Nel carico di lavoro nelle unità di scala, è possibile gestire i due processi batch seguenti in **Gestione magazzino \> Attività periodiche \> Gestione carico di lavoro**:

- Elaborare record di tabelle ciclo
- Elabora eventi di trasferimento del controllo di esecuzione ondata


[!INCLUDE[footer-include](../../includes/footer-banner.md)]