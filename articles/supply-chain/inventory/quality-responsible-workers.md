---
title: Lavoratori responsabili dell'approvazione delle non conformità
description: Questo argomento descrive come configurare i lavoratori responsabili dell'approvazione delle non conformità.
author: rachel-profitt
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: raprofit
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2d3f647de2c188661c2c9c5f31e2642c3f8ca0b5
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021782"
---
# <a name="workers-responsible-for-approving-nonconformances"></a><span data-ttu-id="92ab2-103">Lavoratori responsabili dell'approvazione delle non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-103">Workers responsible for approving nonconformances</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="92ab2-104">Questo argomento descrive come configurare i lavoratori responsabili dell'approvazione delle non conformità.</span><span class="sxs-lookup"><span data-stu-id="92ab2-104">This topic describes how to configure workers that are responsible for approving nonconformances.</span></span>

<span data-ttu-id="92ab2-105">Le non conformità devono essere approvate prima che gli utenti possano iniziare a inserire dettagli come correzioni o operazioni.</span><span class="sxs-lookup"><span data-stu-id="92ab2-105">Nonconformances must be approved before users can start to enter details such as corrections or operations.</span></span> <span data-ttu-id="92ab2-106">Prima che gli utenti possano approvare o respingere le non conformità, il loro ID utente (record utente) deve essere collegato a un record lavoratore.</span><span class="sxs-lookup"><span data-stu-id="92ab2-106">Before users can approve or reject nonconformances, their user ID (user record) must be linked to a worker record.</span></span> <span data-ttu-id="92ab2-107">Facoltativamente, puoi configurare i lavoratori responsabili della qualità e quindi consentire a un lavoratore di approvare il lavoro per conto di un altro lavoratore.</span><span class="sxs-lookup"><span data-stu-id="92ab2-107">You can optionally configure workers that are responsible for quality and then allow one worker to approve work on behalf of another worker.</span></span>

## <a name="enable-a-user-for-nonconformance-processing"></a><span data-ttu-id="92ab2-108">Abilitare un utente per l'elaborazione di non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-108">Enable a user for nonconformance processing</span></span>

<span data-ttu-id="92ab2-109">Prima che un utente possa approvare o respingere le non conformità, devi collegare il suo record utente a un record lavoratore.</span><span class="sxs-lookup"><span data-stu-id="92ab2-109">Before a user can approve or reject nonconformances, you must link their user record to a worker record.</span></span> <span data-ttu-id="92ab2-110">I campi di approvazione possono quindi essere impostati automaticamente e l'utente corrente può essere compilato automaticamente per il foglio presenze.</span><span class="sxs-lookup"><span data-stu-id="92ab2-110">The approval fields can then be automatically set, and the current user can be automatically filled in for the timesheet.</span></span> <span data-ttu-id="92ab2-111">Prima che l'utente possa utilizzare le note del documento, devi attivare la Gestione documenti nelle sue opzioni utente.</span><span class="sxs-lookup"><span data-stu-id="92ab2-111">Before the user can use the document notes, you must activate document handling in their user options.</span></span>

1. <span data-ttu-id="92ab2-112">Selezionare **Amministrazione sistema \> Utenti \> Utenti**.</span><span class="sxs-lookup"><span data-stu-id="92ab2-112">Go to **System administration \> Users \> Users**.</span></span>
1. <span data-ttu-id="92ab2-113">Trova e apri l'utente che dovrebbe essere in grado di approvare o respingere le non conformità.</span><span class="sxs-lookup"><span data-stu-id="92ab2-113">Find and open the user who should be able to approve or reject nonconformances.</span></span>
1. <span data-ttu-id="92ab2-114">Imposta il campo **Persona** sul nome del lavoratore correlato al record utente corrente.</span><span class="sxs-lookup"><span data-stu-id="92ab2-114">Set the **Person** field to the name of the worker that is related to the current user record.</span></span>
1. <span data-ttu-id="92ab2-115">Nel riquadro azioni selezionare **Opzioni utente**.</span><span class="sxs-lookup"><span data-stu-id="92ab2-115">On the Action Pane, select **User options**.</span></span>
1. <span data-ttu-id="92ab2-116">Nella pagina **Opzioni** per il record utente corrente, nella scheda **Preferenze**, impostare l'opzione **Attiva gestione documenti** su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="92ab2-116">On the **Options** page for the current user record, on the **Preferences** tab, set the **Enable document handling** option to *Yes*.</span></span>
1. <span data-ttu-id="92ab2-117">Chiudere le pagine.</span><span class="sxs-lookup"><span data-stu-id="92ab2-117">Close the pages.</span></span>

