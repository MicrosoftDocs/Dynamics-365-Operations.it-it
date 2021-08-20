---
title: Panoramica del ciclo di vita dell'ordine di produzione
description: Quando si crea un ordine di produzione, si esegue una richiesta di avvio della produzione di un articolo. Nell'ordine di produzione sono contenute informazioni sull'articolo che verrà prodotto, sulla quantità da produrre e sulla data di fine pianificata. Sono contenute anche informazioni sui materiali da utilizzare e sul processo da seguire per produrre l'articolo.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "19741"
- intro-internal
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6f0e3d15cbb522dd4a9322a8bac64e1a14e8432d3aff6722907a7f14fa3fefb2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6773227"
---
# <a name="production-order-lifecycle-overview"></a>Panoramica del ciclo di vita dell'ordine di produzione

[!include [banner](../includes/banner.md)]

Quando si crea un ordine di produzione, si esegue una richiesta di avvio della produzione di un articolo. Nell'ordine di produzione sono contenute informazioni sull'articolo che verrà prodotto, sulla quantità da produrre e sulla data di fine pianificata. Sono contenute anche informazioni sui materiali da utilizzare e sul processo da seguire per produrre l'articolo.

Un ordine di produzione attraversa le fasi del ciclo di vita della produzione. Al momento della creazione, a un ordine viene assegnato lo stato **Creato**. Al termine della creazione, a un ordine viene assegnato lo stato **Terminato**. L'impostazione dei parametri in ogni fase consente a un utente di configurare ogni fase. L'impostazione può essere impostata per un singolo utente o per tutti gli utenti.

La distinta base di produzione e il ciclo di lavorazione di produzione sono le entità principali dell'ordine di produzione. Vengono copiati nell'ordine di produzione in base all'articolo e alla quantità che saranno prodotti. Prima che venga avviato l'ordine di produzione, è possibile modificare la distinta base di produzione e il ciclo.

Un ordine di produzione può essere creato negli scenari seguenti:

-   Creato dall'esecuzione di pianificazione generale in base alla richiesta di materiale.
-   Creato direttamente da una riga ordine cliente o quando un ordine di produzione di livello superiore viene creato e stimato (offerta sottoposta a pegging).
-   Creato manualmente.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]