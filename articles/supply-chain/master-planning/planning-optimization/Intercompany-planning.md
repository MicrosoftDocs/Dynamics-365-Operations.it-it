---
title: Pianificazione interaziendale
description: Questo argomento descrive la pianificazione interaziendale e spiega come configurare la pianificazione interaziendale con Ottimizzazione pianificazione in Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: a3b48667bb266fec082c48e777fd71d8e5ef6dae
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6357025"
---
# <a name="intercompany-planning"></a>Pianificazione interaziendale

[!include [banner](../../includes/banner.md)]

Per alcune organizzazioni, le operazioni logistiche dipendono da altre persone giuridiche (società) nell'organizzazione. Queste operazioni vengono gestite utilizzando le vendite e gli acquisti interaziendali, poiché ogni persona giuridica ha un piano dei conti separato.

Questo argomento descrive la pianificazione interaziendale e spiega come configurare la pianificazione interaziendale con Ottimizzazione pianificazione in Microsoft Dynamics 365 Supply Chain Management.

In questo argomento vengono utilizzati i seguenti importanti termini interaziendali:

- **Upstream** - Un riferimento relativo in un'azienda o catena di approvvigionamento. Indica il movimento nella direzione del fornitore della materia prima.
- **Downstream** - Un riferimento relativo in un'azienda o catena di approvvigionamento. Indica il movimento nella direzione del cliente.
- **Domanda interaziendale pianificata** - Domanda pianificata per un prodotto in un'azienda, basata sulla domanda pianificata per il prodotto da un'azienda downstream.

Nella pianificazione generale, un piano in una società può includere una domanda interaziendale pianificata correlata agli ordini pianificati di un piano di un'altra società. Questa funzionalità è utile perché fornisce piena visibilità degli ordini pianificati tra le aziende. Assicura inoltre che tutti gli ordini di fornitura pianificati richiesti vengano creati, ma senza richiedere che gli ordini pianificati vengano consolidati per la domanda interaziendale.

Se si esegue la pianificazione generale da un piano generale che include la domanda downstream pianificata, gli ordini fornitore pianificati dai fornitori interaziendali correlati verranno inclusi nel piano come domanda.

## <a name="required-setup"></a>Impostazione richiesta

Per utilizzare la pianificazione interaziendale, è necessario preparare il sistema nel modo seguente:

1. I prodotti rilevanti devono essere rilasciati in tutte le società interessate. Per ulteriori informazioni, vedere [Configurare e usare il commercio interaziendale in Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) in Microsoft Learn.
1. La domanda downstream deve essere coperta da acquisti da un fornitore che ha una relazione interaziendale con la società upstream e le relative dimensioni di inventario predefinite (sito e magazzino) per il cliente. Per ulteriori informazioni, vedere [Configurare e usare il commercio interaziendale in Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) in Microsoft Learn.
1. Il piano generale nella società upstream deve includere la domanda downstream pianificata e la società e il piano generale pertinenti devono essere specificati nei piani downstream.

## <a name="include-planned-downstream-demand"></a>Includi domanda downstream pianificata

Seguire questi passaggi per configurare il piano generale in modo che includa la domanda downstream pianificata.

1. Andare a **Pianificazione generale \> Impostazioni \> Piani \> Piani generali**.
1. Selezionare o creare un piano generale.
1. Nella scheda dettaglio **Pianificazione interaziendale**, impostare i seguenti campi:

    - **Includi domanda downstream pianificata** - Impostare questa opzione su *Sì* per abilitare la pianificazione interaziendale per il piano generale.
    - **Piani downstream** - Se si imposta l'opzione **Includi domanda downstream pianificata** su *Sì*, utilizzare la barra degli strumenti e la griglia per aggiungere i piani generali desiderati da altre società.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Pegging tra le aziende utilizzando il pegging multilivello

Nel pegging multilivello, è possibile visualizzare il pegging tra le società per vedere l'origine iniziale della domanda coperta da una fornitura.

Per visualizzare le informazioni sul pegging multilivello, attenersi alla seguente procedura.

1. Andare a **Pianificazione generale \> Pianificazione generale \> Ordini pianificati**.
1. Selezionare o aprire un ordine pianificato.
1. Nella scheda **Visualizza** del riquadro azioni, nel gruppo **Requisiti**, selezionare **Pegging multilivello**.

### <a name="intercompany-example-that-involves-two-companies"></a>Esempio interaziendale che coinvolge due società

In questo esempio, viene creato un ordine di produzione pianificato nella società USMF per coprire un ordine cliente nella società DEMF. In USMF, la domanda diretta è la domanda interaziendale pianificata. Per far apparire questa domanda in USMF, la pianificazione generale viene eseguita prima in DEMF e poi in USMF.

La seguente illustrazione mostra come questo esempio potrebbe apparire nella pagina **Pegging multilivello** per l'ordine di produzione pianificato.

![Esempio interaziendale che coinvolge due società.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Esempio interaziendale che coinvolge tre società

In questo esempio, viene creato un ordine fornitore pianificato nella società USMF per coprire un ordine cliente nella società FRRT. Nelle società DEMF e USMF, la domanda diretta è la domanda interaziendale pianificata. Per far apparire questa domanda in USMF, la pianificazione generale viene eseguita prima in FRRT, poi in DEMF e infine in USMF.

La seguente illustrazione mostra come questo esempio potrebbe apparire nella pagina **Pegging multilivello** per l'ordine di produzione pianificato.

![Esempio interaziendale che coinvolge tre società.](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]