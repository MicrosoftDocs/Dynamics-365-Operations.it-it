---
title: Impostare avvisi antifrode
description: "In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell'assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati. È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 79103
ms.assetid: e342af8d-7498-4d20-8483-ab368429c578
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 09d80015298c3d0219b6ffb290dc456990536a62
ms.contentlocale: it-it
ms.lasthandoff: 06/29/2017



---

# <a name="set-up-fraud-alerts"></a><span data-ttu-id="19273-104">Impostare avvisi antifrode</span><span class="sxs-lookup"><span data-stu-id="19273-104">Set up fraud alerts</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="19273-105">In questo argomento viene illustrato come impostare le regole per avvisare i rappresentanti dell'assistenza clienti di informazioni potenzialmente fraudolente quando gli ordini vengono elaborati.</span><span class="sxs-lookup"><span data-stu-id="19273-105">This topic explains how to set up rules to alert customer service representatives of potentially fraudulent information when orders are processed.</span></span> <span data-ttu-id="19273-106">È possibile definire codici specifici da utilizzare per mettere automaticamente o manualmente gli ordini sospetti in attesa.</span><span class="sxs-lookup"><span data-stu-id="19273-106">You can define specific codes to use to automatically or manually put suspicious orders on hold.</span></span> 

<span data-ttu-id="19273-107">Prima di impostare e di utilizzare le regole di verifica delle frodi, è necessario abilitare la verifica delle frodi e definire i valori di base di verifica delle frodi nei parametri per call center.</span><span class="sxs-lookup"><span data-stu-id="19273-107">Before you set up and use fraud checking rules, you must enable fraud checking and define the basic fraud checking values in the call center parameters.</span></span> <span data-ttu-id="19273-108">Sono disponibili due tipi di regole su frode:</span><span class="sxs-lookup"><span data-stu-id="19273-108">There are two types of fraud rules:</span></span>

-   <span data-ttu-id="19273-109">**Regole statiche**: utilizzano un valore specifico, come un numero di telefono che è stato inserito nella black list.</span><span class="sxs-lookup"><span data-stu-id="19273-109">**Static rules** use a specific value, such as a phone number that has been blacklisted.</span></span>
-   <span data-ttu-id="19273-110">**Regole dinamiche**: possono essere composte da variabili e condizioni.</span><span class="sxs-lookup"><span data-stu-id="19273-110">**Dynamic rules** can be composed from variables and conditions.</span></span>

<span data-ttu-id="19273-111">Prima di creare una regola dinamica, è necessario creare le variabili e le condizioni che definiscono a chi viene applicata la regola e quando questa deve essere applicata.</span><span class="sxs-lookup"><span data-stu-id="19273-111">Before you create a dynamic rule, you must create the variables and conditions that define who the rule applies to and when the rule should be applied.</span></span> <span data-ttu-id="19273-112">Si supponga, ad esempio, di voler creare una regola per richiedere che qualsiasi ordine cliente effettuato dal cliente 1202 del valore di 1.000,00 o più sia sospeso fino a quando non è possibile verificare il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="19273-112">For example, you want to create a rule to require that any sales order that customer 1202 places that is worth 1,000.00 or more be put on hold until the customer payment can be verified.</span></span> <span data-ttu-id="19273-113">In questo caso, le variabili sono il cliente 1202 e un totale dell'ordine di 1.000,00.</span><span class="sxs-lookup"><span data-stu-id="19273-113">In this case, the variables are customer 1202 and an order total of 1,000.00.</span></span> <span data-ttu-id="19273-114">La condizione specifica che se il cliente 1202 effettua un ordine e l'importo totale dell'ordine è uguale o maggiore di 1.000,00, l'ordine cliente deve sospeso fino a quando non viene verificato il pagamento del cliente.</span><span class="sxs-lookup"><span data-stu-id="19273-114">The condition specifies that if customer 1202 places an order, and the total amount of the order is equal to or more than 1,000.00, the sales order must be put on hold until the customer payment can be verified.</span></span>




