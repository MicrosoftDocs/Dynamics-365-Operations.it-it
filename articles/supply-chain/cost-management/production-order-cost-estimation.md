---
title: Stima dei costi degli ordini di produzione
description: In questo articolo vengono fornite informazioni sulla stima dei costi di produzione. Tale stima consente di ottenere i costi relativi al consumo di materiali e alla capacità previsti per la produzione della quantità di un articolo indicata nell'ordine di produzione pianificato.
author: JennySong-SH
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BOMCalcTrans, InventCostTrans, ProdCalcTrans, ProdTableJour, ProdTableListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 80633
ms.assetid: b4625d10-c852-4fda-b718-79df458de0d4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac658b49109a3fb3f987cf30bfa0b62bbff3d1c2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672264"
---
# <a name="production-order-cost-estimation"></a>Stima dei costi degli ordini di produzione

[!include [banner](../includes/banner.md)]

In questo articolo vengono fornite informazioni sulla stima dei costi di produzione. Tale stima consente di ottenere i costi relativi al consumo di materiali e alla capacità previsti per la produzione della quantità di un articolo indicata nell'ordine di produzione pianificato. 

Dopo avere creato un ordine di produzione, è necessario stimare i costi di produzione. Lo scopo è quello di stimare il consumo dell'articolo e del ciclo di lavorazione per il processo di produzione, in quanto queste stime rappresentano la base per i successivi processi di programmazione e produzione.

## <a name="production-cost-estimation"></a>Stima dei costi di produzione
Le stime dei costi di produzione si basano sulle seguenti informazioni:

-   Quantità nell'ordine di produzione
-   Componenti nelle distinte basi (DBA)
-   Operazioni dei percorsi di trasferimento nel ciclo di lavorazione produzione
-   Costi indiretti applicabili ai componenti e alle operazioni
-   Dati dei costi attivi alla data di calcolo

Se è presente una voce fittizia nella DBA di produzione, i calcoli riflettono i componenti e le operazioni dei cicli di lavorazione dell'articolo fittizio. L'attività di stima può essere utilizzata per ricalcolare i costi stimati in modo da riflettere le informazioni aggiornate. Le informazioni aggiornate possono essere ad esempio variazioni nella quantità dell'ordine di produzione, componenti della DBA di produzione, operazioni dei percorsi di trasferimento del ciclo di lavorazione produzione, costi indiretti applicabili a tali componenti e operazioni o dati di costi attivi al momento del ricalcolo. Con i calcoli dei costi stimati è inoltre possibile consigliare un prezzo di vendita per l'articolo di produzione sulla base di un approccio comprendente una percentuale di ricarico. I calcoli dei costi stimati possono facoltativamente applicarsi a ordini di riferimento che riflettono ordini di produzione collegati all'ordine di produzione.

## <a name="view-the-estimated-costs"></a>Visualizzare i costi stimati
Dopo aver eseguito una stima, è possibile visualizzare i risultati nella pagina **Calcolo dei prezzi**. Durante l'esecuzione della stima vengono calcolati i seguenti valori:

-   **Costo di produzione**: è la prima riga della stima. Indica il costo completo dell'esecuzione dell'ordine di produzione e il prezzo di vendita totale per la produzione. Corrisponde alla somma di tutte le righe dei costi nella stima.
-   **Costi di risorse o del ciclo di lavorazione**: i costi delle risorse o del ciclo di lavorazione sono i costi per le operazioni di produzione. È incluso il costo degli elementi, ad esempio tempo di attrezzaggio, tempo di esecuzione e i costi generali.
-   **Costi relativi ai materiali**: sono i costi e i prezzi dei componenti della distinta base (DBA) necessari per produrre l'articolo. Questi costi sono stati stabiliti e immessi nel sistema in precedenza.

## <a name="other-uses-of-cost-estimation"></a>Altri utilizzi di una stima dei costi
Una stima dei costi fornisce inoltre le informazioni seguenti:

-   Quotazioni significative dei prezzi
-   Stime della redditività dell'ordine
-   Stime dell'utilizzo delle materie prime
-   Confronti con informazioni sui costi relative a produzioni precedenti
-   Informazioni relative a budget e previsioni
-   Stime del volume di produzione necessario per mantenere un costo a un determinato livello






[!INCLUDE[footer-include](../../includes/footer-banner.md)]