## <a name="define-workers-that-are-responsible-for-quality"></a><span data-ttu-id="92ab2-118">Definire i lavoratori responsabili della qualità</span><span class="sxs-lookup"><span data-stu-id="92ab2-118">Define workers that are responsible for quality</span></span>

1. <span data-ttu-id="92ab2-119">Andare a **Gestione inventario \> Impostazione \> Controllo qualità \> Lavoratori responsabili della qualità**.</span><span class="sxs-lookup"><span data-stu-id="92ab2-119">Go to **Inventory management \> Setup \> Quality control \> Workers responsible for quality**.</span></span>
2. <span data-ttu-id="92ab2-120">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="92ab2-120">On the Action Pane, select **New**.</span></span>
3. <span data-ttu-id="92ab2-121">Nel campo **Lavoratore** selezionare il lavoratore che inserisce i dati sulla qualità.</span><span class="sxs-lookup"><span data-stu-id="92ab2-121">In the **Worker** field, select the worker that enters quality data.</span></span>
4. <span data-ttu-id="92ab2-122">Nel campo **Lavoratore responsabile** selezionare il lavoratore per conto del quale il lavoratore selezionato inserisce il lavoro.</span><span class="sxs-lookup"><span data-stu-id="92ab2-122">In the **Worker responsible** field, select the worker that the selected worker enters work on behalf of.</span></span> <span data-ttu-id="92ab2-123">Quando vengono create e aggiornate le non conformità, questo lavoratore verrà inserito per impostazione predefinita nei campi **Lavoratore**.</span><span class="sxs-lookup"><span data-stu-id="92ab2-123">When nonconformances are created and updated, this worker will be entered by default in **Worker** fields.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="92ab2-124">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="92ab2-124">Additional resources</span></span>

- [<span data-ttu-id="92ab2-125">Panoramica gestione qualità</span><span class="sxs-lookup"><span data-stu-id="92ab2-125">Quality management overview</span></span>](quality-management-processes.md)
- [<span data-ttu-id="92ab2-126">Abilitare la gestione della qualità e della non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-126">Enable quality and nonconformance management</span></span>](enable-quality-management.md)
- [<span data-ttu-id="92ab2-127">Spese gestione qualità</span><span class="sxs-lookup"><span data-stu-id="92ab2-127">Quality charges</span></span>](quality-charges.md)
- [<span data-ttu-id="92ab2-128">Aree di quarantena per non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-128">Quarantine zones for nonconformances</span></span>](quality-quarantine-zones.md)
- [<span data-ttu-id="92ab2-129">Tipi di diagnostica per non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-129">Diagnostic types for nonconformances</span></span>](quality-diagnostic-types.md)
- [<span data-ttu-id="92ab2-130">Spese di gestione qualità per non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-130">Quality charges for nonconformances</span></span>](quality-charges.md)
- [<span data-ttu-id="92ab2-131">Operazioni per non conformità</span><span class="sxs-lookup"><span data-stu-id="92ab2-131">Operations for nonconformances</span></span>](quality-operations.md)
- [<span data-ttu-id="92ab2-132">Gestione qualità per i processi di magazzino</span><span class="sxs-lookup"><span data-stu-id="92ab2-132">Quality management for warehouse processes</span></span>](quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
