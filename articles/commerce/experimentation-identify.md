---
title: Identificare un'ipotesi e determinare le metriche per un esperimento
description: In questo argomento viene descritto come identificare l'ipotesi e le metriche per un esperimento che eseguirai in un sito Web di e-commerce in Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 99642861d69b7545f03c6ed2c2650eadeb377534
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930226"
---
# <a name="identify-a-hypothesis-and-determine-success-metrics-for-an-experiment"></a><span data-ttu-id="5e859-103">Identificare un'ipotesi e determinare le metriche per un esperimento</span><span class="sxs-lookup"><span data-stu-id="5e859-103">Identify a hypothesis and determine success metrics for an experiment</span></span>
<span data-ttu-id="5e859-104">La prima fase del ciclo di vita della sperimentazione include l'identificazione dell'ipotesi per l'esperimento e la determinazione delle metriche da monitorare per valutare l'esito positivo dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="5e859-104">The first phase in the experimentation lifecycle includes identifying the hypothesis for the experiment and determining the metrics you'll track to evaluate success.</span></span> <span data-ttu-id="5e859-105">Il diagramma seguente mostra tutti i passaggi relativi alla [configurazione e all'esecuzione di un esperimento](experimentation-overview.md) su un sito Web di e-commerce in Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e859-105">The following diagram shows all of the steps involved in [setting up and running an experiment](experimentation-overview.md) on an e-Commerce website in Dynamics 365 Commerce.</span></span> <span data-ttu-id="5e859-106">I passaggi aggiuntivi sono esposti in argomenti separati.</span><span class="sxs-lookup"><span data-stu-id="5e859-106">Additional steps are covered in separate topics.</span></span> 

<span data-ttu-id="5e859-107">[ ![Percorso utente per sperimentazione - Identificazione](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span><span class="sxs-lookup"><span data-stu-id="5e859-107">[ ![Experimentation user journey - Identify](./media/experimentation_identify.svg) ](./media/experimentation_identify.svg#lightbox)</span></span>

<span data-ttu-id="5e859-108">Un'ipotesi è un'asserzione in cui prevedi il risultato dell'esperimento.</span><span class="sxs-lookup"><span data-stu-id="5e859-108">A hypothesis is a statement where you predict the outcome of the experiment.</span></span> <span data-ttu-id="5e859-109">Molti fattori contribuiscono alla definizione di un'ipotesi, ad esempio la ricerca sul comportamento degli utenti e sui dati del sito Web raccolti.</span><span class="sxs-lookup"><span data-stu-id="5e859-109">Many factors go into defining a hypothesis, for example, research about user behavior and website data you've collected.</span></span> <span data-ttu-id="5e859-110">Con l'ipotesi, definirai l'assunto o la teoria che vuoi convalidare con l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="5e859-110">With the hypothesis, you'll define the assumption or theory you want to validate with your experiment.</span></span> <span data-ttu-id="5e859-111">Un esempio di ipotesi per l'esperimento potrebbe essere "*un'immagine di una t-shirt bianca sulla mia home page genererà una percentuale di clic più alta rispetto a un maglione blu scuro durante i mesi estivi poiché le persone vogliono indossare qualcosa di leggero e di colore chiaro in estate.*"</span><span class="sxs-lookup"><span data-stu-id="5e859-111">An example of a hypothesis for your experiment may be "*a picture of a white t-shirt on my home page will drive a higher clickthrough rate than a navy sweater during summer months because people want to wear something lightweight and light colored in the summer.*"</span></span> <span data-ttu-id="5e859-112">In tal caso, creerai varianti che includono una t-shirt bianca e un maglione blu scuro e pubblicherai entrambi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="5e859-112">In that case, you'll create variations that include a white t-shirt and a navy sweater, and publish both at the same time.</span></span>

<span data-ttu-id="5e859-113">Per convalidare un'ipotesi, l'esito positivo o negativo di un esperimento dovrebbe essere direttamente associato alle azioni dell'utente; ad esempio, se l'utente del sito web fa clic su un collegamento o un pulsante.</span><span class="sxs-lookup"><span data-stu-id="5e859-113">To validate a hypothesis, the success or failure of an experiment should be directly tied to user actions; for example, if the website user clicks a link or button.</span></span> <span data-ttu-id="5e859-114">Queste azioni devono corrispondere agli eventi che verranno segnalati al servizio di terze parti che monitora l'esperimento.</span><span class="sxs-lookup"><span data-stu-id="5e859-114">These actions must correspond with events that will be reported to the third-party service tracking the experiment.</span></span> <span data-ttu-id="5e859-115">Nel tempo, la percentuale di utenti che intraprendono l'azione verrà conteggiata come metrica che puoi utilizzare per generare rapporti e condurre analisi.</span><span class="sxs-lookup"><span data-stu-id="5e859-115">Over time, the percentage of users that take the action will be tallied as a metric you can use to generate reports and conduct analyses.</span></span> <span data-ttu-id="5e859-116">Fai riferimento all'argomento [Eventi dei componenti Commerce per la diagnostica e la risoluzione dei problemi](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) per esaminare tutti gli eventi e gli attributi disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e859-116">Refer to the [Commerce component events for diagnostics and troubleshooting](dev-itpro/retail-component-events-diagnostics-troubleshooting.md) topic to review all of the available events and attributes.</span></span>

## <a name="previous-step"></a><span data-ttu-id="5e859-117">Passaggio precedente</span><span class="sxs-lookup"><span data-stu-id="5e859-117">Previous step</span></span>
[<span data-ttu-id="5e859-118">Sperimentazione in Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5e859-118">Experimentation in Dynamics 365 Commerce</span></span>](experimentation-overview.md)


## <a name="next-step"></a><span data-ttu-id="5e859-119">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="5e859-119">Next step</span></span>
[<span data-ttu-id="5e859-120">Configurare un esperimento</span><span class="sxs-lookup"><span data-stu-id="5e859-120">Set up an experiment</span></span>](experimentation-setup.md)
