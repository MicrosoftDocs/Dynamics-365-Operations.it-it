---
title: Panoramica dei criteri di acquisto
description: Questo articolo fornisce informazioni sui criteri di acquisto. I criteri di acquisto rappresentano raccolte di regole per il controllo del processo di richiesta di acquisto. I criteri di acquisto consentono agli amministratori di approvvigionamento di implementare la strategia di approvvigionamento creando una struttura di criteri in linea con le esigenze per gli acquisti strategici dell'organizzazione.
author: mkirknel
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchReqSourcingPolicyRule, SysPolicy, SysPolicyListPage, PurchReqControlRule, RequisitionReplenishCatAccessPolicyRule, PurchReApprovalPolicyRule, RequisitionReplenishControlRule, PurchReqControlRFQRule
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 11614
ms.assetid: 729a304d-0f3f-4ccb-bd5b-46ee0976c57f
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 00200bc79f83e9d072ff8220c89a6aaa70cb07a5
ms.sourcegitcommit: 827d77c638555396b32d36af5d22d1b61dafb0e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "4431582"
---
# <a name="purchasing-policies-overview"></a>Panoramica dei criteri di acquisto

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui criteri di acquisto. I criteri di acquisto rappresentano raccolte di regole per il controllo del processo di richiesta di acquisto. I criteri di acquisto consentono agli amministratori di approvvigionamento di implementare la strategia di approvvigionamento creando una struttura di criteri in linea con le esigenze per gli acquisti strategici dell'organizzazione.

I criteri di acquisto sono sostituiti da un insieme di regole dei criteri. Quando si definisce una regola dei criteri, è necessario selezionare innanzitutto un tipo di regola. Si crea quindi una regola per il tipo di regola definendo le relative impostazioni, la data di inizio e la data di fine.  

Ad esempio, un amministratore crea un criterio, seleziona il tipo di regola **Criteri di catalogo**, quindi aggiunge ai criteri una regola dei criteri del catalogo, nella quale viene specificato che per l'approvvigionamento interno deve essere utilizzato il catalogo Adventure. Dopo l'associazione dei criteri di acquisto a una particolare organizzazione, i relativi dipendenti potranno visualizzare il catalogo Adventure per creare le richieste di approvvigionamento.

## <a name="assigning-policies-to-organizations"></a>Assegnazione di criteri alle organizzazioni
Prima che i criteri diventino effettivi, è necessario associarli a un'organizzazione. I criteri di acquisto vengono associati allo scopo gerarchia **Controllo interno approvvigionamento**. Di conseguenza, i criteri di acquisto sono applicabili solo alle organizzazioni appartenenti a gerarchie il cui scopo è **Controllo interno approvvigionamento**. È inoltre possibile selezionare organizzazioni dall'elenco di persone giuridiche nella tabella CompanyInfo. Tali persone giuridiche vengono designate nel framework dei criteri come "Società".

## <a name="determining-which-rule-to-apply"></a>Determinazione della regola da applicare
A seconda della modalità di configurazione dei criteri di acquisto, gli utenti di un'organizzazione potrebbero essere interessati da più regole. Negli esempi seguenti vengono illustrate varie modalità di configurazione dei criteri di acquisto e viene descritto come si applicano i criteri quando si verifica una transazione.

### <a name="example-1-simple-purchasing-policy-configuration"></a>Esempio 1: configurazione semplice dei criteri di acquisto

Le organizzazioni di piccole dimensioni e meno complesse possono impostare i criteri di acquisto in base alla persona giuridica e possono utilizzare solo la gerarchia organizzativa Società.  

Per Fabrikam, un'azienda di piccole dimensioni, le esigenze di acquisto a livello di organizzazione variano poco. Le regole di acquisto variano solo tra le persone giuridiche dell'organizzazione. Ad esempio, i dipendenti di Fabrikam Canada e quelli di Fabrikam negli Stati Uniti acquistano prodotti e servizi da cataloghi e fornitori diversi. Di conseguenza, Fabrikam imposta i criteri di acquisto a livello di persona giuridica.  

