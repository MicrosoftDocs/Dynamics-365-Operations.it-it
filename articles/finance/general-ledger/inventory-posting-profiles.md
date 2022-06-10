---
title: Profili di registrazione dell'inventario
description: In questo argomento viene fornita una panoramica dei profili di registrazione dell'inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28e3a3051978f921e01a929496e96909e6c32429
ms.sourcegitcommit: 00b39900d3cbdbc9ca1ab3145265007f5dc98a3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "8806373"
---
# <a name="inventory-posting-profiles"></a>Profili di registrazione dell'inventario

[!include [banner](../includes/banner.md)]

I profili di registrazione inventario controllano la registrazione delle transazioni della contabilità secondaria di magazzino nella contabilità generale. Le transazioni di contabilità secondaria di magazzino possono essere generate da molti moduli, tra cui **Vendite e marketing**, **Approvvigionamento**, **Controllo di produzione**, e altri ancora. Le transazioni di contabilità secondaria di magazzino possono essere registrate ogni volta che un articolo viene utilizzato in un ordine cliente o in un ordine fornitore. 

Ulteriori transazioni contabili di magazzino potrebbero essere registrate:
- Ogni volta che un documento viene aggiornato.
- Quando viene registrato un documento di trasporto dell'ordine cliente o una fattura.
- Quando viene generata un'entrata o una fattura del prodotto dell'ordine fornitore.

Per ulteriori informazioni, vedi Transazioni di contabilità secondaria di magazzino.

## <a name="inventory-transaction-overview"></a>Panoramica delle transazioni di inventario

Ogni transazione di contabilità secondaria di magazzino contiene:
 - Quantity 
 - Prezzo 
 - Sito 
 - Magazzino 
 - Posizione 

Le transazioni di contabilità secondaria di magazzino creano due movimenti nella contabilità generale tramite la registrazione fisica e la registrazione finanziaria. Per ulteriori informazioni, vai ad [Aggiornamenti fisici e finanziari](/supply-chain/cost-management/physical-financial-updates.md).
L'esempio seguente è un ordine fornitore con tre righe. Per questo esempio, si presuppone che l'intero ordine riguardi un unico sito e magazzino. Ogni riga dell'ordine fornitore ha un singolo record InventTrans correlato, noto anche come transazione di inventario, e ogni riga è per una quantità di 10. Il diagramma seguente mostra la relazione tra un'intestazione dell'ordine fornitore e tre righe dell'ordine fornitore, ciascuna con un record InventTrans.

![Diagramma di relazione per un ordine fornitore con tre righe ciascuna con un record InventTrans.](./media/InventTransRelationship.PNG)

Viene ricevuta una quantità pari a 5 sulla prima riga dell'ordine fornitore. La quantità completa per la seconda riga e nessuna quantità viene ricevuta nella terza riga dell'ordine fornitore. È ora disponibile una seconda transazione di inventario correlata alla prima riga dell'ordine fornitore. La transazione per la seconda riga dell'ordine fornitore verrà aggiornata a **Ricevuto** e la terza transazione rimarrà la stessa. Il diagramma seguente mostra la relazione con il record InventTrans aggiuntivo per la riga ordine fornitore 1.

![Diagramma di relazione per un ordine fornitore con tre righe. Una riga è parzialmente ricevuta e mostra due record InventTrans.](./media/InventTransRelationshipPartialReceipt.PNG)

In questo esempio, un giustificativo verrà registrato nella contabilità generale; questo è il giustificativo fisico. Il gruppo di modelli di articoli è configurato per registrare l'inventario fisico e tutti gli articoli utilizzano lo stesso gruppo di modelli di articoli. Il profilo di registrazione dell'inventario utilizza un unico set di conti principali. Verrà creato un unico giustificativo e il record InventTrans collegherà InventTrans 1 e InventTrans 2 allo stesso giustificativo.

Successivamente, viene ricevuta una fattura per la quantità ricevuta alle righe 1 e 2. Un altro giustificativo viene creato nella contabilità generale; questo è il giustificativo finanziario. Il gruppo di modelli di articoli è configurato per registrare l'inventario finanziario. Il nuovo secondo giustificativo è relativo a InventTrans 1 e InventTrans 2.

