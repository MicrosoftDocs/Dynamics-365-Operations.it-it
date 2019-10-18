---
title: Un giustificativo
description: Un giustificativo per giornali di registrazione finanziari (giornale di registrazione generale, giornale di registrazione cespiti, giornali di registrazione pagamenti fornitore e così via) consente di immettere più transazioni di giornali di registrazione secondari nel contesto di un singolo giustificativo.
author: kweekley
manager: AnnBe
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: 2b755dcfbcdf41ada0302fc04f527ce7c309f4bb
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2186396"
---
# <a name="one-voucher"></a>Un giustificativo

[!include [banner](../includes/banner.md)]


## <a name="what-is-one-voucher"></a>Che cos'è Un giustificativo?

La funzionalità esistente per giornali di registrazione finanziari (il giornale di registrazione generale, il giornale di registrazione cespiti, il giornale di registrazione pagamenti fornitore e così via) consente di immettere più transazioni di giornali di registrazione secondari (cliente, fornitore, cespiti, progetto e banca) nel contesto di un singolo giustificativo. Microsoft indica questa funzionalità come *Un giustificativo*. È possibile creare un giustificativo singolo utilizzando uno dei metodi seguenti:

- Impostare il nome del giornale di registrazione (**Contabilità generale** \> **Impostazione giornale di registrazione** \> **Nomi giornale di registrazione**) in modo da impostare il campo **Nuovo giustificativo** su **Un solo numero di giustificativo**. Ogni riga aggiunta al giornale di registrazione viene ora inclusa nello stesso giustificativo. Di conseguenza, il giustificativo può essere inserito come giustificativo plurimo, ad esempio un conto/conto di contropartita nella stessa riga, o come combinazione.

    [![Riga singola](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > La definizione di Un giustificativo **non** copre i casi in cui i nomi di giornali di registrazione sono impostati come **Un solo numero di giustificativo**, ma l'utente immette poi un giustificativo che include solo tipi di conto CoGe. In questo argomento Un giustificativo significa che c'è un solo giustificativo che contiene più di un fornitore, cliente, banca, cespite o progetto.

- Immettere un giustificativo plurimo in cui non sono presenti conti di contropartita.

    [![Giustificativo plurimo](./media/Multi-line.png)](./media/Multi-line.png)

- Immettere un giustificativo in cui sia il conto che il conto di contropartita contengono un tipo di conto secondario, ad esempio **Fornitore**/**Fornitore**, **Cliente**/**Cliente**, **Fornitore**/**Cliente** o **Banca**/**Banca**.

    [![Giustificativo contabilità generale secondaria](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problemi con un giustificativo

La funzionalità Un giustificativo genera problemi durante liquidazione, calcolo delle imposte, storno transazione, riconciliazione tra contabilità secondaria e contabilità generale, creazione di report finanziari e altro. (Per ulteriori informazioni sui problemi che possono verificarsi durante la liquidazione, vedere, ad esempio, [Giustificativo singolo con più record cliente o fornitore](https://docs.microsoft.com/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records).) Per funzionare e segnalare correttamente, questi processi e questi report necessitano dei dettagli delle transazioni. Sebbene alcuni scenari funzionino comunque correttamente, in base alle impostazioni dell'organizzazione, si verificano spesso problemi quando si immettono più transazioni in un unico giustificativo.

Ad esempio, si registra il giustificativo plurimo seguente.

[![Esempio](./media/example.png)](./media/example.png)

Si genera quindi il report **Spese per fornitore** nell'area di lavoro **Informazioni finanziarie dettagliate**. In questo report i saldi del conto spese sono raggruppati per gruppo di fornitori e quindi per fornitore. Durante la generazione del report il sistema non può determinare quali gruppi di fornitori/fornitori hanno sostenuto la spesa di 250,00. Poiché mancano i dettagli della transazione, il sistema suppone che l'intera spesa di 250,00 sia stata sostenuta dal primo fornitore indicato nel giustificativo. Pertanto, l'importo di 250,00, incluso nel saldo del conto principale 600120, viene visualizzato sotto quel gruppo fornitori/fornitore. Tuttavia, è molto probabile che il primo fornitore nel giustificativo non sia il fornitore corretto. Di conseguenza, il report è probabilmente errato.

[![Spese](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>Utilizzo futuro della funzionalità Un giustificativo

A causa dei problemi descritti in precedenza, la funzionalità Un giustificativo diventerà obsoleta. Tuttavia, poiché si presentano discontinuità funzionali che dipendono da questa funzionalità, la funzionalità non diventerà obsoleta tutto d'un tratto. Si utilizzerà invece la seguente programmazione:

- **Versione di primavera 2018** - Per impostazione predefinita, la funzionalità sarà disattivata per impostazione predefinita attraverso il parametro **Consenti più transazioni in un giustificativo** nella scheda **Generale** della pagina **Parametri di contabilità generale**. È tuttavia possibile attivare la funzionalità se l'organizzazione ha uno scenario che rientra in uno delle discontinuità funzionali indicate più avanti in questo argomento.

    - Se i clienti dispongono di uno scenario aziendale che non richiede la funzionalità Un giustificativo, non devono attivarla. Questi "bug" non verranno corretti da Microsoft nelle aree identificate oltre in questo argomento se questa funzionalità viene utilizzata anche se un'altra soluzione esiste.
    - Smettere di utilizzare Un giustificativo per le integrazioni, a meno che la funzionalità sia necessaria per uno dei gap funzionali.

- **Versioni successive** - Verranno corretti tutti i gap funzionali. **Dopo che le interruzioni funzionali verranno colmate e le nuove funzionalità consegnate, passerà almeno un anno prima che la funzionalità Un giustificativo venga definitivamente disattivata**, poiché i clienti e fornitori di software indipendenti (ISV) devono avere sufficiente tempo per reagire alla nuova funzionalità. Ad esempio, è possibile che debbano aggiornare i processi aziendali, le entità e le integrazioni.

> [!IMPORTANT]
> L'opzione **Un solo numero di giustificativo** **non** è stata rimossa dall'impostazione dei nomi del giornale di registrazione. Questa opzione è ancora supportata quando il giustificativo contiene solo tipi di conto CoGe. I clienti devono fare attenzione quando utilizzano questa impostazione, perché il giustificativo non verrà registrato se utilizzano l'opzione **Un solo numero di giustificativo**, ma poi immettono più di un cliente, fornitore, banca, cespite o progetto. Inoltre, i clienti possono ancora immettere una combinazione di tipi di conto CoGe secondario, ad esempio un pagamento in un singolo giustificativo contenente i tipi di conto **Fornitore**/**Banca**.

## <a name="why-use-one-voucher"></a>Perché utilizzare la funzionalità Un giustificativo?

In seguito ad alcune conversazioni con i clienti, Microsoft ha compilato il seguente elenco di scenari in cui i clienti utilizzano la funzionalità Un giustificativo e un elenco dei motivi per cui utilizzano questa funzionalità. Alcuni di questi requisiti aziendali possono essere soddisfatti utilizzando soltanto Un giustificativo. Tuttavia, per molti scenari, esistono alternative che possono soddisfare gli stessi requisiti aziendali.

### <a name="scenarios-that-require-one-voucher"></a>Scenari che richiedono Un giustificativo

I seguenti scenari possono essere soddisfatti solo utilizzando la funzionalità Un giustificativo. Se l'organizzazione ha uno di questi scenari, è necessario consentire l'immissione di più transazioni in un giustificativo impostando il parametro **Consenti più transazioni in un giustificativo** nella pagina **Parametri di contabilità generale**. Tali gap funzionali verranno corretti con altre funzionalità nelle versioni successive.

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Registrare i pagamenti cliente o fornitore in formato riepilogativo in un conto bancario

**Scenario** Un'organizzazione comunica un elenco di fornitori e importi alla banca e quest'ultima utilizza questo elenco per pagare i fornitori per conto dell'organizzazione. La banca registra la somma dei pagamenti come singolo prelievo sul conto bancario.

Il riepilogo dei pagamenti fornitore è in genere supportato solo mediante Un giustificativo. Ogni fornitore viene immesso come riga separata per gestire i dettagli nella contabilità secondaria della contabilità fornitori. Tuttavia, l'importo riepilogativo di tutti i pagamenti viene compensato in un'unica riga per il conto bancario. Di conseguenza, il prelievo viene visualizzato come singolo importo riepilogativo nella contabilità secondaria della banca.

**Scenario** Un'organizzazione deposita i pagamenti cliente o i pagamenti clienti sui depositi bancari per conto dell'organizzazione e il deposito viene visualizzato come somma forfettaria nel conto bancario.

Il riepilogo dei pagamenti cliente è in genere supportato mediante la funzionalità di deposito. Se tuttavia si utilizza il "bridging" sul metodo di pagamento, questo scenario viene supportato solo con la funzionalità Un giustificativo. I pagamenti cliente vengono immessi nello stesso modo descritto per il riepilogo dei pagamenti fornitore.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Meccanismo per raggruppare le transazioni da un evento aziendale

**Scenario** Un'organizzazione ha un singolo evento aziendale che attiva più transazioni. Tuttavia, il reparto di Contabilità desidera visualizzare le voci contabili insieme per garantire un controllo più preciso.

Se un'organizzazione deve visualizzare insieme le voci contabili di un evento aziendale, deve utilizzare la funzionalità Un giustificativo. 

### <a name="country-specific-features"></a>Funzionalità specifiche del paese

**Scenario** La funzionalità Documento amministrativo unico (SAD) per la Polonia richiede attualmente l'utilizzo di un singolo giustificativo. Finché un'opzione di raggruppamento è disponibile per questa funzionalità, è necessario continuare a utilizzare la funzionalità Un giustificativo. Possono esserci ulteriori funzionalità specifiche del paese che richiedono la funzionalità Un giustificativo.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Giornale di registrazione pagamenti anticipati clienti con imposte su più "righe"

In questo scenario, i clienti nel singolo giustificativo sono lo stesso cliente, poiché la transazione simula le righe di un ordine cliente. Il pagamento anticipato deve essere immesso in un singolo giustificativo, poiché il calcolo dell'imposta deve essere eseguito sulle "righe" del singolo pagamento effettuato dal cliente.

### <a name="customer-reimbursement"></a>Rimborso cliente

**Scenario** Un cliente effettua un pagamento anticipato di un ordine e le righe dell'ordine hanno imposte differenti che devono essere registrate per il pagamento anticipato. Il pagamento anticipato cliente è una transazione che simula le righe dell'ordine, di modo che l'imposta appropriata possa essere registrata per l'importo in ogni riga.

Se l'attività periodica di rimborso viene eseguita dal modulo Contabilità clienti, viene creata una transazione per spostare il saldo da un cliente a un fornitore. Per questo scenario, Un giustificativo deve essere utilizzato per rimborsare il cliente.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Gestione cespiti: rideterminazione ammortamento, divisione cespite, calcolo ammortamento su dismissione
Le seguenti transazioni cespiti creano anche più transazioni in un singolo giustificativo:

- Viene effettuata un'acquisizione aggiuntiva su un cespite e viene calcolata la rideterminazione dell'ammortamento.
- Un cespite viene diviso.
- Viene abilitato un parametro per calcolare l'ammortamento su dismissione e quindi viene dismesso il cespite.
- Una data di messa in servizio di un cespite è precedente alla data di acquisizione. Di conseguenza, una rettifica dell'ammortamento viene registrata.

### <a name="bills-of-exchange-and-promissory-notes"></a> Effetti attivi ed effetti passivi
Gli effetti attivi ed effetti passivi richiedono l'utilizzo di Un giustificativo, poiché le transazioni spostano il saldo del cliente o del fornitore da un conto CoGe Contabilità fornitori o Contabilità clienti a un altro, in base allo stato del pagamento.

## <a name="scenarios-that-dont-require-one-voucher"></a>Scenari che non richiedono Un giustificativo

I seguenti scenari possono essere soddisfatti differentemente e non devono utilizzare la funzionalità Un giustificativo.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Registrare i pagamenti cliente in formato riepilogativo nel conto bancario

Un'organizzazione deposita i pagamenti cliente o i pagamenti clienti sui depositi bancari per conto dell'organizzazione e il deposito viene visualizzato come somma forfettaria nel conto bancario.

Il riepilogo dei pagamenti cliente è supportato mediante la funzionalità di deposito quando la "registrazione compensativa" non viene utilizzata per il metodo di pagamento.

### <a name="netting"></a>Compensazione

Nella compensazione i saldi per un fornitore e il cliente si compensano l'un con l'altro, perché il fornitore e il cliente sono la stessa parte. Questo approccio riduce al minimo lo scambio di denaro tra un'organizzazione e la parte del cliente/fornitore.

La compensazione può essere ottenuta immettendo l'incremento e la diminuzione in giustificativi separati e registrando quindi la contropartita in un conto CoGe di compensazione.

### <a name="post-in-summary-to-the-general-ledger"></a>Registrare in formato riepilogativo nella contabilità generale

Le organizzazioni spesso desiderano registrare nella contabilità generale in formato riepilogativo per ridurre la quantità di dati. In genere, tali organizzazioni richiedono che vengano mantenuti i dettagli delle transazioni. Quando la registrazione viene eseguita in formato riepilogativo mediante un singolo giustificativo, i dettagli della transazione non sono noti e non possono essere gestiti.

- Poiché al momento non è possibile mantenere i dettagli delle transazioni, è consigliabile che l'organizzazione **non** utilizzi la funzionalità Un giustificativo per registrare in formato riepilogativo.
- Dopo avere rimosso il supporto per la funzionalità Un giustificativo, i framework Documento di origine e Contabilità possono essere implementati nei giornali di registrazione. Questi framework manterranno quindi i dettagli delle transazioni e supporteranno riepiloghi nella contabilità generale.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Liquidare più pagamenti non registrati con la stessa fattura

Questo scenario è tipico soprattutto delle organizzazioni di vendita al dettaglio in cui i clienti possono utilizzare molteplici metodi di pagamento per pagare gli acquisti. In questo scenario, l'organizzazione deve poter registrare i molteplici pagamenti non registrati e liquidarli a fronte della fattura cliente.

Una nuova funzionalità aggiunta in Microsoft Dynamics 365 for Operations versione 1611 (novembre 2016) consente di liquidare un'unica fattura con più pagamenti non registrati. I pagamenti cliente multipli non devono più essere immessi in un singolo giustificativo.

### <a name="import-bank-statement-transactions"></a>Importa transazioni rendiconto bancario

Spesso le banche pagano e ricevono pagamenti per conto di un'organizzazione e tali transazioni vengono registrate in Finance attraverso un file ricevuto dalla banca. Le organizzazioni spesso desiderano raggruppare quelle transazioni utilizzando il numero di rendiconto bancario nel file. Poiché ogni transazione viene visualizzata in dettaglio nel rendiconto bancario, non è necessario alcun riepilogo nella contabilità secondaria della banca.

Le transazioni possono essere raggruppate utilizzando altri campi del giornale di registrazione, ad esempio il numero batch del giornale di registrazione o il numero di documento.


### <a name="transfer-balances"></a>Trasferisci saldi

Un'organizzazione potrebbe dover trasferire un saldo da un fornitore a un altro, a causa di un errore o perché un altro fornitore ha assunto la passività. I trasferimenti di questo tipo si hanno anche per i tipi di conto, quali **Cliente** e **Banca**.

I trasferimenti del saldo da un conto (fornitore, cliente, bancario e così via) a un altro conto possono essere effettuati tramite giustificativi separati e la contropartita può essere registrata in un conto CoGe di compensazione.

### <a name="enter-beginning-balances"></a>Immettere saldi iniziali

Le organizzazioni spesso immettono saldi iniziali per conti CoGe secondari (fornitori, clienti, cespiti e così via) come transazione giustificativo. I saldi iniziali per ogni conto CoGe secondario possono essere immessi come giustificativi separati e la contropartita può essere registrata in un conto CoGe di compensazione.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Correggere la voce contabile di un documento fornitore o cliente registrato

Un'organizzazione potrebbe dover correggere la contabilità generale della contabilità clienti o della contabilità fornitori per una voce contabile di una fattura registrata, ma tale fattura non può essere annullata o corretta tramite un altro meccanismo.

Se occorre effettuare una correzione nel conto CoGe della Contabilità fornitori o della Contabilità clienti, la rettifica deve essere effettuata direttamente nel conto CoGe. La correzione non può essere effettuata eseguendo la registrazione tramite il fornitore o il cliente. Questo approccio richiede l'esecuzione della correzione durante un "tempo di inattività", di modo che il conto CoGe possa consentire temporaneamente l'immissione manuale.

### <a name="the-system-allows-it"></a>"Consentito dal sistema"

Le organizzazioni spesso utilizzano la funzionalità Un giustificativo principalmente perché il sistema ne consente l'utilizzo, senza conoscere le implicazioni.
