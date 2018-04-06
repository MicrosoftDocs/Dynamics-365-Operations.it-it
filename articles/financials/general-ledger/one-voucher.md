---
title: Un giustificativo
description: "Un giustificativo per giornali di registrazione finanziari (giornale di registrazione generale, giornale di registrazione cespiti, giornali di registrazione pagamenti fornitore e così via) consente di immettere più transazioni di giornali di registrazione secondari nel contesto di un singolo giustificativo."
author: kweekley
manager: AnnBe
ms.date: 03/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 
ms.translationtype: HT
ms.sourcegitcommit: 3831a6b5ec458495134b4b490d33a9acd76b6d2e
ms.openlocfilehash: 76ea8470786bd50896400a65564d698d96119d6f
ms.contentlocale: it-it
ms.lasthandoff: 03/20/2018

---

# <a name="one-voucher"></a>Un giustificativo

[!include[banner](../includes/banner.md)]

> [!NOTE]
>  Questa funzionalità sarà inclusa in Dynamics 365 for Finance and Operations versione 8.0 che sarà disponibile nella versione Spring '18.   

<a name="what-is-one-voucher"></a>Che cos'è "Un giustificativo"?
======================

La funzionalità esistente per giornali di registrazione finanziari (giornale di registrazione generale, giornale di registrazione cespiti, giornali di registrazione pagamenti fornitore e così via) consente di immettere più transazioni di giornali di registrazione secondari nel contesto di un singolo giustificativo. Questa funzionalità è denominata "Un giustificativo". È possibile creare Un giustificativo utilizzando uno dei metodi seguenti:

-   Impostare il nome del giornale di registrazione (**Contabilità generale** \> **Impostazione giornale di registrazione** \>**Nomi giornale di registrazione**) in modo da impostare il campo **Nuovo giustificativo** su **Un solo numero di giustificativo**. Ogni riga che si aggiunge al giornale di registrazione viene ora inclusa nello stesso giustificativo. Poiché ogni riga viene aggiunta nello stesso giustificativo, il giustificativo può essere inserito come giustificativo plurimo, ad esempio un conto/conto di contropartita nella stessa riga, o come combinazione.

[![Riga singola](./media/same-line.png)](./media/same-line.png)

-   Immettere un giustificativo plurimo in cui non sono presenti conti di contropartita.

[![Giustificativo plurimo](./media/Multi-line.png)](./media/Multi-line.png)

-   Immettere un giustificativo in cui sia il conto che il conto di contropartita contengono un tipo di conto secondario, ad esempio fornitore/fornitore, cliente/cliente, fornitore/cliente o banca/banca.