A seconda del modello di determinazione dei costi, potrebbe esistere una terza registrazione di contabilità generale per le transazioni di contabilità secondaria dell'inventario relative alla chiusura e alla liquidazione dell'inventario. Per ulteriori informazioni, vai a [Chiusura inventario](/supply-chain/cost-management/inventory-close.md). Puoi visualizzare i dettagli di tutte le transazioni di inventario andando in **Gestione inventario** > **Richieste informazioni e report** > **Transazioni**.

>[!Important]
> Le transazioni di inventario verranno suddivise per ogni combinazione univoca di dimensioni inventariali e per ogni aggiornamento parziale. Ciò è stato mostrato nell'esempio precedente per gli aggiornamenti parziali.

### <a name="split-inventory-based-on-inventory-dimension-example"></a>Esempio di divisione dell'inventario in base alla dimensione inventariale

La riga 3 dell'ordine fornitore nell'esempio è un articolo con numero di serie. Durante il processo di entrata vengono registrati dieci numeri di serie per l'ordine fornitore. La transazione di inventario sarà suddivisa in 10 transazioni di inventario. Il diagramma seguente mostra la relazione e le transazioni di inventario aggiuntive, ciascuna con il proprio numero di serie relativo alla riga 3 dell'ordine fornitore.

![Diagramma di relazione per un ordine fornitore con tre righe. Una riga è serializzata e mostra record InventTrans aggiuntivi](./media/InventTransRelationshipSerialNumber.PNG)

Nell'esempio precedente, se ogni numero di serie viene ricevuto su una singola entrata di prodotto, verrà creato un giustificativo aggiuntivo. Il campo del giustificativo fisico sarà collegato a ciascun numero di serie. Lo stesso vale per l'aggiornamento finanziario quando si fattura l'ordine fornitore.

## <a name="inventory-transactions"></a>Transazioni di inventario

È possibile visualizzare le transazioni di inventario nella pagina **Transazioni di inventario** sotto **Gestione inventario e magazzino** o **Gestione costi**. È inoltre possibile visualizzare le transazioni di inventario relative a una riga di documento di origine specifica, ad esempio una riga ordine fornitore o una riga ordine cliente, selezionando **Inventario** e quindi selezionando **Transazioni**. 

La pagina **Transazioni di inventario** contiene i seguenti campi.

| Campo            | Description                                 |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|
| Numero articolo      | Numero di articolo correlato alla transazione.                                                                  |
| Data effettiva    | La data in cui l'inventario arriva al magazzino, lascia il magazzino, viene consumato in produzione o viene prodotto. Ad esempio, la data di registrazione
sulla registrazione del documento di trasporto per un ordine cliente o della registrazione dell'entrata prodotti per un ordine fornitore.                             |
| Data finanziaria   | La data in cui la transazione di inventario viene chiusa e il costo viene registrato nella contabilità generale. Ad esempio, la data di registrazione sulla generazione fattura 
per un ordine fornitore o cliente. Non sono consentiti aggiornamenti del documento di riferimento dopo il popolamento della data finanziaria. |
| Riferimento        | Indica l'origine della transazione e il tipo di documento visualizzato nel campo **Numero**. Ad esempio, ordine cliente, ordine fornitore o ricevuta dell'ordine di trasferimento.                                                 |
| Numero           | Indica l'ID di riferimento per una transazione. Ad esempio, se il campo **Riferimento** indica l'ordine cliente, il campo **Numero** indica il numero dell'ordine cliente.                                                       |
| Entrata (stato) | Per le transazioni di inventario che sono entrate, questo campo indica lo stato dell'entrata. Ad esempio, un ordine fornitore è un'entrata e lo stato potrebbe essere **Ordinato** o **Acquistato**.                                                            |
| Uscita (stato)   | Per le transazioni di inventario che sono uscite, questo campo indica lo stato dell'uscita. Ad esempio, un ordine cliente è un'uscita e lo stato potrebbe essere **Merci ordinate in corso di consegna** o **Venduto**.                         |
| Quantity         | Quantità della transazione di inventario. I numeri positivi vengono utilizzati per le entrate nell'inventario, mentre i numeri negativi vengono utilizzati per le uscite dall'inventario.                                                                                                                          |
| Unità             | L'unità di misura in cui è espressa la quantità.                                                                                   |
| Quantità a peso variabile      | Quantità a peso variabile della transazione. Per ulteriori informazioni, vai a [Informazioni sugli articoli a peso variabile](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.).       |
| Unità a peso variabile          | L'unità di misura in cui è espressa la quantità a peso variabile.                                                         |
| Importo costi      | Il costo finale della transazione di inventario. Questo campo viene compilato quando una transazione viene aggiornata finanziariamente. A seconda della metodologia di determinazione dei costi, il processo di chiusura e rettifica dell'inventario potrebbe aggiornare questo campo.                            |

