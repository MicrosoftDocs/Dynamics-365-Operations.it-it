---
title: " Configurazioni dei punti vendita per rendiconti di vendita al dettaglio"
description: In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.
author: jashanno
manager: AnnBe
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dbedcda59f503b103d5448e59038e4ed8ca0b51d
ms.sourcegitcommit: cbcf344b3b552acca56c3e27606eac7f2f124afe
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "1916532"
---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="17ab9-103"> Configurazioni dei punti vendita per rendiconti di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="17ab9-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="17ab9-104">In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="17ab9-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="17ab9-105">Le dimensioni finanziarie dei punti vendita al dettaglio sono analizzate in un'altra procedura.</span><span class="sxs-lookup"><span data-stu-id="17ab9-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="17ab9-106">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="17ab9-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="17ab9-107">Nel **pannello di navigazione**, andare a **Moduli > Vendita al dettaglio e commercio > Canali > Punti di vendita al dettaglio**.</span><span class="sxs-lookup"><span data-stu-id="17ab9-107">In the **Navgiation pane**, go to **Modules > Retail and commerce > Channels > Retail stores > All retail stores**.</span></span>
2. <span data-ttu-id="17ab9-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="17ab9-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="17ab9-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="17ab9-109">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="17ab9-110">Fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="17ab9-110">Click **Edit**.</span></span>
5. <span data-ttu-id="17ab9-111">Le impostazioni nella Scheda dettaglio **Rendiconto/Chiusura** interessano la creazione, la convalida e la registrazione del rendiconto per l'archivio.</span><span class="sxs-lookup"><span data-stu-id="17ab9-111">The settings in the **Statement/closing** fastTab affect the statement creation, validation, and posting for the store.</span></span> <span data-ttu-id="17ab9-112">Espandere la Scheda dettaglio **Rendiconto/Chiusura**.</span><span class="sxs-lookup"><span data-stu-id="17ab9-112">Expand the **Statement/closing** fastTab.</span></span>  
6. <span data-ttu-id="17ab9-113">Nel campo **Metodo rendiconto**, selezionare il metodo in base al quale raggruppare le linee del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="17ab9-113">In the **Statement method** field, select the method you want to use to to group the statement lines by.</span></span>  
7. <span data-ttu-id="17ab9-114">Selezionare "Sì" in **Un rendiconto al giorno** se si deve creare un solo rendiconto al giorno quando si creano i rendiconti tramite il processo batch di creazione dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="17ab9-114">Select "Yes" in **One statement per day** if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
8. <span data-ttu-id="17ab9-115">Il campo **Calcolo riepilogo incassi** definisce se si devono aggiungere tutti i riepiloghi incassi o solo l'ultimo.</span><span class="sxs-lookup"><span data-stu-id="17ab9-115">The **Tender declaration calculation** field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
9. <span data-ttu-id="17ab9-116">Nel campo **Arrotondamento**, selezionare il conto CoGe per la registrazione delle differenze di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="17ab9-116">In the **Rounding** field, select the ledger account to post rounding differences into.</span></span>  
10. <span data-ttu-id="17ab9-117">Nel campo **Importo arrotondamento massimo**, immettere la differenza di arrotondamento massima consentita.</span><span class="sxs-lookup"><span data-stu-id="17ab9-117">In the **Maximum rounding difference** field, enter the maximum rounding difference allowed.</span></span>
11. <span data-ttu-id="17ab9-118">Nel campo **Registrazione**, immettere la differenza di registrazione totale massima consentita per un rendiconto.</span><span class="sxs-lookup"><span data-stu-id="17ab9-118">In the **Posting** field, enter the maximum total posting difference allowed for a statement.</span></span>
12. <span data-ttu-id="17ab9-119">Nel campo **Turno**, immettere la differenza totale massima in un turno di un rendiconto.</span><span class="sxs-lookup"><span data-stu-id="17ab9-119">In the **Shift** field, enter the maximum total difference within a shift in a statement.</span></span>  
13. <span data-ttu-id="17ab9-120">Nel campo **Transazione**, immettere la differenza totale massima in una riga del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="17ab9-120">In the **Transaction** field, enter the maximum total difference in a statement line.</span></span>  
14. <span data-ttu-id="17ab9-121">Nel campo **Metodo di chiusura**, definire se le transazioni da includere nel rendiconto devono fanno parte di turno chiuso o se possono essere transazioni che rientrano nell'intervallo di data/ora definito.</span><span class="sxs-lookup"><span data-stu-id="17ab9-121">In the **Closing method** field, define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
15. <span data-ttu-id="17ab9-122">Nel campo **Fine giorno lavorativo**, immettere un'ora se le transazioni che si verificano dopo la mezzanotte devono essere registrate per il giorno precedente.</span><span class="sxs-lookup"><span data-stu-id="17ab9-122">In the **End of business day** field, enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
16. <span data-ttu-id="17ab9-123">Selezionare "Sì" in **Registra come giorno lavorativo** se le transazioni che si verificano dopo la mezzanotte devono essere registrate come parte del giorno precedente.</span><span class="sxs-lookup"><span data-stu-id="17ab9-123">Select "Yes" in **Post as business day** if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
17. <span data-ttu-id="17ab9-124">Selezionare "Sì" in **Dividi per metodo rendiconto** per ottenere i rendiconti creati per ciascun metodo di rendiconto definito.</span><span class="sxs-lookup"><span data-stu-id="17ab9-124">Select "Yes" in **Split by Statement method** to get statements created for each statement method defined.</span></span> <span data-ttu-id="17ab9-125">Ciò può essere utile se le prestazioni di registrazione devono essere migliorate per gli archivi con alti volumi di transazioni perché creano molti piccoli rendiconti che possono essere elaborati in parallelo.</span><span class="sxs-lookup"><span data-stu-id="17ab9-125">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
18. <span data-ttu-id="17ab9-126">Nella Scheda dettatlio **Generale**, nel campo **Cliente predefinito**, è possibile selezionare il conto cliente da utilizzare per le vendite ai clienti che entrano.</span><span class="sxs-lookup"><span data-stu-id="17ab9-126">In the **General** fastTab, in the **Default customer** field, you can select the customer account to use for sales to walk-in customers.</span></span>  

