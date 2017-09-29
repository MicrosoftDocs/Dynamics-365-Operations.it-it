--- 
title: Importare la configurazione di bonifico ISO20022
description: In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore.
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 71c0175178203006e297466c4a37cd3e6319b6ea
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="import-iso20022-credit-transfer-configuration"></a><span data-ttu-id="886c4-103">Importare la configurazione di bonifico ISO20022</span><span class="sxs-lookup"><span data-stu-id="886c4-103">Import ISO20022 credit transfer configuration</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="886c4-104">In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="886c4-104">This procedure shows how to import a vendor payment electronic reporting configuration.</span></span> <span data-ttu-id="886c4-105">Viene usato il formato di bonifico tedesco ISO 20022 come esempio.</span><span class="sxs-lookup"><span data-stu-id="886c4-105">The German ISO 20022 credit transfer format is used as an example.</span></span> <span data-ttu-id="886c4-106">Questa procedura può essere utilizzata per un altro formato di creazione di report elettronici disponibile.</span><span class="sxs-lookup"><span data-stu-id="886c4-106">This procedure can be used for other available electronic reporting format.</span></span> 

<span data-ttu-id="886c4-107">Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF ma è possibile utilizzare qualsiasi società di dati dimostrativi per completare l'attività.</span><span class="sxs-lookup"><span data-stu-id="886c4-107">This task was created using the demo data company DEMF but you can use any demo data company to complete this task.</span></span>

<span data-ttu-id="886c4-108">Si tratta della prima attività di cinque, tale set illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="886c4-108">This is the first of five tasks, that together illustrate the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="886c4-109">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="886c4-109">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="886c4-110">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="886c4-110">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="886c4-111">Nell'elenco di provider di configurazioni disponibili selezionare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="886c4-111">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="886c4-112">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="886c4-112">Click Set active.</span></span>
4. <span data-ttu-id="886c4-113">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="886c4-113">Click Repositories.</span></span>
5. <span data-ttu-id="886c4-114">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="886c4-114">Click Open.</span></span>
6. <span data-ttu-id="886c4-115">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="886c4-115">Click Show filters.</span></span>
7. <span data-ttu-id="886c4-116">Applicare i filtri seguenti: immettere un valore di filtro "Bonifico ISO20022 (DE)" nel campo "Nome configurazione" utilizzando l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="886c4-116">Apply the following filters: Enter a filter value of "ISO20022 Credit transfer (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="886c4-117">In alternativa, individuare la configurazione nell'elenco, selezionarla e spostarla nell'attività di importazione.</span><span class="sxs-lookup"><span data-stu-id="886c4-117">Alternatively, you can find the configuration in the list, select it, and then move it to the Import task.</span></span>  
8. <span data-ttu-id="886c4-118">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="886c4-118">Click Import.</span></span>
    * <span data-ttu-id="886c4-119">Se il pulsante di importazione non è disponibile, significa che la configurazione è già stata importata.</span><span class="sxs-lookup"><span data-stu-id="886c4-119">If the Import button is not available, it means that the configuration has  already been imported.</span></span>  
9. <span data-ttu-id="886c4-120">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="886c4-120">Click Yes.</span></span>


