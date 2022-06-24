---
title: Panoramica delle entità dei costi di spedizione
description: Questo articolo fornisce una panoramica delle entità di dati costi di spedizione che consentono alle origini dati esterne di creare viaggi e costi e di aggiornare i record di tracciabilità del contenitore.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 34721421d4bf0f052d1bce2cc822dcb2a408170f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8906010"
---
# <a name="landed-cost-entities-overview"></a>Panoramica delle entità dei costi di spedizione

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Il modulo **Costo di spedizione** consente alle aziende di semplificare le operazioni di spedizione in entrata fornendo un controllo finanziario e logistico completo sulle merci importate, dal produttore al magazzino. Lee entità di dati di transazione per i costi di spedizione consentono alle origini dati esterne (come i servizi di spedizioniere) di creare viaggi e costi e di aggiornare i record di tracciabilità del contenitore.

Di seguito sono riportate alcune operazioni supportate:

- Crea e aggiorna i record di viaggio, contenitori di spedizione e registrazioni per le righe ordine in entrata esistenti.
- Crea e aggiorna i costi stimati per ciascuna area di costo.
- Crea e aggiorna i record di attività del container di spedizione per acquisire la data di inizio, la data di fine stimata e la data di fine effettiva per ciascuna tratta del viaggio del container.
- Crea allocazioni delle fatture dei costi del fornitore.
