---
title: Configurare un canale per utilizzare una gerarchia di navigazione nei canali
description: In questo argomento viene descritto come configurare un canale per utilizzare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: ceb6aa65c2ed5bc8d4224bdaf7095fba769181e8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5220584"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="3c82f-103">Configurare un canale per utilizzare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="3c82f-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="3c82f-104">In questo argomento viene descritto come configurare un canale per utilizzare una gerarchia di navigazione nei canali in Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="3c82f-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="3c82f-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="3c82f-105">Overview</span></span>

<span data-ttu-id="3c82f-106">Le gerarchie di navigazione nei canali organizzano i prodotti in categorie di modo che i prodotti possano essere esaminati in un sito di e-commerce o nel POS.</span><span class="sxs-lookup"><span data-stu-id="3c82f-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="3c82f-107">I canali di vendita al dettaglio e online devono essere configurati con gerarchie di navigazione nei canali.</span><span class="sxs-lookup"><span data-stu-id="3c82f-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="3c82f-108">Configurare il canale</span><span class="sxs-lookup"><span data-stu-id="3c82f-108">Configure the channel</span></span>

<span data-ttu-id="3c82f-109">Per configurare un canale allo scopo di utilizzare una gerarchia di navigazione nei canali, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="3c82f-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="3c82f-110">Nel pannello di navigazione andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione canale \> Categorie canale e attributi del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="3c82f-111">Selezionare il canale da configurare.</span><span class="sxs-lookup"><span data-stu-id="3c82f-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="3c82f-112">Nel riquadro azioni, selezionare **Imposta metadati di attributi**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="3c82f-113">Nell'elenco a discesa **Gerarchia di categorie**, selezionare la gerarchia di navigazione nei canali appropriata.</span><span class="sxs-lookup"><span data-stu-id="3c82f-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="3c82f-114">Nel riquadro azioni selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="3c82f-115">Sotto **Gruppo di attributi**, aggiungere tutti i gruppi di attributi che saranno attributi globali per tutti i nodi.</span><span class="sxs-lookup"><span data-stu-id="3c82f-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="3c82f-116">L'immagine seguente mostra come configurare un canale allo scopo di utilizzare una gerarchia di navigazione nei canali.</span><span class="sxs-lookup"><span data-stu-id="3c82f-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Esempio di configurazione di un canale](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="3c82f-118">Imposta metadati di attributi</span><span class="sxs-lookup"><span data-stu-id="3c82f-118">Set attribute metadata</span></span>

<span data-ttu-id="3c82f-119">L'impostazione dei metadati di attributi consentirà la configurazione degli attributi in ogni nodo.</span><span class="sxs-lookup"><span data-stu-id="3c82f-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="3c82f-120">Per impostare i metadati di attributi, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="3c82f-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="3c82f-121">Nel riquadro azioni, selezionare **Imposta metadati di attributi**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="3c82f-122">Per ciascun nodo selezionare **Attributi del prodotto del canale**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="3c82f-123">Impostare **Mostra attributo sul canale** su **Sì** e **Ridefinizione possibile** su **Sì**, per abilitare raffinatori su quel canale.</span><span class="sxs-lookup"><span data-stu-id="3c82f-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="3c82f-124">Dopo aver configurato ciascun nodo come desiderato, nel **Riquadro azioni**, selezionare il pulsante **Salva** per salvare.</span><span class="sxs-lookup"><span data-stu-id="3c82f-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="3c82f-125">Selezionare la **X** nell'angolo in alto a destra per uscire da questa schermata e ritornare alla pagina **Categorie canale e attributi del prodotto**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="3c82f-126">L'immagine seguente mostra un set di esempi di attributi del prodotto del canale configurati in un nodo di categoria del canale.</span><span class="sxs-lookup"><span data-stu-id="3c82f-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Attributi del canale in un nodo di categoria del canale](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="3c82f-128">Pubblicare le modifiche</span><span class="sxs-lookup"><span data-stu-id="3c82f-128">Publish changes</span></span>

<span data-ttu-id="3c82f-129">Affinché le modifiche diventino effettive, è necessario pubblicarle.</span><span class="sxs-lookup"><span data-stu-id="3c82f-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="3c82f-130">Per pubblicare le modifiche, attenersi alla procedura riportata di seguito.</span><span class="sxs-lookup"><span data-stu-id="3c82f-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="3c82f-131">Nel riquadro azioni, selezionare **Pubblica aggiornamenti canale**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="3c82f-132">Nel riquadro **Pubblica aggiornamenti canale**, selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c82f-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="3c82f-133">L'immagine seguente mostra come pubblicare gli aggiornamenti dei canali.</span><span class="sxs-lookup"><span data-stu-id="3c82f-133">The following image shows how to publish channel updates.</span></span>

![Pubblica aggiornamenti canale](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="3c82f-135">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="3c82f-135">Additional resources</span></span>

[<span data-ttu-id="3c82f-136">Creare una gerarchia di navigazione nei canali</span><span class="sxs-lookup"><span data-stu-id="3c82f-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)




[!INCLUDE[footer-include](../includes/footer-banner.md)]