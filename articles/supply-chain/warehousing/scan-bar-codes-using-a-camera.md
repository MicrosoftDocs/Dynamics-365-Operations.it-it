---
title: Eseguire la scansione dei codici a barre utilizzando una fotocamera in Dynamics 365 for Finance and Operations - Magazzino
description: In questo argomento viene descritto come installare Dynamics 365 for Finance and Operations - Magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.
author: MarkusFogelberg
manager: AnnBe
ms.date: 01/03/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7be3e9970e2599c159e7c9d414b54876d0116350
ms.openlocfilehash: f7fe3ab07578b09822fbfeaa4b07331b79f13610
ms.contentlocale: it-it
ms.lasthandoff: 03/09/2018

---

# <a name="scan-bar-codes-using-a-camera-in-dynamics-365-for-finance-and-operations--warehousing"></a><span data-ttu-id="44219-103">Eseguire la scansione dei codici a barre utilizzando una fotocamera in Dynamics 365 for Finance and Operations - Magazzino</span><span class="sxs-lookup"><span data-stu-id="44219-103">Scan bar codes using a camera in Dynamics 365 for Finance and Operations – Warehousing</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="44219-104">In questo argomento viene descritto come installare Dynamics 365 for Finance and Operations - Magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="44219-104">This topic explains how to set up Dynamics 365 for Finance and Operations – Warehousing to scan bar codes using a camera on a mobile device.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="44219-105">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="44219-105">Prerequisites</span></span>
<span data-ttu-id="44219-106">Per utilizzare questa funzione, è necessario disporre della versione 1.2.0.0 di Magazzino e il dispositivo deve disporre di una fotocamera.</span><span class="sxs-lookup"><span data-stu-id="44219-106">To use this feature, you need to have version 1.2.0.0 of Warehousing installed, and your device must have a camera.</span></span> <span data-ttu-id="44219-107">Quando si apre l'app dopo l'aggiornamento, verrà richiesto di consentire all'applicazione Dynamics 365 for Finance e Operations - Magazzino di utilizzare la fotocamera.</span><span class="sxs-lookup"><span data-stu-id="44219-107">When you open the app after updating, you will be prompted to allow the Dynamics 365 for Finance and Operations – Warehousing application to use the camera.</span></span> <span data-ttu-id="44219-108">Se il dispositivo non dispone di una fotocamera, non verrà visualizzato alcun messaggio e non sarà possibile utilizzare una fotocamera come scanner.</span><span class="sxs-lookup"><span data-stu-id="44219-108">If your device doesn’t have a camera, no prompt will be shown, and you will not be able to use a camera as a scanner.</span></span> 

## <a name="setup"></a><span data-ttu-id="44219-109">Imposta</span><span class="sxs-lookup"><span data-stu-id="44219-109">Setup</span></span>
<span data-ttu-id="44219-110">Nelle impostazioni di visualizzazione dell'applicazione Magazzino, è possibile specificare se la fotocamera deve essere utilizzata per la scansione del codice a barre.</span><span class="sxs-lookup"><span data-stu-id="44219-110">In the Display settings of the Warehousing application, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="44219-111">Se si consente l'**utilizzo della fotocamera come scanner**, è possibile utilizzare la fotocamera per ogni campo di input con modalità di input preferito impostata su **Scansione**.</span><span class="sxs-lookup"><span data-stu-id="44219-111">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span> 

