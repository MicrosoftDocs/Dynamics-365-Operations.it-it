--- 
title: Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)
description: "I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici."
author: NickSelin
manager: AnnBe
ms.date: 10/18/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: bdb3a3857a7293828a7766b6988c123a43e0673c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-configuration-providand-mark-it-as-active-for-electronic-reporting-er"></a><span data-ttu-id="f2947-103">Creare e attivare un provider di configurazione per la creazione di report elettronici (ER)</span><span class="sxs-lookup"><span data-stu-id="f2947-103">Create a configuration providand mark it as active for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="f2947-104">I passaggi seguenti illustrano come un utente assegnato al ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici può creare un provider di configurazione per la creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f2947-104">The following steps explain how a user assigned to the System Administrator or Electronic Reporting Developer role can create a configuration provider for Electronic reporting (ER).</span></span> <span data-ttu-id="f2947-105">Ciascuna configurazione di questo tipo farà riferimento al provider come autore della configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2947-105">Each ER configuration will refer to the provider as the author of the configuration.</span></span> <span data-ttu-id="f2947-106">In questo esempio verrà creato un provider di configurazione per la società di esempio Litware, Inc. Queste operazioni possono essere eseguite in qualsiasi società perché i provider di configurazione per la creazione di report elettronici sono condivisi tra tutte le società.</span><span class="sxs-lookup"><span data-stu-id="f2947-106">In this example, you will create a configuration provider for sample company, Litware, Inc. These steps can be performed in any company as ER configuration providers are shared among all companies.</span></span>


## <a name="create-a-provider"></a><span data-ttu-id="f2947-107">Creare un provider</span><span class="sxs-lookup"><span data-stu-id="f2947-107">Create a provider</span></span>
1. <span data-ttu-id="f2947-108">Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.</span><span class="sxs-lookup"><span data-stu-id="f2947-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
2. <span data-ttu-id="f2947-109">Fare clic su Provider di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f2947-109">Click Configuration providers.</span></span>
3. <span data-ttu-id="f2947-110">Fare clic su Nuovo.</span><span class="sxs-lookup"><span data-stu-id="f2947-110">Click New.</span></span>
    * <span data-ttu-id="f2947-111">Un record del provider ha un nome e un URL univoci.</span><span class="sxs-lookup"><span data-stu-id="f2947-111">A provider record has a unique name and URL.</span></span> <span data-ttu-id="f2947-112">Esaminare il contenuto della pagina e ignorare questa procedura se un record per Litware, Inc. (http://www.litware.com) esiste già.</span><span class="sxs-lookup"><span data-stu-id="f2947-112">Review the content of this page and skip this procedure if a record for Litware, Inc. (http://www.litware.com) already exists.</span></span>  
4. <span data-ttu-id="f2947-113">Nel campo Nome digitare Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="f2947-113">In the Name field, type 'Litware, Inc.'.</span></span>
    * <span data-ttu-id="f2947-114">Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="f2947-114">Litware, Inc.</span></span>  
5. <span data-ttu-id="f2947-115">Nel campo dell'indirizzo Internet immettere http://www.litware.com.</span><span class="sxs-lookup"><span data-stu-id="f2947-115">In the Internet address field, type 'http://www.litware.com'.</span></span>
    * <span data-ttu-id="f2947-116">http://www.litware.com</span><span class="sxs-lookup"><span data-stu-id="f2947-116">http://www.litware.com</span></span>  
6. <span data-ttu-id="f2947-117">Fare clic su Salva.</span><span class="sxs-lookup"><span data-stu-id="f2947-117">Click Save.</span></span>
7. <span data-ttu-id="f2947-118">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="f2947-118">Close the page.</span></span>

## <a name="select-as-an-active-provider"></a><span data-ttu-id="f2947-119">Selezionare il provider come attivo</span><span class="sxs-lookup"><span data-stu-id="f2947-119">Select as an active provider</span></span>
1. <span data-ttu-id="f2947-120">Selezionare il provider Litware, Inc. .</span><span class="sxs-lookup"><span data-stu-id="f2947-120">Select the Litware, Inc. provider.</span></span>
2. <span data-ttu-id="f2947-121">Fare clic su Imposta attivo.</span><span class="sxs-lookup"><span data-stu-id="f2947-121">Click Set active.</span></span>


