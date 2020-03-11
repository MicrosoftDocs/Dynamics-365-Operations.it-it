---
title: Funzionalità della piattaforma rimosse o deprecate
description: In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 02/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: sericks
ms.search.validFrom: 2020-02-29
ms.dyn365.ops.version: Platform update 33
ms.openlocfilehash: 66e1420c7053c0df9f42b15c55aba1a8c869f02a
ms.sourcegitcommit: 2cc3b89efdd90f8d80883b7a271d7885282ba3e8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "3087885"
---
# <a name="removed-or-deprecated-platform-features"></a><span data-ttu-id="9b3ca-103">Funzionalità della piattaforma rimosse o deprecate</span><span class="sxs-lookup"><span data-stu-id="9b3ca-103">Removed or deprecated platform features</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9b3ca-104">In questo argomento vengono descritte le funzionalità rimosse, o di cui è stata progettata la rimozione dagli aggiornamenti della piattaforma per le app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-104">This topic describes features that have been removed, or that are planned for removal in platform updates of Finance and Operations apps.</span></span>

- <span data-ttu-id="9b3ca-105">Una funzionalità *rimossa* non è più disponibile nel prodotto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-105">A *removed* feature is no longer available in the product.</span></span>
- <span data-ttu-id="9b3ca-106">Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-106">A *deprecated* feature is not in active development and may be removed in a future update.</span></span>

<span data-ttu-id="9b3ca-107">Questo elenco ha lo scopo di aiutare a tenere in considerazione queste rimozioni e deprecazioni per la pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-107">This list is intended to help you consider these removals and deprecations for your own planning.</span></span> 

> [!NOTE]
> <span data-ttu-id="9b3ca-108">Informazioni dettagliate sugli oggetti nella app Finance and Operations sono disponibili nei [Report tecnici di riferimento](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-108">Detailed information about objects in Finance and Operations apps can be found in the [Technical reference reports](https://mbs.microsoft.com/customersource/northamerica/AX/downloads/reports/axtechrefrep).</span></span> <span data-ttu-id="9b3ca-109">È possibile confrontare le diverse versioni dei report per ottenere informazioni sugli oggetti che sono stati modificati o rimossi in ogni versione delle app Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-109">You can compare the different versions of these reports to learn about objects that have changed or been removed in each version of Finance and Operations apps.</span></span>

## <a name="platform-update-32"></a><span data-ttu-id="9b3ca-110">Update 32 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="9b3ca-110">Platform update 32</span></span>

### <a name="workflow-request-change-dialog-box-no-longer-includes-user-selection-drop-down-list"></a><span data-ttu-id="9b3ca-111">La finestra di dialogo per la modifica della richiesta del flusso di lavoro non include più l'elenco a discesa per la selezione dell'utente</span><span class="sxs-lookup"><span data-stu-id="9b3ca-111">Workflow request change dialog box no longer includes user selection drop-down list</span></span>
|   |  |
|------------|--------------------|
| <span data-ttu-id="9b3ca-112">**Motivo del deprecamento/rimozione**</span><span class="sxs-lookup"><span data-stu-id="9b3ca-112">**Reason for deprecation/removal**</span></span> | <span data-ttu-id="9b3ca-113">Questo era un problema di sicurezza perché la richiesta di modifica poteva essere inviata a un utente non intenzionale.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-113">This was a security issue because the request for change could be sent to an unintended user.</span></span> <span data-ttu-id="9b3ca-114">Anche questo era un problema di usabilità perché costringeva l'utente a determinare chi era il creatore del flusso di lavoro e selezionarlo manualmente.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-114">This was also a usability issue because it forced the user to determine who the workflow originator was and manually select them.</span></span>  |
| <span data-ttu-id="9b3ca-115">**Sostituita da un'altra funzionalità?**</span><span class="sxs-lookup"><span data-stu-id="9b3ca-115">**Replaced by another feature?**</span></span>   | <span data-ttu-id="9b3ca-116">Nessuno</span><span class="sxs-lookup"><span data-stu-id="9b3ca-116">No</span></span> |
| <span data-ttu-id="9b3ca-117">**Aree del prodotto interessate**</span><span class="sxs-lookup"><span data-stu-id="9b3ca-117">**Product areas affected**</span></span>         | <span data-ttu-id="9b3ca-118">Flusso di lavoro</span><span class="sxs-lookup"><span data-stu-id="9b3ca-118">Workflow</span></span> |
| <span data-ttu-id="9b3ca-119">**Opzione di distribuzione**</span><span class="sxs-lookup"><span data-stu-id="9b3ca-119">**Deployment option**</span></span>              | <span data-ttu-id="9b3ca-120">Tutte</span><span class="sxs-lookup"><span data-stu-id="9b3ca-120">All</span></span> |
| <span data-ttu-id="9b3ca-121">**Stato**</span><span class="sxs-lookup"><span data-stu-id="9b3ca-121">**Status**</span></span>                         | <span data-ttu-id="9b3ca-122">L'elenco a discesa di selezione dell'utente è stato rimosso dalla finestra di dialogo di modifica della richiesta nell'aggiornamento 32 della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-122">The user selection drop-down list was removed from the request change dialog box in Platform update 32.</span></span> <span data-ttu-id="9b3ca-123">Le richieste di modifica della richiesta verranno inviate automaticamente al mittente come previsto.</span><span class="sxs-lookup"><span data-stu-id="9b3ca-123">Request change requests will be automatically sent to the originator as intended.</span></span> <span data-ttu-id="9b3ca-124">Per ulteriori informazioni su questa funzionalità, vedere [Azioni nei processi di approvazione del flusso di lavoro](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-124">For more information about this functionality, see [Actions in workflow approval processes](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/workflow-actions?toc=%2Fdynamics365%2Fcommerce%2Ftoc.json#request-change).</span></span> |

## <a name="previous-announcements-about-removed-or-deprecated-features"></a><span data-ttu-id="9b3ca-125">Annunci precedenti sulle funzionalità rimosse o deprecate</span><span class="sxs-lookup"><span data-stu-id="9b3ca-125">Previous announcements about removed or deprecated features</span></span>
<span data-ttu-id="9b3ca-126">Per ulteriori informazioni sulle funzionalità che sono state rimosse o deprecate nelle versioni precedenti, vedere [Funzionalità rimosse o deprecate nelle versioni precedenti](../migration-upgrade/deprecated-features.md).</span><span class="sxs-lookup"><span data-stu-id="9b3ca-126">To learn more about features that have been removed or deprecated in previous releases, see [Removed or deprecated features in previous releases](../migration-upgrade/deprecated-features.md).</span></span>

