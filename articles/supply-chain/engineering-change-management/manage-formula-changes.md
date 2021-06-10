---
title: Gestisci le modifiche nelle formule e nei loro ingredienti
description: Questo argomento descrive come eseguire la gestione delle formule e gestire le modifiche per elaborare i dati anagrafici di produzione.
author: t-benebo
ms.date: 05/19/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2021-05-19
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 825cc5b9355695a648c857e5197b5b93a21fdb43
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115197"
---
# <a name="manage-changes-in-formulas-and-their-ingredients"></a>Gestisci le modifiche nelle formule e nei loro ingredienti

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

Se stai utilizzando le funzionalità di produzione dei processi di Microsoft Dynamics 365 Supply Chain Management, puoi anche utilizzare le relative funzionalità di gestione delle formule per gestire le seguenti modifiche:

- **Formula ed elementi di pianificazione:** gestisci le modifiche agli ingredienti nelle formule e ai loro co-prodotti e sottoprodotti.
- **Co-prodotti e sottoprodotti:** modifica le quantità e altre informazioni dei co-prodotti e dei sottoprodotti in una formula.
- **Articoli a peso variabile:** gestisci le modifiche agli articoli a peso variabile.

## <a name="turn-on-this-feature-in-your-system"></a>Attivare la funzionalità nel tuo sistema

Per utilizzare questa funzionalità, è necessario completare le seguenti attività:

1. Abilita la funzionalità *Gestione delle modifiche di progettazione* e la relativa chiave di configurazione come descritto in [Panoramica di Gestione delle modifiche di progettazione](product-engineering-overview.md). Come accennato in quell'argomento, assicurati di abilitare anche la chiave di licenza **Gestione delle modifiche per la produzione di processo**, che è nidificata sotto la chiave di licenza **Gestione modifiche di progettazione** principale.
1. Attiva la funzionalità *Gestisci le modifiche alle formule e ai loro ingredienti* in [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="feature-naming-conventions"></a>Convenzioni di denominazione delle funzioni

Nell'interfaccia utente (UI) e nella documentazione di Supply Chain Management, la funzionalità di gestione delle modifiche viene in genere denominata *gestione delle modifiche di progettazione* e i prodotti gestibili sono generalmente indicati come *prodotti di progettazione*. Sebbene questa terminologia non sia solitamente associata alla gestione delle formule per la produzione di processo, è consigliabile pensare alla gestione delle modifiche di progettazione come una semplice gestione delle modifiche e ai prodotti di progettazione come prodotti con versione.

## <a name="work-with-formula-change-management-features"></a>Utilizzare le funzionalità di gestione delle modifiche alle formule

Il seguente elenco riepiloga il modo in cui le funzionalità di gestione delle modifiche tecniche si applicano alla gestione delle formule. Fornisce inoltre collegamenti ad altre informazioni. Poiché la gestione delle modifiche alle formule si avvale delle funzionalità di gestione delle modifiche di progettazione, è consigliabile imparare come funziona la gestione delle modifiche di progettazione in generale, in modo da poterla utilizzare per gestire le tue formule e i loro ingredienti.

- **Gestione centralizzata dei dati di prodotto** configura un'organizzazione che, attraverso un processo di rilascio gestito, assicuri che dati di prodotto accurati e pertinenti siano disponibili per gli utenti in tutta l'azienda. Per ulteriori informazioni, vedere [Società di progettazione e regole sulla proprietà dei dati](engineering-org-data-ownership-rules.md).
- **Controllo delle versioni del prodotto**: tieni traccia delle modifiche ai prodotti attraverso le versioni del prodotto e controlla il prodotto in tutte le fasi della catena di approvvigionamento. In questo modo, puoi tener traccia delle modifiche nelle tue formulazioni. Per ulteriori informazioni, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).
- **Gestione del ciclo di vita del prodotto**: gestisci la visibilità dei dati di prodotto in tutta l'organizzazione e controlla la disponibilità delle versioni del prodotto in ogni fase della catena di fornitura. Hai il controllo dettagliato su quando una versione del prodotto può essere utilizzata in processi aziendali specifici e puoi creare i tuoi stati del ciclo di vita per soddisfare le tue esigenze aziendali. Per ulteriori informazioni, vedere [Stati e transazioni del ciclo di vita del prodotto](product-lifecycle-state-transactions.md).
- **Gestione delle modifiche alla formula**: gli utenti di tutta l'organizzazione possono richiedere modifiche alle formule. Utilizza gli ordini di modifica per valutare e documentare l'impatto delle modifiche proposte. Aggiungi flussi di lavoro per gestire il processo di modifica e il rilascio di nuove versioni del prodotto e della sua formula. Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).
- **Controllo della disponibilità**: utilizza i controlli di sistema e la guida dell'utente (questionari e liste di controllo) per garantire che tutti i dati di prodotto richiesti siano stati inseriti completamente prima che il prodotto venga rilasciato. Per ulteriori informazioni, vedere [Preparazione del prodotto](product-readiness.md).
- **Funzionalità di rilascio del prodotto migliorate**: rilascia le versioni completamente definite di un prodotto e la sua formula da un'organizzazione (persona giuridica) ad altre persone giuridiche. Puoi persino decidere se le informazioni sul prodotto devono essere riviste o modificate prima del rilascio. Per ulteriori informazioni, vedere [Strutture di rilascio prodotti](release-product-structure.md).

Si noti che la maggior parte degli argomenti a cui sono collegati nell'elenco precedente forniscono esempi basati su distinte base (BOM). Tuttavia, le formule funzionano in modo simile. Di seguito sono riportati alcuni concetti aggiuntivi utili da conoscere quando si utilizza la gestione delle modifiche (o solo la gestione delle modifiche delle formule) per gestire formule e distinte materiali:

- Per ogni [categoria di progettazione del prodotto](engineering-versions-product-category.md), è possibile specificare il tipo di produzione (DBA, formula o articolo di pianificazione). Puoi inoltre specificare se il supporto del peso variabile è richiesto per i prodotti che utilizzano quella categoria.
- Co-prodotti e sottoprodotti non sono prodotti di progettazione. Pertanto, non ne viene eseguito il controllo delle versioni. Se devi modificarli, crea semplicemente un nuovo prodotto. Questo approccio semplifica la manutenzione.
- Puoi gestire i prodotti finiti che sono distinte materiali e che hanno elementi formula figlio. La funzionalità avrà effetto su qualsiasi combinazione di distinte materiali che contengono formule e/o formule che contengono distinte materiali.
