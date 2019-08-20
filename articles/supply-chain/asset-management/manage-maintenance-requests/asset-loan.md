---
title: Cespiti in prestito
description: Viene descritta la procedura per la registrazione dei cespiti in prestito in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8680241b1300aceda3280893982a1eff3d2e09e0
ms.sourcegitcommit: 871b76f8808a48d282f151144829323258ffc912
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/02/2019
ms.locfileid: "1847484"
---
# <a name="asset-loans"></a><span data-ttu-id="b7c55-103">Cespiti in prestito</span><span class="sxs-lookup"><span data-stu-id="b7c55-103">Asset loans</span></span>

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="b7c55-104">Se la società riceve cespiti per i processi di manutenzione o di riparazione da ubicazioni interne o dai clienti e presta temporaneamente cespiti a tali ubicazioni o clienti, Gestione cespiti può tenere traccia dei cespiti in prestito.</span><span class="sxs-lookup"><span data-stu-id="b7c55-104">If your company receives assets for repair or maintenance jobs from either internal locations or customers, and if you temporarily loan assets to those locations or customers, Asset Management can track the asset loans.</span></span>

## <a name="register-asset-loans-on-a-maintenance-request"></a><span data-ttu-id="b7c55-105">Registrare cespiti in prestito in una richiesta di intervento di manutenzione</span><span class="sxs-lookup"><span data-stu-id="b7c55-105">Register asset loans on a maintenance request</span></span>

1. <span data-ttu-id="b7c55-106">Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Tutte le richieste di intervento di manutenzione** o **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-106">Select **Asset management** \> **Common** \> **Maintenance requests** \> **All maintenance requests** or **Active maintenance requests**.</span></span>
2. <span data-ttu-id="b7c55-107">Selezionare la richiesta di intervento di manutenzione in cui registrare un cespite in prestito e selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-107">Select the maintenance request to register an asset loan on, and then select **Edit**.</span></span>
3. <span data-ttu-id="b7c55-108">Nella pagina **Richiesta**, selezionare **Invia cespite in prestito**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-108">On the **Request** page, select **Send loan asset**.</span></span>
4. <span data-ttu-id="b7c55-109">Selezionare il cespite e immettere la data di restituzione prevista.</span><span class="sxs-lookup"><span data-stu-id="b7c55-109">Select the asset, and enter the expected return date.</span></span>
5. <span data-ttu-id="b7c55-110">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-110">Select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="b7c55-111">È possibile inviare un cespite in prestito solo se un cespite dello stesso tipo del cespite è disponibile.</span><span class="sxs-lookup"><span data-stu-id="b7c55-111">You can send a loan asset only if an asset of the same asset type is available.</span></span>
> - <span data-ttu-id="b7c55-112">Cespite prestato deve avere uno stato del ciclo di vita del cespite che ne consenta l'uso come cespite in prestito, ad esempio **InStorage**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-112">The asset that you loan must have an asset lifecycle state that allows it to be used as a loan asset, such as **InStorage**.</span></span> <span data-ttu-id="b7c55-113">Quando il cespite in prestito viene registrato, lo stato del ciclo di vita del cespite viene aggiornato automaticamente in, ad esempio, **OnLoan**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-113">When the asset loan is registered, the asset lifecycle state of the asset is automatically updated to, for example, **OnLoan**.</span></span>

<span data-ttu-id="b7c55-114">Per visualizzare un elenco di tutti i cespiti pestati ad altre ubicazioni o clienti, selezionare **Gestione cespiti** \> **Comune** \> **Cespite in prestito** \> **Tutti i cespiti in prestito**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-114">To view a list of all the assets that you've loaned to other locations or customers, select **Asset management** \> **Common** \> **Asset loan** \> **All asset loans**.</span></span> <span data-ttu-id="b7c55-115">Se la casella di controllo **Finito** è selezionata per un cespite, il cespite è stato registrato come restituito alla società.</span><span class="sxs-lookup"><span data-stu-id="b7c55-115">If the **Ended** check box is selected for an asset, the asset has been registered as returned to your company.</span></span>

![Figura 1](media/06-manage-maintenance-requests.png)

<span data-ttu-id="b7c55-117">Nella pagina **Prestiti attivi cespiti**, è possibile visualizzare un elenco di tutti i cespiti in prestito che non sono stati restituiti alla società.</span><span class="sxs-lookup"><span data-stu-id="b7c55-117">On the **Active asset loans** page, you can view a list of all the loan assets that haven't yet been returned to your company.</span></span>

## <a name="register-loan-assets-as-returned"></a><span data-ttu-id="b7c55-118">Registrare cespiti in prestito come restituiti</span><span class="sxs-lookup"><span data-stu-id="b7c55-118">Register loan assets as returned</span></span>

1. <span data-ttu-id="b7c55-119">Selezionare **Gestione cespiti** \> **Comune** \> **Cespite in prestito** \> **Prestiti attivi cespiti**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-119">Select **Asset management** \> **Common** \> **Asset loan** \> **Active asset loans**.</span></span>
2. <span data-ttu-id="b7c55-120">Selezionare il cespite in prestito da registrare come restituito e selezionare **Restituisci cespite in prestito**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-120">Select the asset loan to register as returned, and then select **Return asset loan**.</span></span>
3. <span data-ttu-id="b7c55-121">Nel campo **Restituito** immettere la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="b7c55-121">In the **Returned** field, enter the date and time.</span></span>
4. <span data-ttu-id="b7c55-122">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7c55-122">Select **OK**.</span></span>
5. <span data-ttu-id="b7c55-123">Aggiornare la pagina elenco **Prestiti attivi cespiti** e osservare che il cespite in prestito non è più presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b7c55-123">Refresh the **Active asset loans** list page, and notice that the asset loan no longer appears in the list.</span></span>