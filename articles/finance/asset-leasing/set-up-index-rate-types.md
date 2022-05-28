---
title: Configurare i tassi di indicizzazione
description: In questo argomento viene spiegato come configurare i tassi di indicizzazione. I tassi di indicizzazione sono obbligatori se la tua organizzazione associa gli importi del canone di leasing a una serie di tassi di indicizzazione.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseIndexRateType
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: c6396b8c12520abb0e33cda713d5483f61610db4
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726524"
---
# <a name="set-up-index-rates"></a>Configurare i tassi di indicizzazione

[!include [banner](../includes/banner.md)]

Se i canoni di leasing dipendono da un indice, i tipi di tasso di indicizzazione possono essere aggiunti e gestiti nel sistema. Per rivalutare i canoni di leasing dalla pagina **Tipo di tasso di indicizzazione**, il processo di rivalutazione del tasso di indicizzazione utilizza il tasso di indicizzazione più recente dalla data di rivalutazione.

Per aggiungere tipi di tassi di indicizzazione e tassi di indicizzazione, segui questi passaggi.

1. Vai a **Leasing cespiti \> Imposta \> Tipi di tassi di indicizzazione**.
2. Selezionare **Nuovo**.
3. Nei campi appropriati, immetti il tipo di tasso e il nome del tasso di indicizzazione.
4. Per aggiungere un nuovo valore di tasso di indicizzazione, seleziona il tipo di tasso di indicizzazione, quindi seleziona **Aggiungi**.
5. Seleziona la data di inizio effettiva del tasso e seleziona il valore del tasso.

Devi selezionare **Differenza di valore del tasso di indicizzazione** o **Valore del tasso di indicizzazione** come metodo del tasso di indicizzazione.

- Seleziona il metodo **Differenza di valore del tasso di indicizzazione** per calcolare un nuovo canone di leasing, basato sulla differenza tra il tasso di indicizzazione alla data di inizio e il tasso di indicizzazione più recente. Il tasso di indicizzazione è definito nel campo **Tasso di indicizzazione (%)**.
- Seleziona il metodo **Valore del tasso di indicizzazione** per calcolare il canone di leasing utilizzando la percentuale specificata nel campo **Tasso di indicizzazione (%)**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
