---
title: Siti e magazzini integrati
description: In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Dataverse.
author: t-benebo
manager: AnnBe
ms.date: 10/09/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-08-15
ms.openlocfilehash: b93e5f15e281c20f8688d496fc78f8b46b8aa996
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5560363"
---
# <a name="integrated-sites-and-warehouses"></a>Siti e magazzini integrati

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



In questo argomento viene descritta l'integrazione dei dati di siti e magazzini tra Finance and Operations e Dataverse. I siti e magazzini operativi sono concetti comuni in un'applicazione di Supply Chain Management. Questi vengono utilizzati per modellare la catena di approvvigionamento della società.

## <a name="templates"></a>Modelli

Grazie all'integrazione con Dataverse, tali concetti e tutte le informazioni correlate sono disponibili in Dataverse utilizzando le tabelle di dati di siti e magazzini nella tabella seguente.

App di Finance and Operations | Altre app Dynamics 365 | Descrizione
--------------------------|---------------------------|---
Siti | msdyn_operationalsites | 
Magazzini | msdyn_warehouses | 

[!include [symbols](../../includes/dual-write-symbols.md)]

[!include [operational sites](includes/InventOperationalSiteEntity-msdyn-operationalsite.md)]

[!include [warehouses](includes/InventWarehouseEntity-msdyn-warehouse.md)]



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]