---
title: Creare un profilo funzionalità online
description: In questo argomento viene descritto come creare un profilo funzionalità online in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: be78b92858979b8bb009a4699eff96379ef7cef3
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791104"
---
# <a name="create-an-online-functionality-profile"></a><span data-ttu-id="b51f9-103">Creare un profilo funzionalità online</span><span class="sxs-lookup"><span data-stu-id="b51f9-103">Create an online functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b51f9-104">In questo argomento viene presentata una panoramica sulla configurazione di un profilo funzionalità online per Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b51f9-104">This topic presents an overview of setting up an online functionality profile for Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b51f9-105">Il profilo funzionalità online fornisce varie impostazioni utilizzate per canali online.</span><span class="sxs-lookup"><span data-stu-id="b51f9-105">The online functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="b51f9-106">Ogni canale online deve specificare un profilo funzionalità online.</span><span class="sxs-lookup"><span data-stu-id="b51f9-106">Each online channel must specify an online functionality profile.</span></span>

## <a name="create-an-online-functionality-profile"></a><span data-ttu-id="b51f9-107">Creare un profilo funzionalità online</span><span class="sxs-lookup"><span data-stu-id="b51f9-107">Create an online functionality profile</span></span>

<span data-ttu-id="b51f9-108">La seguente procedura spiega come creare un profilo funzionalità online nell'app Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="b51f9-108">The following procedure explains how to create an online functionality profile from within Commerce Headquarters app.</span></span>

1. <span data-ttu-id="b51f9-109">Nel pannello di navigazione, andare a **Moduli \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="b51f9-109">In the navigation pane, go to **Modules \> Channel setup \> Online store setup \> Functionality profiles**.</span></span>
1. <span data-ttu-id="b51f9-110">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="b51f9-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="b51f9-111">Nel campo **Profilo**, immettere un ID per il profilo.</span><span class="sxs-lookup"><span data-stu-id="b51f9-111">In the **Profile** field, enter an ID for the profile.</span></span>
1. <span data-ttu-id="b51f9-112">Nel campo **Descrizione**, immettere un valore per il profilo ("Adventure Works Profile" nell'immagine di esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="b51f9-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="b51f9-113">Nella sezione **Funzioni**, modificare le impostazioni **CARRELLO**, **CLIENTI DI VENDITA AL DETTAGLIO** o **CHECKOUT** come necessario.</span><span class="sxs-lookup"><span data-stu-id="b51f9-113">In the **Functions** section, modify the **CART**, **RETAIL CUSTOMERS**, or **CHECKOUT** settings, as needed.</span></span>
1. <span data-ttu-id="b51f9-114">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b51f9-114">On the action pane, select **Save**.</span></span>

<span data-ttu-id="b51f9-115">L'immagine seguente mostra un esempio di profilo funzionalità online.</span><span class="sxs-lookup"><span data-stu-id="b51f9-115">The following image shows an example online functionality profile.</span></span>
  
![Esempio di profilo funzionalità online](media/online-functionality-profile.png)

## <a name="functions"></a><span data-ttu-id="b51f9-117">Funzioni</span><span class="sxs-lookup"><span data-stu-id="b51f9-117">Functions</span></span>

- <span data-ttu-id="b51f9-118">**Aggrega prodotti**: se abilitata, questa funzione consente al carrello di aggiornare la quantità quando lo stesso articolo viene aggiunto più volte.</span><span class="sxs-lookup"><span data-stu-id="b51f9-118">**Aggregate products**: When enabled, this function allows the cart to update quantity when the same item is added multiple times.</span></span>
- <span data-ttu-id="b51f9-119">**Consenti checkout senza pagamenti**: se abilitata, questa funzione gestisce lo scenario in cui gli articoli aggiunti al carrello hanno un prezzo $0,00.</span><span class="sxs-lookup"><span data-stu-id="b51f9-119">**Allow checkout with no payments**: When enabled, this function handles the scenario when items added to cart have a price $0.00.</span></span>
- <span data-ttu-id="b51f9-120">**Crea cliente in modalità asincrona**: questa è un'impostazione legacy applicabile a canali di e-commerce di terze parti e non è applicabile al sito di e-commerce di Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b51f9-120">**Create customer in async mode**: This is a legacy setting applicable to third-party e-Commerce channels and is not applicable to the Dynamics 365 e-Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b51f9-121">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b51f9-121">Additional resources</span></span>

[<span data-ttu-id="b51f9-122">Panoramica dei canali</span><span class="sxs-lookup"><span data-stu-id="b51f9-122">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="b51f9-123">Prerequisiti di impostazione dei canali</span><span class="sxs-lookup"><span data-stu-id="b51f9-123">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="b51f9-124">Impostare un canale online</span><span class="sxs-lookup"><span data-stu-id="b51f9-124">Set up an online channel</span></span>](channel-setup-online.md)

[<span data-ttu-id="b51f9-125">Impostare un canale di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="b51f9-125">Set up a retail channel</span></span>](channel-setup-retail.md)

[<span data-ttu-id="b51f9-126">Impostare un canale servizio clienti</span><span class="sxs-lookup"><span data-stu-id="b51f9-126">Set up a call center channel</span></span>](channel-setup-callcenter.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
