---
title: Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps
description: In questo articolo viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f4c75706183a3d6c961852395e464d46ba3ec1f2
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "3009510"
---
# <a name="cant-create-an-environment-in-the-power-apps-admin-center"></a>Impossibile creare un ambiente nell'interfaccia di amministrazione di Power Apps

**Problema**

- L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft Power Apps.
- Una licenza che concede agli utenti il diritto di eseguire l'operazione di creazione dell'ambiente non è stata assegnata direttamente all'utente che esegue quell'operazione.

**Soluzione**

Verificare che l'amministratore del tenant abbia assegnato una licenza Power Apps P2 valida direttamente all'utente che esegue l'operazione di creazione dell'ambiente. Di seguito sono riportati i piani del servizio Microsoft Dynamics che forniscono quel diritto.

| Unità di stockkeeping (SKU) globale di un prodotto       | Piano di servizio Power Apps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | Power Apps per Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | Power Apps per Dynamics 365 |

Da notare che oltre alle unità di stockkeeping di Power Apps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto. L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.

1. Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Human Resources](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