Fabrikam crea due criteri di acquisto. I criteri A vengono applicati alla persona giuridica 1111 negli Stati Uniti. I criteri B vengono applicati alla persona giuridica 2222 in Canada. Quando un dipendente nella persona giuridica 1111 crea una richiesta di acquisto, le regole dei criteri vengono ricavate dai criteri A. Ad esempio, il catalogo prodotti visualizzato dal dipendente è specificato nella regola dei criteri dei criteri A.  

Quando un dipendente nella persona giuridica 2222 crea una richiesta di acquisto, le regole dei criteri vengono ricavate dai criteri B.  

**Nota:** Se un dipendente nella persona giuridica 1111 acquista un articolo per conto di un dipendente nella persona giuridica 2222, vengono applicate le regole dei criteri specificate per la persona giuridica 2222 (cioè le regole dei criteri dai criteri B).

### <a name="example-2-complex-purchasing-policy-configuration"></a>Esempio 2: configurazione complessa dei criteri di acquisto

Nell'esempio precedente tutte le regole di acquisto vengono definite in un'unica gerarchia organizzativa, nel caso specifico nella gerarchia organizzativa Società. In un'organizzazione complessa invece è possibile che vengano definiti criteri per più gerarchie organizzative.  


Contoso è una grande società che richiede regole di acquisto complesse per il controllo del processo di richiesta di acquisto. Contoso ha definito le regole per due diverse gerarchie organizzative: Reparto e Controllo acquisti globale.  

I criteri 123 sono definiti per la gerarchia organizzativa Reparto per il reparto Regno Unito - Vendite. Nei criteri 123, la regola Controllo richiesta di acquisto specifica la necessità di imporre delle restrizioni sulle quantità minime degli ordini. In questa regola, l'opzione **Applica restrizioni quantità ordine minima** è selezionata.  

I criteri 456 sono definiti per la gerarchia organizzativa Controllo acquisti globale per il reparto Vendite e marketing. Nei criteri 456 la regola Controllo richiesta di acquisto non specifica che devono essere applicate restrizioni sulle quantità minime degli ordini. In questa regola, l'opzione **Applica restrizioni quantità ordine minima** è deselezionata.  

Sam lavora nel reparto Vendite Regno Unito - Vendite presso l'ufficio di Contoso nel Regno Unito. I criteri per entrambe le gerarchie organizzative Reparto e Controllo acquisti globale sono applicabili al reparto di Sam. Quando Sam crea una richiesta di acquisto, nel sistema devono essere determinati i criteri da applicare. L'amministratore di sistema imposta i parametri dei criteri di acquisto specificando che tali criteri devono essere applicati nel seguente ordine di precedenza:

1.  Controllo acquisti globale
2.  Reparto
3.  Società

Di conseguenza, i criteri 456 vengono applicati alla richiesta di acquisto che Sam crea e non è richiesta alcuna quantità ordine minima per la richiesta di acquisto.

## <a name="policy-rules"></a>Regole dei criteri
### <a name="catalog-policy-rule"></a>Regola dei criteri di catalogo

La regola dei criteri di catalogo determina quali utenti del catalogo di approvvigionamento vedono quando creano richieste di acquisto. Se un utente dispone delle autorizzazioni necessarie per ordinare prodotti per conto di altri utenti, la richiesta utilizza la regola dei criteri del catalogo che è definita per la persona giuridica e l'unità operativa del richiedente per determinare il catalogo da visualizzare. Prima di poter definire una regola dei criteri di catalogo, è necessario creare e pubblicare un catalogo di approvvigionamento.

### <a name="category-access-policy-rule"></a>Regola dei criteri di accesso alle categorie

La regola dei criteri di accesso alle categorie determina le categorie a cui gli utenti hanno accesso quando creano richieste di acquisto. Se non è specificata alcuna regola, sarà possibile aggiungere alla richiesta di acquisto tutte le categorie di approvvigionamento.

1.  Selezionare l'opzione **Includi regola padre** per applicare alla categoria la regola dei criteri di accesso alle categorie dell'organizzazione padre.
2.  Nel riquadro **Categorie disponibili** selezionare le categorie a cui si applica la regola. Quando si seleziona una categoria, tutte le categorie di livello più elevato nella gerarchia vengono aggiunte all'elenco **Categorie selezionate**.
3.  Selezionare l'opzione **Includi sottocategorie** per applicare la regola a tutte le sottocategorie della categoria selezionata.

