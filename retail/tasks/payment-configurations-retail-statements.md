--- 
title: " Configurazioni dei pagamenti per rendiconti di vendita al dettaglio"
description: "In questa procedura sono illustrate le configurazioni per i metodi di pagamento di punto vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: jashanno
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 6305eecebdd53f85167a0a60e11f1989f9f073c8
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="payment-configurations-for-retail-statements"></a><span data-ttu-id="58171-103"> Configurazioni dei pagamenti per rendiconti di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="58171-103">Payment configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="58171-104">In questa procedura sono illustrate le configurazioni per i metodi di pagamento di punto vendita al dettaglio che interessano la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="58171-104">This procedure demonstrates configurations for Retail store payment methods, which affect how Retail statements get created and posted.</span></span>

<span data-ttu-id="58171-105">Questa registrazione utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="58171-105">This recording uses the USRT demo company.</span></span>

1. <span data-ttu-id="58171-106">Passare a Vendita al dettaglio e commercio > Canali > Punti vendita al dettaglio > Tutti i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="58171-106">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="58171-107">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="58171-107">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="58171-108">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="58171-108">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="58171-109">Nel riquadro azioni, fare clic su Imposta.</span><span class="sxs-lookup"><span data-stu-id="58171-109">On the Action Pane, click Set up.</span></span>
5. <span data-ttu-id="58171-110">Fare clic su Metodi di pagamento.</span><span class="sxs-lookup"><span data-stu-id="58171-110">Click Payment methods.</span></span>
6. <span data-ttu-id="58171-111">Espandere o comprimere la sezione Registrazione.</span><span class="sxs-lookup"><span data-stu-id="58171-111">Expand or collapse the Posting section.</span></span>
7. <span data-ttu-id="58171-112">Fare clic su Modifica.</span><span class="sxs-lookup"><span data-stu-id="58171-112">Click Edit.</span></span>
    * <span data-ttu-id="58171-113">Selezionare se gli importi ricevuti per il metodo di pagamento devono essere registrati in un conto CoGe o in un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58171-113">Select whether the amounts received for this payment method should be posted to a ledger account or bank account.</span></span>  
    * <span data-ttu-id="58171-114">Selezionare il conto in cui dovranno essere registrati gli importi ricevuti per il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="58171-114">Select the account that amounts received for this payment method should be posted to.</span></span>  
    * <span data-ttu-id="58171-115">Selezionare un conto per registrare le possibili differenze tra l'importo totale della transazione ricevuto e l'importo conteggiato per il metodo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="58171-115">Select an account to post possible differences between the total transaction amount received and the amount counted for this payment method.</span></span>  
    * <span data-ttu-id="58171-116">In questo campo è possibile immettere un importo per verificare se l'importo della differenza deve essere registrato in un altro conto di differenza.</span><span class="sxs-lookup"><span data-stu-id="58171-116">In this field you can enter an amount to control when the difference amount should be posted to another difference account.</span></span> <span data-ttu-id="58171-117">È possibile utilizzare questa opzione per tenere traccia delle grandi differenze.</span><span class="sxs-lookup"><span data-stu-id="58171-117">You can use this to track big differences.</span></span>  
    * <span data-ttu-id="58171-118">Selezionare un conto per registrare le possibili differenze tra l'importo totale della transazione ricevuto e l'importo conteggiato, quando supera il valore specificato nel campo "Importo massimo di differenza".</span><span class="sxs-lookup"><span data-stu-id="58171-118">Select an account to post possible differences between the total transaction amount received and the amount counted, when it exceeds the value that is defined in the "Maximum difference amount" field.</span></span>  
    * <span data-ttu-id="58171-119">Selezionare "Sì" per registrare gli importi di deposito bancario in un conto separato.</span><span class="sxs-lookup"><span data-stu-id="58171-119">Select "Yes" to post bank drop amounts to a seperate account.</span></span>  
    * <span data-ttu-id="58171-120">In questo campo è possibile selezionare se gli importi di deposito bancario devono essere registrati in un conto CoGe o in un conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58171-120">In this field you can select whether bank drop amounts should be posted to a ledger account or a bank account.</span></span>  
    * <span data-ttu-id="58171-121">Selezionare il conto in cui registrare gli importi di deposito bancario.</span><span class="sxs-lookup"><span data-stu-id="58171-121">Select the account to post bank drop amounts into.</span></span>  
    * <span data-ttu-id="58171-122">Selezionare il tipo di transazione bancaria da utilizzare per la registrazione degli importi di deposito bancario nel conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58171-122">Select the bank transaction type to use when posting bank drop amounts to the bank account.</span></span>  
    * <span data-ttu-id="58171-123">Selezionare "Sì" per registrare gli importi di deposito in cassaforte in un conto separato.</span><span class="sxs-lookup"><span data-stu-id="58171-123">Select "Yes" to post safe drop amounts to a seperate account.</span></span>  
    * <span data-ttu-id="58171-124">Selezionare se gli importi di deposito in cassaforte devono essere registrati nel conto CoGe o nel conto bancario.</span><span class="sxs-lookup"><span data-stu-id="58171-124">Select whether safe drop amounts should be posted to the ledger account or the bank account.</span></span>  
    * <span data-ttu-id="58171-125">Selezionare il conto in cui registrare gli importi di deposito in cassaforte.</span><span class="sxs-lookup"><span data-stu-id="58171-125">Select the account to post safe drop amounts into.</span></span>  
8. <span data-ttu-id="58171-126">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="58171-126">Click Save.</span></span>

