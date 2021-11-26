---
title: Definire il piano dei conti locale
description: Questo argomento fornisce informazioni che ti aiuteranno a pianificare il piano dei conti quando hai requisiti per i requisiti legali/locali per la tua organizzazione.
author: VeselinaE
ms.date: 10/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts, LedgerConsolidateAccountGroup, MainAccountConsolidateAccount, DimensionDetails, MainAccountDetails
ROBOTS: ''
audience: Application User
ms.devlang: ''
ms.reviewer: roschlom
ms.tgt_pltfrm: ''
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.search.industry: ''
ms.author: veneva
ms.search.validFrom: 10/07/2021
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e224a2e24b4ba293c953c6c883307038128e2f04
ms.sourcegitcommit: ba10ba2cd4fb4267afb5aacae4f6a52aa2456e7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/11/2021
ms.locfileid: "7798298"
---
# <a name="plan-your-local-chart-of-accounts"></a>Definire il piano dei conti locale

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni che consentono di pianificare il piano dei conti quando l'organizzazione include persone giuridiche che devono soddisfare i requisiti per località specifiche in cui operano. Questo argomento utilizza i seguenti termini per descrivere i piani dei conti:

- **Globale**: il piano dei conti che l'organizzazione utilizza a livello globale. Nella maggior parte dei casi, rientrerai in questo piano dei conti.
- **Locale**: un piano dei conti utilizzato dalle persone giuridiche di un paese o di una regione specifici.
- **Condiviso**: un piano dei conti utilizzabile da più persone giuridiche. È possibile condividere sia il piano dei conti globale che il piano dei conti locale.

Puoi creare e condividere più piani dei conti. Un piano dei conti condiviso può essere utilizzato da più persone giuridiche, ma a ciascuna persona giuridica può essere assegnato un solo piano dei conti. Il piano dei conti utilizzato da una persona giuridica è definito nella pagina **Contabilità generale**.

Quando progettano il piano dei conti, molte organizzazioni mirano a un piano dei conti globale. La funzionalità del piano dei conti condiviso consente la creazione di un piano dei conti globale. Ci sono vantaggi nella creazione e nell'utilizzo di un unico piano dei conti. Ad esempio, governance e controllo, manutenzione e reporting sono più semplici.

La maggior parte delle organizzazioni preferisce un piano dei conti globale ed è il tipo più semplice da implementare. Tuttavia, alcune persone giuridiche richiedono un piano dei conti locale per i seguenti motivi:

- Requisiti statutari locali
- Requisiti degli standard contabili locali
- Requisiti settoriali
- Requisiti di rendicontazione e analisi specifici dell'azienda

Se la tua organizzazione richiede che una persona giuridica utilizzi un piano dei conti locale, sono disponibili due opzioni per implementarlo:

- Assegnare il piano dei conti globale e definire altri mezzi per soddisfare i requisiti locali.
- Assegnare un piano dei conti locale alla persona giuridica e definire le relazioni con il piano dei conti globale.

La struttura organizzativa e la struttura di reporting determinano l'opzione utilizzata.

[![Diagramma che mostra come la struttura organizzativa determina se utilizzare un piano dei conti globale o locale](./media/local-chart-of-accounts-diagram.png)](./media/local-chart-of-accounts-diagram.png)

Se il piano dei conti globale è assegnato alla persona giuridica, sono disponibili le seguenti opzioni per soddisfare i requisiti di reporting locali:

- Eseguire consolidamenti locali.
- Utilizzare una dimensione finanziaria per tenere traccia del piano dei conti locale.
- Creare conti principali locali nel piano dei conti globale.
- Eseguire il mapping esterno al piano dei conti locale.

Se un piano dei conti locale è assegnato alla persona giuridica, l'unica opzione attualmente disponibile opzioni per soddisfare i requisiti di reporting globali è il consolidamento globale.

## <a name="global-chart-of-accounts-assigned-to-a-legal-entity"></a>Piano dei conti globale assegnato a una persona giuridica

