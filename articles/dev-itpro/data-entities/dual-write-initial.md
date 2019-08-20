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
ms.openlocfilehash: b74bc2d3133af7e87663a4e6bafb8780e0a6a66f
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797300"
---
# <a name="execution-order-for-initial-sychronization-of-finance-and-operations-and-common-data-service"></a><span data-ttu-id="54232-103">Ordine di esecuzione per la sincronizzazione iniziale di Finance and Operations e Common Data Service</span><span class="sxs-lookup"><span data-stu-id="54232-103">Execution order for initial sychronization of Finance and Operations and Common Data Service</span></span>

<span data-ttu-id="54232-104">Prima di utilizzare l'integrazione dei dati, è necessario creare i dati iniziali necessari per clienti, fornitori e i contatti.</span><span class="sxs-lookup"><span data-stu-id="54232-104">Before you use data integration, you must create the initial data required for customers, vendors and contacts.</span></span> <span data-ttu-id="54232-105">Ad esempio, se si desidera creare un nuovo articolo **Gruppo di fornitori** e impostare il relativo **Termini di pagamento** come **Net30**, prima di tentiate di creare l'articolo **Gruppo di fornitori** è necessario assicurarsi che **Net30** sia presente sia in Finance and Operations che in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="54232-105">For example, if you want to create a new **Vendor group** item and set its **Terms of Payment** as **Net30**, then before you attempt to create the **Vendor group** item you need to make sure that **Net30** exists in both Finance and Operations and Common Data Service.</span></span> <span data-ttu-id="54232-106">(In futuro, rilasceremo una funzionalità per la piattaforma di doppia scrittura denominata **Sincronizzazione iniziale**. Farà una sincronizzazione una-tantum dei dati tra Finance and Operations e Common Data Service come parte dell'impostazione di doppia scrittura).</span><span class="sxs-lookup"><span data-stu-id="54232-106">(In the future, we will release a  dual-write platform functionality called **Initial Sync**. It will do a one-time data synchronization between Finance and Operations and Common Data Service as part of the dual-write setup.)</span></span>

<span data-ttu-id="54232-107">Suggerimenti: Stiamo rilasciando una mappa di doppia scrittura per tutti i dati di riferimento inclusi **Termini di pagamento** (condizioni di pagamento).</span><span class="sxs-lookup"><span data-stu-id="54232-107">Tips: We are releasing a dual-write map for all reference data including **Terms of Payment** (Payment Terms).</span></span> <span data-ttu-id="54232-108">Se si dispone già dei dati iniziali in un sistema, una piccola operazione di aggiornamento su un record può attivare la doppia scrittura su tale record.</span><span class="sxs-lookup"><span data-stu-id="54232-108">If you already have the initial data in one system, a small update operation on a record can trigger dual-write on that record.</span></span> 

<span data-ttu-id="54232-109">È necessario seguire il seguente ordine di priorità e accertarsi che i dati iniziali sono disponibili sia in Finance and Operations che in Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="54232-109">You must follow the following order of precedence and make sure that the initial data is available on both Finance and Operations and Common Data Service.</span></span>   

## <a name="vendor"></a><span data-ttu-id="54232-110">Fornitore</span><span class="sxs-lookup"><span data-stu-id="54232-110">Vendor</span></span>

<span data-ttu-id="54232-111">L'ordine dell'esecuzione per Fornitore è:</span><span class="sxs-lookup"><span data-stu-id="54232-111">The order of execution for Vendor is:</span></span>

```
Vendor Group
    Terms of payment
        Payment day & lines
        Payment schedule
Vendor payment method
```

## <a name="customer-organization"></a><span data-ttu-id="54232-112">Cliente (Organizzazione)</span><span class="sxs-lookup"><span data-stu-id="54232-112">Customer (Organization)</span></span>

<span data-ttu-id="54232-113">L'ordine dell'esecuzione per Cliente è:</span><span class="sxs-lookup"><span data-stu-id="54232-113">The order of execution for Customer is:</span></span>

```
Customer Group
    Terms of payment
        Payment day & lines
        Payment 
Customer payment method
```

## <a name="contact-person"></a><span data-ttu-id="54232-114">Contatto (Persona)</span><span class="sxs-lookup"><span data-stu-id="54232-114">Contact (Person)</span></span>

<span data-ttu-id="54232-115">L'ordine dell'esecuzione per Contatto è:</span><span class="sxs-lookup"><span data-stu-id="54232-115">The order of execution for Contact is:</span></span>

```
Customer
Vendor               
```
