--- 
title: Configurare i parametri di Retail che influiscono sui rendiconti al dettaglio
description: "In questa procedura sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: josaw1
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ff12587d8332801131d5b0cac84e0db38f8f6142
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="configure-retail-parameters-that-affect-retail-statements"></a><span data-ttu-id="5fd75-103">Configurare i parametri di Retail che influiscono sui rendiconti al dettaglio</span><span class="sxs-lookup"><span data-stu-id="5fd75-103">Configure Retail parameters that affect retail statements</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="5fd75-104">In questa procedura sono illustrate le configurazioni per i parametri di vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5fd75-104">This procedure demonstrates configurations for Retail parameters that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="5fd75-105">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="5fd75-105">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="5fd75-106">Andare a Vendita al dettaglio e commercio > Impostazione sedi centrali > Parametri > Parametri di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="5fd75-106">Go to Retail and commerce > Headquarters setup  > Parameters > Retail parameters.</span></span>
2. <span data-ttu-id="5fd75-107">Fare clic sulla scheda Registrazione.</span><span class="sxs-lookup"><span data-stu-id="5fd75-107">Click the Posting tab.</span></span>
    * <span data-ttu-id="5fd75-108">Selezionare "Sì" se si desidera registrare gli importi di sconto periodici in modo specifico.</span><span class="sxs-lookup"><span data-stu-id="5fd75-108">Select "Yes" if you want to post the periodic discount amounts specifically.</span></span>  
    * <span data-ttu-id="5fd75-109">Selezionare "Standard" per utilizzare i conti predefiniti o selezionare "Periodico" per definire il conto da utilizzare per ciascuno sconto periodico.</span><span class="sxs-lookup"><span data-stu-id="5fd75-109">Select "Standard" to use default accounts, or select "Periodic" if you want to define which account to use for each periodic discount.</span></span>  
    * <span data-ttu-id="5fd75-110">Selezionare "Riepilogo" se le righe di scorte devono essere aggregate ove possibile.</span><span class="sxs-lookup"><span data-stu-id="5fd75-110">Select "Summary" if inventory lines should get aggregated whenever possible.</span></span>  
    * <span data-ttu-id="5fd75-111">Selezionare "Sì" se le fatture e pagamenti devono essere automaticamente liquidati durante il processo di registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="5fd75-111">Select "Yes" if Invoices and Payments should get automatically settled as part of the Statement posting process.</span></span>  
    * <span data-ttu-id="5fd75-112">Selezionare "Sì" se le transazioni deposito in cassaforte devono essere aggregate.</span><span class="sxs-lookup"><span data-stu-id="5fd75-112">Select "Yes" if Safe drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="5fd75-113">Selezionare "Sì" se le transazioni deposito bancario devono essere aggregate.</span><span class="sxs-lookup"><span data-stu-id="5fd75-113">Select "Yes" if Bank drop transactions should get aggregated.</span></span>  
    * <span data-ttu-id="5fd75-114">Selezionare "Sì" per attivare l'aggregazione per la registrazione rendiconti.</span><span class="sxs-lookup"><span data-stu-id="5fd75-114">Select "Yes" to turn aggregation on for Statement posting.</span></span>  
    * <span data-ttu-id="5fd75-115">Selezionare "Sì" per creare ed elaborare gli ordini in parallelo quando i rendiconti vengono registrati.</span><span class="sxs-lookup"><span data-stu-id="5fd75-115">Select "Yes" to create and process orders in parallel when statements are posted.</span></span>  
    * <span data-ttu-id="5fd75-116">Immettere il numero massimo di ordini da elaborare in ogni attività di processo batch.</span><span class="sxs-lookup"><span data-stu-id="5fd75-116">Enter the maximum orders to be processed in each batch job task.</span></span>  
3. <span data-ttu-id="5fd75-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="5fd75-117">Click Save.</span></span>