Se devi assegnare il piano dei conti globale a una persona giuridica, sono disponibili quattro opzioni per la configurazione del sistema, come descritto in precedenza. Per tutte e quattro le opzioni, viene configurato un unico piano dei conti e collegato a ciascuna persona giuridica nella pagina **Contabilità generale**. Ciascuna opzione utilizza quindi un approccio diverso per soddisfare i requisiti di localizzazione. Le sezioni seguenti descrivono i passaggi di alto livello per configurare il sistema per i requisiti di localizzazione. Descrivono anche i vantaggi e gli svantaggi di ciascuna opzione.

### <a name="do-local-consolidation"></a>Eseguire consolidamenti locali

Il consolidamento locale è l'approccio consigliato per soddisfare i requisiti del piano dei conti locale e sfruttare le funzionalità di sistema progettate per questo scopo.

#### <a name="set-up-consolidation-for-a-local-chart-of-accounts"></a>Configurare il consolidamento per un piano dei conti locale

1. Crea un unico piano dei conti globale che includa tutti i conti principali richiesti.
2. In ogni persona giuridica, assegnare il piano dei conti globale nella pagina **Contabilità generale**.
3. Crea una persona giuridica di consolidamento per ogni localizzazione richiesta.
4. Eseguire uno dei passaggi riportati di seguito.

    - Se è necessaria una sola localizzazione, configurare l'account di consolidamento nella pagina **Conto principale** oppure utilizzare le pagine **Gruppi di consolidamento** e **Conti di consolidamento aggiuntivi**.
    - Se è necessaria più di una localizzazione o se sia il numero di conto che il nome di conto richiedono la traduzione, utilizza le pagine **Gruppi di consolidamento** e **Conti di consolidamento aggiuntivi** per rappresentare i requisiti di localizzazione.

5. Esegui il processo di consolidamento per trasformare il valore dalla persona giuridica di origine che utilizza il piano dei conti globale alla società di consolidamento che utilizza il piano dei conti locale.

#### <a name="advantages"></a>Vantaggi

- Questo approccio fornisce un modo coerente di lavorare in tutta l'organizzazione.
- Viene eseguita una traduzione della posizione locale.
- Questo approccio supporta la traduzione sia dell'ID del conto principale che del nome di ogni conto principale.
- Supporta più localizzazioni.

#### <a name="disadvantages"></a>Svantaggi

- Viene creata un'ulteriore società di consolidamento.
- Viene completato un ulteriore processo di consolidamento.
- Questo approccio può generare report sul grafico localizzato solo dopo il completamento del processo di consolidamento.

### <a name="use-a-financial-dimension-to-track-the-local-chart-of-accounts"></a>Utilizzare una dimensione finanziaria per tenere traccia del piano dei conti locale

Questo approccio utilizza una dimensione finanziaria in cui i valori della dimensione finanziaria rappresentano i conti principali locali necessari per la localizzazione. Funziona bene se è richiesta una sola localizzazione. Tuttavia, diventa meno utilizzabile man mano che si aggiungono più localizzazioni e dimensioni finanziarie.

#### <a name="set-up-a-financial-dimension-for-a-local-chart-of-accounts"></a>Configurare una dimensione finanziaria per un piano dei conti locale

1. Crea un unico piano dei conti globale che includa tutti i conti principali richiesti.
2. In ogni persona giuridica, assegnare il piano dei conti globale nella pagina **Contabilità generale**.
3. Creare una dimensione finanziaria che rappresenti il piano dei conti locale.
4. Creare valori di dimensione finanziaria che rappresentino i conti principali nel piano dei conti locale.
5. Aggiorna la struttura dei conti in modo da includere la dimensione finanziaria "piano dei conti locale".
6. Assicurati che la dimensione finanziaria "piano dei conti locale" abbia sempre un valore e che non consenta un valore vuoto. Considera l'utilizzo di quote derivate o quote fisse.
7. Crea un set di dimensioni finanziarie in cui la dimensione finanziaria "piano dei conti locale" è la prima dimensione finanziaria selezionata. Il set di dimensioni finanziarie può essere utilizzato quando viene generato il bilancio di verifica.