## <a name="inventory-status"></a>Stato inventario

Ogni transazione di inventario ha uno stato che viene visualizzato nel campo **Entrata** o **Uscita**. Il campo utilizzato dipende dal tipo di transazioni di inventario. Le entrate sono transazioni che aumentano l'inventario. Ad esempio, un ordine fornitore con una quantità positiva o un reso di un ordine cliente con una quantità negativa. Le uscite sono transazioni di inventario che hanno ridotto l'inventario. Ad esempio, un ordine cliente con una quantità positiva o un reso di un ordine fornitore con una quantità negativa.

### <a name="receipt-status"></a>Stato entrata

La tabella seguente descrive lo stato **Entrata**.

| **Stato entrata** | **Descrizione**       |
|--------------------|------------------------------------------------------------------------------------------------------------------------------------------|
| Quantità ordinata            | Lo stato iniziale di qualsiasi transazione di inventario che rappresenta un'entrata. Ciò include gli ordini fornitore con una quantità positiva, gli ordini di produzione o i resi degli ordini cliente con una quantità negativa.                                                   |
| Registrato         | Questo stato viene utilizzato quando è in atto un processo di entrata in due fasi o quando l'arrivo dell'articolo viene utilizzato per indicare che il prodotto è arrivato. Viene utilizzato quando i numeri di batch o di serie vengono "allocati" o registrati nell'ordine. Per ulteriori informazioni sull'arrivo degli articoli, vai a [Panoramica dell'arrivo](/supply-chain/inventory/arrival-overview.md). |
| Ricevute           | Questo stato viene utilizzato quando la transazione viene aggiornata fisicamente. Per un ordine fornitore, è il momento in cui viene registrata l'entrata prodotti. Per un reso di un ordine cliente, è il momento in cui viene registrato il documento di trasporto.                                                                            |
| Acquistato          | Questo stato viene utilizzato quando la transazione viene aggiornata finanziariamente. Per un ordine fornitore o un reso di un ordine cliente, è il momento in cui viene generata la fattura.                                                                                             |

### <a name="issue-status"></a>Stato uscita

La tabella seguente descrive lo stato **Uscita**.

| **Stato uscita**  | **Descrizione**            |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| Merci ordinate in corso di consegna          | Lo stato iniziale di qualsiasi transazione di inventario che rappresenta un'uscita. Ciò include gli ordini cliente con una quantità positiva, le righe formula o DBA ordini di produzione o i resi degli ordini fornitore con una quantità negativa.                                             |
| Ordinato prenotato  | Questo stato dell'inventario indica che l'inventario è prenotato per un ordine che è stato creato, ma non è stato ancora ricevuto fisicamente nell'inventario. Quando l'inventario viene ricevuto, lo stato si aggiornerà automaticamente a **Fisico prenotato**. Per maggiori informazioni sulle prenotazioni, vai a [Prenotare quantità di inventario](/supply-chain/inventory/reserve-inventory-quantities.md). |
| Fisico prenotato | Questo stato indica che l'inventario è stato allocato o prenotato rispetto a un ordine specifico. Quando l'inventario è prenotato, non è fisicamente disponibile per altri ordini.                                 |
| Prelevata         | Questo stato indica che l'inventario è stato prelevato dal magazzino. L'inventario è ancora fisicamente nel magazzino, non è stato rimosso, ma non è disponibile per altri ordini.  |
| Detratto          | Questo stato viene utilizzato quando la transazione viene aggiornata fisicamente. Per un ordine cliente, questo avviene quando viene registrato il documento di trasporto; per un reso di un ordine fornitore, quando viene registrata l'entrata del prodotto.                                                                      |
| Venduta              | Questo stato viene utilizzato quando la transazione viene aggiornata finanziariamente. Per un ordine fornitore o unordine cliente, è il momento in cui viene generata la fattura.|

Per ulteriori informazioni sulle transazioni di inventario, vai a [Dettaglio delle transazioni di inventario](/supply-chain/inventory/inventory-transactions-details.md).

## <a name="configure-an-inventory-posting-profile"></a>Configurare un profilo di registrazione dell'inventario

Per configurare un profilo di registrazione dell'inventario, attieniti alla seguente procedura:

1.  Apri **Gestione scorte** > **Impostazioni** > **Registrazione** > **Registrazione**.
2.  Seleziona la scheda per il tipo di transazione. Ad esempio seleziona **Ordine fornitore**.
3.  Seleziona il pulsante di opzione per il tipo di registrazione. Ad esempio, seleziona **Spese acquisto da registrare nelle spese**.
4.  Selezionare **Nuovo**.
5.  Nel campo **Codice articolo**, seleziona un'opzione per **Tabella**, **Gruppo**, **Tutti**, o **Categoria**. Ad esempio, per configurare un profilo di registrazione per un gruppo di articoli specifico, seleziona **Gruppo**.
     - Se hai selezionato **Tabella** al passaggio 5, seleziona il Numero articolo specifico per il profilo di registrazione nel campo **Relazione articolo**.
     - Se hai selezionato **Gruppo** al passaggio 5, seleziona il **Gruppo articoli** specifico per il profilo di registrazione nel campo **Relazione articolo**.
     - Se hai selezionato **Tutti** al passaggio 5, il campo **Relazione articolo** sarà vuoto.
     - Se hai selezionato **Categoria** al passaggio 5, il campo **Relazione articolo** sarà vuoto. Usa il campo **Relazione categorie** per selezionare la categoria che si applica al profilo di registrazione.

6.  Nel campo **Codice conto**, seleziona un'opzione per **Tabella**, **Gruppo** o **Tutti**. Ad esempio, per applicare il profilo di registrazione a tutti i fornitori, seleziona **Tutti**.
     - Se hai selezionato **Tabella** al passaggio 5, seleziona il numero fornitore specifico per il profilo di registrazione nel campo **Relazione conto**.
     - Se hai selezionato **Gruppo** al passaggio 5, seleziona il gruppo fornitori specifico per il profilo di registrazione nel campo **Relazione conto**.
     - Se hai selezionato **Tutti** al passaggio 5, il campo **Relazione conto** sarà vuoto.

7.  **Selezionare una fascia IVA** per associare una determinata fascia IVA che dispone del tipo di registrazione selezionato. Se questo campo è vuoto, il tipo di registrazione si applica a tutti i gruppi di imposte esistenti. La registrazione specificata per i gruppi di imposte si applica solo alle transazioni di vendita e acquisto.
8.  Nel campo **Conto principale**, specifica il numero di conto in cui registrare il tipo di conto. Se non è stato ancora creato un numero di conto da utilizzare come tipo di contabilità, sarà possibile creare un nuovo conto. Creare un nuovo conto nella pagina **Dettagli conto principale** in Contabilità generale.

## <a name="additional-resources"></a>Risorse aggiuntive

Ogni scheda sulla pagina **Profilo di registrazione dell'inventario** si riferisce a un giornale di registrazione secondario in Dynamics 365 Supply Chain Management. Per ulteriori informazioni, vedi:
-   [Registrazione ordine cliente](sales-order-posting.md)
-   [Registrazione ordine fornitore](purchase-order-posting.md)
-   [Registrazione magazzino](inventory-posting.md)
-   [Registrazione del controllo di produzione](production-posting.md)
-   [Registrazione dello scostamento costo standard](standard-cost-variance-posting.md)
