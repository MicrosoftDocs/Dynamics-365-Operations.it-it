---
title: Ordine di esecuzione per la sincronizzazione iniziale di Finance and Operations e Common Data Service
description: In questo argomento specifica l'ordine di sincronizzazione che è necessario seguire per creare i dati iniziali.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 1473c3bad55734d5f83ee3e4c1654921b872f3bb
ms.sourcegitcommit: 3f05ede8b8acdf0550240a83a013e093b4ad043d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "1873130"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="2501b-103">Ordine di esecuzione per la sincronizzazione iniziale di Finance and Operations e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2501b-103">Execution order for initial synchronization of Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="2501b-104">Prima di utilizzare l'integrazione dei dati, è necessario creare i dati iniziali necessari per clienti, fornitori e i contatti.</span><span class="sxs-lookup"><span data-stu-id="2501b-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="2501b-105">Ad esempio, se si desidera creare un nuovo articolo **Gruppo di fornitori** e impostare il relativo valore **Termini di pagamento** su **Net30**.</span><span class="sxs-lookup"><span data-stu-id="2501b-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="2501b-106">In questo caso, prima di provare a creare l'articolo **Gruppo di fornitori**, verificare che **Net30** sia presente in Microsoft Dynamics 365 for Finance and Operations e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="2501b-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both Microsoft Dynamics 365 for Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="2501b-107">(in futuro, Microsoft rilascerà una funzionalità per la piattaforma di doppia scrittura denominata Sincronizzazione iniziale. Questa funzionalità eseguirà una sincronizzazione una-tantum dei dati tra Finance and Operations e Common Data Service come parte dell'impostazione di doppia scrittura).</span><span class="sxs-lookup"><span data-stu-id="2501b-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="2501b-108">Microsoft sta rilasciando una mappa di doppia scrittura per tutti i dati di riferimento inclusi **Termini di pagamento** (condizioni di pagamento).</span><span class="sxs-lookup"><span data-stu-id="2501b-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="2501b-109">Se si dispone già dei dati iniziali in un sistema, una piccola operazione di aggiornamento su un record può attivare la doppia scrittura su tale record.</span><span class="sxs-lookup"><span data-stu-id="2501b-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="2501b-110">È necessario seguire il seguente ordine di priorità e accertarsi che i dati iniziali sono disponibili sia in Finance and Operations che in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="2501b-110">You must follow the following order of precedence and make sure that the initial data is available in both Finance and Operations and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="2501b-111">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2501b-111">Vendor</span></span>

<span data-ttu-id="2501b-112">Di seguito è riportato l'ordine di esecuzione dell'entità **Fornitore** :</span><span class="sxs-lookup"><span data-stu-id="2501b-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="2501b-113">Gruppo di fornitori</span><span class="sxs-lookup"><span data-stu-id="2501b-113">Vendor group</span></span>

    1. <span data-ttu-id="2501b-114">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="2501b-114">Terms of payment</span></span>

        1. <span data-ttu-id="2501b-115">Righe e giorno di pagamento</span><span class="sxs-lookup"><span data-stu-id="2501b-115">Payment day and lines</span></span>
        2. <span data-ttu-id="2501b-116">Scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="2501b-116">Payment schedule</span></span>

2. <span data-ttu-id="2501b-117">Metodo di pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="2501b-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="2501b-118">Cliente (Organizzazione)</span><span class="sxs-lookup"><span data-stu-id="2501b-118">Customer (Organization)</span></span>

<span data-ttu-id="2501b-119">Di seguito è riportato l'ordine di esecuzione dell'entità **Cliente**:</span><span class="sxs-lookup"><span data-stu-id="2501b-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="2501b-120">Gruppo di clienti</span><span class="sxs-lookup"><span data-stu-id="2501b-120">Customer group</span></span>

    1. <span data-ttu-id="2501b-121">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="2501b-121">Terms of payment</span></span>

        1. <span data-ttu-id="2501b-122">Righe e giorno di pagamento</span><span class="sxs-lookup"><span data-stu-id="2501b-122">Payment day and lines</span></span>
        2. <span data-ttu-id="2501b-123">Pagamento</span><span class="sxs-lookup"><span data-stu-id="2501b-123">Payment</span></span> 

2. <span data-ttu-id="2501b-124">Metodo di pagamento clienti</span><span class="sxs-lookup"><span data-stu-id="2501b-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="2501b-125">Contatto (Persona)</span><span class="sxs-lookup"><span data-stu-id="2501b-125">Contact (Person)</span></span>

<span data-ttu-id="2501b-126">Di seguito è riportato l'ordine di esecuzione dell'entità **Contatto**:</span><span class="sxs-lookup"><span data-stu-id="2501b-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="2501b-127">Cliente</span><span class="sxs-lookup"><span data-stu-id="2501b-127">Customer</span></span>
2. <span data-ttu-id="2501b-128">Fornitore</span><span class="sxs-lookup"><span data-stu-id="2501b-128">Vendor</span></span>
