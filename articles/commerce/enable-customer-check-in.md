---
title: Abilitare le notifiche di check-in dei clienti nel POS
description: Questo argomento descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: b42dc7766f8a69a7409c28d21b49cc96eca18dd4
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271427"
---
# <a name="enable-customer-check-in-notifications-in-point-of-sale-pos"></a><span data-ttu-id="d7089-103">Abilitare le notifiche di check-in dei clienti nel POS</span><span class="sxs-lookup"><span data-stu-id="d7089-103">Enable customer check-in notifications in point of sale (POS)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d7089-104">Questo argomento descrive come abilitare le notifiche di check-in del cliente nel POS di Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d7089-104">This topic describes how to enable customer check-in notifications in Microsoft Dynamics 365 Commerce point of sale (POS).</span></span>

<span data-ttu-id="d7089-105">Nelle loro e-mail di ordine pronto per il ritiro, le organizzazioni possono fornire un collegamento o un pulsante che consente ai clienti di notificare al punto vendita che si trovano sul posto e che aspettano che il loro pacco venga loro consegnato.</span><span class="sxs-lookup"><span data-stu-id="d7089-105">In their "order ready for pickup" emails, organizations can provide a link or button that lets customers notify the store that they are on the premises and waiting for their package to be brought out to them.</span></span> <span data-ttu-id="d7089-106">I clienti ricevono quindi una conferma del check-in e il punto vendita riceve una notifica come attività nella sua applicazione POS.</span><span class="sxs-lookup"><span data-stu-id="d7089-106">Customers then receive a check-in confirmation, and the store receives a notification as a task in its POS application.</span></span> <span data-ttu-id="d7089-107">Questa attività serve come richiesta per un addetto alle vendite di consegnare l'ordine al veicolo del cliente.</span><span class="sxs-lookup"><span data-stu-id="d7089-107">This task serves as a prompt for a sales associate to deliver the order to the customer's vehicle.</span></span> <span data-ttu-id="d7089-108">Pertanto, il cliente non deve entrare nel punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d7089-108">Therefore, the customer doesn't have to enter the store.</span></span>

<span data-ttu-id="d7089-109">Il flusso di lavoro del check-in del cliente può anche essere configurato per raccogliere informazioni aggiuntive dai clienti, come il numero del parcheggio, la marca, il modello e il colore del veicolo e le istruzioni di consegna.</span><span class="sxs-lookup"><span data-stu-id="d7089-109">The customer check-in workflow can also be configured to collect additional information from customers, such as their parking spot number, the make, model, and color of their vehicle, and delivery instructions.</span></span> <span data-ttu-id="d7089-110">L'addetto del punto vendita al dettaglio può utilizzare queste informazioni per facilitare l'evasione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="d7089-110">The retail store attendant can use this information to facilitate order fulfillment.</span></span>

## <a name="enable-customer-check-in"></a><span data-ttu-id="d7089-111">Abilitare il check-in del cliente</span><span class="sxs-lookup"><span data-stu-id="d7089-111">Enable customer check-in</span></span>

<span data-ttu-id="d7089-112">Quando la funzionalità di check-in del cliente è attivata, Commerce genera un ID di conferma dell'ordine (noto anche come ID di riferimento canale).</span><span class="sxs-lookup"><span data-stu-id="d7089-112">When the customer check-in feature is turned on, Commerce generates an order confirmation ID (also known as the channel reference ID).</span></span> <span data-ttu-id="d7089-113">Genera inoltre ID di conferma dell'ordine per gli ordini creati tramite i canali POS o call center.</span><span class="sxs-lookup"><span data-stu-id="d7089-113">It also generates order confirmation IDs for orders that are created through point of sale (POS) or call center channels.</span></span> 

<span data-ttu-id="d7089-114">Per attivare la funzionalità di check-in del cliente in Commerce Headquarters, segui questa procedura.</span><span class="sxs-lookup"><span data-stu-id="d7089-114">To turn on the customer check-in feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="d7089-115">Vai a **Aree di lavoro \> Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="d7089-115">Go to **Workspaces \> Feature management**.</span></span>
2. <span data-ttu-id="d7089-116">Cerca la funzionalità **Genera un formato ID di riferimento canale coerente per tutti i canali**.</span><span class="sxs-lookup"><span data-stu-id="d7089-116">Search for the **Generate a consistent channel reference ID format across channels** feature.</span></span> 
3. <span data-ttu-id="d7089-117">Selezionare la funzionalità, quindi nel riquadro delle proprietà selezionare **Abilita ora**.</span><span class="sxs-lookup"><span data-stu-id="d7089-117">Select the feature, and then select **Enable now** in the properties pane.</span></span> 

## <a name="create-a-check-in-confirmation-page"></a><span data-ttu-id="d7089-118">Creare una pagina di conferma del check-in</span><span class="sxs-lookup"><span data-stu-id="d7089-118">Create a check-in confirmation page</span></span>

