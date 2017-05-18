---
title: Aggiornare i costi standard per un nuovo articolo prodotto
description: Questo articolo fornisce indicazioni per aggiornare i costi standard per un nuovo articolo prodotto.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 79693
ms.assetid: ba64b70f-3f4c-4373-9a7d-8fd07c45a8cf
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: fb9f7b8aa9198b66f196613641de5237fac2ac2c
ms.contentlocale: it-it
ms.lasthandoff: 04/25/2017


---

# <a name="update-standard-costs-for-a-new-manufactured-item"></a>Aggiornare i costi standard per un nuovo articolo prodotto

[!include[banner](../includes/banner.md)]


Questo articolo fornisce indicazioni per aggiornare i costi standard per un nuovo articolo prodotto. 

Nelle seguenti indicazioni si presuppone che venga utilizzato per l'aggiornamento dei costi standard un approccio basato su due versioni. In tale approccio, una versione di determinazione costi contiene i costi standard inizialmente definiti per il periodo bloccato e la seconda versione di determinazione costi contiene gli aggiornamenti incrementali dei nuovi articoli prodotti. Gli aggiornamenti incrementali verranno immessi come record costi nella seconda versione di determinazione costi e infine verranno attivati. L'approccio basato su due versioni richiede la definizione di una seconda versione di determinazione costi. Di seguito sono riportate le indicazioni per la definizione di tale versione.

-   Assegnare un tipo di determinazione costi di **Costo standard**.
-   Assegnare un identificatore significativo che indichi il contenuto della versione di determinazione costi, ad esempio **AGGIORNAMENTI-2016**.
-   Nel gruppo di campi **Consenti tipo di prezzo**, verificare che **Prezzo di costo** sia impostato su **Sì**.
-   Consente l'immissione di record costi per tutti i siti (ciò significa lasciare vuoto il campo **Sito**). Se si immette un sito, è possibile immettere i record costi solo per tale sito.
-   Utilizzare un principio di fallback **Attivo**.

Per aggiungere nuovi articoli prodotti durante il periodo bloccato, effettuare le seguenti operazioni.

1.  Utilizzare la pagina **Impostazione versione di determinazione costi** per attivare i record costi da inserire nella seconda versione di determinazione costi che contiene gli aggiornamenti incrementali. Impedire l'attivazione dei costi in sospeso, in modo che l'attivazione venga consentita dopo che i costi in sospeso sono stati definiti in modo completo e accurato. Indicare una data iniziale vuota come criterio nella versione di determinazione costi, quindi immettere la data iniziale quando viene immesso ciascun record di costo. La data iniziale deve rappresentare una data antecedente all'acquisto o alla fabbricazione dei nuovi articoli.
2.  Utilizzare la pagina **Prezzo articolo** per immettere record costi per i nuovi articoli acquistati. Per ciascun record di costo, immettere la versione di determinazione costi contenente gli aggiornamenti incrementali, quindi utilizzare una data iniziale antecedente alla data di fabbricazione prevista per i nuovi articoli prodotti.
3.  Calcolare tramite la pagina **Calcolo** il costo dei nuovi articoli prodotti. Aprire la pagina **Calcolo** dalla pagina **Gestione versione di determinazione costi** e selezionare la versione di determinazione costi contenente gli aggiornamenti incrementali. Utilizzare i criteri di selezione per specificare il nuovo articolo prodotto e uno degli eventuali componenti prodotti correlati. In una struttura di prodotti multilivello può inoltre essere necessario specificare l'eventuale articolo principale contenente come componente i nuovi articoli prodotti. Immettere per il calcolo della distinta base (DBA) una data iniziale corrispondente all'inizio della fabbricazione dei nuovi articoli. La data iniziale deve essere compresa tra le date di validità della versione DBA e della versione del ciclo di lavorazione dell'articolo. **Nota**: un record costi mancante può indicare un nuovo articolo prodotto. I calcoli DBA possono essere limitati agli articoli con costi mancanti.
4.  Verificare la completezza e l'accuratezza dei costi calcolati per i nuovi articoli prodotti. Utilizzare la pagina **Completata** per esaminare i costi calcolati per il record costo di ogni articolo e l'eventuale registro dei messaggi di avviso. In alternativa, utilizzare la pagina **Calcolo** per esaminare i costi calcolati.
5.  Utilizzare la pagina **Impostazione versione di determinazione costi** per modificare il flag di blocco per consentire l'attivazione dei record costi in sospeso nella seconda versione di determinazione costi.
6.  Utilizzare la pagina **Attiva prezzi** (accessibile dalla pagina **Gestione versione di determinazione costi**) per attivare tutti i record di costo articolo in sospeso nella seconda versione di determinazione costi. È inoltre possibile attivare i record costi in sospeso per i singoli articoli facendo clic sul pulsante **Attiva** nella pagina **Prezzo articolo**.
7.  Utilizzare la pagina **Impostazione versione di determinazione costi** per modificare i flag di blocco nella seconda versione di determinazione costi per evitare ulteriori operazioni di manutenzione dati. I criteri di bloccaggio impediranno l'immissione di nuovi costi in sospeso e l'attivazione dei costi in sospeso.





