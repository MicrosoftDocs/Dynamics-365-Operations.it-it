---
title: Generare documenti elettronici con aggiornare i dati dell'applicazione utilizzando la creazione di report elettronici (ER)
description: È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione per generare i documenti elettronici in uscita.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f66a173c7d66f915a7802e42caf1a36f661eea1
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944319"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a><span data-ttu-id="c9274-103">Generare documenti elettronici e aggiornare i dati dell'applicazione con la creazione di report elettronici</span><span class="sxs-lookup"><span data-stu-id="c9274-103">Generate electronic documents and update application data by using ER</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c9274-104">È possibile progettare i formati di report elettronici (ER) utilizzabili nell'applicazione per generare i documenti elettronici in uscita.</span><span class="sxs-lookup"><span data-stu-id="c9274-104">You can design Electronic reporting (ER) formats that can be used in the application to generate outgoing electronic documents.</span></span> <span data-ttu-id="c9274-105">È inoltre possibile progettare i formati di ER che analizzano i documenti elettronici in entrata e utilizzano il contenuto di questi documenti per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c9274-105">You can also design ER formats that parse incoming electronic documents and use the content in those documents to update application data.</span></span>

<span data-ttu-id="c9274-106">Grazie a questa funzionalità, un unico formato di ER può essere utilizzato per generare i documenti elettronici in uscita quindi aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c9274-106">With this functionality, a single ER format can be used to generate outgoing electronic documents and then update the application data.</span></span> <span data-ttu-id="c9274-107">Questa funzionalità può essere utilizzata negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="c9274-107">This feature can be used in the following scenarios:</span></span>

- <span data-ttu-id="c9274-108">Per impedire l'utilizzo ripetuto dei dati dell'applicazione nei successivi processi, è possibile contrassegnare i dati di un'applicazione subito dopo essere stati utilizzati per generare i documenti elettronici.</span><span class="sxs-lookup"><span data-stu-id="c9274-108">To prevent repeated usage of application data in subsequent processes you can mark an application’s data immediately after it is used to generate electronic documents.</span></span> <span data-ttu-id="c9274-109">Ad esempio, è possibile contrassegnare le transazioni di pagamento come già elaborate subito dopo che sono state importate in un messaggio di pagamento generato.</span><span class="sxs-lookup"><span data-stu-id="c9274-109">For example, you can mark payment transactions as already processed immediately after they have been included in a generated payment message.</span></span>
- <span data-ttu-id="c9274-110">Per archiviare i dettagli di elaborazione di documenti elettronici generati mediante la logica ER.</span><span class="sxs-lookup"><span data-stu-id="c9274-110">To store the processing details of electronic documents that have been generated using ER logic.</span></span> <span data-ttu-id="c9274-111">Ad esempio, un ID univoco del messaggio di pagamento generato utilizzando l'espressione ER.</span><span class="sxs-lookup"><span data-stu-id="c9274-111">For example, a unique payment message identification that is generated using the ER expression.</span></span> <span data-ttu-id="c9274-112">L'espressione è basata sulle informazioni immesse nella finestra di dialogo ER quando il formato di ER viene eseguito per generare documenti.</span><span class="sxs-lookup"><span data-stu-id="c9274-112">The expression is based on information entered in the ER dialog box when the ER format is run to generate documents.</span></span>

<span data-ttu-id="c9274-113">Per ulteriori informazioni su questa funzionalità, utilizzare il set di Guide attività sulla generazione dei documenti ER mediante l'aggiornamento dei dati dell'applicazione (parte del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)), che include i dettagli sul reporting e l'archiviazione Intrastat.</span><span class="sxs-lookup"><span data-stu-id="c9274-113">To learn more about this feature, play the set of ER Generate documents with application data update Task guides (part of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process), which walk you through the details of Intrastat reporting and archiving.</span></span> <span data-ttu-id="c9274-114">I seguenti file sono necessari per completare alcuni passaggi in queste Guide attività.</span><span class="sxs-lookup"><span data-stu-id="c9274-114">The following files are required to complete certain steps in these Task guides.</span></span> <span data-ttu-id="c9274-115">Scaricare e salvare i file nel computer locale.</span><span class="sxs-lookup"><span data-stu-id="c9274-115">Download and save these files to your local machine.</span></span>

- [<span data-ttu-id="c9274-116">Configurazione del modello dati di ER: Intrastat (modello)</span><span class="sxs-lookup"><span data-stu-id="c9274-116">ER data model configuration: Intrastat (model)</span></span>](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [<span data-ttu-id="c9274-117">Configurazione del mapping del modello di ER: Intrastat (mapping)</span><span class="sxs-lookup"><span data-stu-id="c9274-117">ER model mapping configuration: Intrastat (mapping)</span></span>](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [<span data-ttu-id="c9274-118">Configurazione del formato di ER: Intrastat (formato)</span><span class="sxs-lookup"><span data-stu-id="c9274-118">ER format configuration: Intrastat (format)</span></span>](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
