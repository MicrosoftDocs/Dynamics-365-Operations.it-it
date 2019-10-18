---
title: Informazioni generali sui pagamenti sicuri
description: Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 88463
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 49fe8369fce599d16134541b1c968727f38ebff9
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2189639"
---
# <a name="positive-pay-overview"></a><span data-ttu-id="97424-103">Informazioni generali sui pagamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="97424-103">Positive pay overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="97424-104">Questo articolo fornisce informazioni sui pagamenti sicuri, che vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca.</span><span class="sxs-lookup"><span data-stu-id="97424-104">This article provides information about positive pay, which is used to generate an electronic list of checks that can be presented to a bank.</span></span> 

<span data-ttu-id="97424-105">I pagamenti sicuri vengono utilizzati per generare un elenco elettronico di assegni da presentare a una banca.</span><span class="sxs-lookup"><span data-stu-id="97424-105">Positive pay is used to generate an electronic list of checks that can be presented to a bank.</span></span> <span data-ttu-id="97424-106">I file pagamenti sicuri possono agevolare le banche a impedire le frodi di assegni.</span><span class="sxs-lookup"><span data-stu-id="97424-106">Positive pay files can help banks prevent check fraud.</span></span> <span data-ttu-id="97424-107">È possibile impostare un pagamento sicuro per generare un elenco elettronico di assegni ogni volta che vengono stampati.</span><span class="sxs-lookup"><span data-stu-id="97424-107">You set up positive pay to generate an electronic list of checks every time that checks are printed.</span></span> <span data-ttu-id="97424-108">Quando un assegno viene presentato alla banca, la banca lo confronta con l'elenco degli assegni inviati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="97424-108">Then, when a check is presented to the bank, the bank compares the check with the list of checks that you previously submitted.</span></span> <span data-ttu-id="97424-109">Se l'assegno corrisponde a uno presente nell'elenco, la banca lo liquida.</span><span class="sxs-lookup"><span data-stu-id="97424-109">If the check matches a check in the list, the bank clears it.</span></span> <span data-ttu-id="97424-110">Se l'assegno non corrisponde a un assegno nell'elenco, la banca lo trattiene per esaminarlo.</span><span class="sxs-lookup"><span data-stu-id="97424-110">If the check doesn't match a check in the list, the bank holds it for review.</span></span>

<span data-ttu-id="97424-111">La retribuzione positiva anche è conosciuta come SafePay.</span><span class="sxs-lookup"><span data-stu-id="97424-111">Positive pay is also known as SafePay.</span></span> 

<span data-ttu-id="97424-112">I file pagamenti sicuri possono contenere dati riservati sui beneficiari e sugli importi dell'assegno.</span><span class="sxs-lookup"><span data-stu-id="97424-112">Positive pay files can contain sensitive information about payees and check amounts.</span></span> <span data-ttu-id="97424-113">Di conseguenza, assicurarsi di utilizzare le misure di sicurezza appropriate dalla generazione dei file fino alla loro ricezione da parte della banca.</span><span class="sxs-lookup"><span data-stu-id="97424-113">Therefore, make sure that you use appropriate security measures from the time that the files are generated until they are received by the bank.</span></span> <span data-ttu-id="97424-114">I file pagamenti sicuri vengono scaricati in base alle istruzioni di download per il Web browser.</span><span class="sxs-lookup"><span data-stu-id="97424-114">Positive pay files are downloaded according to the download instructions for the web browser.</span></span> 

<span data-ttu-id="97424-115">Questi file vengono creati tramite entità di dati.</span><span class="sxs-lookup"><span data-stu-id="97424-115">Positive pay files are created by using data entities.</span></span> <span data-ttu-id="97424-116">Prima di generare un file pagamenti sicuri, è necessario impostare i formati di trasformazione per l'XML che converte i dati in un formato interpretabile dalla banca.</span><span class="sxs-lookup"><span data-stu-id="97424-116">Before you generate a positive pay file, you must set up the transformation formats for the XML that translates the data into a format that the bank can consume.</span></span> 

<span data-ttu-id="97424-117">Per ogni conto bancario per il quale generare informazioni pagamenti sicuri, è necessario assegnare il formato pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="97424-117">For each bank account that you want to generate positive pay information for, you must assign the positive pay format.</span></span> <span data-ttu-id="97424-118">Dopo aver generato pagamenti, è possibile generare un file pagamenti sicuri per una singola persona giuridica e un singolo conto bancario.</span><span class="sxs-lookup"><span data-stu-id="97424-118">After you generate payments, you can generate a positive pay file for a single legal entity and a single bank account.</span></span> <span data-ttu-id="97424-119">In alternativa, è possibile generare file pagamenti sicuri per più persone giuridiche e più conti bancari contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="97424-119">Alternatively, you can generate positive pay files for multiple legal entities and bank accounts at the same time.</span></span> 

<span data-ttu-id="97424-120">Dopo aver pagato gli assegni elencati in un file pagamenti sicuri, viene visualizzato un numero di conferma dalla banca.</span><span class="sxs-lookup"><span data-stu-id="97424-120">After the checks that are listed in a positive pay file have been paid, you receive a confirmation number from your bank.</span></span> <span data-ttu-id="97424-121">Sarà quindi possibile confermare il file pagamenti sicuri nel sistema.</span><span class="sxs-lookup"><span data-stu-id="97424-121">You can then confirm the positive pay file in the system.</span></span> 

<span data-ttu-id="97424-122">Per modificare un file pagamenti sicuri, è possibile richiamarlo.</span><span class="sxs-lookup"><span data-stu-id="97424-122">If you must change a positive pay file, you can recall it.</span></span> <span data-ttu-id="97424-123">Per ogni assegno nel file pagamenti sicuri, viene reimpostato il campo che indica se l'assegno è stato incluso in un file pagamenti sicuri.</span><span class="sxs-lookup"><span data-stu-id="97424-123">Then, for each check in the positive pay file, the field that indicates whether that check has been included in a positive pay file is reset.</span></span>

<span data-ttu-id="97424-124">Per ulteriori informazioni, vedere [Impostare e generare file di pagamenti sicuri](set-up-generate-positive-pay-files.md).</span><span class="sxs-lookup"><span data-stu-id="97424-124">For more information, see [Set up and generate positive pay files](set-up-generate-positive-pay-files.md).</span></span>



