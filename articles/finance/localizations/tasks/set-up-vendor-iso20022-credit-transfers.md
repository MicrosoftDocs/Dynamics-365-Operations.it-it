---
title: Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022
description: Questa procedura descrive come impostare le informazioni sul fornitore e sul conto bancario specifico del fornitore necessarie per la generazione del bonifico ISO20022 o di qualsiasi altro file di pagamento fornitore.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b3a16d614efed0aafbf13fc59c17ab568811d82
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222041"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="05f1c-103">Impostare i fornitori e i conti bancari dei fornitori per i bonifici ISO20022</span><span class="sxs-lookup"><span data-stu-id="05f1c-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="05f1c-104">Questa procedura descrive come impostare le informazioni sul fornitore e sul conto bancario specifico del fornitore necessarie per la generazione del bonifico ISO20022 o di qualsiasi altro file di pagamento fornitore.</span><span class="sxs-lookup"><span data-stu-id="05f1c-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="05f1c-105">La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.</span><span class="sxs-lookup"><span data-stu-id="05f1c-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="05f1c-106">Si tratta della quarta procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="05f1c-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="05f1c-107">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="05f1c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="05f1c-108">Impostare i dettagli della banca</span><span class="sxs-lookup"><span data-stu-id="05f1c-108">Set up bank details</span></span>
1. <span data-ttu-id="05f1c-109">Andare a Contabilità fornitori > Fornitori > Tutti i fornitori.</span><span class="sxs-lookup"><span data-stu-id="05f1c-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="05f1c-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="05f1c-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="05f1c-111">Ad esempio, applicare un filtro al Conto fornitore in base al valore "DE-001".</span><span class="sxs-lookup"><span data-stu-id="05f1c-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="05f1c-112">Fare clic su DE-001 per aprire i dettagli del fornitore.</span><span class="sxs-lookup"><span data-stu-id="05f1c-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="05f1c-113">Nel riquadro azioni, fare clic su Fornitore.</span><span class="sxs-lookup"><span data-stu-id="05f1c-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="05f1c-114">Fare clic su Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="05f1c-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="05f1c-115">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="05f1c-115">Click Edit.</span></span>
    * <span data-ttu-id="05f1c-116">Se non è disponibile alcun conto bancario, è necessario crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="05f1c-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="05f1c-117">Nel campo Codice SWIFT digitare "COBADEFFXXX".</span><span class="sxs-lookup"><span data-stu-id="05f1c-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="05f1c-118">Nel campo IBAN digitare "DE36200400000628808808".</span><span class="sxs-lookup"><span data-stu-id="05f1c-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="05f1c-119">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="05f1c-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="05f1c-120">Impostare un metodo di pagamento per il fornitore</span><span class="sxs-lookup"><span data-stu-id="05f1c-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="05f1c-121">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="05f1c-121">Click Edit.</span></span>
2. <span data-ttu-id="05f1c-122">Espandere o comprimere la sezione Pagamento.</span><span class="sxs-lookup"><span data-stu-id="05f1c-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="05f1c-123">Nel campo Metodo fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="05f1c-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="05f1c-124">Nell'elenco fare clic sul collegamento nella riga SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="05f1c-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="05f1c-125">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="05f1c-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]