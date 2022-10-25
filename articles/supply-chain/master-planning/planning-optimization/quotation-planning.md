---
title: Piani basati su preventivi e richieste di offerta
description: Questo articolo descrive come configurare la pianificazione generale per considerare le offerte e le richieste di offerta (RFQ) quando genera ordini pianificati.
author: t-benebo
ms.date: 09/20/2022
ms.topic: article
ms.search.form: SalesQuotationListPage, ReqPlanSched, SalesQuotationTable, smmOpportunityTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-20
ms.dyn365.ops.version: 10.0.30
ms.openlocfilehash: eaeb3c26a562c1daebe8296b26077ee5a3223e4d
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690095"
---
# <a name="plan-based-on-quotations-and-rfqs"></a>Piano basato su preventivi e richieste di offerta

[!include [banner](../../includes/banner.md)]

I preventivi e le richieste di offerta (RFQ) rappresentano possibili o addirittura probabili ordini futuri. Pertanto, ha senso prenderli in considerazione durante la pianificazione generale, in modo che sia possibile pianificare una fornitura aggiuntiva in base alle richieste di offerta esistenti e alla probabilità che ogni preventivo diventi un ordine effettivo. Questo articolo descrive come configurare la pianificazione generale per considerare le offerte e le richieste di offerta quando genera ordini pianificati.

## <a name="set-up-master-planning-to-consider-sales-quotations-andor-rfqs"></a>Configurare la pianificazione generale per considerare le offerte di vendita e/o le richieste di offerta

Utilizza la procedura seguente per configurare la pianificazione generale in modo da prendere in considerazione le offerte di vendita e/o le richieste di offerta.

1. Vai a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Seleziona un piano esistente nel riquadro dell'elenco oppure seleziona **Nuovo** per crearne uno nuovo.
1. Nella scheda dettaglio **Generale**, impostare i seguenti campi:

    - **Includi preventivi di vendita** – Imposta questa opzione su *Sì* per prendere in considerazione le offerte di vendita quando viene eseguito il piano corrente. Impostala su *No* per ignorarli.
    - **% di probabilità** – Imposta il livello minimo di attendibilità richiesto per l'inclusione di un'offerta nella pianificazione generale. Il calcolo della pianificazione generale includerà tutte le offerte create da opportunità che hanno questa percentuale di probabilità o superiore. Per includere tutte le offerte, comprese le offerte a cui non è stata assegnata alcuna probabilità o a cui non è associata alcuna opportunità, imposta questo campo su *0* (zero). Per ulteriori informazioni sulle probabilità per le offerte, vedi la sezione successiva.
    - **Includi richieste di offerte** – Imposta questa opzione su *Sì* per prendere in considerazione le richieste di offerta quando viene eseguito il piano corrente. Impostala su *No* per ignorarli. Se scegli di prendere in considerazione le richieste di offerta, il sistema creerà per loro ordini di acquisto pianificati, ma non specificherà il fornitore fino a quando la richiesta di offerta non sarà stata risolta. Gli ordini di acquisto pianificati creati per le richieste di offerta potrebbero influire sulle quantità di altri ordini pianificati.

1. Continua a configurare il tuo piano generale nel solito modo.

## <a name="assign-and-view-probabilities-for-quotations"></a>Assegnare e visualizzare le probabilità per le citazioni

Come accennato nella sezione precedente, un piano generale prenderà in considerazione solo le offerte che soddisfano o superano la soglia di probabilità definita per il piano (se è definita una soglia). Tuttavia, la probabilità non è impostata direttamente su ciascuna offerta. Viene invece ereditato dall'opportunità utilizzata per generare l'offerta. Pertanto, le offerte che vengono create direttamente nella pagina **Tutte le offerte** non avranno una probabilità assegnata loro o un'opportunità ad esse associata e non saranno mai prese in considerazione dalla pianificazione generale (a meno che il campo **% di probabilità** non sia impostato su *0* \[zero\]). Per avere una probabilità assegnata ad esso, un'offerta deve essere generata da un'opportunità.

### <a name="create-a-quotation-from-an-opportunity"></a>Creare un'offerta da un'opportunità

Utilizza la procedura seguente per assegnare una probabilità a un'opportunità e quindi creare un'offerta da tale opportunità.

1. Vai a **Vendite e marketing \> Relazioni \> Opportunità \> Tutte le opportunità**.
1. Seleziona un'opportunità esistente oppure seleziona **Nuovo** nel riquadro Azioni per crearne uno nuovo.
1. Compila la pagina dell'opportunità per identificare l'opportunità come desideri. Assicurati di impostare il campo **Probabilità** su un valore appropriato. Solo i piani generali configurati per cercare probabilità di questo valore o superiori prenderanno in considerazione le offerte generate da questa opportunità.
1. Nel riquadro azioni selezionare **Salva**.
1. Nel riquadro Azioni, nella scheda **Opportunità**, nel gruppo **Nuovo**, seleziona **Offerta di vendita** o **Offerta di progetto**, a seconda del tipo di offerta che si desidera creare.
1. Nella finestra dialogo **Crea offerta**, imposta i campi come richiesto e quindi seleziona **OK**.
1. Viene creata e aperta una nuova offerta. Nella Scheda dettaglio **Righe**, utilizza la barra degli strumenti per aggiungere righe di vendita come richiesto per definire il contenuto dell'offerta.
1. Nel riquadro azioni selezionare **Salva**. Quindi, chiudi l'offerta.

### <a name="view-the-probability-that-is-assigned-to-a-quotation"></a>Visualizzare la probabilità che venga assegnata a un'offerta

L'unico modo per visualizzare la probabilità assegnata a un'offerta consiste nell'aprire l'opportunità utilizzata per creare l'offerta, come descritto nella procedura seguente.

1. Vai a **Vendite e marketing \> Offerte di vendita \> Tutte le offerte**.
1. Se la colonna **ID opportunità** non viene mostrata (è nascosta in un'installazione predefinita), segui questi passaggi per mostrarla temporaneamente. (In alternativa, per mantenere la colonna **ID opportunità** disponibile, crea una [visualizzazione salvata](../../../fin-ops-core/fin-ops/get-started/saved-views.md?toc=/dynamics365/supply-chain/toc.json) che la includa).

    1. Seleziona e tieni premuta (o fai clic con il pulsante destro del mouse) la griglia, quindi seleziona **Inserisci colonne**.
    1. Nella finestra di dialogo **Inserisci colonne**, trova la riga in cui il campo **Campo** è impostato su *Opportunità* e seleziona la casella di controllo **Seleziona** per quella riga.
    1. Seleziona **Aggiorna** per aggiungere la colonna selezionata alla pagina **Tutte le offerte**.

1. Nella griglia, trova la riga per l'offerta pertinente. Poi, nella colonna **ID opportunità**, seleziona il valore per quella riga.

    > [!NOTE]
    > Se stai cercando un'offerta di progetto, è consigliabile selezionare l'intestazione di colonna **Tipo di offerta** e deselezionare il relativo filtro. In un'installazione predefinita, questo filtro è impostato in modo che vengano visualizzate solo le offerte di vendita.

1. Si apre la relativa opportunità. È ora possibile visualizzare e modificare il valore **Probabilità** come richiesto.
