---
title: Unità funzionali e cespiti
description: Questo articolo illustra unità funzionali e cespiti in Gestione cespiti. Gestione cespiti è un modulo avanzato per gestire i cespiti e processi di manutenzione in Dynamics 365 Supply Chain Management.
author: johanhoffmann
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d8d155b8bbf981408f6f15e914fc3bb1da25c9c
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111078"
---
# <a name="functional-locations-and-assets"></a>Unità funzionali e cespiti

[!include [banner](../../includes/banner.md)]

 

Questo articolo illustra unità funzionali e cespiti in Gestione cespiti. Gestione cespiti è un modulo avanzato per gestire i cespiti e processi di manutenzione in Dynamics 365 Supply Chain Management.

## <a name="overview"></a>Panoramica

Gestione cespiti è integrato con diversi moduli in altre app per la finanza e le operazioni. La figura di seguito mostra le interfacce con altri moduli.

![Diagramma che mostra come Gestione cespiti si interfaccia con altri moduli.](media/01-overview-image.png)

Gestione cespiti consente di gestire e eseguire in modo efficiente tutte le attività correlate alla gestione e alla manutenzione di molti tipi di attrezzature della società. Queste attrezzatture includono macchine, impianti di produzione e veicoli. Gestione cespiti supporta anche soluzioni per numerosi settori.

Nella seguente figura è illustrata una panoramica delle funzionalità principali di Gestione cespiti.

![Diagramma che mostra le funzionalità principali in Gestione cespiti.](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Unità funzionali e cespiti

Le unità funzionali vengono utilizzate per gestire i cespiti nelle ubicazioni. La gestione comprende la tracciabilità dei costi dei cespiti nelle unità funzionali. Le unità funzionali sono strutturate in modo gerarchico e le ubicazioni possono avere ubicazioni secondarie. La struttura delle unità funzionali è statica. Ovvero le ubicazioni non possono cambiare posto. I cespiti possono essere installati nelle unità funzionali e, secondo le esigenze, è possibile installarli più avanti in altre unità funzionali.

I costi dei cespiti seguono sempre l'ubicazione del cespite. Ovvero se si installa un cespite in una nuova unità funzionale, il cespite utilizza automaticamente le dimensioni finanziarie correlate alla nuova unità funzionale. Di conseguenza, i costi dei cespiti sono sempre correlati all'unità funzionale in cui il cespite è attualmente installato. Questa gestione automatica delle dimensioni finanziarie facilita la tracciabilità completa dei costi quando la società effettua il controllo dei progetti e il reporting sulle unità funzionali.

Il modo in cui sviluppare la gerarchia delle unità funzionali dipende dai requisiti della società per la manutenzione delle attrezzature interne o dei clienti. Nella figura seguente viene illustrato un esempio di unità funzionali basate sulle ubicazioni geografiche.

![Diagramma che mostra le unità funzionali in base alle ubicazioni geografiche.](media/03-overview-image.png)

Nella figura seguente viene illustrato un esempio di unità funzionali basate sui clienti.

![Diagramma che mostra le unità funzionali in base ai clienti.](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
