---
title: Introduzione alle unità funzionali
description: Questo articolo fornisce una panoramica sulle unità funzionali in Gestione cespiti.
author: johanhoffmann
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationEditSubLocations, EntAssetFunctionalLocationLookup, EntAssetFunctionalLocationRename, EntAssetFunctionalLocation
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "2214"
- intro-internal
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a94b366dc725db3af01c156ae517a241213f7d52
ms.sourcegitcommit: cfe8fbc202c3eb05d894076fdf99e46704f17365
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9016045"
---
# <a name="introduction-to-functional-locations"></a>Introduzione alle unità funzionali

[!include [banner](../../includes/banner.md)]

 

Questo articolo fornisce una panoramica sulle unità funzionali in Gestione cespiti. Le unità funzionali sono elementi di una struttura tecnica, ad esempio unità funzionali in un sistema. Le unità funzionali vengono create in modo gerarchico e vi si installano cespiti. L'impostazione delle unità funzionali della società dipende dalle esigenze della società.

Di seguito sono riportati alcuni esempi di come utilizzare le unità funzionali:

- **Funzionale** - le unità funzionali possono essere orientate all'utente e usate per gestire i cespiti con comportamento simile.
- **Correlate a processo** - le unità funzionali possono essere orientate al flusso di lavoro.
- **Spaziale** - le unità funzionali possono rappresentare ubicazioni geografiche o sedi.

Ogni unità funzionale viene gestita in modo indipendente in Gestione cespiti. Di seguito vengono descritte alcune utili funzionalità delle unità funzionali:

- Impostare specifiche delle unità funzionali.
- Impostare requisiti di specifiche per i cespiti.
- Impostare sequenze di manutenzione per la manutenzione preventiva e reattiva.
- Gestire i cespiti installati.
- Tenere traccia di richieste e ordini di lavoro attivi correlati ai cespiti installati.
- Tenere traccia di problemi registrati nei cespiti.
- Tenere traccia dei costi della manutenzione dei cespiti correlati a una unità funzionale in qualsiasi dato momento.

Le unità funzionali forniscono la tracciabilità dei cespiti in relazione a richieste, ordini di lavoro, alle registrazioni di problemi, valutazione di condizioni, registrazioni di interruzioni di produzione e registrazioni di contatori dei cespiti.

> [!NOTE]
> Anche se un cespite viene installato in varie unità funzionali durante la sua vita, i costi possono essere correlati a ogni ubicazione. In altre parole, i costi dei cespiti sono sempre correlati all'unità funzionale in cui il cespite è installato in un dato momento.

Le unità funzionali **non** sono flessibili. Di conseguenza, dopo aver impostato una gerarchia di unità funzionali, non è possibile spostare le ubicazioni al suo interno. 

Dopo aver creato una gerarchia di unità funzionali, sarà necessario installarvi cespiti. Per ulteriori informazioni, vedere [Installare i cespiti nelle unità funzionali](../functional-locations/install-objects-on-functional-locations.md).

## <a name="all-functional-locations"></a>Tutte le unità funzionali

Seleziona **Gestione cespiti** \> **Unità funzionali** \> **Tutte le unità funzionali** per aprire la pagina elenco **Tutte le unità funzionali**. In questa pagina vengono visualizzate tutte le unità funzionali e alcune informazioni correlate a ciascuna. Per visualizzare solo le unità funzionali attive, selezionare **Unità funzionali attive**. Per visualizzare solo le unità funzionali a cui si è correlati come lavoratore, selezionare **Unità funzionali attive personali**. Questa relazione viene impostata nella pagina **Lavoratori**. Per ulteriori informazioni, vedere [Addetti alla manutenzione e gruppi di lavoratori](../setup-for-objects/workers-and-worker-groups.md).

Nella pagina elenco **Tutte le unità funzionali**, selezionare un collegamento nella colonna **Unità funzionale** per visualizzare i dettagli relativi al record selezionato. Per modificare l'unità funzionale, selezionare il pulsante **Modifica**. La visualizzazione dettagli mostra informazioni dettagliate correlate alla ubicazione. Include inoltre un riquadro **Informazioni correlate** a destra. In questo riquadro è illustrata la gerarchia dell'unità funzionale. È possibile espandere e comprimere il riquadro **Informazioni correlate**.

I pulsanti del riquadro azioni sono organizzati in schede. Nella tabella seguente vengono brevemente descritte i pulsanti correlati a Gestione cespiti.

| Nome del pulsante                         | Descrizione                                                                                                                                  |
|-------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------|
| Modifica                                | Consente di passare dalla modalità di modifica alla modalità di visualizzazione della pagina.                                                                                         |
| Nuove                                 | Crea una nuova unità funzionale.                                                                                                            |
| Eliminazione                              | Elimina l'unità funzionale selezionata                                                                                                     |
| Rinomina                              | Rinomina l'unità funzionale selezionata                                                                                                     |
| Copia la struttura di unità funzionali  | Consente di copiare la gerarchia dell'unità funzionale.                                                                                                      |
| Installa cespite                       | Installa un cespite, inclusi i cespiti figlio, nella unità funzionale.                                                                        |
| Sostituisci cespite                       | Sostituisce la gerarchia di cespiti con un'altra gerarchia di cespiti nella unità funzionale.                                                         |
| Controllo costi                        | Apre la pagina **Controllo costi unità funzionale**, in cui è possibile effettuare un calcolo dei costi per l'unità funzionale selezionata.                |
| Controllo ore                        | Apre la pagina **Controllo ore unità funzionale**, in cui è possibile effettuare un calcolo dei costi per l'unità funzionale selezionata.                |
| Risorse                              | Apre la pagina **Tutti i cespiti**, in cui è possibile visualizzare un elenco di cespiti correlati alla unità funzionale selezionata.                      |
| Richieste                            | Apre la pagina **Richieste attive**, in cui è possibile visualizzare un elenco di richieste correlati alla unità funzionale selezionata.               |
| Ordini di lavoro                         | Apre la pagina **Ordini di lavoro attivi**, in cui è possibile visualizzare un elenco di ordini di lavoro correlati alla unità funzionale selezionata.         |
| Errori                              | Apre la pagina **Errori del cespite**, in cui è possibile visualizzare un elenco di registrazioni di problemi dei cespiti correlati alla unità funzionale selezionata. |
| Aggiorna stato dell'unità funzionale    | Aggiorna la fase dell'unità funzionale selezionata                                                                                        |
| Registro dello stato del ciclo di vita                 | Consente di visualizzare un registro contenente le fasi dell'unità funzionale selezionata.                                                                        |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]