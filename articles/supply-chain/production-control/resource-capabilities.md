---
title: Capacità risorsa
description: Questo articolo fornisce informazioni sulle capacità delle risorse. Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. L'articolo illustra come le capacità e i concetti correlati, ad esempio il livello di competenza e priorità, vengono utilizzati per selezionare le risorse appropriate per un'attività.
author: sorenva
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrCapability, WrkCtrTable, WrkCtrCapRes, WrkCtrApplicableResources
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 29961
ms.assetid: 30e38233-2a64-4070-911f-8ffd78dd8281
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fc01e2d28758008d2e147a92c498da7ccb14b173
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431078"
---
# <a name="resource-capabilities"></a>Capacità risorsa

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle capacità delle risorse. Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. L'articolo illustra come le capacità e i concetti correlati, ad esempio il livello di competenza e priorità, vengono utilizzati per selezionare le risorse appropriate per un'attività.

Si definisce capacità l'idoneità di una risorsa operativa di eseguire un'attività specifica. È possibile assegnare più funzioni a una risorsa operativa e più risorse a una funzione. È inoltre possibile assegnare capacità a risorse in modo temporaneo, definendo una data di inizio e una di scadenza durante l'assegnazione delle capacità. Una volta che le capacità di una risorsa sono scadute, non è possibile pianificare la risorsa per un progetto o una produzione che richiede quelle capacità. È possibile rinnovare una capacità scaduta. È possibile eliminare capacità a condizione che non si trovino in una relazione ciclo di lavorazione o che non facciano parte di un ciclo di lavorazione produzione per un ordine di produzione attivo. In generale, effettuare le operazioni di eliminazione delle capacità con molta cautela. Si consiglia piuttosto di rettificare la data di scadenza delle risorse che possiedono la capacità. È possibile assegnare capacità a tutti i tipi di risorse: strumento, fornitore, computer, ubicazione, struttura o risorsa umana.

## <a name="level"></a>Livello
Più risorse spesso hanno la stessa capacità funzionale ma con livello di competenza differenti (ad esempio, forza, velocità di elaborazione o precisione). Di conseguenza, quando si assegna una capacità a una risorsa, è necessario specificare un valore per **Livello**. Il livello è un valore numerico semplice. Se si specifica che una capacità è un requisito di risorsa per un ciclo di lavorazione produzione, è possibile specificare un valore in **Livello minimo necessario** per la capacità. Il motore di programmazione quindi seleziona solo le risorse con la capacità richiesta a un livello uguale o superiore al livello minimo che è specificato nei requisiti delle risorse.

## <a name="priority"></a>Priorità
Alle risorse operative che hanno le stesse capacità è possibile assegnare una priorità. Se quindi più risorse hanno funzionalità che soddisfano i requisiti di programmazione al livello richiesto e hanno capacità disponibile, il motore di programmazione può selezionare tra queste risorse. Se è selezionata l'opzione **Priorità** nel campo **Selezione risorsa primaria** della pagina **Parametri di programmazione**, viene selezionata per prima la risorsa con la massima priorità (il valore numerico più basso nel campo **Priorità**) durante la programmazione.

## <a name="resource-requirements"></a>Requisiti risorsa
Quando si definiscono i requisiti risorsa per un ciclo di lavorazione produzione, è possibile specificare una o più capacità come requisiti. Durante la programmazione della produzione, le capacità definite nei requisiti risorsa per l'operazione del ciclo di lavorazione vengono associate alle capacità definite per le risorse. Vengono quindi selezionate le risorse le cui capacità soddisfano i requisiti. Se più risorse hanno la stessa capacità funzionale ma competenze differenti (ad esempio forza, velocità di elaborazione o precisione), è possibile definire più funzionalità o utilizzare il livello di capacità per qualificare la capacità della risorsa. Ecco un esempio:

-   In un ciclo di lavorazione, il tempo di elaborazione per le perforazioni è impostato su 10 unità per ora e il requisito è definito come "Perforazione".
-   Sono presenti due perforatrici, M1 e M2.
-   La capacità "Perforazione" è assegnata a entrambe le risorse: M1 e M2.
-   La macchina M1 è in grado di perforare due unità all'ora, mentre la macchina M2 può perforarne 11 in un'ora.

In questo esempio, entrambe le macchine possono essere selezionate dal motore di programmazione in quanto entrambe soddisfano il requisito di capacità di base, "Perforazione". Tuttavia, la macchina M1 può perforare solo due unità all'ora. Poiché il tasso è molto inferiore alle 10 unità all'ora specificate nel ciclo di lavorazione, la macchina M1 causerà problemi di produzione se viene selezionata. Sono disponibili due metodi per risolvere il problema e assicurarsi che venga selezionata la macchina M2:

-   Creare due capacità separate: perforazione lenta e perforazione rapida. Definire "Perforazione lenta" con un tempo di elaborazione di perforazione compreso tra una e nove unità all'ora. Definire la capacità "Perforazione rapida" con un tempo di elaborazione di perforazione compreso tra 10 e 19 unità all'ora. Assegnare quindi alla macchina M1 la funzionalità di perforazione lenta e assegnare alla macchina M2 la funzionalità di perforazione rapida. Infine, impostare il requisito di capacità della risorsa nel ciclo di lavorazione su perforazione rapida. Il motore di programmazione selezionerà quindi la macchina corretta (in questo caso M2).
-   Utilizzare il livello di capacità per qualificare la capacità di perforazione assegnata alle perforatrici. Specificare che la macchina M1 dispone della capacità di perforazione a un livello pari a 2.0 e che la macchina M2 dispone della capacità di perforazione a un livello pari a 11.0. Specificare quindi che 10.0 è il livello minimo necessario per il requisito di capacità di perforazione nel ciclo di lavorazione. Il motore di programmazione determinerà quindi che solo la macchina M2 soddisfa i requisiti di risorsa.

## <a name="competencies-for-human-resources"></a>Competenze per le risorse umane
Quando si dispone di risorse operative del tipo **Risorse umane** che sono collegate ai lavoratori in Risorse umane, è possibile usufruire anche delle competenze dei lavoratori quando si definiscono i requisiti delle risorse per un ciclo di lavorazione produzione. In altre parole, è possibile specificare i requisiti per specifiche competenze, corsi, certificati o titoli. Il motore di programmazione può quindi selezionare le risorse che sono collegate ai lavoratori e la selezione si basa sulle competenze dei lavoratori. Le competenze vengono impostate in Risorse umane, non nella pagina **Capacità risorsa**. Quando si definiscono competenze, corsi, certificati o titoli come requisiti di risorsa, è necessario utilizzare la funzionalità Risorse umane e collegare ogni risorsa di tipo **Risorse umane** a un lavoratore corrispondente. Se non si utilizza la funzionalità Risorse umane, è possibile definire delle capacità nella pagina **Capacità risorsa** che assomiglino o copino le competenze di Risorse umane. Tuttavia, la pagina **Capacità risorsa** non contiene la funzionalità richiesta per gestire le competenze, i corsi, le certificazioni o i titoli.



