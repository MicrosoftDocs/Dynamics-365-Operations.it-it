---
title: Esaminare le informazioni sulla riscossione
description: In questa argomento vengono descritti i passaggi per esaminare le informazioni sulla riscossione nonché le varie opzioni di impostazione e le transazioni di riscossione.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustCollectionsPool, SysQueryForm, CustCollectionsAgent, OMTeamSelectMemberDialog, CustVendReportInterval, CustParameters, CustAgingSnapshot, CustVendAgingBucketLookUp, CustCollectionsPoolsListPage, CustCollectionsContactPart, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9bbfb6537118a9936c127018427b0516e7ea002a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971530"
---
# <a name="review-collections-information"></a>Esaminare le informazioni sulla riscossione

[!include [banner](../../includes/banner.md)]

In questa argomento vengono descritti i passaggi per esaminare le informazioni sulla riscossione nonché le varie opzioni di impostazione e le transazioni di riscossione. Questa procedura utilizza la società dimostrativa USMF.

## <a name="create-customer-pools"></a>Creare pool di clienti
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione > Pool di clienti**.
- Utilizzare questa pagina per impostare pool di clienti, ovvero query che definiscono un gruppo di conti cliente che possono essere visualizzati e gestiti per i processi di riscossione o di aging. Utilizzare i pool di clienti per filtrare le informazioni presenti nella pagina elenco **Riscossioni** e nelle pagine elenco correlate. È possibile utilizzare i pool di clienti per filtrare i conti cliente inclusi quando vengono creati gli snapshot di aging.  
- È possibile utilizzare i pool di clienti per filtrare i conti cliente inclusi quando vengono creati gli snapshot di aging.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **ID pool**.
4. Nel campo **Descrizione pool**, immettere un valore.
5. Fare clic su **Seleziona criteri pool**.
6. Digitare un valore nel campo **Criteri**.
7. Selezionare **OK**.
8. Selezionare **Anteprima pool di clienti**.

## <a name="create-collections-agents"></a>Creare agenti di riscossione
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione > Agenti di riscossione**.  
- Utilizzare questa pagina per impostare i lavoratori come agenti di riscossione e facoltativamente assegnare loro pool di clienti. Un *agente di riscossione* è una persona che lavora con i clienti per accertarsi che i pagamenti vengano riscossi con puntualità.  
- Gli agenti di riscossione impostati in questa pagina vengono aggiunti automaticamente a un team di riscossione. Se un team è selezionato nel campo **Team** della pagina **Parametri contabilità clienti**, gli agenti di riscossione vengono aggiunti a tale team. Se non è selezionato alcun team, viene creato automaticamente un nuovo team denominato Riscossioni e gli agenti di riscossione vengono aggiunti a tale team.  
2. Selezionare l'agente desiderato, quindi selezionare **Aggiungi** nella pagina.
3. Nel campo **ID pool** fare clic sul record desiderato del menu a discesa.
4. Selezionare o deselezionare la casella di controllo **Pool predefinito**.
- Selezionare questa opzione per includere tutti i pool di clienti negli elenchi di filtri per l'agente di recupero crediti selezionato. Se questa opzione non è selezionata, negli elenchi di filtri sono disponibili solo i pool di clienti assegnati all'agente di recupero crediti.  

## <a name="create-aging-period-definition"></a>Creare la definizione del periodo di aging
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione > Definizioni periodo di aging**.
- Utilizzando le definizioni di periodo di aging, è possibile analizzare le scadenze dei conti cliente e fornitore in base a una data immessa. Ciascun periodo di aging impostato per la definizione del periodo di aging corrisponde a una colonna nella pagina elenco, nel modulo o nel report quando viene eseguita l'analisi.  
2. Selezionare **Nuovo**.
3. Nel campo **Definizione periodo di aging**, digitare un valore.
4. Digitare un valore nel campo **Descrizione**
- Consente di specificare l'intervallo, l'unità e il nome per ciascun periodo di aging da includere nella definizione del periodo di aging. La riga per cui è specificato 0 (zero) nel campo Unità rappresenta la data in cui viene eseguita l'analisi. Per impostazione predefinita, nel campo Unità delle righe che precedono lo zero è presente il valore -1, mentre quello delle righe che seguono lo zero è impostato su 1. È possibile modificare tali valori. Selezionare **Su** e **Giù** per riorganizzare le righe. La riga zero non può essere spostata.  
- Spostare il puntatore del mouse nella posizione in cui si desidera inserire una nuova riga, quindi fare clic su **Aggiungi**.  
- Selezionare un indicatore per rappresentare il periodo di aging nel modulo e nella pagina elenco  **Riscossioni**. È possibile, ad esempio, selezionare un indicatore verde per il periodo corrente, un indicatore giallo per un periodo di 30 giorni precedenti e un indicatore rosso per un periodo di 90 giorni precedenti.  
- Consente di selezionare la direzione di stampa per la definizione del periodo di aging. Questa selezione determina l'ordine di visualizzazione delle colonne in Report di aging clienti o Report di aging fornitori.  
  - Avanti : consente di stampare le colonne nello stesso ordine in cui le intestazioni vengono visualizzate nella tabella, a partire dalla prima riga.  
  - Indietro: consente di stampare le colonne nell'ordine inverso rispetto a quello con cui le intestazioni vengono visualizzate nella tabella, a partire dall'ultima riga.    