<span data-ttu-id="44219-112">Per verificare se un campo di input deve essere sottoposto a scansione, nella pagina **Nomi campo per app magazzino** in Dynamics 365 for Finance and Operations impostare **Modalità di input preferita** su **Scansione**.</span><span class="sxs-lookup"><span data-stu-id="44219-112">To control whether an input field should be scannable, on the **Warehouse app field names** page in Dynamics 365 for Finance and Operations, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="44219-113">Quando questa opzione è selezionata, una fotocamera può essere utilizzata per la scansione nell'app Magazzino.</span><span class="sxs-lookup"><span data-stu-id="44219-113">When this option is selected, a camera can be used for scanning in the Warehousing app.</span></span> <span data-ttu-id="44219-114">Per informazioni su come configurare i nomi dei campi dell'app in Magazzino, vedere [Configurare i nomi di campo app nell'app Magazzino](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span><span class="sxs-lookup"><span data-stu-id="44219-114">For information about how to configure app field names in Warehousing, see [Configure app field names in Warehousing app](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/warehousing/configure-app-field-names-priorities-warehouse).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="44219-115">Formati di codice a barre supportati</span><span class="sxs-lookup"><span data-stu-id="44219-115">Supported bar code formats</span></span>
<span data-ttu-id="44219-116">I formati di codice a barre più comuni sono supportati, inclusi Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A e i codici QR.</span><span class="sxs-lookup"><span data-stu-id="44219-116">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span> 

## <a name="navigation"></a><span data-ttu-id="44219-117">Navigazione</span><span class="sxs-lookup"><span data-stu-id="44219-117">Navigation</span></span>
<span data-ttu-id="44219-118">La pagina della fotocamera verrà avviata in ogni pagina in cui il campo di input ha modalità di input preferita impostata su Scansione. Nella pagina Fotocamera utilizzare le seguenti opzioni per navigare:</span><span class="sxs-lookup"><span data-stu-id="44219-118">The camera page will be initiated on each page where the input field has the preferred input mode set to Scanning, when you are on the Camera page use the following options to navigate:</span></span>
- <span data-ttu-id="44219-119">Fare clic sul pulsante Indietro per tornare alla pagina dei dettagli e delle attività.</span><span class="sxs-lookup"><span data-stu-id="44219-119">Click the back button to go back to the Task and details page.</span></span> 
- <span data-ttu-id="44219-120">Fare clic sulla matita alla pagina dei dettagli di attività e passare alla finestra in cui è possibile immettere manualmente l'input.</span><span class="sxs-lookup"><span data-stu-id="44219-120">Click the pencil on the Task and details page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="44219-121">Fare clic sulla fotocamera alla pagina dei dettagli e delle attività per tornare alla pagina della fotocamera.</span><span class="sxs-lookup"><span data-stu-id="44219-121">Click the camera on the Task and details page to go back to the Camera page.</span></span> 

| <span data-ttu-id="44219-122">Pagina dei dettagli e delle attività</span><span class="sxs-lookup"><span data-stu-id="44219-122">Task and details page</span></span> | <span data-ttu-id="44219-123">Pagina della fotocamera</span><span class="sxs-lookup"><span data-stu-id="44219-123">Camera page</span></span> | 
| :---------------------: | :--------------------: |
| ![pagina dettagli attività di esempio scansione fotocamera](./media/camera-scanning-example-task-detail-page50.png)          | ![pagina fotocamera di esempio scansione fotocamera minori dimensioni](./media/camera-scanning-example-camera-page50.png)          |

<span data-ttu-id="44219-126">Nella pagina della fotocamera, facendo clic sul pulsante Fotocamera, questo appare inattivo durante il tentativo di identificare un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="44219-126">On the camera page, when you click the Camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="44219-127">Se un codice a barre non viene identificato entro 5 secondi, il processo si interrompe e il pulsante Fotocamera diventa nuovamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="44219-127">If a bar code is not identified within 5 seconds, the process will time out and the Camera button will become available again.</span></span> <span data-ttu-id="44219-128">Sarà quindi possibile provare ad eseguire di nuovo la scansione di un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="44219-128">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="44219-129">Quando si punta la fotocamera su un codice a barre, mantenere il codice a barre allineato alle parentesi per ottenere il miglior risultato.</span><span class="sxs-lookup"><span data-stu-id="44219-129">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="44219-130">Se la scansione di un codice a barre viene effettuata correttamente, il risultato verrà elaborato e si verrà indirizzati al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="44219-130">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="44219-131">Se il passaggio successivo contiene un altro campo di input con la modalità di input preferita impostata su Scansione, la pagina della fotocamera verrà riavviata.</span><span class="sxs-lookup"><span data-stu-id="44219-131">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="44219-132">Se il passaggio successivo non contiene un campo di scansione, la pagina della fotocamera non verrà avviata.</span><span class="sxs-lookup"><span data-stu-id="44219-132">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>


