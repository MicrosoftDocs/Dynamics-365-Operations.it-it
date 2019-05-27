---
title: Impostazioni della copertura
description: In questo argomento vengono fornite informazioni sulle impostazioni di copertura utilizzate dalla programmazione generale per calcolare le richieste articolo.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 99e094a7131b6d3a299fc72abd0141529908ddd2
ms.sourcegitcommit: 9e50bee6a67f0fe2fa6f86e02c7e8de16d0e2482
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2019
ms.locfileid: "1538896"
---
# <a name="coverage-settings"></a>Impostazioni della copertura

[!include [banner](../includes/banner.md)]

Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.

È possibile specificare impostazioni di copertura in vari modi:

- Specificare impostazioni di copertura per un gruppo di copertura.

    È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo. Per creare un gruppo di copertura, fare clic su **Pianificazione generale &gt; Impostazione &gt; Copertura &gt; Gruppi di copertura**. È possibile collegare un gruppo di copertura a un prodotto. Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**. Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare il campo **Gruppo di copertura** in **Piano** su **Dettagli prodotto**. Per impostazione predefinita, se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato il Gruppo di copertura generale specificato in **Parametri di pianificazione generale**.

- Specificare le impostazioni di copertura per un prodotto.

    È possibile creare impostazioni di copertura per un prodotto specifico. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare il prodotto, nel riquadro azioni della scheda **Pianificazione** fare clic su **Gruppo di copertura**, **Copertura articolo** per aprire la pagina **Copertura articolo**. Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**. Le impostazioni**Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.

- Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata.

    La procedura guida l'utente passo dopo passo nel processo di impostazione dei parametri di copertura degli articoli principali. Nella pagina **Copertura articoli**, nel riquadro azioni selezionare **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.

- Specificare impostazioni di copertura per un gruppo di dimensioni.

    Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Nella pagina **Dettagli prodotto rilasciato** , nella scheda dettagli **Generale**, nella sezione **Amministrazione** selezionare il collegamento nel campo **Gruppo di dimensioni di immagazzinamento**. Nella pagina **Gruppi di dimensioni di immagazzinamento** selezionare la casella di controllo **Piano di copertura della dimensione** per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento. Per tutte le dimensioni prodotto, ad esempio configurazione, colore, dimensioni, stile, il campo **Piano di copertura per dimensione** deve essere selezionato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Piani generali](master-plans.md)
