--- 
title: Impostare un metodo di pagamento per bonifico ISO20022
description: In questa procedura viene illustrato come impostare il metodo di pagamento del fornitore per bonifico ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici per generare un file.
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: bed51f8749dfa0264ad39f51f9ceb295ac46fe93
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="a486e-103">Impostare un metodo di pagamento per bonifico ISO20022</span><span class="sxs-lookup"><span data-stu-id="a486e-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="a486e-104">In questa procedura viene illustrato come impostare il metodo di pagamento del fornitore per bonifico ISO20022 o qualsiasi altro tipo di pagamento mediante la creazione di report elettronici per generare un file.</span><span class="sxs-lookup"><span data-stu-id="a486e-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="a486e-105">Prima di completare l'attività, è necessario esportare le configurazioni del formato impostare i conti di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a486e-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="a486e-106">Questa attività è stata creata utilizzando la società di dati dimostrativi DEMF.</span><span class="sxs-lookup"><span data-stu-id="a486e-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="a486e-107">Si tratta della terza procedura di cinque, che illustra il processo di pagamento fornitore utilizzando le configurazioni di creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="a486e-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="a486e-108">Questa procedura è per una funzionalità che è stata aggiunta in Dynamics 365 for Operations versione 1611.</span><span class="sxs-lookup"><span data-stu-id="a486e-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="a486e-109">Andare a Contabilità fornitori > Impostazione pagamenti > Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="a486e-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="a486e-110">Utilizzare il filtro rapido per trovare i record.</span><span class="sxs-lookup"><span data-stu-id="a486e-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="a486e-111">Ad esempio, applicare un filtro al campo Metodo di pagamento in base al valore "SEPA CT".</span><span class="sxs-lookup"><span data-stu-id="a486e-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="a486e-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="a486e-112">Click Edit.</span></span>
4. <span data-ttu-id="a486e-113">Nel campo Periodo selezionare "Totale".</span><span class="sxs-lookup"><span data-stu-id="a486e-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="a486e-114">Nel campo Tipo di pagamento selezionare "Pagamento elettronico".</span><span class="sxs-lookup"><span data-stu-id="a486e-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="a486e-115">Espandere la sezione Formati file.</span><span class="sxs-lookup"><span data-stu-id="a486e-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="a486e-116">Selezionare Sì nel campo Report elettronici generici.</span><span class="sxs-lookup"><span data-stu-id="a486e-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="a486e-117">Nel campo Esporta configurazione formato immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="a486e-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="a486e-118">Nell'elenco selezionare il valore di bonifico ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="a486e-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="a486e-119">Se l'elenco è vuoto, significa che la configurazione del formato di esportazione dei pagamenti fornitore non è importata e attiva.</span><span class="sxs-lookup"><span data-stu-id="a486e-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="a486e-120">Nel campo Tipo di conto selezionare "Banca".</span><span class="sxs-lookup"><span data-stu-id="a486e-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="a486e-121">Nel campo Conto pagamenti specificare i valori "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="a486e-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="a486e-122">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="a486e-122">Click Save.</span></span>


