---
title: Home page di pianificazione generale
description: "La pianificazione generale consente alle società di determinare ed equilibrare il fabbisogno futuro di materie prime e la capacità di soddisfare gli obiettivi aziendali."
author: YuyuScheller
manager: AnnBe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 18ed011fa1c1aa35b4a401d51bffc6af19395577
ms.openlocfilehash: 030579ac73d6333ac4ed55433b9679a58247c088
ms.contentlocale: it-it
ms.lasthandoff: 02/13/2018

---

# <a name="master-planning-home-page"></a>Home page di pianificazione generale

[!INCLUDE [banner](../includes/banner.md)]

Fondamentalmente, la pianificazione generale consente alle società di determinare ed equilibrare il fabbisogno futuro di materie prime e la capacità di soddisfare gli obiettivi aziendali. La pianificazione generale valuta quanto segue: 

-  Quali sono le materie prime e le capacità attualmente disponibili? 
-  Quali materie prime e capacità sono necessarie per completare la produzione? Ad esempio, cosa deve essere prodotto, acquistato, trasferito o accantonato come scorta di sicurezza per poter completare la produzione.

La pianificazione generale utilizza le informazioni per calcolare i requisiti e generare ordini pianificati.

I tre principali processi di progettazione sono:

-  **Pianificazione generale** - Il piano generale calcola i fabbisogni netti. Si basa sugli ordini correnti effettivi e consente alle società di controllare il rifornimento delle scorte a breve termine, su base quotidiana. Un altro termine per descriverlo è *Piano dei fabbisogni netti*. Per ulteriori informazioni, vedere [Pianificazione generale](master-plans.md). 

-  **Pianificazione previsionale** - La programmazione delle previsioni calcola i fabbisogni lordi. Si basa su proiezioni future (o previsioni) e consente alle società di condurre pianificazioni di materie prime e di capacità a lungo termine. Per ulteriori informazioni, vedere [Pianificazione previsionale](introduction-demand-forecasting.md). 

-  **Pianificazione generale interaziendale** - Il piano generale interaziendale calcola i fabbisogni netti tra le persone giuridiche. Collega la domanda e l'offerta tra società non solo per la domanda e l'offerta a breve termine e costanti ma anche per la domanda e l'offerta pianificate (non ancora consolidate) a lungo termine. Per ulteriori informazioni, vedere [Pianificazione generale interaziendale](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (richiede l'account CustomerSource). 

Le società possono modificare l'output del piano. Possono eseguire la modifica netta o rigenerativa o entrambi. I piani rigeneratori aggiornano tutti i fabbisogni, mentre, i piani di modifica netta aggiornano solo il piano degli articoli con nuovi requisiti che sono stati inseriti dopo l'esecuzione dell'ultima programmazione.

I piani di programmazione generale sono in genere a breve termine, quindi nell'ordine da una settimana a sei mesi. Il modulo di pianificazione generale determina le esigenze di fornitura (materiali) e di capacità (risorse) che risponderanno alla domanda corrente (fabbisogni netti). Nella maggior parte delle società questo viene esteso per includere il lead time cumulativo massimo tra i prodotti da ricevere.

## <a name="learning-map"></a>Mappa di apprendimento

Nella mappa di apprendimento seguente vengono visualizzati i concetti e le attività principali che costituiscono il framework del modulo Pianificazione generale. Fare clic sui collegamenti nella sezione [Collegamenti rapidi](#quick-links) per informazioni su come utilizzare il modulo.

[![Mappa di apprendimento per la pianificazione generale](./media/master-planning-learning-map.png)](./media/master-planning-learning-map.png)

## <a name="quick-links"></a>Collegamenti rapidi

|      |   |
|------|---|
|        [Piani generali](master-plans.md)       |     [Generare un piano con vincoli](./tasks/constrained-plan.md)  |
| [Creare un piano materiali per co-prodotti](./tasks/create-material-plan-co-products.md)   |  [Pianificazione generale e funzionalità multisito](master-plan-multisite-functionality.md)  |
| [Creare un piano interaziendale](./tasks/create-intercompany-plan.md) | [Cenni preliminari sulla previsione della domanda](introduction-demand-forecasting.md)  | 
|[Chiavi di riduzione](reduction-keys.md)| [Nozioni fondamentali sulla pianificazione generale](https://mbspartner.microsoft.com/AX/CourseOverview/1275) (eLearning) (richiede un account CustomerSource)     |
|  [Pianificazione generale per la Produzione processo](https://mbspartner.microsoft.com/D365E/CourseOverview/1514) (eLearning) (richiede un account CustomerSource) | [Pianificazione generale interaziendale](https://mbspartner.microsoft.com/AX/CourseOverview/1276) (eLearning) (richiede un account CustomerSource)|
                                  
## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="roadmaps"></a>Roadmap
Passare alla [roadmap di Microsoft Dynamics 365](https://roadmap.dynamics.com/) per un elenco delle nuove funzionalità rilasciate e di quelle che sono in via di sviluppo.

### <a name="blogs"></a>Blog
Opinioni, notizie e altre informazioni sulla Pianificazione generale e altre soluzioni sono disponibili nel [blog del team di ricerca e sviluppo per Dynamics AX - Produzione](https://blogs.msdn.microsoft.com/axmfg) e nel [blog del team di ricerca e sviluppo per Dynamics AX - Gestione della supply chain](https://blogs.msdn.microsoft.com/dynamicsaxscm).

### <a name="task-guides"></a>Guide attività
Informazioni aggiuntive sono disponibili come guide attività in Finance and Operations. Per accedere alle guide attività, fare clic sul pulsante **?** in qualsiasi pagina.

### <a name="webinars"></a>Webinar
[Utilizzare Azure Machine Learning per la previsione della domanda](https://www.youtube.com/watch?v=4nQsccdFFDA&feature=youtu.be)

### <a name="tech-conference-recordings"></a>Registrazioni di conferenze sulla tecnologia
-  [Estendere la funzionalità di previsione della domanda](https://www.youtube.com/watch?v=4OIKIXLiNjI&feature=youtu.be)
-  [Pianificazione generale - Suggerimenti e trucchi per risolvere problemi in modo efficiente](https://youtu.be/7v8BPmEs9Dg)
-  [MRP è lento](https://youtu.be/RLXybx20B5o)




