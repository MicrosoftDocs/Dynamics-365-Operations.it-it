---
title: Richiamare i flussi di automazione dei processi per creare ordini di controllo qualità
description: Questo argomento fornisce risorse per l'utilizzo di Power Automate per automatizzare i processi aziendali, utilizzando l'esempio degli ordini di controllo qualità.
author: cabeln
ms.date: 05/28/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: cabeln
ms.search.validFrom: 2021-05-28
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f35adab3075ba810964a41899ba95ae40c115e83
ms.sourcegitcommit: 588f8343aaa654309d2ff735fd437dba6acd9d46
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115195"
---
# <a name="invoke-process-automation-flows-to-create-quality-orders"></a><span data-ttu-id="daf07-103">Richiamare i flussi di automazione dei processi per creare ordini di controllo qualità</span><span class="sxs-lookup"><span data-stu-id="daf07-103">Invoke process automation flows to create quality orders</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="daf07-104">Le organizzazioni sono testimoni di una crescente richiesta di automatizzazione dei processi aziendali standard, di interazioni più convenienti al personale e di utilizzo dei vari segnali di dati e sistemi per guidare automaticamente i processi aziendali.</span><span class="sxs-lookup"><span data-stu-id="daf07-104">Organizations have an increasing demand to automate standard business processes, provide more convenient interactions to the staff, and utilize various data signals and systems to drive business processes automatically.</span></span> <span data-ttu-id="daf07-105">Con Robotic Process Automation (RPA) e Microsoft Power Automate, le aziende possono utilizzare un'esperienza senza codice per automatizzare i processi ripetitivi, ottenendo così efficienza e precisione.</span><span class="sxs-lookup"><span data-stu-id="daf07-105">With robotic process automation (RPA) and Microsoft Power Automate, businesses can use a no-code experience to automate repetitive processes, thus gaining efficiency and accuracy.</span></span>

<span data-ttu-id="daf07-106">Il modello di soluzione di automazione scaricabile per Supply Chain Management mostra come Power Automate può essere utilizzato per automatizzare i processi aziendali utilizzando gli ordini di controllo qualità come esempio.</span><span class="sxs-lookup"><span data-stu-id="daf07-106">The downloadable automation solution template for Supply Chain Management showcases how Power Automate can be used to automate business processes using quality orders as an example.</span></span>

<span data-ttu-id="daf07-107">È possibile scaricare il modello della soluzione di automazione [qui](https://aka.ms/D365SCMQualityOrderRPASolution).</span><span class="sxs-lookup"><span data-stu-id="daf07-107">You can download the automation solution template [here](https://aka.ms/D365SCMQualityOrderRPASolution).</span></span>

<span data-ttu-id="daf07-108">Per una panoramica di questa funzionalità e delle sue capacità, guarda il seguente video: [Utilizzare RPA per creare ordini di qualità in Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span><span class="sxs-lookup"><span data-stu-id="daf07-108">For an overview of this feature and its capabilities, see the following video: [Utilize RPA to create quality orders in Dynamics 365 Supply Chain Management](https://www.youtube.com/watch?v=LFbzJ6-H89w)</span></span>

<span data-ttu-id="daf07-109">![Opzioni di automazione con RPA](media/rpa-automation-options.png "Opzioni di automazione con RPA")</span><span class="sxs-lookup"><span data-stu-id="daf07-109">![Automation options with RPA](media/rpa-automation-options.png "Automation options with RPA")</span></span>

<span data-ttu-id="daf07-110">Il modello di soluzione Power Automate include un flusso di automazione cloud e un flusso di automazione desktop che automatizzano la creazione di ordini di controllo qualità in Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="daf07-110">The Power Automate solution template includes a cloud automation flow and a desktop automation flow that automate the creation of quality orders in Supply Chain Management.</span></span>

<span data-ttu-id="daf07-111">L'automazione può essere avviata in risposta a molti eventi e segnali, inclusi input dell'utente o segnali del computer (incluso Internet of Things (IoT)).</span><span class="sxs-lookup"><span data-stu-id="daf07-111">The automation can be started in response to many events and signals, including user input or machine signals (including the Internet of Things (IoT)).</span></span> <span data-ttu-id="daf07-112">L'esempio della Power Application *Q-Order* è incluso nel modello della soluzione.</span><span class="sxs-lookup"><span data-stu-id="daf07-112">The *Q-Order* Power Application example is included in the solution template.</span></span> <span data-ttu-id="daf07-113">Consente all'utente di eseguire la scansione del codice a matrice di un articolo, inserire la quantità e allegare immagini utilizzando una fotocamera.</span><span class="sxs-lookup"><span data-stu-id="daf07-113">It allows the user to scan an item QR code, enter quantity, and attach pictures using a camera.</span></span>

<span data-ttu-id="daf07-114">I parametri della soluzione sono inclusi per configurare l'automazione per un caso d'uso specifico in una struttura di produzione.</span><span class="sxs-lookup"><span data-stu-id="daf07-114">Solution parameters are included to configure the automation for a specific use case in a production facility.</span></span>

<span data-ttu-id="daf07-115">![Crea ordine di controllo qualità](media/rpa-create-quality-roder.png "Crea ordine di controllo qualità")</span><span class="sxs-lookup"><span data-stu-id="daf07-115">![Create quality order](media/rpa-create-quality-roder.png "Create quality order")</span></span>

<span data-ttu-id="daf07-116">Per una guida dettagliata completa su come scaricare, installare e utilizzare la soluzione di esempio per automatizzare la creazione dell'ordine di controllo qualità, vedi [Automatizzare la creazione degli ordini di controllo qualità Dynamics 365 Supply Chain Management con Robotic Process Automation utilizzando Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span><span class="sxs-lookup"><span data-stu-id="daf07-116">For a complete step-by-step guide about how to download, install, and use the sample solution for automating quality order creation, see [Automate quality order creation on Dynamics 365 Supply Chain Management with Robotic Process Automation using Power Automate Desktop](/power-automate/desktop-flows/dynamics365-scm-rpa).</span></span>

