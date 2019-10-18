---
title: Specificare il tasso di cambio incrociato
description: Questo argomento include informazioni sui tassi di cambio incrociato in Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 05/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 146794557a3a6ba1801598fe6b814e209d9f5fc6
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178535"
---
# <a name="specify-the-cross-rate"></a><span data-ttu-id="1da2f-103">Specificare il tasso di cambio incrociato</span><span class="sxs-lookup"><span data-stu-id="1da2f-103">Specify the cross rate</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1da2f-104">In questo argomento viene illustrato lo scopo di un tasso di cambio incrociato e come specificare il tasso di cambio incrociato quando viene liquidato un pagamento con una fattura.</span><span class="sxs-lookup"><span data-stu-id="1da2f-104">This topic explains the purpose of a cross rate, and how to specify the cross rate when you settle a payment with an invoice.</span></span> <span data-ttu-id="1da2f-105">Utilizzare un tasso di cambio incrociato quando sono applicabili tutti i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="1da2f-105">Use a cross rate when all of the following criteria apply:</span></span> 
-   <span data-ttu-id="1da2f-106">Si liquida un pagamento con una fattura.</span><span class="sxs-lookup"><span data-stu-id="1da2f-106">You are settling a payment with an invoice.</span></span> 
-   <span data-ttu-id="1da2f-107">La riga di pagamento e la riga fattura utilizzano valute diverse.</span><span class="sxs-lookup"><span data-stu-id="1da2f-107">The payment line and the invoice line use different currencies.</span></span> 
-   <span data-ttu-id="1da2f-108">Nessuna valuta è quella di contabilizzazione.</span><span class="sxs-lookup"><span data-stu-id="1da2f-108">Neither currency is the accounting currency.</span></span> 

<span data-ttu-id="1da2f-109">Il tasso di cambio incrociato non viene utilizzato per calcolare la conversione di valuta di transazione di pagamento nella valuta di contabilizzazione pagamento.</span><span class="sxs-lookup"><span data-stu-id="1da2f-109">The cross rate is not used to calculate the payment transaction currency translation to the payment accounting currency.</span></span> <span data-ttu-id="1da2f-110">I tassi di cambio delle tabelle del tasso di cambio vengono invece recuperati per calcolare il valore dell'importo valuta della transazione di pagamento e dell'importo nella valuta di contabilizzazione pagamento.</span><span class="sxs-lookup"><span data-stu-id="1da2f-110">Instead, the exchange rates from the exchange rate tables are retrieved to calculate the value of the payment transaction currency amount and the payment accounting currency amount.</span></span> 

<span data-ttu-id="1da2f-111">Ad esempio, la valuta di contabilizzazione è USD, la valuta della fattura è CAD e la valuta del pagamento è EUR.</span><span class="sxs-lookup"><span data-stu-id="1da2f-111">For example, the accounting currency is USD, the invoice currency is CAD, and the payment currency is EUR.</span></span> <span data-ttu-id="1da2f-112">Il tasso di cambio incrociato consente di immettere un tasso di cambio per passare direttamente dal CAD all'EUR senza che sia necessario passare attraverso USD.</span><span class="sxs-lookup"><span data-stu-id="1da2f-112">The cross rate lets you enter an exchange rate to translate directly between CAD and EUR, and not have to translate through USD.</span></span> <span data-ttu-id="1da2f-113">Al momento della selezione dei una fattura e di un pagamento primario è possibile immettere un tasso di cambio incrociato per la riga di fattura.</span><span class="sxs-lookup"><span data-stu-id="1da2f-113">When you select an invoice and a primary payment, you can enter a cross rate for the invoice line.</span></span> <span data-ttu-id="1da2f-114">Questo tasso è il tasso di cambio tra le valute di queste transazioni alla data della liquidazione.</span><span class="sxs-lookup"><span data-stu-id="1da2f-114">The cross rate is the exchange rate between the currencies for those transactions, as of the settlement date.</span></span>

1.  <span data-ttu-id="1da2f-115">Passare a una delle pagine seguenti:</span><span class="sxs-lookup"><span data-stu-id="1da2f-115">Go to one of the following pages:</span></span>
- <span data-ttu-id="1da2f-116">**Contabilità clienti > Comune > Clienti > Tutti i clienti**</span><span class="sxs-lookup"><span data-stu-id="1da2f-116">**Accounts receivable > Common > Customers > All customers**</span></span> 
- <span data-ttu-id="1da2f-117">**Contabilità fornitori > Comune > Fornitori > Tutti i fornitori**</span><span class="sxs-lookup"><span data-stu-id="1da2f-117">**Accounts payable > Common > Vendors > All vendors**</span></span> 
- <span data-ttu-id="1da2f-118">**Approvvigionamento > Comune > Fornitori > Tutti i fornitori**</span><span class="sxs-lookup"><span data-stu-id="1da2f-118">**Procurement and sourcing > Common > Vendors > All vendors**</span></span>
2.  <span data-ttu-id="1da2f-119">Selezionare il cliente o il fornitore di cui si desidera compensare le transazioni aperte.</span><span class="sxs-lookup"><span data-stu-id="1da2f-119">Select the customer or vendor whose open transactions you are settling.</span></span> 
3.  <span data-ttu-id="1da2f-120">Per un cliente, nella pagina elenco **Tutti i clienti**, passare a **Raccolta > Liquida transazioni aperte**.</span><span class="sxs-lookup"><span data-stu-id="1da2f-120">For a customer, on the **All customers** list page, go to **Collect > Settle open transactions**.</span></span> <span data-ttu-id="1da2f-121">Per un fornitore, nella pagina elenco **Tutti i fornitori**, passare a **Fattura > Liquida transazioni aperte**.</span><span class="sxs-lookup"><span data-stu-id="1da2f-121">For a vendor, on the **All vendors** list page, go to **Invoice > Settle open transactions**.</span></span> 
4.  <span data-ttu-id="1da2f-122">Selezionare la transazione corrispondente al pagamento primario, quindi fare clic su **Contrassegna pagamento**.</span><span class="sxs-lookup"><span data-stu-id="1da2f-122">Select the transaction that is the primary payment, and then click **Mark payment**.</span></span> <span data-ttu-id="1da2f-123">Verrà selezionata la casella di controllo nella colonna **Contrassegna** e verrà visualizzata un'icona informativa nella colonna **Pagamento primario**.</span><span class="sxs-lookup"><span data-stu-id="1da2f-123">The check box in the **Mark** column is selected, and an information icon is shown in the **Primary payment** column.</span></span> 
5.  <span data-ttu-id="1da2f-124">Nel campo **Tasso di cambio incrociato**, immettere il tasso di cambio tra la valuta della fattura e la valuta del pagamento alla data di liquidazione.</span><span class="sxs-lookup"><span data-stu-id="1da2f-124">In the **Cross rate** field, enter the exchange rate between the invoice currency and the payment currency, as of the settlement date.</span></span> 
