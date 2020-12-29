---
title: Pianificazione della gerarchia organizzativa
description: Prima di impostare le organizzazioni e le gerarchie organizzative, è necessario comprendere qual è il modo migliore di modellare l'azienda.
author: sericks007
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: OMHierarchyManager, OMLegalEntity, OMOperatingUnit
audience: Application User
ms.reviewer: sericks
ms.custom: 17404
ms.assetid: babde0c6-bb5d-45ae-95ca-2af75a0ea292
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 986d8986375aac9454483d89c46c1b2b6f52e68e
ms.sourcegitcommit: f5e31c34640add6d40308ac1365cc0ee60e60e24
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "4694691"
---
# <a name="plan-your-organizational-hierarchy"></a>Pianificazione della gerarchia organizzativa

[!include [banner](../includes/banner.md)]

Prima di impostare le organizzazioni e le gerarchie organizzative, assicurarsi di pianificare come l'azienda verrà modellata. Il modello di organizzazione ha un effetto significativo sull'implementazione e sui processi aziendali.

Le gerarchie organizzative rappresentano i rapporti tra le organizzazioni che fanno parte di un'azienda. Di conseguenza, l'aspetto più importante da considerare quando si modellano le organizzazioni è la struttura della società. È consigliabile definire le strutture dell'organizzazione in base al riscontro dei dirigenti e dei senior manager di aree funzionali quali finanze e contabilità, risorse umane, operazioni, acquisti, vendite e marketing.

Quando si effettua la pianificazione delle gerarchie, è inoltre importante considerare la relazione tra la gerarchia organizzativa e le dimensioni finanziarie. È possibile impostare più gerarchie organizzative per rappresentare visualizzazioni diverse dell'azienda. Utilizzando le dimensioni finanziarie, è possibile creare report in base a queste visualizzazioni. È possibile collaborare con il proprio partner per creare gerarchie che soddisfano le esigenze di reporting sia organizzative che statutarie.

> [!NOTE]
> Sebbene sia possibile utilizzare le dimensioni finanziarie per rappresentare le persone giuridiche senza creare le persone giuridiche, le dimensioni finanziarie non sono progettate per rispondere alle esigenze operative o aziendali delle persone giuridiche. La funzionalità di contabilità interunità è stata progettata per inviare solo le voci contabili create da ciascuna transazione.

> [!IMPORTANT]
> Non è necessario decidere come modellare le organizzazioni in base solo alle informazioni in questo articolo. La documentazione rappresenta una guida. Per ulteriori indicazioni è possibile collaborare con il proprio partner. Il partner ha accumulato esperienza in vari settori e nell'intera base clienti.

## <a name="decide-whether-to-model-internal-organizations-as-legal-entities-or-operating-units"></a>Decidere se modellare le organizzazioni interne come persone giuridiche o come unità operative

È necessario disporre di almeno una persona giuridica che rappresenti l'azienda. Una persona giuridica può stipulare contratti legali e ha l'obbligo di preparare rendiconti finanziari sul proprio rendimento.

Le persone giuridiche possono essere utilizzate per le attività transazionali o per il consolidamento. Ciò significa che una persona giuridica in Finance and Operations non rappresenta necessariamente un'entità reale nell'azienda. Ad esempio, una società che partecipa alle transazioni può possedere persone giuridiche affiliate. In questo scenario, sono necessarie una persona giuridica per le transazioni e una persona giuridica virtuale per consolidare i risultati e i saldi delle persone giuridiche affiliate.

Le organizzazioni interne all'azienda, ad esempio gli uffici regionali, possono essere rappresentate come persone giuridiche aggiuntive o come unità operative della persona giuridica principale. Non è necessario che un'unità operativa sia un'organizzazione legalmente definita. Le unità operative vengono utilizzate per controllare le risorse economiche e i processi operativi nell'azienda. Ad esempio, i reparti e i centri di costo sono unità operative.