### <a name="category-policy-rule"></a>Regola dei criteri categorie

La regola dei criteri categorie definisce il modo in cui gli utenti possono selezionare i fornitori per ogni categoria. Definisce inoltre i requisiti per i processi di ricezione e di fatturazione.

### <a name="re-approval-rule-for-purchase-orders"></a>Regola di riapprovazione per gli ordini fornitore

La regola di riapprovazione è una regola facoltativa che definisce i criteri per richiedere la riapprovazione quando vengono apportate modifiche a un ordine acquisto. I campi selezionati vengono valutati nel flusso di lavoro dell'ordine acquisto quando la condizione "Riapprovazione dell'ordine fornitore richiesta" è impostata nel flusso di lavoro.

> [!NOTE]
> La distribuzione contabile viene sempre reimpostata quando viene modificato un ordine fornitore approvato con la gestione modifiche attivata. È pertanto necessario tenere presente che per evitare una nuova approvazione di un ordine fornitore quando determinati campi vengono modificati, il campo Distribuzione contabile modificato NON deve essere incluso come campo selezionato per rieseguire l'approvazione. 

### <a name="purchase-requisition-rfq-rule"></a>Regola RdO richiesta di acquisto

La regola RdO richiesta di acquisto definisce i criteri per la richiesta di una richiesta di offerta (RdO) per una riga della richiesta di acquisto. Se una riga soddisfa le condizioni, nella riga della richiesta appare il timbro di richiesta di offerta informale o richiesta di offerta formale.

### <a name="purchase-requisition-control-rule"></a>Regola di controllo richiesta di acquisto

La regola di controllo della richiesta di acquisto per le richieste di tipo **consumo** è una regola facoltativa. Quando si creano regole di questo tipo, è possibile impostare delle opzioni nelle varie schede:

-   Nella scheda **Invio flusso di lavoro**, è possibile configurare i campi che devono essere immessi nella riga di richiesta affinché la richiesta venga inviata per l'approvazione.
-   Nella scheda **Quantità ordine** è possibile configurare i campi che sono obbligatori nella richiesta di acquisto in determinate situazioni. È inoltre possibile imporre le quantità ordine.
-   Nella scheda **Date** è possibile configurare se la data di registrazione è uguale alla data richiesta.
-   Nella scheda **Indirizzo** è possibile definire se all'utente è permesso creare nuovi indirizzi nel sistema da applicare alla richiesta di acquisto.

### <a name="requisition-purpose-rule"></a>Regola scopo richiesta

La regola scopo richiesta è una regola facoltativa che determina il tipo di scopo richiesta consentito per una persona giuridica specifica. Se non diversamente indicato nella regola, le richieste, nel momento in cui vengono create, hanno automaticamente lo scopo **Consumo**.

### <a name="replenishment-category-access-policy-rule"></a>Regola dei criteri di accesso alle categorie di rifornimento

La regola dei criteri di accesso alle categorie di rifornimento regola facoltativa che determina i prodotti disponibili per soddisfare la domanda della richiesta di acquisto per una persona giuridica specifica quando lo scopo della richiesta è **Rifornimento**.

### <a name="replenishment-control-rule"></a>Regola di controllo rifornimento

La regola di controllo rifornimento è una regola facoltativa che definisce i campi che devono essere immessi nella riga di richiesta affinché la richiesta sia inviata per l'approvazione quando lo scopo richiesta è **Rifornimento**.

### <a name="purchase-order-creation-and-demand-consolidation-rule"></a>Regola di consolidamento domanda e creazione ordini fornitore

La regola di consolidamento domanda e creazione ordini fornitore definisce le regole dei criteri da utilizzare quando viene generato un ordine fornitore da una richiesta di acquisto approvata. Quando si creano regole di questo tipo, è possibile impostare delle opzioni nelle varie schede:

