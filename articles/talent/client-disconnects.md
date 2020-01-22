---
title: Disconnessione del client Talent
description: In questo argomento viene illustrato come procedere se il cliente viene disconnesso dal relativo ambiente e non sa il motivo.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 02df31b56c0e960a16ec2aadd8b1e817e0b6ec65
ms.sourcegitcommit: 871707a3fd236da693a3d51f401eb0cb9d4bae39
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/06/2019
ms.locfileid: "2898459"
---
# <a name="talent-client-disconnects"></a><span data-ttu-id="7ec39-103">Disconnessione del client Talent</span><span class="sxs-lookup"><span data-stu-id="7ec39-103">Talent client disconnects</span></span>

<span data-ttu-id="7ec39-104">**Dettagli ambiente**</span><span class="sxs-lookup"><span data-stu-id="7ec39-104">**Environment details**</span></span> 

<span data-ttu-id="7ec39-105">Questo problema può verificarsi in tutti gli ambienti.</span><span class="sxs-lookup"><span data-stu-id="7ec39-105">This issue can occur in all environments.</span></span>
 
<span data-ttu-id="7ec39-106">**Sintomo**</span><span class="sxs-lookup"><span data-stu-id="7ec39-106">**Symptom**</span></span> 

<span data-ttu-id="7ec39-107">Il cliente viene disconnesso dal relativo ambiente e non sa il motivo.</span><span class="sxs-lookup"><span data-stu-id="7ec39-107">The customer is disconnected from his or her environment and doesn't know why.</span></span> <span data-ttu-id="7ec39-108">Il cliente riceve uno dei seguenti messaggi di errore:</span><span class="sxs-lookup"><span data-stu-id="7ec39-108">The customer receives one of the following error messages:</span></span>

- <span data-ttu-id="7ec39-109">La connessione è stata persa.</span><span class="sxs-lookup"><span data-stu-id="7ec39-109">We've lost your connection.</span></span> <span data-ttu-id="7ec39-110">Fare clic su Chiudi per continuare a lavorare.</span><span class="sxs-lookup"><span data-stu-id="7ec39-110">Click Close to continue working.</span></span>
- <span data-ttu-id="7ec39-111">Connettività di rete persa. Fare clic su Riprova per riprovare.</span><span class="sxs-lookup"><span data-stu-id="7ec39-111">It appears you lost network connectivity, click Retry to try again.</span></span>

<span data-ttu-id="7ec39-112">**Flag rosso**</span><span class="sxs-lookup"><span data-stu-id="7ec39-112">**Red flag**</span></span>

<span data-ttu-id="7ec39-113">Questo problema si verifica in genere quando gli utenti nella fase di implementazione confrontano informazioni negli ambienti di produzione e test e dimenticano che si spostano da una sessione all'altra.</span><span class="sxs-lookup"><span data-stu-id="7ec39-113">This issue often occurs when users are in the implementation stage, are comparing information across production and test environments, and forget that they are moving between sessions.</span></span> <span data-ttu-id="7ec39-114">Se gli utenti sono in questa fase, molto probabilmente avranno questo problema.</span><span class="sxs-lookup"><span data-stu-id="7ec39-114">If users are at this stage, they will most likely experience this issue.</span></span>

<span data-ttu-id="7ec39-115">**Problema**</span><span class="sxs-lookup"><span data-stu-id="7ec39-115">**Issue**</span></span> 

<span data-ttu-id="7ec39-116">**Tipi di browser:** Google Chrome, Internet Explorer e Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="7ec39-116">**Browser types:** Google Chrome, Internet Explorer, and Microsoft Edge</span></span>

<span data-ttu-id="7ec39-117">Microsoft Dynamics 365 Talent disconnette gli utenti quando due differenti sessioni sono aperte contemporaneamente per lo stesso utente e lo stesso tipo di browser.</span><span class="sxs-lookup"><span data-stu-id="7ec39-117">Microsoft Dynamics 365 Talent disconnects users when two different sessions are open at the same time for the same user and the same browser type.</span></span> <span data-ttu-id="7ec39-118">Ad esempio, l'utente A sta visualizzando l'ambiente 1 e l'ambiente 2 in Chrome. Non è rilevante se gli utenti aprono differenti finestre di browser o schede.</span><span class="sxs-lookup"><span data-stu-id="7ec39-118">(For example, user A is viewing both environment 1 and environment 2 in Chrome.) It doesn't matter whether the users open different browser windows or different tabs.</span></span> <span data-ttu-id="7ec39-119">Se le stesse credenziali utente sono utilizzate per accedere contemporaneamente all'ambiente 1 e all'ambiente 2 e nello stesso tipo di browser, Talent disconnette una delle sessioni.</span><span class="sxs-lookup"><span data-stu-id="7ec39-119">If the same user credentials are used to sign in to both environment 1 and environment 2 at the same time and in the same browser type, Talent disconnects one of the sessions.</span></span>

<span data-ttu-id="7ec39-120">**Soluzione**</span><span class="sxs-lookup"><span data-stu-id="7ec39-120">**Solution**</span></span>

<span data-ttu-id="7ec39-121">Assicurarsi che un solo ambiente sia aperto in uno specifico momento per un determinato tipo di browser.</span><span class="sxs-lookup"><span data-stu-id="7ec39-121">Make sure that only one environment is open at a time for a given browser type.</span></span> <span data-ttu-id="7ec39-122">Gli utenti possono aprire più sessioni per lo stesso ambiente (ovvero più schede nello stesso browser).</span><span class="sxs-lookup"><span data-stu-id="7ec39-122">Users can open multiple sessions to the same environment (that is, multiple tabs in the same browser).</span></span>

<span data-ttu-id="7ec39-123">Gli utenti che desiderano accedere a due ambienti contemporaneamente devono aprire ogni ambiente in un tipo di browser diverso.</span><span class="sxs-lookup"><span data-stu-id="7ec39-123">Users who want to jump between two environments at the same time should open each environment in a different browser type.</span></span> <span data-ttu-id="7ec39-124">Ad esempio, l'utente A può visualizzare l'ambiente 1 in Chrome e l'ambiente 2 in Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="7ec39-124">(For example, user A can view environment 1 in Chrome and environment 2 in Microsoft Edge.)</span></span>
