---
title: Scissione dei pagamenti per fatture emesse alla Pubblica Amministrazione
description: "In questo argomento vengono fornite informazioni sullo schema di contabilità di scissione dei pagamenti."
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

# <a name="split-payment-for-invoices-issued-to-the-public-administration"></a>Scissione dei pagamenti per fatture emesse alla Pubblica Amministrazione

[!include[banner](../includes/banner.md)]


In questo argomento vengono fornite informazioni sullo schema di contabilità di scissione dei pagamenti.

Lo schema di contabilità di scissione dei pagamenti è valido per la vendita di merci e servizi resi alla Pubblica amministrazione. Il meccanismo di scissione dei pagamenti trasferisce l'obbligo di pagamento delle imposte alla Pubblica amministrazione che sarà obbligata a pagare solo la base imponibile al fornitore. L'IVA viene accreditata in un conto riservato specifico. Le società con relazioni con la Pubblica amministrazione devono assicurarsi che l'IVA relativa venga registrata nelle vendite del registro, senza contribuire al pagamento IVA periodico.

## <a name="prerequisites"></a>Prerequisiti
Nella seguente tabella vengono visualizzati i prerequisiti che devono essere validi prima di iniziare.

**Categoria**

**Prerequisito**

**Impostazioni**: registrazione IVA

Creare un nuovo conto principale per la scissione dei pagamenti IVA, quindi selezionare **IVA** nel campo **Tipo di registrazione**. Creare un gruppo di registrazione per la scissione dei pagamenti IVA, quindi selezionare il conto CoGe creato nei campi **IVA a debito**, **IVA a credito** e **Conto di liquidazione**.

**Impostazione: **IVA

Creare una **Fascia IVA** per la Pubblica amministrazione, quindi selezionare l'opzione **Scissione dei pagamenti**. Creare un codice IVA per la scissione dei pagamenti IVA. Impostare il valore utilizzabile per il paese, quindi aggiungere il codice IVA in **Fascia IVA** e **Fascia IVA articoli**.

**Impostazioni:** contabilità clienti

Impostare la **Sequenza numerica** per il riferimento **Giustificativo scissione dei pagamenti** nei parametri di contabilità fornitori. Selezionare il codice di sequenza numerica per registrare l'IVA stornata per le fatture nel meccanismo di scissione dei pagamenti per il riferimento **Giustificativo scissione dei pagamenti**. Creare un gruppo di sequenze numeriche per il cliente - Pubblica amministrazione. Nella scheda **Sequenze numeriche**, selezionare la riga con il riferimento **Giustificativo fattura a testo libero**, quindi fare clic sul pulsante **Gruppo**. Nella pagina **Gruppi di sequenze numeriche**, creare un nuovo gruppo, quindi selezionare una sequenza numerica per i riferimenti seguenti:

-   Giustificativo fattura a testo libero
-   Giustificativo nota di accredito a testo libero
-   Giustificativo fattura cliente
-   Giustificativo nota di accredito vendita

Impostare **Fascia IVA** e **Gruppo di sequenze numeriche** per i Clienti- Pubblica amministrazione nella pagina **Tutti i clienti**.

**Impostazioni:** libro IVA e sezione Libro IVA

Creare un nuovo libro IVA per registrare fatture alla Pubblica amministrazione. Creare una nuova sezione per il libro IVA.

**Transazioni correlate**

-   Registrare una vendita a un cliente con le impostazioni di scissione dei pagamenti.
-   Registrare una fattura a testo libero per un cliente con impostazioni di scissione dei pagamenti.

## <a name="working-with-the-split-payment-invoices"></a>Utilizzo delle fatture di scissione dei pagamenti
Quando si registra la fattura, ad esempio un ordine cliente, una fattura a testo libero o una fattura di progetto. Con la fascia IVA di scissione dei pagamenti, le transazioni IVA di storno con i relativi codici di imposta vengono registrate per eliminare l'imposta accumulata. Per ridurre il saldo cliente, una transazione cliente per l'importo IVA viene creata e automaticamente compensata con la fattura durante la registrazione della fattura. In tal modo, il saldo cliente viene ridotto dell'importo IVA. **Nota:** le transazioni IVA registrate con l'opzione **Scissione dei pagamenti** selezionata sono escluse dal processo di pagamento IVA. Le fatture create utilizzando il processo di scissione dei pagamenti hanno una "S" nel tag &lt;EsigibilitaIVA&gt;.

### <a name="booking-example-for-sales-invoice"></a>Esempio di prenotazione per la fattura di vendita

Nella seguente tabella è riportato un esempio di transazioni di contabilità generale per due transazioni cliente create per una fattura di scissione dei pagamenti.

** **

**Conto**

**Dare**

**Avere**

**Contabilizzazione fattura**

Cliente\_Società pubblica

1220

Ricavi vendite

1000

Scissione dei pagamenti IVA

220

**Eliminazione debito IVA**

Cliente\_Società pubblica

220

Scissione dei pagamenti IVA

220

 