#### <a name="advantages"></a>Vantaggi

- I conti principali dei piani dei conti globali e locali esistono a livello di transazione. Il conto principale è globale e il valore della dimensione finanziaria è locale.
- Questo approccio fornisce report e visualizzazioni in tempo reale sia della posizione finanziaria globale che della posizione finanziaria locale.

#### <a name="disadvantages"></a>Svantaggi

- In Parametri di contabilità generale, se il campo **Valori utilizzati per il conto riepilogativo** è impostato su **Distribuzione contabile**, le dimensioni finanziarie che rappresentano il conto principale per spese/attività/ricavi verranno utilizzate in modo errato per il conto di riepilogo Contabilità clienti e Contabilità fornitori. Ti consigliamo invece di impostare il campo su un documento di origine per garantire che vengano utilizzati i valori di dimensione finanziaria corretti.
- Se sono necessari molti piani dei conti locali e per tutti viene utilizzata una dimensione finanziaria, l'elenco dei valori delle dimensioni finanziarie utilizzati può diventare lungo e difficile da gestire.
- Se sono necessari molti piani dei conti locali e viene utilizzata una dimensione finanziaria separata per rappresentarli, l'usabilità e le prestazioni del sistema possono essere influenzate dall'aggiunta di dimensioni finanziarie e set di dimensioni finanziarie.
- Ti consigliamo di considerare attentamente il numero di dimensioni finanziarie necessarie, il numero di valori in ciascuna di esse e il numero di set di dimensioni finanziarie, poiché tutti questi fattori possono influire sulle prestazioni del sistema.

### <a name="create-local-main-accounts-in-the-global-chart-of-accounts"></a>Creare conti principali locali nel piano dei conti globale

*Cosa ha chiesto il copy editor:* In questo approccio, i conti principali locali nel piano dei conti globale includono i conti principali nel piano dei conti locale nel piano dei conti globale.

*Versione originale:* i conti principali locali nell'ambito dell'approccio del CoA globale è che i conti principali del CoA locale sono inclusi nel CoA globale.

*Dovrebbe dire questo:* in questo approccio, i conti principali locali nel piano dei conti locale sono inclusi nel piano dei conti globale.


#### <a name="set-up-local-main-accounts-in-the-global-chart-of-accounts"></a>Configurare conti principali locali nel piano dei conti globale

1. Creare un unico piano dei conti che includa i conti principali sia per il piano dei conti globale che per il piano dei conti locale.
2. In ogni persona giuridica, assegna il piano dei conti globale nella pagina **Contabilità generale**.
3. Creare conti totali nel piano dei conti per sommare i conti principali che rappresentano lo stesso scopo.
4. Crea sostituzioni di persone giuridiche su ciascun account locale per impedire transazioni da altre persone giuridiche per le quali l'account locale non è stato progettato.
5. Crea sostituzioni di persone giuridiche su ogni conto globale per impedire transazioni dalle persone giuridiche di localizzazione.

#### <a name="advantages"></a>Vantaggi

- Una vista in tempo reale sia della posizione finanziaria globale che della posizione finanziaria locale è disponibile su report specifici e in viste specifiche nel sistema, come un report finanziario di stato patrimoniale. È possibile accedervi anche utilizzando il pulsante **Periodo** sul conto totale.
- Non hai un segmento aggiuntivo nella contabilità generale.

#### <a name="disadvantages"></a>Svantaggi

- L'utilizzo e la visibilità totali del conto sono limitati. Ad esempio, il totale dei conti non è visibile nella pagina dell'elenco **Bilancio di verifica**.
- La manutenzione richiede uno sforzo aggiuntivo.
- La creazione di report finanziari richiede uno sforzo manuale aggiuntivo.

### <a name="do-external-mapping-to-the-local-chart-of-accounts"></a>Eseguire il mapping esterno al piano dei conti locale

L'adozione di un piano dei conti globale presuppone la gestione della mappatura e delle localizzazioni al di fuori del sistema. In questo approccio, basta creare un unico piano dei conti globale in Microsoft Dynamics 365 Finance e gestire i requisiti al di fuori del sistema.

