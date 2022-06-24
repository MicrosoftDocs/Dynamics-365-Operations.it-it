---
title: Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps
description: In questo articolo viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cc62d3c8fe560d4f7d2e754a79de6fec3ef6041b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882926"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Problema**

- L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
- L'utente non dispone di una licenza che dia il diritto di creare ambienti.

**Soluzione**

Assicurati che l'amministratore del tenant abbia assegnato una licenza Power Apps P2 per l'utente che crea l'ambiente. I seguenti piani di servizio Microsoft Dynamics forniscono le autorizzazioni per creare ambienti:

| Unità di stockkeeping (SKU) globale di un prodotto       | Piano di servizio Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps per Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps per Dynamics 365 |

Da notare che oltre alle unità di stockkeeping di Power Apps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto. L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.

1. Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Human Resources](/dynamics365/unified-operations/talent/provisioning-talent).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
