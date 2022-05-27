---
title: Aggiornare costi standard in un ambiente non di produzione
description: Questo articolo fornisce indicazioni per aggiornare i costi standard in un ambiente non di produzione.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79723
ms.assetid: 7ba0c408-2450-4042-9542-6fdf83c12e6c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 548955f544842ea5f60fd2d800c8c11cb459ee4c
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8679081"
---
# <a name="update-standard-costs-in-a-non-manufacturing-environment"></a>Aggiornare costi standard in un ambiente non di produzione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce indicazioni per aggiornare i costi standard in un ambiente non di produzione.

Nelle seguenti indicazioni si presuppone che venga utilizzato per l'aggiornamento dei costi standard un approccio basato su due versioni. Secondo questo approccio, una versione di determinazione costi contiene i costi standard inizialmente definiti per il periodo bloccato e la seconda versione di determinazione costi contiene gli aggiornamenti incrementali. Ogni aggiornamento viene immesso come record dei costi all'interno della seconda versione di determinazione costi e infine attivato. In alternativa, è possibile adottare un approccio basato su una sola versione, in cui si utilizza il set di costi standard definiti inizialmente. L'approccio basato su due versioni richiede la definizione di una seconda versione di determinazione costi. Di seguito sono riportate le indicazioni per la definizione di tale versione.

-   Assegnare un tipo di determinazione costi per **Costi standard**.
-   Assegnare un identificatore significativo che indichi il contenuto della versione di determinazione costi, ad esempio **AGGIORNAMENTI-2016**.
-   Assicurarsi che nel contenuto siano inclusi i record dei costi.
-   Consentire l'immissione dei record dei costi per tutti i siti. Se si specifica un sito, è possibile immettere i record dei costi solo per tale sito.
-   Impostare il principio di fallback su **Nessuno**. Tale principio si applica infatti solo al calcolo dei costi degli articoli prodotti.

Per correggere, rettificare o aggiornare i costi standard dei nuovi articoli, effettuare i passaggi riportati di seguito.

1.  Utilizzare la pagina **Impostazione versione di determinazione** **costi** per attivare i dati sui costi da inserire nella seconda versione di determinazione costi. Impedire eventualmente l'attivazione dei costi in sospeso, con la possibilità di consentire l'attivazione dopo che i costi in sospeso siano stati definiti in modo completo e accurato. È inoltre possibile immettere facoltativamente una data nel campo **Dal**. In generale, utilizzare la data in cui si intende attivare gli aggiornamenti incrementali. In alternativa, lasciare vuoto il campo **Dal** per la versione di determinazione costi, quindi immettere una data nel campo **Dal** per ciascun record costi.
2.  Utilizzare la pagina **Prezzo articolo** per immettere gli aggiornamenti come record costi articoli all'interno della seconda versione di determinazione costi.
3.  Utilizzare il report **Prezzi articoli** per verificare la completezza e l'accuratezza dei record costi articoli all'interno della seconda versione di determinazione costi.
4.  Utilizzare la pagina **Gestione versione di determinazione costi** per modificare il flag di blocco per consentire l'attivazione dei record costi in sospeso all'interno della seconda versione di determinazione costi.
5.  Utilizzare la pagina **Attiva prezzi** (accessibile dalla pagina **Gestione versione di determinazione costi**) per attivare tutti i record di costo articolo in sospeso all'interno della seconda versione di determinazione costi. È inoltre possibile attivare i record costi in sospeso per i singoli articoli facendo clic sul pulsante **Attiva prezzo in sospeso** nella pagina **Prezzo articolo**.
6.  Per evitare ulteriori operazioni di manutenzione dati, utilizzare la pagina **Impostazione versione di determinazione costi** per modificare i flag di blocco all'interno della seconda versione di determinazione costi. I criteri di blocco impediranno l'immissione di nuovi costi in sospeso e l'attivazione dei costi in sospeso.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]