---
title: Riclassificare la quota a breve termine di un'obbligazione sul leasing
description: Questo argomento spiega come creare una scrittura contabile mensile per riclassificare una parte dell'obbligazione sul leasing come a breve termine.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3a71b809b4bb16c2b918b7acd4fbb8bc49278ff6
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727736"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Riclassificare la quota a breve termine di obbligazione sul leasing

[!include [banner](../includes/banner.md)]

Questo argomento spiega come creare una scrittura contabile mensile per riclassificare una parte dell'obbligazione sul leasing come a breve termine. Quando lo scadenziario selezionato nel processo batch è **Riclassificazione dell'obbligazione sul leasing a breve termine**, viene creata una scrittura contabile. Questa voce viene utilizzata per registrare la parte corrente dell'obbligazione sul leasing l'ultimo giorno del mese. Allo stesso tempo, viene registrato un movimento di storno a partire dal primo giorno del mese successivo.

La quota a breve termine dell'obbligazione sul leasing è indicata nel piano di ammortamento della passività. Quando la scrittura contabile viene registrata, la colonna **Giornale di riclassificazione passività creato** diventa disponibile e l'ID del giornale di registrazione viene inserito anche nello scadenziario.

Per creare e registrare la scrittura contabile di riclassificazione dell'obbligazione a breve termine, attieniti alla seguente procedura.

1. Vai a **Leasing cespite \> Periodico \> Creazione di un giornale in batch**.
2. Nella finestra di dialogo **Creazione di un giornale in batch**, nel campo **Seleziona scadenziario**, seleziona **Riclassificazione dell'obbligazione sul leasing a breve termine**.
3. Nel campo **Gruppo di leasing** selezionare un gruppo di leasing. In alternativa, nel campo **ID libro** seleziona l'ID libro.
4. Attiva il parametro **Registra**. In alternativa, se la voce deve essere creata ma non pubblicata, lascia questo parametro disattivato.
5. Selezionare **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
