---
title: " Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push"
description: In questa procedura vengono descritti i passaggi per creare ed elaborare una distribuzione push da un'ubicazione a uno o più punti vendita.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3720945823cf127f776a9ea6a6ad75a72ceec00c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5012343"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a> Inviare i prodotti del centro di distribuzione al punto vendita utilizzando la distribuzione push

[!include [banner](../includes/banner.md)]

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]