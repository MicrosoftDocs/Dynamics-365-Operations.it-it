---
title: Il rimborso di un ordine di reso viene rifiutato
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: d8d1c40673d4b159a7b7bf00bf6011ba45f47edd
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268234"
---
# <a name="refund-on-a-return-order-is-declined"></a>Il rimborso di un ordine di reso viene rifiutato

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.

## <a name="description"></a>Descrizione

Un rimborso viene rifiutato quando la carta di credito utilizzata per fatturare un ordine di reso è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale. Viene visualizzato il messaggio di errore seguente: "Lo stato di alcuni pagamenti non è corretto per la registrazione. Riconvalidare lo stato di tutti i pagamenti prima della fatturazione.".

I dettagli dell'autorizzazione di pagamento includeranno il seguente messaggio di errore: "SendRequest() gateway Adyen non riuscito con stato 'InternalServerError'.22144; risposta vuota restituita da Adyen. (22001);"

![Rimborso di un ordine di reso rifiutato.](media/refund-order-decline.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="enable-blind-returns-in-adyen"></a>Abilitare resi senza ricevuta in Adyen

Per abilitare i resi senza ricevuta, seguire i passaggi in [Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen](adyen-support.md) per contattare il team di supporto Adyen e richiedere che i resi senza ricevuta siano abilitati nell'account esercente Adyen.

## <a name="additional-resources"></a>Risorse aggiuntive

[Connettore pagamenti di Dynamics 365 per Adyen](../dev-itpro/adyen-connector.md)

[Impostare il connettore pagamenti di Dynamics 365 per Adyen](https://docs.adyen.com/plugins/microsoft-dynamics)
