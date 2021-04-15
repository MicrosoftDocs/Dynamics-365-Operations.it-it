---
title: Aggiungere un codice a matrice o un codice a barre ai messaggi di posta elettronica transazionali e di ricevuta
description: In questo argomento viene descritto come inserire codici a matrice e codici a barre che rappresentano ID ordine nei messaggi di posta elettronica transazionali e di ricevuta in Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/04/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2021-02-16
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: f8d9408090846799c1bb421c4b6e5e248d37fa07
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797505"
---
# <a name="add-a-qr-code-or-bar-code-to-transactional-and-receipt-emails"></a><span data-ttu-id="0c71c-103">Aggiungere un codice a matrice o un codice a barre ai messaggi di posta elettronica transazionali e di ricevuta</span><span class="sxs-lookup"><span data-stu-id="0c71c-103">Add a QR code or bar code to transactional and receipt emails</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="0c71c-104">In questo argomento viene descritto come inserire codici a matrice e codici a barre che rappresentano ID ordine nei messaggi di posta elettronica transazionali e di ricevuta in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c71c-104">This topic explains how to insert QR codes and bar codes that represent order IDs into transactional and receipt emails in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="0c71c-105">È possibile includere facilmente codici a matrice e codici a barre nei messaggi di posta elettronica transazionali per accelerare il processo di ricerca di ordini in un ambiente di vendita al dettaglio.</span><span class="sxs-lookup"><span data-stu-id="0c71c-105">You can easily include QR codes and bar codes in transactional emails to help speed up the order lookup process in a retail environment.</span></span> <span data-ttu-id="0c71c-106">Per inserire codici a matrice e codici a barre nei messaggi di posta elettronica, utilizzare un tag **\<img\>** HTML che richiede un'immagine del codice a matrice o del codice a barre di un servizio di generazione e rendering.</span><span class="sxs-lookup"><span data-stu-id="0c71c-106">To insert QR codes and bar codes into emails, you use an HTML **\<img\>** tag that requests a QR code or bar code image from a generation and rendering service.</span></span> <span data-ttu-id="0c71c-107">Microsoft non fornisce questo servizio.</span><span class="sxs-lookup"><span data-stu-id="0c71c-107">Microsoft doesn't provide this service.</span></span> <span data-ttu-id="0c71c-108">Tuttavia, esistono molti servizi gratuiti o poco costosi che possono fornire codici a matrice o codici a barre generati dinamicamente in base a un valore passato in una stringa di query.</span><span class="sxs-lookup"><span data-stu-id="0c71c-108">However, there are many free or inexpensive services that can serve QR codes or bar codes that are dynamically generated based on a value that is passed in a query string.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-transactional-email"></a><span data-ttu-id="0c71c-109">Aggiungere un codice a matrice o un codice a barre a un messaggio di posta elettronica transazionale</span><span class="sxs-lookup"><span data-stu-id="0c71c-109">Add a QR code or bar code to a transactional email</span></span>

<span data-ttu-id="0c71c-110">Per inserire un codice a matrice o un codice a barre in un messaggio di posta elettronica transazionale inviato come parte di un acquisto e-commerce, seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="0c71c-110">To insert a QR code or bar code into a transactional email that is sent as part of an e-commerce purchase, follow these steps.</span></span>

