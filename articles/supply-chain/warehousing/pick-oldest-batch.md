---
title: Prelevare il batch meno recente su un dispositivo mobile
description: In questo argomento viene descritto come impostare e applicare le opzioni per prelevare il batch meno recente da un dispositivo mobile.
author: Mirzaab
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fdf6335bd333569e278ccd9cf3972c0ec57d4e6c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989670"
---
# <a name="pick-oldest-batch-on-a-mobile-device"></a><span data-ttu-id="03571-103">Prelevare il batch meno recente su un dispositivo mobile</span><span class="sxs-lookup"><span data-stu-id="03571-103">Pick oldest batch on a mobile device</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="03571-104">È possibile accedere alla configurazione **Preleva batch meno recente** tramite un menu del dispositivo mobile e forzare o avvertire gli addetti del magazzino a prelevare il batch meno recente per l'ubicazione corrente.</span><span class="sxs-lookup"><span data-stu-id="03571-104">You can access the configuration **Pick oldest batch** via a mobile device menu and it allows you to force or warn warehouse workers to pick the oldest batch in their current location.</span></span>  

## <a name="where-it-applies"></a><span data-ttu-id="03571-105">Dove si applica</span><span class="sxs-lookup"><span data-stu-id="03571-105">Where it applies</span></span>
<span data-ttu-id="03571-106">L'opzione Preleva batch meno recente è configurata nelle voci di menu del dispositivo mobile e ha impatto sul prelievo di batch degli articoli seguenti.</span><span class="sxs-lookup"><span data-stu-id="03571-106">Pick oldest batch is configured on mobile device menu items and effects the pick for batch below items.</span></span>

## <a name="how-to-set-up-the-configuration-for-pick-oldest-batch"></a><span data-ttu-id="03571-107">Come impostare la configurazione per Preleva batch meno recente</span><span class="sxs-lookup"><span data-stu-id="03571-107">How to set up the configuration for Pick oldest batch</span></span> 
<span data-ttu-id="03571-108">Per gli articoli impostati per utilizzare il lavoro esistente, **Preleva batch meno recente** può essere impostata su **Nessuno**, **Avvisa** o **Forza** dal menu del dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="03571-108">For items that are set to use existing work, **Pick oldest batch** can be set to **None**, **Warn**, or **Force** from a mobile device menu.</span></span>

<span data-ttu-id="03571-109">**Nessuno**: i lavoratori non riceveranno messaggi e potranno prelevare qualsiasi batch nella loro ubicazione.</span><span class="sxs-lookup"><span data-stu-id="03571-109">**None**: Workers will not receive any messages and they will be allowed to pick any batch in their location.</span></span>

<span data-ttu-id="03571-110">**Avvisa** e **Forza**: un elenco di batch con la data di scadenza meno recente verrà visualizzato sopra il controllo del batch quando il lavoratore seleziona un batch.</span><span class="sxs-lookup"><span data-stu-id="03571-110">**Warn** and **Force**:  A list of the batch(es) with the oldest expiration date will be displayed above the batch control when the worker selects a batch.</span></span> <span data-ttu-id="03571-111">Se l'ubicazione è controllata mediante targa, un elenco delle targhe con il batch meno recente verrà visualizzato sopra il controllo della targa.</span><span class="sxs-lookup"><span data-stu-id="03571-111">If the location is license plate controlled, a list of license plates that have the oldest batch will be displayed above the license plate control.</span></span> 
-   <span data-ttu-id="03571-112">**Avvisa**: se un lavoratore sceglie una targa o un batch che non appaiono nell'elenco, il controllo verrà lasciato vuoto e verrà visualizzato un avviso che indica la presenza di un batch meno recente da selezionare.</span><span class="sxs-lookup"><span data-stu-id="03571-112">**Warn**: If a worker chooses a license plate or batch that is not on the shown list, the control will be blanked and a warning will be shown that there is an older batch to select.</span></span> <span data-ttu-id="03571-113">Per continuare il lavoro, il lavoratore può selezionare nuovamente la stessa targa o batch.</span><span class="sxs-lookup"><span data-stu-id="03571-113">To be allowed to continue the work, the worker can select the same license plate or batch again.</span></span>  
-   <span data-ttu-id="03571-114">**Forza**: i lavoratori continueranno a ricevere il messaggio che indica la presenza di un batch meno recente da prelevare.</span><span class="sxs-lookup"><span data-stu-id="03571-114">**Force**: Workers will continue to receive the message that there is an older batch to pick.</span></span>
