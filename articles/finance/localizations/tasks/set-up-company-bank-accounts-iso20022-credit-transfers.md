---
title: Impostare i conti bancari della società per i bonifici ISO20022
description: Questa procedura descrive come impostare le informazioni sui conti bancari specifici della società necessarie per la generazione del file di pagamento.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5e121ce7d87ee50a4e6b367a170eea4375d64fb3
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3144878"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="ee0c5-103">Impostare i conti bancari della società per i bonifici ISO20022</span><span class="sxs-lookup"><span data-stu-id="ee0c5-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ee0c5-104">Questa procedura descrive come impostare le informazioni sui conti bancari specifici della società necessarie per la generazione del file di pagamento.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="ee0c5-105">Si imposteranno le informazioni richieste per generare il formato di bonifico ISO 20022 ma in base al formato potrebbero essere necessarie altre informazioni, ad esempio l'ID società o il Codice di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="ee0c5-106">La società di dati dimostrativi utilizzata per creare questa procedura è DEMF.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="ee0c5-107">Si tratta della seconda procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="ee0c5-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="ee0c5-109">Impostare i codici SWIFT e IBAN</span><span class="sxs-lookup"><span data-stu-id="ee0c5-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="ee0c5-110">Andare a Gestione banche e di cassa > Conti bancari.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="ee0c5-111">Utilizzare il filtro rapido per applicare un filtro al campo Conto bancario in base al valore "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="ee0c5-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="ee0c5-112">Fare clic su DEMF OPER per aprire i dettagli del conto bancario.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="ee0c5-113">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-113">Click Edit.</span></span>
5. <span data-ttu-id="ee0c5-114">Espandere la sezione Identificazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="ee0c5-115">Nel campo IBAN digitare "DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="ee0c5-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="ee0c5-116">Nel campo Codice SWIFT digitare "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="ee0c5-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="ee0c5-117">Si noti che SWIFT\BIC non è necessario per numerosi formati di pagamento, tuttavia è consigliabile registrarli per un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="ee0c5-118">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="ee0c5-119">Impostare un conto bancario per la persona giuridica</span><span class="sxs-lookup"><span data-stu-id="ee0c5-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="ee0c5-120">Andare ad Amministrazione organizzazione > Organizzazioni > Persone giuridiche.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="ee0c5-121">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-121">Click Edit.</span></span>
3. <span data-ttu-id="ee0c5-122">Espandere la sezione Informazioni conto bancario.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="ee0c5-123">Nel campo Conto bancario immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="ee0c5-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="ee0c5-124">Click Save.</span></span>

