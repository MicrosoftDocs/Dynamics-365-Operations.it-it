---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
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
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: d2c3845c1a7371d9e992495246e8dd0eb8631020
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747989"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Carte fedeltà e punti premio fedeltà dei clienti

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti. Per esempio, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi. Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Dataverse, le app Customer Engagement possono utilizzare tali dati. Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.

## <a name="templates"></a>Modelli

| App di Finance and Operations | App basate su modello in Dynamics 365 | Descrizione |
|-----------------------------|-----------------------------------|-------------|
| Carta fedeltà                | msdyn\_loyaltycards               | Questo modello sincronizza le informazioni delle carte fedeltà dei clienti. |
| Punti premio fedeltà       | msdyn\_loyaltyrewardpoints        | Questo modello sincronizza le informazioni dei punti premio dei clienti. |

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [mapping loyalty card](includes/LoyaltyCard-msdyn-loyaltycards.md)]

[!include [mapping reward points](includes/LoyaltyRewardPoints-msdyn-loyaltyrewardpoints.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]