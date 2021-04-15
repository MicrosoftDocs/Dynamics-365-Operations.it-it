---
title: Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.
author: Reza-Assadi
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
ms.openlocfilehash: 45eeae751051b58e1c9e725eb4ed4b5240026e7f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801437"
---
# <a name="order-synchronization-error-related-to-the-default-payment-service"></a>Errore di sincronizzazione dell'ordine relativo al servizio di pagamento predefinito

[!include [banner](../../includes/banner.md)]

Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono aiutare a correggere un errore che potrebbe verificarsi quando viene sincronizzato un ordine online.

## <a name="description"></a>Descrizione

Quando si sincronizza un ordine online, viene visualizzato il seguente messaggio di errore: "Deve essere presente un servizio di pagamento predefinito per elaborare le transazioni con carta di credito".

![Errore dovuto al servizio di pagamento predefinito mancante](media/default-payment-method-error.jpg)

## <a name="resolution"></a>Risoluzione

### <a name="confirm-or-set-the-default-payment-service-in-commerce-headquarters"></a>Confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters

Per confermare o impostare il servizio di pagamento predefinito in Commerce Headquarters, procedere come segue.

1. Selezionare **Contabilità clienti \> Impostazione pagamenti \> Servizi di pagamento**.
1. Assicurarsi che l'opzione **Processore predefinito per nuove carte di credito** è impostata su **Sì** per un servizio di pagamento.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostazione, autorizzazione e acquisizione della carta di credito](https://docs.microsoft.com/dynamics365/finance/accounts-receivable/credit-card-authorizations)
