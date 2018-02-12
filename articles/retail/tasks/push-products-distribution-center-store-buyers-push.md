--- 
title: " Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push"
description: "In questa procedura vengono descritti i passaggi per creare ed elaborare una distribuzione push da un'ubicazione a uno o più punti vendita."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dce0016ede691a70a6eb1bf3240fa595efec0241
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a> Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push

[!include[task guide banner](../includes/task-guide-banner.md)]

In questa procedura vengono descritti i passaggi per creare ed elaborare una distribuzione push da un'ubicazione a uno o più punti vendita. L'utente può definire più configurazioni e seguire i suggerimenti del sistema per distribuire i prodotti oppure immettere manualmente i punti vendita a cui i prodotti vengono distribuiti e la quantità distribuita a ogni punto vendita. La procedura non include l'impostazione dei dati che possono essere utilizzati nella distribuzione push, ad esempio le regole di rifornimento, le gerarchie organizzative e i pesi dei punti vendita. Questa procedura utilizza la società dimostrativa USRT.

1. Passare a Distribuzione push.
2. Fare clic su Nuovo.
3. Nel campo Descrizione digitare un valore.
4. Nel campo Sito immettere o selezionare un valore.
5. Nel campo Magazzino, immettere o selezionare un magazzino con prodotti con quantità disponibili.
6. Scegliere Aggiungi.
7. Nell'elenco contrassegnare la riga selezionata.
8. Nel campo Numero articolo immettere o selezionare un prodotto.
9. Scegliere Aggiungi.
10. Nell'elenco contrassegnare la riga selezionata.
11. Nel campo Numero articolo immettere o selezionare un prodotto variante.
    * Quando si immette un prodotto variante, le righe vengono create per ogni variante.  
12. Nell'elenco selezionare una riga.
13. Nel campo Quantità inviata con distribuzione push, immettere la quantità del prodotto selezionato che si desidera distribuire.
14. Nel campo Quantità aggiuntiva da distribuire, immettere la quantità di prodotti con quantità disponibile da distribuire.
15. Nel campo Distribuzione, immettere 'Peso ubicazione'.
    * È possibile selezionare gli altri tipi per utilizzare altre regole per la distribuzione.  
16. Nel campo Gerarchia di rifornimenti immettere o selezionare un valore.
17. Selezionare Sì nel campo Rispetta assortimento.
18. Fare clic Calcola quantità e rivedere le quantità aggiunte alle righe nella sezione Magazzino.
19. Fare clic su Crea ordine.
20. Fare clic su Sì.


