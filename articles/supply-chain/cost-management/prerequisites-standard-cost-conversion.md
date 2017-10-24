---
title: Prerequisiti per la conversione in costo standard
description: "In questo argomento vengono illustrate le attività da completare prima di eseguire una conversione in costo standard."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 50891
ms.assetid: 73af66cf-c924-45be-837a-a648dbd05a31
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0ee55ef8a1d7ee47ff3b7d24b50da613dd2ac4ce
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="prerequisites-for-a-standard-cost-conversion"></a>Prerequisiti per la conversione in costo standard

[!include[banner](../includes/banner.md)]


In questo argomento vengono illustrate le attività da completare prima di eseguire una conversione in costo standard. 

Prima di eseguire una conversione in costo standard, completare i seguenti passaggi.

1.  Definire un **gruppo di modelli di articoli** per costi standard. Utilizzare la pagina Gruppi di modelli di articoli per creare un gruppo di modelli di articoli con un modello inventariale di tipo costo standard. Per impostare una conversione in costo standard, è necessario assegnare questo gruppo di modelli di articoli agli articoli che devono essere convertiti.
2.  Assegnare un **gruppo di costi** a ciascun articolo.
    -   Il gruppo di costi assegnato a un articolo acquistato può funzionare come base per l'assegnazione di conti CoGe correlati ai costi standard, ad esempio per l'assegnazione di conti CoGe per scostamenti dei prezzi di acquisto. In un ambiente di produzione, anche il gruppo di costi assegnato ai componenti acquistati fornisce la segmentazione dei costi nei costi calcolati di un articolo prodotto.
    -   Il gruppo di costi assegnato a un articolo prodotto può funzionare come base per l'assegnazione di conti CoGe correlati ai costi standard, ad esempio per l'assegnazione di conti CoGe per scostamenti della produzione.

3.  Assegnare una **quantità ordine standard** a un articolo prodotto con costi costanti. La quantità ordine standard per un articolo prodotto funziona come dimensioni lotto di contabilità per ammortizzare (o ripartire proporzionalmente) i costi costanti, ad esempio i tempi di impostazione nelle operazioni dei cicli di lavorazione o una quantità di componenti costante in una distinta base (DBA).
4.  Assegnare **conto CoGe** correlati ai costi standard, in particolare lo scostamento di rivalutazione. Utilizzare la pagina **Registrazione** (**Gestione articoli** &gt; **Impostazioni**) per assegnare conti CoGe correlati ai costi standard. I requisiti minimi per il processo di conversione a costo standard prevedono l'assegnazione del conto relativo allo scostamento di rivalutazione per tutti gli articoli e per tutti i gruppi di costi. Utilizzare la pagina **Piano dei conti** per definire i conti CoGe che saranno necessari per i costi standard. Utilizzare il modulo **Combinazioni di transazioni** per attivare le relazioni costi (per tabelle, gruppi e tutti gli elementi) prima di definire le regole di registrazione articoli.
5.  Definire i parametri di Gestione articoli correlati ai costi standard. Utilizzare la scheda **Sequenze numeriche** nella pagina **Parametri di Gestione articoli e magazzino** per assegnare una sequenza numerica ai giustificativi di rivalutazione. Il giustificativo di rivalutazione viene generato quando la conversione a costo standard determina una variazione del valore di magazzino di un articolo. Utilizzare la pagina **Parametri di Gestione articoli e magazzino** per definire i parametri di controllo dei costi (nella scheda **Contabilità inventario**) per definire due parametri correlati ai costi standard.
    -   Utilizzare il campo **Scomposizione costi** per selezionare No o contabilità secondaria. La selezione di contabilità secondaria è definita scomposizione dei costi attiva. La scomposizione dei costi attiva è fondamentale per il calcolo, il mantenimento e la visualizzazione della segmentazione per gruppi di costi in una struttura di prodotti multilivello per voci di costo standard. Quando la scomposizione dei costi è attiva, è possibile eseguire il reporting e l'analisi dei seguenti elementi in un formato a livello singolo, multilivello o totale:
        1.  Scorte
        2.  Semilavorati (WIP)
        3.  Costo del venduto (COGS) per gruppo di costi

        Con una scomposizione dei costi attiva, l'attivazione del costo di un articolo prodotto determina l'archiviazione della segmentazione dei gruppi di costi nel record del costo dell'articolo. Se non si immette alcun valore nel campo **Scomposizione costi**, non verrà eseguita la segmentazione per gruppi di costi per le voci di costo standard. Il costo standard di un articolo prodotto verrà pertanto calcolato e gestito come singolo importo, senza segmentazione per gruppi di costi e i contributi costi dei componenti prodotti verranno aggregati nell'importo singolo.
    -   Impostare il campo **Scostamenti rispetto a standard** su Riepilogo o Per gruppo di costo. L'opzione Per gruppo di costo consente di identificare gli scostamenti dei prezzi di acquisto e gli scostamenti produzione per gruppo di costi, nonché di identificare i quattro tipi di scostamenti produzione, ovvero Scostamento dimensioni lotto, Scostamento quantità, Scostamento prezzi e Scostamento sostitutivo. Se si seleziona Riepilogo, non sarà possibile identificare gli scostamenti per gruppo di costi né identificare i quattro tipi di scostamenti produzione. Sarà possibile visualizzare solo uno scostamento produzione riepilogativo. I criteri relativi allo scostamento rispetto al costo standard sono indipendenti dai criteri di scomposizione dei costi. È possibile pertanto impostare il criterio di scomposizione dei costi su nessuno e gli scostamenti su Per gruppo di costo in modo che vengano comunque acquisiti gli scostamenti produzione per gruppo di costi.






