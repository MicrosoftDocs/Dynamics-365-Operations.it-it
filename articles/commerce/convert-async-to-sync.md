---
title: Convertire i clienti asincroni in clienti sincroni
description: Questo articolo spiega come convertire i clienti asincroni in clienti sincroni in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 12/10/2021
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: 0ce4906816deab8824b1079a34489e55651c0e03
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884393"
---
# <a name="convert-asynchronous-customers-to-synchronous-customers"></a>Convertire i clienti asincroni in clienti sincroni

[!include [banner](includes/banner.md)]

Questo articolo spiega come convertire i clienti asincroni in clienti sincroni in Microsoft Dynamics 365 Commerce.

Per convertire i clienti asincroni in clienti sincroni segui questi passaggi.

1. In Commerce headquarters, esegui il **Processo P** per inviare i clienti asincroni a Commerce headquarters.
1. Esegui il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** per creare gli ID account cliente. (Questo processo era precedentemente chiamato **Sincronizza clienti e partner commerciali dalla modalità asincrona**.)
1. Esegui il processo **1010** per sincronizzare i nuovi ID account cliente con i canali.

Se un ordine fa riferimento a un cliente o indirizzo asincrono che non è stato ancora sincronizzato con Commerce headquarters, il cliente o l'indirizzo verranno sincronizzati come parte del processo batch **Sincronizzare ordini**. Se una transazione cash-and-carry fa riferimento a un cliente o indirizzo asincrono, il cliente o l'indirizzo verranno sincronizzati prima della registrazione di fine giornata (EOD).

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestione dei clienti nei punti vendita](customer-mgmt-stores.md)

[Modalità di creazione clienti asicroni](async-customer-mode.md)

[Attributi cliente](dev-itpro/customer-attributes.md)

[Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
