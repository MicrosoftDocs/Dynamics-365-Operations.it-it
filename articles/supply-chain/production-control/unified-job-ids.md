---
title: Sequenza numerica unificata per gli ID processo
description: Questa funzione fornisce un'unica sequenza numerica unificata che genera ID processo per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze.
author: johanhoffmann
ms.date: 03/25/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 00212803c46d898a39eafbc5c62016eb829535e2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824944"
---
# <a name="unified-number-sequence-for-job-ids"></a><span data-ttu-id="17126-103">Sequenza numerica unificata per gli ID processo</span><span class="sxs-lookup"><span data-stu-id="17126-103">Unified number sequence for job IDs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="17126-104">Questa funzione fornisce un'unica sequenza numerica unificata che genera ID processo per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze.</span><span class="sxs-lookup"><span data-stu-id="17126-104">This feature provides a single, unified number sequence that generates job IDs for the Production control, Manufacturing execution, and Time and attendance modules.</span></span> <span data-ttu-id="17126-105">In precedenza, era possibile scegliere una sequenza numerica diversa per ciascuno di questi moduli, il che poteva generare ID processo in conflitto se due o più di queste sequenze utilizzavano un formato identico.</span><span class="sxs-lookup"><span data-stu-id="17126-105">Previously, you were able to choose a different number sequence for each of these modules, which could result in conflicting job IDs if two or more of these sequences used an identical format.</span></span> <span data-ttu-id="17126-106">Un tale conflitto può causare il danneggiamento dei dati.</span><span class="sxs-lookup"><span data-stu-id="17126-106">Such a conflict can cause data corruption.</span></span>

## <a name="turn-on-this-feature-for-your-system"></a><span data-ttu-id="17126-107">Attivare questa funzionalità per il sistema</span><span class="sxs-lookup"><span data-stu-id="17126-107">Turn on this feature for your system</span></span>

<span data-ttu-id="17126-108">Se il sistema in uso non include già la funzione descritta in questo argomento, vedi [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attiva la funzionalità *Sequenza numerica unificata per ID processo*.</span><span class="sxs-lookup"><span data-stu-id="17126-108">If your system doesn't already include the feature described in this topic, go to [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) and turn on the *Unified number sequence for job IDs* feature.</span></span>

## <a name="set-up-the-unified-number-sequence-for-job-ids"></a><span data-ttu-id="17126-109">Impostare la sequenza numerica per gli ID processo</span><span class="sxs-lookup"><span data-stu-id="17126-109">Set up the unified number sequence for job IDs</span></span>

<span data-ttu-id="17126-110">Dopo aver abilitato questa funzione, le impostazioni della sequenza numerica **identificazione del processo** esistenti nelle pagine dei parametri per i moduli Controllo produzione, Esecuzione produzione e Orario e presenze saranno obsolete e verrà aggiunto il nuovo campo **ID processo unificato**.</span><span class="sxs-lookup"><span data-stu-id="17126-110">After enabling this feature, the existing **Job identification** number-sequence settings located on the parameters pages for the Production control, Manufacturing execution, and Time and attendance modules will be deprecated and a new **Unified job ID** field will be added.</span></span> <span data-ttu-id="17126-111">Il valore **ID processo unificato** è condiviso da tutti e tre i moduli, assicurando così che tutti i moduli facciano riferimento alla stessa sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="17126-111">The **Unified job ID** value is shared by all three modules, thus ensuring that all modules reference the same number sequence.</span></span> <span data-ttu-id="17126-112">Gli ID processo saranno quindi univoci in tutti e tre i moduli e non si verificherà mai un conflitto.</span><span class="sxs-lookup"><span data-stu-id="17126-112">Job IDs will therefore be unique across all three modules and a conflict will never occur.</span></span>

<span data-ttu-id="17126-113">Per impostare la sequenza numerica per gli ID processo:</span><span class="sxs-lookup"><span data-stu-id="17126-113">To set up the unified number sequence for job IDs:</span></span>

1. <span data-ttu-id="17126-114">Attiva la funzione come descritto nella sezione precedente.</span><span class="sxs-lookup"><span data-stu-id="17126-114">Turn on the feature as described in the previous section.</span></span>
1. <span data-ttu-id="17126-115">Identifica la sequenza numerica che desideri utilizzare per gli ID processo unificati o creane una nuova.</span><span class="sxs-lookup"><span data-stu-id="17126-115">Either identify the number sequence you want to use for your unified job IDs, or create a new one.</span></span> <span data-ttu-id="17126-116">Per ulteriori informazioni, vedere [Panoramica delle sequenze numeriche](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span><span class="sxs-lookup"><span data-stu-id="17126-116">For more information, see [Number sequences overview](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md).</span></span>
1. <span data-ttu-id="17126-117">Vai allla pagina **Parametri di controllo produzione**, **Parametri di esecuzione produzione**, o **Parametri di orario e presenze**.</span><span class="sxs-lookup"><span data-stu-id="17126-117">Go to the **Production control parameters**, **Manufacturing execution parameters**, or **Time and attendance parameters** page.</span></span> <span data-ttu-id="17126-118">Non importa quale scegli perché quando effettui questa impostazione su una di quelle pagine, tutte le altre pagine si aggiorneranno automaticamente.</span><span class="sxs-lookup"><span data-stu-id="17126-118">It doesn't matter which one you choose because when you make this setting on any of those pages, all of the other pages will update automatically.</span></span>
1. <span data-ttu-id="17126-119">Apri la scheda **Sequenze numeriche** nella pagina dei parametri selezionata.</span><span class="sxs-lookup"><span data-stu-id="17126-119">Open the **Number sequences** tab on your selected parameters page.</span></span>
1. <span data-ttu-id="17126-120">Assegna il **Codice di sequenza numerica** che hai identificato in precedenza alla riga **ID processo unificati** della griglia.</span><span class="sxs-lookup"><span data-stu-id="17126-120">Assign the **Number sequence code** that you identified previously to the **Unified job IDs** row of the grid.</span></span>
