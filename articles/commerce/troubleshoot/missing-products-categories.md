---
title: Prodotti e categorie mancanti dopo la copia dell'ambiente
description: Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando prodotti e categorie risultano mancanti dopo che un sito viene copiato tra ambienti o nello stesso ambiente.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 527fd0fa62775f65f61b538474b1d45d1a0155ed
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801725"
---
# <a name="products-and-categories-missing-after-environment-copy"></a><span data-ttu-id="7ea80-103">Prodotti e categorie mancanti dopo la copia dell'ambiente</span><span class="sxs-lookup"><span data-stu-id="7ea80-103">Products and categories missing after environment copy</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7ea80-104">Questo argomento fornisce indicazioni per la risoluzione dei problemi che possono essere utili quando prodotti e categorie risultano mancanti dopo che un sito viene copiato tra ambienti o nello stesso ambiente.</span><span class="sxs-lookup"><span data-stu-id="7ea80-104">This topic provides troubleshooting guidance that can help when products and categories are missing after a site is copied between environments or within the same environment.</span></span>

## <a name="description"></a><span data-ttu-id="7ea80-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7ea80-105">Description</span></span>

<span data-ttu-id="7ea80-106">Dopo che un sito viene copiato da un ambiente a un altro o nello stesso ambiente, i prodotti e le categorie risultano mancanti nel sito.</span><span class="sxs-lookup"><span data-stu-id="7ea80-106">After a site is copied from one environment to another, or within the same environment, the products and categories are missing from the site.</span></span> <span data-ttu-id="7ea80-107">I prodotti e le categorie mancheranno nella vetrina di e-commerce e nella scheda **Prodotti** di Creazione di siti di Commerce.</span><span class="sxs-lookup"><span data-stu-id="7ea80-107">The products and categories will be missing from the e-commerce storefront and from the **Products** tab in Commerce site builder.</span></span>

## <a name="resolution"></a><span data-ttu-id="7ea80-108">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="7ea80-108">Resolution</span></span>

### <a name="map-the-channel-operating-unit-number-to-a-newly-copied-site-in-commerce-site-builder"></a><span data-ttu-id="7ea80-109">Mappare il numero di unità operativa del canale a un sito appena copiato in Creazione di siti di Commerce</span><span class="sxs-lookup"><span data-stu-id="7ea80-109">Map the channel operating unit number to a newly copied site in Commerce site builder</span></span>

<span data-ttu-id="7ea80-110">Per mappare il numero di unità operativa del canale a un sito appena copiato in Creazione di siti di Commerce, procedere come segue.</span><span class="sxs-lookup"><span data-stu-id="7ea80-110">To map the channel operating unit number (OUN) to a newly copied site in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="7ea80-111">Selezionare il sito appena copiato.</span><span class="sxs-lookup"><span data-stu-id="7ea80-111">Select the newly copied site.</span></span>
1. <span data-ttu-id="7ea80-112">Sotto **Impostazioni sito**, selezionare **Canali**.</span><span class="sxs-lookup"><span data-stu-id="7ea80-112">Under **Site settings**, select **Channels**.</span></span>
1. <span data-ttu-id="7ea80-113">Accanto al nome del canale, selezionare i puntini di sospensione (**...**), quindi selezionare **Modifica canale punto vendita online**.</span><span class="sxs-lookup"><span data-stu-id="7ea80-113">Next to the channel name, select the ellipsis (**...**), and then select **Change online store channel**.</span></span>
1. <span data-ttu-id="7ea80-114">Nella finestra di dialogo **Modifica canale punto vendita online**, selezionare il canale da mappare al sito appena copiato, quindi selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ea80-114">In the **Change online store channel** dialog box, select the channel to map to the newly copied site, and then select **OK**.</span></span>
1. <span data-ttu-id="7ea80-115">Seleziona **Salva e pubblica**.</span><span class="sxs-lookup"><span data-stu-id="7ea80-115">Select **Save and publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7ea80-116">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="7ea80-116">Additional resources</span></span>

[<span data-ttu-id="7ea80-117">Associare un sito Dynamics 365 Commerce a un canale online</span><span class="sxs-lookup"><span data-stu-id="7ea80-117">Associate a Dynamics 365 Commerce site with an online channel</span></span>](../associate-site-online-store.md)
