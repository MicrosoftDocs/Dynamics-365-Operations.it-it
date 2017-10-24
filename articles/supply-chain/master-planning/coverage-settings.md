---
title: Impostazioni copertura
description: Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fb11a470d98a9742749daaac3244a5bb0d3a689c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="coverage-settings"></a>Impostazioni copertura

[!include[banner](../includes/banner.md)]


Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli. 

È possibile specificare impostazioni di copertura in vari modi:

-   Specificare impostazioni di copertura per un gruppo di copertura. È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo. Fare clic su **Pianificazione generale &gt; Impostazione &gt; Copertura &gt; Gruppi di copertura** per creare un gruppo di copertura. È possibile collegare un gruppo di copertura a un prodotto. Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**. Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare **Gruppo di copertura** in **Piano** su **Dettagli prodotto**. Se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato per impostazione predefinita il **Gruppo di copertura generale** specificato in **Parametri di pianificazione generale**.

-   Specificare le impostazioni di copertura per un prodotto. È possibile creare impostazioni di copertura per un prodotto specifico. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare il prodotto, nel **riquadro azion**i della scheda **Pianificazione** fare clic su **Gruppo di copertura**, **Copertura articolo** per aprire la pagina **Copertura articolo**. Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**. Le impostazioni**Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.

<!-- -->

-   Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata. La procedura guidata fornisce tutte le istruzioni necessarie per l'impostazione dei principali parametri di copertura articoli. Nella pagina **Copertura articoli**, fare clic su **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.

<!-- -->

-   Specificare impostazioni di copertura per un gruppo di dimensioni. Fare clic su **Gestione informazioni sul prodotto &gt; Comune &gt; Prodotti rilasciati**. Nella pagina **Dettagli prodotto rilasciato** , nella scheda **Generale**, nel gruppo **Amministrazione** fare clic sul collegamento **Gruppo di dimensioni di immagazzinamento**. Nella pagina **Gruppo di dimensioni di immagazzinamento** selezionare il campo **Piano di copertura della dimensione** per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento. Tutte le dimensioni prodotto, ad esempio configurazione, colore, dimensioni, stile, devono avere il campo **Piano di copertura per dimensione** selezionato.



<a name="see-also"></a>Vedere anche
--------

[Piani generali](master-plans.md)




