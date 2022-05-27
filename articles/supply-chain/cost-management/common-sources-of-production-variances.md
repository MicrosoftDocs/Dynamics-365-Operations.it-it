---
title: Origini comuni degli scostamenti di produzione
description: Questo articolo illustra le varie origini normali di ciascun tipo di scostamento produzione.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostTrans, ProdCalcVarianceTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8b0f7a66c00540216887c7913e7f094c819b693a
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8674000"
---
# <a name="common-sources-of-production-variances"></a>Origini comuni degli scostamenti di produzione

[!include [banner](../includes/banner.md)]

Questo articolo illustra le varie origini normali di ciascun tipo di scostamento produzione. 

Di seguito sono alcune origini tipiche di uno scostamento di **dimensioni lotto**:

-   La quantità idonea per un ordine di produzione è diversa dalla quantità utilizzata nel calcolo dei costi standard. La quantità costituisce la base per l'ammortamento dei costi costanti.
-   Il valore dei costi costanti nell'ordine di produzione è diverso da quello dei costi costanti utilizzati nel calcolo dei costi standard. I costi costanti nell'ordine di produzione possono differire per diversi motivi. Ad esempio, i costi costanti potrebbero riflettere i fattori seguenti:
    -   Modifiche manuali apportate alla distinta base (DBA) di produzione o al ciclo di produzione
    -   La selezione di una diversa versione DBA o versione del ciclo di lavorazione durante la creazione dell'ordine di produzione
    -   Modifiche di progettazione pianificate apportate alla versione DBA o alla versione del ciclo di lavorazione assegnata all'articolo.

Di seguito sono alcune origini tipiche di uno scostamento di **prezzi di produzione**:

-   La categoria costi (e il prezzo della categoria costi) per il consumo dichiarato di un'operazione relativa ai cicli di lavorazione è diversa dalla categoria costi utilizzata nel calcolo dei costi standard.
-   Il costo attivo relativo al prezzo della categoria di costi è diverso dal prezzo della categoria di costi utilizzata nel calcolo di costo standard.

Di seguito sono alcune origini tipiche di uno scostamento di **quantità di produzione**:

-   Uscita eccessiva o insufficiente di un componente del materiale.
-   Dichiarazione ore eccessiva o insufficiente per una operazione relativa ai percorsi di trasferimento.
-   Ricezione eccessiva o insufficiente di quantità idonea dell'elemento padre, rispetto alla quantità ordine. Tuttavia, si verifica l'uscita completa di componenti e la dichiarazione completa di operazioni in base alla quantità dell'ordine di produzione.

Di seguito sono alcune origini tipiche di uno scostamento **sostitutivo di produzione**:

-   Uscita di un componente del materiale non presente nella DBA di produzione.
-   Aggiunta manuale di un componente alla DBA di produzione e dichiarazione dello stesso come consumato.
-   Dichiarare un articolo come consumato senza l'aggiunta manuale dello stesso alla DBA di produzione.
-   Aggiunta manuale di un'operazione al ciclo di lavorazione di produzione e dichiarazione della stessa come consumata.
-   Quando si crea l'ordine di produzione, si seleziona una versione DBA diversa dalla versione DBA utilizzata nel calcolo di costo standard.
-   Quando si crea l'ordine di produzione, si seleziona una versione del ciclo di lavorazione diversa dalla versione del ciclo di lavorazione utilizzata nel calcolo di costo standard.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]