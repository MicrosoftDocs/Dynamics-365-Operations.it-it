---
title: Configurare nomi di giornale di leasing
description: Questo argomento spiega come definire i nomi dei giornali di leasing. I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrati i movimenti che hanno origine in Leasing cespite.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 89c5fc768aafe9e5de9adcde32e7b4d0a084941b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990919"
---
# <a name="set-up-lease-journal-names"></a>Configurare nomi di giornale di leasing

[!include [banner](../includes/banner.md)]

I nomi dei giornali di leasing specificano i giornali di registrazione in cui vengono registrate le transazioni di Leasing cespite. Solo i nomi di giornale di registrazione assegnati al tipo di giornale di registrazione **Leasing cespite** vengono visualizzati nei campi **Riconoscimento iniziale** e **Nome giornale di registrazione mensile** della pagina **Parametri del leasing cespite**. Solo il tipo di giornale di registrazione **registrazione fattura fornitore** può essere assegnato al campo **Nome giornale di registrazione fatture**.

Per configurare i nomi dei giornali di leasing, segui questi passaggi.

1. Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.
2. Nella scheda **Generale**, nel campo **Nome giornale di registrazione riconoscimento iniziale**, seleziona un giornale di registrazione. Tutte le registrazioni a giornale di riconoscimento iniziale verranno registrate in questo nome di giornale di registrazione.
3. Nel campo **Nome giornale di registrazione fatture**, seleziona un giornale di registrazione. Se l'opzione **Paga a fornitore** è impostata su **Sì** per il libro di leasing, le fatture di pagamento di leasing e spese verranno registrate in questo nome di giornale di registrazione.
4. Nel campo **Nome giornale di registrazione leasing**, seleziona un giornale di registrazione. Tutti i movimenti di ammortamento, interessi e riclassificazione a breve termine verranno registrati in questo nome giornale di registrazione. Se l'opzione **Paga a fornitore** è impostata su **No** per il libro di leasing, anche i movimenti di pagamento di leasing e spese verranno registrati in questo nome di giornale di registrazione.
