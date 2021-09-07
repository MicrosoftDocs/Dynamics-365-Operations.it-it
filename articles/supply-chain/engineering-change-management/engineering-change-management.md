---
title: Gestire le modifiche ai prodotti di progettazione
description: Vengono fornite le informazioni sulla gestione delle modifiche ai prodotti di progettazione. La gestione delle modifiche di progettazione fornisce processi strutturati per la gestione delle modifiche ai prodotti di progettazione, dalla proposta, richiesta e apporto di modifiche, alla revisione e approvazione delle modifiche, alla valutazione del loro impatto sulle transazioni esistenti e alle attività di follow-up.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgEcmRequestSelection,EngChgEcmRequestProducts,EngChgEcmRequestPriorityChart,EngChgEcmRequestListPage,EngChgEcmRequestFilteredPart,EngChgEcmRequestDetails,EngChgEcmReason,EngChgEcmProjTableInformation,EngChgEcmProductRoute,EngChgEcmProductRelease,EngChgEcmProductPreview, EngChgEcmWhereUsed, EngChgEcmInventTrans,EngChgEcmHeaderSelection,EngChgEcmHeaderPreviewPart,EngChgEcmHeaderFilteredPart,EngChgEcmHeaderDetails, EngChgCaseWhereUsedAnalysis, EngChgCaseValidatorMessage
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: bb6fd57f200b101cb2df396cb10417feaa9425c1
ms.sourcegitcommit: 2b04b5a5c883d216072bb91123f9c7709a41f69a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/16/2021
ms.locfileid: "7384587"
---
# <a name="manage-changes-to-engineering-products"></a>Gestire le modifiche ai prodotti di progettazione

[!include [banner](../includes/banner.md)]

La gestione delle modifiche di progettazione fornisce processi strutturati per la gestione delle modifiche ai prodotti di progettazione. È possibile utilizzare il processo *richiesta di modifiche di progettazione* per proporre e richiedere modifiche, quindi utilizzare il processo *ordine di modifica di progettazione* per apportare effettivamente tali modifiche. Gli utenti possono creare richieste di modifica di progettazione oppure ordini di modifica di progettazione, quindi è disponibile un processo per esaminarli e approvarli, valutarne l'impatto sulle transazioni esistenti ed eseguire le attività di follow-up.

## <a name="engineering-change-requests"></a>Richieste di modifica di progettazione

Il processo di richiesta di modifica di progettazione consente di acquisire richieste di modifiche da tutti i reparti pertinenti dell'azienda. Indipendentemente dal tipo di lavoro, come tecnico o nel reparto produzione, approvvigionamento, magazzino o vendite, chiunque può utilizzare una richiesta di modifica di progettazione per richiedere una modifica. Questa modifica potrebbe essere un'idea per un nuovo prodotto, un problema scoperto mentre si lavorava su un prodotto esistente, un suggerimento per migliorare un prodotto esistente o altro.

Dopo che qualcuno ha inviato una richiesta di modifica, il processo *revisione e approvazione* è gestito da un flusso di lavoro che identifica chi deve approvare la modifica (ad esempio il proprietario del prodotto).

Per impostare un flusso di lavoro per gli ordini di modifica di progettazione o le richieste di modifica di progettazione, andare a **Gestione modifiche di progettazione \> Flussi di lavoro di progettazione**. Selezionare **Nuovo**, selezionare se il flusso di lavoro verrà utilizzato per esaminare gli ordini di modifica di progettazione o le richieste di modifica di progettazione, quindi configurare il flusso di lavoro.

Per ulteriori informazioni sui flussi di lavoro, vedere [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md). Per ulteriori informazioni sui proprietari di prodotti, vedere [Proprietari di prodotti](product-owner.md).

### <a name="create-a-new-engineering-change-request"></a>Crea una nuova richiesta di modifica di progettazione

Per creare una richiesta di modifica di progettazione, eseguire una delle operazioni seguenti.

