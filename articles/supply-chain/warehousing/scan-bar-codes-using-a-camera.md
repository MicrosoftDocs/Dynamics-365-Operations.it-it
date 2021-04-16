---
title: Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app per dispositivi mobili Gestione magazzino
description: In questo argomento viene descritto come installare l'app per dispositivi mobili Gestione magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.
author: MarkusFogelberg
ms.date: 01/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSMobileAppField
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2017-01-03
ms.dyn365.ops.version: AX 8.0.0
ms.openlocfilehash: 2f61f9c45b95b730a7f1743963658ec00abfbb56
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831220"
---
# <a name="scan-bar-codes-using-a-camera-in-the-warehouse-management-mobile-app"></a><span data-ttu-id="0b41a-103">Eseguire la scansione dei codici a barre utilizzando una fotocamera nell'app per dispositivi mobili Gestione magazzino</span><span class="sxs-lookup"><span data-stu-id="0b41a-103">Scan bar codes using a camera in the Warehouse Management mobile app</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b41a-104">In questo argomento viene descritto come installare l'app per dispositivi mobili Gestione magazzino per eseguire la scansione dei codici a barre utilizzando una fotocamera su un dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="0b41a-104">This topic explains how to set up the Warehouse Management mobile app to scan bar codes using a camera on a mobile device.</span></span>

## <a name="setup"></a><span data-ttu-id="0b41a-105">Attrezzaggio</span><span class="sxs-lookup"><span data-stu-id="0b41a-105">Setup</span></span>

<span data-ttu-id="0b41a-106">Nelle impostazioni di visualizzazione dell'app per dispositivi mobili Gestione magazzino, è possibile specificare se la fotocamera deve essere utilizzata per la scansione del codice a barre.</span><span class="sxs-lookup"><span data-stu-id="0b41a-106">In the display settings of the Warehouse Management mobile app, you can select if the camera should be used for bar code scanning.</span></span> <span data-ttu-id="0b41a-107">Se si consente l'**utilizzo della fotocamera come scanner**, è possibile utilizzare la fotocamera per ogni campo di input con modalità di input preferito impostata su **Scansione**.</span><span class="sxs-lookup"><span data-stu-id="0b41a-107">If you enable **Use the camera as scanner**, you can use the camera on every input field that has the preferred input mode set to **Scanning**.</span></span>

