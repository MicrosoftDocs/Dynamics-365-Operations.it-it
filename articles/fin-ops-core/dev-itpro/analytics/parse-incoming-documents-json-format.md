---
title: Analizzare i documenti in entrata in formato JSON
description: In questo argomento viene descritto come impostare i formati di report elettronici (ER) per analizzare i documenti in arrivo in formato JavaScript Object Notation (JSON).
author: kfend
manager: AnnBe
ms.date: 05/20/2019
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
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: 92ef83bc1783b00a4d7d9739ca1c17e863c7ff44
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185269"
---
# <a name="parse-incoming-documents-in-json-format"></a><span data-ttu-id="a47d4-103">Analizzare i documenti in entrata in formato JSON</span><span class="sxs-lookup"><span data-stu-id="a47d4-103">Parse incoming documents in JSON format</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a47d4-104">È possibile progettare formati di report elettronici (ER) per analizzare i documenti elettronici in arrivo che rappresentano dati in un formato di testo basato su JavaScript (in altre parole, file in formato \[JSON\]).</span><span class="sxs-lookup"><span data-stu-id="a47d4-104">You can design Electronic reporting (ER) formats to parse incoming electronic documents that represent data in a text format that is based on JavaScript (in other words, files in JavaScript Object Notation \[JSON\] format).</span></span>

<span data-ttu-id="a47d4-105">Per ulteriori informazioni su questa funzionalità, scaricare i file nella seguente tabella e quindi riprodurre la guida attività ER Creare una configurazione di formato per importare dati da un file JSON esterno.</span><span class="sxs-lookup"><span data-stu-id="a47d4-105">To learn more about this feature, download the files in the following table, and then play the ER Create a format configuration to import data from an external JSON file task guide.</span></span> <span data-ttu-id="a47d4-106">Questa guida attività illustra come utilizzare un formato ER per analizzare un file JSON in arrivo per aggiornare i dati dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a47d4-106">This task guide shows how an ER format can be used to parse an incoming JSON file to update application data.</span></span>

| <span data-ttu-id="a47d4-107">Funzione</span><span class="sxs-lookup"><span data-stu-id="a47d4-107">Title</span></span>                                  | <span data-ttu-id="a47d4-108">Nome file</span><span class="sxs-lookup"><span data-stu-id="a47d4-108">File name</span></span> |
|----------------------------------------|-----------|
| <span data-ttu-id="a47d4-109">Configurazione di formato ER</span><span class="sxs-lookup"><span data-stu-id="a47d4-109">ER format configuration</span></span>                | [<span data-ttu-id="a47d4-110">Formato per importare il file trans_JSON.xml dei fornitori</span><span class="sxs-lookup"><span data-stu-id="a47d4-110">Format for importing vendors' trans_JSON.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
| <span data-ttu-id="a47d4-111">Esempio del file in arrivo in formato csv</span><span class="sxs-lookup"><span data-stu-id="a47d4-111">Sample of incoming file in .csv format</span></span> | [<span data-ttu-id="a47d4-112">1099entries_JSON.txt</span><span class="sxs-lookup"><span data-stu-id="a47d4-112">1099entries_JSON.txt</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a><span data-ttu-id="a47d4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a47d4-113">Requirements</span></span>

<span data-ttu-id="a47d4-114">Prima di completare la guida attività ER Creare una configurazione di formato per importare dati da un file JSON esterno, è necessario soddisfare il requisito seguente:</span><span class="sxs-lookup"><span data-stu-id="a47d4-114">Before you complete the ER Create a format configuration to import data from an external JSON file task guide, the following requirement must be met:</span></span>

- <span data-ttu-id="a47d4-115">Gli elementi padre nel file JSON possono essere solo elementi di oggetti.</span><span class="sxs-lookup"><span data-stu-id="a47d4-115">Parent elements in the JSON file can be only object elements.</span></span>
- <span data-ttu-id="a47d4-116">Gli elementi nidificati di un oggetto devono essere elementi di proprietà, di modo che venga creata una struttura JSON valida.</span><span class="sxs-lookup"><span data-stu-id="a47d4-116">Nested elements for an object should be property elements, so that a valid JSON structure is created.</span></span>
- <span data-ttu-id="a47d4-117">Le matrici JSON possono essere solo elementi nidificati di elementi di proprietà di un oggetto.</span><span class="sxs-lookup"><span data-stu-id="a47d4-117">JSON arrays can be only nested elements of the property elements of an object.</span></span>
- <span data-ttu-id="a47d4-118">Le matrici JSON possono contenere solo oggetti JSON.</span><span class="sxs-lookup"><span data-stu-id="a47d4-118">JSON arrays can contain only JSON objects.</span></span> <span data-ttu-id="a47d4-119">Non possono contenere valori numerici/stringa diretti e matrici nidificate.</span><span class="sxs-lookup"><span data-stu-id="a47d4-119">They can't contain direct string/numeric values and nested arrays.</span></span> <span data-ttu-id="a47d4-120">Gli elementi in queste matrici saranno analizzati nell'ordine, in quanto sono specificati nel formato.</span><span class="sxs-lookup"><span data-stu-id="a47d4-120">Elements in these arrays will be parsed in order, as they are specified in the format.</span></span> <span data-ttu-id="a47d4-121">Le impostazioni di molteplicità in ogni oggetto JSON verranno prese in considerazione.</span><span class="sxs-lookup"><span data-stu-id="a47d4-121">Multiplicity settings on each JSON object will be considered.</span></span>

<span data-ttu-id="a47d4-122">Inoltre, è necessario completare la guida attività [ER Creare le configurazioni necessarie per importare dati da un file esterno per la creazione di report elettronici](tasks/er-required-configurations-import-data.md) se non lo si è ancora fatto.</span><span class="sxs-lookup"><span data-stu-id="a47d4-122">Additionally, you must complete the [ER Create required configurations to import data from an external file for electronic reporting](tasks/er-required-configurations-import-data.md) task guide if you haven't already completed it.</span></span> <span data-ttu-id="a47d4-123">Scaricare il seguente file per completare la guida attività.</span><span class="sxs-lookup"><span data-stu-id="a47d4-123">Download the following file to complete the task guide.</span></span>

| <span data-ttu-id="a47d4-124">Funzione</span><span class="sxs-lookup"><span data-stu-id="a47d4-124">Title</span></span>                  | <span data-ttu-id="a47d4-125">Nome file</span><span class="sxs-lookup"><span data-stu-id="a47d4-125">File name</span></span> |
|------------------------|-----------|
| <span data-ttu-id="a47d4-126">Configurazione del modello ER</span><span class="sxs-lookup"><span data-stu-id="a47d4-126">ER model configuration</span></span> | [<span data-ttu-id="a47d4-127">1099model.xml</span><span class="sxs-lookup"><span data-stu-id="a47d4-127">1099model.xml</span></span>](https://go.microsoft.com/fwlink/?linkid=874111) |
