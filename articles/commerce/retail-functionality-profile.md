---
title: Creare un profilo funzionalità di vendita al dettaglio
description: In questo argomento viene descritto come creare un profilo funzionalità in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 14da5fd2b409790de2269036ccb941ffa6d3311c
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478310"
---
# <a name="create-a-retail-functionality-profile"></a><span data-ttu-id="aa6c1-103">Creare un profilo funzionalità di vendita al dettaglio</span><span class="sxs-lookup"><span data-stu-id="aa6c1-103">Create a retail functionality profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aa6c1-104">In questo argomento viene descritto come creare un profilo funzionalità in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-104">This topic describes how to create a functionality profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="aa6c1-105">Il profilo funzionalità per commercio fornisce varie impostazioni utilizzate per canali online.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-105">The commerce functionality profile provides various settings used for online channels.</span></span> <span data-ttu-id="aa6c1-106">Ogni canale deve specificare un profilo funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-106">Each channel must specify a functionality profile.</span></span>

## <a name="create-a-functionality-profile"></a><span data-ttu-id="aa6c1-107">Crea un profilo funzionalità</span><span class="sxs-lookup"><span data-stu-id="aa6c1-107">Create a functionality profile</span></span>

<span data-ttu-id="aa6c1-108">Per creare un nuovo profilo funzionalità, completare i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="aa6c1-108">To create a functionality profile, follow these steps.</span></span>

1. <span data-ttu-id="aa6c1-109">Nel pannello di navigazione, andare a **Moduli \> Impostazione canale \> Profili POS \> Profili funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-109">In the navigation pane, go to **Modules \> Channel setup \> POS profiles \> Functionality profiles**.</span></span>
1. <span data-ttu-id="aa6c1-110">Nel Riquadro azioni selezionare **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-110">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="aa6c1-111">Nel campo **Profilo**, immettere un ID per il profilo ("FN006" nell'immagine di esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="aa6c1-111">In the **Profile** field, enter an ID for the profile ("FN006" in the example image below).</span></span>
1. <span data-ttu-id="aa6c1-112">Nel campo **Descrizione**, immettere un valore per il profilo ("Adventure Works Profile" nell'immagine di esempio seguente).</span><span class="sxs-lookup"><span data-stu-id="aa6c1-112">In the **Description** field, enter a value ("Adventure Works Profile" in the example image below).</span></span>
1. <span data-ttu-id="aa6c1-113">Nella sezione **Generale**, selezionare un paese per le impostazioni locali **ISO**.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-113">In the **General** section, select a country for the **ISO** locale.</span></span>
1. <span data-ttu-id="aa6c1-114">Nella sezione **Generale**, modificare altre impostazioni come necessario.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-114">In the **General** section, modify other settings, as needed.</span></span>
1. <span data-ttu-id="aa6c1-115">Nella sezione **Generale**, selezionare a **ID profilo ricevuta** per le ricevute tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-115">In the **General** section, select a **Receipt profile ID** for email receipts.</span></span>
1. <span data-ttu-id="aa6c1-116">Nella sezione **Funzioni**, modificare le impostazioni come necessario.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-116">In the **Functions** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="aa6c1-117">Nella sezione **Importo**, modificare le impostazioni come necessario.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-117">In the **Amount** section, modify settings as, needed.</span></span>
1. <span data-ttu-id="aa6c1-118">Nella sezione **Codici informativi**, modificare le impostazioni come necessario.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-118">In the **Info Codes** section, modify settings, as needed.</span></span>
1. <span data-ttu-id="aa6c1-119">Nella sezione **Numerazione ricevute**, modificare altre impostazioni come necessario.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-119">In the **Receipt numbering** section, modify settings, as needed.</span></span> 
  
<span data-ttu-id="aa6c1-120">L'immagine seguente mostra un esempio di profilo funzionalità.</span><span class="sxs-lookup"><span data-stu-id="aa6c1-120">The following image shows an example functionality profile.</span></span>
  
![Esempio di profilo funzionalità](media/retail-functionality-profile.png)

## <a name="additional-resources"></a><span data-ttu-id="aa6c1-122">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="aa6c1-122">Additional resources</span></span>

[<span data-ttu-id="aa6c1-123">Codici di informazioni e gruppi di codici di informazioni</span><span class="sxs-lookup"><span data-stu-id="aa6c1-123">Info codes and info code groups</span></span>](info-codes-retail.md)           

[<span data-ttu-id="aa6c1-124">Creare una nuova rubrica</span><span class="sxs-lookup"><span data-stu-id="aa6c1-124">Create new address book</span></span>](new-address-book.md) 

[<span data-ttu-id="aa6c1-125">Panoramica del layout schermo</span><span class="sxs-lookup"><span data-stu-id="aa6c1-125">Screen layout overview</span></span>](pos-screen-layouts.md)       

[<span data-ttu-id="aa6c1-126">Configurare e installare Retail hardware station</span><span class="sxs-lookup"><span data-stu-id="aa6c1-126">Configure and install Retail hardware station</span></span>](retail-hardware-station-configuration-installation.md) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
