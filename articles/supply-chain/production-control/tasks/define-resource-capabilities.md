---
title: Definire le capacità delle risorse
description: Capacità risorsa descrive le operazioni che possono effettuare le risorse operative.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrCapability
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 42451da0bd465ce3a18ecf18570f3331847474c1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579114"
---
# <a name="define-resource-capabilities"></a>Definire le capacità delle risorse

[!include [banner](../../includes/banner.md)]

Capacità risorsa descrive le operazioni che possono effettuare le risorse operative. Durante la programmazione, i requisiti di ogni processo e operazione vengono associati alle capacità delle risorse disponibili. Questa guida attività consentirà di creare una capacità risorsa e di assegnarla a una risorsa. La società di dati dimostrativi utilizzata per creare questa attività è USMF.


## <a name="create-a-resource-capability"></a>Consente di creare una capacità risorsa
1. Fare clic su Capacità risorsa.
2. Fare clic su Nuovo.
3. Nel campo Capacità, digitare l'ID della capacità della risorsa.
    * Per un'operazione specifica, utilizzare l'ID della capacità per specificare le risorse devono avere tale capacità per eseguire l'operazione.  
4. Nel campo Descrizione immettere una descrizione della capacità.

## <a name="assign-capability-to-a-resource"></a>Assegna la capacità a una risorsa
1. Scegliere Aggiungi.
2. Nel campo Risorsa, digitare l'ID della risorsa.
    * Una capacità della risorsa può essere assegnata a una o più risorse.  
3. Nel campo Scadenza immettere una data.
    * È possibile utilizzare questo campo per specificare che una risorsa dispone di tale capacità solo per un tempo limitato.  
4. Nel campo Priorità immettere un numero.
    * Quando si programmano i processi e le operazioni, è possibile specificare se selezionare le risorse in base alla priorità. In questo caso e se più risorse possono eseguire il processo o l'operazione entro la data richiesta, viene selezionata la risorsa con la priorità più bassa rispetto alla capacità richiesta.  
5. Nel campo Livello immettere un numero.
    * Se si specifica che un processo o un'operazione richiede una capacità specifica, è possibile specificare il livello minimo necessario. Utilizzare il livello di capacità per distinguere le risorse che possono eseguire lo stesso processo, ma con diverse velocità, forze, dimensioni e così via.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]