---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: 24ce08bb6cba9c74075151bafe0b07509fbdf73d
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "3998016"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Carte fedeltà dei clienti e punti premio

[!include [banner](../../includes/banner.md)]



Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti. Nella suite di applicazioni Microsoft Dynamics 365, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi. Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Common Data Service, le app basate su modello in Dynamics 365 possono utilizzare tali dati. Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.

## <a name="templates"></a>Modelli

| App di Finance and Operations | App basate su modello in Dynamics 365 | descrizione |
|-----------------------------|-----------------------------------|-------------|
| Carta fedeltà                | msdyn\_loyaltycards               | Questo modello sincronizza le informazioni delle carte fedeltà dei clienti. |
| Punti premio fedeltà       | msdyn\_loyaltyrewardpoints        | Questo modello sincronizza le informazioni dei punti premio dei clienti. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]
