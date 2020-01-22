---
title: Abilitare il calcolo IVA differito nei giornali di registrazione
description: In questo argomento viene descritto come attivare la funzionalità del calcolo IVA differito per migliorare le prestazioni di calcolo dell'IVA quando il numero delle righe del giornale di registrazione è molto elevato.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: ed8e5f930bbb6b0fb570ba1eb23c0816210c1814
ms.sourcegitcommit: bfd6142569196a060e3f37893c78f00c40a2a18c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946168"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a><span data-ttu-id="fad1e-103">Abilitare il calcolo IVA differito nei giornali di registrazione</span><span class="sxs-lookup"><span data-stu-id="fad1e-103">Enable delayed tax calculation on journals</span></span>
[!include [banner](../includes/banner.md)]


<span data-ttu-id="fad1e-104">In questo argomento viene descritto come è possibile effettuare il calcolo IVA dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-104">This topic explains how you can delay sales tax calculation on journals.</span></span> <span data-ttu-id="fad1e-105">Questa funzionalità consente di migliorare le prestazioni dei calcoli IVA quando sono presenti molte righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-105">This capability helps improve the performance of tax calculations when there are many journal lines.</span></span>

<span data-ttu-id="fad1e-106">Per impostazione predefinita, gli importi IVA nelle righe del giornale di registrazione vengono calcolati quando i campi relativi all'IVA vengono aggiornati.</span><span class="sxs-lookup"><span data-stu-id="fad1e-106">By default, sales tax amounts on journal lines are calculated whenever tax-related fields are updated.</span></span> <span data-ttu-id="fad1e-107">Tra questi campi sono inclusi i campi delle fasce IVA e delle fasce IVA articoli.</span><span class="sxs-lookup"><span data-stu-id="fad1e-107">These fields include the fields for sales tax groups and item sales tax groups.</span></span> <span data-ttu-id="fad1e-108">Qualsiasi aggiornamento a una riga del giornale di registrazione comporta il ricalcolo degli importi IVA per tutte le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-108">Any update to a journal line causes tax amounts to be recalculated for all journal lines.</span></span> <span data-ttu-id="fad1e-109">Sebbene questo comportamento aiuti l'utente a visualizzare gli importi IVA calcolati in tempo reale, può anche influire sulle prestazioni se il numero di righe del giornale di registrazione è molto elevato.</span><span class="sxs-lookup"><span data-stu-id="fad1e-109">Although this behavior helps user see tax amounts calculated in real time, it can also affect performance if the number of journal lines is very large.</span></span>

<span data-ttu-id="fad1e-110">La funzionalità Calcolo IVA differito consente di posticipare il calcolo IVA nei giornali di registrazione e in modo da ovviare ai problemi relativi alle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fad1e-110">The Delayed tax calculation feature lets you delay tax calculation on journals and therefore helps fix performance issues.</span></span> <span data-ttu-id="fad1e-111">Quando questa funzionalità è attivata, gli importi IVA vengono calcolati solo quando un utente seleziona **IVA** o registra il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-111">When this feature is turned on, tax amounts are calculated only when a user selects **Sales Tax** or posts the journal.</span></span>

<span data-ttu-id="fad1e-112">È possibile ritardare il calcolo dell'IVA a tre livelli:</span><span class="sxs-lookup"><span data-stu-id="fad1e-112">You can delay the calculation of sales taxes at three levels:</span></span>

- <span data-ttu-id="fad1e-113">Persona giuridica</span><span class="sxs-lookup"><span data-stu-id="fad1e-113">Legal entity</span></span>
- <span data-ttu-id="fad1e-114">Nome giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fad1e-114">Journal name</span></span>
- <span data-ttu-id="fad1e-115">Intestazione giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fad1e-115">Journal header</span></span>

<span data-ttu-id="fad1e-116">Il sistema assegna la priorità all'impostazione dell'intestazione del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-116">The system gives priority to the setting for the journal header.</span></span> <span data-ttu-id="fad1e-117">Per impostazione predefinita, questa impostazione viene ricavata dal nome del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-117">By default, this setting is taken from the journal name.</span></span> <span data-ttu-id="fad1e-118">Per impostazione predefinita, l'impostazione del nome del giornale di registrazione viene ricavata dall'impostazione della pagina **Parametri di contabilità generale** quando il nome del giornale di registrazione viene creato.</span><span class="sxs-lookup"><span data-stu-id="fad1e-118">By default, the setting for the journal name is taken from the setting on the **General ledger parameters** page when the journal name is created.</span></span> <span data-ttu-id="fad1e-119">Nelle seguenti sezioni viene descritto come abilitare il calcolo IVA differito per le persone giuridiche, i nomi dei giornali di registrazione e le intestazioni dei giornali di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-119">The following sections explain how to turn on delayed tax calculation for legal entities, journal names, and journal headers.</span></span>

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a><span data-ttu-id="fad1e-120">Attivare il calcolo IVA differito a livello di persona giuridica</span><span class="sxs-lookup"><span data-stu-id="fad1e-120">Turn on delayed tax calculation at the legal entity level</span></span>

1. <span data-ttu-id="fad1e-121">Passare a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-121">Go to **General ledger \> Ledger setup \> General ledger parameters**.</span></span>
2. <span data-ttu-id="fad1e-122">Nella scheda **IVA**, nella scheda dettaglio **Generale**, impostare l'opzione **Calcolo IVA differito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-122">On the **Sales tax** tab, on the **General** FastTab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Immagine dei parametri di contabilità generale](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a><span data-ttu-id="fad1e-124">Attivare il calcolo IVA differito a livello di nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fad1e-124">Turn on delayed tax calculation at the journal name level</span></span>

1. <span data-ttu-id="fad1e-125">Passare a **Contabilità generale \> Impostazione giornale di registrazione \> Nomi giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-125">Go to **General ledger \> Journal setup \> Journal names**.</span></span>
2. <span data-ttu-id="fad1e-126">Nella scheda dettaglio **Generale**, nella sezione **IVA**, impostare l'opzione **Calcolo IVA differito** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-126">On the **General** FastTab, in the **Sales tax** section, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Immagine dei nomi del giornale di registrazione](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a><span data-ttu-id="fad1e-128">Attivare il calcolo IVA differito a livello di intestazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="fad1e-128">Turn on delayed tax calculation at the journal header level</span></span>

1. <span data-ttu-id="fad1e-129">Fare clic su **Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-129">Go to **General ledger \> Journal entries \> General journals**.</span></span>
2. <span data-ttu-id="fad1e-130">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-130">Select **New**.</span></span>
3. <span data-ttu-id="fad1e-131">Selezionare un nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="fad1e-131">Select a journal name.</span></span>
4. <span data-ttu-id="fad1e-132">Nella scheda **Impostazione**, impostare l'opzione **Calcolo IVA differito** **Sì**.</span><span class="sxs-lookup"><span data-stu-id="fad1e-132">On the **Setup** tab, set the **Delayed tax calculation** option to **Yes**.</span></span>

![Immagine della pagina del giornale di registrazione generale](media/delayed-tax-calculation-journal-header.png)
