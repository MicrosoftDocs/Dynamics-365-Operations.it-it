---
title: Creare un contratto per linea di credito bancaria per una lettera di credito
description: In questa attività viene illustrato come creare un contratto per linea di credito bancaria per elaborare una lettera di credito.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankDocumentFacilityAgreement, BankAccountTableLookUp, BankDocumentFacilityAgreementExtension, DefaultDashboard
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: leguo
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb624700e0b052de977fabecf9670b3515d32ab7
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141720"
---
# <a name="create-a-bank-facility-agreement-for-a-letter-of-credit"></a><span data-ttu-id="62685-103">Creare un contratto per linea di credito bancaria per una lettera di credito</span><span class="sxs-lookup"><span data-stu-id="62685-103">Create a bank facility agreement for a letter of credit</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="62685-104">In questa attività viene illustrato come creare un contratto per linea di credito bancaria per elaborare una lettera di credito.</span><span class="sxs-lookup"><span data-stu-id="62685-104">This task walks through the creating a Bank facility agreement to process a Letter of credit.</span></span> <span data-ttu-id="62685-105">Si consiglia di impostare le linee di credito bancarie e i profili di registrazione prima di tale attività.</span><span class="sxs-lookup"><span data-stu-id="62685-105">You will want to set up bank facilities and posting profiles before this task.</span></span>  <span data-ttu-id="62685-106">In questa attività viene utilizzata la società dimostrativa "USMF".</span><span class="sxs-lookup"><span data-stu-id="62685-106">This task uses the demo company 'USMF'.</span></span>  


## <a name="create-bank-facility-agreement"></a><span data-ttu-id="62685-107">Creare un contratto per linea di credito bancaria</span><span class="sxs-lookup"><span data-stu-id="62685-107">Create Bank facility agreement</span></span>
1. <span data-ttu-id="62685-108">Andare a Gestione cassa e banche > Lettere di credito > Contratti per linea di credito bancaria.</span><span class="sxs-lookup"><span data-stu-id="62685-108">Go to Cash and bank management > Letters of credit > Bank facility agreements.</span></span>
2. <span data-ttu-id="62685-109">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="62685-109">Click New.</span></span>
3. <span data-ttu-id="62685-110">Nel campo Numero contratto, immettere il numero di contratto in base al contratto con la banca.</span><span class="sxs-lookup"><span data-stu-id="62685-110">In the Agreement number field, enter the agreement number according to the agreement with the bank.</span></span>
4. <span data-ttu-id="62685-111">Nel campo conto bancario immettere il numero di conto presso la banca emittente.</span><span class="sxs-lookup"><span data-stu-id="62685-111">In the Bank account field, enter the account number at the issuing bank.</span></span>
5. <span data-ttu-id="62685-112">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="62685-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="62685-113">Nel campo Data di inizio immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="62685-113">In the Start date field, enter a date and time.</span></span>
7. <span data-ttu-id="62685-114">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="62685-114">In the End date field, enter a date and time.</span></span>
8. <span data-ttu-id="62685-115">Espandere o comprimere la sezione Generale.</span><span class="sxs-lookup"><span data-stu-id="62685-115">Expand or collapse the General section.</span></span>
9. <span data-ttu-id="62685-116">Fare clic su Aggiungi riga.</span><span class="sxs-lookup"><span data-stu-id="62685-116">Click Add line.</span></span>
10. <span data-ttu-id="62685-117">Nel campo Tipo di linea di credito fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="62685-117">In the Facility type field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="62685-118">Trovare e selezionare il record desiderato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="62685-118">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="62685-119">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="62685-119">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="62685-120">Nel campo Limite immettere l'importo della linea di credito negoziato con la banca.</span><span class="sxs-lookup"><span data-stu-id="62685-120">In the Limit field, enter the facility amount that was negotiated with the bank.</span></span>
14. <span data-ttu-id="62685-121">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="62685-121">Click Save.</span></span>
15. <span data-ttu-id="62685-122">Fare clic su Estendi per aprire la finestra di dialogo a discesa.</span><span class="sxs-lookup"><span data-stu-id="62685-122">Click Extend to open the drop dialog.</span></span>
16. <span data-ttu-id="62685-123">Digitare un valore nel campo Nuovo numero contratto.</span><span class="sxs-lookup"><span data-stu-id="62685-123">In the New agreement number field, type a value.</span></span>
17. <span data-ttu-id="62685-124">Nel campo Data di fine immettere una data e un'ora.</span><span class="sxs-lookup"><span data-stu-id="62685-124">In the End date field, enter a date and time.</span></span>
18. <span data-ttu-id="62685-125">Fare clic su Estendi.</span><span class="sxs-lookup"><span data-stu-id="62685-125">Click Extend.</span></span>
19. <span data-ttu-id="62685-126">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="62685-126">Close the page.</span></span>