Alcune funzionalità operano in modo diverso a seconda che l'organizzazione sia una persona giuridica o un'unità operativa. Considerare attentamente la funzionalità descritta di seguito quando si prende la decisione.

### <a name="master-data"></a>Dati master

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Alcuni dati di anagrafica, come i clienti, i termini di pagamento, gli uffici tributari e l'ordine predefinito specifico a un sito, devono essere impostati per ciascuna persona giuridica. Alcuni dati di anagrafica, come gli utenti, i prodotti e la maggior parte dei dati relativi alle risorse umane, vengono condivisi tra tutte le persone giuridiche.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

L'anagrafica viene condivisa tra le unità operative.

### <a name="module-parameters"></a>Parametri del modulo

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

I parametri per i moduli, ad esempio i parametri di contabilità clienti, i parametri di contabilità fornitori e i parametri di gestione della banca e della cassa, devono essere impostati in base alla persona giuridica. Poiché l'impostazione del modulo per le persone giuridiche è separata, ogni filiale può conformarsi agli obblighi locali e alle pratiche aziendali. Ad esempio, una persona giuridica di servizi professionali e una persona giuridica di produzione possono avere parametri del modulo differenti anche se fanno riferimento alla stessa società consolidata.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

I parametri del modulo sono condivisi tra le unità operative.

### <a name="data-security"></a>Sicurezza dei dati

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

La maggior parte dei dati è protetta automaticamente dall'ID società. Un'ID di società è un identificatore univoco per i dati associati a una persona giuridica. Una società può essere associata a una sola persona giuridica e una persona giuridica può essere associata a una sola società. Gli utenti possono accedere ai dati solo per le società a cui hanno accesso. Non è necessario personalizzare per proteggere i dati tramite l'ID società.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

I dati possono essere protetti per unità operativa creando criteri di sicurezza dei dati personalizzati. I criteri di sicurezza dei dati vengono utilizzati per limitare l'accesso ai dati. Ad esempio, si supponga che a un utente sia consentito creare gli ordini fornitore solo in una determinata unità operativa. È possibile creare dei criteri di sicurezza dei dati per impedire all'utente di accedere ai dati dell'ordine fornitore da qualsiasi altra unità operativa. Il volume di transazioni e il numero di criteri di sicurezza possono influire sulle prestazioni. Quando si progettano i criteri di sicurezza, è importante tenere a mente gli effetti sulle prestazioni.

### <a name="ledgers"></a>Contabilità generali

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Ogni persona giuridica richiede una contabilità generale che includa un piano dei conti, la valuta di contabilizzazione, la valuta di dichiarazione e il calendario fiscale. Uno stato patrimoniale può essere creato solo per una persona giuridica. I conti principali, le dimensioni, le strutture dei conti, i piani dei conti e le regole contabili possono essere utilizzati da più di una persona giuridica.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Un'unità operativa non può disporre di dati di contabilità generale propri. Se le organizzazioni interne non richiedono una contabilità generale univoca, è possibile modellarle come unità operative. I dati di contabilità generale verranno impostati per la persona giuridica padre nella gerarchia. Le dichiarazioni dei redditi possono essere create per le unità operative all'interno di una persona giuridica o per la persona giuridica padre.

### <a name="fiscal-calendars"></a>Calendari fiscali

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Ogni persona giuridica dispone di un proprio calendario fiscale. Se le organizzazioni interne utilizzano anni fiscali e calendari fiscali differenti, è necessario modellare le organizzazioni come persone giuridiche.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Le unità operative devono condividere un calendario fiscale. Se le organizzazioni interne possono utilizzare anni fiscali e calendari fiscali uguali, è possibile modellare le organizzazioni come unità operative.

### <a name="consolidation"></a>Consolidamento

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

È necessario consolidare i risultati finanziari degli uffici regionali in una singola società consolidata per preparare i rendiconti finanziari.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Il consolidamento non è obbligatorio, poiché i dati sono già condivisi tra le unità operative.

### <a name="centralized-payments"></a>Pagamenti centralizzati

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

