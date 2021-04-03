---
title: Aggiornare costi standard in un ambiente di produzione
description: Questo articolo fornisce indicazioni su come aggiornare i costi standard in un ambiente di produzione.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom: 79663
ms.assetid: 3a7c3d13-8dbc-442d-a281-ac0ebe99ec83
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 726eccdc8a9350a292ba719784b5db99afdfad4f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5262431"
---
# <a name="update-standard-costs-in-a-manufacturing-environment"></a><span data-ttu-id="5141d-103">Aggiornare costi standard in un ambiente di produzione</span><span class="sxs-lookup"><span data-stu-id="5141d-103">Update standard costs in a manufacturing environment</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5141d-104">Questo articolo fornisce indicazioni su come aggiornare i costi standard in un ambiente di produzione.</span><span class="sxs-lookup"><span data-stu-id="5141d-104">This article provides guidance about how to update standard costs in a manufacturing environment.</span></span> 

<span data-ttu-id="5141d-105">Gli aggiornamenti possono riflettere nuovi articoli, categorie di costi o formule di calcolo dei costi indiretti.</span><span class="sxs-lookup"><span data-stu-id="5141d-105">Updates can reflect new items, cost categories, or indirect cost calculation formulas.</span></span> <span data-ttu-id="5141d-106">Possono anche riflettere le correzioni e le variazioni di costo.</span><span class="sxs-lookup"><span data-stu-id="5141d-106">They can also reflect corrections and cost changes.</span></span> <span data-ttu-id="5141d-107">Le operazioni da completare per l'aggiornamento dei costi standard dipendono dal tipo di aggiornamento, come illustrato nei casi descritti di seguito;</span><span class="sxs-lookup"><span data-stu-id="5141d-107">The type of update affects the steps that you must complete to update standard costs, as illustrated in the following cases:</span></span>

-   <span data-ttu-id="5141d-108">Immettere le variazioni dei costi standard previste per gli articoli acquistati, quindi cambiare lo stato dei record dei costi degli articoli in **Attivo** alla data appropriata.</span><span class="sxs-lookup"><span data-stu-id="5141d-108">Enter expected standard cost changes for purchased items, and then change the status of the item cost records to **Active** on the appropriate date.</span></span> <span data-ttu-id="5141d-109">Non ricalcolare tuttavia i costi degli articoli prodotti in cui vengono utilizzati gli articoli acquistati.</span><span class="sxs-lookup"><span data-stu-id="5141d-109">However, don't recalculate the costs of manufactured items that use the purchased items.</span></span>
-   <span data-ttu-id="5141d-110">Immettere i costi standard per un nuovo articolo acquistato, ma non ricalcolare i costi degli articoli prodotti con una versione distinta base (DBA) contenente come componente il nuovo articolo acquistato.</span><span class="sxs-lookup"><span data-stu-id="5141d-110">Enter standard costs for a new purchased item, but don't recalculate the costs of manufactured items that have a bill of materials (BOM) version that contains the new purchased item as a component.</span></span>
-   <span data-ttu-id="5141d-111">Correggere o modificare il costo di un articolo acquistato oppure cambiare il gruppo di costi assegnato a un articolo acquistato, quindi calcolare il costo di tutti gli articoli prodotti che hanno una versione DBA contenente come componente l'articolo acquistato.</span><span class="sxs-lookup"><span data-stu-id="5141d-111">Correct or change the cost of a purchased item, or change the cost group that is assigned to a purchased item, and calculate the cost for all manufactured items that have a BOM version that contains the purchased item as a component.</span></span>
-   <span data-ttu-id="5141d-112">Cambiare il costo per una categoria di costi e calcolare il costo di tutti gli articoli prodotti che hanno una versione del ciclo di lavorazione contenente operazioni del ciclo di lavorazione in cui viene utilizzata la categoria di costi.</span><span class="sxs-lookup"><span data-stu-id="5141d-112">Change the cost for a cost category, and calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="5141d-113">Modificare le categorie di costi assegnate alle operazioni del ciclo di lavorazione o il gruppo di costi assegnato alle categorie di costi.</span><span class="sxs-lookup"><span data-stu-id="5141d-113">Change the cost categories that are assigned to routing operations or the cost group that is assigned to cost categories.</span></span> <span data-ttu-id="5141d-114">Calcolare quindi il costo di tutti gli articoli prodotti che hanno una versione del ciclo di lavorazione contenente operazioni del ciclo di lavorazione in cui viene utilizzata la categoria di costi.</span><span class="sxs-lookup"><span data-stu-id="5141d-114">Then calculate the cost for all manufactured items that have a route version that contains routing operations that use the cost category.</span></span>
-   <span data-ttu-id="5141d-115">Modificare la formula di calcolo di un costo indiretto, quindi calcolare il costo di tutti gli articoli prodotti interessati dalla modifica.</span><span class="sxs-lookup"><span data-stu-id="5141d-115">Change an indirect cost calculation formula, and calculate the cost for all manufactured items that are affected by the change.</span></span>
-   <span data-ttu-id="5141d-116">Modificare o aggiungere un sito di fabbricazione per un articolo prodotto, quindi calcolare il costo di produzione dell'articolo per tale sito.</span><span class="sxs-lookup"><span data-stu-id="5141d-116">Change or add a manufacturing site for a manufactured item, and calculate the item's manufactured cost for the site.</span></span>
-   <span data-ttu-id="5141d-117">Calcolare o ricalcolare il costo di un articolo prodotto, quindi ricalcolare il costo di tutti gli articoli prodotti che hanno una versione DBA contenente come componente l'articolo prodotto.</span><span class="sxs-lookup"><span data-stu-id="5141d-117">Calculate, or recalculate, the cost for a manufactured item, and recalculate the cost for all manufactured items that have a BOM version that contains the manufactured item as a component.</span></span>
-   <span data-ttu-id="5141d-118">Calcolare i costi di un nuovo articolo prodotto in base alle informazioni sui cicli di lavorazione e sulla DBA definita, approvata e attiva.</span><span class="sxs-lookup"><span data-stu-id="5141d-118">Calculate costs for a new manufactured item, based on its defined, approved, and active BOM and route information.</span></span>

<span data-ttu-id="5141d-119">In ciascun caso è necessario valutare con attenzione come aggiornare i costi standard.</span><span class="sxs-lookup"><span data-stu-id="5141d-119">Each case requires careful consideration about how to update standard costs.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]