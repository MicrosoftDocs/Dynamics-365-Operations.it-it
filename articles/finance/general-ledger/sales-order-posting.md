---
title: Registrazione ordine cliente
description: Questo argomento fornisce informazioni sulla scheda Ordine cliente della pagina del profilo di registrazione dell'inventario.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 5d84723b51d6977867fa162c4a47befa61bd9ef6
ms.sourcegitcommit: dc3053625dfe24aef64399dd1d002214e7f7619f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755930"
---
# <a name="sales-order-posting"></a>Registrazione ordine cliente

La scheda **Ordine cliente** nella pagina **Profili di registrazione inventario** viene utilizzata per controllare la modalità di registrazione degli ordini cliente nella contabilità generale. Due attività principali vengono registrate nella contabilità generale per un ordine cliente: 

- Documento di trasporto
- Fattura

Affinché una transazione fisica (documento di accompagnamento) venga registrata nella contabilità generale per un ordine cliente, devono essere soddisfatte le seguenti condizioni:

- Nella pagina **Parametri di gestione articoli e magazzino** deve essere selezionata la casella di controllo **Registra il documento di trasporto nella contabilità generale**.
- Nella pagina **Gruppo di modelli di articoli** relativa all'articolo selezionato nella riga dell'ordine cliente deve essere selezionata la casella di controllo **Registra l'inventario fisico nel libro mastro**.
- Nella pagina **Profilo di registrazione inventario**, i conti principali devono essere specificati per i seguenti tipi di registrazione:
  - Costo delle unità, consegnate
  - Costo del venduto, consegnato

Affinché una transazione finanziaria (fattura) venga registrata nella contabilità generale per un ordine cliente, devono essere soddisfatte le seguenti condizioni:

- Nella pagina **Gruppo di modelli di articoli** relativa all'articolo selezionato nella riga dell'ordine cliente deve essere selezionata la casella di controllo **Registra l'inventario finanziario nel libro mastro**.
- I conti principali devono essere specificati nella pagina **Profilo di registrazione inventario** per i seguenti tipi di registrazione:
  - Costo delle unità, fatturato
  - Costo del venduto, fatturato
  - Ricavi
  - Sconto\*

> [!NOTE]
> Il conto Sconto è facoltativo. Molte normative contabili, come GAAP e IFRS, richiedono che gli sconti riducano i ricavi delle vendite e pertanto questi account non vengono utilizzati in molti scenari. Se le normative locali lo consentono, utilizza un conto principale separato per registrare la parte del prezzo di vendita che viene scontata.

Per registrare il valore del ricavo differito (stimato) nella contabilità generale quando si genera un documento di trasporto per un ordine cliente, devono essere soddisfatte le seguenti condizioni:

- Nella pagina **Gruppo di modelli di articoli** relativa all'articolo selezionato nella riga dell'ordine cliente deve essere selezionata la casella di controllo **Registra l'inventario fisico nel libro mastro**.
- Nella pagina **Gruppo di modelli di articoli** deve essere selezionata la casella di controllo **Registra in conto ricavi differiti alla consegna vendite**.
- Nella pagina **Parametri di gestione articoli e magazzino** deve essere selezionata la casella di controllo **Registra il documento di trasporto nella contabilità generale**.
- Nella pagina **Parametri di gestione articoli e magazzino** deve essere selezionata la casella di controllo **Registra IVA effettiva**.
- Nella pagina **Parametri contabilità clienti** deve essere selezionata la casella di controllo **Registra il documento di trasporto nella contabilità generale**.
- Nella pagina **Profilo di registrazione inventario**, i conti principali devono essere specificati per i seguenti tipi di registrazione:
  - Ricavi differiti alla consegna
  - Contropartita ricavi differiti alla consegna
  - IVA differita alla consegna

> [!NOTE]
> In genere si consiglia di abilitare le opzioni **Registra inventario fisico** e **Registra il documento di trasporto nella contabilità generale**. L'abilitazione di queste opzioni può aiutare ad accelerare le procedure di chiusura di fine mese, poiché non sarà necessario calcolare e registrare manualmente i differimenti. Inoltre, i rendiconti finanziari rifletteranno automaticamente gli importi differiti senza intervento manuale.

