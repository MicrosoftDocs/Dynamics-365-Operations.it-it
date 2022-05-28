---
title: Dettagli sulle operazioni di magazzino
description: Questo argomento fornisce una panoramica della pagina Dettagli transazioni che mostra i dettagli di un'operazione di magazzino selezionata.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: fd1416f21ce15dc832dd41ea4110c93bf5bb41a2
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8735914"
---
# <a name="inventory-transaction-details"></a>Dettagli sulle operazioni di magazzino

Usare la pagina **Dettagli transazioni** per visualizzare i dettagli di un'operazione di magazzino selezionata.

## <a name="open-the-transaction-details-page"></a>Aprire la pagina Dettagli transazione

Per aprire la pagina **Dettagli transazioni**, eseguire i passaggi indicati di seguito.

1. Andare a **Gestione articoli \> Richieste di informazioni e report \> Transazioni**.
1. Selezionare la transazione da esaminare.
1. Nel riquadro azioni selezionare **Dettagli transazioni**.

## <a name="fasttabs-overview"></a>Panoramica delle Schede dettaglio

La pagina **Dettagli transazioni** è suddivisa in più Schede dettaglio. Nella tabella riportata di seguito viene descritto lo scopo di ciascuna Scheda dettaglio.

| Scheda dettaglio | Description |
|---|---|
| Generali | Questa Scheda dettaglio mostra le informazioni di base sull'operazione di magazzino selezionata. Oltre ai campi visualizzati nella pagina **Operazioni di magazzino**, sono inclusi i campi aggiuntivi descritti più avanti in questo argomento. |
| Aggiornamenti | Questa Scheda dettaglio mostra le informazioni relative agli aspetti fisici, finanziari e di liquidazione dell'operazione di magazzino selezionata. A seconda dello stato corrente della transazione, alcuni campi potrebbero essere vuoti. Tuttavia, questi campi verranno impostati automaticamente al momento della registrazione delle transazioni. Oltre ai campi visualizzati nella pagina **Operazioni di magazzino**, questa Scheda dettaglio include i campi aggiuntivi descritti più avanti in questo argomento. |
| Registrazioni contabilità generale | Questa Scheda dettaglio mostra il tipo di registrazione e il conto CoGe utilizzati per l'aggiornamento fisico, l'aggiornamento finanziario, i ricavi fisici, gli oneri fisici, i ricavi finanziari e gli oneri finanziari correlati all'operazione di magazzino selezionata. |
| Riferimenti | Questa Scheda dettaglio mostra informazioni aggiuntive sulla transazione di origine che ha creato l'operazione di magazzino selezionata. Ad esempio, queste informazioni potrebbero includere i dettagli dell'ordine fornitore o dell'ordine cliente. |
| Informazioni correlate | Questa Scheda dettaglio mostra informazioni aggiuntive sull'operazione di magazzino selezionata. Questi campi potrebbero non essere impostati se non si utilizzano alcune funzionalità, come categorie di approvvigionamento o progetti. |
| Dimensioni finanziarie - fisiche | Questa Scheda dettaglio mostra i valori della dimensione finanziaria utilizzati al momento della registrazione dell'aggiornamento fisico. Se l'aggiornamento fisico non è stato registrato, i campi saranno vuoti. |
| Dimensioni finanziarie - finanziarie | Questa Scheda dettaglio mostra i valori della dimensione finanziaria utilizzati al momento della registrazione dell'aggiornamento finanziario. Se l'aggiornamento finanziario non è stato registrato, i campi saranno vuoti. |
| Dimensioni inventariali | Questa Scheda dettaglio mostra i valori della dimensione inventariale assegnati all'operazione di magazzino selezionata. Questi valori includono il sito, il magazzino, le dimensioni, il colore, la configurazione, l'ubicazione, il numero batch, il numero di serie, lo stato inventario, la targa e il proprietario. |

## <a name="fields-on-the-general-fasttab"></a>Campi della Scheda dettaglio Generale

La tabella seguente descrive i campi della Scheda dettaglio **Generale** che non sono visualizzati anche nella pagina **Operazioni di magazzino**.

