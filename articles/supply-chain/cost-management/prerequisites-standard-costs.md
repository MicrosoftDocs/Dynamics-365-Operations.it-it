---
title: Prerequisiti per i costi standard
description: In questo argomento vengono descritti i passaggi di base per l'utilizzo dei costi standard.
author: AndersGirke
manager: AnnBe
ms.date: 01/17/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventStdCostConv, CostingVersion
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e63f2b4289b640e601492425331ea8f3804d139a
ms.openlocfilehash: 4f505a2de89863d1a12d415795fdfb82b3557bc0
ms.contentlocale: it-it
ms.lasthandoff: 01/17/2018

---

# <a name="prerequisites-for-standard-costs"></a>Prerequisiti per i costi standard

[!include[banner](../includes/banner.md)]


In questo argomento vengono descritti i passaggi di base per l'utilizzo dei costi standard. I passaggi successivi dipendono dalle operazioni svolte dalla società. Ad esempio, i passaggi variano a seconda che si operi in un ambiente non di produzione, in un ambiente di produzione che non utilizza cicli di lavorazione o in un ambiente di produzione che utilizza cicli di lavorazione. 

Per impostare i costi standard, effettuare le operazioni indicate di seguito.

**1. Creare un gruppo di modelli di articoli per costi standard.**

Utilizzare la pagina **Gruppi di modelli di articoli** per creare un nuovo gruppo per costi standard e assegnare un modello inventariale **Costo standard**. Assegnare un identificatore significativo al gruppo di modelli di articoli, ad esempio **Costo standard**. Selezionare le caselle di controllo appropriate per indicare che il gruppo deve consentire le scorte finanziarie negative e che deve effettuare la registrazione dell'inventario fisico e dell'inventario finanziario. Questo gruppo di costi standard verrà assegnato agli articoli.

**2. Definire conti CoGe correlati a scostamenti dei costi standard.** 

Utilizzare la pagina **Piano dei conti** per definire conti CoGe correlati a scostamenti dei costi standard. Questi conti CoGe devono essere definiti prima dell'assegnazione nella pagina **Registrazione**. I conti CoGe possono riflettere gruppi di articoli e gruppi di costi.

**3. Assegnare conti CoGe a registrazioni articoli correlate a scostamenti dei costi standard.** 

Utilizzare la pagina **Registrazione** per assegnare i conti CoGe correlati a scostamenti dei costi standard. È possibile specificare il conto CoGe di uno scostamento per articolo o gruppo di articoli oppure per gruppo di costi o tipo di gruppo di costi, nonché specificare che il conto CoGe si applica a tutti gli articoli e a tutti i gruppi di costi. Queste opzioni corrispondono alle relazioni costi per tabelle, gruppi e tutto. 

Prima di definire le regole di registrazione articoli, utilizzare il modulo **Combinazioni di transazioni** per attivare le relazioni costi (per tabelle, gruppi e tutti gli elementi).

**4. Definire parametri di Gestione articoli correlati ai costi standard.** 

-  Utilizzare la scheda **Distinte base** nella pagina **Parametri Gestione articoli** per definire due parametri di controllo dei costi correlati ai costi standard. 

    -  Nel campo **Scomposizione costi** selezionare **Nessuna** o **Contabilità secondaria**. Se si seleziona **Contabilità secondaria**, la scomposizione dei costi sarà una scomposizione costi *attiva*. La scomposizione dei costi attiva è fondamentale per il calcolo, il mantenimento e la visualizzazione della segmentazione per gruppi di costi in una struttura di prodotti multilivello per voci di costo standard. Quando la scomposizione dei costi è attiva, è possibile eseguire il reporting e l'analisi dell'inventario, di WIP e del costo del venduto (COGS) per gruppo di costi in un formato a livello singolo, multilivello o totale. Quando la scomposizione dei costi è attiva, se si attiva un costo di un articolo prodotto, questo determina l'archiviazione della segmentazione dei gruppi di costi nel record del costo dell'articolo. 

    -  Se si seleziona **Nessuna**, non verrà eseguita nessuna segmentazione per gruppi di costi per le voci di costo standard. Ovvero, il costo standard di un articolo prodotto verrà calcolato e gestito come singolo importo, senza segmentazione per gruppi di costi. I contributi costi dei componenti prodotti verranno aggregati nell'importo singolo.

-  Nel campo **Scostamenti rispetto a standard** selezionare **Riepilogo** o **Per gruppo di costo**. Se si seleziona l'opzione **Per gruppo di costo** è possibile identificare gli scostamenti dei prezzi di acquisto e gli scostamenti produzione per gruppo di costi. È anche possibile di identificare i quattro tipi di scostamenti produzione, ovvero Scostamento dimensioni lotto, Scostamento quantità, Scostamento prezzi e Scostamento sostitutivo. Se si seleziona **Riepilogo**, non è possibile identificare gli scostamenti per gruppo di costi né identificare i quattro tipi di scostamenti produzione. Sarà solo possibile visualizzare uno scostamento produzione riepilogativo.

-  Il criterio relativo allo scostamento rispetto al costo standard funziona in modo indipendente dal criterio di scomposizione dei costi. È possibile pertanto impostare il criterio di scomposizione dei costi su **Nessuna** e gli scostamenti su Per gruppo di costo in modo che vengano comunque acquisiti gli scostamenti produzione per gruppo di costi.

**5. Creare versioni di determinazione costi per i costi standard.** 

Utilizzare la pagina **Impostazione versione di determinazione costi** per creare una o più versioni di determinazione costi per i costi standard. Ciascuna versione di determinazione costi deve essere designata da un tipo di determinazione costi di **Costo standard** e deve consentire l'inclusione di dati relativi ai costi nel contenuto.

**6. Preparare un cliente esistente per l'utilizzo dei costi standard.** 

I clienti che desiderano cambiare gli articoli esistenti e impostare un modello inventariale Costo standard devono utilizzare la pagina **Conversioni costo standard**.


<a name="related-topics"></a>Argomenti correlati
--------

[Panoramica della conversione in costo standard](standard-cost-conversion-overview.md)


