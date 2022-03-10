---
title: Report di Costo sbarcato
description: In questo argomento viene descritto come trovare e utilizzare vari tipi di report disponibili per il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-21
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: cb0ea44c0924fc5d2c295a9285701d1f678c3473
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571739"
---
# <a name="landed-cost-reports"></a>Report di Costo sbarcato

[!include [banner](../../includes/banner.md)]

## <a name="outstanding-invoices"></a>Fatture arretrate

Il report sulle fatture arretrate contiene un elenco di tutte le fatture arretrate dei vari livelli di costo associati a ogni viaggio. Viene utilizzato per riconciliare regolarmente viaggio e costi di viaggio con l'elenco delle transazioni contabili. Dopo che un costo generale è stato fatturato, viene rimosso dal report.

Per generare un report Fatture arretrate, effettuare le seguenti operazioni.

1. Selezionare **Costo sbarcato \> Report \> Tracciabilità \> Fatture arretrate**.
1. Nella finestra di dialogo **Fatture arretrate**, nel campo **Alla data**, specificare una data. Qualsiasi fattura arretrata a tale data verrà inclusa nell'output.
1. In **Mostra** selezionare una delle seguenti opzioni:

    - **Costo non fatturato** - Includere i costi delle spedizioni fatturate che hanno un valore di costo stimato ma nessun costo effettivo.
    - **Scorte non fatturate** - Includere i costi che sono stati fatturati, ma per i quali l'ordine fornitore non è stato ancora ricevuto.
    - **Tutto il non fatturato** - Includere i risultati di entrambi le opzioni **Costo non fatturato** e **Scorte non fatturate**.

1. Impostare l'opzione **Includi nuovi costi** su *Sì* per includere i costi che non hanno ancora un costo effettivo e per cui le scorte non sono state ricevute. Se la si imposta su *No*, il report includerà solo i costi che sono stati fatturati.
1. Nella sezione **Visualizza**, abilitare ogni tipo di dettaglio che si desidera includere nel report.
1. Come per altri tipi di report in Microsoft Dynamics 365 Supply Chain Management, usare la Scheda dettaglio **Destinazione** per selezionare il formato di output del report.
1. Come per altri tipi di report in Supply Chain Management, utilizzare la Scheda dettaglio **Record da includere** per limitare ulteriormente i record che verranno inclusi nel report.
1. Scegliere **OK** per generare il report.

## <a name="activityprovider-analysis-reports"></a>Report Analisi di attività/provider

I report Analisi di attività/provider consentono di esaminare l'accuratezza delle stime di tempo per ciascun provider.

Per generare un report Analisi di attività/provider, effettuare le seguenti operazioni.

1. A seconda del tipo di report che si desidera creare, effettuare uno di questi passaggi:

    - Selezionare **Costo sbarcato \> Report \> Analisi di attività/provider per attività**. In questo caso, le stime di tempo verranno raggruppate per attività.
    - Selezionare **Costo sbarcato \> Report \> Analisi di attività/provider per provider**. In questo caso, le stime di tempo verranno raggruppate per provider.

    Viene visualizzata la finestra di dialogo **Analisi di attività/provider per attività** o **Analisi di attività/provider per provider**. Le finestre di dialogo forniscono le stesse opzioni.

1. Come per altri tipi di report in Supply Chain Management, usare la Scheda dettaglio **Destinazione** per selezionare il formato di output del report.
1. Come per altri tipi di report in Supply Chain Management, utilizzare la Scheda dettaglio **Record da includere** per limitare ulteriormente i record che verranno inclusi nel report.
1. Scegliere **OK** per generare il report.

## <a name="voyage-costing-reports"></a>Report Costi di viaggio

I report Costi di viaggio mostrano il costo degli articoli e i costi di importazione per registrazione, contenitore di spedizione o viaggio, a seconda delle opzioni selezionate durante la generazione del report. Ogni report Costi di viaggio consente di visualizzare il costo stimato di un viaggio rispetto al costo effettivo e può essere suddiviso in base a diversi fattori di identificazione.

Per generare un report Costi di viaggio, effettuare le seguenti operazioni.

