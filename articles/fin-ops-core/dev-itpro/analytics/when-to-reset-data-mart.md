---
title: Domande frequenti sul ripristino dei data mart
description: In questo argomento vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart.
author: jinniew
ms.date: 06/09/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jiwo
ms.search.validFrom: 2021-05-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7cd96c7bc698986ef1ef07ca88479a3d49f22924
ms.sourcegitcommit: ecabf43282a3e55f1db40341aa3f3c7950b9e94c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "6266611"
---
# <a name="data-mart-resets-faq"></a><span data-ttu-id="cd853-103">Domande frequenti sul ripristino dei data mart</span><span class="sxs-lookup"><span data-stu-id="cd853-103">Data mart resets FAQ</span></span>

<span data-ttu-id="cd853-104">In questo argomento vengono fornite risposte ad alcune domande frequenti sul ripristino dei data mart.</span><span class="sxs-lookup"><span data-stu-id="cd853-104">This topic provides answers to some frequently asked questions about data mart resets.</span></span> <span data-ttu-id="cd853-105">Un ripristino del data mart può richiedere molto tempo e, a seconda delle circostanze, potrebbe non essere la soluzione necessaria.</span><span class="sxs-lookup"><span data-stu-id="cd853-105">A reset of the data mart can be a time-consuming process and, depending on the circumstances, might not be the solution that is required.</span></span> <span data-ttu-id="cd853-106">Pertanto, questo argomento include informazioni sulle circostanze in cui un ripristino del data mart potrebbe essere d'aiuto e anche sulle circostanze in cui è improbabile che sia d'aiuto.</span><span class="sxs-lookup"><span data-stu-id="cd853-106">Therefore, this topic includes information about circumstances where a data mart reset might help and also circumstances where it's unlikely to help.</span></span>

## <a name="what-is-a-data-mart-reset"></a><span data-ttu-id="cd853-107">Cos'è una reimpostazione di un data mart?</span><span class="sxs-lookup"><span data-stu-id="cd853-107">What is a data mart reset?</span></span>

<span data-ttu-id="cd853-108">Un ripristino del data mart disabiliterà le attività di integrazione, eliminerà tutti i dati del data mart e quindi riattiverà l'integrazione.</span><span class="sxs-lookup"><span data-stu-id="cd853-108">A data mart reset will disable the integration tasks, delete all the data mart data, and then re-enable integration.</span></span>

<span data-ttu-id="cd853-109">Per garantire che i vecchi dati non vengano inseriti, è possibile avviare un ripristino del data mart solo dopo che le attività esistenti sono state completate.</span><span class="sxs-lookup"><span data-stu-id="cd853-109">To ensure that old data isn't inserted, a data mart reset can be started only after existing tasks are completed.</span></span> <span data-ttu-id="cd853-110">Se tenti di reimpostare il data mart prima del completamento di tutte le attività, è possibile che venga visualizzato un messaggio del tipo "Impossibile elaborare il ripristino del data mart a causa di un'attività attiva.</span><span class="sxs-lookup"><span data-stu-id="cd853-110">If you try to reset the data mart before all tasks are completed, you might receive a message such as, "The data mart reset was unable to be processed because of an active task.</span></span> <span data-ttu-id="cd853-111">Riprova più tardi."</span><span class="sxs-lookup"><span data-stu-id="cd853-111">Please try again later."</span></span>

## <a name="when-do-i-have-to-do-a-data-mart-reset"></a><span data-ttu-id="cd853-112">Quando si esegue il ripristino del data mart?</span><span class="sxs-lookup"><span data-stu-id="cd853-112">When do I have to do a data mart reset?</span></span>

<span data-ttu-id="cd853-113">Se una o più delle seguenti affermazioni si applicano alla tua situazione, la tua organizzazione può trarre vantaggio da un ripristino del data mart:</span><span class="sxs-lookup"><span data-stu-id="cd853-113">If one or more of the following statements apply to your situation, your organization can benefit from a data mart reset:</span></span>

- <span data-ttu-id="cd853-114">Il database dell'applicazione è stato ripristinato.</span><span class="sxs-lookup"><span data-stu-id="cd853-114">The application database was restored.</span></span>
- <span data-ttu-id="cd853-115">Hai aperto un ticket di supporto e un tecnico del supporto ti ha chiesto di ripristinare il data mart come parte di un passaggio di risoluzione dei problemi.</span><span class="sxs-lookup"><span data-stu-id="cd853-115">You opened a support ticket, and a Support engineer instructed you to reset the data mart as part of a troubleshooting step.</span></span>
 
