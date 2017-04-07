---
title: Impostazioni copertura
description: Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli.
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c1c5654afa6b592e178af052e3e4a7e246a94c9f
ms.lasthandoff: 03/31/2017


---

# <a name="coverage-settings"></a>Impostazioni copertura

Nella programmazione generale vengono utilizzate impostazioni di copertura per calcolare le richieste di articoli. 

È possibile specificare impostazioni di copertura in vari modi:

-   Specificare impostazioni di copertura per un gruppo di copertura. È possibile creare un gruppo di copertura contenente impostazioni per tutti i prodotti collegati al gruppo. Fare clic su ** pianificazione &gt; generale impostare &gt; i gruppi &gt; di copertura di copertura ** per creare un gruppo di copertura. È possibile collegare un gruppo di copertura a un prodotto. Se il collegamento è specifico a un sito, un magazzino, o a una dimensione prodotto, utilizzare il campo **Gruppo di copertura** nella pagina **Copertura articoli**. Se il collegamento è generico, indipendentemente dalle dimensioni prodotto, utilizzare **Gruppo di copertura** in **Piano** su **Dettagli prodotto**. Se non si collega un gruppo di copertura a una pianificazione generale prodotti, verrà utilizzato per impostazione predefinita il **Gruppo di copertura generale** specificato in **Parametri di pianificazione generale**.

-   Specificare le impostazioni di copertura per un prodotto. È possibile creare impostazioni di copertura per un prodotto specifico. ** Prodotti Fare clic su Gestione informazioni &gt; sul &gt; prodotto rilasciati i prodotti **. Selezionare il prodotto, ** nel riquadro azioni **, nel piano ** ** la scheda, in ** gruppo di copertura **, fare clic su ** copertura articoli ** per aprire ** copertura articoli ** la pagina. Se il prodotto è già collegato a un gruppo di copertura, è possibile ignorare le impostazioni del gruppo utilizzando il campo **Forzatura**. Le impostazioni** Copertura articoli** di copertura nella pagina hanno la priorità sulle impostazioni **Gruppo di copertura** nella pagina.

<!-- -->

-   Specificare le impostazioni di copertura per un prodotto utilizzando una procedura guidata. La procedura guidata fornisce tutte le istruzioni necessarie per l'impostazione dei principali parametri di copertura articoli. Nella pagina **Copertura articoli**, fare clic su **Procedura guidata** per aprire la **Procedura guidata di copertura articoli**.

<!-- -->

-   Specificare impostazioni di copertura per un gruppo di dimensioni. Fare clic su ** Ordinarie Gestione informazioni &gt; sul &gt; prodotto rilasciati i prodotti **. ** Nei dettagli del prodotto rilasciato ** pagine, il ** ** la scheda dettagli relativi all'identificazione, amministrazione ** ** nel gruppo, fare clic su ** gruppo di dimensioni di immagazzinamento ** il collegamento. Nella pagina **Gruppo di dimensioni di immagazzinamento** selezionare il campo **Piano di copertura della dimensione** per creare le impostazioni di copertura per una dimensione nel gruppo di dimensioni di immagazzinamento. Tutte le dimensioni, ad esempio la configurazione, colore, la dimensione, stile, devono avere ** piano di copertura per dimensione ** il campo selezionato.



<a name="see-also"></a>Vedere anche
--------

[Master plans](master-plans.md)


