--- 
title: Cross-docking di prodotti da magazzino ricevente a punti vendita
description: "In questa procedura vengono descritti i passaggi per creare ed elaborare un cross-docking per distribuire i prodotti dall'ubicazione di ricevimento di un ordine fornitore a uno o più punti vendita."
author: BibiSp
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: daa42bb83d6b988e8fd18db6ad8386c67fd3e6e5
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Cross-docking di prodotti da magazzino ricevente a punti vendita

[!include [task guide banner](../../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare ed elaborare un cross-docking per distribuire i prodotti dall'ubicazione di ricevimento di un ordine fornitore a uno o più punti vendita. L'utente può definire più configurazioni e seguire i suggerimenti del sistema per distribuire i prodotti oppure immettere manualmente i punti vendita a cui i prodotti vengono distribuiti e la quantità distribuita a ogni punto vendita. La procedura non include l'impostazione dei dati che possono essere utilizzati nel cross-docking, ad esempio le regole di rifornimento, le gerarchie organizzative e i pesi dei punti vendita. La procedura utilizza la società dimostrativa USRT.

1. Fare clic su Tutti gli ordini fornitore.
2. Selezionare l'ordine fornitore nell'elenco e fare clic sul collegamento per aprire l'ordine.
3. Nel riquadro azioni, fare clic su Vendita al dettaglio.
4. Fare clic su Cross-docking.
5. Fare clic su Modifica.
    * La categoria può essere utilizzata per filtrare gli articoli nella sezione Righe.  
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nel campo Quantità cross-docking, immettere un valore per specificare la quantità acquistata del prodotto selezionato che deve essere distribuita.
8. Nel campo Quantità cross-docking aggiuntiva, immettere un valore per specificare le quantità da distribuire per i prodotti disponibili acquistati
9. Nel campo Distribuzione, immettere 'Peso ubicazione'.
    * È possibile selezionare gli altri tipi per utilizzare regole diverse per la distribuzione.  
10. Nel campo Gerarchia di rifornimenti immettere o selezionare un valore.
11. Selezionare Sì nel campo Rispetta assortimento.
12. Fare clic su Calcola quantità.
13. Fare clic su Crea ordine.
14. Fare clic su Sì.
15. Nell'elenco, individuare e selezionare il magazzino di ricezione dei prodotti
16. Fare clic su Ordine per visualizzare gli ordini creati per il magazzino selezionato