## <a name="setup-collections-parameters"></a>Impostare i parametri di riscossione
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Impostazione > Parametri contabilità clienti**.
2. Selezionare la scheda **Riscossioni**.
3. Espandere o comprimere la sezione **Valori predefiniti riscossioni**.
- Selezionare una definizione del periodo di aging per lo snapshot di aging predefinito da utilizzare nel modulo **Riscossioni**.  
- Selezionare un team a cui vengono assegnati gli agenti di riscossione nel modulo **Agente di riscossione**. Nell'elenco vengono visualizzati solo i team il cui tipo è Riscossioni.  
4. Espandere o comprimere la sezione **Annullamento**
- Selezionare il nome del giornale di registrazione, impostato per i giornali di registrazione contabili giornalieri, da utilizzare in caso di annullamento di una transazione mediante il modulo **Riscossioni** o le pagine elenco correlate.  
- Selezionare il codice motivo predefinito da utilizzare quando vengono create le transazioni di annullamento mediante il modulo **Riscossioni** o le pagine elenco correlate.  
- Selezionare questa opzioni per creare una riga del giornale di registrazione separata per gli importi IVA quando vengono create le transazioni di annullamento utilizzando la pagina **Riscossioni** o le pagine elenco correlate. Se si seleziona questa opzione, è possibile tenere facilmente traccia degli importi IVA inclusi nelle transazioni di annullamento. È possibile tenere traccia degli importi IVA separatamente per facilitare la rettifica della passività IVA per il periodo interessato.  
5. Espandere o comprimere la sezione **Modello di messaggio di posta elettronica**
- Selezionare il modello di messaggio di posta elettronica da utilizzare quando si invia un messaggio di posta elettronica mediante l'azione **Posta elettronica > Transazioni** a contatto inclusa nel modulo **Riscossioni**.  
- Selezionare il modello di messaggio di posta elettronica da utilizzare per l'invio di un rendiconto cliente come allegato a un messaggio di posta elettronica mediante l'azione **Posta elettronica > Rendiconto** a contatto inclusa nel modulo **Riscossioni**.  
- Selezionare il modello di messaggio di posta elettronica mediante l'azione **Posta elettronica > Transazioni** a venditore inclusa nel modulo **Riscossioni**.  

## <a name="age-customer-balance"></a>Saldo con aging cliente
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Attività periodiche > Saldi con aging cliente**.
- Consente di selezionare una definizione del periodo di aging. L'aging delle transazioni viene eseguito dal processo dello snapshot di aging, in base ai periodi di aging specificati nella definizione del periodo di aging selezionata.  
- Selezionare un pool di clienti o lasciare vuoto il campo per creare uno snapshot di aging per tutti i clienti. Se viene selezionato un pool di clienti, il processo dello snapshot di aging viene applicato solo ai conti cliente appartenenti a tale pool di clienti. Il pool di clienti selezionato deve essere di tipo Snapshot di aging.  
- Selezionare il tipo di data su cui basare lo snapshot di aging.  
  - Data della transazione: esegue l'aging di ogni transazione in base alla relativa data.    
  - Data di scadenza: esegue l'aging di ogni transazione in base alla relativa data di scadenza.    
  - Data documento: esegue l'aging di ogni transazione in base alla relativa data del documento.  
