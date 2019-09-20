---
title: Non è possibile creare un ambiente nell'interfaccia di amministrazione di PowerApps
description: In questo argomento viene descritto come procedere se l'amministratore non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft PowerApps.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 96119ca869cbbb15ed8d8d5d0fe3b0f94b5f36cc
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742844"
---
# <a name="cant-create-an-environment-in-the-powerapps-admin-center"></a>Non è possibile creare un ambiente nell'interfaccia di amministrazione di PowerApps

[!include [banner](includes/banner.md)]

**Uscita**

- L'amministratore di ambiente/tenant non è in grado di creare un ambiente nell'interfaccia di amministrazione di Microsoft PowerApps.
- Una licenza che concede agli utenti il diritto di eseguire l'operazione di creazione dell'ambiente non è stata assegnata direttamente all'utente che esegue quell'operazione.

**Soluzione**

Verificare che l'amministratore del tenant abbia assegnato una licenza PowerApps P2 valida direttamente all'utente che esegue l'operazione di creazione dell'ambiente. Di seguito sono riportati i piani del servizio Microsoft Dynamics che forniscono quel diritto.

| Unità di stockkeeping (SKU) globale di un prodotto       | Piano del servizio PowerApps P2  |
|------------------------------------------------|----------------------------|
| Microsoft Dynamics 365 for Operations          | PowerApps per Dynamics 365 |
| Microsoft Dynamics 365 Plan Enterprise Edition | PowerApps per Dynamics 365 |

Da notare che oltre alle unità di stockkeeping di PowerApps Piano 2, anche varie unità di stockkeeping di Microsoft Office forniscono quel diritto. L'aspetto importante è che una di queste unità di stockkeeping deve essere presente.

1. Accedere a [https://preview.admin.powerapps.com/environments](https://preview.admin.powerapps.com/environments).
2. Creare gli ambienti seguendo le istruzioni in [Eseguire il provisioning di Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).