-   Nella scheda **Divisione ordine fornitore** è possibile definire i criteri per dividere le righe di richiesta di acquisto in ordini acquisto distinti.
-   Nella scheda **Trasferimento prezzi/sconti** è possibile definire quando ricalcolare l'accordo sul prezzo durante la creazione di un ordine acquisto:
    -   **Solo se non è presente alcun accordo commerciale**: I prezzi e gli sconti vengono trasferiti dalla richiesta di acquisto solo se non è presente un accordo commerciale o un prezzo di base applicabile. Se esiste un accordo commerciale o un prezzo di base per l'articolo o il fornitore, i prezzi e gli sconti vengono ricalcolati in base all'accordo commerciale o al prezzo di base e vengono applicati all'ordine acquisto. Salvo diversamente specificato, questo è il comportamento predefinito.
    -   **Sempre**: i prezzi e gli sconti vengono trasferiti sempre dalla richiesta di acquisto.

    È inoltre possibile consentire al richiedente di modificare il metodo di trasferimento dello sconto e del prezzo per le singole righe di acquisto, indipendentemente dalla regola di trasferimento sconto/prezzo definita. Selezionare l'opzione **Consenti forzatura manuale per la riga richiesta di acquisto** per attivare questa funzionalità.
-   Nella scheda **Trasferimento descrizione articolo** è possibile trasferire la descrizione dell'articolo dalla richiesta quando viene originata da una RdO.
-   Nella scheda **Tolleranza prezzi** è possibile definire le regole per instradare di nuovo le richieste di acquisto approvate attraverso il processo di revisione quando il prezzo di un articolo del catalogo di approvvigionamento aumenta. Impostare l'importo massimo di cui l'importo netto in una voce di una richiesta di acquisto può aumentare tra il momento dell'approvazione della richiesta di acquisto e il momento della creazione dell'ordine acquisto. L'importo netto viene calcolato utilizzando la formula seguente: (\[Quantità × (Prezzo unitario - Sconto) ÷ Prezzo unitario\]  + Spese varie di acquisto) × (100 – Percentuale di sconto) ÷ 100. Le righe richiesta di acquisto che superano la tolleranza di prezzo impostata sono conservate per l'elaborazione manuale. Le regole che si configurano nella scheda **Elaborazione errore** determinano la modalità di elaborazione delle righe della richiesta di acquisto.
-   Nella scheda **Elaborazione errore** è possibile configurare la regola di elaborazione che viene applicata a una richiesta di acquisto se durante la creazione l'ordine di acquisto fallisce la convalida a causa di un errore del fornitore o un errore nella tolleranza del prezzo. Consente di selezionare una delle opzioni indicate di seguito.
    -   **Nessuna azione** - Le righe della richiesta di acquisto rimangono nella pagina **Rilascia richieste di acquisto approvate**. Lo stato delle righe di richiesta di acquisto rimane impostato su **Approvata**. Tuttavia, è necessario risolvere gli errori affinché sia possibile generare un ordine fornitore per le righe di richiesta di acquisto.
    -   **Annulla la riga della richiesta di acquisto** - Le righe della richiesta di acquisto vengono annullate. Tuttavia, il richiedente può creare una nuova richiesta di acquisto per le righe annullate se desidera richiedere le voci.
    -   **Crea una nuova riga della richiesta di acquisto** - Le righe della richiesta di acquisto vengono annullate. Vengono quindi generate nuove richieste di acquisto contenenti solo le righe di richiesta di acquisto che non hanno superato la convalida. Le nuove richieste di acquisto generate avranno lo stato impostato su **Bozza**. e potranno essere inviate nuovamente una volta risolti gli errori di convalida. Al preparatore delle righe di richiesta di acquisto viene inviata una notifica dell'annullamento delle righe e della generazione di nuove richieste di acquisto al posto delle righe di richiesta di acquisto che non hanno superato la convalida.
