---
title: Pagina dell'elenco transazioni fornitore
description: Questo argomento fornisce informazioni sulla pagina dell'elenco delle transazioni fornitore per Microsoft Dynamics 365 for Finance and Operations.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendTrans
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.translationtype: HT
ms.sourcegitcommit: 98ed3378ab05c0c69c9e5b2a82310113a81c2264
ms.openlocfilehash: 1ef7d97f059801f2fb2c0d451546b57055208f81
ms.contentlocale: it-it
ms.lasthandoff: 08/31/2018

---

# <a name="vendor-transaction-list-page"></a><span data-ttu-id="fc683-103">Pagina dell'elenco transazioni fornitore</span><span class="sxs-lookup"><span data-stu-id="fc683-103">Vendor transaction list page</span></span>

[!include [banner](../includes/banner.md)]

## <a name="view-settlements"></a><span data-ttu-id="fc683-104">Visualizza liquidazioni</span><span class="sxs-lookup"><span data-stu-id="fc683-104">View settlements</span></span>

<span data-ttu-id="fc683-105">La scheda **Visualizza liquidazioni** del riquadro azioni offre un accesso rapido allo storico delle liquidazioni e altre informazioni sull'intera transazione delle liquidazioni.</span><span class="sxs-lookup"><span data-stu-id="fc683-105">The **View settlements** tab on the action pane provides quick access to settlement history and more information about the whole settlement transaction.</span></span> <span data-ttu-id="fc683-106">È inoltre possibile mostrare altre transazioni che sono correlate alla transazione selezionata, perché fanno parte della stessa liquidazione o perché sono pagamenti creati nello stesso giornale di registrazione pagamenti.</span><span class="sxs-lookup"><span data-stu-id="fc683-106">You can also show additional transactions that are related to the selected transaction, either because they were part of the same settlement or because they are payments that were created in the same payment journal.</span></span>

1. <span data-ttu-id="fc683-107">Selezionare **Contabilità fornitori \> Tutti i fornitori**.</span><span class="sxs-lookup"><span data-stu-id="fc683-107">Select **Accounts payable \> All vendors**.</span></span>
2. <span data-ttu-id="fc683-108">Selezionare un fornitore con transazioni e quindi selezionare **Fornitore \> Transazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc683-108">Select a vendor that has transactions, and then select **Vendor \> Transactions**.</span></span>
3. <span data-ttu-id="fc683-109">Selezionare una transazione da cercare.</span><span class="sxs-lookup"><span data-stu-id="fc683-109">Select a transaction to research.</span></span>
4. <span data-ttu-id="fc683-110">Selezionare la scheda **Visualizza liquidazioni** nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="fc683-110">Select the **View settlements** tab on the action pane.</span></span>

    <span data-ttu-id="fc683-111">Viene visualizzata la finestra di dialogo **Visualizza liquidazioni** che mostra la transazione selezionata e tutti i documento che sono stati liquidati ad essa collegati.</span><span class="sxs-lookup"><span data-stu-id="fc683-111">The **View settlements** dialog box opens and shows the selected transaction and all documents that are settled against it.</span></span> <span data-ttu-id="fc683-112">Questa finestra di dialogo assomiglia alla visualizzazione dello storico delle liquidazioni, ma include tutti i documenti correlati.</span><span class="sxs-lookup"><span data-stu-id="fc683-112">This dialog box resembles the settlement history view, but it includes all related documents.</span></span>

5. <span data-ttu-id="fc683-113">È possibile eseguire varie attività da questa finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fc683-113">You can perform various tasks from this dialog box.</span></span> <span data-ttu-id="fc683-114">Selezionare uno o più giustificativi e quindi selezionare uno dei menu seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc683-114">Select one or more vouchers, and then select one of the following menus:</span></span>

   - <span data-ttu-id="fc683-115">**Visualizza contabilità** - Vengono visualizzati tutti i giustificativi che sono correlati ai documenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="fc683-115">**View accounting** – All vouchers that are related to the selected documents appear.</span></span> <span data-ttu-id="fc683-116">Selezionare **Chiudi** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fc683-116">Select **Close** to close the dialog box.</span></span>
   - <span data-ttu-id="fc683-117">**Esporta** - Esportare i giustificativi selezionati in Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="fc683-117">**Export** – Export the selected vouchers to Microsoft Excel.</span></span>
   - <span data-ttu-id="fc683-118">**Visualizza pagamenti correlati** - Vengono visualizzate tutte le transazioni del giornale di registrazione pagamenti che sono state create nel giornale di registrazione pagamenti che è correlato al documento selezionato.</span><span class="sxs-lookup"><span data-stu-id="fc683-118">**View related payments** – All the payment journal transactions that were created in the payment journal that is related to the selected document appear.</span></span> <span data-ttu-id="fc683-119">Vengono inoltre visualizzate tutte le liquidazioni correlate a tali pagamenti.</span><span class="sxs-lookup"><span data-stu-id="fc683-119">In addition, all the settlements that are related to those payments appear.</span></span> <span data-ttu-id="fc683-120">Anche l'etichetta di questo menu cambia in **Visualizza liquidazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc683-120">The label of this menu also changes to **View settlements**.</span></span> <span data-ttu-id="fc683-121">Selezionare **Visualizza liquidazioni** per mostrare solo le transazioni che erano visualizzate la prima volta che è stata aperta la finestra di dialogo **Visualizza liquidazioni**.</span><span class="sxs-lookup"><span data-stu-id="fc683-121">Select **View settlements** to show only the transactions that were shown when you first opened the  **View settlements** dialog box.</span></span>
    - <span data-ttu-id="fc683-122">**Liquida transazioni** - Questo menu viene visualizzato se il documento originale che era selezionato non è stato completamente liquidato.</span><span class="sxs-lookup"><span data-stu-id="fc683-122">**Settle transactions** – This menu appears if the original document that was selected wasn't fully settled.</span></span> <span data-ttu-id="fc683-123">Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Liquida transazioni**, nella quale è possibile selezionare le transazioni da liquidare.</span><span class="sxs-lookup"><span data-stu-id="fc683-123">When you select it, the **Settle transactions** dialog box appears, where you can select transactions for settlement.</span></span>
    - <span data-ttu-id="fc683-124">**Annulla liquidazioni** - Questo menu viene visualizzato se il documento originale che era stato selezionato era stato completamente liquidato.</span><span class="sxs-lookup"><span data-stu-id="fc683-124">**Undo settlements** – This menu appears if the original document that was selected was fully settled.</span></span> <span data-ttu-id="fc683-125">Quando si seleziona questo menu, viene visualizzata la finestra di dialogo **Annulla liquidazioni** nella quale è possibile annullare le liquidazioni eseguite per il documento.</span><span class="sxs-lookup"><span data-stu-id="fc683-125">When you select it, the **Undo settlements** dialog box appears, where you can undo the settlements that were done for that document.</span></span>

