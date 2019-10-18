---
title: Abilitare il calcolo IVA differito nel giornale di registrazione
description: In questo argomento viene descritto come utilizzare la funzionalità **Abilita calcolo IVA differito nel giornale di registrazione** per migliorare le prestazioni di calcolo dell'IVA quando il volume delle righe del giornale di registrazione è enorme.
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
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178432"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a><span data-ttu-id="c16b9-103">Abilitare il calcolo IVA differito nel giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c16b9-103">Enable delayed tax calculation on journal</span></span>
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="c16b9-104">In questo argomento viene descritto come utilizzare la funzionalità **Abilita calcolo IVA differito nel giornale di registrazione** per migliorare le prestazioni di calcolo dell'IVA quando il volume delle righe del giornale di registrazione è enorme.</span><span class="sxs-lookup"><span data-stu-id="c16b9-104">This topic explains how to use the **Enable delayed tax calculation on journal** feature to improve tax calculation performance when the volume of journal lines is huge.</span></span>

<span data-ttu-id="c16b9-105">Il comportamento corrente del calcolo dell'IVA nel giornale di registrazione è attivato in tempo reale quando l'utente aggiorna i campi relativi all'IVA, ad esempio Fascia IVA/Fascia IVA articoli.</span><span class="sxs-lookup"><span data-stu-id="c16b9-105">Current sales tax calculation behavior on journal is real-time triggered when user updates tax related fields, e.g. sales tax group/item sales tax group.</span></span> <span data-ttu-id="c16b9-106">Qualsiasi aggiornamento a livello di riga del giornale di registrazione ricalcolerà l'importo IVA in tutte le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c16b9-106">Any update at journal line level will re-calculate tax amount on all journal lines.</span></span> <span data-ttu-id="c16b9-107">Ciò consente all'utente di ottenere il calcolo dell'importo IVA in tempo reale ma può anche generare un problema di prestazioni se il volume delle righe del giornale di registrazione è enorme.</span><span class="sxs-lookup"><span data-stu-id="c16b9-107">It helps user to see real-time calculated tax amount but it could also bring performance issue if  the volume of journal lines is huge.</span></span>

<span data-ttu-id="c16b9-108">Questa funzionalità fornisce un'opzione per differire il calcolo dell'IVA e risolvere il problema di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c16b9-108">This feature provides an option to delay tax calculation to solve performance issue.</span></span> <span data-ttu-id="c16b9-109">Se questa funzionalità è attivata, l'importo IVA verrà calcolato solo quando l'utente fa clic sul comando "IVA" o registra il giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c16b9-109">If this feature is turned on, tax amount will only be calculated when user clicks "Sales Tax" command or posts the journal.</span></span>

<span data-ttu-id="c16b9-110">L'utente può attivare/disattivare il parametro a tre livelli:</span><span class="sxs-lookup"><span data-stu-id="c16b9-110">User can turn on/off the parameter at three levels:</span></span>
- <span data-ttu-id="c16b9-111">In base all'entità giuridica</span><span class="sxs-lookup"><span data-stu-id="c16b9-111">By legal entity</span></span>
- <span data-ttu-id="c16b9-112">In base al nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c16b9-112">By journal name</span></span>
- <span data-ttu-id="c16b9-113">In base all'intestazione del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c16b9-113">By journal header</span></span>

<span data-ttu-id="c16b9-114">Il sistema considererà il valore del parametro nell'intestazione del giornale di registrazione come finale.</span><span class="sxs-lookup"><span data-stu-id="c16b9-114">System will take the parameter value on journal header as final.</span></span> <span data-ttu-id="c16b9-115">Per impostazione predefinita, il valore del parametro nell'intestazione del giornale di registrazione è il nome del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c16b9-115">Parameter value on journal header will be defaulted from journal name.</span></span> <span data-ttu-id="c16b9-116">Per impostazione predefinita, il valore del parametro nel nome del giornale di registrazione è il parametro di contabilità generale quando il nome del giornale di registrazione viene creato.</span><span class="sxs-lookup"><span data-stu-id="c16b9-116">Parameter value on journal name will be defaulted from general ledger parameter when the journal name is created.</span></span>

<span data-ttu-id="c16b9-117">I campi "Importo IVA effettiva" e "Importo IVA calcolato" nel giornale di registrazione non saranno visibili se questo parametro è abilitato.</span><span class="sxs-lookup"><span data-stu-id="c16b9-117">"Actual sales tax amount" and "Calculated sales tax amount" fields on journal will be hided if this parameter is turned on.</span></span> <span data-ttu-id="c16b9-118">Lo scopo è di non confondere l'utente in quanto il valore di questi due campi sarà sempre pari a 0 prima che l'utente attivi il calcolo dell'IVA.</span><span class="sxs-lookup"><span data-stu-id="c16b9-118">The purpose is not to confuse user because the value of these two fields will always show 0 before user trigger the tax calculation.</span></span>

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a><span data-ttu-id="c16b9-119">Abilitare il calcolo IVA differito in base alla persona giuridica</span><span class="sxs-lookup"><span data-stu-id="c16b9-119">Enable delayed tax calculation by legal entity</span></span>

1. <span data-ttu-id="c16b9-120">Selezionare **Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-120">Go to **General ledger > Ledger setup > General ledger parameters**</span></span>
2. <span data-ttu-id="c16b9-121">Fare clic sulla scheda **Fascia IVA**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-121">Click **Sales tax** tab</span></span>
3. <span data-ttu-id="c16b9-122">Nella Scheda dettaglio **Generale**, individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo</span><span class="sxs-lookup"><span data-stu-id="c16b9-122">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a><span data-ttu-id="c16b9-123">Abilitare il calcolo IVA differito in base al nome del giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c16b9-123">Enable delayed tax calculation by journal name</span></span>

1. <span data-ttu-id="c16b9-124">Selezionare **Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-124">Go to **General ledger > Journal setup > Journal names**</span></span>
2. <span data-ttu-id="c16b9-125">Nella Scheda dettaglio **Generale**, individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo</span><span class="sxs-lookup"><span data-stu-id="c16b9-125">Under **General** fast tab, find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a><span data-ttu-id="c16b9-126">Abilitare il calcolo IVA differito in base al giornale di registrazione</span><span class="sxs-lookup"><span data-stu-id="c16b9-126">Enable delayed tax calculation by journal</span></span>

1. <span data-ttu-id="c16b9-127">Selezionare **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-127">Go to **General ledger > Journal entries > General journals**</span></span>
2. <span data-ttu-id="c16b9-128">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-128">Click **New**</span></span>
3. <span data-ttu-id="c16b9-129">Selezionare un nome di giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="c16b9-129">Select a journal name</span></span>
4. <span data-ttu-id="c16b9-130">Fare clic su **Imposta**.</span><span class="sxs-lookup"><span data-stu-id="c16b9-130">Click **Setup**</span></span>
5. <span data-ttu-id="c16b9-131">Individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo.</span><span class="sxs-lookup"><span data-stu-id="c16b9-131">Find parameter **Delayed tax calculation**, turn on/off it</span></span>

![](media/delayed-tax-calculation-journal-header.png)
