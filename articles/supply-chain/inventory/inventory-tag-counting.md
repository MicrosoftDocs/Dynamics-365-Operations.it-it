---
title: Conteggio tag scorte
description: Questo articolo fornisce informazioni sul conteggio dei tag, utilizzato per confrontare l'effettivo contenuto di un magazzino con le scorte disponibili.
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCountTag
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 11594
ms.assetid: 03772d0e-5c37-454c-ab85-82bc8b60a76d
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dff899d0e6d94287c0f1924fe1787189d79c09f4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1570836"
---
# <a name="inventory-tag-counting"></a><span data-ttu-id="48103-103">Conteggio tag scorte</span><span class="sxs-lookup"><span data-stu-id="48103-103">Inventory tag counting</span></span>

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

<span data-ttu-id="48103-104">Questo articolo fornisce informazioni sul conteggio dei tag, utilizzato per confrontare l'effettivo contenuto di un magazzino con le scorte disponibili.</span><span class="sxs-lookup"><span data-stu-id="48103-104">This article provides information about tag counting, which you use to compare the actual contents of a warehouse with the on-hand inventory.</span></span>

<span data-ttu-id="48103-105">La creazione di righe nella pagina **Conteggio tag** consente di inserire un numero tag su ogni articolo di magazzino, ad esempio un numero da 1 a 500.</span><span class="sxs-lookup"><span data-stu-id="48103-105">By creating lines on the **Tag counting** page, you place a tag number on each inventory item, such as a number from 1 to 500.</span></span> <span data-ttu-id="48103-106">Durante il conteggio, si immette il numero di articolo e la quantità su un tag corrispondente.</span><span class="sxs-lookup"><span data-stu-id="48103-106">During the count, you enter the item number and the quantity on a corresponding tag.</span></span> <span data-ttu-id="48103-107">Il tag può quindi essere utilizzato come base per l'inserimento nel giornale di registrazione del conteggio tag.</span><span class="sxs-lookup"><span data-stu-id="48103-107">This tag can then be used as the basis for input in the tag counting journal.</span></span> <span data-ttu-id="48103-108">Dopo la registrazione del giornale di registrazione del conteggio tag viene creato un nuovo giornale di registrazione del conteggio nella pagina **Conteggio**.</span><span class="sxs-lookup"><span data-stu-id="48103-108">After you post the tag counting journal, a new counting journal is created on the **Counting** page.</span></span> <span data-ttu-id="48103-109">Il nuovo giornale di registrazione si basa sulle righe del giornale di registrazione del conteggio tag creato.</span><span class="sxs-lookup"><span data-stu-id="48103-109">The new journal is based on the tag counting journal lines that you created.</span></span> <span data-ttu-id="48103-110">Per il conteggio tag degli articoli di una dimensione inventariale specifica selezionare la dimensione nella pagina **Visualizza dimensioni** che appare quando si crea il giornale di registrazione del conteggio tag.</span><span class="sxs-lookup"><span data-stu-id="48103-110">To tag-count items by a specific inventory dimension, select the dimension on the **Display dimension** page that is displayed when you create the tag counting journal.</span></span> <span data-ttu-id="48103-111">Ad esempio, per conteggiare gli articoli in un magazzino specifico, selezionare la casella di controllo **Magazzino**.</span><span class="sxs-lookup"><span data-stu-id="48103-111">For example, to count items in a specific warehouse, select the **Warehouse** check box.</span></span> <span data-ttu-id="48103-112">Se il dispositivo **Blocca articoli durante il conteggio** nella pagina **Parametri di gestione inventario e magazzino** è selezionato, gli articoli non possono essere aggiornati fisicamente durante il conteggio.</span><span class="sxs-lookup"><span data-stu-id="48103-112">If the **Lock items during count** slider on the **Inventory and warehouse management parameters** page is selected, items can't be physically updated during counting.</span></span> <span data-ttu-id="48103-113">Tuttavia, gli articoli nei giornali di registrazione del conteggio tag non sono bloccati durante il conteggio.</span><span class="sxs-lookup"><span data-stu-id="48103-113">However, items in tag counting journals aren't locked during counting.</span></span> <span data-ttu-id="48103-114">Le operazioni di magazzino non vengono create fino a quando le righe del conteggio tag non vengono registrate e trasferite a un giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="48103-114">Inventory transactions aren't created until the tag counting lines are posted and transferred to a counting journal.</span></span> <span data-ttu-id="48103-115">Se i tag vengono immessi casualmente e si desidera visualizzare quelli mancanti, fare clic sull'intestazione della colonna **Tag** per ordinare le righe in base al tag.</span><span class="sxs-lookup"><span data-stu-id="48103-115">If tags are entered randomly, and you want to identify missing tags, click the **Tag** column header to sort the lines by tag.</span></span>

<a name="additional-resources"></a><span data-ttu-id="48103-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="48103-116">Additional resources</span></span>
--------

[<span data-ttu-id="48103-117">Conteggio ciclo</span><span class="sxs-lookup"><span data-stu-id="48103-117">Cycle counting</span></span>](../warehousing/cycle-counting.md)
