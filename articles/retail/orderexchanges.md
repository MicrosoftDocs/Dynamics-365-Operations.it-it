---
title: Configurare ed elaborare uno scambio in un ordine di reso
description: In questo argomento viene descritto come configurare uno scambio su un reso in Microsoft Dynamics 365 for Retail.
author: josaw1
manager: AnnBe
ms.date: 11/12/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 5a0a6a060a1b4a4d5a80c797f61b212a828d2f04
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1517101"
---
# <a name="configure-and-process-an-exchange-on-a-return-order"></a><span data-ttu-id="cf6d4-103">Configurare ed elaborare uno scambio in un ordine di reso</span><span class="sxs-lookup"><span data-stu-id="cf6d4-103">Configure and process an exchange on a return order</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="cf6d4-104">Nelle versioni precedenti di Microsoft Dynamics 365 for Retail, i resi a fronte degli ordini cliente venivano elaborati tramite il documento dell'ordine di reso in Retail Headquarters.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-104">In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail Headquarters.</span></span> <span data-ttu-id="cf6d4-105">Tuttavia, il documento dell'ordine di reso può essere utilizzato per elaborare solo i prodotti resi.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-105">However, the return order document can be used to process only products that are being returned.</span></span> <span data-ttu-id="cf6d4-106">I prodotti resi sono indicati da una quantità negativa nelle righe dell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-106">The returned products are indicated by a negative quantity on the return order lines.</span></span> <span data-ttu-id="cf6d4-107">Di contro, le vendite vengono contrassegnate da una quantità positiva.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-107">By contrast, sales are indicated by a positive quantity.</span></span> <span data-ttu-id="cf6d4-108">Tuttavia, il documento dell'ordine di reso non supporta le quantità positive.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-108">However, the return order document doesn't support positive quantities.</span></span> <span data-ttu-id="cf6d4-109">A causa di questa limitazione, le versioni precedenti di Retail non supportavano scenari in cui gli scambi di prodotto sono effettuati utilizzando il documento dell'ordine di reso.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-109">Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</span></span>

<span data-ttu-id="cf6d4-110">Tuttavia, è stata aggiunta una funzionalità per supportare gli scenari in cui gli scambi vengono effettuati sugli ordini di reso.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-110">However, functionality has been added to support scenarios where exchanges are done on return orders.</span></span> <span data-ttu-id="cf6d4-111">Retail utilizza ora il documento dell'ordine cliente anziché il documento dell'ordine di reso per elaborare questi tipi di transazioni.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-111">Retail now uses the sales order document instead of the return order document to process these types of transactions.</span></span>

## <a name="configure-retail-to-support-exchanges-on-return-orders"></a><span data-ttu-id="cf6d4-112">Configurare Retail per supportare gli scambi sugli ordini di reso</span><span class="sxs-lookup"><span data-stu-id="cf6d4-112">Configure Retail to support exchanges on return orders</span></span>

<span data-ttu-id="cf6d4-113">Seguire questi passaggi per configurare il sistema in modo da supportare cambi sugli ordini di reso.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-113">Follow these steps to configure the system to support exchanges on return orders.</span></span>

1. <span data-ttu-id="cf6d4-114">Accedere a **Vendita al dettaglio \> Impostazione sedi centrali \> Parametri \> Parametri Retail**.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-114">Go to **Retail \> Headquarters setup \> Parameters \> Retail parameters**.</span></span> <span data-ttu-id="cf6d4-115">Nella Scheda dettaglio **Ordini cliente**, impostare l'opzione **Elabora ordini di reso come ordini cliente** su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-115">On the **Customer orders** FastTab, set the **Process return orders as sales orders** option to **Yes**.</span></span>
2. <span data-ttu-id="cf6d4-116">Eseguire il processo **Programmazione di distribuzione configurazione globale** (**1110**).</span><span class="sxs-lookup"><span data-stu-id="cf6d4-116">Run the **Global configuration distribution schedule** job (**1110**).</span></span>

## <a name="make-an-exchange"></a><span data-ttu-id="cf6d4-117">Eseguire uno scambio</span><span class="sxs-lookup"><span data-stu-id="cf6d4-117">Make an exchange</span></span>

<span data-ttu-id="cf6d4-118">Dopo che il sistema è configurato come descritto nella sezione precedente, l'utente di POS selezionerà comunque un ordine cliente o una fattura di vendita per elaborare un reso, come nelle versioni precedenti di Retail.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-118">After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</span></span> <span data-ttu-id="cf6d4-119">Tuttavia, dopo che i resi vengono aggiunti al carrello, l'utente potrà aggiungere nuove righe di vendita al carrello.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-119">However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</span></span>

<span data-ttu-id="cf6d4-120">Per le nuove righe di vendita, l'utente deve definire tutti gli attributi necessari per l'elaborazione di una riga di ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-120">For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</span></span> <span data-ttu-id="cf6d4-121">Tali attributi includono il metodo di consegna e l'ubicazione di evasione.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-121">These attributes include the delivery method and fulfillment location.</span></span> <span data-ttu-id="cf6d4-122">Il pagamento dovuto per la transazione sarà il netto delle righe dell'ordine di reso e righe ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-122">The payment that is due for the transaction will be a net of the return order lines and sales order lines.</span></span> <span data-ttu-id="cf6d4-123">Quando un pagamento viene offerto per la transazione, l'ordine di reso verrà registrato come documento dell'ordine cliente in Retail Headquarters e il sistema fatturerà immediatamente le righe di reso.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-123">When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail Headquarters, and the system will immediately invoice the return lines.</span></span>

<span data-ttu-id="cf6d4-124">Per una maggiore visibilità dei vari importi relativi al carrello, tre nuovi campi di importi sono stati aggiunti al carrello.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-124">To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</span></span> <span data-ttu-id="cf6d4-125">È possibile utilizzare la finestra di progettazione della schermata per rendere disponibili i nuovi campi nell'interfaccia utente di POS (UI).</span><span class="sxs-lookup"><span data-stu-id="cf6d4-125">You can use the screen designer to make these new fields available in the POS user interface (UI).</span></span>

- <span data-ttu-id="cf6d4-126">**Deposito applicato**: l'importo del deposito applicato in una transazione quando l'utente effettua un prelievo dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-126">**Deposit applied** – The deposit amount that is applied on a transaction when the user does a customer order pickup.</span></span> <span data-ttu-id="cf6d4-127">Se non esiste alcuna sostituzione deposito e viene configurato un deposito del 10 per cento, l'importo riportato in questo campo è 90 percento dell'importo totale dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-127">If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</span></span>
- <span data-ttu-id="cf6d4-128">**Importo esecuzione**: l'importo totale per le righe in cui la modalità di consegna è stata impostata su **Eseguire** quando l'ordine cliente è stato creato o modificato o durante lo scambio degli ordini cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-128">**Carry out amount** – The total amount for lines where the delivery mode was set to **Carry out** when the customer order was created or edited, or during a customer order exchange.</span></span> <span data-ttu-id="cf6d4-129">L'importo in questo campo include IVA e spese.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-129">The amount in this field includes taxes and charges.</span></span>
- <span data-ttu-id="cf6d4-130">**Importo reso**: l'importo totale per le righe con le quantità negative durante lo scambio dell'ordine cliente.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-130">**Return amount** – The total amount for lines that have negative quantities during the customer order exchange.</span></span> <span data-ttu-id="cf6d4-131">L'importo in questo campo include IVA e spese.</span><span class="sxs-lookup"><span data-stu-id="cf6d4-131">The amount in this field includes taxes and charges.</span></span>