<span data-ttu-id="0b41a-108">Per verificare se un campo di input deve essere sottoposto a scansione, nella pagina **Nomi campo per app magazzino** impostare **Modalità di input preferita** su **Scansione**.</span><span class="sxs-lookup"><span data-stu-id="0b41a-108">To control whether an input field should be scannable, on the **Warehouse app field names** page, set **Preferred input mode** to **Scanning**.</span></span> <span data-ttu-id="0b41a-109">Quando questa opzione è selezionata, una fotocamera può essere utilizzata per la scansione nell'app per dispositivi mobili Gestione magazzino.</span><span class="sxs-lookup"><span data-stu-id="0b41a-109">When this option is selected, a camera can be used for scanning in the Warehouse Management mobile app.</span></span> <span data-ttu-id="0b41a-110">Per ulteriori informazioni, vedi [Configurare i campi per l'app per dispositivi mobili Gestione magazzino](configure-app-field-names-priorities-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="0b41a-110">For more information, see [Configure fields for the Warehouse Management mobile app](configure-app-field-names-priorities-warehouse.md).</span></span>

## <a name="supported-bar-code-formats"></a><span data-ttu-id="0b41a-111">Formati di codice a barre supportati</span><span class="sxs-lookup"><span data-stu-id="0b41a-111">Supported bar code formats</span></span>

<span data-ttu-id="0b41a-112">I formati di codice a barre più comuni sono supportati, inclusi Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A e i codici QR.</span><span class="sxs-lookup"><span data-stu-id="0b41a-112">The most common bar code formats are supported, including Code 128, Code 39, Code 93, EAN-8, EAN-13, UPC-E, UPC-A, and QR codes.</span></span>

## <a name="navigation"></a><span data-ttu-id="0b41a-113">Navigazione</span><span class="sxs-lookup"><span data-stu-id="0b41a-113">Navigation</span></span>

<span data-ttu-id="0b41a-114">La pagina della fotocamera verrà avviata in ogni pagina in cui il campo di input ha **modalità di input preferita** impostata su *Scansione*. Nella pagina della fotocamera utilizza le seguenti opzioni per navigare:</span><span class="sxs-lookup"><span data-stu-id="0b41a-114">The camera page will be initiated on each page where the input field has its **Preferred input mode** set to *Scanning*, when you are on the camera page use the following options to navigate:</span></span>

- <span data-ttu-id="0b41a-115">Seleziona il pulsante Indietro per tornare alla pagina **dei dettagli e delle attività**.</span><span class="sxs-lookup"><span data-stu-id="0b41a-115">Select the back button to go back to the **Task and details** page.</span></span>
- <span data-ttu-id="0b41a-116">Seleziona la matita nella pagina **dei dettagli delle attività** e passa alla finestra in cui è possibile immettere manualmente l'input.</span><span class="sxs-lookup"><span data-stu-id="0b41a-116">Select the pencil on the **Task and details** page to go to the page where you can type input manually.</span></span>
- <span data-ttu-id="0b41a-117">Seleziona la fotocamera nella pagina **dei dettagli e delle attività** per tornare alla pagina della fotocamera.</span><span class="sxs-lookup"><span data-stu-id="0b41a-117">Select the camera on the **Task and details** page to go back to the camera page.</span></span>

<span data-ttu-id="0b41a-118">Nella pagina della fotocamera, quando selezioni il pulsante Fotocamera, questo appare inattivo durante il tentativo di identificare un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="0b41a-118">On the camera page, when you select the camera button, it will appear dimmed while trying to identify a bar code.</span></span> <span data-ttu-id="0b41a-119">Se un codice a barre non viene identificato entro 5 secondi, il processo si interrompe e il pulsante Fotocamera diventa nuovamente disponibile.</span><span class="sxs-lookup"><span data-stu-id="0b41a-119">If a bar code is not identified within 5 seconds, the process will time out and the camera button will become available again.</span></span> <span data-ttu-id="0b41a-120">Sarà quindi possibile provare ad eseguire di nuovo la scansione di un codice a barre.</span><span class="sxs-lookup"><span data-stu-id="0b41a-120">You will then be able to try to scan a bar code again.</span></span>

<span data-ttu-id="0b41a-121">Quando si punta la fotocamera su un codice a barre, mantenere il codice a barre allineato alle parentesi per ottenere il miglior risultato.</span><span class="sxs-lookup"><span data-stu-id="0b41a-121">When you aim the camera at a bar code, keep the bar code aligned within the brackets for best result.</span></span> <span data-ttu-id="0b41a-122">Se la scansione di un codice a barre viene effettuata correttamente, il risultato verrà elaborato e si verrà indirizzati al passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="0b41a-122">When a bar code is scanned successfully, the result will be processed, and you will be taken to the next step.</span></span> <span data-ttu-id="0b41a-123">Se il passaggio successivo contiene un altro campo di input con la modalità di input preferita impostata su Scansione, la pagina della fotocamera verrà riavviata.</span><span class="sxs-lookup"><span data-stu-id="0b41a-123">If the next step contains another input field with the preferred input mode set to Scanning, the camera page will start again.</span></span> <span data-ttu-id="0b41a-124">Se il passaggio successivo non contiene un campo di scansione, la pagina della fotocamera non verrà avviata.</span><span class="sxs-lookup"><span data-stu-id="0b41a-124">If the next step is not a scanning field, then the camera page will not be initiated.</span></span>



[!INCLUDE[footer-include](../../includes/footer-banner.md)]