---
title: Impostare gli assegni postdatati
description: In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 22e67aa051b5ea8267df7efac40e007d0f11a83d
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141110"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="afafb-103">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="afafb-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="afafb-104">In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="afafb-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="afafb-105">È inoltre possibile specificare i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="afafb-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="afafb-106">Gli assegni postdatati che sono emessi per effettuare e ricevere pagamenti in una data futura.</span><span class="sxs-lookup"><span data-stu-id="afafb-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="afafb-107">È possibile specificare se l'assegno deve essere riportato nei libri contabili prima della relativa data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="afafb-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="afafb-108">Il ruolo di questa procedura è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="afafb-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="afafb-109">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="afafb-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="afafb-110">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="afafb-110">Set up postdated checks</span></span>
1. <span data-ttu-id="afafb-111">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="afafb-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="afafb-112">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="afafb-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="afafb-113">Selezionare o deselezionare la casella di controllo Abilita assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="afafb-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="afafb-114">Selezionare o deselezionare la casella di controllo Inserimenti nel giornale di registrazione per assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="afafb-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="afafb-115">Nel campo Conto di compensazione per assegni emessi specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="afafb-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="afafb-116">Nel campo Conto di compensazione per assegni ricevuti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="afafb-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="afafb-117">Nel campo Giornale di registrazione generale per voci di compensazione immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="afafb-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="afafb-118">Nel campo Trasferisci assegni postdatati a questo giornale di registrazione pagamenti fornitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="afafb-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="afafb-119">Nel campo Conto di compensazione per ritenuta d'acconto specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="afafb-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="afafb-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="afafb-120">Click Save.</span></span>
11. <span data-ttu-id="afafb-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="afafb-121">Close the page.</span></span>
12. <span data-ttu-id="afafb-122">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="afafb-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="afafb-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="afafb-123">Click New.</span></span>
14. <span data-ttu-id="afafb-124">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="afafb-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="afafb-125">Selezionare l'opzione Registrazione compensazione assegni postdatati per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="afafb-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="afafb-126">Nel campo Tipo di conto selezionare "Banca".</span><span class="sxs-lookup"><span data-stu-id="afafb-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="afafb-127">Il conto di contropartita del metodo di pagamento sarà una banca.</span><span class="sxs-lookup"><span data-stu-id="afafb-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="afafb-128">Nel campo Conto pagamenti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="afafb-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="afafb-129">Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="afafb-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="afafb-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="afafb-130">Click Save.</span></span>
19. <span data-ttu-id="afafb-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="afafb-131">Close the page.</span></span>

