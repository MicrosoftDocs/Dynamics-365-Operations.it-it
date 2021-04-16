---
title: Parametri di approvvigionamento per Costo sbarcato
description: In questo argomento viene descritto come impostare i parametri di approvvigionamento quando si utilizza il modulo Costo sbarcato.
author: sherry-zheng
ms.date: 12/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SrmParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-09
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: df91fcb97794be32924707fcecf2b5fb34844596
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833931"
---
# <a name="procurement-and-sourcing-parameters-for-landed-cost"></a><span data-ttu-id="887c0-103">Parametri di approvvigionamento per Costo sbarcato</span><span class="sxs-lookup"><span data-stu-id="887c0-103">Procurement and sourcing parameters for Landed cost</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="887c0-104">La pagina **Parametri di approvvigionamento** ha alcune impostazioni che sono particolarmente pertinenti quando si utilizza il modulo **Costo sbarcato**.</span><span class="sxs-lookup"><span data-stu-id="887c0-104">The **Procurement and sourcing parameters** page has a few settings that are especially relevant when you use the **Landed cost** module.</span></span> <span data-ttu-id="887c0-105">Utilizzare la finestra di dialogo **Aggiorna righe ordine** che viene aperta dalla pagina **Parametri di approvvigionamento** per specificare se le righe dell'ordine fornitore devono essere aggiornate automaticamente quando vengono apportate modifiche all'intestazione dell'ordine fornitore.</span><span class="sxs-lookup"><span data-stu-id="887c0-105">Use the **Update order lines** dialog box that is opened from the **Procurement and sourcing parameters** page to specify whether purchase order lines should automatically be updated when changes are made on the purchase order header.</span></span>

<span data-ttu-id="887c0-106">Per completare questa impostazione, attenersi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="887c0-106">To complete this setup, follow these steps.</span></span>

1. <span data-ttu-id="887c0-107">Passare a **Approvvigionamento \> Impostazione \> Parametri di approvvigionamento**.</span><span class="sxs-lookup"><span data-stu-id="887c0-107">Go to **Procurement and sourcing \> Setup \> Procurement and sourcing parameters**.</span></span>
1. <span data-ttu-id="887c0-108">Nella scheda **Generale**, selezionare il collegamento **Aggiorna righe ordine**.</span><span class="sxs-lookup"><span data-stu-id="887c0-108">On the **General** tab, select the **Update order lines** link.</span></span>
1. <span data-ttu-id="887c0-109">La finestra di dialogo **Aggiorna righe ordine** elenca i campi nell'intestazione dell'ordine che possono anche applicare aggiornamenti automatici ai campi correlati nelle righe ordine.</span><span class="sxs-lookup"><span data-stu-id="887c0-109">The **Update order lines** dialog box lists the fields on the order header that can also apply automatic updates to related fields on the order lines.</span></span> <span data-ttu-id="887c0-110">Impostare ogni campo nell'elenco su uno dei seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="887c0-110">Set each field in the list to one of the following values:</span></span>

    - <span data-ttu-id="887c0-111">**Sempre** - Le righe ordine devono essere aggiornate automaticamente quando l'intestazione ordine viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="887c0-111">**Always** – The order lines should automatically be updated when the order header is updated.</span></span>
    - <span data-ttu-id="887c0-112">**Mai** - Le righe ordine non devono mai essere aggiornate quando l'intestazione dell'ordine viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="887c0-112">**Never** – The order lines should never be updated when the order header is updated.</span></span>
    - <span data-ttu-id="887c0-113">**Richiesta** - All'utente verrà chiesto se le righe ordine devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="887c0-113">**Prompt** – The user will be prompted to select whether the order lines should be updated.</span></span>
