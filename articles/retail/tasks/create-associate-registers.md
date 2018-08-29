--- 
title: Creare il POS (registri)
description: Questa procedura dimostra come creare un registratore di cassa POS.
author: rubencdelgado
manager: AnnBe
ms.date: 10/05/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: b477b201df62c9fbbbb18978a4a15fa3b4a964ae
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---
# <a name="create-point-of-sale-registers"></a><span data-ttu-id="69d0c-103">Creare il POS (registri)</span><span class="sxs-lookup"><span data-stu-id="69d0c-103">Create point of sale (registers)</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="69d0c-104">Questa procedura dimostra come creare un registratore di cassa POS.</span><span class="sxs-lookup"><span data-stu-id="69d0c-104">This procedure demonstrates how to create a point of sale (POS) register.</span></span> <span data-ttu-id="69d0c-105">Questa procedura utilizza la società di dati dimostrativi USRT.</span><span class="sxs-lookup"><span data-stu-id="69d0c-105">This procedure uses the demo data company USRT.</span></span>

1. <span data-ttu-id="69d0c-106">Passare a Vendita al dettaglio e commercio > Impostazione canale > Impostazione POS > Registri.</span><span class="sxs-lookup"><span data-stu-id="69d0c-106">Go to Retail and commerce > Channel setup > POS setup > Registers.</span></span>
2. <span data-ttu-id="69d0c-107">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="69d0c-107">Click New.</span></span>
3. <span data-ttu-id="69d0c-108">Nel campo Numero registratore di cassa, digitare l'ID relativo al nuovo registratore.</span><span class="sxs-lookup"><span data-stu-id="69d0c-108">In the Register number field, type an ID for the new register.</span></span>
    * <span data-ttu-id="69d0c-109">L'ID registratore comprende tipicamente i codici che contribuiscono a mappare il registratore al punto vendita a cui appartiene ed alla posizione all'interno del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="69d0c-109">The register ID typically includes codes that help map the register to the store to which it belongs, and the location within the store.</span></span>  
4. <span data-ttu-id="69d0c-110">Nel campo Nome digitare un nome descrittivo per il registratore di cassa.</span><span class="sxs-lookup"><span data-stu-id="69d0c-110">In the Name field, type a descriptive name for the register..</span></span>
5. <span data-ttu-id="69d0c-111">Nel campo Numero punto vendita immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69d0c-111">In the Store number field, enter or select a value.</span></span>
6. <span data-ttu-id="69d0c-112">Nel campo Profilo hardware immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69d0c-112">In the Hardware profile field, enter or select a value.</span></span>
    * <span data-ttu-id="69d0c-113">I profili hardware sono usati per specificare le periferiche di vendita al dettaglio che saranno collegate al registratore, quali il cassetto della cassa e la stampante delle ricevute.</span><span class="sxs-lookup"><span data-stu-id="69d0c-113">Hardware profiles are used to specify the retail peripherals that will be connected to the register, such as cash drawer and receipt printer.</span></span>  
7. <span data-ttu-id="69d0c-114">Nel campo Profilo visivo immettere o selezionare un valore.</span><span class="sxs-lookup"><span data-stu-id="69d0c-114">In the Visual profile field, enter or select a value.</span></span>
    * <span data-ttu-id="69d0c-115">I profili visivi sono usati per specificare le immagini utilizzate nello sfondo POS e nella pagina di accesso come pure i temi per il POS.</span><span class="sxs-lookup"><span data-stu-id="69d0c-115">Visual profiles are used to specify the images used in the POS background and login page as well as themes for the POS.</span></span>  
8. <span data-ttu-id="69d0c-116">Nel campo Numero di registratore di cassa POS EFT, digitare un valore.</span><span class="sxs-lookup"><span data-stu-id="69d0c-116">In the EFT POS register number field, type a value.</span></span>
    * <span data-ttu-id="69d0c-117">Il numero di registratore di cassa POS EFT è usato per indicare all'unità di elaborazione di pagamento quale terminale di pagamento sta inviando le richieste di autorizzazione.</span><span class="sxs-lookup"><span data-stu-id="69d0c-117">The EFT POS register number is used to inform the payment processor which payment terminal is sending authorization requests.</span></span> <span data-ttu-id="69d0c-118">Questo valore spesso è chiamato "ID terminale" o “TID”.</span><span class="sxs-lookup"><span data-stu-id="69d0c-118">This value is often called the "Terminal ID" or “TID”.</span></span> <span data-ttu-id="69d0c-119">Il TID può essere trovato generalmente su un autoadesivo sul dispositivo di pagamento.</span><span class="sxs-lookup"><span data-stu-id="69d0c-119">The TID can generally be found on a sticker on the payment device.</span></span>  
9. <span data-ttu-id="69d0c-120">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="69d0c-120">Click Save.</span></span>


