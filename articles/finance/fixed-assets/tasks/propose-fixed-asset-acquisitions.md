---
title: Proporre acquisizioni di cespiti
description: Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.
author: saraschi2
ms.date: 03/17/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetTable, AssetBook, LedgerJournalTable, LedgerJournalTransAsset, SysQueryForm
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d529cd53b41827a78b282afd4d2c69d2f2db555e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817170"
---
# <a name="propose-fixed-asset-acquisitions"></a><span data-ttu-id="41107-103">Proporre acquisizioni di cespiti</span><span class="sxs-lookup"><span data-stu-id="41107-103">Propose fixed asset acquisitions</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="41107-104">Questa argomento descrive come acquisire un cespite utilizzando la proposta di acquisizione nel giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="41107-104">This topic describes how to acquire a fixed asset using the acquisition proposal in the Fixed assets journal.</span></span> <span data-ttu-id="41107-105">Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.</span><span class="sxs-lookup"><span data-stu-id="41107-105">It uses the accountant role and demo data for the USMF legal entity.</span></span> <span data-ttu-id="41107-106">Per acquisire un cespite tramite un giornale di proposte cespite, è necessario innanzitutto creare il record cespite, quindi definire il prezzo di acquisizione nel libro patrimoniale.</span><span class="sxs-lookup"><span data-stu-id="41107-106">To acquire a fixed asset through a fixed asset proposal journal, you must first create the fixed asset record, and then define the acquisition price in the asset book.</span></span>

## <a name="create-an-asset-acquisition-proposal"></a><span data-ttu-id="41107-107">Creare una proposta di acquisizione cespite</span><span class="sxs-lookup"><span data-stu-id="41107-107">Create an asset acquisition proposal</span></span>

<span data-ttu-id="41107-108">Completa i seguenti passaggi per creare una proposta di acquisizione di cespite.</span><span class="sxs-lookup"><span data-stu-id="41107-108">Complete the following steps to create an asset acquisition proposal.</span></span> 

1. <span data-ttu-id="41107-109">Nel pannello di navigazione, andare a **Moduli > Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="41107-109">In the navigation pane, go to **Modules > Fixed assets > Journal entries > Fixed assets journal**.</span></span>
2. <span data-ttu-id="41107-110">Selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="41107-110">Select **New**.</span></span>
3. <span data-ttu-id="41107-111">Nel campo **Nome** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41107-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="41107-112">Nel riquadro azioni selezionare **Righe**.</span><span class="sxs-lookup"><span data-stu-id="41107-112">In the Action Pane, select **Lines**.</span></span>
5. <span data-ttu-id="41107-113">Selezione **Proposte**.</span><span class="sxs-lookup"><span data-stu-id="41107-113">Select **Proposals**.</span></span>
6. <span data-ttu-id="41107-114">Selezionare **Proposta di acquisizione**.</span><span class="sxs-lookup"><span data-stu-id="41107-114">Select **Acquisition proposal**.</span></span>
7. <span data-ttu-id="41107-115">Seleziona **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="41107-115">Select **Filter**.</span></span> <span data-ttu-id="41107-116">Seleziona **Reimposta** per cancellare i valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="41107-116">Select **Reset** to clear previous values.</span></span>
8. <span data-ttu-id="41107-117">Selezionare la riga **Numero cespite**.</span><span class="sxs-lookup"><span data-stu-id="41107-117">Select the **Fixed asset number** row.</span></span>
9. <span data-ttu-id="41107-118">Nel campo **Criteri** immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="41107-118">In the **Criteria** field, enter or select a value.</span></span> <span data-ttu-id="41107-119">Impostare i criteri rimanenti per i cespiti che si desidera acquisire con la proposta.</span><span class="sxs-lookup"><span data-stu-id="41107-119">Set the remaining criteria for the fixed assets that you want to acquire with this proposal.</span></span>  
10. <span data-ttu-id="41107-120">Selezionare due volte **OK** per uscire dal riquadro.</span><span class="sxs-lookup"><span data-stu-id="41107-120">Select **OK** twice to exit out of the pane.</span></span>
- <span data-ttu-id="41107-121">Verifica che le righe transazione siano create.</span><span class="sxs-lookup"><span data-stu-id="41107-121">Verify that the transaction lines are created.</span></span>  
- <span data-ttu-id="41107-122">Solo i cespiti con la data di acquisizione e il prezzo di acquisizione impostati sul libro verranno inclusi nella proposta di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="41107-122">Only fixed assets with the acquisition date and acquisition price set on the book will be included in the acquisition proposal.</span></span>  
11. <span data-ttu-id="41107-123">Nella pagina, selezionare la scheda **Libri**.</span><span class="sxs-lookup"><span data-stu-id="41107-123">On the page, select the **Books** tab.</span></span>
12. <span data-ttu-id="41107-124">Selezionare **Registra**.</span><span class="sxs-lookup"><span data-stu-id="41107-124">Select **Post**.</span></span>

