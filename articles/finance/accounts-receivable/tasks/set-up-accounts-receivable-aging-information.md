---
title: Registrare la fattura fornitore e associarla alla quantità ricevuta
description: Questa guida consentirà di impostare una definizione periodo di aging, i saldi con aging cliente e di visualizzare i saldi nell'elenco Saldo con aging e nella pagina Riscossioni.
author: mikefalkner
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustVendReportInterval, CustAgingSnapshot, CustCollectionsPoolsListPage, CustCollections
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e3c1ec73da27a08aa7a6cd859d1adac772916e4
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140181"
---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a><span data-ttu-id="8d5b9-103">Registrare la fattura fornitore e associarla alla quantità ricevuta</span><span class="sxs-lookup"><span data-stu-id="8d5b9-103">Set up and generate accounts receivable aging information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8d5b9-104">Questa guida consentirà di impostare una definizione periodo di aging, i saldi con aging cliente e di visualizzare i saldi nell'elenco Saldo con aging e nella pagina Riscossioni.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-104">This guide will help you set up an aging period definition, age customer balances, and view balances in the Aged balance list and the Collections page.</span></span> <span data-ttu-id="8d5b9-105">Questa registrazione utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-105">This recording uses the USMF demo company.</span></span>


## <a name="create-an-aging-period-definition"></a><span data-ttu-id="8d5b9-106">Creare una definizione di periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-106">Create an aging period definition</span></span>
1. <span data-ttu-id="8d5b9-107">Andare a **pannello di navigazione > Moduli > Crediti e riscossioni > Impostazione > Definizioni periodo di aging**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Aging period definitions**.</span></span>
2. <span data-ttu-id="8d5b9-108">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-108">Click **New**.</span></span>
3. <span data-ttu-id="8d5b9-109">Nel campo **Definizione periodo di aging**, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-109">In the **Aging period definition** field, type a value.</span></span>
4. <span data-ttu-id="8d5b9-110">Digitare un valore nel campo **Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8d5b9-110">In the **Description** field, type a value.</span></span>
5. <span data-ttu-id="8d5b9-111">Fare clic su **Aggiungi sotto** per inserire un nuovo periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-111">Click **Add below** to insert a new aging period.</span></span>
6. <span data-ttu-id="8d5b9-112">Nel campo **Periodo**, immettere la descrizione da visualizzare nei report di aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-112">In the **Period** field, enter the description to show on aging reports.</span></span>
7. <span data-ttu-id="8d5b9-113">Immettere un numero nel campo **Unità**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-113">In the **Unit** field, enter a number.</span></span>
8. <span data-ttu-id="8d5b9-114">Selezionare un'opzione nel campo **Intervallo**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-114">In the **Interval** field, select an option.</span></span> <span data-ttu-id="8d5b9-115">Il periodo contabile corrisponde al periodo nel calendario di contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-115">Ledger period matches the period to your ledger calendar.</span></span> <span data-ttu-id="8d5b9-116">Il giorno, la settimana, il mese, il trimestre e gli anni definiscono la dimensione dell'intervallo in base al tipo di data.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-116">Day, week, month, quarter and years define the size of the interval by date type.</span></span> <span data-ttu-id="8d5b9-117">Illimitato consente di selezionare tutte le transazioni prima o dopo il periodo precedente, a seconda che si tratti del primo o dell'ultimo periodo.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-117">Unlimited selects all transactions before or after the previous period, depending on whether it is the first or last period.</span></span>  
9. <span data-ttu-id="8d5b9-118">Selezionare un'opzione nel campo **Indicatore di aging**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-118">In the **Aging indicator** field, select an option.</span></span>
10. <span data-ttu-id="8d5b9-119">Selezionare il periodo nella parte superiore della griglia.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-119">Select the period at the top of the grid.</span></span> <span data-ttu-id="8d5b9-120">Aggiornare la descrizione per descrivere il periodo meno recente nella definizione del periodo di aging</span><span class="sxs-lookup"><span data-stu-id="8d5b9-120">Update the description to describe the oldest period in the aging period definition</span></span>
11. <span data-ttu-id="8d5b9-121">Nel campo **Periodo** immettere la nuova descrizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-121">In the **Period** field, enter the new description of the aging period.</span></span>
12. <span data-ttu-id="8d5b9-122">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-122">Close the page.</span></span>

