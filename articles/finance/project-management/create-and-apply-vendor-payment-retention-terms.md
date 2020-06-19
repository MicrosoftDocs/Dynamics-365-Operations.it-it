---
title: Creare e applicare termini di ritenuta per pagamenti fornitore
description: In questo argomento vengono fornite informazioni sull'impostazione e la gestione dei termini di ritenuta per pagamenti fornitore.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410237"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a>Creare e applicare termini di ritenuta per pagamenti fornitore

[!include [banner](../includes/banner.md)] 

L'impostazione dei termini di ritenuta per pagamenti fornitore per un progetto è utile quando l'organizzazione desidera trattenere una parte dei pagamenti effettuati a un fornitore. Ad esempio, nel caso in cui si desidera trattenere il pagamento a un fornitore fino a quando i prodotti consegnati soddisfano le proprie aspettative. I termini di ritenuta per pagamenti fornitore possono essere specificati durante la negoziazione di un contratto fornitore.

## <a name="create-vendor-payment-retention-terms"></a>Creare termini di ritenuta per pagamenti fornitore

È possibile immettere la percentuale di ritenuta per un pagamento fornitore e la percentuale degli importi di ritenute precedenti da rilasciare. Gli importi vengono automaticamente considerati come ritenuta nelle fatture fornitore fino al raggiungimento dello stato di completamento specificato per il contratto. Dopo aver impostato i termini di ritenuta, è possibile applicarli a qualsiasi progetto per quel fornitore.

Utilizzare i passaggi seguenti per impostare e gestire i termini di ritenuta per pagamenti fornitori. 

1. Andare a **Gestione progetti e contabilità** > **Ritenuta** > **Termini ritenuta pagamento fornitore**.
2. Selezionare **Nuovo** per aggiungere termini di ritenuta fornitore. Viene automaticamente immesso il valore **ID regola** per il nuovo termine. 
3. Immettere una breve descrizione nel campo **Descrizione** e nella Scheda dettaglio **Termini**, selezionare **Aggiungi riga** per inserire i seguenti valori relativi ai termini:

   - **Percentuale di unità consegnate**: immettere una percentuale di completamento per i termini. Gli importi vengono automaticamente trattenuti nelle fatture fornitore fino a quando la fase di completamento del progetto non è uguale alla percentuale specificata. Ad esempio, se viene immesso il valore 50,00, gli importi vengono trattenuti finché il progetto non viene completato al 50%.
   - **Percentuale da trattenere**: immettere una percentuale dell'importo della fattura fornitore da trattenere. Ad esempio, se si immette 10,00, viene trattenuto il 10% dell'importo in una fattura fornitore finché il progetto non raggiunge la percentuale di completamento impostata nel campo **Percentuale di unità consegnate**.
   - **Percentuale da rilasciare**: selezionare **Aggiungi riga** per immettere una percentuale di qualsiasi importo di ritenuta precedente da rilasciare al raggiungimento del livello di completamento selezionato del progetto.

> [!NOTE]
> Se vi sono più punti cardine per diversi livelli di completamento del progetto, immettere una riga di termini di ritenuta fornitore separata per ogni regola di ritenuta. In ogni riga è possibile specificare una percentuale di ritenuta differente e una percentuale di rilascio differente per ogni livello specificato di completamento del progetto.

Dopo la creazione dei termini di ritenuta fornitore per un fornitore, è possibile applicarli a qualsiasi progetto.

## <a name="apply-vendor-retention-terms-to-a-project"></a>Applicare i termini di ritenuta fornitore a un progetto

1. Passare a **Gestione progetti e contabilità** > **Progetti** > **Tutti i progetti** e aprire il progetto dall'elenco dei progetti.
2. Nella Scheda dettaglio **Contratti fornitore** fare clic su **Aggiungi riga**.
3. Nel campo **Codice conto** selezionare una delle seguenti opzioni: 

   - **Tabella**: i termini di ritenuta fornitore vengono applicati a un unico venditore.
   - **Gruppo**: i termini di ritenuta fornitore vengono applicati a tutti i fornitori in un gruppo di fornitori.
   - **Tutti**: i termini di ritenuta fornitore vengono applicati a tutti i fornitori.

4. Nel campo **Fornitore/gruppo fornitori** selezionare il fornitore o il gruppo di fornitori a cui sono applicabili i termini di ritenuta fornitore. Se è stata selezionata l'opzione **Tutti** nel passaggio precedente, questo campo non è disponibile.
5. Nel campo **Termini di ritenuta fornitore**, selezionare i termini di ritenuta creati nella procedura precedente.
6. Se nel progetto per il fornitore sono impostati anche i termini Retribuisci su retribuzione, immettere la percentuale di soglia per il progetto nel campo **Percentuale soglia opzione Retribuisci su retribuzione**.

I termini di ritenuta fornitore vengono inoltre visualizzati negli ordini fornitore creati per il fornitore.
