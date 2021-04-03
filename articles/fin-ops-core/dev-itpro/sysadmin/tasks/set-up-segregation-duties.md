---
title: Impostare la separazione dei compiti
description: È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi.
author: peakerbl
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1c1521d6bbbe12964fef0942fcc4943f12a4360a
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5562499"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="f907d-103">Impostare la separazione dei compiti</span><span class="sxs-lookup"><span data-stu-id="f907d-103">Set up segregation of duties</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f907d-104">È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="f907d-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="f907d-105">Questo concetto è denominato separazione dei compiti.</span><span class="sxs-lookup"><span data-stu-id="f907d-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="f907d-106">Ad esempio, non è possibile che la stessa persona confermi l'entrata delle merci ed elabori il pagamento al fornitore.</span><span class="sxs-lookup"><span data-stu-id="f907d-106">For example, you might not want the same person to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="f907d-107">La separazione dei compiti consente di ridurre il rischio di frode e aiuta anche a rilevare errori o irregolarità.</span><span class="sxs-lookup"><span data-stu-id="f907d-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="f907d-108">È inoltre possibile utilizzare la separazione dei compiti per applicare i criteri di controllo interno.</span><span class="sxs-lookup"><span data-stu-id="f907d-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="f907d-109">Completare la procedura indicata di seguito per creare una regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="f907d-110">È necessario essere un amministratore di sistema per completare la procedura.</span><span class="sxs-lookup"><span data-stu-id="f907d-110">You must be a system administrator to complete the procedure.</span></span>

1. <span data-ttu-id="f907d-111">Scegliere **Amministrazione sistema** > **Sicurezza** > **Separazione dei compiti** > **Regole di separazione dei compiti**.</span><span class="sxs-lookup"><span data-stu-id="f907d-111">Go to **System administration** > **Security** > **Segregation of duties** > **Segregation of duties rules**.</span></span>
2. <span data-ttu-id="f907d-112">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f907d-112">Click **New**.</span></span>
3. <span data-ttu-id="f907d-113">Digitare un valore per la regola nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="f907d-113">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="f907d-114">Nel campo **Primo compito** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f907d-114">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="f907d-115">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f907d-115">In the list, find and select the desired record.</span></span> <span data-ttu-id="f907d-116">Selezionare il primo compito che è controllato dalla regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-116">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="f907d-117">Nel campo **Secondo compito** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="f907d-117">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="f907d-118">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="f907d-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="f907d-119">Selezionare il secondo compito che è controllato dalla regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-119">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="f907d-120">Selezionare un'opzione nel campo **Gravità**.</span><span class="sxs-lookup"><span data-stu-id="f907d-120">In the **Severity** field, select an option.</span></span> <span data-ttu-id="f907d-121">Selezionare la gravità del rischio che si verifica quando entrambi i compiti vengono eseguiti dallo stesso utente o ruolo.</span><span class="sxs-lookup"><span data-stu-id="f907d-121">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="f907d-122">Digitare un valore nel campo **Rischio di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f907d-122">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="f907d-123">Immettere una descrizione del rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f907d-123">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="f907d-124">Digitare un valore nel campo **Riduzione dei rischi di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f907d-124">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="f907d-125">Immettere una descrizione delle azioni prese per attenuare il rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f907d-125">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="f907d-126">Ad esempio, è possibile attenuare il rischio effettuando revisioni più dettagliati del processo, svolgendo una revisione manageriale mensile o condividendo le risorse con altri reparti.</span><span class="sxs-lookup"><span data-stu-id="f907d-126">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="f907d-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f907d-127">Click **Save**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="f907d-128">Il rispetto delle regole per la separazione dei compiti non viene verificato quando si crea una regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-128">Compliance with the rules for segregation of duties is not verified when you create a rule.</span></span> <span data-ttu-id="f907d-129">È possibile creare una regola che crei un conflitto per i ruoli esistenti.</span><span class="sxs-lookup"><span data-stu-id="f907d-129">You can create a rule that creates a conflict for existing roles.</span></span> <span data-ttu-id="f907d-130">Anche le assegnazioni di ruoli utente esistenti possono essere in conflitto con la nuova regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-130">Existing user role assignments can also be in conflict with the new rule.</span></span> <span data-ttu-id="f907d-131">È necessario convalidare la conformità dopo aver creato o modificato una regola.</span><span class="sxs-lookup"><span data-stu-id="f907d-131">You must validate compliance after you create or modify a rule.</span></span> <span data-ttu-id="f907d-132">Per altre informazioni, vedere [Identificare e risolvere conflitti di separazione dei compiti](identify-resolve-conflicts-segregation-duties.md)</span><span class="sxs-lookup"><span data-stu-id="f907d-132">For more information, see [Identify and resolve conflicts in segregation of duties](identify-resolve-conflicts-segregation-duties.md)</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]