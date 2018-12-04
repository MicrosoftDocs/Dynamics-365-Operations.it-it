---
title: Gestire le categorie di prodotti al dettaglio e i prodotti
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
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: 19c972164474c972aab642c3cccc67cf396a6cb2
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="manage-retail-product-categories-and-products"></a>Gestire le categorie di prodotti al dettaglio e i prodotti

[!include [banner](./includes/banner.md)]

In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti al dettaglio e i prodotti in Microsoft Dynamics 365 for Retail. I miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura di proprietà dei prodotti condivisa tra la gerarchia di prodotti al dettaglio e i dettagli dei prodotti rilasciati.

Per ulteriori informazioni su come gestire le categorie di prodotti al dettaglio, nell'area di lavoro **Gestione categorie e prodotti** selezionare il riquadro **Gerarchia di prodotti al dettaglio**.

Notare la struttura avanzata della pagina **Gerarchia di prodotti al dettaglio** che viene visualizzata. Nelle versioni precedenti di Retail, le proprietà di prodotto erano suddivise in *proprietà di prodotto di base* e *proprietà di prodotto al dettaglio*, a seconda dell'ambito di applicabilità. Le proprietà di prodotto al dettaglio sono *globali* nell'ambito dell'applicabilità. In altre parole, per una determinata proprietà di prodotto al dettaglio, lo stesso valore viene condiviso tra tutte le persone giuridiche. Le proprietà di prodotto di base sono invece *specifiche della persona giuridica*. In altre parole, per una determinata proprietà di prodotto di base il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali di ogni persona giuridica.

Nella struttura avanzata di categorie di prodotti al dettaglio, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.

![Raggruppamento dei campi in base all'ambito di applicabilità delle proprietà](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.

Per visualizzare le proprietà in tutte le persone giuridiche, selezionare **Visualizza per tutte le persone giuridiche** (o **Modifica per tutte le persone giuridiche**).

![Visualizza/Modifica per tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Per gestire le proprietà di una persona giuridica specifica, selezionare **Visualizza per una specifica persona giuridica** (o **Modifica per una persona giuridica specifica**).

![Visualizza/Modifica per una specifica persona giuridica](media/ToggleToEditForAllLegalEntities.PNG)

Inoltre, nella struttura avanzata di categorie di prodotti al dettaglio un responsabile del merchandising può ora definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a livello di singola categoria. Quando i prodotti vengono creati, ereditano i valori predefiniti per le proprietà i prodotto, in base all'associazione di tali proprietà con una categoria individuale nella gerarchia di prodotti al dettaglio. Queste proprietà di prodotto ereditate possono anche essere modificate per ciascun prodotto allo scopo di soddisfare i requisiti aziendali.

## <a name="selecting-properties-to-update-products-on-the-retail-product-hierarchy-page"></a>Selezione delle proprietà per aggiornare i prodotti nella pagina della categoria di prodotti al dettaglio

È possibile utilizzare la nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati. Nella pagina **Gerarchia di prodotti al dettaglio**, nel Riquadro azioni, selezionare **Categoria**, quindi selezionare **Aggiorna prodotti** per aprire la finestra di dialogo **Aggiorna prodotti**.

![Finestra di dialogo Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG)