#### <a name="set-up-external-mapping-to-a-local-chart-of-accounts"></a>Configurare il mapping esterno a un piano dei conti locale

1. Crea un unico piano dei conti globale che includa tutti i conti principali richiesti.
2. In ogni persona giuridica, assegnare il piano dei conti globale nella pagina **Contabilità generale**.
3. Eseguire il mapping esterno al piano dei conti locale al di fuori di Finance.

#### <a name="advantages"></a>Vantaggi

- Questo approccio fornisce un modo unificato di lavorare in tutta l'organizzazione.

#### <a name="disadvantages"></a>Svantaggi

- Non è disponibile alcuna segnalazione locale dal sistema.
- Questo approccio è soggetto a errori durante la creazione di report finanziari.

## <a name="local-chart-of-accounts-assigned-to-legal-entity"></a>Piano dei conti locale assegnato a una persona giuridica

Se l'organizzazione decide di non utilizzare un piano dei conti globale tra le persone giuridiche, viene creato un piano dei conti separato per ogni piano dei conti locale univoco. Ciascuna persona giuridica è quindi collegata al piano dei conti corrispondente nella pagina **Contabilità generale**.

### <a name="do-global-consolidation"></a>Eseguire il consolidamento globale

In questo approccio, una società di consolidamento viene utilizzata per raggruppare e combinare i saldi di ciascuna società locale di origine nel piano dei conti globale combinato nella società di consolidamento. Questo approccio richiede che si mantenga un mapping di ogni piano dei conti locale al piano dei conti globale nella società di consolidamento.

#### <a name="set-up-global-consolidation"></a>Configurare il consolidamento globale

1. Creare un piano dei conti separato per ogni persona giuridica che ha un piano dei conti locale diverso. Se le persone giuridiche hanno lo stesso piano dei conti locale, è richiesto un solo piano dei conti locale e può essere condiviso.
2. In ogni persona giuridica, assegnare il piano dei conti appropriato nella pagina **Contabilità generale**.
3. Facoltativo: creare un piano dei conti per il piano dei conti globale di ciascuna società di consolidamento che dispone di un piano dei conti globale diverso.
4. Creare una persona giuridica di consolidamento per ogni livello di consolidamento richiesto e assegnare il piano dei conti appropriato nella pagina **Contabilità generale**.
5. Eseguire uno dei passaggi riportati di seguito.

    - Se è richiesto un solo consolidamento, configurare l'account di consolidamento nella pagina **Conto principale**.
    - Se è necessario più di un consolidamento o se sia il numero di conto che il nome di conto richiedono la traduzione, utilizza le pagine **Gruppi di consolidamento** e **Conti di consolidamento aggiuntivi** per rappresentare i requisiti per il piano dei conti globale.

6. Esegui il processo di consolidamento per trasferire i saldi dalle persone giuridiche locali alla persona giuridica consolidata. Questa persona giuridica consolidata utilizza i conti di consolidamento definiti nel passaggio 5.

#### <a name="advantages"></a>Vantaggi

- Il formato dei principi contabili locali è applicato in modalità nativa.
- Questo approccio offre al team finanziario locale un modo più semplice di lavorare.

#### <a name="disadvantages"></a>Svantaggi

- Non è disponibile una visualizzazione in tempo reale della posizione globale.
- Il processo di consolidamento potrebbe essere eseguito più spesso.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Definire il piano dei conti](plan-chart-of-accounts.md)
- [Configurare i libri contabili](configure-ledger.md)
- [Dimensioni finanziarie e registrazione](Default-dimensions.md#balancing-dimension)
- [Set di dimensioni finanziarie](financial-dimension-sets.md)
- [Panoramica dell'eliminazione e del consolidamento](../budgeting/consolidation-elimination-overview.md)
- [Gruppi di conti di consolidamento e conti di consolidamento aggiuntivi](../budgeting/consolidation-account-groups-consolidation-accounts.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
