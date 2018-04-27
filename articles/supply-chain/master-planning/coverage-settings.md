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
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 591b1cd739bb3be61299f33f180ca7c264d21a35
ms.contentlocale: it-it
ms.lasthandoff: 04/13/2018

---

# <a name="coverage-settings"></a>Impostazioni copertura

[!INCLUDE [banner](../includes/banner.md)]

Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli. 

È possibile specificare impostazioni di copertura in vari modi:

-   Specificare impostazioni di copertura per un gruppo di copertura. È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo. Fare clic su **Pianificazione generale &gt; Impostazione &gt; Copertura &gt; Gruppi di copertura** per creare un gruppo di copertura. È possibile collegare un gruppo di copertura a un prodotto. Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**. Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare **Gruppo di copertura** in **Piano** su **Dettagli prodotto**. Se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato per impostazione predefinita il **Gruppo di copertura generale** specificato in **Parametri di pianificazione generale**.

-   Specificare le impostazioni di copertura per un prodotto. È possibile creare impostazioni di copertura per un prodotto specifico. Fare clic su **Gestione informazioni sul prodotto &gt; Prodotti &gt; Prodotti rilasciati**. Selezionare il prodotto, nel **riquadro azion**i della scheda **Pianificazione** fare clic su **Gruppo di copertura**, **Copertura articolo** per aprire la pagina **Copertura articolo**. Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**. Le impostazioni**Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.

<!-- -->

-   Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata. La procedura guidata fornisce tutte le istruzioni necessarie per l'impostazione dei principali parametri di copertura articoli. Nella pagina **Copertura articoli**, fare clic su **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.

<!-- -->

- Specificare impostazioni di copertura per un gruppo di dimensioni. Fare clic su <strong>Gestione informazioni sul prodotto &gt; Comune &gt; Prodotti rilasciati</strong>. Nella pagina <strong>Dettagli prodotto rilasciato**, nella scheda **Generale</strong>, nel gruppo <strong>Amministrazione</strong> fare clic sul collegamento <strong>Gruppo di dimensioni di immagazzinamento</strong>. Nella pagina <strong>Gruppo di dimensioni di immagazzinamento</strong> selezionare il campo <strong>Piano di copertura della dimensione</strong> per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento. Tutte le dimensioni prodotto, ad esempio configurazione, colore, dimensioni, stile, devono avere il campo <strong>Piano di copertura per dimensione</strong> selezionato.



<a name="see-also"></a>Vedere anche
--------

[Piani generali](master-plans.md)




