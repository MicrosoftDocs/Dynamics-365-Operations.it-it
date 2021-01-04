---
title: Società di progettazione e regole sulla proprietà dei dati
description: Questo argomento spiega come utilizzare una o più società di progettazione per garantire che i dati master per i prodotti siano creati e gestiti a livello centrale. Una società di progettazione rappresenta la società che possiede i prodotti di progettazione e i dati rilevanti corrispondenti.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgEngineeringOrganization
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 5cab02600e13a1a539b5ae0cd3ff66960430e826
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2020
ms.locfileid: "4431596"
---
# <a name="engineering-companies-and-data-ownership-rules"></a>Società di progettazione e regole sulla proprietà dei dati

[!include [banner](../includes/banner.md)]

## <a name="engineering-companies-and-operational-companies"></a>Società di progettazione e società operative

Per garantire che i dati master per i prodotti siano creati e gestiti a livello centrale, è possibile utilizzare una o più *società di progettazione*. Una società di progettazione possiede i prodotti di progettazione e i dati rilevanti corrispondenti. È sempre connessa a (in base a) una *persona giuridica* esistente, anch'essa un'azienda. Tramite questa connessione, il sistema stabilisce un punto di ingresso centrale per tutti i dati di progettazione rilevanti per i prodotti nella società di progettazione. In questo punto di ingresso centrale, vengono creati i prodotti di progettazione e vengono gestiti i dati di progettazione rilevanti. Da tale punto, i prodotti di progettazione e i dati di progettazione rilevanti verranno rilasciati a *società operative*, che sono altre persone giuridiche. Per ulteriori informazioni sulla gestione del rilascio, vedere [Strutture prodotto di rilascio](release-product-structure.md). Tali società operative utilizzeranno i dati di progettazione così come sono stati progettati dalla società di progettazione. Tutti i dati logistici vengono gestiti localmente da ciascuna società di progettazione e società operativa.

Per cerare una società di progettazione, andare a **Gestione modifiche di progettazione \> Imposta \> Organizzazioni di progettazione**. Selezionare **Nuovo**, immettere un nome per la società di progettazione e selezionare la società esistente (persona giuridica) su cui si basa.

Se si esegue l'integrazione con sistemi di gestione del ciclo di vita del prodotto esterni, è necessario creare una Business Unit (tipo di azienda) che diventerà una società esterna.

## <a name="engineering-product-categories-and-engineering-companies"></a>Categoria di prodotti di progettazione e società di progettazione

Le *Categorie di prodotti di progettazione* contribuiscono a garantire che i prodotti di progettazione vengano creati in base alle regole aziendali stabilite e si comportino come richiesto. Per ulteriori informazioni sulle categorie di prodotti di progettazione, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

Ogni categoria di prodotti di progettazione appartiene a una società di progettazione specifica e può creare solo prodotti che appartengono a tale società. Allo stesso modo, il diritto di gestire un prodotto di progettazione appartiene anche alla società associata alla categoria di prodotto di progettazione per il prodotto specifico.

## <a name="data-that-is-owned-by-the-engineering-company"></a>Dati di proprietà della società di progettazione

Poiché la società di progettazione possiede i dati rilevanti per la progettazione, controlla i seguenti processi:

- **Creazione di prodotti di progettazione:** ogni società di progettazione può creare solo nuovi prodotti di progettazione basati su una categoria di prodotti di progettazione di sua proprietà. In alcuni casi, le società operative gestiscono i propri dati locali correlati a tali prodotti.
- **Creazione di versioni di progettazione:** quando una società crea un nuovo prodotto di progettazione, il sistema crea automaticamente una versione di progettazione iniziale per il prodotto stesso. Solo la società di progettazione proprietaria sarà in grado di creare nuove versioni di tale prodotto.
- **Creazione e gestione di attributi di progettazione:** quando una società crea un nuovo prodotto di progettazione, il sistema aggiunge automaticamente attributi di progettazione al prodotto stesso. Solo la società di progettazione proprietaria sarà in grado di creare e gestire i valori per tali attributi. Per ulteriori informazioni sugli attributi di progettazione, vedere [Attributi di progettazione e ricerca di attributi di progettazione](engineering-attributes-and-search.md).
- **Creazione e gestione di distinte base (DBA) collegate alle versioni di progettazione:** la società di progettazione proprietaria può collegare direttamente una distinta base a una versione del prodotto di progettazione. Quando queste distinte base vengono rilasciate ad altre persone giuridiche, le modifiche ai dati di progettazione sulle distinte base sono limitate nei seguenti modi:

    - La società operativa non può rimuovere le righe DBA rilasciate.
    - I campi di progettazione nelle righe DBA sono di sola lettura per la società operativa. Tutti gli altri campi sono campi di implementazione logistica e possono essere modificati dalla società operativa.
    - La società operativa può aggiungere righe DBA alla stessa DBA. In questo modo, può inserire aggiunte locali, come materiali di imballaggio o fluidi lubrificanti.
    - La società operativa può aggiungere una distinta base locale completamente nuova. Questa modifica potrebbe essere necessaria nei casi in cui, ad esempio, non viene fornita alcuna distinta base durante il rilascio. La società operativa possiede e gestisce queste DBA locali. Per ulteriori informazioni sulla gestione dei rilasci, vedere [Strutture prodotto di rilascio](release-product-structure.md).
    - Tutte le DBA e le righe DBA locali vengono mantenute quando la società di progettazione aggiorna la propria DBA.

- **Creazione e gestione di cicli di lavorazione collegate alle versioni di progettazione:** la società di progettazione proprietaria può collegare direttamente un ciclo di lavorazione a ciascuna versione di progettazione. Quando questi cicli di lavorazione vengono rilasciati ad altre persone giuridiche, le modifiche ai dati sui cicli di lavorazione sono limitati nei seguenti modi:

    - Le altre persone giuridiche non possono rimuovere i dati di progettazione sui cicli di lavorazione.
    - Le altre persone giuridiche possono aggiungere operazioni al ciclo di lavorazione. In questo modo, possono aggiungere passaggi del ciclo di lavorazione locale.
    - Le società operative possono aggiungere cicli di lavorazione locali completamente nuovi. Questa modifica potrebbe essere necessaria, ad esempio, se non sono stati inclusi rilasci durante il rilascio. Le società operative possiedono e gestiscono tali cicli di lavorazione locali. Per ulteriori informazioni sulla gestione dei rilasci, vedere [Strutture prodotto di rilascio](release-product-structure.md).
    - Tutte le modifiche apportate a livello locale vengono mantenute quando gli aggiornamenti dalla società di progettazione vengono nuovamente rilasciati sui cicli di lavorazione.

- **Creazione e manutenzione di documenti di progettazione:** la società di progettazione può allegare documenti di progettazione a ciascuna versione di progettazione.

    - Quando vengono rilasciati ad altre persone giuridiche, i documenti sono protetti dalla rimozione dalla società operativa.
    - Altre persone giuridiche possono aggiungere documenti locali completamente nuovi. La società operativa possiede e gestisce questi documenti locali.
