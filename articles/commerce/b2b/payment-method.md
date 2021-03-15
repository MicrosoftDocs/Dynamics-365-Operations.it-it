---
title: Configurare il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B
description: Questo argomento descrive come configurare il metodo di pagamento del conto cliente per i siti di e-commerce business-to-business (B2B).
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 754e2f83d6c8ff5d3698d98062e54bba7ccd9836
ms.sourcegitcommit: f9df202aefef761be52c0360b0e22da88773914c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035926"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Configurare il metodo di pagamento dell'account cliente per i siti Web di e-commerce B2B

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come configurare il metodo di pagamento del conto cliente per i siti di e-commerce business-to-business (B2B).

I rivenditori possono accettare diversi tipi di pagamento per i prodotti venduti e i servizi forniti in un canale di e-commerce. Ogni tipo di pagamento accettato dal rivenditore deve essere configurato in Microsoft Dynamics 365 Commerce quando si imposta il sistema. Il metodo di pagamento del conto cliente (o "in acconto") deve essere supportato sui siti di e-commerce B2B. 

## <a name="prerequisites"></a>Prerequisiti

1. Aggiungi il metodo di pagamento del conto cliente in Commerce headquarters.
2. Associa il metodo di pagamento del conto cliente al canale di e-commerce.
3. Assicurati che **Consenti in acconto** sia abilitato per il cliente in **Retail e Commerce \> Clienti \> Tutti i clienti \> Impostazioni predefinite pagamento** in Commerce headquarters. Assicurati anche che i parametri **Limite di credito** siano impostati in modo appropriato per il cliente in **Retail e Commerce \> Clienti \> Tutti i clienti \> Credito e riscossioni** in Commerce headquarters. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce 

Per abilitare il metodo di pagamento del conto cliente in Creazione di siti di Commerce, segui questi passaggi.

1. Vai a **Impostazioni sito \> Estensioni**.
1. Imposta la proprietà **Abilita pagamenti conto cliente** su **Abilitato per clienti B2B**. 
1. Selezionare **Salva e pubblica**.

> [!NOTE]
> Le nuove impostazioni del sito avranno effetto solo dopo l'aggiornamento del file app.settings.json. Per ulteriori informazioni, vedi [SDK e aggiornamenti della libreria moduli](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B

Per abilitare il metodo di pagamento del conto cliente nella pagina di pagamento del sito di e-commerce B2B, segui questi passaggi.

1. In Creazione di siti di Commerce, trova e modifica la pagina di pagamento o il frammento che contiene il modulo di pagamento per il sito di e-commerce B2B.
1. Nello slot **Contenitore sezione checkout**, seleziona **Aggiungi modulo**, quindi aggiungi un modulo **Pagamento conto cliente**.
1. Posiziona il modulo **Pagamento conto cliente** selezionando i puntini di sospensione (**...**), quindi selezionando **Sposta su** o **Sposta giù** come necessario.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato

Per verificare che il metodo di pagamento del conto cliente sia stato abilitato e pubblicato, segui questi passaggi.

1. Accedi al sito di e-commerce.
1. Aggiungi un prodotto al carrello.
1. Vai alla pagina di pagamento. Dovresti vedere il nuovo metodo di pagamento **Conto cliente**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare un sito di e-commerce B2B](set-up-b2b-site.md)

[Creare gerarchie di modellazione per le organizzazioni B2B](org-model.md)

[Gestisci gli utenti dei partner commerciali sui siti di e-commerce B2B](manage-b2b-users.md)

[Impostare limiti di quantità di prodotti per i siti di e-commerce B2B](quantity-limits.md)

[SDK e aggiornamenti libreria dei moduli](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]