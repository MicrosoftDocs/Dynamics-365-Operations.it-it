---
title: Limitare i metodi di pagamento per i resi senza una ricevuta
description: In questo argomento viene descritto come determinati tipi di pagamento possono essere limitati per il rimborso se i resi vengono eseguiti senza una ricevuta.
author: rapraj
manager: AnnBe
ms.date: 01/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTenderTypeTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15831
ms.assetid: 465893a5-6b4f-4c5f-b305-db071df2d33f
ms.search.region: global
ms.search.industry: Retail
ms.author: yabinl
ms.search.validFrom: 2019-02-01
ms.dyn365.ops.version: AX 10.0.0, Retail Feb 2019 update
ms.openlocfilehash: 1f84a6382453c0ba7540e618ad90ae1d3c684a2b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "315914"
---
# <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Limitare i metodi di pagamento per i resi senza una ricevuta

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Ogni tipo di pagamento accettato dal rivenditore deve essere configurato quando si imposta il sistema. In questo argomento viene descritto come determinati tipi di pagamento possono essere limitati per il rimborso se i resi vengono eseguiti senza una ricevuta.

## <a name="set-up-payment-methods"></a>Impostare i metodi di pagamento

Per impostare i metodi di pagamento, è necessario completare le attività indicate di seguito.
1. Creare i metodi di pagamento accettati da tutta l'organizzazione.
2. Creare tipi e numeri di carta a livello di organizzazione. Se le carte di credito o di debito sono accettate, è necessario creare un metodo di pagamento per carte, quindi creare i tipi e i numeri di carta a livello di organizzazione.
3. Impostare metodi di pagamento per punti vendita. Associare i metodi di pagamento a ogni punto vendita, quindi immettere le impostazioni specifiche del punto vendita per ogni metodo di pagamento.
4. Impostare metodi di pagamento con carta per punti vendita. Per qualsiasi metodo di pagamento con carta accettato dal punto vendita, è necessario completare l'impostazione della carta.

![impostazione punto vendita al dettaglio](media/NoReceiptReturns1.png "Impostazione punto vendita al dettaglio") 


## <a name="restrict-payment-methods-for-returns-without-a-receipt"></a>Limitare i metodi di pagamento per i resi senza una ricevuta

Per ogni metodo di pagamento per punto vendita, nella pagina **Gestione punto vendita al dettaglio**, in **Resi senza ricevuta**, impostare **Limitare per rimborsi senza ricevuta** su **Sì**. 

Il valore predefinito è **No**, a indicare che il metodo di pagamento è consentito per i rimborsi. 

Quando l'opzione **Limitare per i rimborsi senza ricevuta** è impostata su **Sì**, il metodo di pagamento selezionato non sarà consentito per i rimborsi. 

![Metodo di pagamento per punto vendita al dettaglio](media/NoReceiptReturns3.png "Metodo di pagamento per punto vendita al dettaglio") 

> [!NOTE]
> Quando un cassiere seleziona un metodo di pagamento che è limitato per il rimborso senza ricevuta, viene visualizzato un messaggio per verificare i metodi di pagamento accettabili.

![Metodi di pagamento accettabili](media/NoReceiptReturns4.png "Metodi di pagamento accettabili") 

Se una transazione ha un reso con ricevuta e un reso senza ricevuta, le condizioni di restrizione non verranno applicate perché la transazione sarà un flusso di lavoro di reso con una ricevuta. 

