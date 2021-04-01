---
title: Sequenza numerica della gestione trasporto
description: Questo argomento descrive come impostare le sequenze numeriche per la gestione del trasporto.
author: Henrikan
manager: tfehr
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2020-10-16
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: cc19110f481c11ab28532d69a4689c1db048f6c3
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2021
ms.locfileid: "5233369"
---
# <a name="transportation-management-number-sequence"></a><span data-ttu-id="b3090-103">Sequenza numerica della gestione trasporto</span><span class="sxs-lookup"><span data-stu-id="b3090-103">Transportation management number sequence</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b3090-104">Utilizzare la pagina **Sequenze numeriche** nel modulo di gestione dei trasporti per impostare vari numeri processo.</span><span class="sxs-lookup"><span data-stu-id="b3090-104">Use the **Number sequences** page in the transportation management module to set up various pro numbers.</span></span> <span data-ttu-id="b3090-105">I numeri processo vengono utilizzati dai corrieri per organizzare e monitorare lo stato di avanzamento di ogni spedizione.</span><span class="sxs-lookup"><span data-stu-id="b3090-105">Pro numbers are used by carriers to organize and track the progress of each shipment.</span></span>

## <a name="create-a-number-sequence-for-a-pro-number"></a><span data-ttu-id="b3090-106">Creare una sequenza numerica per un numero prodotto</span><span class="sxs-lookup"><span data-stu-id="b3090-106">Create a number sequence for a pro number</span></span>

<span data-ttu-id="b3090-107">Per creare una sequenza numerica per un numero prodotto, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b3090-107">To create a number sequence for a pro number, do the following:</span></span>

1. <span data-ttu-id="b3090-108">Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Sequenze numeriche**.</span><span class="sxs-lookup"><span data-stu-id="b3090-108">Go to **Transportation management \> Setup \> Carriers \> Number sequences**.</span></span>
1. <span data-ttu-id="b3090-109">Selezionare **Nuovo** per creare una nuova sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="b3090-109">Select **New** to create a new number sequence.</span></span>
1. <span data-ttu-id="b3090-110">Immettere un ID univoco e un nome descrittivo per la sequenza numerica.</span><span class="sxs-lookup"><span data-stu-id="b3090-110">Enter a unique ID and descriptive name for the number sequence.</span></span>
1. <span data-ttu-id="b3090-111">Nel campo **Tipo di sequenza numerica**, *Numero prodotto* è l'unica opzione.</span><span class="sxs-lookup"><span data-stu-id="b3090-111">In the **Number sequence type** field, *Pro number* is the only option.</span></span>
1. <span data-ttu-id="b3090-112">Nel campo **Cifra di controllo**, *Cifra di controllo* è l'unica opzione ed è impostato come motore generico.</span><span class="sxs-lookup"><span data-stu-id="b3090-112">In the **Check digit** field, *Check digit* is the only option and is set up as a generic engine.</span></span>
1. <span data-ttu-id="b3090-113">Nella scheda dettaglio **Sequenza** fornire informazioni sulla sequenza.</span><span class="sxs-lookup"><span data-stu-id="b3090-113">On the **Sequence** FastTab, provide information about the sequence.</span></span>
1. <span data-ttu-id="b3090-114">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b3090-114">Close the page.</span></span>

## <a name="link-a-number-sequence-to-a-shipping-carrier"></a><span data-ttu-id="b3090-115">Collegare una sequenza numerica a un vettore</span><span class="sxs-lookup"><span data-stu-id="b3090-115">Link a number sequence to a shipping carrier</span></span>

<span data-ttu-id="b3090-116">Per collegare una sequenza numerica a un vettore, procedere come segue:</span><span class="sxs-lookup"><span data-stu-id="b3090-116">To link a number sequence to a carrier, do the following:</span></span>

1. <span data-ttu-id="b3090-117">Vai a **Gestione trasporto \> Impostazioni \> Vettori \> Vettori spedizione**.</span><span class="sxs-lookup"><span data-stu-id="b3090-117">Go to **Transportation management \> Setup \> Carriers \> Shipping carriers**.</span></span>
1. <span data-ttu-id="b3090-118">Selezionare un vettore di spedizione.</span><span class="sxs-lookup"><span data-stu-id="b3090-118">Select a shipping carrier.</span></span>
1. <span data-ttu-id="b3090-119">Seleziona **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b3090-119">Select **Edit**.</span></span>
1. <span data-ttu-id="b3090-120">Nella scheda dettaglio **Panoramica** selezionare un'opzione nel campo **Sequenza numerica prodotto**.</span><span class="sxs-lookup"><span data-stu-id="b3090-120">On the **Overview** FastTab, select an option in the **Pro number sequence** field.</span></span>
1. <span data-ttu-id="b3090-121">Chiudere la pagina.</span><span class="sxs-lookup"><span data-stu-id="b3090-121">Close the page.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]