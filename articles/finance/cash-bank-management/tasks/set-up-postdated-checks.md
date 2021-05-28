---
title: Impostare gli assegni postdatati
description: In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d0d4afd74f9a0f9018629fa92ab6595bfa94f973
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026207"
---
# <a name="set-up-postdated-checks"></a><span data-ttu-id="41016-103">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="41016-103">Set up postdated checks</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="41016-104">In questo argomento viene illustrato come specificare se registrare gli inserimenti nel giornale per gli assegni postdatati e quali giornali di registrazione utilizzare per cancellare le voci e i pagamenti fornitore.</span><span class="sxs-lookup"><span data-stu-id="41016-104">This topic explains how to specify whether to post journal entries for postdated checks and which posting journals to use for clearing entries and vendor payments.</span></span> <span data-ttu-id="41016-105">È inoltre possibile specificare i conti di compensazione per gli assegni emessi, gli assegni ricevuti e la ritenuta d'acconto.</span><span class="sxs-lookup"><span data-stu-id="41016-105">You can also specify clearing accounts for issued checks, received checks, and withholding tax.</span></span> <span data-ttu-id="41016-106">Gli assegni postdatati che sono emessi per effettuare e ricevere pagamenti in una data futura.</span><span class="sxs-lookup"><span data-stu-id="41016-106">Postdated checks that are issued to make and receive payments on a future date.</span></span> <span data-ttu-id="41016-107">È possibile specificare se l'assegno deve essere riportato nei libri contabili prima della relativa data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="41016-107">You can specify whether the check must be reflected in the accounting books before its maturity date.</span></span>



<span data-ttu-id="41016-108">Il ruolo di questa procedura è Tesoriere.</span><span class="sxs-lookup"><span data-stu-id="41016-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="41016-109">Questa procedura utilizza la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="41016-109">This procedure uses the USMF demo company.</span></span>


## <a name="set-up-postdated-checks"></a><span data-ttu-id="41016-110">Impostare gli assegni postdatati</span><span class="sxs-lookup"><span data-stu-id="41016-110">Set up postdated checks</span></span>
1. <span data-ttu-id="41016-111">Andare a Gestione cassa e banche > Impostazioni > Parametri di gestione cassa e banche.</span><span class="sxs-lookup"><span data-stu-id="41016-111">Go to Cash and bank management > Setup > Cash and bank management parameters.</span></span>
2. <span data-ttu-id="41016-112">Fare clic sulla scheda Assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="41016-112">Click the Postdated checks tab.</span></span>
3. <span data-ttu-id="41016-113">Selezionare o deselezionare la casella di controllo Abilita assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="41016-113">Select or clear the Enable postdated checks check box.</span></span>
4. <span data-ttu-id="41016-114">Selezionare o deselezionare la casella di controllo Inserimenti nel giornale di registrazione per assegni postdatati.</span><span class="sxs-lookup"><span data-stu-id="41016-114">Select or clear the Post journal entries for postdated checks check box.</span></span>
5. <span data-ttu-id="41016-115">Nel campo Conto di compensazione per assegni emessi specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="41016-115">In the Clearing account for issued checks field, specify the desired values.</span></span>
6. <span data-ttu-id="41016-116">Nel campo Conto di compensazione per assegni ricevuti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="41016-116">In the Clearing account for received checks field, specify the desired values.</span></span>
7. <span data-ttu-id="41016-117">Nel campo Giornale di registrazione generale per voci di compensazione immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="41016-117">In the General journal for clearing entries field, type a value.</span></span>
8. <span data-ttu-id="41016-118">Nel campo Trasferisci assegni postdatati a questo giornale di registrazione pagamenti fornitore immettere un valore.</span><span class="sxs-lookup"><span data-stu-id="41016-118">In the Transfer postdated checks to this vendor payment journal field, type a value.</span></span>
9. <span data-ttu-id="41016-119">Nel campo Conto di compensazione per ritenuta d'acconto specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="41016-119">In the Withholding tax clearing account field, specify the desired values.</span></span>
10. <span data-ttu-id="41016-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="41016-120">Click Save.</span></span>
11. <span data-ttu-id="41016-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41016-121">Close the page.</span></span>
12. <span data-ttu-id="41016-122">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="41016-122">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
13. <span data-ttu-id="41016-123">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="41016-123">Click New.</span></span>
14. <span data-ttu-id="41016-124">Digitare un valore nel campo Metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="41016-124">In the Method of payment field, type a value.</span></span>
15. <span data-ttu-id="41016-125">Selezionare l'opzione Registrazione compensazione assegni postdatati per indicare che l'importo dell'assegno viene registrato in un conto di compensazione.</span><span class="sxs-lookup"><span data-stu-id="41016-125">Select the Postdated check clearing posting option to indicate that the check amount is posted to a clearing account.</span></span>
16. <span data-ttu-id="41016-126">Nel campo Tipo di conto selezionare "Banca".</span><span class="sxs-lookup"><span data-stu-id="41016-126">In the Account type field, select 'Bank'.</span></span>
    * <span data-ttu-id="41016-127">Il conto di contropartita del metodo di pagamento sarà una banca.</span><span class="sxs-lookup"><span data-stu-id="41016-127">The offset account of the payment method will be a bank.</span></span>  
