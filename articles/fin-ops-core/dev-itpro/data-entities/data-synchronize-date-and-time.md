---
title: Sincronizzare la data e l'ora nei processi di importazione
description: Utilizza i fusi orari UTC nei processi di importazione per evitare problemi con le conversioni di fuso orario.
author: peakerbl
ms.date: 12/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-12-01
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b8faa7b73349c48d3a02b685546b47c4969c6027
ms.sourcegitcommit: 3289478a05040910f356baf1995ce0523d347368
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "9109434"
---
# <a name="synchronize-date-and-time-in-import-jobs"></a>Sincronizzare la data e l'ora nei processi di importazione

[!include [banner](../includes/banner.md)]

È importante impostare il fuso orario per il processo di importazione su UTC (Coordinated Universal Time). Potresti visualizzare date e ore impreviste nei dati importati se utilizzi un'impostazione diversa. Senza l'impostazione corretta, il processo di importazione converte la data UTC nel formato locale, quindi le impostazioni di sistema la convertono di nuovo.

Questa doppia conversione fa sì che le date cambino tra le applicazioni. Ad esempio, la doppia conversione potrebbe far sì che la data di inizio di un dipendente sia diversa tra Dynamics 365 Human Resources e Dynamics 365 Finance a causa delle differenze nei fusi orari locali. L'impostazione del processo di importazione su UTC risolve questo problema.

1. Nell'ambiente di finanza e operazioni di Dynamics 365, selezionare **Gestione dati**.

2. Seleziona **Importa progetti** e quindi seleziona il progetto.

3. In **Formato data di origine**, seleziona **CSV-Unicode**.

   [![Modificare il formato della data di origine in UTC.](./media/data-source-date-format.png)](./media/data-source-date-format.png)

4. Modificare **Fuso orario** in **Fuso orario UTC** e cambiare **Lingua** in **En-US**.




[!INCLUDE[footer-include](../../../includes/footer-banner.md)]