-   Nella scheda **Creazione manuale ordini fornitore** è possibile definire i parametri che determinano se una richiesta di acquisto deve essere elaborata manualmente o se può essere convertita automaticamente in un ordine acquisto. I parametri possono essere applicati ad articoli del catalogo interno, ad articoli del catalogo esterno o ad articoli fuori catalogo. Consente di selezionare una delle opzioni indicate di seguito.
    -   **Crea manualmente ordini fornitore** - Creare manualmente gli ordini acquisto per tutte le richieste di acquisto.
    -   **Crea automaticamente ordini fornitore** - Creare automaticamente ordini di acquisto per tutte le richieste di acquisto approvate. Nessuna richiesta di acquisto viene impostata per la creazione manuale degli ordini fornitore.
    -   **Crea automaticamente ordini fornitore tranne che in queste condizioni** - Creare manualmente ordini acquisto per richieste di acquisto che corrispondono ai criteri definiti dall'utente. Tutte le altre richieste di acquisto approvate vengono automaticamente convertite in ordini fornitore. Se si seleziona **Crea automaticamente ordini fornitore tranne che in queste condizioni**, è possibile aggiungere categorie di approvvigionamento e fornitori per specificare quali righe della richiesta di acquisto approvata conservare per l'elaborazione manuale. Questa opzione può essere applicata ad articoli del catalogo interno, ad articoli del catalogo esterno e ad articoli fuori catalogo. Quando si seleziona una categoria di approvvigionamento, vengono selezionate anche tutte le sottocategorie definite per tale categoria di approvvigionamento. Selezionare l'opzione **Tutte** per uno specifico tipo di riga della richiesta di acquisto per conservare tutte le righe di tale tipo per l'elaborazione manuale.

    Se si desidera che gli ordini acquisto vengano generati automaticamente da richieste di acquisto approvate durante l'esecuzione del processo batch per la generazione di ordini acquisto, selezionare l'opzione **Esegui creazione automatica ordini fornitore come processo batch**. Questa opzione si applica solo alle richieste di acquisto che non richiedono elaborazione manuale. L'esecuzione della generazione automatica degli ordini fornitore come processo batch consente di programmare tale attività in un momento in cui le risorse sono più libere. Se l'opzione **Pagamento anticipato richiesto** è selezionata nelle righe della richiesta di acquisto, selezionare l'opzione **Quando la richiesta è impostata per il pagamento anticipato** per conservare le richieste di acquisto approvate per l'elaborazione manuale. Le richieste di acquisto impostate per l'elaborazione manuale possono essere filtrate in modo da visualizzare solo le righe di richiesta di acquisto che richiedono il pagamento anticipato.
-   Nella scheda **Consolidamento domanda** è possibile definire i parametri che determinano se le richieste di acquisto che vengono elaborate manualmente possono essere considerate per il consolidamento delle richieste di acquisto. I parametri possono essere applicati ad articoli del catalogo interno, ad articoli del catalogo esterno o ad articoli fuori catalogo. Consente di selezionare una delle opzioni indicate di seguito.
    -   **Non consentire consolidamento domanda** - Nessuna riga della richiesta di acquisto è idonea per il consolidamento della domanda. Questa opzione è selezionata per impostazione predefinita e si applica solo alle righe di richiesta di acquisto che richiedono l'elaborazione manuale per la creazione dell'ordine fornitore.
    -   **Consenti sempre consolidamento domanda** - Tutte le righe della richiesta di acquisto sono idonee per il consolidamento della domanda. **Nota:** se si seleziona l'opzione **Consenti sempre consolidamento domanda** nella scheda **Consolidamento domanda** ma si seleziona l'opzione **Crea automaticamente ordini fornitore** nella scheda **Creazione manuale ordini fornitore**, tutte le richieste di acquisto vengono conservate per l'elaborazione manuale.
    -   **Consenti consolidamento domanda in queste condizioni** - Definire i criteri che determinano se le righe della richiesta di acquisto approvata sono idonee al consolidamento della domanda. Per ogni tipo di riga di richiesta di acquisto è possibile impostare i criteri in base alla categoria di approvvigionamento e al fornitore. Se si seleziona **Consenti consolidamento domanda in queste condizioni**, è possibile impostare i criteri in base alla categoria di approvvigionamento e al fornitore per ciascun tipo di riga della richiesta di acquisto. Quando si seleziona una categoria di approvvigionamento, vengono selezionate anche tutte le sottocategorie definite per tale categoria di approvvigionamento. Se si seleziona l'opzione **Tutte** per un tipo di riga specifico, tutte le righe della richiesta di acquisto di tale tipo saranno idonee per il consolidamento della domanda.




