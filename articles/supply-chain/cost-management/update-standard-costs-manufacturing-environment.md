---
title: Aggiornare costi standard in un ambiente di produzione
description: Questo articolo fornisce indicazioni su come aggiornare i costi standard in un ambiente di produzione.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8acbcb79fa45ea2f225775068e0d061a44cba1f7
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8675237"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a>Aggiornare costi standard in un ambiente di produzione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce indicazioni su come aggiornare i costi standard in un ambiente di produzione. 

Gli aggiornamenti possono riflettere nuovi articoli, categorie di costi o formule di calcolo dei costi indiretti. Possono anche riflettere le correzioni e le variazioni di costo. Le operazioni da completare per l'aggiornamento dei costi standard dipendono dal tipo di aggiornamento, come illustrato nei casi descritti di seguito;

-   Immettere le variazioni dei costi standard previste per gli articoli acquistati, quindi cambiare lo stato dei record dei costi degli articoli in **Attivo** alla data appropriata. Non ricalcolare tuttavia i costi degli articoli prodotti in cui vengono utilizzati gli articoli acquistati.
-   Immettere i costi standard per un nuovo articolo acquistato, ma non ricalcolare i costi degli articoli prodotti con una versione distinta base (DBA) contenente come componente il nuovo articolo acquistato.
-   Correggere o modificare il costo di un articolo acquistato oppure cambiare il gruppo di costi assegnato a un articolo acquistato, quindi calcolare il costo di tutti gli articoli prodotti che hanno una versione DBA contenente come componente l'articolo acquistato.
-   Cambiare il costo per una categoria di costi e calcolare il costo di tutti gli articoli prodotti che hanno una versione del ciclo di lavorazione contenente operazioni del ciclo di lavorazione in cui viene utilizzata la categoria di costi.
-   Modificare le categorie di costi assegnate alle operazioni del ciclo di lavorazione o il gruppo di costi assegnato alle categorie di costi. Calcolare quindi il costo di tutti gli articoli prodotti che hanno una versione del ciclo di lavorazione contenente operazioni del ciclo di lavorazione in cui viene utilizzata la categoria di costi.
-   Modificare la formula di calcolo di un costo indiretto, quindi calcolare il costo di tutti gli articoli prodotti interessati dalla modifica.
-   Modificare o aggiungere un sito di fabbricazione per un articolo prodotto, quindi calcolare il costo di produzione dell'articolo per tale sito.
-   Calcolare o ricalcolare il costo di un articolo prodotto, quindi ricalcolare il costo di tutti gli articoli prodotti che hanno una versione DBA contenente come componente l'articolo prodotto.
-   Calcolare i costi di un nuovo articolo prodotto in base alle informazioni sui cicli di lavorazione e sulla DBA definita, approvata e attiva.

In ciascun caso è necessario valutare con attenzione come aggiornare i costi standard.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]