17. <span data-ttu-id="41016-128">Nel campo Conto pagamenti specificare i valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="41016-128">In the Payment account field, specify the desired values.</span></span>
    * <span data-ttu-id="41016-129">Selezionare il conto bancario utilizzato per detrarre l'importo della fattura.</span><span class="sxs-lookup"><span data-stu-id="41016-129">Select the bank account that is used to deduct the invoice amount.</span></span>  
18. <span data-ttu-id="41016-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="41016-130">Click Save.</span></span>
19. <span data-ttu-id="41016-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="41016-131">Close the page.</span></span>
> [!NOTE]
> <span data-ttu-id="41016-132">Per poter registrare un assegno postdatato in un conto bancario quando la data della sessione è successiva o uguale alla data di scadenza, è necessario abilitare la funzionalità **Convalida della data di scadenza della registrazione del giornale di registrazione pagamenti con assegni postdatati sul conto bancario**.</span><span class="sxs-lookup"><span data-stu-id="41016-132">To be able to post a postdated check to a bank account when the session date is greater than or equal to the maturity date, you must enable the feature **Maturity date validation of posting payment journal with postdated checks to bank account**.</span></span> <span data-ttu-id="41016-133">Questa funzionalità consente di registrare giornali di registrazione pagamenti per fornitori o clienti con assegni postdatati, quando la data della sessione è successiva o uguale alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="41016-133">This feature allows you to post payment journals for vendors or customers with postdated checks, when the session date is greater than or equal to the maturity date.</span></span>
> 
> <span data-ttu-id="41016-134">Quando si imposta il **Metodo di pagamento** (**Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento**), non riempire il campo **Conto provvisorio**.</span><span class="sxs-lookup"><span data-stu-id="41016-134">When setting the **Method of payment** (**Accounts payable > Payment setup > Methods of payment**), do not fill in **Bridging account**.</span></span> <span data-ttu-id="41016-135">In questo caso, il conto di contropartita viene compilato con il conto bancario, impostato in **Metodo di pagamento**.</span><span class="sxs-lookup"><span data-stu-id="41016-135">In this case, the offset account is filled in with the bank account, which is set up in the **Method of payment**.</span></span>
>  
> <span data-ttu-id="41016-136">Quando la funzionalità è abilitata e la data della sessione è antecedente alla data di scadenza, viene visualizzato il seguente messaggio di errore durante la registrazione di un giornale di registrazione pagamenti: "La data di scadenza deve essere antecedente o uguale alla data della sessione se il tipo di conto di contropartita è Banca".</span><span class="sxs-lookup"><span data-stu-id="41016-136">When the feature is enabled and the session date is less than the maturity date, the following error message is displayed when posting a payment journal, "Maturity date must be less or equal to the session date if offset account type is Bank".</span></span> <span data-ttu-id="41016-137">Se la funzionalità non è abilitata, è possibile registrare un giornale di registrazione pagamenti con un assegno postdatato quando la data della sessione è inferiore alla data di scadenza.</span><span class="sxs-lookup"><span data-stu-id="41016-137">If the feature is not enabled, you can post a payment journal with a postdated check when the session date is less than the maturity date.</span></span>    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
