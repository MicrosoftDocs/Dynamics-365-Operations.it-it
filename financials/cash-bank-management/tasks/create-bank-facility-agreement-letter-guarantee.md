--- 
title: Creare un contratto per linea di credito bancaria per una lettera di garanzia
description: "Questa attività crea un contratto per linea di credito bancaria per elaborare una lettera di garanzia."
author: ShylaThompson
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 7b6e35c922edeb3c3c7a33ff741a25e699242abf
ms.contentlocale: it-it
ms.lasthandoff: 08/29/2017

---
# <a name="create-a-bank-facility-agreement-for-the-letter-of-guarantee"></a><span data-ttu-id="4fb9e-103">Creare un contratto per linea di credito bancaria per una lettera di garanzia</span><span class="sxs-lookup"><span data-stu-id="4fb9e-103">Create a bank facility agreement for the letter of guarantee</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fb9e-104">Questa attività crea un contratto per linea di credito bancaria per elaborare una lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-104">This task creates a bank facility agreement to process a letter of guarantee.</span></span> <span data-ttu-id="4fb9e-105">In questa attività viene utilizzata la società dimostrativa USMF.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-105">This task uses the USMF demo company.</span></span> 


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="4fb9e-106">Creare un contratto per linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="4fb9e-106">Create Bank facility agreement</span></span>
1. <span data-ttu-id="4fb9e-107">Fare clic su Gestione cassa e banche > Lettere di garanzia > Contratti per linea di credito bancaria.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-107">Go to Cash and bank management > Letters of guarantee > Bank facility agreements.</span></span>
2. <span data-ttu-id="4fb9e-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-108">Click New.</span></span>
3. <span data-ttu-id="4fb9e-109">Nel campo Numero contratto immettere il numero di contratto bancario per la transazione.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-109">In the Agreement number field, enter the bank agreement number for the transaction.</span></span>
4. <span data-ttu-id="4fb9e-110">Nel campo Conto bancario selezionare il numero del conto bancario per cui viene aperta la lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-110">In the Bank account field, select the bank account number for which the letter of guarantee is open.</span></span> 
5. <span data-ttu-id="4fb9e-111">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-111">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="4fb9e-112">Nel campo Data di inizio immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-112">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="4fb9e-113">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-113">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="4fb9e-114">Attivare/disattivare l'espansione della sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-114">Toggle the expansion of the General section.</span></span>
9. <span data-ttu-id="4fb9e-115">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-115">Click Add line.</span></span>
10. <span data-ttu-id="4fb9e-116">Nel campo Tipo di linea di credito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-116">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="4fb9e-117">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-117">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="4fb9e-118">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-118">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="4fb9e-119">Nel campo Limite immettere l'importo negoziato con la banca.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-119">In the Limit field, enter the amount negotiated with the bank.</span></span>
14. <span data-ttu-id="4fb9e-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-120">Click Save.</span></span>
15. <span data-ttu-id="4fb9e-121">Attivare/disattivare l'espansione della sezione Lettera di garanzia.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-121">Toggle the expansion of the Letter of guarantee section.</span></span>
16. <span data-ttu-id="4fb9e-122">Selezionare un'opzione nel campo Metodo di calcolo.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-122">In the Calculation method field, select an option.</span></span>
    * <span data-ttu-id="4fb9e-123">Immettere i dettagli di percentuale e metodo di calcolo per Margine di garanzia, Commissione emissione, Commissione proroga, Aumenta commissione su valore o Diminuisci commissione su valore, in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-123">Enter the calculation method and percentage details for the Cash margin, Issuance commission, Extension commission, Increase value commission, or Decrease value commission, as appropriate.</span></span>   
17. <span data-ttu-id="4fb9e-124">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-124">Click Save.</span></span>

## <a name="extend-bank-facility-agreement"></a><span data-ttu-id="4fb9e-125">Prorogare il contratto linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="4fb9e-125">Extend bank facility agreement</span></span>
1. <span data-ttu-id="4fb9e-126">Fare clic su Estendi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-126">Click Extend to open the drop dialog.</span></span>
2. <span data-ttu-id="4fb9e-127">Digitare un valore nel campo Nuovo numero contratto.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-127">In the New agreement number field, type a value.</span></span>
3. <span data-ttu-id="4fb9e-128">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-128">In the End date field, enter a date and time.</span></span>
4. <span data-ttu-id="4fb9e-129">Fare clic su Estendi.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-129">Click Extend.</span></span>
5. <span data-ttu-id="4fb9e-130">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-130">Click Save.</span></span>
6. <span data-ttu-id="4fb9e-131">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="4fb9e-131">Close the page.</span></span>

