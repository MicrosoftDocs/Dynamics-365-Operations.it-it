---
title: Ordine di esecuzione per la sincronizzazione iniziale delle app Finance and Operations e Common Data Service
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
ms.openlocfilehash: befe4e12a10f4a39b90bcb4faba6431a063a40e2
ms.sourcegitcommit: 54baab2a04e5c534fc2d1fd67b67e23a152d4e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "3019860"
---
# <a name="execution-order-for-initial-synchronization-of-finance-and-operations-apps-and-common-data-service"></a><span data-ttu-id="f8d1a-103">Ordine di esecuzione per la sincronizzazione iniziale delle app Finance and Operations e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="f8d1a-103">Execution order for initial synchronization of Finance and Operations apps and Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

[!include [preview-banner](../../includes/preview-banner.md)]

<span data-ttu-id="f8d1a-104">Prima di utilizzare l'integrazione dei dati, è necessario creare i dati iniziali necessari per clienti, fornitori e i contatti.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-104">Before you use data integration, you must create the initial data that is required for customers, vendors, and contacts.</span></span> <span data-ttu-id="f8d1a-105">Ad esempio, se si desidera creare un nuovo articolo **Gruppo di fornitori** e impostare il relativo valore **Termini di pagamento** su **Net30**.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-105">For example, you want to create a new **Vendor group** item and set its **Terms of Payment** value to **Net30**.</span></span> <span data-ttu-id="f8d1a-106">In questo caso, prima di provare a creare l'articolo **Gruppo di fornitori**, verificare che **Net30** sia presente nell'applicazione e in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-106">In this case, before you try to create the **Vendor group** item, you must make sure that **Net30** exists in both the application and Common Data Service.</span></span> <span data-ttu-id="f8d1a-107">(in futuro, Microsoft rilascerà una funzionalità per la piattaforma di doppia scrittura denominata Sincronizzazione iniziale. Questa funzionalità eseguirà una sincronizzazione una-tantum dei dati tra l'applicazione e Common Data Service come parte dell'impostazione di doppia scrittura).</span><span class="sxs-lookup"><span data-stu-id="f8d1a-107">(In the future, Microsoft will release dual-write platform functionality that is named Initial Sync. This functionality will do a one-time data synchronization between the application and Common Data Service as part of the dual-write setup.)</span></span>

> [!TIP]
> <span data-ttu-id="f8d1a-108">Microsoft sta rilasciando una mappa di doppia scrittura per tutti i dati di riferimento inclusi **Termini di pagamento** (condizioni di pagamento).</span><span class="sxs-lookup"><span data-stu-id="f8d1a-108">Microsoft is releasing a dual-write map for all reference data, including **Terms of Payment** (payment terms).</span></span> <span data-ttu-id="f8d1a-109">Se si dispone già dei dati iniziali in un sistema, una piccola operazione di aggiornamento su un record può attivare la doppia scrittura su tale record.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-109">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span>

<span data-ttu-id="f8d1a-110">È necessario seguire il seguente ordine di priorità e accertarsi che i dati iniziali siano disponibili sia nell'applicazione che in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="f8d1a-110">You must follow the following order of precedence and make sure that the initial data is available in the application and Common Data Service.</span></span>

## <a name="vendor"></a><span data-ttu-id="f8d1a-111">Fornitore</span><span class="sxs-lookup"><span data-stu-id="f8d1a-111">Vendor</span></span>

<span data-ttu-id="f8d1a-112">Di seguito è riportato l'ordine di esecuzione dell'entità **Fornitore** :</span><span class="sxs-lookup"><span data-stu-id="f8d1a-112">Here is the order of execution for the **Vendor** entity:</span></span>

1. <span data-ttu-id="f8d1a-113">Gruppo di fornitori</span><span class="sxs-lookup"><span data-stu-id="f8d1a-113">Vendor group</span></span>

    1. <span data-ttu-id="f8d1a-114">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="f8d1a-114">Terms of payment</span></span>

        1. <span data-ttu-id="f8d1a-115">Righe e giorno di pagamento</span><span class="sxs-lookup"><span data-stu-id="f8d1a-115">Payment day and lines</span></span>
        2. <span data-ttu-id="f8d1a-116">Scadenzario pagamenti</span><span class="sxs-lookup"><span data-stu-id="f8d1a-116">Payment schedule</span></span>

2. <span data-ttu-id="f8d1a-117">Metodo di pagamento fornitore</span><span class="sxs-lookup"><span data-stu-id="f8d1a-117">Vendor payment method</span></span>

## <a name="customer-organization"></a><span data-ttu-id="f8d1a-118">Cliente (Organizzazione)</span><span class="sxs-lookup"><span data-stu-id="f8d1a-118">Customer (Organization)</span></span>

<span data-ttu-id="f8d1a-119">Di seguito è riportato l'ordine di esecuzione dell'entità **Cliente**:</span><span class="sxs-lookup"><span data-stu-id="f8d1a-119">Here is the order of execution for the **Customer** entity:</span></span>

1. <span data-ttu-id="f8d1a-120">Gruppo di clienti</span><span class="sxs-lookup"><span data-stu-id="f8d1a-120">Customer group</span></span>

    1. <span data-ttu-id="f8d1a-121">Termini di pagamento</span><span class="sxs-lookup"><span data-stu-id="f8d1a-121">Terms of payment</span></span>

        1. <span data-ttu-id="f8d1a-122">Righe e giorno di pagamento</span><span class="sxs-lookup"><span data-stu-id="f8d1a-122">Payment day and lines</span></span>
        2. <span data-ttu-id="f8d1a-123">Pagamento</span><span class="sxs-lookup"><span data-stu-id="f8d1a-123">Payment</span></span> 

2. <span data-ttu-id="f8d1a-124">Metodo di pagamento clienti</span><span class="sxs-lookup"><span data-stu-id="f8d1a-124">Customer payment method</span></span>

## <a name="contact-person"></a><span data-ttu-id="f8d1a-125">Contatto (Persona)</span><span class="sxs-lookup"><span data-stu-id="f8d1a-125">Contact (Person)</span></span>

<span data-ttu-id="f8d1a-126">Di seguito è riportato l'ordine di esecuzione dell'entità **Contatto**:</span><span class="sxs-lookup"><span data-stu-id="f8d1a-126">Here is the order of execution for the **Contact** entity:</span></span>

1. <span data-ttu-id="f8d1a-127">Cliente</span><span class="sxs-lookup"><span data-stu-id="f8d1a-127">Customer</span></span>
2. <span data-ttu-id="f8d1a-128">Fornitore</span><span class="sxs-lookup"><span data-stu-id="f8d1a-128">Vendor</span></span>