> [!IMPORTANT]
> L'opzione **Registra in conto ricavi differiti alla consegna vendite** non viene utilizzata con il riconoscimento dei ricavi. Per ulteriori informazioni sul riconoscimento dei ricavi, vai alla [Panoramica sul riconoscimento dei ricavi](/accounts-receivable/revenue-recognition-overview.md)

## <a name="sample-posting-profile-configuration"></a>Esempio di configurazione del profilo di registrazione 

La tabella seguente mostra esempi dei tipi di registrazione predefiniti con conti principali e descrizioni di esempio:
 
- La colonna **Conto di compensazione** indica che il tipo di registrazione è un conto di compensazione. L'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva. 
- La colonna **P/F** indica **P** per la pubblicazione fisica e **F** per la registrazione finanziaria. 
- La colonna **Segui** indica se il conto principale per un tipo di registrazione specifico è in genere uguale a un altro tipo di registrazione. Il valore nella colonna indica il tipo di registrazione generalmente utilizzato.

> [!NOTE]
> Questi conti principali e nomi di conti principali sono solo suggerimenti. Ti consigliamo di collaborare con il tuo commercialista per determinare la configurazione migliore per le tue esigenze aziendali.


| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere? | Conto di compensazione | P/F | Segui | Description |
|------------|------------------------|-------------------------|--------------|---------|-------------------|------------|------|-------------------------|
| Costo delle unità, consegnate | 140100</br>140101 | Inventario dei materiali</br>Materiali spediti non fatturati | Cespite | Credito | Sì | P | Costo delle unità, fatturato | Utilizzato quando viene registrato un documento di trasporto dell'ordine cliente. La compensazione sul conto è il costo del venduto della merce consegnata. L'importo in questo conto viene automaticamente stornato quando viene registrata una fattura per l'ordine cliente. È consigliabile utilizzare un conto Materiali spediti non fatturati per rappresentare l'inventario fisico e prenotare il conto inventario Materiali per l'aggiornamento finanziario. |
| Costo del venduto, consegnato | 500150 | COGS differito | Spese | Dare | Sì | P  | Utilizzato quando viene registrato un documento di trasporto dell'ordine cliente. La compensazione sul conto è il costo delle unità consegnate. L'importo in questo conto viene automaticamente stornato quando viene registrata una fattura per l'ordine cliente. |
| Costo delle unità, fatturato | 140100 | Inventario dei materiali | Cespite | Credito | Numero | V | Costo delle unità, consegnate | Utilizzato quando viene registrata una fattura dell'ordine cliente. La compensazione sul conto è il costo del venduto fatturato. Questo conto rappresenta l'inventario nel tuo stato patrimoniale. |
| Costo del venduto, fatturato | 500100 | Materiali COGS | Spese | Dare | Numero | V  | Utilizzato quando viene registrata una fattura dell'ordine cliente. La compensazione sul conto è il costo unitario fatturato. Questo conto rappresenta i COGS sulla tua dichiarazione P&amp;L. |
| Ricavi (ricavi ordine cliente*) | 400100 | Materiali ricavi | Ricavi | Credito | Numero | V   | Utilizzato quando viene registrata una fattura dell'ordine cliente. La compensazione per questo conto è il conto Riepilogo (Saldo cliente*) sul **Profilo di registrazione della contabilità clienti**. |
| Commissione (vendite, commissione*) | 602150 | Commissioni | Spese | Dare | Numero | V  | Utilizzato quando la commissione è abilitata e calcolata per una vendita e registrata durante il processo di fatturazione dell'ordine cliente. La compensazione su questo conto è la Commissione pagabile. |
| Compensazione delle commissioni (vendite, compensazione delle commissioni*) | 201110 | Importi a debito provvigioni | Passività | Credito | Sì | V | Utilizzato quando la commissione è abilitata e calcolata per una vendita e registrata durante il processo di fatturazione dell'ordine cliente. La compensazione su questo conto sono le commissioni. |
| Ricavi differiti alla consegna (Vendite – ricavi da documento di trasporto*) | 401400 | Vendite maturate | Ricavi | Credito | Sì | P  | Utilizzato quando il ricavo differito per la consegna è abilitato e viene registrato quando si elabora un documento di trasporto dell'ordine cliente. Il conto di contropartita è il conto dei ricavi o dei ricavi differiti. Gli importi in questo conto vengono automaticamente stornati quando si registra la fattura dell'ordine cliente. |
| Compensazione ricavi differiti alla consegna (Vendite – compensazione ricavi da documento di trasporto)* | 130400 | Contabilità clienti – non fatturata | Cespite | Dare | Sì | P  | Utilizzato quando il ricavo differito per la consegna è abilitato e viene registrato quando si elabora un documento di trasporto dell'ordine cliente. Il conto di contropartita è il conto dei ricavi alla consegna. Gli importi in questo conto vengono automaticamente stornati quando si registra la fattura dell'ordine cliente. |
| IVA differita alla consegna (Vendite – IVA da documento di trasporto*) | 250500 | IVA differita | Passività | Credito | Sì | P  | Utilizzato quando è abilitato il ricavo differito per la consegna e l'IVA fisica sulle vendite è abilitata. L'importo dell'imposta viene registrato quando si elabora un documento di trasporto dell'ordine cliente. |

