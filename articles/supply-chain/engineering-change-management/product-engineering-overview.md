---
title: Panoramica della gestione delle modifiche di progettazione
description: Questo argomento fornisce una panoramica della gestione delle modifiche di progettazione, che consente di pianificare e gestire il controllo delle versioni del prodotto e gestire i cicli di vita del prodotto e le modifiche di progettazione.
author: t-benebo
ms.date: 11/11/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 70567489e5a1b84677ee63c296d15f5bdeb728ca
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6338609"
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

## <a name="turn-on-the-engineering-change-management-and-version-dimension-features-for-your-system"></a>Attivare le funzionalità Gestione delle modifiche di progettazione e Dimensione versione prodotti per il sistema

Per poter utilizzare la gestione delle modifiche di progettazione, è necessario abilitare la funzionalità *Gestione delle modifiche di progettazione* e la relativa chiave di configurazione. Se inoltre si desidera monitorare la dimensione della versione dei prodotti nelle transazioni (facoltativo), si deve abilitare anche la funzionalità *Dimensione versione prodotti* e la relativa chiave di configurazione.

Innanzi tutto, attivare le funzionalità procedendo come segue.

1. Andare all'area di lavoro [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).
1. Controllare gli aggiornamenti.
1. Attiva la funzionalità denominata *Gestione modifiche di progettazione*.
1. Per utilizzarla, attivare anche la funzionalità *Versione dimensione prodotto*.

Successivamente, attivare le chiavi di configurazione procedendo come segue.

1. Mettere il sistema in modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
1. Accedere a **Amministrazione sistema \> Imposta \> Configurazione licenza**.
1. Espandere il nodo **Commercio**
1. Abilitare la chiave di configurazione per la funzionalità principale selezionando la casella di controllo **Gestione delle modifiche di progettazione**.
1. Espandi il nodo **Gestione delle modifiche di progettazione** e seleziona o deseleziona le seguenti caselle di controllo come richiesto (a seconda delle funzionalità che si desidera utilizzare):

    - **Ricerca attributi**: seleziona questa casella di controllo per abilitare la [funzionalità di ricerca degli attributi](engineering-attributes-and-search.md). È consigliabile utilizzare questa funzionalità, ma puoi deselezionare questa casella di controllo se non la utilizzerai.
    - **Gestione delle modifiche per la produzione di processo**: seleziona questa casella di controllo se desideri utilizzare le funzionalità di gestione delle modifiche di progettazione per gestire le modifiche nelle formule per la produzione di processo. Se non devi gestire le formule, puoi deselezionare questa casella di controllo. Per altre informazioni, vedi [Gestisci le modifiche nelle formule e nei loro ingredienti](manage-formula-changes.md).

1. Per usare anche la dimensione versione, selezionare la casella di controllo **Dimensione prodotto - Versione**. (Questa casella di controllo è più in basso nell'elenco, non nidificata sotto il nodo **Gestione delle modifiche di progettazione**.)
1. Disattivare la modalità di manutenzione come descritto in [Modalità di manutenzione](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).

> [!IMPORTANT]
> A partire da aprile 2022, le chiavi di licenza per **Gestione delle modifiche di progettazione** e **Dimensione prodotto - Versione** saranno abilitate per impostazione predefinita per tutte le nuove installazioni, ma potrai comunque disabilitarle se necessario.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
