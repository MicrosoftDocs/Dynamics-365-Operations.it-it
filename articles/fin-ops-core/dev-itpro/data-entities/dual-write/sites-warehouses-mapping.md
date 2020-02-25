---
title: Siti e magazzini integrati
description: In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Common Data Service.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: 0f5ed58ad50df49250aa4c001401ff52d460dfa6
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019855"
---
# <a name="integrated-sites-and-warehouses"></a>Siti e magazzini integrati

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Common Data Service. I siti e magazzini operativi sono concetti comuni in un'applicazione di Supply Chain Management. Questi vengono utilizzati per modellare la catena di approvvigionamento della società.

## <a name="templates"></a>Modelli

Grazie all'integrazione con Common Data Service, tali concetti e tutte le informazioni correlate sono disponibili in Common Data Service utilizzando le entità di dati di siti e magazzini nella tabella seguente.

App di Finance and Operations | Altre app Dynamics 365 | Descrizione
--------------------------|---------------------------|---
Siti | msdyn_operationalsites | 
Magazzini | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]