1. A seconda del tipo di report che si desidera creare, effettuare uno di questi passaggi:

    - Selezionare **Costo sbarcato \> Report \> Determinazione costi \> Costi di viaggio per singolo costo**. In questo caso, l'opzione relativa al singolo costo mostrerà i costi di importazione per area di costo per codice di tipo di costo.
    - Selezionare **Costo sbarcato \> Report \> Determinazione costi \> Costi di viaggio per categoria di reporting**. In questo caso, il costo di importazione sarà suddiviso nelle varie categorie di reporting. I tipi di costo sono raggruppati per categorie di reporting.

    Viene visualizzata la finestra di dialogo **Costi di viaggio per singolo costo** o **Costi di viaggio per categoria di reporting**. Queste finestre di dialogo sono simili. Eventuali differenze sono descritte nel resto di questa procedura.

1. Se si apre la finestra di dialogo **Costi di viaggio per categoria di reporting**, nel campo **Costo** selezionare uno dei seguenti valori:

    - **Valore di costo** - Il valore viene calcolato utilizzando i costi automatici o creati manualmente nell'area di costo.
    - **Stimato** - Dopo che la merce è stata ricevuta, viene impostato il costo stimato.
    - **Effettivo** - Dopo che l'ordine è stato fatturato, il costo effettivo viene impostato sul costo nella fattura.
    - **Migliore** - Il sistema utilizzerà la più accurata delle tre opzioni precedenti (è consigliabile selezionare questa opzione).

1. Impostare l'opzione **Per articolo** su *Sì* per mostrare il costo di ogni articolo. Impostarla su *No* per mostrare i costi per viaggio.
1. Nella sezione **Visualizza**, selezionare le categorie in base alle quali suddividere il costo.
1. Nella sezione **Dimensioni**, selezionare le dimensioni da includere nel report.
1. Come per altri tipi di report in Supply Chain Management, usare la Scheda dettaglio **Destinazione** per selezionare il formato di output del report.
1. Come per altri tipi di report in Supply Chain Management, utilizzare la Scheda dettaglio **Record da includere** per limitare ulteriormente i record che verranno inclusi nel report.
1. Scegliere **OK** per generare il report.

## <a name="shipping-container-receipts-list"></a>Elenco entrate contenitore di spedizione

L'elenco delle entrate del contenitore di spedizione contiene tutte le quantità non ricevute in scadenza entro una data prevista. Il personale del magazzino può utilizzare questo report per identificare le merci previste in un contenitore di spedizione. Può anche essere utilizzato per convalidare manualmente le merci quando vengono ricevute in un contenitore di spedizione.

Per generare un elenco di entrate di contenitore di spedizione, attenersi alla seguente procedura.

1. Selezionare **Costo sbarcato \> Report \> Tracciabilità \> Elenco entrate contenitore di spedizione**.
1. Nella finestra di dialogo **Elenco entrate contenitore di spedizione**, nel campo **Data prevista**, specificare una data. Qualsiasi quantità non ricevuta a quella data verrà inclusa nell'output.
1. Nella sezione **Dimensioni**, selezionare le dimensioni da includere nel report.
1. Come per altri tipi di report in Supply Chain Management, usare la Scheda dettaglio **Destinazione** per selezionare il formato di output del report.
1. Come per altri tipi di report in Supply Chain Management, utilizzare la Scheda dettaglio **Record da includere** per limitare ulteriormente i record che verranno inclusi nel report.
1. Scegliere **OK** per generare il report.

## <a name="expected-delivery-report"></a>Report Consegna prevista

Il report Consegna prevista contiene le informazioni di base su viaggio, contenitore di spedizione, registrazione e data di consegna prevista.

Per generare un report Consegna prevista, effettuare le seguenti operazioni.

1. Selezionare **Costo sbarcato \> Report \> Tracciabilità \> Consegna prevista**.
1. Nella finestra di dialogo **Consegna prevista**, nel campo **Data prevista**, selezionare la data in cui è prevista la consegna della merce al magazzino di destinazione finale. Qualsiasi linea di viaggio che ha una data prevista uguale o precedente a quella data e che non è stata ancora ricevuta, verrà inclusa nell'output.
1. Facoltativo: nel campo **Conto fornitore** selezionare un conto fornitore per includere solo le consegne di uno specifico fornitore.
1. Nella sezione **Dimensioni**, selezionare le dimensioni da includere nel report.
1. Come per altri tipi di report in Supply Chain Management, usare la Scheda dettaglio **Destinazione** per selezionare il formato di output del report.
1. Come per altri tipi di report in Supply Chain Management, utilizzare la Scheda dettaglio **Record da includere** per limitare ulteriormente i record che verranno inclusi nel report.
1. Scegliere **OK** per generare il report.
