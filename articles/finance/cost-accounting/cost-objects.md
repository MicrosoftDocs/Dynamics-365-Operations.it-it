---
title: Dimensioni oggetto di costo
description: Quando si analizzano i costi, si usano le dimensioni elemento di costo per determinare la destinazione del flusso dei costi. Le dimensioni oggetto di costo sono utilizzate per determinare dove assegnare i costi. In questo argomento vengono fornite informazioni sulle dimensioni oggetto di costo.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 90d9176a2ca37b581ef82306cc1ceef515ceb624
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2187891"
---
# <a name="cost-object-dimensions"></a>Dimensioni oggetto di costo

[!include [banner](../includes/banner.md)]

Quando si analizzano i costi, si usano le dimensioni elemento di costo per determinare la destinazione del flusso dei costi. Le dimensioni oggetto di costo sono utilizzate per determinare dove assegnare i costi. In questo argomento vengono fornite informazioni sulle dimensioni oggetto di costo.

Un oggetto di costo può essere qualsiasi tipo di oggetto da stimare, a cui allocare i costi, o misurare direttamente. Gli oggetti di costo tipici includono prodotti, progetti, risorse, i reparti, i centri di costo e aree geografiche. La gestione utilizza gli oggetti di costo per quantificare i costi nonché per determinare l'analisi di redditività.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Dimensioni oggetto di costo e membri di dimensioni oggetto di costo
Gli oggetti di costo sono definiti come *dimensioni oggetto di costo*. Una volta deciso a quale entità la dimensione oggetto di costo deve fare riferimento, è necessario specificare i singoli valori di dimensione o importarli nella contabilità industriale da altri sistemi di origine. I singoli valori delle dimensioni vengono denominati *membri delle dimensioni oggetto di costo*. Ad esempio, si desidera utilizzare la dimensione finanziaria denominata Centro di costo come dimensione oggetto di costo. Per visualizzare come i costi fluiscono nei singoli centri di costo, è necessario importare i membri delle dimensioni oggetto di costo. In questo caso, i membri delle dimensioni oggetto di costo sono gli effettivi centri di costo, ad esempio Vendite, Produzione, Amministrazione e Località geografiche. Nella schermata seguente è illustrato un esempio di centri di costo come dimensione oggetto di costo con i relativi centri di costo effettivi come membri della dimensione oggetto di costo. 

[![cost-object-dimensions](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importare i membri delle dimensioni oggetto di costo tramite connettori dati
Per semplificare l'importazione di membri delle dimensioni oggetto di costo si utilizzano i connettori dati per recuperare i valori dalle entità che si desidera utilizzare come dimensioni oggetto di costo. È possibile utilizzare connettori dati predefiniti oppure crearne di propri personalizzati.



