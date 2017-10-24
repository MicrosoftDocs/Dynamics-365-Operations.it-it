--- 
title: Impostare i tipi di documento I-9
description: Questa procedura illustra come visualizzare e impostare i tipi di documento utilizzati per la verifica I-9.
author: ShielaSogge
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3b0e7f09994367f5683ed5c6d1f3b3ba3d550cc7
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-i-9-document-types"></a><span data-ttu-id="03715-103">Impostare i tipi di documento I-9</span><span class="sxs-lookup"><span data-stu-id="03715-103">Set up I-9 document types</span></span>

[!include[task guide banner](../../../includes/task-guide-banner.md)]

<span data-ttu-id="03715-104">Questa procedura illustra come visualizzare e impostare i tipi di documento utilizzati per la verifica I-9.</span><span class="sxs-lookup"><span data-stu-id="03715-104">This procedure shows how to view and set up document types that are used for I-9 verification.</span></span> <span data-ttu-id="03715-105">Prima di impostare i tipi di documento I-9, è necessario impostare gli enti emittenti e i tipi di identificazione.</span><span class="sxs-lookup"><span data-stu-id="03715-105">Before you set up I-9 document types, you must also set up the issuing agencies and identification types.</span></span> <span data-ttu-id="03715-106">La società di dati dimostrativi utilizzata per creare questa procedura è USMF, che include esempi degli enti emittenti e dei tipi di identificazione necessari per completare la procedura.</span><span class="sxs-lookup"><span data-stu-id="03715-106">The demo data company used to create this procedure is USMF, which includes examples of the issue agencies and identification types that are needed to complete the procedure.</span></span>

1. <span data-ttu-id="03715-107">Andare a Risorse umane > Lavoratori > I-9 > Tipi di documento I-9.</span><span class="sxs-lookup"><span data-stu-id="03715-107">Go to Human resources > Workers > I-9 > I-9 document types.</span></span>
2. <span data-ttu-id="03715-108">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="03715-108">Click New.</span></span>
3. <span data-ttu-id="03715-109">Nel campo Tipo di documento I-9 digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="03715-109">In the I-9 document type field, type a value.</span></span>
    * <span data-ttu-id="03715-110">Esempio: ID scuola.</span><span class="sxs-lookup"><span data-stu-id="03715-110">Example: School ID.</span></span>  
4. <span data-ttu-id="03715-111">Selezionare il tipo di identificazione.</span><span class="sxs-lookup"><span data-stu-id="03715-111">Select the identification type.</span></span>  <span data-ttu-id="03715-112">Esempio: ID scuola</span><span class="sxs-lookup"><span data-stu-id="03715-112">Example:  School ID</span></span>
    * <span data-ttu-id="03715-113">Esempi di tipi di identificazione includono il numero SSN (Social Security Number), il numero del visto, l'ID passaporto o la patente di guida.</span><span class="sxs-lookup"><span data-stu-id="03715-113">Examples of identification types include a Social Security number (SSN), visa number, passport ID, or driver's licence.</span></span>  
5. <span data-ttu-id="03715-114">Selezionare l'elenco di documento I-9 utilizzato per il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="03715-114">Select the I-9 document list that is used for the document type.</span></span>
    * <span data-ttu-id="03715-115">Durante il processo I-9, i dipendenti devono presentare la documentazione che dimostri al datore di lavoro l'identità e l'autorizzazione all'impiego.</span><span class="sxs-lookup"><span data-stu-id="03715-115">As part of the I-9 process, employees must present documentation that shows the employer their identity and employment authorization.</span></span> <span data-ttu-id="03715-116">Il sito Web sui servizi per la cittadinanza e l'immigrazione negli Stati Uniti contiene informazioni sui documenti accettabili e sull'elenco a cui appartengono.</span><span class="sxs-lookup"><span data-stu-id="03715-116">The US Citizenship and Immigration Services website contains information about which documents are acceptable, and which list they belong to.</span></span>  <span data-ttu-id="03715-117">Vedere il sito http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="03715-117">http://www.uscis.gov</span></span>  
6. <span data-ttu-id="03715-118">Nel campo Modulo immettere il numero del documento ufficiale per il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="03715-118">In the Form field, Enter the official form number for the document type.</span></span> <span data-ttu-id="03715-119">Esempio: ID scuola.</span><span class="sxs-lookup"><span data-stu-id="03715-119">Example: School ID.</span></span>
    * <span data-ttu-id="03715-120">I numeri dei documenti ufficiali sono disponibili nel sito Web sui servizi per la cittadinanza e l'immigrazione negli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="03715-120">The official form numbers can be found on the US Citizenship and Immigration Services website.</span></span>  <span data-ttu-id="03715-121">Vedere il sito http://www.uscis.gov</span><span class="sxs-lookup"><span data-stu-id="03715-121">http://www.uscis.gov</span></span>  
7. <span data-ttu-id="03715-122">Selezionare o deselezionare la casella di controllo Attivo.</span><span class="sxs-lookup"><span data-stu-id="03715-122">Check or uncheck the Active checkbox.</span></span>
8. <span data-ttu-id="03715-123">Nel campo Data di scadenza impostare la data su "27-10-2019".</span><span class="sxs-lookup"><span data-stu-id="03715-123">In the Expire field, set the date to '2019-10-27'.</span></span>
    * <span data-ttu-id="03715-124">La data di scadenza è facoltativa.</span><span class="sxs-lookup"><span data-stu-id="03715-124">The expiration date is optional.</span></span>  
9. <span data-ttu-id="03715-125">Selezionare l'ente che ha emesso il tipo di documento.</span><span class="sxs-lookup"><span data-stu-id="03715-125">Select the agency that issued the document type.</span></span> <span data-ttu-id="03715-126">Esempio: Regione/provincia/territorio</span><span class="sxs-lookup"><span data-stu-id="03715-126">Example: Province/territory</span></span>
10. <span data-ttu-id="03715-127">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="03715-127">Click Save.</span></span>


