--- 
title: " Configurare i suggerimenti sul prodotto basati su Machine Learning"
description: "Questa procedura consente di aggiornare i dati nell'archivio entità utilizzati dal sistema di apprendimento automatico su cui si basano i suggerimenti sul prodotto e quindi di abilitare tali suggierimenti sui client POS."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: e32c7cf1283487cb7a52f7d8e261b6b587b76364
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a> Configurare i suggerimenti sul prodotto basati su Machine Learning

[!include[task guide banner](../includes/task-guide-banner.md)]

Questa procedura consente di aggiornare i dati nell'archivio entità utilizzati dal sistema di apprendimento automatico su cui si basano i suggerimenti sul prodotto e quindi di abilitare tali suggierimenti sui client POS. Questa procedura utilizza i dati dimostrativi della società USRT.

1. Scegliere Amministrazione sistema > Impostazioni > Archivio entità.
2. Nell'elenco trovare e selezionare il record 'RetailSales'.
3. Fare clic su Aggiorna.
4. Fare clic su OK.
5. Chiudere la pagina.
6. Andare a Vendita al dettaglio e commercio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.
7. Fare clic sulla scheda Machine Learning.
8. Selezionare 'Sì' nel campo Abilita suggerimenti sul prodotto.
    * Se si riceve il messaggio 'Impossibile recuperare i modelli di suggerimento', significa che si è aggiornato l'archivio entità molto di recente e il sistema può non avere completato di assimilare i nuovi dati. Attendere 2-3 ore e riprovare.  
9. Fare clic su Salva.
10. Chiudere la pagina.


