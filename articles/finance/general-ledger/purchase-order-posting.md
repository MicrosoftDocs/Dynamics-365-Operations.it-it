---
title: Registrazione ordine fornitore
description: Questo articolo descrive la scheda Ordine fornitore della pagina Profili di registrazione inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 38a9e2740232b18255109ba867fcdddd5b890774
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151034"
---
# <a name="purchase-order-posting"></a>Registrazione ordine fornitore

La scheda **Ordine fornitore** nella pagina **Profili di registrazione inventario** viene utilizzata per controllare la modalità di registrazione degli ordini fornitore nella contabilità generale. Due attività principali vengono registrate nella contabilità generale per un ordine fornitore: 

- Entrata prodotti
- Fattura

Affinché una transazione fisica (entrata prodotti) venga registrata nella contabilità generale per un ordine fornitore, devono essere selezionate le seguenti caselle di controllo:

- Nella pagina **Parametri di gestione articoli e magazzino** deve essere selezionata la casella di controllo **Registra il documento di trasporto nella contabilità generale**.
- Le caselle di controllo **Registra inventario fisico** e **Passività ratei all'entrata prodotti** della pagina **Gruppi di modelli di articoli**.

I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** per i seguenti tipi di registrazione:

- Costo dei materiali acquistati ricevuti
- Spese acquisto, non fatturate
- Acquisto, rateo

Affinché una transazione finanziaria (fattura) venga registrata nella contabilità generale per un ordine fornitore, devono essere soddisfatte le seguenti condizioni:

- La casella di controllo **Registra inventario finanziario** deve essere selezionata nella pagina **Gruppi di modelli di articoli** per l'articolo selezionato nella riga dell'ordine fornitore.
- I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** per i seguenti tipi di registrazione:
  - Costo dei materiali acquistati fatturati
  - Spese acquisto per prodotto
  - Spese acquisto da registrare nelle spese
  - Sconto (facoltativo)

## <a name="fixed-receipt-price-posting"></a>Registrazione del prezzo di entrata fisso

È possibile utilizzare il prezzo di entrata fisso come costo standard per un prodotto in alternativa alla selezione dell'opzione **Costo standard** nel campo **Modello di inventario** sulla pagina **Gruppi di modelli di articoli** per un articolo. La differenza principale è che quando si utilizza **Prezzo entrata fisso**, il prezzo di costo corrente verrà utilizzato per l'articolo al momento della registrazione dell'entrata in magazzino. Non è previsto alcun processo di rivalutazione dei costi per **Prezzo entrata fisso**; quando viene registrato un aggiornamento finanziario, al momento della registrazione viene utilizzato il prezzo di costo corrente. Se c'è una differenza tra il prezzo di costo utilizzato al momento dell'entrata e della fattura, lo scostamento verrà registrato nei conti profitti e perdite del prezzo di entrata fisso.

Per utilizzare un prezzo di entrata fisso per un prodotto, è necessario configurare quanto segue:

- Nella pagina **Gruppi di modelli di articoli**, seleziona le caselle di controllo **Registra inventario fisico** e **Prezzo entrata fisso**. 
- Nella pagina **Parametri di gestione articoli e magazzino** seleziona la casella di controllo **Registra il documento di trasporto nella contabilità generale**.
- Specifica i conti principali per i seguenti tipi di registrazione nella pagina **Profilo di registrazione inventario**:
  - Profitto sul prezzo di entrata fisso
  - Perdita sul prezzo di entrata fisso
  - Deviazione prezzo di entrata fisso

