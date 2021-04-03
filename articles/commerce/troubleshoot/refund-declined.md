---
title: Il rimborso di un ordine di reso viene rifiutato
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e202c6b4b9e025d5af1cd5eb6235884aab6444e6
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585399"
---
# <a name="refund-on-a-return-order-is-declined"></a>Il rimborso di un ordine di reso viene rifiutato

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando un rimborso di un ordine di reso viene rifiutato perché la carta di credito utilizzata per la fatturazione è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale.

## <a name="description"></a>Descrizione

Un rimborso viene rifiutato quando la carta di credito utilizzata per fatturare un ordine di reso è diversa dalla carta utilizzata durante l'autorizzazione di pagamento originale. Viene visualizzato il messaggio di errore seguente: "Lo stato di alcuni pagamenti non è corretto per la registrazione. Riconvalidare lo stato di tutti i pagamenti prima della fatturazione.".

I dettagli dell'autorizzazione di pagamento includeranno il seguente messaggio di errore: "SendRequest() gateway Adyen non riuscito con stato 'InternalServerError'.22144; risposta vuota restituita da Adyen. (22001);"

![Rimborso di un ordine di reso rifiutato](media/refund-order-decline.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="enable-blind-returns-in-adyen"></a>Abilitare resi senza ricevuta in Adyen

Per abilitare i resi senza ricevuta, seguire i passaggi in [Risoluzione dei problemi relativi al Connettore pagamenti di Dynamics 365 per Adyen](adyen-support.md) per contattare il team di supporto Adyen e richiedere che i resi senza ricevuta siano abilitati nell'account esercente Adyen.

## <a name="additional-resources"></a>Risorse aggiuntive

[Connettore pagamenti di Dynamics 365 per Adyen](../dev-itpro/adyen-connector.md)

[Impostare il connettore pagamenti di Dynamics 365 per Adyen](https://docs.adyen.com/plugins/microsoft-dynamics)
