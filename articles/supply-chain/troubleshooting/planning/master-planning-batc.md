---
title: Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato
description: Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ilebedev
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: fa0b614b6710c65811add8725a0e255ce2c34b88
ms.sourcegitcommit: 3c15a26e9708adc9a75082dc551f0a3a0a7d89f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049475"
---
# <a name="you-cant-filter-master-planning-items-by-their-related-coverage-group-values"></a><span data-ttu-id="66272-103">Non è possibile filtrare gli elementi di pianificazione generale in base ai valori del gruppo di copertura correlato</span><span class="sxs-lookup"><span data-stu-id="66272-103">You can't filter master planning items by their related coverage group values</span></span>

<span data-ttu-id="66272-104">Numero KB: 4612572</span><span class="sxs-lookup"><span data-stu-id="66272-104">KB number: 4612572</span></span>

## <a name="symptoms"></a><span data-ttu-id="66272-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="66272-105">Symptoms</span></span>

<span data-ttu-id="66272-106">Vuoi filtrare gli articoli che verranno inclusi in un processo batch di pianificazione principale, in base ai valori dei record correlati dalla tabella di copertura articolo.</span><span class="sxs-lookup"><span data-stu-id="66272-106">You want to filter the items that will be included in a master planning batch job, based on the values of related records from the item coverage table.</span></span> <span data-ttu-id="66272-107">(Ad esempio, vuoi filtrare gli elementi in base al loro valore **Fornitore** e/o **Gruppo di copertura**).</span><span class="sxs-lookup"><span data-stu-id="66272-107">(For example, you want to filter items by their **Vendor** and/or **Coverage group** value).</span></span> <span data-ttu-id="66272-108">La configurazione del filtro per il processo batch consente di creare un join dalla tabella **Articoli** alla tabella **Copertura dell'articolo**, quindi specificare i valori dei campi dalla tabella di copertura articoli nella query.</span><span class="sxs-lookup"><span data-stu-id="66272-108">The filter setup for the batch job lets you create a join from the **Items** table to the **Item coverage** table, and then specify field values from the item coverage table in your query.</span></span> <span data-ttu-id="66272-109">Tuttavia, dopo aver completato questa configurazione, il sistema crea comunque ordini pianificati per l'intera copertura articolo, non solo per gli articoli che corrispondono ai valori di campo specificati dalla tabella di copertura articolo.</span><span class="sxs-lookup"><span data-stu-id="66272-109">However, after you complete this setup, the system still creates planned orders for the whole item coverage, not just for the items that match the specified field values from the item coverage table.</span></span>

## <a name="resolution"></a><span data-ttu-id="66272-110">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="66272-110">Resolution</span></span>

<span data-ttu-id="66272-111">Il filtro del processo batch può filtrare solo sugli elementi.</span><span class="sxs-lookup"><span data-stu-id="66272-111">The batch job filter can filter only on items.</span></span> <span data-ttu-id="66272-112">Sebbene tu possa aggiungere un join alla tabella **Copertura dell'articolo**, le impostazioni di filtro effettuate su quella tabella non influiranno sull'output della query.</span><span class="sxs-lookup"><span data-stu-id="66272-112">Although you can add a join to the **Item coverage** table, filter settings that you make against that table won't affect the query output.</span></span> <span data-ttu-id="66272-113">In fase di esecuzione, il sistema esegue la pianificazione per tutti i gruppi di copertura e tutte le varianti di cui dispongono gli articoli filtrati.</span><span class="sxs-lookup"><span data-stu-id="66272-113">At runtime, the system runs planning for all the coverage groups and all the variations that the filtered items have.</span></span> <span data-ttu-id="66272-114">Dopo che un articolo è già stato incluso nell'esecuzione, eventuali gruppi di copertura inclusi nel filtro articolo non influiranno sull'output della pianificazione.</span><span class="sxs-lookup"><span data-stu-id="66272-114">After an item is already included in the run, any coverage groups that are included in the item filter a won't affect the planning output.</span></span>
