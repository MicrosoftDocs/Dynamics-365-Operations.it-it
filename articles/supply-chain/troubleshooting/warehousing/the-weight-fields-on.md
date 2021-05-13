---
title: I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico
description: I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico
author: perlynne
ms.date: 04/15/2021
ms.topic: troubleshooting
ms.search.form: WHSShipmentDetails_WHSShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-05-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 639b82a9d46b74f179d6904d2c3b8e7dfb813b58
ms.sourcegitcommit: 5f5afb46431e1abd8fb6e92e0189914b598dc7fd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "5924353"
---
# <a name="the-weight-fields-on-load-lines-dont-match-the-weight-fields-on-the-load"></a><span data-ttu-id="9e5ae-103">I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico</span><span class="sxs-lookup"><span data-stu-id="9e5ae-103">The weight fields on load lines don't match the weight fields on the load</span></span>

<span data-ttu-id="9e5ae-104">Codici di errore: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span><span class="sxs-lookup"><span data-stu-id="9e5ae-104">Error codes: WHSLoadWeightOnLinesDoNotMatchLoadWarning</span></span>

## <a name="symptoms"></a><span data-ttu-id="9e5ae-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="9e5ae-105">Symptoms</span></span>

<span data-ttu-id="9e5ae-106">Il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="9e5ae-106">The system shows the following error message:</span></span>

> <span data-ttu-id="9e5ae-107">I campi del peso nelle righe di carico non corrispondono ai campi del peso nel carico %1.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-107">The weight fields on load lines do not match the weight fields on load %1.</span></span> <span data-ttu-id="9e5ae-108">Eseguire la verifica della coerenza del peso del carico di magazzino per ricalcolare i campi del peso.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-108">Run the Warehouse load weight consistency check to recalculate the weight fields.</span></span>

## <a name="cause"></a><span data-ttu-id="9e5ae-109">Causa</span><span class="sxs-lookup"><span data-stu-id="9e5ae-109">Cause</span></span>

<span data-ttu-id="9e5ae-110">I campi **Peso netto** e **Tara** sono impostati su *0* (zero) sulla riga di carico.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-110">The **Net weight** and **Tara weight** fields are set to *0* (zero) on the load line.</span></span> <span data-ttu-id="9e5ae-111">Tuttavia, i campi del peso non sono impostati su *0* per le misurazioni del peso nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-111">However, the weight fields aren't set to *0* for the weight measurements on the product.</span></span> <span data-ttu-id="9e5ae-112">Quando i campi del peso non sono impostati sulla riga di carico, qualsiasi correzione della quantità riga linea di carico potrebbe causare un calcolo del peso errato sul carico.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-112">When weight fields aren't set on the load line, any corrections of the quantity on the load line might cause incorrect weight calculation on the load.</span></span> <span data-ttu-id="9e5ae-113">Questo problema potrebbe verificarsi se i pesi del prodotto sono stati modificati dopo la creazione della riga di carico.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-113">This issue might occur if the weights on the product have been changed since the load line was created.</span></span>

## <a name="resolution"></a><span data-ttu-id="9e5ae-114">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="9e5ae-114">Resolution</span></span>

<span data-ttu-id="9e5ae-115">Per impostazione predefinita, quando viene creata una riga di carico, i campi del peso del prodotto vengono inseriti in essa.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-115">By default, when a load line is created, the weight fields from the product are entered on it.</span></span> <span data-ttu-id="9e5ae-116">Se il peso è zero, è possibile ricalcolarlo utilizzando la funzionalità *Verifica coerenza peso carico magazzino*.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-116">If the weight is zero, you can recalculate it by using the *Warehouse load weight consistency check* functionality.</span></span>

1. <span data-ttu-id="9e5ae-117">Selezionare **Amministrazione sistema \> Attività periodiche \> Database \> Verifica coerenza**.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-117">Go to **System administration \> Periodic tasks \> Database \> Consistency check**.</span></span>
1. <span data-ttu-id="9e5ae-118">Nella finestra di dialogo **Verifica coerenza**, impostare il campo **Modulo** su *Gestione magazzino*.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-118">In the **Consistency check** dialog box, set the **Module** field to *Warehouse management*.</span></span>
1. <span data-ttu-id="9e5ae-119">Impostare il campo **Verifica/Correggi** su *Correggi errore*.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-119">Set the **Check/Fix** field to *Fix error*.</span></span>
1. <span data-ttu-id="9e5ae-120">Nell'elenco delle caselle di controllo, seleziona **Verifica coerenza peso carico magazzino** e assicurati che sia evidenziata solo la riga per questa casella di controllo.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-120">In the checkbox list, select the **Warehouse load weight consistency check** checkbox, and make sure that only the row for this checkbox is highlighted.</span></span>
1. <span data-ttu-id="9e5ae-121">Nella parte superiore dell'elenco delle caselle di controllo, seleziona il pulsante con i puntini di sospensione (**...**), quindi seleziona **Finestra di dialogo** sul menu.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-121">At the top of the checkbox list, select the ellipsis button (**...**), and then select **Dialog** on the menu.</span></span>
1. <span data-ttu-id="9e5ae-122">Nella finestra di dialogo **Verifica coerenza peso carico magazzino** impostare i seguenti campi per specificare i criteri per i quali deve essere eseguita la verifica di coerenza:</span><span class="sxs-lookup"><span data-stu-id="9e5ae-122">In the **Warehouse load weight consistency check** dialog box, set the following fields to specify the criteria that the consistency check should run for:</span></span>

    - <span data-ttu-id="9e5ae-123">**ID carico:** Specifica un ID carico.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-123">**Load ID:** Specify a load ID.</span></span> <span data-ttu-id="9e5ae-124">Lascia questo campo vuoto per controllare tutti gli ID carico.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-124">Leave this blank to check all load IDs.</span></span>
    - <span data-ttu-id="9e5ae-125">**Numero articolo:** Specifica un numero di articolo.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-125">**Item number:** Specify an item number.</span></span> <span data-ttu-id="9e5ae-126">Lascia questo campo vuoto per controllare tutti gli articoli.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-126">Leave this blank to check all items.</span></span>
    - <span data-ttu-id="9e5ae-127">**Ricalcola sempre peso su carichi:** Imposta questa opzione su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-127">**Always recalculate weight on loads:** Set this option to *Yes*.</span></span>
    - <span data-ttu-id="9e5ae-128">**Consenti sovrascrittura peso su righe di carico:** Imposta questa opzione su *Sì*.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-128">**Allow overwrite of weight on load lines:** Set this option to *Yes*.</span></span>

1. <span data-ttu-id="9e5ae-129">Selezionare **OK** per chiudere la finestra di dialogo **Verifica coerenza peso carico magazzino**.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-129">Select **OK** to close the **Warehouse load weight consistency check** dialog box.</span></span>
1. <span data-ttu-id="9e5ae-130">Seleziona il pulsante con i puntini di sospensione e quindi seleziona **Esegui** sul menu.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-130">Select the ellipsis button, and then select **Execute** on the menu.</span></span>

<span data-ttu-id="9e5ae-131">Il peso viene ricalcolato in base ai criteri specificati.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-131">The weight is recalculated based on the criteria that you specified.</span></span> <span data-ttu-id="9e5ae-132">Seleziona il collegamento **Dettagli messaggio** per visualizzare il risultato della verifica di coerenza.</span><span class="sxs-lookup"><span data-stu-id="9e5ae-132">Select the **Message details** link to view the result of the consistency check.</span></span>