I pagamenti centralizzati devono essere impostati in modo che le fatture per tutte le persone giuridiche figlio siano pagate a o da un'unica persona giuridica padre.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

I pagamenti centralizzati non sono obbligatori poiché tutte le fatture vengono registrate in una singola persona giuridica.

### <a name="intercompany-transactions"></a>Transazioni interaziendali

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Gli ordini cliente, gli ordini fornitore, i pagamenti o le ricevute interaziendali possono essere applicati reciprocamente. Non è necessario utilizzare i giustificativi giornale di registrazione. È possibile visualizzare le transazioni interaziendali a livello di contabilità secondaria (contabilità clienti, contabilità fornitori). Negli esempi riportati di seguito viene illustrato il modo in cui vengono gestite le transazioni interaziendali.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Esempio 1: la sede centrale fornisce i servizi agli uffici regionali e deve addebitare i costi dei servizi agli uffici regionali.

Se si modella l'ufficio regionale come persona giuridica, sono disponibili le seguenti opzioni:

- La sede centrale crea una scrittura contabile per creare un addebito interaziendale all'ufficio regionale per le spese. Le transazioni non sono soggette ad aging.
- La sede centrale invia un ordine acquisto per i servizi all'ufficio regionale. Un ordine cliente viene creato automaticamente nella persona giuridica per l'ufficio regionale, con le transazioni di contabilità secondaria interaziendali.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Esempio 2: la sede centrale procura il servizio all'ufficio regionale e lo paga.

Se si modella l'ufficio regionale come persona giuridica, sono disponibili le seguenti opzioni:

- La fattura e il pagamento seguono i requisiti normativi della sede centrale. La sede centrale può creare una scrittura contabile per creare un addebito interaziendale all'ufficio regionale per le spese. Le transazioni non sono soggette ad aging.
- La fattura e il pagamento seguono i requisiti normativi della sede centrale. La sede centrale può creare una transazione di contabilità secondaria interaziendale.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Le transazioni interaziendali tra unità operative sono supportate solo tramite i giustificativi giornale di registrazione. Un'unità operativa non può rilasciare un ordine fornitore, un ordine cliente o una fattura a un'altra unità operativa né può ricevere questi documenti da un'altra unità operativa nella stessa persona giuridica. Non è possibile visualizzare le transazioni interaziendali a livello di contabilità secondaria (contabilità clienti, contabilità fornitori). Negli esempi riportati di seguito viene illustrato il modo in cui vengono gestite le transazioni interaziendali.

##### <a name="example-1-headquarters-provides-services-to-regional-offices-and-must-charge-the-costs-of-those-services-to-the-regional-offices"></a>Esempio 1: la sede centrale fornisce i servizi agli uffici regionali e deve addebitare i costi dei servizi agli uffici regionali.

Se si modella l'ufficio regionale come unità operativa, la sede centrale immette una transazione di spesa e la codifica all'ufficio regionale.

##### <a name="example-2-headquarters-procures-and-pays-for-service-that-is-delivered-to-a-regional-office"></a>Esempio 2: la sede centrale procura il servizio all'ufficio regionale e lo paga.

Se si modella l'ufficio regionale come unità operativa, la fattura e il pagamento seguono i requisiti normativi della sede centrale. La fattura può essere codificata all'ufficio regionale. Nella dichiarazione dei redditi, utilizzare una dimensione finanziaria di compensazione per riportare i costi per l'ufficio regionale.