- Selezionare la data da utilizzare come data corrente per lo snapshot di aging. I periodi di aging vengono calcolati in base a tale data.    
  - Data odierna: viene utilizzata la data di sistema. Utilizzare questa opzione se si è impostata l'esecuzione dell'elaborazione in un batch ricorrente. Se si utilizza tale data, è possibile eseguire il batch ricorrente periodicamente utilizzando la data di sistema corrente.    
  - Data selezionata: viene utilizzata una data specificata dall'utente. Se si seleziona questa opzione, immettere una data di aging.  
2. Selezionare **OK**.

## <a name="view-aged-customer-balances"></a>Visualizzare i saldi con aging cliente
1. Nel pannello di navigazione andare a **Moduli > Crediti e riscossioni > Riscossioni > Saldi con aging**.
- Utilizzare questa pagina elenco per visualizzare i saldi dei clienti e gli importi con aging in base al periodo di aging. Tali informazioni vengono archiviate in uno snapshot di aging. I periodi di aging vengono determinati dalla definizione del periodo di aging utilizzata. La definizione del periodo di aging viene ricavata dal pool di clienti, se ne è stato specificato uno per la query sul pool. Se il pool di clienti non contiene una definizione del periodo di aging, viene utilizzata la definizione del periodo di aging predefinita specificata nel modulo Parametri contabilità clienti.  
2. Espandi il riquadro Dettaglio informazioni **Contatto** Ecco come visualizzare le informazioni di contatto:
- Contatto di riscossioni per il cliente.  
- Venditore predefinito per il cliente.  
3. Espandere il riquadro Dettaglio informazioni **Limite di credito**
- Utilizzare il riquadro Dettaglio informazioni **Informazioni crediti** per visualizzare le informazioni relative al saldo corrente e al limite di credito del cliente.  

## <a name="view-customer-collections-details"></a>Visualizzare i dettagli riscossioni cliente
1. Verificare che il record desiderato sia selezionato.
2. Espandere i riquadri Dettaglio informazioni **Indirizzo**, **Contatto**, **Aging** e **Limite di credito** per visualizzare le informazioni fornite.
3. Nel riquadro azioni fare clic su **Raccogli**.
- Consente di aggiornare lo snapshot di aging del cliente, utilizzando la data corrente come data di aging con cui vengono confrontate le date delle transazioni. Se lo snapshot di aging contiene informazioni relative a più persone giuridiche, lo snapshot di aging aggiornato conterrà informazioni per lo stesso gruppo di persone giuridiche. Gli importi vengono archiviati nella valuta di contabilizzazione della persona giuridica a cui si è connessi al momento dell'aggiornamento dello snapshot di aging.  
- Consente di selezionare una definizione del periodo di aging. Per impostazione predefinita, viene visualizzata la definizione del periodo di aging associata allo snapshot di aging per il cliente. La definizione del periodo di aging regola i periodi di aging e gli importi visualizzati nei riquadri Dettaglio informazioni **Saldi con aging** e **Informazioni crediti**.  
- Aprire un menu contenente le opzioni riportate di seguito:    
  - Società: visualizza gli importi nei riquadri Dettaglio informazioni Saldi con aging e Informazioni crediti nella valuta di contabilizzazione della persona giuridica.  
  - Cliente: visualizza gli importi nei riquadri Dettaglio informazioni Saldi con aging e Informazioni crediti nella valuta del cliente.  
