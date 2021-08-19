---
title: Visibilità nelle eccezioni materiali
description: In questo argomento viene descritto come è possibile migliorare la visibilità delle eccezioni per le materie prime per gli ordini di produzione e gli ordini batch.
author: johanhoffmann
ms.date: 10/30/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: JmgShopSupervisorWorkspace, WHSProdWaveTableListPage, WHSProdWaveTableManageBOMPool
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: d3ea260535e76d7ac3d73d4bca930b7b4b2d22b2b2c076d4d1346785eaed85b8
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726803"
---
# <a name="visibility-into-material-exceptions"></a>Visibilità nelle eccezioni materiali

[!include [banner](../includes/banner.md)]

Nell'area di lavoro **Gestione area di produzione** tre riquadri consentono una migliore visibilità delle eccezioni per le materie prime per gli ordini di produzione e gli ordini lotto:

- Righe materiale non rilasciate che richiedono attenzione
- Ondate inevase che richiedono attenzione
- Lavoro magazzino aperto che richiede attenzione

Per tutte e tre i riquadri, la data di materie prime delle righe distinta base (BOM) e le righe formula viene comparata con la data dell'area di lavoro nonché i filtri per **Unità di produzione**, **Gruppo di risorse** e **Risorsa** che sono impostati nel menu **Configura area di lavoro personale**. Per impostazione predefinita, la data dell'area di lavoro è impostata sulla data corrente, ma è possibile modificarla.

Una riga DBA o una riga formula non rilasciate richiedono attenzione se la data della materia prima della riga è uguale o precedente alla data dell'area di lavoro e se soddisfa i criteri definiti dai filtri nell'area di lavoro.

Nella seguente figura, la barra blu rappresenta un processo di produzione programmato per una risorsa. Il processo è programmato per l'inizio il 1° maggio (01/05/2017). Questa data spesso corrisponde alla data della materia prima. Ovvero, i materiali assegnati al processo nella DBA e nelle righe formula devono essere pronti per questa data. L'altra data nella figura, il 6 maggio 2017 (06/05/2017), rappresenta la data dell'area di lavoro. In questo esempio, la data della materia prima è precedente alla data dell'area di lavoro. Pertanto, la data in cui il consumo della materia prima doveva iniziare è passata e la distinta base e le righe formula soddisfano i criteri per richiedere attenzione.

![Esempio di processo di produzione in cui la data della materia prima è precedente alla data dell'area di lavoro.](./media/improved-visibility.png)

## <a name="unreleased-material-lines-needing-attention"></a>Righe materiale non rilasciate che richiedono attenzione

Una DBA o una riga formula può essere rilasciata nel magazzino in tre modi:

- Come parte del rilascio di un ordine di produzione o batch
- Come rilascio manuale
- Automaticamente mediante un processo batch

Per ulteriori informazioni, vedere [Rilascio delle righe di formula e DBA nel magazzino](releasing-bom-and-formula-lines-to-warehouse.md). 

Se una DBA o una riga della formula non è stata rilasciata o è stata rilasciata solo parzialmente, e se i criteri di data e filtro dell'area di lavoro sono soddisfatti, la riga viene inclusa nel calcolo del numero visualizzato nel riquadro **Righe materiale non rilasciate che richiedono attenzione**.

Quando si selezionano i riquadri, viene aperta la pagina **Rilascia in magazzino**. In questa pagina vengono visualizzati il numero di DBA e righe formula non rilasciate indicate dal numero sul riquadro. Le righe non rilasciate vengono visualizzate nella griglia superiore. Questa griglia mostra la quantità originariamente stimata per la riga, la quantità che è stata già rilasciata e la quantità rimanente che deve ancora essere rilasciata. È possibile aggiungere righe dalla griglia superiore alla griglia inferiore. Nella griglia inferiore, è possibile quindi rilasciare le righe selezionate in magazzino. Nella griglia inferiore, è inoltre possibile rettificare la quantità da rilasciare in modo da rilasciare solo una quantità parziale.

## <a name="unprocessed-waves-needing-attention"></a>Ondate inevase che richiedono attenzione

Quando una DBA o una riga formula viene rilasciata, viene aggiunta a una nuova ondata di produzione o a un'ondata aperta esistente, in base alla configurazione del modello di ondata di produzione. Tramite la configurazione del modello d'ondata, si può anche impostare un'ondate in modo che venga elaborata automaticamente quando viene rilasciata una distinta base o una riga formula Quando l'ondata viene elaborata, il lavoro di magazzino per il prelievo della materia prima viene creato. Se il modello d'ondata è configurato in modo tale che le ondate non vengano elaborate al momento del rilascio, l'ondata rimane in uno stato non elaborato. Il riquadro **Ondate inevase che richiedono attenzione** indica il numero di DBA e righe formula rilasciate in magazzino in ondate non elaborate e con data di materie prime precedente o uguale alla data dell'area di lavoro. Le righe devono essere utilizzate anche da una risorsa operativa che si applica al filtro dell'area di lavoro.

Quando il riquadro è selezionato, la pagina **Tutte le ondate di produzione** viene aperta. Questa pagina viene filtrata per numero di ondate aperte che contengono righe d'ondata di DBA e righe formula rilasciate che soddisfano i criteri per il riquadro.

### <a name="manually-maintain-production-waves"></a>Mantenere manualmente i cicli di produzione

Sulla pagina **Tutti i cicli di produzione** puoi usare i pulsanti della scheda **Ciclo** del riquadro azioni per **elaborare** e **rilasciare** manualmente un ciclo. Puoi anche usare l'opzione **Mantieni produzioni** per visualizzare e mantenere i dati del **pool DBA di produzione** che vengono utilizzati per gestire il processo di ciclo.

## <a name="open-warehouse-work-needing-attention"></a>Lavoro di magazzino aperto che richiede attenzione

Il riquadro **Lavoro magazzino aperto che richiede attenzione** indica il numero di DBA e righe formula rilasciate in magazzino con lavoro non elaborato e con data di materie prime precedente o uguale alla data dell'area di lavoro. Le righe devono essere utilizzate anche da una risorsa operativa che si applica al filtro dell'area di lavoro.

Quando il riquadro è selezionato, la pagina **Tutto il lavoro** si apre. Questa pagina viene filtrata per numero di intestazioni di lavoro aperte che contengono righe di lavoro di DBA e righe formula rilasciate che soddisfano i criteri per il riquadro. Nella pagina **Tutto il lavoro** è possibile elaborare manualmente il lavoro.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]