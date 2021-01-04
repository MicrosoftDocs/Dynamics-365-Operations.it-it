---
title: Panoramica della gestione delle modifiche di progettazione
description: Questo argomento fornisce una panoramica della gestione delle modifiche di progettazione, che consente di pianificare e gestire il controllo delle versioni del prodotto e gestire i cicli di vita del prodotto e le modifiche di progettazione.
author: t-benebo
manager: tfehr
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: f1aa04b472eaef7ed398f08a05d46bac2d589561
ms.sourcegitcommit: 9f32389715b226c11e74c53547527e0a8b51e300
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/12/2020
ms.locfileid: "4514352"
---
# <a name="engineering-change-management-overview"></a>Panoramica della gestione delle modifiche di progettazione

[!include [banner](../includes/banner.md)]

## <a name="feature-summary"></a>Riepilogo funzionalità

I produttori di oggi richiedono una potete gestione di dati del prodotto, controllo della versione e gestione delle modifiche di progettazione per avere successo in un mondo di cicli di vita dei prodotti in costante riduzione, requisiti di qualità e affidabilità aumentati e una maggiore attenzione alla sicurezza del prodotto.

La gestione delle modifiche di progettazione conferisce struttura e disciplina al processo di gestione dei dati di prodotto e consente di definire, rilasciare e rivedere i prodotti in modo controllato e supportato dai flussi di lavoro.Tramite le versioni del prodotto e la gestione delle modifiche di progettazione, è possibile documentare, valutare l'impatto e applicare le modifiche di progettazione durante l'intero ciclo di vita di un prodotto.

La gestione delle modifiche di progettazione consente di pianificare e gestire il controllo delle versioni del prodotto e gestire i cicli di vita del prodotto e le modifiche di progettazione. Ecco un elenco delle sue funzionalità principali:

- Controllo delle versioni del prodotto
- Funzionalità di rilascio del prodotto migliorata che consente di mantenere i dati anagrafici del prodotto in una persona giuridica (la società di progettazione) e pubblicare il prodotto rilasciato completamente configurato in altre persone giuridiche
- Regole per la convalida dell'inserimento delle informazioni richieste prima dell'attivazione di una versione del prodotto (controlli di disponibilità)
- Gestione migliorata del ciclo di vita del prodotto tramite un controllo dettagliato su quando un prodotto rilasciato può essere utilizzato in processi aziendali specifici
- Richieste di modifiche di progettazione supportate dai flussi di lavoro
- Ordini di modifiche di progettazione supportati dai flussi di lavoro

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4HE6B]

Il video precedente ([Cambia capacità di gestione in Dynamics 365 Supply Chain Management](https://youtu.be/N313FqvRuBc)) è incluso nella[playlist di Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="turn-on-engineering-change-management-for-your-system"></a>Attivare la gestione delle modifiche di progettazione per il sistema

Innanzitutto, attivare la gestione delle modifiche di progettazione seguendo questi passaggi.

1. Andare a [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Controllare gli aggiornamenti.
1. Attiva la funzionalità denominata **Gestione modifiche di progettazione**.

Quindi, attivare la chiave di configurazione **Gestione modifiche di progettazione** seguendo questi passaggi.

1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Espandere il nodo **Commercio** e selezionare la casella di controllo **Gestione modifiche di progettazione**.
1. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
