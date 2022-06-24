---
title: Creazione di ordini fornitore e ordini cliente interaziendali in più società
description: In questo articolo viene illustrato come creare ordini fornitore o ordini cliente interaziendali in più società
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 6dce419126d60199bc11d4bd3209185ad779e979
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873552"
---
# <a name="creating-intercompany-purchase-and-sales-orders-in-several-companies"></a>Creazione di ordini fornitore e ordini cliente interaziendali in più società

[!include [banner](../../includes/banner.md)]

L'utilizzo di Microsoft Dynamics 365 Supply Chain Management non è limitato solo alla gestione di una società di produzione e più società di vendita. Tutte le società impostate nell'ambito di un'organizzazione interaziendale possono infatti essere sia società commerciali sia società di produzione.

Se più società possono consegnare lo stesso articolo, è possibile scegliere liberamente da chi acquistare e gli aggiornamenti vengono elaborati anche se un solo ordine cliente viene trasformato in più ordini fornitore.

Nello stesso modo in cui viene creato automaticamente un ordine fornitore interaziendale, è possibile creare un ordine cliente originario nella società e quindi fare in modo che più fornitori interaziendali completino l'ordine mediante la creazione di più ordini fornitore interaziendale. Gli ordini cliente interaziendali verranno creati automaticamente da Microsoft Dynamics 365 Supply Chain Management nelle società fornitore.

A tale scopo, tutte le società devono essere impostate come relazioni commerciali. Le società fornitore devono essere impostate in Microsoft Dynamics 365 Supply Chain Management come fornitori interaziendali ed essere il fornitore principale per l'articolo rilevante. Sull'ordine cliente, in **Vista intestazione**, è necessario selezionare il campo **Crea ordini interaziendali automaticamente** e il campo **Consegna diretta** sulla Scheda dettaglio **Impostazioni interaziendali**. Si tratta dell'impostazione predefinita.

Creare le righe di vendita seguendo la procedura abituale. Quando si esce dal record, viene visualizzato un messaggio nel quale è indicato che sono stati creati ordini fornitore interaziendali e ordini cliente interaziendali. Nel messaggio sono inoltre presenti i collegamenti ai nuovi ordini. Per visualizzare gli ordini cliente interaziendali creati nelle società fornitore, aprire l'ordine cliente originario e nel gruppo **Informazioni correlate** della scheda **Generale** selezionare **Riferimenti**.

Se si aprono gli ordini fornitore interaziendali per i fornitori, si noterà che in Microsoft Dynamics 365 Supply Chain Management vengono inseriti automaticamente il numero dell'ordine cliente originario e il numero dell'ordine cliente interaziendali per ciascun fornitore.

Analogamente, se si aprono gli ordini cliente interaziendali per i fornitori, si noterà che in Microsoft Dynamics 365 Supply Chain Management vengono inseriti automaticamente il numero dell'ordine cliente originario e il numero dell'ordine fornitore interaziendali per ciascun fornitore.

> [!NOTE]
> Se gli articoli in ordinazione sono disponibili in una delle società fornitore interaziendali ma non nell'altra, verranno creati automaticamente in Microsoft Dynamics 365 Supply Chain Management gli ordini interaziendali per la società fornitore in cui sono disponibili gli articoli, bloccando la creazione dell'ordine per l'altra società. In questi casi viene visualizzato un messaggio di notifica.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
