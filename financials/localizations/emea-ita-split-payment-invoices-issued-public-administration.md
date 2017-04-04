---
title: Pagamento diviso per le fatture ha rilasciato in Amministrazione pubblica
description: "In questo argomento vengono fornite informazioni sullo schema di contabilità di pagamento divise."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TaxBookSection, TaxGroup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 261314
ms.assetid: 31b20504-a9e7-4d8e-b290-92e6e80a9ff4
ms.search.region: Italy
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 6bb98cc72c2ec0c1551412dd39d5bea3ce10e2cd
ms.openlocfilehash: 55027a762e62c672532a92fc9d0a9a6cfcab051b
ms.lasthandoff: 03/31/2017


---

# <a name="split-payment-for-invoices-issued-to-the-public-administration"></a>Pagamento diviso per le fatture ha rilasciato in Amministrazione pubblica

In questo argomento vengono fornite informazioni sullo schema di contabilità di pagamento divise.

Lo schema di contabilità di pagamento da dividere è valido per la vendita di merci e servizi resi a pubblica amministrazione. Il meccanismo di pagamento Dividi di trasferisce obbligo di pagamento VAT a pubblica ufficio che sarà obbligatorio per pagare solo la base imponibile al fornitore. L'VAT viene accreditata sul conto prenotato specifico. Le società con relazioni con la pubblica ufficio devono essere certi che l'VAT venga registrata rilevante per vendite del registro, senza procedere al pagamento VAT periodico.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

**Category**

**Prerequisite**

** Attrezzaggio: ** Registrazione VAT

Creare un nuovo conto principale per il pagamento VAT dividere e quindi selezionare ** VAT ** ** tipo di registrazione ** nel campo. Creare un gruppo registrazione per dividere il pagamento VAT quindi selezionare il conto CoGe creato ** VAT a debito, ** ** VAT a credito ** e ** conto di liquidazione ** campi.

**Impostazione: **IVA

Creare ** alla fascia VAT ** pubblica per la gestione e quindi selezionare ** dividi pagamento ** l'opzione. Creare un codice VAT per dividere il pagamento VAT. Impostare il valore utilizzabile per il paese e aggiungere il codice VAT in ** fascia VAT e ** ** fascia VAT articoli **.

** Attrezzaggio: ** Contabilità clienti

Impostare ** sequenza numerica ** ** per dividere il giustificativo di pagamento ** il riferimento nei parametri di contabilità fornitori. Selezionare il codice di sequenza numerica per registrare l'VAT invertita per le fatture nel meccanismo di pagamento Dividi ** per dividere il giustificativo di pagamento ** il riferimento. Creare un gruppo di sequenze numeriche per il cliente - pubblica amministrazione. ** Sequenze numeriche ** la scheda, quindi selezionare la riga con ** giustificativi fattura a testo libero ** il riferimento e fare clic su ** gruppo ** il pulsante. ** Gruppi di sequenze numeriche ** nella pagina, creare un nuovo gruppo e selezionare una sequenza numerica per i riferimenti seguenti:

-   Giustificativo fattura a testo libero
-   Giustificativo nota di accredito a testo libero
-   Giustificativo fattura cliente
-   Giustificativo nota di accredito vendita

Impostare ** alla fascia VAT ** e ** gruppo di sequenze numeriche ** per l'amministrazione di Cliente- pubblico ** tutti i clienti ** nella pagina.

** Attrezzaggio: ** Area del libro VAT e del libro VAT

Creare un nuovo libro VAT per le fatture a pubblica amministrazione. Creare una nuova area per il libro VAT.

**Transazioni correlate**

-   Consente di registrare una vendita a un cliente con le impostazioni di pagamento divise.
-   Registrare una fattura a testo libero per un cliente con le impostazioni di pagamento divise.

## <a name="working-with-the-split-payment-invoices"></a>Utilizzo delle fatture di pagamento Dividi
Quando si registra la fattura, ad esempio un ordine cliente, una fattura a testo libero, o fattura di progetto. con la fascia VAT di pagamento Dividi, le transazioni di storno VAT ai codici VAT rilevanti vengono registrate per risolvere le imposte che accumulata. Per ridurre il saldo cliente, una transazione cliente per l'importo VAT verrà creata automaticamente e verrà compensata con la fattura come registrazione fatture. Si riduce il saldo del cliente dall'importo VAT. ** Nota: ** Le transazioni VAT registrate con ** pagamento diviso ** l'opzione selezionata vengono escluse dal processo di liquidazione VAT. eInvoice creati utilizzando il processo di pagamento Dividi hanno una " S" nel tag &lt; esigibilitaIVA&gt;.

### <a name="booking-example-for-sales-invoice"></a>Esempio di prenotazione per la fattura di vendita

Nella seguente tabella è riportato un esempio di transazioni di contabilità generale per due transazioni cliente сreated per una fattura di pagamento divise.

** **

**Conto**

**Debit**

**Credit**

** Contabilità fatture **

Società di utilizzo\_cliente

1220

Rendita da vendite

1000

Pagamento VAT diviso

220

** Eliminazione di debito VAT **

Società di utilizzo\_cliente

220

Pagamento VAT diviso

220

 


