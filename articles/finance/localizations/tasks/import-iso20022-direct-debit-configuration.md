---
title: Importare la configurazione di addebito diretto ISO20022
description: In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti cliente.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d68e5a63ea3b037cc111d6732857f0aae1ce7e5d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989954"
---
# <a name="import-iso20022-direct-debit-configuration"></a><span data-ttu-id="7b046-103">Importare la configurazione di addebito diretto ISO20022</span><span class="sxs-lookup"><span data-stu-id="7b046-103">Import ISO20022 direct debit configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7b046-104">In questa procedura viene descritto come importare una configurazione di creazione di report elettronici dei pagamenti cliente.</span><span class="sxs-lookup"><span data-stu-id="7b046-104">This procedure demonstrates how to import a customer payment electronic reporting configuration.</span></span> <span data-ttu-id="7b046-105">In questa procedura viene utilizzato il formato di pagamento in addebito diretto ISO 20022 come esempio.</span><span class="sxs-lookup"><span data-stu-id="7b046-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> 



<span data-ttu-id="7b046-106">Questa procedura è stata creata utilizzando la società di dati dimostrativi DEMF ma è possibile utilizzare qualsiasi società di dati dimostrativi per questo scopo.</span><span class="sxs-lookup"><span data-stu-id="7b046-106">This procedure was created using the demo data company DEMF but you can use any demo data company for this purpose.</span></span>



<span data-ttu-id="7b046-107">Si tratta della prima di cinque procedure che illustrano il processo di pagamento cliente utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7b046-107">This is the first of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>

1. <span data-ttu-id="7b046-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="7b046-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="7b046-109">Nell'elenco di provider di configurazioni disponibili selezionare Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7b046-109">In the list of available configuration providers, select Microsoft.</span></span>
3. <span data-ttu-id="7b046-110">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="7b046-110">Click Set active.</span></span>
4. <span data-ttu-id="7b046-111">Fare clic su Archivi.</span><span class="sxs-lookup"><span data-stu-id="7b046-111">Click Repositories.</span></span>
5. <span data-ttu-id="7b046-112">Fare clic su Apri.</span><span class="sxs-lookup"><span data-stu-id="7b046-112">Click Open.</span></span>
6. <span data-ttu-id="7b046-113">Fare clic su Mostra filtri.</span><span class="sxs-lookup"><span data-stu-id="7b046-113">Click Show filters.</span></span>
7. <span data-ttu-id="7b046-114">Applicare i filtri seguenti: immettere un valore di filtro "Addebito diretto ISO20022 (DE)" nel campo "Nome configurazione" utilizzando l'operatore di filtro "inizia con".</span><span class="sxs-lookup"><span data-stu-id="7b046-114">Apply the following filters: Enter a filter value of "ISO20022 Direct debit (DE)" on the "Configuration name" field using the "begins with" filter operator</span></span>
    * <span data-ttu-id="7b046-115">Facoltativamente, è possibile trovare la configurazione nell'elenco, selezionarlo e ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="7b046-115">Optionally, you can find the configuration in the list, select it, and skip this step.</span></span>  
8. <span data-ttu-id="7b046-116">Fare clic su Importa.</span><span class="sxs-lookup"><span data-stu-id="7b046-116">Click Import.</span></span>
    * <span data-ttu-id="7b046-117">Se il pulsante di importazione non è disponibile, significa che la configurazione è già stata importata.</span><span class="sxs-lookup"><span data-stu-id="7b046-117">If the Import button is not available, it means that the configuration has been imported already.</span></span>  
9. <span data-ttu-id="7b046-118">Fare clic su Sì.</span><span class="sxs-lookup"><span data-stu-id="7b046-118">Click Yes.</span></span>

