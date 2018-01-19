--- 
title: " Configurazioni dei punti vendita per rendiconti di vendita al dettaglio"
description: "In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio."
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ceea24519d641c676521771cee274feb64ca7783
ms.openlocfilehash: c2140afc869686ae3f6d6c73ddaa31a4954d4d72
ms.contentlocale: it-it
ms.lasthandoff: 01/19/2018

---
# <a name="store-configurations-for-retail-statements"></a><span data-ttu-id="d65be-103"> Configurazioni dei punti vendita per rendiconti di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="d65be-103">Store configurations for Retail statements</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="d65be-104">In questa procedura sono illustrate le configurazioni per il punto vendita al dettaglio che interessa la modalità di creazione e registrazione dei rendiconti di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="d65be-104">This procedure walks through configurations for the Retail store that affect how Retail statements get created and posted.</span></span> <span data-ttu-id="d65be-105">Le dimensioni finanziarie dei punti vendita al dettaglio sono analizzate in un'altra procedura.</span><span class="sxs-lookup"><span data-stu-id="d65be-105">Financial dimensions on Retail stores are covered in another procedure.</span></span> <span data-ttu-id="d65be-106">Questa procedura utilizza la società dimostrativa USRT.</span><span class="sxs-lookup"><span data-stu-id="d65be-106">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="d65be-107">Passare a Vendita al dettaglio e commercio > Canali > Punti vendita al dettaglio > Tutti i punti vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="d65be-107">Go to Retail and commerce > Channels > Retail stores > All retail stores.</span></span>
2. <span data-ttu-id="d65be-108">Nell'elenco trovare e selezionare il record desiderato.</span><span class="sxs-lookup"><span data-stu-id="d65be-108">In the list, find and select the desired record.</span></span>
3. <span data-ttu-id="d65be-109">Nell'elenco fare clic sul collegamento nella riga selezionata.</span><span class="sxs-lookup"><span data-stu-id="d65be-109">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d65be-110">Le impostazioni nella sezione Rendiconto/Chiusura interessa la creazione, la convalida e la registrazione del rendiconto per l'archivio.</span><span class="sxs-lookup"><span data-stu-id="d65be-110">The settings in the Statement/closing section affect the statement creation, validation, and posting for the store.</span></span>  <span data-ttu-id="d65be-111">Aprire la sezione Rendiconto/Chiusura.</span><span class="sxs-lookup"><span data-stu-id="d65be-111">Open the Statement/closing section.</span></span>  
    * <span data-ttu-id="d65be-112">Selezionare il metodo da utilizzare per raggruppare le linee del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="d65be-112">Select the method you want to use to group the statement lines by.</span></span>  
    * <span data-ttu-id="d65be-113">Selezionare "Sì" se si deve creare un solo rendiconto al giorno quando si creano i rendiconti tramite il processo batch di creazione dei rendiconti.</span><span class="sxs-lookup"><span data-stu-id="d65be-113">Select "Yes" if there should only be one statement created per day when creating statements from the statement creation batch job.</span></span>  
    * <span data-ttu-id="d65be-114">Il campo Calcolo riepilogo incassi definisce se si devono aggiungere tutti i riepiloghi incassi o solo l'ultimo.</span><span class="sxs-lookup"><span data-stu-id="d65be-114">The Tender declaration calculation field defines whether tender declarations should be added together or if the last one should be used.</span></span>  
    * <span data-ttu-id="d65be-115">Selezionare il conto CoGe per la registrazione delle differenze di arrotondamento.</span><span class="sxs-lookup"><span data-stu-id="d65be-115">Select the ledger account to post rounding differences into.</span></span>  
    * <span data-ttu-id="d65be-116">Nel campo Importo arrotondamento massimo, è possibile immettere la differenza di arrotondamento massima consentita.</span><span class="sxs-lookup"><span data-stu-id="d65be-116">In the Maximum rounding difference field, you can enter the maximum rounding difference allowed.</span></span>  
    * <span data-ttu-id="d65be-117">Nel campo Registrazione, è possibile immettere la differenza di registrazione totale massima consentita per un rendiconto.</span><span class="sxs-lookup"><span data-stu-id="d65be-117">In the Posting field, you can enter the maximum total posting difference allowed for a statement.</span></span>  
    * <span data-ttu-id="d65be-118">Nel campo Turno, è possibile immettere la differenza totale massima in un turno di un rendiconto.</span><span class="sxs-lookup"><span data-stu-id="d65be-118">In the Shift field, you can enter the maximum total difference within a shift in a statement.</span></span>  
    * <span data-ttu-id="d65be-119">Nel campo Transazione, è possibile immettere la differenza totale massima in una riga del rendiconto.</span><span class="sxs-lookup"><span data-stu-id="d65be-119">In the Transaction field, you can enter the maximum total difference in a statement line.</span></span>  
    * <span data-ttu-id="d65be-120">Nel campo Metodo di chiusura, è possibile definire se le transazioni da includere nel rendiconto devono fanno parte di turno chiuso o se possono essere transazioni che rientrano nell'intervallo di data/ora definito.</span><span class="sxs-lookup"><span data-stu-id="d65be-120">In the Closing method field, you can define whether transactions that will be included in a statement should be part of a closed shift or if they can be any transactions within the defined date/time range.</span></span>  
    * <span data-ttu-id="d65be-121">Nel campo Fine giorno lavorativo, è possibile immettere un'ora se le transazioni che si verificano dopo la mezzanotte devono essere registrate per il giorno precedente.</span><span class="sxs-lookup"><span data-stu-id="d65be-121">In the End of business day field, you can enter a time if transactions that happen after midnight should be posted with the previous day.</span></span>  
    * <span data-ttu-id="d65be-122">Selezionare "Sì" se le transazioni che si verificano dopo la mezzanotte devono essere registrate come parte del giorno precedente.</span><span class="sxs-lookup"><span data-stu-id="d65be-122">Select "Yes" if transactions that happen after midnight should be posted as part of the previous day.</span></span>  
    * <span data-ttu-id="d65be-123">Selezionare "Sì" per ottenere i rendiconti creati per ciascun metodo di rendiconto definito.</span><span class="sxs-lookup"><span data-stu-id="d65be-123">Select "Yes" to get statements created for each statement method defined.</span></span> <span data-ttu-id="d65be-124">Ciò può essere utile se le prestazioni di registrazione devono essere migliorate per gli archivi con alti volumi di transazioni perché creano molti piccoli rendiconti che possono essere elaborati in parallelo.</span><span class="sxs-lookup"><span data-stu-id="d65be-124">This can be useful if the performance of the posting needs to be improved for stores with high transaction volumes since it will create many smaller statements that can be processed in parallel.</span></span>  
    * <span data-ttu-id="d65be-125">Nel campo Cliente predefinito, è possibile selezionare il conto cliente da utilizzare per le vendite ai clienti che entrano.</span><span class="sxs-lookup"><span data-stu-id="d65be-125">In the Default customer field, you can select the customer account to use for sales to walk-in customers.</span></span>  


