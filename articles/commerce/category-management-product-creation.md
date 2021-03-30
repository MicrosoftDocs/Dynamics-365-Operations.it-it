---
title: Gestire le categorie di prodotti e i prodotti
description: In questo argomento viene descritto come i responsabili del merchandising possono utilizzare le categorie di prodotti per gestire le relazioni tra la gerarchia di prodotti di Commerce e i dettagli dei prodotti rilasciati.
author: ashishmsft
manager: AnnBe
ms.date: 10/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: EcoResCategorySearchList, EcoResAttribute, COODualUseCategories, EcoResProductCategory, EcoResCategoryAddProduct, EcoResAttributeValue
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: c7ed2ba5-87c6-4d99-9728-2a83e6d95ca9
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2017-09-01
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 95a4bac6beeaf5fad449027d93132fc1499288a0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5215488"
---
# <a name="manage-product-categories-and-products"></a>Gestire le categorie di prodotti e i prodotti

[!include [banner](./includes/banner.md)]

In questo argomento viene descritta una modalità avanzata per gestire le categorie di prodotti e i prodotti in Dynamics 365 Commerce. I miglioramenti consentono ai responsabili del merchandising di visualizzare una struttura di proprietà dei prodotti condivisa tra la gerarchia di prodotti e i dettagli dei prodotti rilasciati.

Per ulteriori informazioni su come gestire le categorie di prodotti, nell'area di lavoro **Gestione categorie e prodotti** selezionare il riquadro **Gerarchia di prodotti di Commerce**.

Notare la struttura avanzata della pagina **Gerarchia di prodotti di Commerce** che viene visualizzata. Nelle versioni precedenti dell'app, le proprietà di prodotto erano suddivise in *proprietà di prodotto di base* e *proprietà di prodotto al dettaglio*, a seconda dell'ambito di applicabilità. Le proprietà di prodotto al dettaglio sono *globali* nell'ambito dell'applicabilità. In altre parole, per una determinata proprietà di prodotto, lo stesso valore viene condiviso tra tutte le persone giuridiche. Le proprietà di prodotto di base sono invece *specifiche della persona giuridica*. In altre parole, per una determinata proprietà di prodotto di base il valore può differire tra le persone giuridiche, in base ai singoli requisiti aziendali di ogni persona giuridica.

Nella struttura avanzata di categorie di prodotti, le proprietà di prodotto sono separate in modo logico in base alla relativa applicabilità in un gruppo, per riflettere la struttura del modulo dei dettagli dei prodotti rilasciati.

![Raggruppamento dei campi in base all'ambito di applicabilità delle proprietà](media/NoticeGroupingOfFieldsBasedOnTheirScope.PNG)

È possibile passare dalla gestione di proprietà specifiche della persona giuridica in tutte le persone giuridiche alla gestione delle stesse per una specifica persona giuridica e viceversa.

Per visualizzare le proprietà in tutte le persone giuridiche, selezionare **Visualizza per tutte le persone giuridiche** (o **Modifica per tutte le persone giuridiche**).

![Visualizza/Modifica per tutte le persone giuridiche](media/ToggleBackToEditForSpecificLegalEntity.PNG)

Per gestire le proprietà di una persona giuridica specifica, selezionare **Visualizza per una specifica persona giuridica** (o **Modifica per una persona giuridica specifica**).

![Visualizza/Modifica per una specifica persona giuridica](media/ToggleToEditForAllLegalEntities.PNG)

Inoltre, nella struttura avanzata di categorie di prodotti, un responsabile del merchandising può ora definire valori predefiniti per un insieme di proprietà di prodotto aggiuntivo a livello di singola categoria. Quando i prodotti vengono creati, ereditano i valori predefiniti per le proprietà i prodotto, in base all'associazione di tali proprietà con una categoria individuale nella gerarchia di prodotti. Queste proprietà di prodotto ereditate possono anche essere modificate per ciascun prodotto allo scopo di soddisfare i requisiti aziendali.

## <a name="selecting-properties-to-update-products-on-the-commerce-product-hierarchy-page"></a>Selezione delle proprietà per aggiornare i prodotti nella pagina della categoria di prodotti di Commerce

È possibile utilizzare la nuova struttura avanzata per le proprietà di prodotto per selezionare quali proprietà di prodotto aggiornate devono essere distribuite ai prodotti associati. Nella pagina **Gerarchia di prodotti di Commerce**, nel Riquadro azioni, selezionare **Categoria**, quindi selezionare **Aggiorna prodotti** per aprire la finestra di dialogo **Aggiorna prodotti**.

![Finestra di dialogo Aggiorna prodotti](media/NewUpdateProductsEnhancedView.PNG)


[!INCLUDE[footer-include](../includes/footer-banner.md)]