---
title: Flussi di lavoro di transazioni per la gestione degli sconti
description: Questo argomento spiega come impostare un flusso di lavoro di transazioni per la gestione degli sconti per approvare e attivare le transazioni.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowTableListPageRnr
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 37b8022633e61c4d98d6f5d129bcf494a9ed92e0
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831724"
---
# <a name="rebate-management-deal-workflows"></a><span data-ttu-id="3c458-103">Flussi di lavoro di transazioni per la gestione degli sconti</span><span class="sxs-lookup"><span data-stu-id="3c458-103">Rebate management deal workflows</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="3c458-104">Per approvare le transazioni di sconti, la gestione degli sconti utilizza la stessa piattaforma del flusso di lavoro delle altre app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3c458-104">To approve rebate deals, Rebate management uses the same workflow platform as other Finance and Operations apps.</span></span> <span data-ttu-id="3c458-105">Ad ogni flusso di lavoro sono associati due processi di lavoro:</span><span class="sxs-lookup"><span data-stu-id="3c458-105">Two job processes are associated with every workflow:</span></span>

- <span data-ttu-id="3c458-106">Un elemento del flusso di lavoro attiva la transazione in modo che l'utente o il processo del flusso di lavoro possa approvare le transazioni.</span><span class="sxs-lookup"><span data-stu-id="3c458-106">One element of the workflow activates the deal so that the user or workflow process can approve the transactions.</span></span>
- <span data-ttu-id="3c458-107">Un elemento del flusso di lavoro approva la transazione.</span><span class="sxs-lookup"><span data-stu-id="3c458-107">One element of the workflow approves the deal.</span></span>

<span data-ttu-id="3c458-108">Prima di poter utilizzare una transazione di sconti, è necessario che sia attiva nel modulo **Gestione degli sconti**.</span><span class="sxs-lookup"><span data-stu-id="3c458-108">Before you can use a rebate deal, it must be active in the **Rebate management** module.</span></span> <span data-ttu-id="3c458-109">Per attivare una transazione, devi prima creare e configurare un *Flusso di lavoro per la gestione degli sconti*.</span><span class="sxs-lookup"><span data-stu-id="3c458-109">To activate a deal, you must first create and configure a *Rebate management deal workflow*.</span></span>

<span data-ttu-id="3c458-110">Dopo che un flusso di lavoro è stato attivato per la gestione degli sconti, gli utenti non possono approvare manualmente le transazioni.</span><span class="sxs-lookup"><span data-stu-id="3c458-110">After a workflow is activated for Rebate management, users can't manually approve deals.</span></span> <span data-ttu-id="3c458-111">Il flusso di lavoro deve essere sempre utilizzato.</span><span class="sxs-lookup"><span data-stu-id="3c458-111">The workflow must be always used.</span></span>

## <a name="create-and-manage-rebate-management-deal-workflows"></a><span data-ttu-id="3c458-112">Creare e gestire flussi di lavoro di transazioni per la gestione degli sconti</span><span class="sxs-lookup"><span data-stu-id="3c458-112">Create and manage Rebate management deal workflows</span></span>

<span data-ttu-id="3c458-113">Per lavorare con i flussi di lavoro di transazioni per la gestione dei rimborsi, vai a **Gestione degli sconti \> Impostazioni \> Flussi di lavoro di gestione degli sconti**.</span><span class="sxs-lookup"><span data-stu-id="3c458-113">To work with your Rebate management deal workflows, go to **Rebate management \> Setup \> Rebate management workflows**.</span></span> <span data-ttu-id="3c458-114">Qui è possibile visualizzare, creare e aggiornare i flussi di lavoro secondo necessità.</span><span class="sxs-lookup"><span data-stu-id="3c458-114">There, you can view, create, and update workflows as required.</span></span> <span data-ttu-id="3c458-115">È possibile attivare un solo flusso di lavoro di questo tipo alla volta.</span><span class="sxs-lookup"><span data-stu-id="3c458-115">Only one workflow of this type can be active at a time.</span></span> <span data-ttu-id="3c458-116">Per ulteriori informazioni sui flussi di lavoro, come lavorare con la pagina **Flussi di lavoro di gestione degli sconti** e come creare flussi di lavoro, vedi [Panoramica del sistema del flusso di lavoro](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) e argomenti correlati.</span><span class="sxs-lookup"><span data-stu-id="3c458-116">For more information about workflows, how to work with the **Rebate management workflows** page, and how to create workflows, see [Workflow system overview](../../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md) and its related topics.</span></span>

## <a name="use-a-workflow-to-activate-a-deal"></a><span data-ttu-id="3c458-117">Usrea un flusso di lavoro per attivare una transazione</span><span class="sxs-lookup"><span data-stu-id="3c458-117">Use a workflow to activate a deal</span></span>

<span data-ttu-id="3c458-118">Per attivare una transazione tramite un flusso di lavoro, apri la transazione (ad esempio, nella pagina **Tutte le transazioni di gestione degli sconti**).</span><span class="sxs-lookup"><span data-stu-id="3c458-118">To activate a deal through a workflow, open the deal (for example, on the **All rebate management deals** page).</span></span> <span data-ttu-id="3c458-119">Quindi, nel riquadro azioni seleziona **Flusso di lavoro \> Invia**.</span><span class="sxs-lookup"><span data-stu-id="3c458-119">Then, on the Action Pane, select **Workflow \> Submit**.</span></span> <span data-ttu-id="3c458-120">Dopo che la nuova transazione è stata elaborata e approvata tramite il flusso di lavoro, sarà attiva e pronta per l'uso.</span><span class="sxs-lookup"><span data-stu-id="3c458-120">After the new deal has been processed and approved through the workflow, it will be active and ready to use.</span></span>

<span data-ttu-id="3c458-121">Dopo che una transazione è stata attivata non puoi modificarne l'impostazione.</span><span class="sxs-lookup"><span data-stu-id="3c458-121">After a deal has been activated, you can't change its setup.</span></span> <span data-ttu-id="3c458-122">Se devi modificare una transazione attiva, disattivala e quindi creane una nuova.</span><span class="sxs-lookup"><span data-stu-id="3c458-122">If you must change an active deal, inactivate it, and then create a new deal.</span></span> <span data-ttu-id="3c458-123">Se la nuova transazione assomiglierà alla vecchia, puoi crearla copiando la vecchia transazione.</span><span class="sxs-lookup"><span data-stu-id="3c458-123">If the new deal will resemble the old deal, you can create it by copying the old deal.</span></span>
