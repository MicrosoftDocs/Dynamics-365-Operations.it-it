---
title: Pianificare il piano dei conti
description: Questo articolo fornisce le informazioni che consentono di pianificare il piano dei conti per l&quot;organizzazione.
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: DimensionConfigureAccountStructure, LedgerChartOfAccounts
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14051
ms.assetid: 10edb129-33f0-4cf9-b2a7-4b7ffa09b229
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 34425ecd4b78a134c92a2282576d0d7967d870b3
ms.lasthandoff: 03/31/2017


---

# <a name="plan-your-chart-of-accounts"></a>Pianificare il piano dei conti

[!include[banner](../includes/banner.md)]


Questo articolo fornisce le informazioni che consentono di pianificare il piano dei conti per l'organizzazione.

Per tenere traccia e gestire le informazioni finanziarie in un'organizzazione, è possibile impostare un piano dei conti. Un piano dei conti è un insieme di conti che definiscono una struttura finanziaria. Per tenere ulteriormente traccia delle transazioni in tali conti, è possibile aggiungere segmenti, definiti dimensioni finanziarie. Ad esempio, un conto spese potrebbe includere dimensioni finanziarie denominate Reparto, Centro di costo e Scopo. Le regole definite dall'utente, definite strutture dei conti e regole avanzate, determinano le modalità di collegamento delle dimensioni finanziarie ai conti principali e ad altre dimensioni finanziarie, nonché quelle di immissione delle transazioni. 

Il piano dei conti consiste in un elenco strutturato dei conti CoGe di una persona giuridica. Questo elenco viene utilizzato per preparare i report finanziari destinati agli uffici competenti e ai proprietari. I conti vengono raggruppati in tipi di conti, quindi ulteriormente aggregati in categorie più ampie. A livello generale, i conti vengono raggruppati in costi e ricavi (conti di gestione) e in attività e passività (conti collettivi). 

Un piano dei conti può essere condiviso e utilizzato da qualsiasi persona giuridica in un'organizzazione. Il piano dei conti utilizzato da una persona giuridica è definito nella pagina **Contabilità generale**. 

Di seguito vengono indicati alcuni fattori da prendere in considerazione quando si pianifica la struttura del piano dei conti per l'organizzazione:

-   Gli adempimenti richiesti dal paese in cui ha sede l'organizzazione per quanto riguarda i report finanziari
-   Gli adempimenti richiesti dalla persona giuridica
-   Il grado di specifica richiesto, sia per le organizzazioni esterne che per la propria

Creare i piani dei conti nella pagina **Piano dei conti**. I conti principali possono essere creati dalla pagina **Piano dei conti** o **Conti principali**. Nei conti principali non è possibile utilizzare caratteri speciali come delimitatori del piano dei conti. Se si dispone di un carattere speciale uguale al delimitatore del piano dei conti, è possibile che il sistema diventi instabile o che sia necessario utilizzare sempre le ricerche o il riquadro a comparsa quando si immettono combinazioni di conto e dimensione. 

È consigliabile collegare i conti principali alle categorie dei conti principali, in modo da poter sfruttare i report finanziari predefiniti senza dover apportare eventuali modifiche. Di conseguenza, è possibile progettare e gestire i report in modo più rapido e facile. 

Utilizzare la pagina **Configura strutture dei conti** per creare strutture dei conti. Le strutture dei conti consentono di definire combinazioni valide. Le combinazioni, insieme ai conti principali, formano un piano dei conti. 

**Sostituzioni persona giuridica** 

Non tutti i conti principali sono validi per tutte le persone giuridiche e alcuni potrebbero essere pertinenti solo per un periodo di tempo specifico. In questo scenario la sezione Sostituzioni persona giuridica può essere utilizzata per identificare quali sono le società per cui è necessario sospendere il conto principale, l'identità del proprietario e il periodo di tempo durante il quale la dimensione è attiva. Le sostituzioni a livello condiviso non possono essere più restrittive di quelle a livello della persona giuridica.

Per ulteriori informazioni, vedere [Dimensioni finanzarie](financial-dimensions.md).