1. <span data-ttu-id="0c71c-111">Apri l'HTML di origine per il modello di messaggio di posta elettronica transazionale e aggiungere un tag **\<img\>** HTML che punta al servizio di codici a matrice o codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-111">Open the source HTML for the transactional email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="0c71c-112">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="0c71c-112">Here is an example.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%salesid%&param1=value1&param2=value2" alt="%salesid%" />
    ```

    <span data-ttu-id="0c71c-113">Di seguito è riportata una dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="0c71c-113">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="0c71c-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** rappresenta il dominio del servizio di codici a matrice o codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-114">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="0c71c-115">**data** rappresenta il parametro utilizzato dal servizio di codici a matrice o codici a barre per ricevere il contenuto di cui deve essere eseguito il rendering come codice a matrice o codice a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-115">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="0c71c-116">Il valore **%salesid%** deve essere assegnato a questo parametro.</span><span class="sxs-lookup"><span data-stu-id="0c71c-116">The value **%salesid%** must be assigned to this parameter.</span></span> <span data-ttu-id="0c71c-117">In questo esempio, si noti che il valore viene utilizzato anche come testo alternativo dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0c71c-117">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="0c71c-118">**param1** e **param2** rappresentano parametri facoltativi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="0c71c-118">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="0c71c-119">Selezionare **Retail e Commerce \> Impostazione sedi centrali \> Parametri\> Modelli di posta elettronica a livello di organizzazione** e caricare l'HTML aggiornato nel modello di messaggio di posta elettronica transazionale appropriato.</span><span class="sxs-lookup"><span data-stu-id="0c71c-119">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the appropriate transactional email template.</span></span>

> [!NOTE]
> <span data-ttu-id="0c71c-120">I parametri potrebbero differire tra i provider di servizi di codici a matrice e codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-120">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="0c71c-121">Pertanto, assicurarsi di contattare il provider di servizi per confermare i parametri a cui è necessario assegnare i valori.</span><span class="sxs-lookup"><span data-stu-id="0c71c-121">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="add-a-qr-code-or-bar-code-to-a-receipt-email"></a><span data-ttu-id="0c71c-122">Aggiungere un codice a matrice o un codice a barre a un messaggio di posta elettronica di ricevuta</span><span class="sxs-lookup"><span data-stu-id="0c71c-122">Add a QR code or bar code to a receipt email</span></span> 

<span data-ttu-id="0c71c-123">Per inserire un codice a matrice o un codice a barre in un messaggio di posta elettronica di ricevuta che può essere inviato dopo aver effettuato un acquisto presso il punto vendita (POS), seguire questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="0c71c-123">To insert a QR code or bar code into a receipt email that can be sent after a purchase is made at the point of sale (POS), follow these steps.</span></span>

1. <span data-ttu-id="0c71c-124">Aprire l'HTML di origine per il modello di messaggio di posta elettronica di ricevuta e aggiungere un tag **\<img\>** HTML che punta al servizio di codici a matrice o codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-124">Open the source HTML for the receipt email template, and add an HTML **\<img\>** tag that points to your QR code or bar code service.</span></span> <span data-ttu-id="0c71c-125">Di seguito è riportato un esempio.</span><span class="sxs-lookup"><span data-stu-id="0c71c-125">Here is an example below.</span></span>

    ```HTML
    <img src="https://YOUR_QR_CODE_BAR_CODE_SERVICE?data=%receiptid%&param1=value1&param2=value2" alt="%receiptid%" />
    ```

    <span data-ttu-id="0c71c-126">Di seguito è riportata una dell'esempio precedente:</span><span class="sxs-lookup"><span data-stu-id="0c71c-126">Here is an explanation of the preceding example:</span></span>

    - <span data-ttu-id="0c71c-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** rappresenta il dominio del servizio di codici a matrice o codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-127">**YOUR\_QR\_CODE\_BAR\_CODE\_SERVICE** represents the domain of your QR code or bar code service.</span></span>
    - <span data-ttu-id="0c71c-128">**data** rappresenta il parametro utilizzato dal servizio di codici a matrice o codici a barre per ricevere il contenuto di cui deve essere eseguito il rendering come codice a matrice o codice a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-128">**data** represents the parameter that the QR code or bar code service uses to receive the content that should be rendered as a QR code or bar code.</span></span>

        <span data-ttu-id="0c71c-129">Il valore **%receiptid%** deve essere assegnato a questo parametro.</span><span class="sxs-lookup"><span data-stu-id="0c71c-129">The value **%receiptid%** must be assigned to this parameter.</span></span> <span data-ttu-id="0c71c-130">In questo esempio, si noti che il valore viene utilizzato anche come testo alternativo dell'immagine.</span><span class="sxs-lookup"><span data-stu-id="0c71c-130">In this example, notice that the value is also used as alt text for the image.</span></span>

    - <span data-ttu-id="0c71c-131">**param1** e **param2** rappresentano parametri facoltativi aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="0c71c-131">**param1** and **param2** represent additional optional parameters.</span></span>

1. <span data-ttu-id="0c71c-132">Selezionare **Retail e Commerce \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione** e caricare l'HTML aggiornato nel modello di messaggio di posta elettronica il cui ID posta elettronica è **emailrecpt**.</span><span class="sxs-lookup"><span data-stu-id="0c71c-132">Go to **Retail and Commerce \> Headquarters setup \> Parameters \> Organization email templates**, and upload the updated HTML to the email template that has the email ID **emailrecpt**.</span></span>

> [!NOTE]
> <span data-ttu-id="0c71c-133">I parametri potrebbero differire tra i provider di servizi di codici a matrice e codici a barre.</span><span class="sxs-lookup"><span data-stu-id="0c71c-133">Parameters might differ among QR code and bar code service providers.</span></span> <span data-ttu-id="0c71c-134">Pertanto, assicurarsi di contattare il provider di servizi per confermare i parametri a cui è necessario assegnare i valori.</span><span class="sxs-lookup"><span data-stu-id="0c71c-134">Therefore, be sure to contact your service provider to confirm the parameters that you must assign values to.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0c71c-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="0c71c-135">Additional resources</span></span>

[<span data-ttu-id="0c71c-136">Inviare le ricevute tramite posta elettronica da Modern POS (MPOS)</span><span class="sxs-lookup"><span data-stu-id="0c71c-136">Send email receipts from Modern POS (MPOS)</span></span>](email-receipts.md)

[<span data-ttu-id="0c71c-137">Creare modelli e-mail per eventi transazionali</span><span class="sxs-lookup"><span data-stu-id="0c71c-137">Create email templates for transactional events</span></span>](email-templates-transactions.md)