## <a name="include-default-financial-dimensions-in-an-acquisition-proposal"></a><span data-ttu-id="41107-125">Includere dimensioni finanziarie predefinite in una proposta di acquisizione</span><span class="sxs-lookup"><span data-stu-id="41107-125">Include default financial dimensions in an acquisition proposal</span></span>

<span data-ttu-id="41107-126">La transazione di acquisizione può essere creata utilizzando componenti aggiuntivi di Excel, andando a **Cespiti > Scritture contabili > Giornale di registrazione cespiti**.</span><span class="sxs-lookup"><span data-stu-id="41107-126">The acquisition transaction can be created using Excel add-ins, by going to **Fixed assets > Journal entries > Fixed asset journal**.</span></span> <span data-ttu-id="41107-127">Crea un nuovo giornale di registrazione e passa alla sezione **Righe** nella pagina e seleziona l'icona di Excel, quindi seleziona una riga del giornale di registrazione cespiti.</span><span class="sxs-lookup"><span data-stu-id="41107-127">Create a new journal and move to the **Lines** section on the page and select the Excel icon, and then select a Fixed asset journal line.</span></span> <span data-ttu-id="41107-128">Il sistema creerà e aprirà un modello Excel che rappresenta le righe del giornale di registrazione.</span><span class="sxs-lookup"><span data-stu-id="41107-128">The system will create and open an Excel template representing journal lines.</span></span> <span data-ttu-id="41107-129">Puoi aggiungere dati per le righe del giornale di registrazione che stai aggiungendo al modello e quindi pubblicare nuovamente le informazioni nel sistema.</span><span class="sxs-lookup"><span data-stu-id="41107-129">You can add data for the journal lines you're adding into the template, and then publish that information back into the system.</span></span> 

<span data-ttu-id="41107-130">Se le dimensioni predefinite sono state impostate per il libro cespiti selezionato e i cespiti corrispondenti immessi nel modello Excel, le dimensioni finanziarie predefinite verranno richiamate dai dati master del libro cespiti quando il giornale di registrazione viene pubblicato da Excel nel sistema.</span><span class="sxs-lookup"><span data-stu-id="41107-130">If default dimensions have been set up for the selected asset book and the corresponding fixed assets that were entered in the Excel template, the default financial dimensions will be called from the asset book master data when the journal is published from the Excel to the system.</span></span> <span data-ttu-id="41107-131">Per includere automaticamente le dimensioni finanziarie in un libro cespiti durante la pubblicazione del giornale di registrazione cespiti dal componente aggiuntivo di Excel, le dimensioni predefinite devono essere impostate in anticipo.</span><span class="sxs-lookup"><span data-stu-id="41107-131">To include financial dimensions on an asset book automatically while publishing the fixed asset journal from the Excel add-in, the default dimensions must be set up in advance.</span></span>  


[!INCLUDE [footer-include](../../../includes/footer-banner.md)]
