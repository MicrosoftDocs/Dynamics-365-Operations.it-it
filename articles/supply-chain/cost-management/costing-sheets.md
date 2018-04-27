---
title: Schede di determinazione costi
description: "L'impostazione della scheda di determinazione costi prevede due obiettivi. Come primo obiettivo viene definito il formato di visualizzazione delle informazioni sul costo del venduto per un articolo prodotto o un ordine di produzione. La visualizzazione formattata è denominata scheda di determinazione costi. Come secondo obiettivo viene definita la base per il calcolo dei costi indiretti. L'impostazione della scheda di determinazione costi si basa sulla funzionalità gruppo di costi per visualizzare le informazioni e per le formule di calcolo dei costi indiretti. I due obiettivi dell'impostazione della scheda di determinazione costi sono descritti in questo articolo."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CostSheetDesigner
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53201
ms.assetid: e7d72b43-3892-49ae-8821-9eede3f4d24a
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 3988bd478cfad791b5d4c73d28a86c9cfb68288f
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="costing-sheets"></a>Schede di determinazione costi

[!INCLUDE [banner](../includes/banner.md)]

L'impostazione della scheda di determinazione costi prevede due obiettivi. Come primo obiettivo viene definito il formato di visualizzazione delle informazioni sul costo del venduto per un articolo prodotto o un ordine di produzione. La visualizzazione formattata è denominata scheda di determinazione costi. Come secondo obiettivo viene definita la base per il calcolo dei costi indiretti. L'impostazione della scheda di determinazione costi si basa sulla funzionalità gruppo di costi per visualizzare le informazioni e per le formule di calcolo dei costi indiretti. I due obiettivi dell'impostazione della scheda di determinazione costi sono descritti in questo articolo. 

Una scheda di determinazione costi è la visualizzazione formattata delle informazioni sul costo del venduto per un articolo prodotto o un ordine di produzione. Quando si imposta una scheda di determinazione costi, si definisce il formato delle informazioni e anche la base per il calcolo dei costi indiretti. L'impostazione della scheda di determinazione costi si basa sulle funzionalità gruppo di costi per visualizzare le informazioni e per le formule di calcolo dei costi indiretti. Di seguito sono riportate ulteriori informazioni sui due obiettivi dell'impostazione della scheda di determinazione costi:
-   **Definire il formato della scheda di determinazione costi.** Nel formato definito dall'utente per una scheda di determinazione costi viene specificata la segmentazione dei costi che includono il costo del venduto di un articolo prodotto. Ad esempio, le informazioni sul costo del venduto di un articolo possono essere segmentate in materiale, manodopera e costi generali in base a gruppi di costi assegnati agli articoli, a categorie di costi per le operazioni dei cicli di lavorazione e a formule di calcolo dei costi indiretti. Il formato della scheda di determinazione costi in genere richiede totali intermedi se vengono definiti più gruppi di costi, aggregando ad esempio più gruppi di costi relativi al materiale. La definizione di un formato per la scheda di determinazione costi è facoltativa, ma è necessaria se devono essere calcolati i costi indiretti.
-   **Definire la base per il calcolo dei costi indiretti.** I costi indiretti riflettono i costi generali di fabbricazione associati alla produzione di un articolo. Una formula di calcolo dei costi indiretti può essere espressa come supplemento o come tariffa. Un supplemento rappresenta una percentuale di valore, mentre una tariffa rappresenta un importo orario per un'operazione del ciclo di lavorazione. Un gruppo di costi definisce la base per la formula di calcolo, ad esempio un supplemento del 100% per un gruppo di costi di manodopera o una tariffa oraria di USD 50,00 per un gruppo di costi di macchine. Se si desidera definire una formula di calcolo e la relativa base del gruppo di costi, nell'impostazione della scheda di determinazione costi è necessario identificare il gruppo di costi che rappresenta i costi generali e selezionare se viene utilizzato un approccio basato su supplemento o tasso.

Ciascuna formula di calcolo deve essere immessa come record di costo. Il record di un costo è costituito da una versione di determinazione costi specificata, da una percentuale di supplemento o da un importo di tasso, dalla base del gruppo di costi, da uno stato e da una data di validità. Quando un record di costo viene immesso per la prima volta, ha lo stato **In sospeso** e una data di validità. Quando si attiva il record di costo, lo stato viene aggiornato in modo che il record sia quello attivo corrente e la data di validità viene aggiornata alla data di attivazione. Il record di costo può anche indicare un sito per una formula di calcolo specifica del sito. In alternativa, è possibile lasciare vuoto il campo **Sito** per indicare che la formula di calcolo è una formula valida a livello aziendale. Il record di costo può facoltativamente essere costituito da un articolo o da un gruppo di articoli specifico quando la formula di calcolo è stata contrassegnata come formula per articolo. 

I record di costo attivi correnti per le formule di calcolo dei costi indiretti sono utilizzati per la stima dei costi degli ordini di produzione e per il calcolo dei costi effettivi correlati al consumo effettivo di tempo e materiale. I record dei costi in sospeso vengono utilizzati nei calcoli DBA per una data futura. 

Due criteri di bloccaggio per una versione di determinazione costi determinano se è possibile gestire costi in sospeso e se il costo in sospeso può essere attivato. Utilizzare i criteri di bloccaggio per consentire la gestione dei dati e quindi per impedire la gestione dei dati per i dati dei costi in una versione di determinazione costi. 

Dopo aver definito il formato della scheda di determinazione costi e i calcoli dei costi indiretti, è necessario eseguire un passaggio a parte per la convalida e il salvataggio delle informazioni. La scheda di determinazione costi rappresenta un formato valido a livello aziendale per la visualizzazione uniforme delle informazioni sui costi del venduto. 

La scheda di determinazione costi viene visualizzata nella pagina **Calcola costo articolo**. La scheda di determinazione costi può essere visualizzata per il record del costo calcolato di un articolo prodotto nella pagina **Prezzo articolo** oppure per il record di calcolo specifico di un ordine nella pagina **Risultati calcolo DBA**. Può essere inoltre visualizzata nella pagina **Calcolo dei prezzi** per un ordine di produzione.