### <a name="local-tax-requirements"></a>Requisiti fiscali locali

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Una persona giuridica è soggetta alle leggi fiscali dell'autorità fiscale del paese in cui la persona giuridica è registrata. Ad esempio, una persona giuridica registrata in Danimarca è soggetta alle leggi fiscali e alle normative danesi. Una persona giuridica può appartenere solo a un paese. Il paese selezionato per l'indirizzo principale della persona giuridica controlla le funzioni specifiche del paese disponibili per quella persona giuridica. Ad esempio, se l'indirizzo principale della persona giuridica è in Danimarca, vengono rese disponibili le funzionalità correlate alle normative e alle leggi fiscali danesi. Di conseguenza, se le organizzazioni si trovano in paesi diversi e devono essere soggette a leggi fiscali diverse, è necessario impostare le organizzazioni come persone giuridiche separate.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Le unità operative utilizzano il contesto del paese della persona giuridica padre. Le unità operative nella stessa persona giuridica non possono avere requisiti specifici del paese differenti. Se le organizzazioni si trovano nello stesso paese e utilizzano le stesse leggi fiscali, è possibile impostarle come unità operative.

### <a name="statutory-reporting-for-a-countryregion"></a>Dichiarazione statutaria per un paese

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Per i paesi che sono supportati, è possibile creare la maggior parte delle dichiarazioni statutarie. Per ulteriori informazioni su quali report sono disponibili per ogni paese, vedere il [Portale di localizzazione di Microsoft Dynamics](https://mbs.microsoft.com/customersource/global/ax/support/support-news/GFMLocalizationPortalMC). (accesso a CustomerSource necessario).

> [!NOTE]
> Un livello di registrazione nella contabilità generale consente di creare voci di rettifica per una società consolidata che utilizza una contabilità standard diversa da quella della filiale. Ad esempio, per una società che utilizza le pratiche contabili generalmente accettate nel Regno Unito (GAAP BRITANNICO), è possibile creare voci di rettifica nel livello di registrazione. Queste voci possono essere consolidate in una società consolidata che utilizza i principi contabili generalmente accettati (GAAP) negli Stati Uniti. Le voci di rettifica non influiscono sulla dichiarazione GAAP britannica.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Le dichiarazioni statutarie devono essere create utilizzando un'altra applicazione. È necessario assicurarsi che i dati vengano acquisiti in Finance and Operations per supportare i requisiti di ciascuna unità operativa, laddove differiscono dai requisiti della sede centrale.

### <a name="currency"></a>Valuta

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Se le organizzazioni devono utilizzare valute funzionali differenti, è necessario modellare le organizzazioni come persone giuridiche. Le valute funzionali vengono impostate per la persona giuridica. Tuttavia, è possibile immettere le transazioni in più valute.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Se le organizzazioni possono utilizzare un'unica valuta funzionale, è possibile modellare le organizzazioni come unità operative. Le unità operative devono condividere una valuta funzionale. Tuttavia, è possibile immettere le transazioni e creare report in più valute.

### <a name="year-end-closing"></a>Chiusura di fine anno

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Se le normative e le pratiche contabili differiscono tra i paesi in cui sono situate le organizzazioni, è possibile che ciascuna organizzazione necessiti di procedure di chiusura di fine anno proprie. Ciò significa che è necessario modellare le organizzazioni come persone giuridiche. Ogni persona giuridica si attiene a procedure di chiusura fine anno proprie.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Se le normative e le pratiche contabili sono uguali tra i paesi in cui sono situate le organizzazioni, è possibile utilizzare delle procedure di chiusura di fine anno uguali per tutte. Ovvero è possibile modellare le organizzazioni come unità operative. Tutte le unità operative devono seguire la stessa procedura di chiusura di fine anno.

### <a name="number-sequences"></a>Sequenze numeriche

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Le sequenze numeriche per alcuni riferimenti possono essere impostate in base alla persona giuridica. Alcune sequenze numeriche possono essere condivise.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Le sequenze numeriche per alcuni riferimenti possono essere impostate in base all'unità operativa. Alcune sequenze numeriche possono essere condivise.

### <a name="products"></a>Prodotti

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

Le definizioni dei prodotti sono condivise e devono essere rilasciate a singole persone giuridiche prima che possano essere incluse nelle transazioni. Ogni persona giuridica dispone di un proprio set di prodotti rilasciati che possono essere inclusi in documenti di transazione. Se le organizzazioni interne devono utilizzare set di prodotti differenti, è necessario modellare le organizzazioni come persone giuridiche.

> [!NOTE]
> Anche se le definizioni dei prodotti sono condivise, in ogni persona giuridica in cui un prodotto è stato rilasciato, è possibile specificare parametri di vendita, di acquisto e di stoccaggio diversi per l'articolo in ogni sito di magazzino.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Tutte le unità operative condividono lo stesso set di prodotti. Se le organizzazioni interne possono condividere lo stesso set di prodotti, è possibile modellare le organizzazioni come unità operative.

### <a name="inquiry-and-reporting"></a>Richiesta di informazioni e creazione di report

#### <a name="if-the-organization-is-modeled-as-a-legal-entity"></a>Se l'organizzazione è modellata come persona giuridica

È necessario modificare manualmente le società per immettere le transazioni ed eseguire richieste di informazioni in più persone giuridiche. A causa dei limiti di sicurezza dei dati, le funzionalità consolidate di richiesta di informazioni e di creazione di report possono richiedere un utilizzo intensivo di tempo e di risorse.

#### <a name="if-the-organization-is-modeled-as-an-operating-unit"></a>Se l'organizzazione è modellata come unità operativa

Non è necessario modificare le società per accedere ai dati da più unità operative. Le funzionalità consolidate di richiesta di informazioni e di creazione di report e la richiesta di informazioni a livello regionale sono più semplici e veloci.

## <a name="best-practices-for-modeling-organizations-and-hierarchies"></a>Procedure consigliate per la modellazione di organizzazioni e gerarchie

Quando si implementa una gerarchia organizzativa, considerare le procedure ottimali seguenti:

- Creare un reparto per modellare l'intersezione tra una persona giuridica e una Business Unit. È quindi possibile riepilogare i dati da un reparto a una persona giuridica per una dichiarazione statutaria e da un reparto a una Business Unit per la creazione di report interni. I reparti possono svolgere la funzione di centri di profitto. Se si utilizzano i reparti, non è necessario utilizzare le persone giuridiche e le Business Unit come dimensioni della struttura dei conti. È possibile utilizzare i reparti come una dimensione. È tuttavia necessario utilizzare i centri di costo e i reparti come dimensioni della struttura dei conti se i centri di costo vengono utilizzati solo come accumulatori di costo e i reparti vengono utilizzati per il riconoscimento dei ricavi.
- Modellare più gerarchie per le unità operative se sussistono requisiti complessi per i rendiconti profitti e perdite.
- In una singola persona giuridica, non modellare più gerarchie per lo stesso scopo di gerarchia.
- Non creare una gerarchia per ogni scopo. In genere, è possibile utilizzare una gerarchia per più scopi. Ad esempio, una gerarchia di unità operative può essere assegnata a tutti gli scopi correlati ai criteri.
- Creare gerarchie bilanciate. In una gerarchia tutti i nodi che si trovano alla stessa distanza dal nodo radice sono definiti livelli. In una gerarchia bilanciata a ogni livello può trovarsi solo un tipo di unità operativa e la distanza dal nodo radice a ogni livello è coerente. Se esistono livelli intermedi tra un reparto e una persona giuridica o una Business Unit, potrebbero essere necessarie delle organizzazioni segnaposto per creare una gerarchia bilanciata.
- Non modellare una gerarchia separata di unità operative se la struttura per le persone giuridiche è anche la struttura operativa. Una gerarchia mista di persone giuridiche e unità operative può servire a entrambi gli scopi.
- Prima di modellare strutture di ristrutturazione consistenti, utilizzare le date di validità della gerarchia per effettuare un'analisi dell'impatto e un test di convalida.
- Utilizzare la modalità bozza per modificare una gerarchia prima di pubblicare una versione in un ambiente di produzione.
- Limitare il numero di persone che dispongono delle autorizzazioni per aggiungere o rimuovere organizzazioni da una gerarchia in un ambiente di produzione. Un numero inferiore riduce le possibilità di commettere costosi errori.
