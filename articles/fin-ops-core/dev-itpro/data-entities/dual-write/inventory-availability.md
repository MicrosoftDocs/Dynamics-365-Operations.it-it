---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni sulla verifica della disponibilità delle scorte in doppia scrittura.
author: yijialuan
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: dd0995eb8c70ed06cdc3c0f6a28b13b117297533
ms.sourcegitcommit: be7e4378c8122c6e7cfc4e7991efbdffee45e006
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2020
ms.locfileid: "3426984"
---
# <a name="inventory-availability"></a>Disponibilità delle scorte

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

Utilizzando la disponibilità delle scorte, è possibile verificare le scorte prima di aggiungere un prodotto nei moduli **Offerte**, **Ordini** o **Fatture** in app basate su modello in Dynamics 365. Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md). Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste. È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.

## <a name="on-hand-inventory"></a>Scorte disponibili 

Nell'intestazione dei moduli **Offerte**, **Ordini** o **Fatture** in Dynamics 365 Sales, viene aggiunto un nuovo pulsante **Scorte disponibili**. Quando si fa clic sul pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili. Vengono restituite le informazioni sulle scorte presenti in Dynamics 365 Supply Chain Management e queste informazioni sono visualizzate come [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md). Le informazioni includono queste quantità:

- **Quantità disponibile**
- **Quantità disponibile prenotata**
- **Quantità disponibile utilizzabile**
- **Quantità ordinata**
- **Quantità in ordinazione**
- **Quantità ordinata prenotata**
- **Quantità totale disponibile**

## <a name="atp-information"></a>Informazioni ATP

Nelle voci dei moduli **Offerte**, **Ordini** o **Fatture** in Dynamics 365 Sales, viene aggiunto un nuovo pulsante **Informazioni ATP**. Quando si fa clic sul pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine. Vengono restituite le **Informazioni ATP** da Supply Chain Management e vengono visualizzate le impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations). Le informazioni includono **Quantità ATP**, **Quantità entrata**, **Quantità uscita** e **Quantità disponibile**.
