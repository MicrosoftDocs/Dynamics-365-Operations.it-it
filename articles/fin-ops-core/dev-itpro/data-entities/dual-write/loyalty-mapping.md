---
title: Carte fedeltà dei clienti e punti premio
description: Questo argomento descrive l'integrazione dei dati relativi alle carte fedeltà dei clienti e ai punti premio in doppia scrittura.
author: RamaKrishnamoorthy
ms.date: 03/10/2019
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-10
ms.openlocfilehash: d70fc6fea0e4e4e8f4ad73de5699b6b3fd481613
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542615"
---
# <a name="customer-loyalty-cards-and-reward-points"></a>Carte fedeltà e punti premio fedeltà dei clienti

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Le aziende classificano i clienti e forniscono servizi sofisticati, basati sui modelli di acquisto e di spesa dei clienti. Per esempio, Dynamics 365 Commerce dispone dell'infrastruttura e delle funzioni per facilitare e gestire le carte fedeltà dei clienti, i punti premio, i prezzi basati sulla fedeltà e le esperienze di acquisto basate sui premi. Quando i dati relativi alle carte fedeltà dei clienti e ai punti premio in Commerce vengono sincronizzati con Dataverse, le app Customer Engagement possono utilizzare tali dati. Ad esempio, gli utenti Dynamics 365 Customer Service possono utilizzare i dati per fornire gli stessi servizi sofisticati tramite l'help desk.

## <a name="templates"></a>Modelli

App Finance and Operations | App di interazione con i clienti     | descrizione
|-----------------------------|-----------------------------------|-------------|
[Carta fedeltà](mapping-reference.md#149) | msdyn_loyaltycards | Questo modello sincronizza le informazioni delle carte fedeltà dei clienti. |
[Livelli fedeltà](mapping-reference.md#226) | msdyn_loyaltylevels | Questo modello sincronizza le informazioni dei punti premio dei clienti. |
[Punti premio fedeltà](mapping-reference.md#150) | msdyn_loyaltyrewardpoints | |

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