## <a name="when-is-a-data-mart-reset-inappropriate"></a><span data-ttu-id="cd853-116">Quando non è appropriato ripristinare un data mart?</span><span class="sxs-lookup"><span data-stu-id="cd853-116">When is a data mart reset inappropriate?</span></span>

<span data-ttu-id="cd853-117">Ecco alcune circostanze in cui non è consigliabile reimpostare un data mart:</span><span class="sxs-lookup"><span data-stu-id="cd853-117">Here are some of the circumstances where we don't recommend that you reset the data mart:</span></span>

- <span data-ttu-id="cd853-118">Stai riscontrando problemi di prestazioni associati a una sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="cd853-118">You're experiencing performance issues that are associated with data synchronization.</span></span>
- <span data-ttu-id="cd853-119">Se hai uno schema di ripristino ricorrente per uno dei seguenti motivi:</span><span class="sxs-lookup"><span data-stu-id="cd853-119">You have a recurring reset pattern for any of the following reasons:</span></span>

    - <span data-ttu-id="cd853-120">**Dati mancanti** – Se noti che mancano dei dati, apri un ticket di supporto con Microsoft per rivedere il formato del report e i possibili problemi di sincronizzazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="cd853-120">**Missing data** – If you notice that data is missing, open a support ticket with Microsoft to review your report format and possible data synchronization issues.</span></span>
    - <span data-ttu-id="cd853-121">**Stato di integrazione bloccato**</span><span class="sxs-lookup"><span data-stu-id="cd853-121">**Stuck integration state**</span></span>
    - <span data-ttu-id="cd853-122">**Record obsoleti** - I record obsoleti da soli non giustificano necessariamente il ripristino del data mart.</span><span class="sxs-lookup"><span data-stu-id="cd853-122">**Stale records** – Stale records by themselves don't necessarily justify a data mart reset.</span></span> <span data-ttu-id="cd853-123">Se hai un set di dati di grandi dimensioni, l'esecuzione del processo di reimpostazione richiederà un po' di tempo, ma è improbabile che si verifichi un miglioramento.</span><span class="sxs-lookup"><span data-stu-id="cd853-123">If you have a large data set, the reset process will take some time to run but is unlikely to lead to any improvement.</span></span>

## <a name="if-i-reset-the-data-mart-will-i-lose-reports-that-ive-already-designed"></a><span data-ttu-id="cd853-124">Se reimposto il data mart, perderò i report che ho già progettato?</span><span class="sxs-lookup"><span data-stu-id="cd853-124">If I reset the data mart, will I lose reports that I've already designed?</span></span>

<span data-ttu-id="cd853-125">N.</span><span class="sxs-lookup"><span data-stu-id="cd853-125">No.</span></span> <span data-ttu-id="cd853-126">I report vengono archiviati in tabelle SQL che non sono influenzate da un ripristino del data mart.</span><span class="sxs-lookup"><span data-stu-id="cd853-126">Your reports are stored in SQL tables that aren't affected by a data mart reset.</span></span> <span data-ttu-id="cd853-127">Se sei preoccupato di perdere i report che hai progettato, puoi eseguire il backup dei dati che non vuoi rischiare di perdere.</span><span class="sxs-lookup"><span data-stu-id="cd853-127">If you're concerned about losing reports that you've designed, you can back up the designs that you don't want to lose.</span></span> <span data-ttu-id="cd853-128">Per eseguire il backup dei progetti, apri Progettazione report e vai a **Società \> Società \> Blocchi predefiniti \> Esporta**.</span><span class="sxs-lookup"><span data-stu-id="cd853-128">To back up designs, open Report Designer, and go to **Company \> Companies \> Building Blocks \> Export**.</span></span>
 
## <a name="do-all-users-have-to-exit-the-system-before-i-can-reset-the-data-mart"></a><span data-ttu-id="cd853-129">Tutti gli utenti devono uscire dal sistema prima di poter ripristinare il data mart?</span><span class="sxs-lookup"><span data-stu-id="cd853-129">Do all users have to exit the system before I can reset the data mart?</span></span>

<span data-ttu-id="cd853-130">N.</span><span class="sxs-lookup"><span data-stu-id="cd853-130">No.</span></span> <span data-ttu-id="cd853-131">Gli utenti possono continuare a lavorare nel sistema durante il ripristino del data mart.</span><span class="sxs-lookup"><span data-stu-id="cd853-131">Users can continue to work in the system during a data mart reset.</span></span> <span data-ttu-id="cd853-132">Tuttavia, non potranno accedere ai report creati con Financial Reporter fino al termine del ripristino.</span><span class="sxs-lookup"><span data-stu-id="cd853-132">However, until the reset is completed, users won't be able to access any reports that were created by using Financial Reporter.</span></span>

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
