---
title: Configurare ed eseguire il processo per calcolare i rendiconti
description: In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato.
author: josaw1
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ecbc35cabced37a51ecedcd3f37bff2f23c093e184607b0c4d57ae9e70ae2c75
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751521"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Configurare ed eseguire il processo per calcolare i rendiconti

[!include [banner](../includes/banner.md)]

In questa procedura vengono descritti i passaggi per configurare ed eseguire i processi batch ricorrenti al fine di creare e calcolare i rendiconti per un punto vendita o un gruppo di punti vendita selezionato. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Passare a Tutte le aree di lavoro > Dati finanziari punto vendita al dettaglio.
2. Fare clic su Calcola rendiconti.
    * Selezionare un punto vendita specifico o un nodo se si desidera creare il processo batch per un gruppo di punti vendita.  
    * Fare clic sulla freccia per aggiungere la selezione.  
3. Fare clic sulla scheda Esecuzione in background.
4. In Elaborazione batch, selezionare 'Sì'.
5. Fare clic su Ricorrenza.
6. Nel campo Data di inizio, immettere una data.
7. Immettere l'ora nel campo Ora di inizio.
8. Selezionare l'opzione Nessuna data di fine.
9. Nel campo PatternUnit immettere 'Giorni'.
10. Nel campo Per immettere un numero.
11. Fare clic su OK.
12. Fare clic su OK.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]