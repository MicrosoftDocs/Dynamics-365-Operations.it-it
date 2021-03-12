---
title: Configurare un esperimento
description: In questo argomento viene descritto come configurare un esperimento in un servizio di terze parti.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 1a60eb459d6d6f710e43ac5418b9375420ca8387
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000793"
---
# <a name="set-up-an-experiment"></a><span data-ttu-id="ba817-103">Configurare un esperimento</span><span class="sxs-lookup"><span data-stu-id="ba817-103">Set up an experiment</span></span>

<span data-ttu-id="ba817-104">Dopo che hai [definito un'ipotesi e determinato quali metriche desideri utilizzare](experimentation-identify.md), dovrai configurare l'esperimento nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ba817-104">After you [define a hypothesis and determine what success metrics you want to use](experimentation-identify.md), you'll need to set up your experiment in the third-party service.</span></span> <span data-ttu-id="ba817-105">Il diagramma seguente mostra tutti i passaggi relativi alla configurazione e all'esecuzione di un esperimento su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ba817-105">The following diagram shows all of the steps involved in setting up and running an experiment on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="ba817-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="ba817-106">Additional steps are covered in separate topics.</span></span>

<span data-ttu-id="ba817-107">[ ![Percorso utente per sperimentazione - Configurazione](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ba817-107">[ ![Experimentation user journey - Setup](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)</span></span>


## <a name="set-up-your-experiment-in-the-third-party-service"></a><span data-ttu-id="ba817-108">Configurare l'esperimento nel servizio di terze parti</span><span class="sxs-lookup"><span data-stu-id="ba817-108">Set up your experiment in the third-party service</span></span>
<span data-ttu-id="ba817-109">A questo punto dovresti aver scelto il servizio di terze parti per eseguire e monitorare l'esperimento e configurare il connettore di sperimentazione.</span><span class="sxs-lookup"><span data-stu-id="ba817-109">By now you should have chosen your third-party service to run and monitor your experiment, and set up the experimentation connector.</span></span> <span data-ttu-id="ba817-110">Questi prerequisiti sono elencati in [Sperimentazione in Dynamics 365 Commerce](experimentation-overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba817-110">These prerequisites are listed in  [Experimentation in Dynamics 365 Commerce](experimentation-overview.md).</span></span>

<span data-ttu-id="ba817-111">Segui i passaggi necessari per creare l'esperimento nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ba817-111">Follow the steps required to create your experiment in the third-party service.</span></span> <span data-ttu-id="ba817-112">Se il connettore è configurato correttamente, l'elenco completo degli esperimenti che hai configurato nel servizio di terze parti sarà visualizzato in Creazione di siti Web di Commerce nel giro di 5 minuti.</span><span class="sxs-lookup"><span data-stu-id="ba817-112">If the connector is configured properly, the complete list of experiments you set up in the third-party service will appear in Commerce site builder within about 5 minutes.</span></span>

## <a name="set-up-your-success-metrics"></a><span data-ttu-id="ba817-113">Configurare le metriche</span><span class="sxs-lookup"><span data-stu-id="ba817-113">Set up your success metrics</span></span>
<span data-ttu-id="ba817-114">Per ogni esperimento sono necessarie metriche per misurare l'impatto delle varianti e per convalidare l'ipotesi.</span><span class="sxs-lookup"><span data-stu-id="ba817-114">Every experiment needs metrics to measure the impact of the variations and to validate the hypothesis.</span></span> <span data-ttu-id="ba817-115">Segui i passaggi seguenti per abilitare il calcolo delle metriche nel servizio di terze parti utilizzando eventi di telemetria in tempo reale di Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ba817-115">Follow the steps below to enable the computation of metrics in the third-party service using live telemetry events from Dynamics 365 Commerce.</span></span>

<span data-ttu-id="ba817-116">Per impostare i parametri corretti effettuare le seguenti operazioni.</span><span class="sxs-lookup"><span data-stu-id="ba817-116">To set up your success metrics, follow these steps.</span></span>

1. <span data-ttu-id="ba817-117">In Creazione di siti Web di Commerce, selezionare **Pagine** nel riquadro di spostamento a sinistra e quindi selezionare la pagina per la quale si desidera raccogliere metriche.</span><span class="sxs-lookup"><span data-stu-id="ba817-117">In Commerce site builder, select **Pages** in the left navigation pane, and then select the page that you want to collect metrics for.</span></span> 
1. <span data-ttu-id="ba817-118">Vai alla sezione **ID evento da monitorare** nel riquadro delle proprietà a destra della pagina o del modulo che desideri monitorare.</span><span class="sxs-lookup"><span data-stu-id="ba817-118">Go to the **Event IDs to track** section in the right property pane of the page or module you want to track.</span></span>
1. <span data-ttu-id="ba817-119">Seleziona **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="ba817-119">Select **View**.</span></span> <span data-ttu-id="ba817-120">Viene visualizzato un elenco di tutti gli ID evento.</span><span class="sxs-lookup"><span data-stu-id="ba817-120">A list of all event IDs is displayed.</span></span> <span data-ttu-id="ba817-121">Copia l'evento che desideri monitorare e incolla la chiave dell'evento nella posizione designata nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ba817-121">Copy the event you want to track, and paste the event key into the designated location in the third-party service.</span></span> <span data-ttu-id="ba817-122">Se hai bisogno di più eventi, copia le chiavi una alla volta.</span><span class="sxs-lookup"><span data-stu-id="ba817-122">If you need more than one event, copy the keys one at a time.</span></span> 
    - <span data-ttu-id="ba817-123">Per informazioni su come visualizzare tutti gli eventi e gli attributi disponibili, comprese le visualizzazioni delle pagine e il monitoraggio delle entrate, vedi [Eventi dei componenti Commerce per diagnostica e risoluzione dei problemi](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ba817-123">To learn how to view all of the available events and attributes, including page views and revenue tracking, see [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md).</span></span>
1. <span data-ttu-id="ba817-124">Esegui altri passaggi per il monitoraggio delle metriche come richiesto nel servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ba817-124">Take any other steps for tracking metrics as required in the third-party service.</span></span>

## <a name="previous-step"></a><span data-ttu-id="ba817-125">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="ba817-125">Previous step</span></span>
[<span data-ttu-id="ba817-126">Identificare un'ipotesi e determina le metriche per un esperimento</span><span class="sxs-lookup"><span data-stu-id="ba817-126">Identify a hypothesis and determine metrics for an experiment</span></span>](experimentation-identify.md) 


## <a name="next-step"></a><span data-ttu-id="ba817-127">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="ba817-127">Next step</span></span>
[<span data-ttu-id="ba817-128">Collegare e modificare un esperimento</span><span class="sxs-lookup"><span data-stu-id="ba817-128">Connect and edit an experiment</span></span>](experimentation-connect-edit.md)
