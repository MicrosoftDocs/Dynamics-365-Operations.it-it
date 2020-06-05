---
title: Spese interaziendali
description: Un lavoratore assunto da una persona giuridica in un'organizzazione può eseguire il lavoro per un'altra persona giuridica nella stessa organizzazione. In questo caso, è possibile utilizzare la funzionalità interaziendale spese per assegnare le spese del lavoratore alla persona giuridica per la quale è stato eseguito il lavoro.
author: ShylaThompson
manager: AnnBe
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvParameters
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0967f23e4e1f8e0431c55d4d54554e7e90e2451c
ms.sourcegitcommit: 07e425707eb20730f10246a27799f4deeef93f97
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "3390886"
---
# <a name="intercompany-expenses"></a><span data-ttu-id="05012-104">Spese interaziendali</span><span class="sxs-lookup"><span data-stu-id="05012-104">Intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05012-105">Un lavoratore assunto da una persona giuridica in un'organizzazione può eseguire il lavoro per un'altra persona giuridica nella stessa organizzazione.</span><span class="sxs-lookup"><span data-stu-id="05012-105">A worker who is employed by one legal entity in an organization might perform work for another legal entity in the same organization.</span></span> <span data-ttu-id="05012-106">In questo caso, è possibile utilizzare la funzionalità interaziendale spese per assegnare le spese del lavoratore alla persona giuridica per la quale è stato eseguito il lavoro.</span><span class="sxs-lookup"><span data-stu-id="05012-106">In this situation, you can use the intercompany expense feature to assign the worker’s expenses to the legal entity for which the work was performed.</span></span> <span data-ttu-id="05012-107">La persona giuridica che impiega il lavoratore è definita persona giuridica offerente.</span><span class="sxs-lookup"><span data-stu-id="05012-107">The legal entity that employs the worker is called the loaning legal entity.</span></span> <span data-ttu-id="05012-108">La persona giuridica per cui il lavoratore sostiene le spese viene chiamata persona giuridica richiedente.</span><span class="sxs-lookup"><span data-stu-id="05012-108">The legal entity for which the worker incurs expenses is called the borrowing legal entity.</span></span> 

<span data-ttu-id="05012-109">Prima che un lavoratore possa creare e inviare le spese di lavoro eseguito per una persona giuridica diversa, per la persona giuridica offerente. selezionare l'opzione **Consenti righe spese aziendali** nella pagina **Parametri di Gestione spese**.</span><span class="sxs-lookup"><span data-stu-id="05012-109">Before a worker can create and submit expenses for work that is performed for a different legal entity, in the loaning legal entity, on the **Expense management parameters** page, select the **Allow intercompany expense lines** option.</span></span> 

## <a name="tax-posting-for-intercompany-expenses"></a><span data-ttu-id="05012-110">Registrazione imposta per spese interaziendali</span><span class="sxs-lookup"><span data-stu-id="05012-110">Tax posting for intercompany expenses</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05012-111">Se desideri utilizzare i gruppi fiscali associati all'entità legale (fonte) del prestito anziché all'entità legale (destinazione) del prestito nella nota spese, devi configurarla nell'impostazione dei codici IVA della Contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="05012-111">If you want to use tax groups that are associated with the loaning (source) legal entity instead of the borrowing (destination) legal entity in your expense report, you will need to configure this in the General ledger sales tax set up.</span></span> <span data-ttu-id="05012-112">Quando il parametro Contabilità generale, **Persona giuridica per la registrazione dell'IVA interaziendale** è impostato su **Fonte** e **Applica regole di tassazione IVA** è impostato su **No**, verrà utilizzata la combinazione fiscale per l'entità giuridica prestante.</span><span class="sxs-lookup"><span data-stu-id="05012-112">When the General ledger parameter, **Legal entity for intercompany tax posting** is set to **Source** and **Apply sales tax taxation rules** is set to **No**, the tax combination for the loaning legal entity will be used.</span></span> <span data-ttu-id="05012-113">Quando lo stesso parametro è impostato su **Destinazione**, verrà utilizzata la combinazione fiscale per l'assunzione dell'entità giuridica.</span><span class="sxs-lookup"><span data-stu-id="05012-113">When the same parameter is set to **Destination**, the tax combination for borrowing legal entity will be used.</span></span> <span data-ttu-id="05012-114">Per le persone giuridiche negli Stati Uniti, quando il parametro è impostato su **Fonte**, il campo **IVA a credito** deve essere anche configurato nella nuova pagina **Gruppi registrazione contabile**.</span><span class="sxs-lookup"><span data-stu-id="05012-114">For legal entities in the United States, when the parameter is set to **Source**, the **Sales tax receivable** field must also be configured on the new **Ledger posting groups** page.</span></span> <span data-ttu-id="05012-115">Il motore di contabilità utilizzerà le informazioni da questo campo per l'immissione contabile relativa alle imposte.</span><span class="sxs-lookup"><span data-stu-id="05012-115">The accounting engine will use the information from this field for tax related accounting entry.</span></span>   
<span data-ttu-id="05012-116">Il comportamento è coerente per le righe di spesa registrate con o senza progetto.</span><span class="sxs-lookup"><span data-stu-id="05012-116">The behavior is consistent for expense lines posted with or without a project.</span></span>  
