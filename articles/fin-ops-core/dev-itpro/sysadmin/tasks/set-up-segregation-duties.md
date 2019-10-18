---
title: Impostare la separazione dei compiti
description: È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi.
author: maertenm
manager: AnnBe
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysSecSegregationOfDutiesRule
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 40b40b77877680e28671b7a15ea8c8b58ce94417
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180877"
---
# <a name="set-up-segregation-of-duties"></a><span data-ttu-id="aeeef-103">Impostare la separazione dei compiti</span><span class="sxs-lookup"><span data-stu-id="aeeef-103">Set up segregation of duties</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="aeeef-104">È possibile impostare le regole per separare le attività che devono essere eseguite da utenti diversi.</span><span class="sxs-lookup"><span data-stu-id="aeeef-104">You can set up rules to separate tasks that must be performed by different users.</span></span> <span data-ttu-id="aeeef-105">Questo concetto è denominato separazione dei compiti.</span><span class="sxs-lookup"><span data-stu-id="aeeef-105">This concept is named segregation of duties.</span></span> <span data-ttu-id="aeeef-106">Ad esempio, non è possibile che la stessa persona confermi l'entrata delle merci ed elabori il pagamento al fornitore.</span><span class="sxs-lookup"><span data-stu-id="aeeef-106">For example, you might not want the same person both to acknowledge the receipt of goods and to process payment to the vendor.</span></span> <span data-ttu-id="aeeef-107">La separazione dei compiti consente di ridurre il rischio di frode e aiuta anche a rilevare errori o irregolarità.</span><span class="sxs-lookup"><span data-stu-id="aeeef-107">Segregation of duties helps you reduce the risk of fraud, and it also helps you detect errors or irregularities.</span></span> <span data-ttu-id="aeeef-108">È inoltre possibile utilizzare la separazione dei compiti per applicare i criteri di controllo interno.</span><span class="sxs-lookup"><span data-stu-id="aeeef-108">You can also use segregation of duties to enforce internal control policies.</span></span> <span data-ttu-id="aeeef-109">Completare la procedura indicata di seguito per creare una regola.</span><span class="sxs-lookup"><span data-stu-id="aeeef-109">Complete the following procedure to create a rule.</span></span> <span data-ttu-id="aeeef-110">È necessario essere un amministratore di sistema per completare la procedura.</span><span class="sxs-lookup"><span data-stu-id="aeeef-110">You must be a system administrator to complete the procedure.</span></span> <span data-ttu-id="aeeef-111">La società di dati dimostrativi utilizzata per creare questa procedura è DAT.</span><span class="sxs-lookup"><span data-stu-id="aeeef-111">The demo data company used to create this procedure is DAT.</span></span> 

1. <span data-ttu-id="aeeef-112">Scegliere **Pannello di navigazione > Moduli > Amministrazione sistema > Sicurezza > Separazione dei compiti > Regole di separazione dei compiti**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-112">Go to **Navigation pane > Modules > System administration > Security > Segregation of duties > Segregation of duties rules**.</span></span>
2. <span data-ttu-id="aeeef-113">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-113">Click **New**.</span></span>
3. <span data-ttu-id="aeeef-114">Digitare un valore per la regola nel campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-114">In the **Name** field, type a value for the rule.</span></span>
4. <span data-ttu-id="aeeef-115">Nel campo **Primo compito** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeeef-115">In the **First duty** field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="aeeef-116">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="aeeef-116">In the list, find and select the desired record.</span></span> <span data-ttu-id="aeeef-117">Selezionare il primo compito che è controllato dalla regola.</span><span class="sxs-lookup"><span data-stu-id="aeeef-117">Select the first duty that is controlled by the rule.</span></span>
6. <span data-ttu-id="aeeef-118">Nel campo **Secondo compito** fare clic sul pulsante a discesa per aprire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="aeeef-118">In the **Second duty** field, click the drop-down button to open the lookup.</span></span> 
7. <span data-ttu-id="aeeef-119">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="aeeef-119">In the list, find and select the desired record.</span></span> <span data-ttu-id="aeeef-120">Selezionare il secondo compito che è controllato dalla regola.</span><span class="sxs-lookup"><span data-stu-id="aeeef-120">Select the second duty that is controlled by the rule.</span></span>
10. <span data-ttu-id="aeeef-121">Selezionare un'opzione nel campo **Gravità**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-121">In the **Severity** field, select an option.</span></span> <span data-ttu-id="aeeef-122">Selezionare la gravità del rischio che si verifica quando entrambi i compiti vengono eseguiti dallo stesso utente o ruolo.</span><span class="sxs-lookup"><span data-stu-id="aeeef-122">Select the severity of the risk that occurs when the same user or role performs both duties.</span></span>  
11. <span data-ttu-id="aeeef-123">Digitare un valore nel campo **Rischio di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-123">In the **Security risk** field, type a value.</span></span> <span data-ttu-id="aeeef-124">Immettere una descrizione del rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aeeef-124">Enter a description of the security risk.</span></span>  
12. <span data-ttu-id="aeeef-125">Digitare un valore nel campo **Riduzione dei rischi di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-125">In the **Security mitigation** field, type a value.</span></span> <span data-ttu-id="aeeef-126">Immettere una descrizione delle azioni prese per attenuare il rischio di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="aeeef-126">Enter a description of the actions that you take to mitigate the security risk.</span></span> <span data-ttu-id="aeeef-127">Ad esempio, è possibile attenuare il rischio effettuando revisioni più dettagliati del processo, svolgendo una revisione manageriale mensile o condividendo le risorse con altri reparti.</span><span class="sxs-lookup"><span data-stu-id="aeeef-127">For example, you can mitigate the risk by conducting more detailed reviews of the process, by conducting a monthly managerial review, or by sharing resources with other departments.</span></span>     
13. <span data-ttu-id="aeeef-128">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="aeeef-128">Click **Save**.</span></span>

