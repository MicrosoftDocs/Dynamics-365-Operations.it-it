---
title: Disponibilità delle scorte in doppia scrittura
description: Questo argomento fornisce informazioni su come controllare la disponibilità delle scorte in doppia scrittura.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: riluan
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-05-26
ms.openlocfilehash: 4d1022eec633bf0a9edb4d5b26982853cec836d7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4454211"
---
# <a name="inventory-availability-in-dual-write"></a>Disponibilità delle scorte in doppia scrittura

[!include [banner](../../includes/banner.md)]

Utilizzando la disponibilità delle scorte, puoi verificare le scorte prima di aggiungere un prodotto alla pagina **Offerte**, **Ordini** o **Fatture** in Microsoft Dynamics 365 Sales. Ad esempio, la verifica delle scorte e la determinazione di una data di evasione sono attività chiave nel processo [prospect-to-cash](dual-write-prospect-to-cash.md).

Se non si dispone di scorte sufficienti, è possibile stimare una data di consegna in base a entrate e uscite da magazzino previste. È anche possibile verificare le informazioni available-to-promise (ATP) del prodotto, che indicano la quantità ATP nell'intervallo temporale predefinito.

## <a name="on-hand-inventory"></a>Scorte disponibili

In Dynamics 365 Sales, nell'intestazione delle pagine **Offerte**, **Ordini** e **Fatture**, viene aggiunto un nuovo pulsante **Scorte disponibili**. Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società e il prodotto per i quali si desidera verificare le scorte disponibili. Questa finestra di dialogo mostra le stesse informazioni di [Scorte disponibili](../../../../supply-chain/inventory/tasks/check-availability-stock.md).

La finestra di dialogo restituisce le informazioni di inventario da Dynamics 365 Supply Chain Management. Queste informazioni includono le seguenti quantità:

- Quantità disponibile
- Quantità disponibile prenotata
- Quantità disponibile utilizzabile
- Quantità ordinata
- Quantità in ordinazione
- Quantità ordinata prenotata
- Quantità totale disponibile

## <a name="atp-information"></a>Informazioni ATP

Nelle Sales, è stato aggiunto alle voci un nuovo pulsante **Informazioni ATP** nelle pagine **Offerte**, **Ordini** e **Fatture**. Quando selezioni questo pulsante, viene visualizzata una finestra di dialogo in cui è possibile specificare la società, il prodotto, il sito magazzino, il magazzino scorte e la quantità dell'ordine. Questa finestra di dialogo ha le stesse impostazioni descritte in [Promesse ordine](../../../../supply-chain/sales-marketing/delivery-dates-available-promise-calculations.md#atp-calculations).

La finestra di dialogo restituisce le informazioni ATP da Supply Chain Management. Queste informazioni includono le seguenti quantità:

- Quantità ATP
- Quantità entrata
- Quantità uscita
- Quantità disponibile
