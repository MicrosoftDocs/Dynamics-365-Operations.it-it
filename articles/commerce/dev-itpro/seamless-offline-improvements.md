---
title: Passare offline con semplicità per le operazioni gift card e nota credito
description: Questo argomento offre una panoramica dei miglioramenti che forniscono un passaggio offline fluido per tipi di pagamento specifici.
author: rubendel
manager: AnnBe
ms.date: 02/11/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 20120-02-28
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 0bf37453740d1c2b09b5bd7ae4841f23da20a3ec
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4687539"
---
# <a name="seamless-offline-switch-for-gift-card-and-credit-memo-operations"></a>Passare offline con semplicità per le operazioni gift card e nota credito

[!include [banner](../includes/banner.md)]

Se un dispositivo POS (punto vendita) perde la connessione al database del canale, la maggior parte delle operazioni e transazioni POS in corso può procedere dopo che il cassiere riceve un messaggio di avviso sulla perdita di connettività. Tuttavia, in alcuni casi, le transazioni hanno elementi che si basano sul servizio in tempo reale e tali elementi non sono supportati quando il POS è offline. Questo argomento descrive alcune funzionalità che aiutano a ridurre l'impatto della perdita di connettività in questi scenari.

## <a name="completing-gift-card-transactions-in-offline-mode"></a>Completamento delle transazioni gift card in modalità offline

Le gift card interne dipendono dal servizio in tempo reale, poiché il saldo delle gift card deve essere mantenuto centralmente in Microsoft Dynamics 365 Commerce Headquarters. Per prevenire frodi o altri problemi di sincronizzazione, le gift card vengono bloccate non appena vengono aggiunte a una transazione. La funzione di blocco garantisce che una gift card non possa essere utilizzata contemporaneamente su più terminali. Al termine della transazione, la gift card verrà aggiornata e sbloccata.

Tuttavia, se il POS perde la connettività dopo che una gift card è stata aggiunta a una transazione, la gift card può diventare inutilizzabile. Per prevenire questa situazione, Dynamics 365 Commerce ha un parametro che consente di completare le transazioni che includono una riga di gift card mentre il POS è offline. Quando questo parametro è attivato, le transazioni con gift card forzate offline vengono salvate insieme alle transazioni offline e vengono sincronizzate con Commerce Headquarters quando le transazioni offline vengono sincronizzate. La sincronizzazione sbloccherà anche la gift card in modo da poter essere utilizzata su un altro terminale.

Per abilitare la funzionalità per concludere le transazioni con gift card dopo essere passati alla modalità offline, andare nella scheda **Registrazione** della pagina **Parametri di commercio**. In quella scheda, individuare la scheda dettaglio **Gift card** e impostare **Consenti chiusura transazioni gift card in modalità offline** su **Sì**.

![Impostazione della gift card offline](../media/gift.png)

I parametri di commercio sono generalmente memorizzati nella cache. Pertanto, dopo aver aggiornato l'impostazione di questo parametro e avviato la programmazione della distribuzione per sincronizzare la modifica nel canale, la modifica può richiedere fino a 24 ore per diventare effettiva. Per rendere immediatamente effettiva la modifica, reimpostare Microsoft Internet Information Services (IIS).

## <a name="completing-credit-memo-transactions-in-offline-mode"></a>Completamento delle transazioni nota credito in modalità offline

Come le gift card interne, le note di credito sono gestite centralmente in Commerce Headquarters. Commerce include un parametro che consente di completare le transazioni delle note di credito mentre il POS è offline. Questo parametro funziona come il parametro della gift card menzionato nella sezione precedente. Quando il parametro è attivato, le transazioni con le note di credito che sono forzate offline vengono sincronizzate nuovamente al database del canale, insieme ad altre transazioni eseguite mentre il POS è offline.

Per abilitare la funzionalità per concludere le transazioni con nota di credito dopo essere passati alla modalità offline, andare nella scheda **Registrazione** della pagina **Parametri di commercio**. In quella scheda, individuare la scheda dettaglio **Nota di credito** e impostare **Consenti chiusura transazioni nota di credito in modalità offline** su **Sì**.

![Impostazione della nota di credito offline](../media/creditmemo.png)

I parametri di commercio sono generalmente memorizzati nella cache. Pertanto, dopo aver aggiornato l'impostazione di questo parametro e avviato la programmazione della distribuzione per sincronizzare la modifica nel canale, la modifica può richiedere fino a 24 ore per diventare effettiva. Per rendere immediatamente effettiva la modifica, reimpostare IIS.

## <a name="related-topics"></a>Argomenti correlati

- [Funzionalità POS offline](https://docs.microsoft.com/dynamics365/retail/pos-offline-functionality)
- [Operazioni POS online e offline](https://docs.microsoft.com/dynamics365/retail/pos-operations)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]