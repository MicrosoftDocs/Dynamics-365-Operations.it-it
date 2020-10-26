---
title: Creare dimensioni e importare i membri di dimensione
description: La contabilità industriale è un modulo indipendente che necessita dei dati master di altri moduli.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 256254
ms.assetid: e1b0a6e3-0c72-4a7d-90e1-20f870c6dbad
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: d61358be79adc943572bb4a5d624cb7c80b52e6e
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977673"
---
# <a name="create-dimensions-and-import-dimension-members"></a>Creare dimensioni e importare i membri di dimensione

[!include [banner](../includes/banner.md)]

La contabilità industriale è un modulo indipendente che necessita dei dati di altri moduli. Questi dati sono suddivisi nelle seguenti categorie:

-  Elementi di costo
-  Oggetti di costo
-  Dimensioni statistiche

Un **elemento di costo** corrisponde a un articolo pertinente per i costi nel piano dei conti. Un **oggetto di costo** corrisponde a qualsiasi tipo di dimensione finanziaria, ad esempio prodotti, centri di costo e progetti da stimare, a cui allocare i costi o da misurare direttamente. Una **dimensione statistica** e i relativi membri vengono utilizzati per registrare le voci non monetarie. I membri di dimensione statistica possono essere utilizzati come base di allocazione nella distribuzione e nell'allocazione dei costi. 

Nel seguente diagramma sono illustrate le dimensioni utilizzate nella contabilità industriale.

[![Dimensioni contabilità industriale](./media/cost-eos-dimensions.png)](./media/cost-eos-dimensions.png)

Dopo l'importazione dei dati nella contabilità industriale, è possibile utilizzarli per creare diverse prospettive che forniscono indicazioni utili ai responsabili a tutti i livelli dell'organizzazione. Negli argomenti riportati di seguito vengono fornite informazioni sulla creazione di dimensioni e sull'importazione dei membri di dimensione. 

-  [Dimensioni elemento di costo](cost-elements.md)
-  [Creare elementi di costo](./tasks/create-cost-elements.md)
-  [Dimensioni oggetto di costo](cost-objects.md)
-  [Eseguire il mapping dei membri di dimensione elemento di costo a un set comune di membri di dimensione](map-cost-elements-dimension-members.md)
-  [Mappare una dimensione elemento di costo](./tasks/map-cost-element-dimension.md)
-  [Membri di dimensione statistica e modelli provider misure statistiche](statistical-measure-provider-template.md)






