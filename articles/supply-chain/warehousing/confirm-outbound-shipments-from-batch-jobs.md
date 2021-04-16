---
title: Conferma spedizioni in uscita da processi batch
description: Questo argomento descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione.
author: perlynne
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-31
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 69e61e1c04dd72efbe1d2f028c078100e07176f6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5838444"
---
# <a name="confirm-outbound-shipments-from-batch-jobs"></a><span data-ttu-id="2c6e9-103">Conferma spedizioni in uscita da processi batch</span><span class="sxs-lookup"><span data-stu-id="2c6e9-103">Confirm outbound shipments from batch jobs</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2c6e9-104">Questo argomento descrive come configurare un processo batch che conferma automaticamente le spedizioni dell'ordine di trasferimento in uscita per i carichi pronti per la spedizione.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-104">This topic describes how to set up a batch job that automatically confirms outbound transfer-order shipments for ready-to-ship loads.</span></span> <span data-ttu-id="2c6e9-105">Il processo batch qui descritto si applica solo alle spedizioni degli ordini di trasferimento, non agli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-105">The batch job described here only applies to transfer order shipments, not to sales orders.</span></span>

## <a name="enable-the-confirm-outbound-shipments-from-batch-jobs-feature"></a><span data-ttu-id="2c6e9-106">Abilitare la funzionalità Conferma spedizioni in uscita da processi batch</span><span class="sxs-lookup"><span data-stu-id="2c6e9-106">Enable the Confirm outbound shipments from batch jobs feature</span></span>

<span data-ttu-id="2c6e9-107">Prima di utilizzare questa funzionalità, è necessario abilitarla nel sistema.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-107">Before you can use this feature, it must be enabled on your system.</span></span> <span data-ttu-id="2c6e9-108">Gli amministratori possono utilizzare la pagina [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per controllare lo stato della funzione e abilitarla se necessario.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-108">Administrators can use the [Feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) page to check the feature status and enable it if needed.</span></span> <span data-ttu-id="2c6e9-109">La funzionalità viene elencata come:</span><span class="sxs-lookup"><span data-stu-id="2c6e9-109">The feature is listed as:</span></span>

- <span data-ttu-id="2c6e9-110">**Modulo** - *Gestione magazzino*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-110">**Module** - *Warehouse management*</span></span>
- <span data-ttu-id="2c6e9-111">**Nome funzionalità** - *Conferma spedizioni in uscita da processi batch*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-111">**Feature name** - *Confirm outbound shipments from batch jobs*</span></span>

## <a name="process-outbound-shipments"></a><span data-ttu-id="2c6e9-112">Elabora spedizioni in uscita</span><span class="sxs-lookup"><span data-stu-id="2c6e9-112">Process outbound shipments</span></span>

<span data-ttu-id="2c6e9-113">Per configurare un processo batch pianificato per eseguire la conferma di spedizione in uscita per i carichi pronti per la spedizione:</span><span class="sxs-lookup"><span data-stu-id="2c6e9-113">To set up a scheduled batch job to run the outbound shipment confirmation for loads that are ready to ship:</span></span>

1. <span data-ttu-id="2c6e9-114">Vai a **Gestione magazzino \> Attività periodiche \> Elaborazione spedizioni in uscita**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-114">Go to **Warehouse management \> Periodic tasks \> Process outbound shipments**.</span></span>
1. <span data-ttu-id="2c6e9-115">Si apre la finestra di dialogo **Conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-115">The **Confirm shipment** dialog box opens.</span></span> <span data-ttu-id="2c6e9-116">Nella scheda dettaglio **Record da includere**, selezionare **Filtro**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-116">On the **Records to include** FastTab, select **Filter**.</span></span>
1. <span data-ttu-id="2c6e9-117">Si apre la finestra di dialogo dell'editor di query.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-117">The query editor dialog box opens.</span></span> <span data-ttu-id="2c6e9-118">Nella scheda **Intervallo**, aggiungi una riga con i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="2c6e9-118">On the **Range** tab, add a row with the following values:</span></span>
    - <span data-ttu-id="2c6e9-119">**Tabella** - *Carichi*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-119">**Table** - *Loads*</span></span>
    - <span data-ttu-id="2c6e9-120">**Tabella derivata** - *Carichi*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-120">**Derived table** - *Loads*</span></span>
    - <span data-ttu-id="2c6e9-121">**Campo** - *Stato carico*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-121">**Field** - *Load status*</span></span>
    - <span data-ttu-id="2c6e9-122">**Criteri** - *Caricato*</span><span class="sxs-lookup"><span data-stu-id="2c6e9-122">**Criteria** - *Loaded*</span></span>
1. <span data-ttu-id="2c6e9-123">Selezionare **OK** per tornare alla finestra di dialogo **Conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-123">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="2c6e9-124">Nella Scheda dettaglio **Esegui in background**, impostare **Elaborazione batch** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-124">On the **Run in the background** FastTab, set **Batch processing** to **Yes**.</span></span>
1. <span data-ttu-id="2c6e9-125">Nella Scheda dettaglio **Esegui in background** selezionare **Ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-125">On the **Run in the background** FastTab, select **Recurrence**.</span></span>
1. <span data-ttu-id="2c6e9-126">Si apre la finestra di dialogo **Definisci ricorrenza**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-126">The **Define recurrence** dialog box opens.</span></span> <span data-ttu-id="2c6e9-127">Imposta il programma di esecuzione secondo necessità per la tua azienda.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-127">Set the run schedule as needed for your business.</span></span>
1. <span data-ttu-id="2c6e9-128">Selezionare **OK** per tornare alla finestra di dialogo **Conferma spedizione**.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-128">Select **OK** to return to the **Confirm shipment** dialog box.</span></span>
1. <span data-ttu-id="2c6e9-129">Selezionare **OK** nella finestra di dialogo **Conferma spedizione** per aggiungere il processo batch alla coda batch.</span><span class="sxs-lookup"><span data-stu-id="2c6e9-129">Select **OK** on the **Confirm shipment** dialog box to add the batch job to the batch queue.</span></span>

<span data-ttu-id="2c6e9-130">Per ulteriori informazioni, vedere [Panoramica elaborazione batch](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span><span class="sxs-lookup"><span data-stu-id="2c6e9-130">For more information, see [Batch processing overview](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]