## <a name="age-the-balances"></a><span data-ttu-id="8d5b9-123">Aging dei saldi</span><span class="sxs-lookup"><span data-stu-id="8d5b9-123">Age the balances</span></span>
1. <span data-ttu-id="8d5b9-124">Andare a **Crediti e riscossioni > Attività periodiche > Saldi con aging cliente**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-124">Go to **Credit and collections > Periodic tasks > Age customer balances**.</span></span>
2. <span data-ttu-id="8d5b9-125">Nel campo **Definizione periodo di aging** selezionare il periodo di aging creato.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-125">In the **Aging period definition** field, select the aging period definition that you created.</span></span>
    + <span data-ttu-id="8d5b9-126">È possibile avere uno snapshot attivo per ogni definizione del periodo di aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-126">You can have one active snapshot for each aging period definition.</span></span>  
    + <span data-ttu-id="8d5b9-127">Per impostazione predefinita vengono elaborati tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-127">All customers are processed by default.</span></span> <span data-ttu-id="8d5b9-128">È possibile utilizzare questa opzione per calcolare un singolo pool di riscossioni dei clienti.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-128">You can use this selection to calculate a single collections pool of customers.</span></span>  
    + <span data-ttu-id="8d5b9-129">Selezionare la data della transazione che verrà utilizzata per l'aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-129">Select the date from the transaction that you will use for the aging.</span></span>  
    + <span data-ttu-id="8d5b9-130">Selezionare una data "a partire da" per l'aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-130">Select an "as of" date for aging.</span></span> <span data-ttu-id="8d5b9-131">L'impostazione predefinita è la data corrente, ma se si modifica il campo su Data selezionata, sarà possibile selezionare la data desiderata.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-131">The default is today but, if you change this field to Selected date, you will be able to pick the date that you want.</span></span> <span data-ttu-id="8d5b9-132">Per l'elaborazione batch, utilizzare la data odierna.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-132">For batch processing, use Today's date.</span></span>  
3. <span data-ttu-id="8d5b9-133">Espandere l'intervallo **Società**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-133">Expand the **Company** range.</span></span> <span data-ttu-id="8d5b9-134">È possibile selezionare le società che verranno incluse nello snapshot.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-134">You can select the companies that will be included in the snapshot.</span></span> <span data-ttu-id="8d5b9-135">Per impostazione predefinita viene selezionata la società corrente.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-135">The current company is selected by default.</span></span>
4. <span data-ttu-id="8d5b9-136">Fare clic su **OK** per elaborare lo snapshot.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-136">Click **Ok** to process the snapshot.</span></span> <span data-ttu-id="8d5b9-137">Questa operazione richiederà alcuni minuti, quindi aspettare che il dispositivo di scorrimento scompaia e controllare il centro messaggi per un messaggio.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-137">It will take some time so wait for the slider to disappear and check the message center for a message.</span></span>

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a><span data-ttu-id="8d5b9-138">Visualizzare i saldi nell'elenco Saldi con aging e nella pagina Riscossione</span><span class="sxs-lookup"><span data-stu-id="8d5b9-138">View the balances on the Aged balances list and on the Collection page</span></span>
1. <span data-ttu-id="8d5b9-139">Andare a **Crediti e riscossioni > Riscossioni > Saldi con aging**.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-139">Go to **Credit and collections > Collections > Aged balances**.</span></span> <span data-ttu-id="8d5b9-140">Nella pagina elenco vengono visualizzati i saldi per il cliente.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-140">The list page shows the balances for the customer.</span></span> <span data-ttu-id="8d5b9-141">Nell'icona di aging viene visualizzato il periodo di aging per la transazione meno recente.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-141">The aging icon shows the aging period for the oldest transaction.</span></span>  
2. <span data-ttu-id="8d5b9-142">Selezionare un cliente con un saldo.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-142">Select a customer with a balance.</span></span>
3. <span data-ttu-id="8d5b9-143">Espandere l'area riquadro Dettaglio informazioni **Aging** per visualizzare i saldi con aging.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-143">Expand the **Aging fact** box area to view the aged balances.</span></span> <span data-ttu-id="8d5b9-144">La definizione del periodo di aging per il riquadro Dettaglio informazioni viene ricavata dalla definizione del periodo di aging specificata nei parametri.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-144">The aging period definition for the fact box is taken from the default aging period definition specified in the parameters.</span></span> <span data-ttu-id="8d5b9-145">È possibile modificarla mediante il menu Pagato a destinazione.</span><span class="sxs-lookup"><span data-stu-id="8d5b9-145">You can change it using the Collect menu.</span></span>  

