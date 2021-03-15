---
title: Modulo di informazioni sul ritiro
description: In questo argomento viene descritto il modulo di informazioni sul ritiro e la procedura per aggiungerlo alle pagine del checkout in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-09021
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: d04e2650f9c601d008ebf19080059b70416d7917
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000611"
---
# <a name="pickup-information-module"></a>Modulo di informazioni sul ritiro

[!include [banner](includes/banner.md)]

In questo argomento viene descritto il modulo di informazioni sul ritiro e la procedura per aggiungerlo alle pagine del checkout in Microsoft Dynamics 365 Commerce.

Il modulo di informazioni sul ritiro può essere utilizzato in un modulo checkout per mostrare le informazioni sul ritiro dell'ordine. I clienti possono visualizzare le date di ritiro e le fasce orarie disponibili, quindi selezionare un orario adatto per ritirare l'ordine. Ad esempio, un cliente può scegliere di ritirare un ordine alle 15.00 del 21 marzo dal negozio di San Francisco.

Le fasce orarie di ritiro per i negozi appropriati devono essere configurate in Commerce headquarters. Per ulteriori informazioni, vedere [Creare e aggiornare le fasce orarie per il ritiro del cliente](dev-itpro/pickup-timeslots.md).

Se un modulo di informazioni sul ritiro viene creato su una pagina checkout, ma non sono definiti intervalli di tempo per il negozio selezionato per il ritiro, il modulo mostrerà le informazioni, ma l'utente non sarà in grado di selezionare alcuna fascia oraria. Le fasce orarie sono opzionali e non sono necessarie per effettuare un ordine.

Se vengono selezionati più articoli per il ritiro in più negozi, il modulo di informazioni sul ritiro consentirà all'utente di selezionare una fascia oraria per ogni negozio, a condizione che siano disponibili le fasce orarie per il negozio.

> [!NOTE]
> Il supporto per le fasce orarie e il modulo di informazioni sul ritiro è disponibile in Dynamics 365 Commerce versione 10.0.15 e successive.

La seguente illustrazione mostra un esempio di selezione della fascia oraria tramite il modulo di informazioni sul ritiro in una pagina checkout.

![Esempio di un modulo di informazioni sul ritiro su una pagina checkout](./dev-itpro/media/Curbside_timeslot_eCommerce.PNG)

## <a name="module-properties"></a>Proprietà del modulo

- **Intestazione** – Immettere un'intestazione per il modulo.

## <a name="show-time-slot-information-after-an-order-is-placed"></a>Mostrare le informazioni sulla fascia oraria dopo aver effettuato un ordine

Dopo aver effettuato un ordine, le informazioni sulla fascia oraria selezionata possono essere visualizzate nel [modulo di conferma dell'ordine](order-confirmation-module.md) e nel [modulo dettagli ordine](account-management.md#order-details-page). Entrambi questi moduli hanno la proprietà **Mostra informazioni sulla fascia oraria**. Per mostrare la fascia oraria selezionata durante il processo di ordinazione, questa proprietà deve essere impostata su **Vero**.

## <a name="add-a-checkout-pickup-information-module-to-a-page"></a>Aggiungere un modulo di informazioni sul ritiro a una pagina checkout

Per istruzioni su come aggiungere un moduli di informazioni sul ritiro a una pagina checkout e impostare le proprietà richieste, vedere [Modulo Checkout](add-checkout-module.md).

La seguente illustrazione mostra un esempio di una pagina checkout e-commerce che include fasce orarie per gli articoli della riga di ritiro.

![Esempio di una pagina checkout e-commerce che include fasce orarie per gli articoli della riga di ritiro.](./dev-itpro/media/Curbside_timeslot_eCommerce_checkoutsummary.PNG)

## <a name="additional-resources"></a>Risorse aggiuntive

[Creare e aggiornare le fasce orarie per il ritiro del cliente](dev-itpro/pickup-timeslots.md)

[Modulo checkout](add-checkout-module.md)

[Modulo conferma ordine](order-confirmation-module.md)

[Modulo Dettagli ordini](account-management.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]