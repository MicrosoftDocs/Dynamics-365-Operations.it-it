---
title: Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito
description: Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: 49d16c39fdcee0a22d1cabe14cd9b6d124d6f04d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8901678"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito

[!include [banner](../../includes/banner.md)]

Questo articolo fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.

## <a name="description"></a>Descrizione

Quando si sincronizza un ordine online, viene visualizzato il seguente messaggio di errore: "Deve essere presente un servizio di pagamento predefinito per elaborare le transazioni con carta di credito".

![Errore dovuto al servizio di pagamento predefinito mancante.](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters

Per confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters, procedere come segue.

1. Selezionare **Contabilità clienti \> Impostazione pagamenti \> Servizi di pagamento**.
1. Assicurarsi che l'opzione **Processore predefinito per nuove carte di credito** è impostata su **Sì** per un servizio di pagamento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostazione, autorizzazione e acquisizione della carta di credito](../../finance/accounts-receivable/credit-card-authorizations.md)