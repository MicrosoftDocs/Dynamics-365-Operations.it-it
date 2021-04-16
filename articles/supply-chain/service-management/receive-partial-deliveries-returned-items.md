---
title: Ricevere consegne parziali relative a resi
description: Le consegne parziali vengono definite in termini di righe, non in termini di spedizioni dell'ordine di reso.
author: ShylaThompson
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 51213f8f46638b0cce10251e761d7f276c39d924
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5836136"
---
# <a name="receive-partial-deliveries-of-returned-items"></a>Ricevere consegne parziali relative a resi    

[!include [banner](../includes/banner.md)]


Le consegne parziali vengono definite in termini di righe, non in termini di spedizioni dell'ordine di reso.

Ciò significa che, se si riceve l'intera quantità indicata in una singola riga dell'ordine di reso ma non si riceve niente di quanto specificato nelle altre righe dell'ordine, la consegna non è da considerarsi parziale. Se tuttavia una riga dell'ordine di reso fa riferimento ad esempio a dieci unità di un determinato articolo da restituire, ma si ricevono solo quattro unità, la consegna è parziale.

Se una spedizione di reso contiene una quantità inferiore all'intera quantità di una riga dell'ordine di reso, è possibile accantonare la spedizione e attendere l'arrivo della quantità rimanente oppure registrare e contabilizzare la quantità parziale.

## <a name="register-and-post-a-partial-quantity"></a>Registrare e contabilizzare una quantità parziale

1.  Dopo avere selezionato un ordine di reso per l'arrivo nel modulo **Panoramica arrivi - Magazzino: %1, Banchina: %2, Nome giornale di registrazione: %3**, fare clic su **Inizia arrivo** per creare il giornale di registrazione arrivi e fare clic su **Giornali di registrazione** \> **Mostra arrivi da ricevimenti** per aprire il modulo **Giornale di registrazione ubicazioni**.

2.  Selezionare la riga del giornale di registrazione che si desidera utilizzare, quindi fare clic su **Righe** per aprire il modulo **Righe giornale di registrazione, ubicazioni**.

3.  Selezionare la riga relativa al numero di articolo per il quale è arrivata solo una quantità parziale, quindi fare clic su **Funzioni** \> **Dividi** per aprire il modulo **Dividi**.

4.  Nel campo **Dividi quantità** digitare la quantità relativa al numero totale di articoli ricevuti, quindi scegliere **OK**.

5.  Nel modulo **Righe giornale di registrazione, ubicazioni** selezionare la riga relativa alla quantità di articoli arrivata, quindi fare clic su **Registra**. La riga relativa alla quantità aggiuntiva potrà essere registrata dopo l'arrivo degli articoli.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]