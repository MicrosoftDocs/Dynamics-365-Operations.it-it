---
title: Conferma prodotto per prelievo cluster
description: Viene descritta la procedura per l'impostazione della verifica dell'articolo e del prelievo cluster.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFAutoConfirm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c8f81d760e8c181891aeba92834577e8869fbdd8
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001126"
---
# <a name="product-confirmation-for-cluster-picking"></a><span data-ttu-id="70a95-103">Conferma prodotto per prelievo cluster</span><span class="sxs-lookup"><span data-stu-id="70a95-103">Product confirmation for cluster picking</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="70a95-104">Il prelievo cluster consente di selezionare gli articoli per più ordini contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="70a95-104">Cluster picking allows you to pick items for several orders at the same time.</span></span> <span data-ttu-id="70a95-105">Quando il prelievo cluster viene applicato, la conferma dell'articolo è essenziale per verificare che gli articoli vengano aggiunti ai cluster.</span><span class="sxs-lookup"><span data-stu-id="70a95-105">When cluster picking is applied, item confirmation is crucial to verify the items that are added to clusters.</span></span> <span data-ttu-id="70a95-106">È possibile verificare gli articoli nel prelievo cluster durante il processo di prelievo cluster.</span><span class="sxs-lookup"><span data-stu-id="70a95-106">You can verify items in cluster picking during the cluster picking process.</span></span>

## <a name="where-it-applies"></a><span data-ttu-id="70a95-107">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="70a95-107">Where it applies</span></span>

<span data-ttu-id="70a95-108">La verifica dell'articolo per il prelievo cluster funziona nello stesso modo della verifica degli articoli nei processi di prelievo non cluster.</span><span class="sxs-lookup"><span data-stu-id="70a95-108">Item verification for cluster picking works the same way as when you verify items in a non-cluster picking processes.</span></span> <span data-ttu-id="70a95-109">L'impostazione dipende dall'impostazione dei codici a barre del prodotto.</span><span class="sxs-lookup"><span data-stu-id="70a95-109">The setup is based on the product bar code setup.</span></span>

## <a name="set-up-item-verification-with-cluster-picking"></a><span data-ttu-id="70a95-110">Impostare la verifica dell'articolo con prelievo cluster</span><span class="sxs-lookup"><span data-stu-id="70a95-110">Set up item verification with cluster picking</span></span>

1. <span data-ttu-id="70a95-111">Su una voce di menu del dispositivo mobile, aprire il modulo di impostazione per la conferma di lavoro: **Gestione magazzino** > **Gestione magazzino** > **Impostazione** > **Dispositivo mobile** > **Voci di menu del dispositivo mobile**.</span><span class="sxs-lookup"><span data-stu-id="70a95-111">On a mobile device menu item, open the setup form for work confirmation: **Warehouse management** > **Warehouse management** > **Setup** > **Mobile device** > **Mobile device menu items**.</span></span>
1. <span data-ttu-id="70a95-112">Dalle voci di menu del dispositivo mobile, aprire la **configurazione della conferma del lavoro**.</span><span class="sxs-lookup"><span data-stu-id="70a95-112">From the mobile device menu item, open **Work confirmation setup**.</span></span>

|        <span data-ttu-id="70a95-113">Opzione</span><span class="sxs-lookup"><span data-stu-id="70a95-113">Option</span></span>        |                                    <span data-ttu-id="70a95-114">descrizione</span><span class="sxs-lookup"><span data-stu-id="70a95-114">Description</span></span>                                    |
|----------------------|-----------------------------------------------------------------------------------|
| <span data-ttu-id="70a95-115">Conferma prodotto</span><span class="sxs-lookup"><span data-stu-id="70a95-115">Product confirmation</span></span> | <span data-ttu-id="70a95-116">Consente di verificare ogni pezzo di magazzino dal dispositivo mobile sottoposto a scansione.</span><span class="sxs-lookup"><span data-stu-id="70a95-116">Allows you to verify each piece of inventory from the mobile device when scanned.</span></span> |