- Andare a **Gestione modifiche di progettazione \> Comune \> Gestione modifiche di progettazione \> Richieste modifiche di progettazione** e quindi selezionare **Nuovo** sul riquadro azioni.
- Aprire la pagina **Dettagli prodotto** per un prodotto di ingegneria esistente. Nel riquadro azioni, nella scheda **Progetta**, nel gruppo **Gestione modifiche di progettazione** selezionare **Richiesta modifica di progettazione \> Nuova richiesta modifica di progettazione**.

Viene creata una nuova richiesta di modifica. In ogni Scheda dettaglio è ora possibile impostare i campi come descritto nelle sottosezioni seguenti.

#### <a name="general-fasttab"></a>Scheda dettaglio Generale

La Scheda dettaglio **Generale** consente di fornire una descrizione di base della richiesta di modifica. Nella tabella seguente vengono illustrati i campi della Scheda dettaglio.

| Campo | Descrizione |
|---|---|
| Richiesta di modifica | Immettere un nome per la richiesta di modifica. |
| Funzione | Immettere un testo che descriva o identifichi brevemente le modifiche nella richiesta. |
| Priorità | Selezionare un valore per indicare il livello di priorità della modifica. È possibile personalizzare i valori disponibili per la propria azienda, in base alle richieste. Per ulteriori informazioni, vedere [Stabilire valori comuni per la gestione delle modifiche di progettazione](engineering-change-management-setup.md). |
| Categoria | Selezionare un valore per descrivere il tipo di modifica richiesta. È possibile personalizzare i valori disponibili per la propria azienda, in base alle richieste. Per ulteriori informazioni, vedere [Stabilire valori comuni per la gestione delle modifiche di progettazione](engineering-change-management-setup.md). |
| Gravità | Selezionare un valore per indicare la gravità del problema che deve essere risolto implementando la richiesta. È possibile personalizzare i valori disponibili per la propria azienda, in base alle richieste. Per ulteriori informazioni, vedere [Stabilire valori comuni per la gestione delle modifiche di progettazione](engineering-change-management-setup.md). |
| Richiesto da | Nome dell'utente che ha creato la richiesta. |
| Su | Data di registrazione della richiesta. |
| Stato | Stato della richiesta. Quando una richiesta viene creata per la prima volta, lo stato è *Creato*. Quando la richiesta viene approvata, lo stato cambia in *Approvato*. Se per la richiesta è stato creato un ordine di modifica correlato, lo stato cambia in *Con follow-up*. |
| Ordine di modifica | Numero dell'ordine di modifica, se alla richiesta di modifica è stato dato seguito tramite un ordine di modifica. |

#### <a name="information-fasttab"></a>Scheda dettaglio Informazioni

La Scheda dettaglio **Informazioni** consente di aggiungere altre informazioni sulla richiesta.

Per aggiungere una riga alla griglia, selezionare **Nuovo** sulla barra degli strumenti sopra la griglia, quindi selezionare una delle seguenti opzioni:

- **File** - Carica un file.
- **Immagine** - Carica un file immagine.
- **Nota** - Consente di immettere una nota direttamente nella griglia.
- **URL** - Consente di immettere un URL direttamente nella griglia.

Nella seguente tabella vengono illustrati i campi di ogni riga.

| Campo | Descrizione |
|---|---|
| Data e ora creazione | Data e ora di creazione della riga. |
| Tipo | Tipo di informazioni per cui è stata creata la riga (file, immagine, nota o URL). |
| Descrizione | Immettere un descrizione per la riga. |
| Restrizione | Valore che indica se le informazioni aggiunte provengono da un'origine interna o esterna. |
| Allegato | Una casella di controllo selezionata indica che la riga include un allegato (file o immagine). Per scaricare l'allegato, selezionare la riga, quindi selezionare **Apri** sulla barra degli strumenti sopra la griglia. |

#### <a name="products-fasttab"></a>Scheda dettaglio Prodotti

La Scheda dettaglio **Prodotti** consente di elencare ogni prodotto interessato dalla richiesta di modifica. Utilizzare i pulsanti sulla barra degli strumenti per aggiungere prodotti alla griglia o per rimuove i prodotti.

