---
title: Creare una polizza di carico
description: In questo articolo viene descritto come creare una polizza di carico quando si utilizzano i processi di gestione del magazzino (WMS).
author: Weijiesa
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSBillOfLading, WHSLoadPlanningWorkbench, WHSBillOfLadingCarrier, WHSBillOfLadingOrder
audience: Application User
ms.reviewer: kamaybac
ms.custom: 193583
ms.assetid: 1ad0c1cb-4346-4042-a59b-923115fac03e
ms.search.region: Global
ms.author: weijiesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 68a703475191255ff6ceaee25ef8e2bdf33ba0c2
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069698"
---
# <a name="create-a-bill-of-lading"></a>Creare una polizza di carico

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come creare una polizza di carico quando si utilizzano i processi di gestione del magazzino (WMS).  

La polizza di carico costituisce un documento legale tra la società che spedisce articoli e il vettore. Il documento accompagna gli articoli spediti e serve come ricevuta di spedizione quando gli articoli vengono consegnati a destinazione. Se si utilizza la gestione magazzino, sono presenti due modi per generare una polizza di carico:

  -   Creare manualmente il report, utilizzando la pagina **Polizza di carico**.
  -   Generare il report da **Workbench pianificazione carico**.

Se si genera la polizza di carico da **Workbench pianificazione carico**, lo stato del carico deve essere **Spedito**. Se sono presenti più di una spedizione nel carico, una polizza di carico viene creata per ogni spedizione. Dopo che una polizza di carico è stata creata è possibile apportarvi modifiche nella pagina **Polizza di carico**.

## <a name="master-bill-of-lading"></a>Polizza di carico generale
Se nel carico è presente più di una spedizione, è possibile generare una polizza di carico generale che ha lo stesso layout e le stesse informazioni di una polizza di carico, ma è presente il contenuto di riepilogo per tutte le spedizioni. Se l'opzione **Creare una polizza di carico generale se è presente più di una spedizione in un carico** è impostata su **Sì** nella pagina **Parametri di gestione trasporto**, una polizza di carico generale viene generata automaticamente se si crea una polizza di carico in **Workbench pianificazione carico** ed è presente più di una spedizione. È inoltre possibile ottenere un elenco delle polizze di carico facendo clic su **Informazioni correlate** &gt; **Polizza di carico**. Se si creano manualmente le polizze di carico, è possibile creare una polizza di carico generale nella pagina **Polizza di carico**.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]