<span data-ttu-id="d7089-119">Sul tuo sito di e-commerce, devi creare una nuova pagina che fungerà da esperienza di conferma del check-in.</span><span class="sxs-lookup"><span data-stu-id="d7089-119">On your e-commerce site, you must create a new page that will serve as the check-in confirmation experience.</span></span> <span data-ttu-id="d7089-120">Attraverso una configurazione aggiuntiva, la pagina può anche includere un modulo che raccoglie informazioni aggiuntive dai clienti per facilitare l'evasione degli ordini.</span><span class="sxs-lookup"><span data-stu-id="d7089-120">Through additional configuration, the page can also include a form that collects additional information from customers to facilitate order fulfillment.</span></span> <span data-ttu-id="d7089-121">Per informazioni su come impostare la pagina e il modulo, vedere [Modulo check-in del cliente](check-in-pickup-module.md).</span><span class="sxs-lookup"><span data-stu-id="d7089-121">For information about how to set up the page and module, see [Customer check-in module](check-in-pickup-module.md).</span></span>

## <a name="configure-the-transactional-email-template"></a><span data-ttu-id="d7089-122">Configurare il modello di messaggio di posta elettronica transazionale</span><span class="sxs-lookup"><span data-stu-id="d7089-122">Configure the transactional email template</span></span>

<span data-ttu-id="d7089-123">Devi aggiungere un collegamento o pulsante **Sono qui** al modello per il messaggio di posta elettronica transazionale che i clienti ricevono quando il loro ordine è pronto per il ritiro.</span><span class="sxs-lookup"><span data-stu-id="d7089-123">You must add an **I am here** link or button to the template for the transactional email that customers receive when their order is ready for pickup.</span></span> <span data-ttu-id="d7089-124">I clienti utilizzeranno questo collegamento o pulsante per notificare al punto vendita che sono arrivati per ritirare l'ordine.</span><span class="sxs-lookup"><span data-stu-id="d7089-124">Customers will use this link or button to notify the store that they have arrived to pick up their order.</span></span> 

<span data-ttu-id="d7089-125">Aggiungere il collegamento o il pulsante al modello mappato al tipo di notifica **Imballaggio completato** e la modalità di consegna che utilizzi per l'evasione degli ordini all'esterno del punto vendita.</span><span class="sxs-lookup"><span data-stu-id="d7089-125">Add the link or button to the template that is mapped to the **Packing completed** notification type and the mode of delivery that you're using for curbside order fulfillment.</span></span> <span data-ttu-id="d7089-126">Nel modello, crea un collegamento HTML o un pulsante che punti all'URL della pagina di conferma del check-in che hai creato.</span><span class="sxs-lookup"><span data-stu-id="d7089-126">In the template, create an HTML link or button that points to the URL of the check-in confirmation page that you created.</span></span> <span data-ttu-id="d7089-127">Ecco un esempio.</span><span class="sxs-lookup"><span data-stu-id="d7089-127">Here is an example.</span></span>

```
<a href="https://[YOUR_SITE_DOMAIN]/[CHECK-IN_CONFIRMATION_PAGE]?channelReferenceId=%channelreferenceid%&channelId=%channelid%&packingSlipId=%packingslipid%" target="_blank">I am here!</a>
```
<span data-ttu-id="d7089-128">Per ulteriori informazioni su come configurare i modelli di posta elettronica, vedere [Personalizzare i messaggi di posta elettronica transazionali in base alla modalità di consegna](customize-email-delivery-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d7089-128">For more information about how to configure email templates, see [Customize transactional emails by mode of delivery](customize-email-delivery-mode.md).</span></span> 

## <a name="a-check-in-confirmation-task-is-created-in-pos"></a><span data-ttu-id="d7089-129">Un'attività di conferma del check-in viene creata in POS</span><span class="sxs-lookup"><span data-stu-id="d7089-129">A check-in confirmation task is created in POS</span></span>

<span data-ttu-id="d7089-130">Dopo che un cliente ha notificato al punto vendita che è presente per il ritiro, riceve una notifica di conferma del check-in e viene creata un'attività nell'elenco delle attività nel POS per il punto vendita in cui il cliente sta ritirando l'ordine.</span><span class="sxs-lookup"><span data-stu-id="d7089-130">After a customer notifies the store that they are present for pickup, they receive a check-in confirmation notification, and a task is created in the tasks list in POS for the store where the customer is picking up the order.</span></span> <span data-ttu-id="d7089-131">L'attività contiene tutte le informazioni sul cliente e sull'ordine necessarie per evadere l'ordine.</span><span class="sxs-lookup"><span data-stu-id="d7089-131">The task contains all the customer and order information that is required to fulfill the order.</span></span> <span data-ttu-id="d7089-132">Nell'attività, il campo delle istruzioni mostra tutte le informazioni raccolte dal cliente tramite il modulo delle informazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="d7089-132">In the task, the instructions field shows any information that was collected from the customer through the additional information form.</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="d7089-133">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d7089-133">Additional resources</span></span>

[<span data-ttu-id="d7089-134">Modulo di check-in per il ritiro</span><span class="sxs-lookup"><span data-stu-id="d7089-134">Check-in for pickup module</span></span>](check-in-pickup-module.md)
