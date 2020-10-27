---
title: Impostazioni della copertura
description: In questo argomento vengono fornite informazioni sulle impostazioni di copertura utilizzate dalla programmazione generale per calcolare le richieste articolo.
author: roxanadiaconu
manager: tfehr
ms.date: 09/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqGroup, ReqItemTable, ReqItemTableWizard, ReqItemTableSetup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2494
ms.assetid: 5a95ae4f-ca75-47d9-a1c3-68c97b42f166
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b1134f734f1025151a56b2a72266a6baa5763ba4
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3982722"
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


## <a name="coverage-codes"></a>Codici di copertura

La pianificazione generale può essere configurata per utilizzare differenti metodi di rifornimento. I metodi di rifornimento o di dimensionamento dei lotti sono le tecniche utilizzate dal sistema per determinare le dimensioni dei batch degli articoli acquistati o prodotti. 

A ogni metodo di rifornimento viene assegnato uno dei seguenti codici di copertura:

- **Manuale** - Il metodo di dimensionamento dei lotti in cui il sistema non suggerisce ordini di produzione, trasferimento o fornitore per l'articolo. Il responsabile della pianificazione dell'articolo dovrà creare gli ordini necessari per il rifornimento dell'articolo.
- **Per fabbisogno** - Il metodo di dimensionamento dei lotti in cui il sistema crea un ordine di produzione, trasferimento o fornitore per fabbisogno per l'articolo. Questo codice viene in genere utilizzato per gli articoli costosi con domanda intermittente.  
- **Per periodo** - Il metodo di dimensionamento dei lotti che combina tutta la domande durante un periodo in un ordine per l'articolo. L'ordine verrà pianificato per il primo giorno del periodo e la relativa quantità soddisferà i fabbisogni netti durante il periodo stabilito. Il periodo inizia con la prima domanda dell'articolo e copre la lunghezza definita nel tempo. Il periodo successivo inizierà con i requisiti successivi dell'articolo.
- **Min/Max** - Il metodo di dimensionamento dei lotti che contiene il rifornimento delle scorte fino a un determinato livello quando la disponibilità prevista è inferiore a una soglia. La quantità di rifornimento sarà la differenza tra il livello massimo e il livello disponibile previsto.


## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica piani generali](master-plans.md)
