---
title: Pagina dell'elenco transazioni cliente
description: Questo argomento fornisce informazioni sulla pagina dell'elenco delle transazioni cliente per Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: e828cb292ad48bb4690117b41589b25edcdf28bc
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2018

---

# <a name="customer-transaction-list-page"></a><span data-ttu-id="30287-103">Pagina dell'elenco transazioni cliente</span><span class="sxs-lookup"><span data-stu-id="30287-103">Customer transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="30287-104">Visualizza liquidazioni</span><span class="sxs-lookup"><span data-stu-id="30287-104">View settlements</span></span>

<span data-ttu-id="30287-105">La scheda **Visualizza liquidazioni** del riquadro azioni offre un accesso rapido allo storico delle liquidazioni e altre informazioni sull'intera transazione delle liquidazioni.</span><span class="sxs-lookup"><span data-stu-id="30287-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="30287-106">È inoltre possibile mostrare altre transazioni che sono correlate alla transazione selezionata, perché fanno parte della stessa liquidazione o perché sono pagamenti creati nello stesso giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="30287-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="30287-107">Selezionare **Contabilità clienti \> Clienti**.</span><span class="sxs-lookup"><span data-stu-id="30287-107">Select **Accounts receivable \> Customers**.</span></span>
2. <span data-ttu-id="30287-108">Selezionare un cliente con transazioni e quindi selezionare **Cliente \> Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="30287-108">Select a customer that has transactions, and then select **Customer \> Transactions**.</span></span>
3. <span data-ttu-id="30287-109">Selezionare una transazione da cercare.</span><span class="sxs-lookup"><span data-stu-id="30287-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="30287-110">Selezionare la scheda **Visualizza liquidazioni** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="30287-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="30287-111">La finestra di dialogo **Visualizza liquidazioni** mostra la transazione selezionata e tutti i documento che sono stati liquidati ad essa collegati.</span><span class="sxs-lookup"><span data-stu-id="30287-111">The **View settlements** dialog box shows the selected transaction and all documents that have been settled against it.</span></span> <span data-ttu-id="30287-112">Questa finestra di dialogo assomiglia alla visualizzazione dello storico delle liquidazioni, ma include tutti i documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="30287-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span> 

5. <span data-ttu-id="30287-113">È possibile eseguire varie attività da questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="30287-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="30287-114">Selezionare uno o più giustificativi e quindi selezionare uno dei menu seguenti:</span><span class="sxs-lookup"><span data-stu-id="30287-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="30287-115">**Visualizza contabilità** - Vengono visualizzati tutti i giustificativi che sono correlati ai documenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="30287-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="30287-116">Selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="30287-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="30287-117">**Esporta** - Esportare i giustificativi selezionati in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="30287-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="30287-118">**Visualizza pagamenti correlati** - Vengono visualizzate tutte le transazioni del giornale di registrazione pagamenti che sono state create nel giornale di registrazione pagamenti che è correlato al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="30287-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="30287-119">Vengono inoltre visualizzate tutte le liquidazioni correlate a tali pagamenti.</span><span class="sxs-lookup"><span data-stu-id="30287-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="30287-120">Anche l'etichetta di questo menu cambia in **Visualizza liquidazioni**.</span><span class="sxs-lookup"><span data-stu-id="30287-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="30287-121">Selezionare **Visualizza liquidazioni** per mostrare solo le transazioni che erano visualizzate la prima volta che è stata aperta la finestra di dialogo **Visualizza liquidazioni**.</span><span class="sxs-lookup"><span data-stu-id="30287-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="30287-122">**Liquida transazioni** - Questo menu viene visualizzato se il documento originale che era selezionato non è stato completamente liquidato.</span><span class="sxs-lookup"><span data-stu-id="30287-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="30287-123">Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Liquida transazioni**, nella quale è possibile selezionare le transazioni da liquidare.</span><span class="sxs-lookup"><span data-stu-id="30287-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="30287-124">**Annulla liquidazioni** - Questo menu viene visualizzato se il documento originale che era stato selezionato era stato completamente liquidato.</span><span class="sxs-lookup"><span data-stu-id="30287-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="30287-125">Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Annulla liquidazioni** nella quale è possibile annullare le liquidazioni eseguite per il documento.</span><span class="sxs-lookup"><span data-stu-id="30287-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>
    