Questo elenco è fornito solo a scopo informativo. Pertanto, è possibile aggiungere tutti i prodotti correlati che si ritengono pertinenti. Se si crea una richiesta di modifica nella pagina **Dettagli prodotto** per un prodotto esistente, tale prodotto deve essere elencato nella Scheda dettaglio **Prodotti** dopo il salvataggio del record di richiesta.

#### <a name="source-fasttab"></a>Scheda dettaglio Origine

La Scheda dettaglio **Origine** consente di tenere traccia del punto di inizio della richiesta di modifica. È utile, ad esempio, se si desidera vedere se la richiesta di modifica è stata creata da un ordine cliente, l'autore della creazione e l'azienda in cui è stata creata.

### <a name="evaluate-the-business-impact-of-a-change-request-and-send-notifications"></a>Valutare l'impatto aziendale di una richiesta di modifica e inviare le notifiche

Quando si esamina una richiesta di modifica, è possibile cercare le dipendenze. In questo modo, è possibile valutare l'impatto della modifica richiesta sulle transazioni aperte, ad esempio ordini cliente, ordini di produzione e scorte disponibili. Mentre esamini le richieste di modifica, puoi inviare notifiche alle persone responsabili dell'adempimento dei vari tipi di ordini correlati.

#### <a name="review-affected-transactions-block-selected-transactions-and-send-notifications"></a>Rivedi le transazioni interessate, blocca le transazioni selezionate e invia notifiche

Per rivedere le transazioni interessate, blocca le transazioni selezionate e inviare le relative notifiche, segui questi passaggi.

1. Andare a **Gestione modifiche di progettazione \> Comune \> Gestione modifiche di progettazione \> Richieste modifiche di progettazione**.
1. Aprire una richiesta di modifica esistente o selezionare **Nuovo** nel riquadro azioni per creare una nuova richiesta di modifica.
1. Nel riquadro azioni, nella scheda **Richiesta di modifica**, nel gruppo **Impatto aziendale** selezionare uno dei pulsanti seguenti:

    - **Cerca** - Esegue la scansione di tutte le transazioni aperte, quindi apre la finestra di dialogo **Impatto aziendale sulle transazioni aperte** in cui sono elencate tutte le transazioni che saranno interessate dalla modifica.
    - **Visualizza ricerca precedente** - Apre la finestra di dialogo **Impatto aziendale sulle transazioni aperte** in cui sono elencati i risultati della ricerca precedente. Non viene eseguita una nuova ricerca.

