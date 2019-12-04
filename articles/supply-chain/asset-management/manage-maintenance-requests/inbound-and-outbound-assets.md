---
title: Cespiti in entrata e in uscita
description: Viene descritta la procedura per la registrazione dei cespiti in entrata e in uscita in Gestione cespiti.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 53100a897dc71758b8920672fea1e684817cb4b7
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812285"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="bd104-103">Cespiti in entrata e in uscita</span><span class="sxs-lookup"><span data-stu-id="bd104-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="bd104-104">Se la società effettua i processi di riparazione o i processi di manutenzione sui cespiti ricevuti da altri ubicazioni o clienti, Gestione cespiti può tenere traccia sia dei cespiti in entrata che stanno per arrivare che dei cespiti in uscita che vengono restituiti.</span><span class="sxs-lookup"><span data-stu-id="bd104-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="bd104-105">Se si desidera utilizzare gli stati del ciclo di vita in entrata e in uscita per gestire i cespiti in arrivo e in restituzione, è necessario impostare gli stati del ciclo di vita delle richieste di intervento di manutenzione e i modelli del ciclo di vita per supportare tali azioni.</span><span class="sxs-lookup"><span data-stu-id="bd104-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="bd104-106">Per ulteriori informazioni, vedere [Richieste di intervento di manutenzione](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="bd104-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="bd104-107">L'impostazione di Gestione cespiti determina se è possibile lavorare con i cespiti in entrata e in uscita.</span><span class="sxs-lookup"><span data-stu-id="bd104-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="bd104-108">Registrare cespiti come in entrata</span><span class="sxs-lookup"><span data-stu-id="bd104-108">Register assets as inbound</span></span>

1. <span data-ttu-id="bd104-109">Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="bd104-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="bd104-110">Selezionare la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="bd104-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="bd104-111">Selezionare **Aggiorna stato della richiesta di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="bd104-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="bd104-112">Selezionare **In entrata** (o un altro stato del ciclo di vita creato per i cespiti in entrata), quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd104-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registrare cespiti come in entrata](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="bd104-114">Registrare i cespiti in entrata come ricevuti</span><span class="sxs-lookup"><span data-stu-id="bd104-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="bd104-115">Selezionare **Gestione cespiti** \> **Comune** \> **In entrata/In uscita** \> **Cespiti in entrata**.</span><span class="sxs-lookup"><span data-stu-id="bd104-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="bd104-116">Selezionare il cespite o la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="bd104-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="bd104-117">Selezionare **Ricevi cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bd104-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="bd104-118">Nel campo **Ricevuto** immettere la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="bd104-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="bd104-119">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd104-119">Then select **OK**.</span></span> <span data-ttu-id="bd104-120">Il record verrà rimosso dalla pagina elenco **Cespiti in entrata**.</span><span class="sxs-lookup"><span data-stu-id="bd104-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registrare i cespiti in entrata come ricevuti](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="bd104-122">Registrare cespiti come in uscita</span><span class="sxs-lookup"><span data-stu-id="bd104-122">Register assets as outbound</span></span>

<span data-ttu-id="bd104-123">Dopo aver completato il processo di riparazione o manutenzione, è possibile registrare il cespite come restituito.</span><span class="sxs-lookup"><span data-stu-id="bd104-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="bd104-124">Selezionare **Gestione cespiti** \> **Comune** \> **Richieste di intervento di manutenzione** \> **Richieste di intervento di manutenzione attive**.</span><span class="sxs-lookup"><span data-stu-id="bd104-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="bd104-125">Selezionare la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="bd104-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="bd104-126">Selezionare **Aggiorna stato della richiesta di intervento di manutenzione**.</span><span class="sxs-lookup"><span data-stu-id="bd104-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="bd104-127">Selezionare **In uscita** (o un altro stato del ciclo di vita creato per i cespiti in uscita), quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd104-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="bd104-128">Registrare i cespiti in uscita come consegnati</span><span class="sxs-lookup"><span data-stu-id="bd104-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="bd104-129">Selezionare **Gestione cespiti** \> **Comune** \> **In entrata/In uscita** \> **Cespiti in uscita**.</span><span class="sxs-lookup"><span data-stu-id="bd104-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="bd104-130">Selezionare il cespite o la richiesta di intervento di manutenzione.</span><span class="sxs-lookup"><span data-stu-id="bd104-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="bd104-131">Selezionare **Consegna cespiti**.</span><span class="sxs-lookup"><span data-stu-id="bd104-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="bd104-132">Nel campo **Consegnato** immettere la data e l'ora.</span><span class="sxs-lookup"><span data-stu-id="bd104-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="bd104-133">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="bd104-133">Then select **OK**.</span></span> <span data-ttu-id="bd104-134">Il record verrà rimosso dalla pagina elenco **Cespiti in uscita**.</span><span class="sxs-lookup"><span data-stu-id="bd104-134">The record is removed from the **Outbound assets** list page.</span></span>
