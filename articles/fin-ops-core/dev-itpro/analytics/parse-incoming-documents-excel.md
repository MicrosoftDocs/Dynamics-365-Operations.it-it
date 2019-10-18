---
title: Analizzare i documenti in entrata in formato Excel
description: In questo argomento vengono fornite informazioni sulla progettazione di formati di report elettronici (ER) per analizzare il contenuto nei file di Microsoft Excel ricevuti.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 3f83271327df186d407516ff1a197800ffc8c78c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249358"
---
# <a name="parse-incoming-documents-in-excel-format"></a><span data-ttu-id="9e30f-103">Analizzare i documenti in entrata in formato Excel</span><span class="sxs-lookup"><span data-stu-id="9e30f-103">Parse incoming documents in Excel format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9e30f-104">È possibile progettare formati di report elettronici per analizzare file ricevuti di Microsoft Excel che rappresentano i dati nelle cartelle di lavoro di Microsoft Excel (file nel formato XLSX).</span><span class="sxs-lookup"><span data-stu-id="9e30f-104">You can design Electronic reporting (ER) formats to parse incoming Microsoft Excel files that represent data in Microsoft Excel workbooks (files in XLSX format).</span></span> <span data-ttu-id="9e30f-105">È quindi possibile utilizzare il contenuto di tali file per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e30f-105">You can then use the content from these files to update application data.</span></span> <span data-ttu-id="9e30f-106">Questa procedura è utile per:</span><span class="sxs-lookup"><span data-stu-id="9e30f-106">This is useful if you:</span></span>

- <span data-ttu-id="9e30f-107">Progettare un nuovo modello e formato e testarli in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="9e30f-107">Design a new model and format and want to test them at run-time.</span></span> <span data-ttu-id="9e30f-108">In questo caso, Excel simula i dati dell'applicazione effettivi.</span><span class="sxs-lookup"><span data-stu-id="9e30f-108">In this case, Excel will simulate the actual application data.</span></span>
- <span data-ttu-id="9e30f-109">Gestire i dati oltre la domanda in Excel e importarli per inviare un report specifico.</span><span class="sxs-lookup"><span data-stu-id="9e30f-109">Manage data beyond your application in Excel and want to import this data to submit a specific report.</span></span>

<span data-ttu-id="9e30f-110">Per ulteriori informazioni su questa funzionalità, riprodurre le guide attività **ER Importare dati da un file di Microsoft Excel (Parte 1: progettare il formato)** e **ER Importare dati da un file di Microsoft Excel (Parte 2: importare i dati)** (parti del processo aziendale 7.5.4.3 Acquisire/sviluppare componenti di soluzioni/servizi IT (10677)).</span><span class="sxs-lookup"><span data-stu-id="9e30f-110">To learn more about this feature, play the task guides **ER Import data from a Microsoft Excel file (Part 1: Design format)** and **ER Import data from a Microsoft Excel file (Part 2: Import data)** (parts of the 7.5.4.3 Acquire/Develop IT service/solution components (10677) business process).</span></span> <span data-ttu-id="9e30f-111">Queste guide attività illustrano in dettaglio come analizzare il file di Excel ricevuto utilizzando il formato di ER per importare le informazioni dai documenti ricevuti e aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="9e30f-111">These task guides walk through how the incoming Excel file can be parsed by using the ER format to import information from incoming documents and update application data.</span></span> <span data-ttu-id="9e30f-112">È possibile scaricare i file delle guide attività dall'[Area download Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).</span><span class="sxs-lookup"><span data-stu-id="9e30f-112">You can download the task guide files from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=874684).</span></span>

<span data-ttu-id="9e30f-113">Scaricare i file seguenti per completare le guide attività sopra menzionate.</span><span class="sxs-lookup"><span data-stu-id="9e30f-113">Download the following files to complete the task guides mentioned above.</span></span>

| <span data-ttu-id="9e30f-114">Descrizione contenuto</span><span class="sxs-lookup"><span data-stu-id="9e30f-114">Content description</span></span>                         | <span data-ttu-id="9e30f-115">File</span><span class="sxs-lookup"><span data-stu-id="9e30f-115">File</span></span>                                                                       |
|---------------------------------------------|----------------------------------------------------------------------------|
| <span data-ttu-id="9e30f-116">File ricevuto nel formato XLSX - modello</span><span class="sxs-lookup"><span data-stu-id="9e30f-116">Incoming file in .XLSX format - template</span></span>    | [<span data-ttu-id="9e30f-117">1099import-template.xlsx</span><span class="sxs-lookup"><span data-stu-id="9e30f-117">1099import-template.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
| <span data-ttu-id="9e30f-118">File ricevuto nel formato XLSX - dati di esempio</span><span class="sxs-lookup"><span data-stu-id="9e30f-118">Incoming file in .XLSX format - sample data</span></span> | [<span data-ttu-id="9e30f-119">1099import-data.xlsx</span><span class="sxs-lookup"><span data-stu-id="9e30f-119">1099import-data.xlsx</span></span>](https://go.microsoft.com/fwlink/?linkid=862266)     |

<span data-ttu-id="9e30f-120">Se non è stata ancora riprodotta la guida attività seguente, [ER Creare le configurazioni necessarie per importare dati da un file esterno](./tasks/er-required-configurations-import-data.md) nell'applicazione Finance and Operations corrente, scaricare il file seguente.</span><span class="sxs-lookup"><span data-stu-id="9e30f-120">If you have not yet played the following task guide, [ER Create required configurations to import data from an external file](./tasks/er-required-configurations-import-data.md) in the current Finance and Operations application, download the following file.</span></span>

| <span data-ttu-id="9e30f-121">Descrizione contenuto</span><span class="sxs-lookup"><span data-stu-id="9e30f-121">Content description</span></span>    | <span data-ttu-id="9e30f-122">File</span><span class="sxs-lookup"><span data-stu-id="9e30f-122">File</span></span>                                                            |
|------------------------|-----------------------------------------------------------------|
| <span data-ttu-id="9e30f-123">Configurazione modello di ER</span><span class="sxs-lookup"><span data-stu-id="9e30f-123">ER model configuration</span></span> | [<span data-ttu-id="9e30f-124">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="9e30f-124">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=862266) |