\*I valori mostrati tra parentesi in questa tabella rappresentano il valore utilizzato nel campo **Tipo di registrazione** sulla pagina **Transazioni giustificativo**. Puoi visualizzare il **Tipo di registrazione** nella pagina **Transazioni giustificativo** della scheda **Generale**.

## <a name="sales-category-posting"></a>Registrazione categorie di vendita

In alternativa all'impostazione della registrazione dell'inventario per tutti gli articoli, un gruppo di articoli o un singolo articolo, è possibile impostare le categorie e controllare la registrazione contabile in base alle categorie di vendita. Per ulteriori informazioni sull'impostazione di una gerarchia di categorie e sull'assegnazione di categorie ai prodotti, vai a [Creare una gerarchia di classificazione del prodotto](/supply-chain/pim/tasks/create-hierarchy-product-classification.md) e [Classificare un prodotto utilizzando le gerarchie di categorie](/supply-chain/pim/tasks/classify-product-category-hierarchies.md).

Dopo aver creato una gerarchia di categorie, è necessario assegnare la gerarchia a uno o più tipi. Per utilizzare una gerarchia di categorie negli ordini cliente, è necessario assegnare la categoria al tipo di gerarchia di categorie Vendite. Per ulteriori informazioni, vai a [Informazioni sulle gerarchie di categorie](/dynamicsax-2012/appuser-itpro/about-category-hierarchies.md).

## <a name="create-revenue-posting-by-sales-category"></a>Creare la registrazione dei ricavi per categoria di vendita

Per assegnare registrazioni contabili per un ordine cliente in base a una categoria di vendita, attenersi alla seguente procedura:

1. Vai a **Gestione scorte** > **Impostazioni** > **Registrazione** > **Registrazione**.
2. Seleziona la scheda **Vendite**.
3. Seleziona il pulsante di opzione per il tipo di registrazione che desideri configurare (ad esempio, **Ricavi**).
4. Selezionare **Nuovo**.
5. Nel campo **Codice articolo** selezionare **Categoria**.
6. Usa il campo **Relazione categorie** per selezionare la categoria per il profilo di registrazione.
7. Nel campo **Codice conto**, seleziona un'opzione per **Tabella**, **Gruppo** o **Tutti**. Ad esempio, per applicare il profilo di registrazione a tutti i clienti, seleziona **Tutti**.
   - Se hai selezionato **Tabella** al passaggio 6, seleziona il **Numero fornitore** specifico per il profilo di registrazione nel campo **Relazione conto**.
   - Se hai selezionato **Gruppo** al passaggio 6, seleziona il **Gruppo fornitore** specifico per il profilo di registrazione nel campo **Relazione conto**.
   - Se hai selezionato **Tutti** al passaggio 6, il campo **Relazione conto** verrà lasciato vuoto.

8. **Selezionare una fascia IVA** per associare una determinata fascia IVA che dispone del tipo di registrazione selezionato. Se questo campo viene lasciato vuoto, il tipo di registrazione si applica a tutte le fasce IVA esistenti. La registrazione specificata per le fasce IVA si applica soltanto alle transazioni effettuate per le vendite e gli acquisti.

9. Nel campo **Conto principale**, specifica il numero di conto in cui registrare il tipo di conto. Selezionare uno dei numeri di conto nel piano dei conti.
