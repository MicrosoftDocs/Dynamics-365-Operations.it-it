--- 
title: Creare le configurazioni necessarie per importare dati da un file esterno per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare configurazioni per la creazione di report elettronici per importare dati nell'applicazione Dynamics 365 for Finance and Operations, Enterprise edition da un file esterno."
author: NickSelin
manager: AnnBe
ms.date: 02/22/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 7cdc02d147a0446d7e1f3c9a55304602774820bf
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="create-required-configurations-to-import-data-from-an-external-file-for-electronic-reporting-er"></a>Creare le configurazioni necessarie per importare dati da un file esterno per la creazione di report elettronici (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può progettare configurazioni per la creazione di report elettronici per importare dati nell'applicazione Dynamics 365 for Finance and Operations, Enterprise edition da un file esterno. In questo esempio verranno create le configurazioni ER necessarie per la società di esempio Litware, Inc. Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi nella guida attività, "ER Creare un provider di configurazione e contrassegnarlo come attivo". Tali passaggi possono essere completati mediante il set di dati USMF. È inoltre necessario scaricare e salvare i seguenti file in locale utilizzando i collegamenti dall'argomento Panoramica sui report elettronici (https://go.microsoft.com/fwlink/?linkid=852550): 1099model.xml, 1099format.xml, 1099entries.xml, 1099entries.xlsx.

    * ER consente agli utenti aziendali di configurare il processo di importazione dei file di dati esterni nelle tabelle in Dynamics 365 for Finance and Operations, Enterprise edition nel formato TXT o XML. Innanzitutto, un modello dati astratto e una configurazione del modello dati ER devono essere disponibili per rappresentare i dati da importare. Quindi, è necessario definire la struttura del file da importare e il metodo che verrà utilizzato per trasferire i dati dal file al modello dati astratto. La configurazione del formato ER che esegue il mapping al modello dati progettato deve essere creata per il modello dati astratto. Quindi, la configurazione del modello dati deve essere estesa con un mapping che descrive come i dati importati vengono resi persistenti come dati del modello dati astratto e come vengono utilizzati per aggiornare le tabelle in Dynamics 365 for Finance and Operations, Enterprise edition.  La configurazione del modello dati ER deve essere aggiunta a un nuovo mapping di modello che descrive l'associazione del modello dati alle destinazioni dell'applicazione.  
    * Il seguente scenario illustra le capacità dell'importazione di dati ER. Sono incluse le transazioni fornitore che vengono registrate esternamente e quindi vengono importate in Dynamics 365 for Finance and Operations, Enterprise edition, per essere dichiarate in seguito nella liquidazione del fornitore per i moduli 1099.   

## <a name="add-a-new-er-model-configuration"></a>Aggiungere una nuova configurazione del modello ER
1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non viene visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".   
2. Fare clic su Configurazioni report.
    * Anziché creare un nuovo modello per supportare l'importazione dati, caricare il file, 1099model.xml, scaricato in precedenza. Questo file contiene il modello dati personalizzati delle transazioni fornitore. Questo modello dati è mappato ai componenti di dati di Dynamics 365 for Finance and Operations, Enterprise edition inclusi nell'entità di dati AOT.   
3. Fare clic su Scambia.
4. Fare clic su Carica da file XML.
    * Fare clic su Sfoglia e trovare il file 1099model.xml in precedenza scaricato.  
5. Fare clic su OK.
6. Nella struttura selezionare '1099 Modello pagamenti'.

## <a name="review-data-model-settings"></a>Esaminare le impostazioni del modello dati
1. Fare clic su Progettazione.
    * Questo modello è progettato per rappresentare le transazioni dei fornitori dal punto di vista aziendale ed è separato dall'implementazione in Dynamics 365 for Finance and Operations, Enterprise edition.   
2. Nella struttura espandere '1099-MISC'.
3. Nella struttura selezionare '1099-MISC\Transazioni'.
4. Nella struttura espandere '1099-MISC\Transazioni'.
    * L'elemento Transazioni del modello rappresenta le singole transazioni. Gli elementi figlio vengono utilizzati per specificare i dettagli necessari, ad esempio il conto fornitore e la data di transazione, per ciascuna transazione.   
5. Chiudere la pagina.

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a>Aggiungere una nuova configurazione del formato ER che supporta l'importazione dati
    * I passaggi in questa sottoattività indicano come una nuova configurazione di formato può essere creata per gestire l'importazione di dati da file esterni.   
1. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
2. Nel campo Nuovo immettere 'Formato in base al modello dati 1099 Modello pagamenti'.
3. Selezionare Sì nel campo Supporta importazione dati.
4. Premere il tasto ESC per chiudere la pagina.
    * Anziché creare un nuovo formato per supportare l'importazione dati, caricare il file 1099format.xml scaricato in precedenza. Questo file contiene la struttura definita del file da importare e il mapping della struttura al modello dati personalizzati delle transazioni fornitore.   
5. Fare clic su Scambia.
6. Fare clic su Carica da file XML.
    * Fare clic su Sfoglia e trovare il file 1099format.xml in precedenza scaricato.  
7. Fare clic su OK.
8. Nella struttura espandere '1099 Modello pagamenti'.
9. Nella struttura, selezionare '1099 Modello pagamenti\Formato per importazione transazioni fornitori'.

## <a name="review-format-settings"></a>Esaminare le impostazioni di formato
1. Fare clic su Progettazione.
2. Attivare 'Mostra dettagli'.
3. Fare clic su Espandi/Comprimi.
4. Fare clic su Espandi/Comprimi.
    * Il formato progettato rappresenta la struttura prevista del file esterno. Questo file deve essere in formato XML e disporre dell'elemento radice della liquidazione. Ogni transazione fornitore è rappresentata dall'elemento transazione definito in base alla molteplicità zero a molti. Ciò significa che il file in entrata può contenere da zero a più transazioni. Gli elementi nidificati dell'elemento 'transazione' rappresentano gli attributi di una singola transazione. Tenere presente che tutti gli attributi, ad eccezione del paese, sono contrassegnati come obbligatori, ovvero è necessaria la loro presenza nel file di importazione.   

## <a name="review-the-settings-of-the-format-mapping-to-the-data-model"></a>Esaminare le impostazioni del mapping di formato al modello dati
1. Fare clic su Mapping formato a modello.
    * Il mapping ‘For importing vendors' transactions’ contiene le regole di trasferimento di dati dal file XML in entrata nella parte selezionata del modello dati personalizzati, definita selezionando la definizione 1099-MISC.  
2. Fare clic su Progettazione.
3. Attivare 'Mostra dettagli'.
4. Nella struttura espandere 'formato: Record'.
5. Nella struttura selezionare 'formato: Record'.
    * Si noti che il formato progettato è visualizzato come componente di origine dati.  
6. Nella struttura, espandere 'formato: Record\*liquidazione: Elemento XML 1..1 (liquidazione): Record'.
7. Nella struttura, espandere 'formato: Record\*liquidazione: Elemento XML 1..1 (liquidazione): Record\transazione: Elemento XML 0..* (transazione): Elenco di record'.
8. Nella struttura, espandere 'formato: Record\*liquidazione: Elemento XML 1..1 (liquidazione): Record\transazione: Elemento XML 0..* (transazione): Elenco di record\*fornitore: Elemento XML 1..1 (fornitore): Record'.
9. Nella struttura, espandere 'formato: Record\*liquidazione: Elemento XML 1..1 (liquidazione): Record\transazione: Elemento XML 0..* (transazione): Elenco di record\paese: Elemento XML 0..1 (country): Record'.
10. Nella struttura, selezionare 'formato: Record\*liquidazione: Elemento XML 1..1 (liquidazione): Record\transazione: Elemento XML 0..* (transazione): Elenco di record\*fornitore: Elemento XML 1..1 (fornitore): Record'.
    * Si noti che la presentazione di elementi di formato obbligatori e facoltativi è diversa nel componente predefinito origine dati 'formato'.  
11. Nella struttura, espandere 'Transazioni: Elenco di record= format.settlement.'$enumerated''.
    * Tenere presente che gli elementi del formato che definisce la struttura del file importato sono associati agli elementi del modello dati personalizzati. In base a queste associazioni, il contenuto del file XML importato verrà archiviato in fase di esecuzione nel modello dati esistente. Si consiglia di prestare attenzione all'associazione dell'elemento paese. Per qualsiasi elemento di transazione nel file in entrata che non ha tale elemento, il codice paese predefinito 'USA' verrà inserito nel modello dati.  
12. Fare clic sulla scheda Convalide.
    * Il mapping di formato può contenere la logica definita dall'utente per convalidare l'accuratezza dei dati importati dal punto di vista dell'azienda. Ad esempio, in base all'impostazione, per qualsiasi transazione nel file di importazione senza codice paese definito viene generato un messaggio di avviso nel Registro informazioni che informa l'utente sul caso e indica il numero progressivo della transazione.  
13. Chiudere la pagina.

## <a name="run-the-format-mapping-to-the-data-model"></a>Eseguire il mapping di formato al modello dati
    * Eseguire questo mapping di formato a scopo di verifica. Utilizzare il file 1099entries.xml in precedenza scaricato. È possibile esportare il file della cartella di lavoro 1099entries.xlsx utilizzata per gestire le transazioni fornitore. L'output generato verrà importato dal file XML selezionato per popolare il modello dati personalizzati al momento dell'importazione effettiva.  
1. Fare clic su Esegui.
    * Fare clic su Sfoglia e trovare il file 1099entries.xml in precedenza scaricato.  
2. Fare clic su OK.
    * Si noti il messaggio di avviso relativo al codice paese mancante per una transazione nel file importato.  
    * Esaminare l'output in formato XML, che rappresenta i dati che sono stati importati dal file selezionato e trasferiti nel modello dati.   
3. Chiudere la pagina.
4. Chiudere la pagina.

## <a name="review-the-settings-for-the-model-mapping-to-the-destinations"></a>Esaminare le impostazioni per il mapping di modello alle destinazioni
1. Nella struttura selezionare '1099 Modello pagamenti'.
2. Fare clic su Progettazione.
3. Fare clic su Mappa modello a origine dati.
    * Il mapping per l'importazione manuale delle transazioni 1099 è stato definito con il tipo di direzione A destinazione. Ciò significa che è stato immesso per supportare l'importazione di dati e contiene l'impostazione delle regole che definiscono come il file esterno importato e persistente come dati del modello dati astratto viene utilizzato per aggiornare le tabelle nell'applicazione Dynamics 365 for Finance and Operations, Enterprise edition.  
4. Fare clic su Progettazione.
5. Nella struttura espandere 'modello: Modello dati 1099 Modello pagamenti'.
6. Nella struttura, espandere 'modello: Modello dati 1099 Modello pagamenti\Transazioni: Elenco di record'.
    * Si noti che il modello progettato è visualizzato come elemento di origine dati. In fase di esecuzione, contiene i dati importati dal file esterno. Diverse tabelle sono state aggiunte come elementi di origine dati per assicurarsi che i dati importati siano conformi ai dati dell'applicazione corrente, ad esempio se il conto fornitore di transazione di importazione è disponibile nel sistema, se la combinazione di codici paese e stato/regione di importazione è presente e così via.  
7. Nella struttura, selezionare 'modello: Modello dati 1099 Modello pagamenti\Transazioni: Elenco di record\$failed: Campo calcolato = IF(OR(ISEMPTY(model.Transactions.'$refs'.vendor), ISEMPTY(model.Transactions.'$refs'.vendor1099), ISEMPTY(model.Transactions.'$refs'.box1099), ISEMPTY(model.Transactions.'$refs'.country), ISEMPTY(model.Transactions.'$refs'.state), ISEMPTY(model.Transactions.'$refs'.location)), true, false): Boolean'.
8. Fare clic su Modifica.
9. Fare clic su Modifica formula.
    * Quando almeno una convalida ha esito negativo per una singola transazione importata, la transazione verrà contrassegnata come errata dall'attributo di origine dati ‘$failed’.  
10. Chiudere la pagina.
11. Scegliere Annulla.
12. Nella struttura, selezionare 'tax1099trans: Tabella 'VendSettlementTax1099' record= model.Validated'.
13. Fare clic su Modifica destinazione.
    * La destinazione ER è stata aggiunta per specificare come i dati importati aggiorneranno le tabelle dell'applicazione. In questo caso, la tabella dati VendSettlementTax1099 è stata selezionata. Poiché l'azione di record Inserisci è selezionata, le transazioni importate verranno inserite nella tabella VendSettlementTax1099. Tenere presente che un singolo mapping modello può contenere più destinazioni. Ciò significa che i dati importati possono essere utilizzati per aggiornare più tabelle dell'applicazione contemporaneamente. Le tabelle, le viste e le entità di dati possono essere utilizzate come destinazioni ER.   
    * Se il mapping verrà chiamato da un punto dell'applicazione Dynamics 365 for Finance and Operations, Enterprise edition (ad esempio un pulsante o una voce di menu), progettato specificatamente per questa azione, la destinazione ER deve essere contrassegnata come punto di integrazione. In questo esempio il punto è ERTableDestination#VendSettlementTax1099.  
14. Scegliere Annulla.
15. Fare clic su Mostra tutto.
16. Fare clic su Mostra solo non mappati.
17. Nella struttura, espandere 'tax1099trans: Tabella 'VendSettlementTax1099' record= model.Validated'.
    * Si noti che l'elemento di origine dati contenente le sole transazioni convalidate è associato alla destinazione creata. È possibile filtrare le transazioni importate per ignorare queste che sono incompatibili con i dati delle applicazioni.  
18. Nella struttura, selezionare 'operazione non riuscita: Tabella 'VendSettlementTax1099Entity' record= model.Failed'.
19. Fare clic sulla scheda Convalide.
    * Il mapping di modello può contenere la logica definita dall'utente per convalidare la correttezza dei dati importati dai dati dell'applicazione esistenti. Ad esempio, in base all'impostazione attuale, per qualsiasi transazione nel file importato con un conto fornitore che non è nel sistema, viene generato un messaggio di avviso nel Registro informazioni che informa l'utente sul caso e indica il codice conto fornitore non corretto.  
    * Tenere presente che l'opzione Azione post-convalida può essere utilizzata per ogni convalida, per specificare se il processo di importazione deve essere eseguito o interrotto nonché se gli inserimenti/aggiornamenti già eseguiti possono essere mantenuti o sottoposti a rollback.  
20. Fare clic su Mostra solo non mappati.
21. Fare clic su Mostra tutto.
22. Chiudere la pagina.
    * Eseguire il mapping di modello per provare i mapping di modello e formato progettati. Utilizzare il file 1099entries.xml. I dati del file selezionato verranno importati nel sistema.  
23. Fare clic su Esegui.
    * Si noti che la finestra di dialogo non contiene domande aggiuntive sul mapping di formato da utilizzare per analizzare il file importato e quindi trasferire i dati nel modello dati. Questo accade perché attualmente un solo formato utilizza il modello, che viene contrassegnato come progettato per supportare l'importazione di dati.  
    * Definire l'ID giustificativo per distinguere le transazioni importate da altre transazioni che potrebbero essere già stati immessi manualmente o importati.  
24. Nel campo Immetti ID giustificativo, digitare 'IMPORT-001'.
    * Esplorare per trovare il file '1099entries.xml'.  
25. Fare clic su OK.
    * L'elenco degli avvisi generati fornisce informazioni sui conti fornitore errati, un codice casella 1099 d'imposta errato, i codici paese mancanti e così via. Confrontare l'elenco degli avvisi al contenuto incluso nel file XML di esecuzione.  
26. Chiudere la pagina.
27. Chiudere la pagina.
28. Chiudere la pagina.
29. Chiudere la pagina.
30. Passare a Contabilità fornitori > Attività periodiche > Imposta 1099 > Liquidazione fornitore per i moduli 1099.
    * In questo modulo vengono visualizzate le transazioni cumulative nella tabella Tax1099Summary creata in base alle transazioni importate.  
31. Nel campo Data iniziale impostare la data su "01-01-2000".
32. Fare clic su Transazioni 1099 manuali.
    * Questo modulo contiene l'elenco delle transazioni aggiunte manualmente e quelle solo importate.  
33. Aprire filtro di colonna Giustificativo.
34. Immettere il valore di filtro "IMPORT-001" nel campo "Giustificativo" utilizzando l'operatore di filtro "inizia con".

## <a name="review-the-relationship-between-model-and-format-mappings"></a>Esaminare la relazione tra il modello e i mapping di formato
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
4. Fare clic su Configurazioni report.
5. Nella struttura selezionare '1099 Modello pagamenti'.
    * Si supponga che si desideri supportare l'importazione degli stessi dati ma da un formato di file TXT.   
6. Fare clic su Crea configurazione per aprire la finestra di dialogo. 
7. Nel campo Nuovo immettere 'Formato in base al modello dati 1099 Modello pagamenti'.
8. Digitare 'Importare dati da file TXT' nel campo Nome.
9. Selezionare Sì nel campo Supporta importazione dati.
10. Fare clic su Crea configurazione.
11. Fare clic su Progettazione.
12. Fare clic su Mapping formato a modello.
13. Fare clic su Nuovo.
14. Nel campo Definizione immettere o selezionare un valore.
    * Selezionare l'opzione '1099-MISC'.  
15. Digitare 'Importare dati da file TXT' nel campo Nome.
16. Digitare 'Importare dati da file TXT' nel campo Descrizione.
17. Fare clic su Salva.
18. Chiudere la pagina.
19. Chiudere la pagina.
20. Fare clic su Modifica.
    * Se è stato installato l'hotfix "KB 4012871 Supporto dei mapping di modello GER in configurazioni separate con la possibilità di specificare diversi tipi di prerequisiti per la distribuzione in diverse versioni di Dynamics 365 for Finance and Operations, Enterprise edition" (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871), eseguire il passaggio successivo "Attivare il flag 'Impostazione predefinita per mapping di modello'" per la configurazione di formato immessa. In caso contrario ignorare il passaggio successivo.  
21. Selezionare Sì nel campo Impostazione predefinita per mapping di modello.
22. Nella struttura selezionare '1099 Modello pagamenti'.
23. Fare clic su Progettazione.
24. Fare clic su Mappa modello a origine dati.
25. Fare clic su Esegui.
    * Se è stato installato l'hotfix KB 4012871 Supporto dei mapping di modello GER in configurazioni separate con la possibilità di specificare diversi tipi di prerequisiti per la distribuzione in diverse versioni di Dynamics 365 for Finance and Operations, Enterprise edition (https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871), selezionare il mapping di modello preferito nel campo di ricerca. Se non è stato ancora installato l'hotfix, ignorare il passaggio successivo perché il mapping è già stato selezionato dalla definizione della configurazione di formato predefinita.  
    * Se non è stato installato l'hotfix KB 4012871, notare che la finestra di dialogo contiene una domanda di mapping di modello aggiuntiva utilizzata per analizzare il file da importare. I dati quindi vengono trasferiti dalla finestra di dialogo nel modello dati. Attualmente, è possibile scegliere il formato di mapping che deve essere utilizzato in base al tipo di file che si prevede di importare.  
    * Se si prevede di chiamare il mapping di modello da un punto di Dynamics 365 for Finance and Operations, Enterprise edition, progettato appositamente per l'azione, la destinazione ER e il mapping di formato devono essere contrassegnati come parte dell'integrazione.  
26. Scegliere Annulla.
27. Chiudere la pagina.
28. Chiudere la pagina.