- Consente di selezionare una o più persone giuridiche nello snapshot di aging del cliente di cui visualizzare le informazioni. Le persone giuridiche visualizzate nell'elenco sono state selezionate alla creazione dello snapshot di aging.  
- Consente di visualizzare il rendiconto del cliente in formato Microsoft Excel. È possibile selezionare una data di inizio per l'intervallo di transazioni da includere nel rendiconto e decidere se includere solo le transazioni aperte o sia quelle aperte che quelle liquidate. Se lo snapshot di aging contiene informazioni relative a più persone giuridiche, vengono incluse le transazioni per tutte le persone giuridiche.  
- Aprire il modulo **Documenti** in cui è possibile creare o modificare documenti o note.  
4. Nel riquadro azioni fare clic su **Comunica**  
- Consente di aprire Outlook, da cui è possibile inviare un messaggio di posta elettronica al contatto specificato nel campo Contatto. Se non è stato specificato un contatto per la riscossione, verrà utilizzato l'indirizzo principale del cliente. Se non è stato specificato un contatto principale, i messaggi di posta elettronica verranno inviati al primo indirizzo elencato nel modulo **Contatti**. Le transazioni selezionate vengono incluse come allegato. L'allegato è in formato Excel e contiene tre fogli di lavoro. È possibile specificare un modello di messaggio di posta elettronica per i messaggi ai contatti del cliente nel modulo **Parametri contabilità clienti**.  
- Il pulsante non è disponibile se il contatto selezionato in questo modulo non dispone di un indirizzo di posta elettronica impostato.  
- Preparare un rendiconto e aprire Outlook, da cui è possibile inviare un messaggio di posta elettronica con rendiconto allegato all'indirizzo specificato nel campo **Contatto**. Se non è stato specificato un contatto per la riscossione, verrà utilizzato l'indirizzo principale del cliente. Se non è stato specificato un contatto principale, i messaggi di posta elettronica verranno inviati al primo indirizzo elencato nel modulo **Contatti**.  
- Il pulsante non è disponibile se il contatto selezionato in questo modulo non dispone di un indirizzo di posta elettronica impostato.  
- Consente di aprire Outlook, da cui è possibile inviare un messaggio di posta elettronica al dipendente specificato come rappresentante per il gruppo vendite assegnato al cliente. Le eventuali transazioni selezionate vengono incluse come allegato. L'allegato è in formato Excel e contiene due fogli di lavoro. È possibile specificare un modello di messaggio di posta elettronica per i messaggi ai venditori nel modulo **Parametri contabilità clienti**.  
- Il pulsante non è disponibile se il venditore visualizzato in questo modulo non dispone di un indirizzo di posta elettronica impostato.  
- Visualizzare ed eseguire azioni sulle transazioni per il cliente. Se si utilizzano pagamenti centralizzati, vengono incluse le informazioni relative a tutte le persone giuridiche incluse nello snapshot di aging del cliente. È possibile limitare le informazioni sulle persone giuridiche mediante il pulsante **Società** nel gruppo **Seleziona** del riquadro azioni.  
- Consente di modificare lo stato delle riscossioni per le transazioni selezionate.    
  - Non in controversia: non è stata eseguita alcuna azione di riscossione per la transazione.    
  - In controversia: il cliente ha notificato la presenza di un problema con la transazione.    
  - Promessa di pagamento: il cliente ha accettato di effettuare il pagamento dell'importo della transazione.    
  - Risolta: tutti i problemi con la transazione sono stati risolti e non sono necessarie ulteriori azioni di riscossione.  
- Consente di aprire un menu e selezionare una delle seguenti opzioni per specificare le transazioni da visualizzare in questo modulo:    
  - Aperto: visualizza solo le transazioni non ancora liquidate.    
  - Aperto e chiuso: visualizza tutte le transazioni, liquidate o meno.  
- Consente di elaborare il pagamento selezionato come pagamento NSF (Non Sufficient Funds, senza copertura).    
  - Questo pulsante è disponibile solo se la transazione selezionata è un pagamento (saldo in Avere senza fattura) registrato in un giornale di registrazione pagamenti, alla transazione viene assegnato un conto bancario e il pagamento non è stato precedentemente annullato.  
- Consente di annullare le transazioni selezionate.  
- Consente di contrassegnare le transazioni selezionate in modo che si liquidino a vicenda.  
- Consente di aprire il modulo **Documento originale**, in cui è possibile visualizzare e stampare il documento per la transazione selezionata.  
- Aprire un **menu** contenente le opzioni riportate di seguito:    
  - Riscossioni: visualizza solo le attività create nel modulo Riscossioni.    
  - Tutto: visualizza tutte le attività del cliente, indipendentemente da dove sono state create.  
- Aprire un **menu** contenente le opzioni riportate di seguito:    
  - Aperto: consente di visualizzare solo le attività non ancora chiuse,    
  - Aperto e chiuso: visualizza tutte le attività, indipendentemente dallo stato.  
- Consente di selezionare un caso di riscossione assegnato al cliente o lasciare vuoto il campo. Se viene selezionato un caso, solo le transazioni e le attività associate al caso vengono visualizzate in questo modulo.  
5. Selezionare **Mostra elenco**.
- Consente di selezionare un conto cliente o accettare il valore predefinito. Per impostazione predefinita, si tratta del conto cliente selezionato nella pagina elenco o nel modulo da cui è stato aperto il modulo. Se il modulo è stato aperto da una pagina elenco, i clienti nell'elenco sono quelli inclusi nel pool di riscossioni utilizzato nella pagina elenco.  