[![Giustificativo contabilità generale secondaria](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problemi con un giustificativo
=======================

La funzionalità Un giustificativo genera problemi durante liquidazione, calcolo delle imposte, riconciliazione tra contabilità secondaria e contabilità generale, creazione di report finanziari e altro. (Ad esempio, per ulteriori informazioni sui problemi che possono verificarsi durante la liquidazione, vedere [Giustificativo singolo con più record cliente o fornitore](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records)). Per funzionare e segnalare correttamente, questi processi e questi report necessitano dei dettagli delle transazioni. Sebbene alcuni scenari funzionino comunque correttamente, in base alle impostazioni dell'organizzazione, si verificano spesso problemi quando si immettono più transazioni in un unico giustificativo.

Ad esempio, si registra il giustificativo plurimo seguente.

[![Esempio](./media/example.png)](./media/example.png)

Si genera quindi il report **Spese per fornitore** nell'area di lavoro **Informazioni finanziarie dettagliate**. Il report raggruppa i saldi del conto spese per gruppo di fornitori e quindi per fornitore. Durante la generazione del report, il sistema non può determinare quali fornitori/gruppi di fornitori hanno sostenuto la spesa di 250,00. Poiché mancano i dettagli della transazione, il sistema suppone che l'intero importo di 250,00 sia stato sostenuto dal primo fornitore indicato nel giustificativo. L'importo di 250,00, incluso nel saldo del conto principale 600120, viene quindi visualizzato sotto quel gruppo fornitori/fornitore. È molto probabile che il primo fornitore nel giustificativo non fosse il fornitore appropriato, di conseguenza il report non è corretto.

[![Spese](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>Utilizzo futuro della funzionalità Un giustificativo
=========================

A causa dei problemi descritti in precedenza, la funzionalità Un giustificativo diventerà obsoleta. Tuttavia, poiché si presentano discontinuità funzionali che dipendono da questa funzionalità, la funzionalità non diventerà obsoleta tutto d'un tratto. Si utilizzerà invece la seguente programmazione: 

-   **Versione di primavera 2018** - La funzionalità verrà disattivata per impostazione predefinita tramite un parametro della contabilità generale. È tuttavia possibile attivare la funzionalità se l'organizzazione ha uno scenario che rientra nelle discontinuità di scenario aziendale indicate più avanti in questo argomento.

    -   Se un cliente dispone di uno scenario aziendale che non richiede la funzionalità Un giustificativo, non attivare la funzionalità. Questi "bug" non verranno corretti nelle aree identificate oltre in questo argomento se questa funzionalità viene utilizzata anche se un'altra soluzione esiste.

    -   Smettere di utilizzare Un giustificativo per le integrazioni in Microsoft Dynamics 365 Finance and Operations, a meno che la funzionalità sia necessaria per uno dei gap funzionali.

-   **Fall 2018 e versioni successive** - Verranno corretti gap funzionali. Dopo il completamento dei gap funzionali, la funzionalità Un giustificativo viene disattivata in modo permanente.

<a name="why-use-one-voucher"></a>Perché utilizzare la funzionalità Un giustificativo?
====================

In seguito ad alcune conversazioni con i clienti, abbiamo compilato il seguente elenco di scenari in cui i clienti utilizzano la funzionalità Un giustificativo e un elenco dei motivi per cui utilizzano questa funzionalità. Alcuni di questi requisiti aziendali possono essere soddisfatti utilizzando soltanto Un giustificativo. Tuttavia, per molti scenari, esistono alternative che possono soddisfare gli stessi requisiti aziendali.

<a name="scenarios-that-require-one-voucher"></a>Scenari che richiedono Un giustificativo
----------------------------------

I seguenti scenari possono essere soddisfatti solo utilizzando la funzionalità Un giustificativo. Tali gap funzionali verranno corretti con altre funzionalità nella versione Fall 2018 e versioni successive.

-   **Registrare i pagamenti cliente o fornitore in formato riepilogativo in un conto bancario**

    -   Un'organizzazione comunica un elenco di fornitori e importi alla banca e quest'ultima utilizza questo elenco per pagare i fornitori per conto dell'organizzazione. La banca registra la somma dei pagamenti come singolo prelievo sul conto bancario.

>   Il riepilogo dei pagamenti fornitore è in genere supportato solo mediante Un giustificativo. Ogni fornitore viene immesso come riga separata per gestire i dettagli nella contabilità secondaria della contabilità fornitori, ma l'importo di riepilogo per tutti i pagamenti è spostato su una riga singola per il conto bancario. Di conseguenza, il prelievo viene visualizzato come singolo importo riepilogativo nella contabilità secondaria della banca.

-   Un'organizzazione deposita i pagamenti cliente o i pagamenti clienti sui depositi bancari per conto dell'organizzazione e il deposito viene visualizzato come somma forfettaria nel conto bancario.

>   Il riepilogo dei pagamenti cliente è in genere supportato mediante la funzionalità di deposito. Se tuttavia si utilizza il "bridging" sul metodo di pagamento, questo scenario viene supportato solo con la funzionalità Un giustificativo. I pagamenti cliente vengono immessi nello stesso modo descritto per il riepilogo dei pagamenti fornitore.

-   **Meccanismo per raggruppare le transazioni da un evento aziendale**

    -   Un'organizzazione ha un singolo evento aziendale che attiva più transazioni. Tuttavia, il reparto di Contabilità desidera visualizzare le voci contabili insieme per garantire un controllo più preciso.

>   Se un'organizzazione deve visualizzare insieme le voci contabili di un evento aziendale, deve utilizzare la funzionalità Un giustificativo. 

-   **Funzionalità specifiche del paese**

 -   La funzionalità Documento amministrativo unico (SAD) per la Polonia richiede attualmente l'utilizzo di un singolo giustificativo. Finché un'opzione di raggruppamento è disponibile per questa funzionalità, è necessario continuare a utilizzare la funzionalità Un giustificativo. Possono esserci ulteriori funzionalità specifiche del paese che richiedono la funzionalità Un giustificativo.

-   **Giornale di registrazione pagamenti anticipati clienti con imposte su più "righe"**

 -   Un cliente effettua un pagamento anticipato per un ordine e le righe dell'ordine hanno imposte differenti che devono essere registrate per il pagamento anticipato. Il pagamento anticipato cliente è una transazione che simula le righe dell'ordine, di modo che l'imposta appropriata possa essere registrata per l'importo in ogni riga.

In questo scenario, i clienti nel singolo giustificativo sono lo stesso cliente, poiché la transazione simula le righe di un ordine cliente. Il pagamento anticipato deve essere immesso in un singolo giustificativo, poiché il calcolo dell'imposta deve essere eseguito sulle "righe" del singolo pagamento effettuato dal cliente.

-   **Gestione cespiti: rideterminazione ammortamento, divisione cespite, calcolo ammortamento su dismissione**

Anche le seguenti transazioni cespiti creano più transazioni in un singolo giustificativo:
-   Viene effettuata un'acquisizione aggiuntiva su un cespite e viene calcolata la rideterminazione dell'ammortamento.
-   Un cespite viene diviso.
-   Viene abilitato un parametro per calcolare l'ammortamento su dismissione e quindi viene dismesso il cespite.

<a name="scenarios-that-dont-require-one-voucher"></a>Scenari che non richiedono Un giustificativo
----------------------------------------

I seguenti scenari possono essere soddisfatti differentemente e non devono utilizzare la funzionalità Un giustificativo.

-   **Registrare i pagamenti cliente in formato riepilogativo nel conto bancario**

Un'organizzazione deposita i pagamenti cliente o i pagamenti clienti sui depositi bancari per conto dell'organizzazione e il deposito viene visualizzato come somma forfettaria nel conto bancario.

Il riepilogo dei pagamenti cliente è supportato mediante la funzionalità di deposito quando la registrazione compensativa non viene utilizzata per il metodo di pagamento.

-   **Compensazione**

Nella compensazione, i saldi per un fornitore e il cliente si compensano l'un con l'altro perché il fornitore e il cliente sono la stessa parte. Questo approccio riduce al minimo lo scambio di denaro tra un'organizzazione e la parte del cliente/fornitore.

La compensazione può essere ottenuta immettendo l'incremento e la diminuzione in giustificativi separati e registrando la contropartita in un conto CoGe di compensazione.

-   **Registrare in formato riepilogativo nella contabilità generale**

Le organizzazioni spesso desiderano registrare nella contabilità generale in formato riepilogativo per ridurre la quantità di dati. In genere, le organizzazioni richiedono che vengano mantenuti i dettagli delle transazioni. Quando la registrazione viene eseguita in formato riepilogativo mediante un singolo giustificativo, i dettagli della transazione non sono noti e non possono essere gestiti.

   -   Poiché al momento non è possibile mantenere i dettagli delle transazioni, è consigliabile non utilizzare la funzionalità Un giustificativo per registrare nel riepilogo.
   -   Dopo avere rimosso il supporto per la funzionalità Un giustificativo, è possibile implementare i framework Documento di origine e Contabilità nei giornali di registrazione. Questi framework manterranno quindi i dettagli delle transazioni e supporteranno riepiloghi nella contabilità generale.

-   **Liquidare più pagamenti non registrati con la stessa fattura**

Questo scenario è tipico soprattutto delle organizzazioni di vendita al dettaglio in cui i clienti possono utilizzare molteplici metodi di pagamento per pagare gli acquisti. In questo scenario, l'organizzazione deve poter registrare i molteplici pagamenti non registrati e liquidarli a fronte della fattura cliente.

Una nuova funzionalità aggiunta in Microsoft Dynamics 365 for Operations versione 1611 (novembre 2016) consente di liquidare un'unica fattura con più pagamenti non registrati. I pagamenti cliente multipli non devono più essere immessi in un singolo giustificativo.

-   **Importa transazioni rendiconto bancario**

Spesso le banche pagano e ricevono pagamenti per conto di un'organizzazione e queste transazioni vengono registrate in Finance and Operations attraverso un file ricevuto dalla banca. Le organizzazioni spesso desiderano raggruppare quelle transazioni utilizzando il numero di rendiconto bancario nel file. Poiché ogni transazione viene visualizzata in dettaglio nel rendiconto bancario, non è necessario alcun riepilogo nella contabilità secondaria della banca.

Le transazioni possono essere raggruppate utilizzando altri campi del giornale di registrazione, ad esempio il numero batch del giornale di registrazione o il numero di documento.

-   **Trasferisci saldi**

Un'organizzazione potrebbe dover trasferire un saldo da un fornitore a un altro, a causa di un errore o perché un altro fornitore ha assunto la passività. I trasferimenti di questo tipo si hanno anche per i tipi di conto ad esempio conti bancari o cliente.

I trasferimenti del saldo da un conto (Fornitore, Cliente, conto bancario e così via) a un altro conto possono essere effettuati tramite giustificativi separati e la contropartita può essere registrata in un conto CoGe di compensazione.

-   **Immettere saldi iniziali**

Le organizzazioni spesso immettono saldi iniziali per conti CoGe secondari (fornitori, clienti, cespiti e così via) come transazione giustificativo. I saldi iniziali per ogni conto CoGe secondario possono essere immessi come giustificativi separati e la contropartita può essere registrata in un conto CoGe di compensazione.

-   **Correggere la voce contabile di un documento fornitore o cliente registrato**

Un'organizzazione potrebbe dover correggere la contabilità generale della contabilità clienti o della contabilità fornitori per una voce contabile di una fattura registrata, ma tale fattura non può essere annullata o corretta tramite un altro meccanismo.

Se occorre effettuare una correzione nel conto CoGe della contabilità fornitori o della contabilità clienti, la rettifica deve essere effettuata direttamente nel conto CoGe. La correzione non può essere effettuata eseguendo la registrazione tramite il fornitore o il cliente. Questo approccio richiede l'esecuzione della correzione durante un "tempo di inattività", di modo che il conto CoGe possa consentire temporaneamente l'immissione manuale.

-   **"Consentito dal sistema"**

Le organizzazioni spesso utilizzano la funzionalità Un giustificativo principalmente perché il sistema ne consente l'utilizzo, senza conoscere le implicazioni.

