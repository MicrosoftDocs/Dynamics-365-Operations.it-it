---
title: Panoramica dello sviluppo e della definizione dei contratti di assistenza
description: I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3b6c83f5ecd29bbd4202014992277c9ba1ae41ec
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996528"
---
# <a name="develop-and-establish-service-agreements-overview"></a>Panoramica dello sviluppo e della definizione dei contratti di assistenza

[!include [banner](../includes/banner.md)]

I contratti di assistenza consentono di definire sia le risorse utilizzate durante un intervento ordinario, sia la modalità di fatturazione di tali risorse a carico del cliente.

Ogni contratto di assistenza è associato a un progetto in base al quale viene eseguita la registrazione e la fatturazione delle transazioni. Tuttavia, è possibile fatturare le transazioni correlate all'ordine di assistenza anche direttamente tramite il progetto, senza associare necessariamente l'ordine di assistenza a un contratto. Questo approccio può rilevarsi utile se l'ordine di assistenza riguarda un intervento occasionale ed è preferibile elaborare rapidamente le transazioni anziché conservare nel tempo i dettagli del cliente contenuti nel contratto di assistenza.

## <a name="service-agreement"></a>Contratto di assistenza

Per ogni contratto di assistenza è necessario specificare un progetto, un ID e un gruppo di contratti di assistenza. Quest'ultimo potrà essere utilizzato per ordinare e organizzare i contratti di assistenza.

Nell'intestazione di un contratto di assistenza sono specificate le impostazioni applicate a tutte le righe del contratto associate:

-  Eventuale sospensione del contratto di assistenza. Se il contratto è sospeso, non potrà essere utilizzato per generare ordini di assistenza.
-  Durata del contratto di assistenza.
-  Modalità di combinazione delle righe in ordini di assistenza.
-  Eventuale configurazione del contratto di assistenza come modello.

Nell'intestazione del contratto di assistenza è inoltre possibile impostare tutte le attività di assistenza tecnica e tutti gli oggetti assistenza utilizzabili per il contratto immettendo le attività di assistenza tecnica o gli oggetti assistenza specifici da collegare alle varie righe del contratto.

È inoltre possibile utilizzare l'intestazione del contratto di assistenza per copiare le righe del contratto di assistenza o del modello di assistenza nel contratto corrente.

È possibile sospendere i contratti di assistenza e interrompere singole righe di un contratto di assistenza.

Se si seleziona la casella di controllo **Sospeso** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:

-    Creare ordini di assistenza automaticamente o manualmente dal contratto di assistenza.

Se si seleziona la casella di controllo **Interrotto** in una riga di un contratto di assistenza, non sarà possibile eseguire le seguenti operazioni:

-    Creare ordini di assistenza automaticamente o manualmente dalla riga del contratto di assistenza.
-    Copiare la riga del contratto di assistenza in un altro contratto o ordine di assistenza.


> [!NOTE]
> Se un contratto di assistenza viene sospeso, tutte le righe collegate verranno interrotte indipendentemente dal relativo stato.

## <a name="service-agreement-lines"></a>Righe del contratto di assistenza

In ogni riga del contratto di assistenza viene descritto dettagliatamente il contenuto dell'intervento di assistenza proposto. Le righe contengono le seguenti impostazioni:

-  Tipo di transazione e relativa descrizione.
-  Dipendente che esegue l'intervento di assistenza.
-  Oggetti su cui è necessario intervenire in base al contratto di assistenza.
-  Frequenza con la quale viene eseguito l'intervento e vengono registrati l'articolo associato, le spese e le transazioni di commissione.
-  Intervallo di tempo in base al quale è possibile raggruppare le righe in un ordine di assistenza.
-  Attività di assistenza tecnica utilizzate per raggruppare set di righe contratto in mansioni e per fornire a tecnici e clienti un riepilogo dell'attività di assistenza da eseguire.
-  Eventuale sospensione della riga. Non è possibile creare ordini di assistenza per una riga sospesa.
-  Impostazioni del progetto, ad esempio categoria e proprietà riga.

## <a name="related-topics"></a>Argomenti correlati

[Creare contratti di assistenza](create-service-agreements.md)