1. La finestra di dialogo **Impatto aziendale sulle transazioni aperte** fornisce una serie di schede, ognuna delle quali mostra un elenco di transazioni interessate di un tipo specifico (**Ordini di vendita**, **Ordini di acquisto**, **Ordini di produzione**, **Inventario**, e così via). Ogni scheda mostra anche un numero che indica il numero di transazioni interessate di quel tipo. Seleziona una scheda per visualizzare l'elenco pertinente.
1. Per lavorare con una transazione nell'elenco, selezionala, quindi seleziona uno dei seguenti pulsanti sulla barra degli strumenti:

    - **Visualizza transazione**: apri il record della transazione selezionato.
    - **Blocca ordine**: questo pulsante è disponibile solo nella scheda **Ordini di vendita**. Selezionalo per bloccare l'ordine cliente selezionato.
    - **Blocca riga**: questo pulsante è disponibile solo nella scheda **Ordini di acquisto**. Selezionalo per bloccare la riga ordine cliente selezionata.
    - **Notifica responsabile**: questo pulsante è disponibile solo nella scheda **Ordini di vendita**. Selezionalo per inviare una notifica di modifica all'utente impostato come responsabile dell'ordine cliente selezionato. Per ulteriori informazioni su chi può vedere le notifiche e come, vedi [Rivedere ed elaborare le notifiche di modifica per le transazioni](#review-notifications).
    - **Notifica responsabile ordine**: questo pulsante è disponibile solo nella scheda **Ordini di acquisto**. Selezionalo per inviare una notifica di modifica all'utente impostato come responsabile dell'ordine di acquisto selezionato. Per ulteriori informazioni su chi può vedere le notifiche e come, vedi [Rivedere ed elaborare le notifiche di modifica per le transazioni](#review-notifications).
    - **Notifica produzione**; questo pulsante è disponibile solo nella scheda **Ordini di produzione**. A differenza degli ordini di vendita e degli ordini di acquisto, gli ordini di produzione non hanno un singolo utente che ne sia responsabile dall'inizio alla fine. Invece, vari supervisori o pianificatori di solito assumono la proprietà di un sito specifico o di una parte specifica della produzione (ad esempio, per risorse o gruppi di risorse specifici). Pertanto, quando si seleziona questo pulsante, tutti gli utenti responsabili di qualsiasi risorsa correlata all'ordine di produzione selezionato ricevono una notifica di modifica. Per ulteriori informazioni su chi può vedere le notifiche e come, vedi [Rivedere ed elaborare le notifiche di modifica per le transazioni](#review-notifications).
    - **Notifica preparatore**: questo pulsante è disponibile solo nella scheda **Richiesta di acquisto**. Selezionalo per inviare una notifica di modifica all'utente impostato come preparatore della richiesta di acquisto selezionata. Per ulteriori informazioni su chi può vedere le notifiche e come, vedi [Rivedere ed elaborare le notifiche di modifica per le transazioni](#review-notifications).
    - **Notifica responsabile vendite**: questo pulsante è disponibile solo nella scheda **Offerte**. Selezionalo per inviare una notifica di modifica all'utente impostato come responsabile dell'offerta selezionata. Per ulteriori informazioni su chi può vedere le notifiche e come, vedi [Rivedere ed elaborare le notifiche di modifica per le transazioni](#review-notifications).
    - **Scarto**: questo pulsante è disponibile solo nella scheda **Inventario**. Selezionalo per scartare l'inventario selezionato.
    - **Visualizza cronologia**: apri una cronologia delle azioni che sono state eseguite sulla transazione selezionata utilizzando la finestra di dialogo **Impatto aziendale sulle transazioni aperte**. (Ad esempio, la cronologia mostra se le notifiche sono state inviate o le transazioni sono state bloccate.) 
    - **Visualizza tutte le transazioni**: apri l'elenco completo di tutte le transazioni, non solo le transazioni aperte.

#### <a name="review-and-process-change-notifications-for-transactions"></a><a name="review-notifications"></a>Rivedere ed elaborare le notifiche di modifica per le transazioni

Puoi leggere ed elaborare le notifiche di modifica che ricevi nei seguenti modi:

- Tranne nel caso degli ordini di produzione, le notifiche di modifica per le transazioni di cui sei responsabile vengono visualizzate nel Centro azioni. Il pulsante **Mostra messaggi** (simbolo della campana) sul lato destro della barra di spostamento indica quando un messaggio del centro azioni è disponibile per l'utente corrente. Seleziona **Mostra messaggi** per aprire il Centro azioni e rivedere i messaggi.
- Per visualizzare tutti gli ordini di produzione per cui è stata inviata una notifica di progettazione, andare a **Ordini di produzione \> Ordini di produzione \> Tutti gli ordini di produzione**. Quindi, nel riquadro azioni, nella scheda **Ordine di produzione**, nel gruppo **Richiesta di modifica di progettazione** seleziona **Notifiche di progettazione** per aprire la pagina **Notifiche di progettazione**.
- Per gli ordini di produzione, puoi scegliere di esaminare solo le notifiche di modifica che si applicano alle risorse di produzione che gestisci. Nell'area di lavoro **Gestione area di produzione** area di lavoro, nel riquadro azioni seleziona **Configura area di lavoro personale** per filtrare la pagina in modo che mostri solo le informazioni sulle unità di produzione, i gruppi e/o le risorse che gestisci. Nella sezione **Riepilogo**, un riquadro denominato **Ordini di produzione con prodotti modificati** mostra un conteggio delle notifiche che corrispondono alle impostazioni del filtro. Seleziona questo riquadro per aprire la pagina **Notifiche di progettazione**, che mostra l'elenco completo delle transazioni che soddisfano i criteri del filtro.

Mentre stai esaminando le notifiche degli ordini di produzione nella pagina **Notifiche di progettazione** è possibile seguire i collegamenti agli ordini di modifica o di produzione correlati selezionando i valori delle colonne o utilizzando i comandi correlati nel riquadro azioni. Dopo aver finito di valutare una modifica e dopo aver annullato o modificato gli ordini di produzione come richiesto, è possibile contrassegnare una notifica come risolta. Seleziona la notifica e quindi, nel riquadro azioni, seleziona **Risolvi**. La notifica viene rimossa dalle visualizzazioni di tutti gli utenti.

### <a name="create-a-change-order-from-a-change-request"></a>Creare un ordine di modifica da una richiesta di modifica

Un tecnico che esamina una richiesta di modifica di progettazione può creare un ordine di modifica di progettazione direttamente dalla pagina **Richieste di modifica di progettazione**. Nel riquadro azioni, nella scheda **Richiesta di modifica**, nel gruppo **Ordine di modifica di progettazione** selezionare **Copia collegamento e prodotti**.

## <a name="engineering-change-orders"></a>Ordini di modifica di progettazione

Gli ordini di modifica di progettazione forniscono un processo strutturato per apportare modifiche ai prodotti di progettazione. È possibile proporre modifiche utilizzando una copia dei dati rilevanti per la progettazione. I dati master reali non sono interessati. Per ulteriori informazioni sui dati di progettazione rilevanti, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

È possibile creare un ordine di modifica di progettazione basato su una richiesta di modifica di progettazione approvata. I tecnici possono anche creare ordini di modifica di progettazione completamente nuovi. È possibile includere più prodotti in un singolo ordine di modifica di progettazione eseguendo una di queste operazioni:

- Selezionare manualmente i prodotti.
- Utilizzare la distinta base (DBA) per includere i prodotti a livello inferiore nella struttura del prodotto (ovvero i figli).
- Utilizzare una ricerca in base al punto di utilizzo per includere i prodotti a livello superiore nella struttura del prodotto (ovvero i genitori).

Dopo che la proposta di modifiche è stata completata, il processo di revisione e approvazione verrà gestito da un flusso di lavoro. È possibile impostare diversi flussi di lavoro, in base alla priorità e alla gravità.

Per impostare un flusso di lavoro per gli ordini di modifica di progettazione o le richieste di modifica di progettazione, andare a **Gestione modifiche di progettazione \> Flussi di lavoro di progettazione**. Selezionare **Nuovo**, selezionare se il flusso di lavoro verrà utilizzato per esaminare gli ordini di modifica di progettazione o le richieste di modifica di progettazione, quindi configurare il flusso di lavoro.

Per ulteriori informazioni sui flussi di lavoro, vedere [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md).

Di seguito sono riportate alcune parti interessate tipiche che potrebbero avere la responsabilità di approvare un ordine di modifica di progettazione:

- **Proprietari informazioni** - Per ulteriori informazioni sui proprietari di prodotti, vedere [Proprietari di prodotti](product-owner.md).
- **Lead team responsabile** - Il campo **Elabora** nella visualizzazione **Intestazione** dell'ordine di modifica di progettazione mostra il tecnico che ha creato l'ordine di modifica di progettazione. Se il tecnico appartiene a un team definito nel sistema, il campo **Responsabile** mostra il leader di tale team.
- **Reparto amministrazione** - Il reparto amministrazione può esaminare i casi in cui la modifica comporta costi elevati.

È possibile scegliere se l'ordine di modifica di progettazione deve essere elaborato subito dopo l'approvazione, come parte del flusso di lavoro, o se l'elaborazione deve essere eseguita in un secondo momento, come passaggio manuale. Durante l'elaborazione di un ordine di modifica di progettazione, i dati tecnici sul prodotto effettivo vengono aggiornati.

Durante la revisione di una richiesta per la modifica, nella scheda **Richiesta di modifica** nel riquadro azioni, nel gruppo **Impatto aziendale** selezionare **Cerca** per valutare l'impatto della modifica proposta sulle transazioni aperte, ad esempio gli ordini cliente, gli ordini di produzione e le scorte disponibili. I risultati sono mostrati nella finestra di dialogo **Impatto aziendale sulle transazioni aperte**, in cui è possibile selezionare le transazioni interessate e quindi utilizzare i comandi nella barra degli strumenti per visualizzare ulteriori informazioni, inviare una notifica all'utente responsabile o bloccare la transazione.

### <a name="engineering-change-orders-in-engineering-or-operational-companies"></a>Ordini di modifica di progettazione in società operative o di progettazione

Come descritto in [Società di progettazione e regole sulla proprietà dei dati](engineering-org-data-ownership-rules.md), i dati di prodotto che è possibile modificare variano a seconda del tipo di persona giuridica in cui si lavora (società operativa o di progettazione). Le regole sulla proprietà dei dati vengono applicate anche agli ordini di modifica di progettazione. Pertanto, a seconda della persona giuridica in cui si crea un ordine di modifica di progettazione, è possibile apportare diversi tipi di modifiche. Di seguito sono riportati alcuni esempi.

- Per gli ordini di modifica di progettazione in una *società di progettazione*, è possibile apportare modifiche di base ai dati di progettazione. Ad esempio, è possibile creare nuove versioni di un prodotto, modificare la struttura di un prodotto tramite la DBA e modificare i valori degli attributi di progettazione. Per ogni prodotto interessato, selezionare uno dei seguenti valori nel campo **Impatto**:

    - **Nessuno** - Aggiorna la versione del prodotto esistente (aggiornamento nella versione).
    - **Nuova versione** - Crea una nuova versione basata sulla versione del prodotto selezionata.
    - **Nuovo prodotto** - Crea un prodotto completamente nuovo basato sulla versione di prodotto selezionata.
    - **Nuova variante** - Crea una nuova variante basata sulla versione del prodotto selezionata. La sua distinta base e le informazioni sul ciclo di lavorazione verranno copiate.

- Per gli ordini di modifica di progettazione in una *società operativa*, è possibile modificare i dati logistici del prodotto. Ad esempio, è possibile arricchire la DBA esistente con le impostazioni per l'approvvigionamento, aggiungere cicli di lavorazione o DBA locali e anche arricchire una DBA aggiungendo nuove righe DBA per materiali di imballaggio locali, fluidi lubrificanti o istruzioni nella lingua locale. I miglioramenti apportati dagli utenti nella società operativa verranno mantenuti quando vengono inviati nuovi aggiornamenti dalla società di progettazione. Per ulteriori informazioni, vedere [Società di progettazione e regole sulla proprietà dei dati](engineering-org-data-ownership-rules.md).

    Quando gli ordini di modifica di progettazione vengono elaborati nella società di progettazione, i prodotti vengono creati e/o aggiornati solo nella società di progettazione. Pertanto, se devono essere aggiornati anche i dati master del prodotto, è necessario rilasciare i prodotti anche alle società operative.

- È possibile rilasciare prodotti direttamente dagli ordini di modifica di progettazione. Aprire l'ordine di modifica e quindi, nella scheda **Ordine di modifica** del riquadro azioni, nel gruppo **Rilasci prodotto** selezionare **Struttura prodotto di rilascio**. Il processo funziona esattamente come quando si rilasciano prodotti dalla pagina **Prodotti rilasciati**. Per ulteriori informazioni, vedere [Strutture di rilascio prodotti](release-product-structure.md).
- È possibile rilasciare automaticamente i prodotti dagli ordini di modifica di progettazione, in base ai fattori seguenti:

    - Nuovi rilasci alle aziende a cui i prodotti erano stati rilasciati in precedenza. Selezionare **Cerca** per eseguire la scansione di tutte le versioni precedenti, quindi selezionare **Visualizza** per visualizzare i risultati. Nella pagina **Visualizza** sono contenute le versioni precedenti del prodotto ed è possibile selezionare i prodotti da rilasciare nuovamente. Chiudere la pagina **Visualizza** e selezionare **Elabora** per rilasciare nuovamente i prodotti selezionati.
    - Rilasciare automaticamente le impostazioni nel controllo del rilascio della categoria di prodotti di progettazione. Questo rilascio può essere eseguito nell'ambito del flusso di lavoro. Quando viene utilizzato il blocco **raccogli proposta di rilascio**, la proposta di rilascio verrà compilata con le proposte di nuovi rilasci (vedere la voce di elenco precedente) e i prodotti verranno rilasciati alle aziende se la casella di controllo **Rilascio automatico** è selezionata nel controllo di rilascio della categoria di prodotti di progettazione. È possibile selezionare **Visualizza** per visualizzare i risultati, come descritto nella voce di elenco precedente. I prodotti verranno rilasciati anche quando viene utilizzato il blocco **elabora proposta di rilascio**. Se si sceglie di raccogliere solo la proposta di rilascio come parte del flusso di lavoro, è possibile avviare manualmente il rilascio selezionando **Elabora**, come descritto nella voce di elenco precedente.

## <a name="follow-up-on-an-engineering-change-request-via-an-engineering-change-order"></a>Dare seguito a una richiesta di modifica di progettazione tramite un ordine di modifica di progettazione

Non appena una richiesta di modifica di progettazione viene approvata, è possibile darvi seguito tramite un ordine di modifica di progettazione. È possibile combinare più richieste di modifica di progettazione in un unico ordine di modifica di progettazione. Un singolo ordine di modifica di progettazione può anche includere più prodotti. In genere, si utilizza questo approccio quando la stessa modifica deve essere applicata a più prodotti. Tuttavia, non è possibile creare più ordini di modifica di progettazione da una singola richiesta di modifica di progettazione.

Per dare seguito a una richiesta di modifica tramite un ordine di modifica, aprire la richiesta di modifica e quindi, nella scheda **Ordine di modifica** del riquadro azioni, nel gruppo **Ordine di modifica di progettazione** selezionare **Copia collegamento e prodotti**. È quindi possibile selezionare un ordine di modifica di progettazione esistente a cui collegare la richiesta di modifica oppure creare un nuovo ordine di modifica di progettazione per la richiesta specifica.

## <a name="engineering-change-order-report"></a>Report ordini di modifica di progettazione

I report sugli ordini di modifica di progettazione descrivono le modifiche apportate a un ordine di modifica di progettazione. Sono utili sia durante che dopo il processo di revisione e approvazione.

Per visualizzare un report sugli ordini di modifica di progettazione, aprire l'ordine di modifica rilevante, quindi, nella scheda **Ordine di modifica** del riquadro azioni, nel gruppo **Visualizza** selezionare **Report ordini di modifica di progettazione**.

## <a name="fields-on-an-engineering-change-order"></a>Campi su un ordine di modifica di progettazione

La maggior parte dei campi sugli ordini di modifica di progettazione sono gli stessi dei campi per prodotti rilasciati, versioni di progettazione, documenti, DBA (righe) e cicli di lavorazione (operazioni). Tuttavia, i campi nella tabella seguente sono univoci per modificare gli ordini.

| Campo | Descrizione |
|---|---|
| Motivi della modifica di progettazione | Selezionare il motivo della modifica per il prodotto interessato. |
| Descrizione della modifica | Immettere una descrizione della modifica. |
| Strumenti speciali richiesti | Specificare se è necessaria un'attrezzatura speciale per applicare la modifica. |
| Smaltimento del materiale di progettazione | Selezionare un codice di smaltimento materiale per qualsiasi rifiuto prodotto quando viene applicata la modifica. |
| Approvazione del cliente richiesta | Specificare se è necessaria l'approvazione del cliente prima che la modifica possa essere applicata. |
| Approvazione del cliente ricevuta | Specificare lo stato dell'approvazione del cliente. |
| Ambiente, salute e sicurezza | Specificare se le regole di salute e sicurezza ambientali sono applicabili alla modifica. Se lo sono, è possibile selezionare le regole applicabili. |

È possibile utilizzare il pulsante **Gestisci/copia informazioni di modifica** per copiare le informazioni sulle modifiche tra i prodotti interessati.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