| Campo | Description |
|---|---|
| Parte | Il nome della parte rilevante per l'operazione di magazzino selezionata. Ad esempio, una transazione dell'ordine fornitore mostra il nome del fornitore nell'ordine fornitore e una transazione dell'ordine cliente mostra il nome del cliente. Questo campo non è disponibile per tutti i tipi di operazioni di magazzino. |
| Riferimento magazzino | Se un'altra operazione di magazzino è correlata all'operazione di magazzino selezionata, il tipo di quell'altra transazione. Ad esempio, se un ordine fornitore è contrassegnato a fronte di un ordine cliente, il campo **Riferimento magazzino** della transazione dell'ordine fornitore sarà impostato su *Ordine cliente*. Il contrassegno avviene automaticamente per gli ordini con consegna diretta e gli ordini interaziendali. Quando si utilizza il contrassegno con metodi di determinazione costi diversi da *costo standard* e *media mobile*, il sistema creerà liquidazioni e rettifiche per le transazioni esatte contrassegnate. In questo modo, è possibile ottenere una determinazione costi "effettiva" che prevale sulla logica per FIFO (first in, first out), LIFO (last in, first out) o media ponderata. |
| Numero ordine di magazzino | La transazione specifica correlata all'operazione di magazzino selezionata. Ad esempio, se un ordine fornitore è contrassegnato a fronte di un ordine cliente, il campo **Numero ordine di magazzino** della transazione dell'ordine fornitore sarà impostato sul numero dell'ordine cliente. |
| ID progetto | Se l'operazione di magazzino selezionata è correlata a un progetto, questo campo è impostato sul numero del progetto. |
| ID lotto | L'ID lotto univoco che il sistema ha assegnato all'operazione di magazzino selezionata. |
| Lotto di riferimento | Se un'altra operazione di magazzino è correlata all'operazione di magazzino selezionata, l'ID lotto di quell'altra transazione. Ad esempio, se un ordine fornitore è contrassegnato a fronte di un ordine cliente, il campo **Lotto di riferimento** della transazione dell'ordine fornitore sarà il valore **ID lotto** dell'operazione di magazzino della riga dell'ordine cliente. |
| Numero dimensione | Un ID univoco che rappresenta la combinazione di tutti i valori delle dimensioni inventariali assegnati all'operazione di magazzino selezionata. |
| Aperta per valore | Un valore che indica se l'operazione di magazzino selezionata è stata liquidata dal processo di chiusura inventario. Se il campo è impostato su *Sì*, la transazione non è stata liquidata. |
| Data prevista | Per le transazioni in entrata, la data in cui è prevista l'entrata in magazzino. Ad esempio, questo campo potrebbe mostrare la data di entrata prevista in un ordine di blocco scorte o la data di consegna in una riga dell'ordine fornitore. |
| Data inventario | Questo campo viene impostato quando una transazione di registrazione è stata eseguita sull'ordine di entrata prima della registrazione di un'entrata fisica. |
| Trasferimento non finanziario | Un valore che indica se l'operazione di magazzino selezionata è un trasferimento non finanziario. Un trasferimento non finanziario si verifica quando una modifica delle dimensioni inventariali non viene tracciata finanziariamente nella pagina **Gruppo di modelli di articoli**. |
| ID lotto di trasferimento | Se l'operazione di magazzino selezionata è un trasferimento non finanziario, questo campo è impostato sul valore **ID lotto** dell'altra operazione di magazzino a fronte della quale viene liquidata la transazione selezionata. |

## <a name="fields-on-the-updates-fasttab"></a>Campi della Scheda dettaglio Aggiornamenti

La tabella seguente descrive i campi della Scheda dettaglio **Aggiornamenti** che non sono visualizzati anche nella pagina **Operazioni di magazzino**.

| Campo | Description |
|---|---|
| Giustificativo fisico | Il numero giustificativo dalla contabilità generale in cui è stata generata la registrazione fisica per l'operazione di magazzino selezionata. |
| Ciclo | Il ciclo di lavorazione correlato all'operazione di magazzino selezionata. Questo campo è impostato solo per le transazioni della distinta di prelievo di produzione in cui la distinta base (BOM) o la riga formula è correlata a un articolo specifico. |
| Documento di trasporto | Il numero del documento di trasporto immesso per una transazione in entrata di prodotti dell'ordine fornitore. |
| Importo costi fisico | L'importo registrato nella contabilità generale per l'aggiornamento fisico. Per un prodotto a costo standard, questo importo rappresenta il costo standard. Per altri metodi di determinazione costi, rappresenta la media ponderata del prodotto al momento della registrazione. |
| Ricavi fisici | L'importo dei ricavi differiti registrato nella contabilità generale per l'aggiornamento fisico. |
| ID carico | Se la transazione corrente è correlata a un carico in Gestione trasporto, questo campo mostra il numero univoco del carico che includeva l'articolo. |
| Registrato fisicamente | Valore che indica se l'operazione di magazzino selezionata è stata registrata fisicamente. Se la transazione corrente viene registrata nella contabilità generale, sarà presente anche un giustificativo fisico. |
| Registrato finanziariamente | Un valore che indica se l'operazione di magazzino selezionata è stata registrata finanziariamente. Se la transazione corrente viene registrata nella contabilità generale, sarà presente anche un giustificativo finanziario. |
| Spese fisiche registrate | Un valore che indica se le spese fisiche correlate all'operazione di magazzino selezionata sono state registrate. |
| Spese finanziarie registrate | Un valore che indica se le spese finanziarie correlate all'operazione di magazzino selezionata sono state registrate. |
| Giustificativo finanziario | Il numero del giustificativo nella contabilità generale in cui è stata generata la registrazione finanziaria. |
| Fattura | Il numero di fattura che è stato generato, ad esempio, per un ordine fornitore o un ordine cliente. |
| Correzione | L'importo che è stato rettificato sull'operazione di magazzino selezionata dal processo di rettifica e chiusura scorte. |
| Profitti e perdite, importo registrato | L'importo dell'operazione di magazzino selezionata che è stato registrato nel rendiconto profitti e perdite. |
| Fattura non registrata | Il numero di fattura di un ordine fornitore correlato che appare nella pagina **Fattura fornitore in sospeso**. |
| Chiuso finanziariamente | La data in cui la transazione è stata interamente liquidata. |
| Quantità a peso variabile coperta | La quantità a peso variabile coperta dalla liquidazione. |
| Quantità liquidata | La quantità che è stata liquidata per l'operazione di magazzino selezionata. |
| Importo liquidato | Il valore che è stato liquidato per l'operazione di magazzino selezionata. |
