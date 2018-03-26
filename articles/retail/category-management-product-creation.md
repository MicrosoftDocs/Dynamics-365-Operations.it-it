---
title: Gestione di categorie di prodotti
description: In questo argomento viene descritto come i responsabili del merchandising possono utilizzare le categorie di prodotti al dettaglio per gestire le relazioni tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 25fa39dc81fc721d7593a25a102ce47041ebc5f0
ms.openlocfilehash: 4b7ef962b777a31e1da238a8ec1be9a42ec5bb5f
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2018

---


# <a name="enhanced-product-and-category-management"></a>Gestione avanzata di categorie e prodotti

[!include[banner](./includes/banner.md)]

In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti al dettaglio e i prodotti in Dynamics 365 for Retail. Questi miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura comune di proprietà dei prodotti tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.

Per ulteriori informazioni sulla gestione delle categorie di prodotti al dettaglio, passare a **Gerarchia di prodotti al dettaglio** dall'area di lavoro **Gestione categorie e prodotti** e osservare la struttura avanzata della pagina **Categoria di prodotti al dettaglio**.

![Area di lavoro di gestione di categorie e prodotti](media/LaunchRetailProductHierarchy.png)

Nelle versioni precedenti, le proprietà di prodotto erano suddivise in **proprietà di prodotto di base** e **proprietà di prodotto al dettaglio**, a seconda dell'ambito di applicabilità. Le **proprietà di prodotto al dettaglio** erano *globali* per ambito di applicabilità; ciò significa che per una **proprietà di prodotto al dettaglio** specificata, lo stesso valore viene condiviso da tutte le persone giuridiche. Le **proprietà di prodotto di base** sono *specifiche della persona giuridica*. In altre parole, per una determinata **proprietà di prodotto di base** il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali.

Nella struttura avanzata di categorie di prodotti al dettaglio, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.

![Raggruppamento dei campi in base al loro ambito di applicabilità](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa. Per effettuare tale operazione, selezionare **Visualizza/Modifica per tutte le persone giuridiche** o **Visualizza/Modifica per una specifica persona giuridica**.

![Alternare le modalità di visualizzazione tra una singola persona giuridica e tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

![Alternare le modalità di visualizzazione tra una singola persona giuridica e tutte le persone giuridiche](media/ToggleToEditForAllLegalEntities.PNG)  

Rispetto alle versioni precedenti, nella nuova struttura di categorie di prodotti al dettaglio un responsabile del merchandising può inoltre definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a un livello di singola categoria. Al momento della creazione del prodotto, questi valori di proprietà del prodotto predefiniti vengono ereditati da un prodotto, in base alla relativa associazione a una singola categoria dalla gerarchia di prodotti al dettaglio. Queste proprietà di prodotto ereditate possono essere anche modificate per ciascun prodotto, allo scopo di soddisfare i requisiti aziendali.

## <a name="select-properties-to-update-products-from-the-retail-product-category-form"></a>Selezionare le proprietà per aggiornare i prodotti nel modulo Categoria di prodotti al dettaglio 
 
È possibile utilizzare questa nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati. 

![Nuova visualizzazione avanzata di Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG) 

I responsabili del merchandising possono modificare queste proprietà di prodotto ereditate per ciascun prodotto, allo scopo di soddisfare i requisiti aziendali.