Per ulteriori informazioni, vedi [Prezzo di entrata fisso](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="purchase-charges-and-stock-variation-posting"></a>Spese di acquisto e registrazione di variazione scorte

Se prevedi di tenere conto delle spese di acquisto e delle variazioni delle scorte, effettua quanto segue:

- Nella pagina **Parametri contabilità fornitori** nella scheda **Fattura**, seleziona la casella di controllo **Registra nel conto di addebito nella contabilità generale**.
- Sulla pagina **Gruppi di modelli di articoli** relativa all'articolo selezionato nella riga dell'ordine fornitore, seleziona le caselle di controllo **Registra inventario fisico**, **Registra inventario finanziario**, e **Passività ratei all'entrata prodotti**.
- Sulla pagina **Parametri di approvvigionamento**, seleziona la casella di controllo **Genera spese sull'entrata prodotti**.
- Nella pagina **Parametri di gestione articoli e magazzino** seleziona la casella di controllo **Registra il documento di trasporto nella contabilità generale**.

Nella pagina **Profilo di registrazione inventario**, è necessario specificare i conti principali per i seguenti tipi di registrazione:

- Spese acquisto, non fatturate
- Spese acquisto per prodotto
- Variazione scorte

> [!NOTE]
> Il tipo di registrazione **Addebito** non viene utilizzato quando il parametro **Registra nel conto di addebito nella contabilità generale** è selezionato.

Per ulteriori informazioni, vai a [Principio di contabilità generale di registrazione nel conto di addebito](/supply-chain/cost-management/post-to-charge-account-accounting-principle.md).

## <a name="sample-posting-profile-configuration"></a>Esempio di configurazione del profilo di registrazione

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio:

- La colonna **Conto di compensazione** indica che il tipo di registrazione è un conto di compensazione. L'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva. 
- La colonna **P/F** indica **P** per la pubblicazione fisica e **F** per la registrazione finanziaria. 
- La colonna **Segui** indica se il conto principale per un tipo di registrazione specifico è in genere uguale a un altro tipo di registrazione. Il valore nella colonna indica il tipo di registrazione generalmente utilizzato.

> [!NOTE]
> I conti principali e i nomi di conti principali sono solo suggerimenti. Consigliamo<!--note from editor: Via Writing Style Guide.--> di collaborare con il tuo contabile per determinare la configurazione migliore per le tue esigenze aziendali.


| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere? | Conto di compensazione | P/F | Segui | Description |
|--------------|---------------------|-------------------------|----------------|----------------|--------------------|----|----------|-----------|
| Costo dei materiali acquistati ricevuti | 140100</br>140101 | Inventario dei materiali</br>Materiali spediti non fatturati | Cespite | Dare | Sì | P | Costo dei materiali acquistati fatturati | Utilizzato quando viene registrata un'entrata prodotti, l'offset per il conto è Spese acquisto, non fatturate. L'importo in questo conto viene automaticamente stornato quando viene registrata una fattura per l'ordine fornitore. |
| Spese acquisto, non fatturate | 600180 | Entrate materiali | Spese | Dare | Sì | P | |Utilizzato quando viene registrata un'entrata prodotti dell'ordine fornitore. Vengono creati due giustificativi per l'entrata per tenere traccia delle variazioni del prezzo di acquisto quando viene utilizzato il costo standard. La compensazione nel conto sul primo giustificativo è il rateo di acquisto. La compensazione nel secondo giustificativo è la somma dei conti Costo dei materiali acquistati ricevuti e Variazione prezzo di acquisto. Gli importi registrati in questo conto vengono automaticamente stornati quando viene registrata una fattura per l'ordine fornitore. |
| Costo dei materiali acquistati fatturati | 140100 | Inventario dei materiali | Cespite | Dare | Numero | V  |Costo dei materiali acquistati ricevuti | Utilizzato quando viene registrata una fattura dell'ordine fornitore. La compensazione sul conto è Spese acquisto per prodotto. Questo conto rappresenta l'inventario nel tuo stato patrimoniale. Il conto utilizzato è in genere lo stesso conto utilizzato per Costo delle unità consegnate e Costo delle unità fatturate per l'ordine cliente. |
| Spese acquisto per prodotto | 600180 | Entrata materiali | Spese | Credito | Sì | V  | |Utilizzato quando viene registrata una fattura dell'ordine fornitore. Vengono creati due giustificativi per la fattura per tenere traccia delle variazioni del prezzo di acquisto quando viene utilizzato il costo standard. L'offset su questo conto è Spese acquisto, non fatturate, usato nella registrazione e lo storno di entrate durante la registrazione delle fatture. Rappresenta i costi per le scorte acquistate con fatturazione non riportata nel conto di magazzino nello stato patrimoniale. È una registrazione di profitti e perdite per lo scostamento del prezzo di acquisto che si verifica più frequentemente negli acquisti di articoli con costo standard.|
| Profitto prezzo entrata fisso (Acquisti, profitto prezzo entrata fisso*) | 510310 | Scostamento prezzi di acquisto | Spese | Credito | Numero | V | Perdita sul prezzo di entrata fisso | Utilizzato quando viene registrata una fattura di un ordine fornitore ed esiste una differenza tra il prezzo fatturato e il costo predefinito per l'articolo. Questo conto viene utilizzato quando la differenza è superiore. Il conto di contropartita è il conto Deviazione prezzo di entrata fisso. |
| Perdita sul prezzo di entrata fisso (Acquisti, perdita sul prezzo di entrata fisso*) | 510310 | Scostamento prezzi di acquisto | Spese | Dare | Numero | V | Profitto sul prezzo di entrata fisso | Utilizzato quando viene registrata una fattura di un ordine fornitore ed esiste una differenza tra il prezzo fatturato e il costo predefinito per l'articolo. Questo conto viene utilizzato quando la differenza è inferiore. Il conto di contropartita è il conto Deviazione prezzo di entrata fisso. |
| Deviazione prezzo di entrata fisso (Acquisti, deviazione prezzo di entrata fisso*) | 140900 | Variazione scorte | Cespite | Entrambi | Numero | V  | |Utilizzato quando viene registrata una fattura di un ordine fornitore ed esiste una differenza tra il prezzo fatturato e il costo predefinito per l'articolo. Questo è il conto di contropartita per i conti profitti e perdite Prezzo di entrata fisso. |
| Addebito | N/D | N/D | N/D | N/D | N/D | N/D | N/D | Questo conto non è più usato. Usa invece la variazione scorte. |
| Variazione scorte | 600170 | Variazione scorte | Spese | Credito | Numero | Entrambi | | Questo conto viene utilizzato quando: <ul><li>C'è una differenza nel prezzo unitario tra l'entrata prodotto e la fattura.</li><li>Gli addebiti vengono registrati nell'articolo.</li><li>I costi indiretti sono stati<!--note from editor: Edit okay?--> aggiunti agli articoli acquistati. </li><li>La compensazione sul conto è il conto Spese acquisto, non fatturate.</li></ul> |
| Acquisto, rateo | 200140 | Acquisti accumulati | Passività | Credito | Y | P | |Utilizzato quando viene registrata un'entrata prodotti dell'ordine fornitore e l'opzione per accumulare importi di acquisto è abilitata. |
| IVA sospesa in entrata | 250500 | IVA sospesa | Passività | Credito | Y | Entrambi  | |Questo conto viene utilizzato quando si seleziona l'opzione **Registra imposta effettiva** in **Parametri di gestione articoli e magazzino** e hai un ordine fornitore con imposte. L'importo viene registrato quando si aggiorna fisicamente l'ordine fornitore (entrata prodotti) e stornato quando si registra l'ordine fornitore finanziariamente (fattura). |
| Entrata cespite (addebito cespite*) | 180100 | Cespiti tangibili | Cespite | Dare | N | Entrambi | Entrambi | Questo conto viene utilizzato quando si seleziona l'opzione nella riga dell'ordine fornitore per Cespiti. L'integrazione dell'ordine fornitore è stata configurata per acquisire il cespite al momento dell'entrata o della fattura del prodotto. Per ulteriori informazioni sull'integrazione dell'ordine fornitore cespite, vai a [Acquisire cespiti tramite approvvigionamento](/fixed-assets/acquire-assets-procurement). |
| Spese acquisto da registrare nelle spese | 618900 | Spese varie | Spese | Dare | N | Entrambi | |Utilizzato quando si registra un'entrata prodotti o una fattura per un ordine fornitore in cui gli articoli non sono stoccati o viene utilizzata una categoria di approvvigionamento. |
| Gestione pagamenti anticipati | 132190 | Risconti attivi | Cespite | Dare | N | Entrambi | | Utilizzato per l'elaborazione di una fattura di pagamento anticipato su un ordine fornitore. |


\*I valori mostrati tra parentesi rappresentano il valore utilizzato nel campo **Tipo di registrazione** sulla pagina **Transazioni giustificativo**. Puoi visualizzare il **Tipo di registrazione** nella pagina **Transazioni giustificativo** della scheda **Generale**.

## <a name="fixed-asset-posting-with-purchase-orders"></a>Registrazione cespiti con ordini fornitore

Se usi il modulo **Cespiti** e pianifichi l'acquisto di cespiti tramite ordini fornitore, è necessario configurare il tipo di registrazione **Entrata cespiti** sulla scheda **Ordine fornitore** della pagina **Profilo di registrazione dell'inventario**. Per ulteriori informazioni, vai a [Integrazione di cespiti](/fixed-assets/fixed-asset-integration.md) e [Creare e acquisire cespiti da Contabilità fornitori](/fixed-assets/tasks/create-acquire-assets-accounts-payable.md).

## <a name="prepayment-purchase-order-invoice-posting"></a>Registrazione della fattura dell'ordine fornitore con pagamento anticipato

Se prevedi di utilizzare la funzione **Fattura di pagamento anticipato** per gli ordini fornitore, il tipo di registrazione **Pagamento anticipato** deve essere selezionato sulla scheda **Ordine fornitore** sulla pagina **Profilo di registrazione dell'inventario**. Per ulteriori informazioni, vai a [Fatture di pagamento anticipato e pagamenti anticipati](/accounts-payable/prepayments-invoices-vs-prepayments.md).

## <a name="purchase-requisition-and-purchase-order-confirmation-posting"></a>Richiesta di acquisto e registrazione della conferma dell'ordine fornitore

Le richieste d'acquisto e le conferme degli ordini fornitore possono essere configurate anche per registrare gli impegni preliminari di spesa e gli impegni nella contabilità generale. Queste registrazioni sono controllate da una definizione di registrazione. Per ulteriori informazioni, vai a [Informazioni sugli impegni di un ordine fornitore](/dynamicsax-2012/appuser-itpro/about-purchase-order-encumbrances).

## <a name="procurement-category-posting"></a>Registrazione categoria di approvvigionamento

In alternativa all'impostazione della registrazione dell'inventario per tutti gli articoli, un gruppo di articoli o un singolo articolo, è possibile impostare le categorie e controllare la registrazione contabile in base alle categorie di approvvigionamento. Per ulteriori informazioni sull'impostazione delle categorie e sull'assegnazione ai prodotti, vai a [Esempio di configurazione del profilo di registrazione](#sample-posting-profile-configuration) in precedenza in questo articolo.

Quando si utilizzano categorie con ordini fornitore o fatture fornitore, è necessario assegnare la gerarchia delle categorie al tipo **Gerarchia delle categorie di approvvigionamento** sulla pagina **Assegnazioni di ruolo della gerarchia di categorie**.

### <a name="vendor-invoices-with-procurement-categories"></a>Fatture fornitore con categorie di approvvigionamento

Se l'organizzazione utilizza ordini fornitore per alcuni acquisti e non per altri, puoi elaborare le fatture non correlate all'ordine fornitore in vari modi. Ciò include l'utilizzo di giornali di registrazione in **contabilità fornitori** o dalla pagina **Fatture fornitore in sospeso** utilizzata per generare le fatture per gli ordini fornitore. Quando crei fatture non correlate all'ordine fornitore, dovrai creare categorie di approvvigionamento per ogni tipo di spesa. Dovrai mappare la categoria al conto spese corretto sulla pagina **Profili di registrazione dell'inventario**.

Il numero esatto di categorie varierà in base al numero di conti spese utilizzati per registrare le fatture. Avrai bisogno di almeno una categoria di approvvigionamento per ogni conto principale a cui hai addebitato le fatture degli ordini non fornitore. Molte categorie possono essere utilizzate per un singolo conto principale. Questo può essere utile per l'usabilità, la ricerca e la creazione dei report dei tipi di spese che utilizzi.

### <a name="benefits-of-using-procurement-categories-for-vendor-invoices"></a>Vantaggi dell'utilizzo delle categorie di approvvigionamento per le fatture fornitore

Alcuni vantaggi dell'utilizzo delle categorie di approvvigionamento per le fatture fornitore sono:

- Esperienza utente coerente: quando si configurano le categorie di approvvigionamento per tutte le spese non correlate all'ordine fornitore, gli utenti possono essere formati su un processo per la fatturazione utilizzando la pagina **Fatture fornitore in sospeso**.
- Esperienza di creazione di report migliorata: quando si configurano le categorie di approvvigionamento per tutti gli articoli e tutte le spese non correlate all'ordine fornitore, il report sulle spese di approvvigionamento analizzerà la spesa per fornitore, categoria e altro.
- Flusso di lavoro coerente: quando si utilizza **Fatture fornitore in sospeso** per elaborare tutte le fatture, puoi creare un flusso di lavoro e un processo di approvazione coerenti utilizzando un unico flusso di lavoro.

## <a name="consignment-inventory-posting"></a>Registrazione dell'inventario delle spedizioni

L'inventario delle spedizioni utilizza la stessa registrazione contabile degli altri articoli acquistati. La differenza fondamentale è che quando l'inventario viene ricevuto, non vengono registrate transazioni contabili. Per trasferire la proprietà all'organizzazione quando viene registrato un giornale di registrazione **Modifica della proprietà dell'inventario**, viene generato un giustificativo per registrare il costo dell'articolo. Per ulteriori informazioni, vai a [Impostare la spedizione](/supply-chain/inventory/consignment.md).
