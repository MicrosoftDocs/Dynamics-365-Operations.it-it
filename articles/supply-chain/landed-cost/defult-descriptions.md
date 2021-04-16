---
title: Descrizioni predefinite per la contabilità generale
description: Le descrizioni predefinite possono essere utilizzate per aggiornare il campo Descrizione nelle registrazioni dei giustificativi nella contabilità generale.
author: sherry-zheng
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TransactionTexts
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: d5a38af57d614ae2c93b0af74ec4a1c085519d46
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5841900"
---
# <a name="default-descriptions-for-the-general-ledger"></a><span data-ttu-id="61ce7-103">Descrizioni predefinite per la contabilità generale</span><span class="sxs-lookup"><span data-stu-id="61ce7-103">Default descriptions for the general ledger</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="61ce7-104">Le descrizioni predefinite possono essere utilizzate per aggiornare il campo **Descrizione** nelle registrazioni dei giustificativi nella contabilità generale.</span><span class="sxs-lookup"><span data-stu-id="61ce7-104">Default descriptions can be used to update the **Description** field in voucher postings to the general ledger.</span></span> <span data-ttu-id="61ce7-105">Questa funzionalità è stata migliorata per essere utilizzata con il modulo Costo sbarcato.</span><span class="sxs-lookup"><span data-stu-id="61ce7-105">This functionality has been enhanced to work with Landed cost.</span></span>

<span data-ttu-id="61ce7-106">Per impostare le descrizioni predefinite per le registrazioni contabili, vai a **Amministrazione organizzativa\> Impostare \> Descrizioni predefinite**.</span><span class="sxs-lookup"><span data-stu-id="61ce7-106">To set up default descriptions for ledger postings, go to **Organizational administration \> Setup \> Default descriptions**.</span></span>

<span data-ttu-id="61ce7-107">La tabella seguente elenca i nuovi valori aggiunti per il campo **Descrizione** nella pagina **Descrizioni predefinite** per supportare il modulo Costo sbarcato.</span><span class="sxs-lookup"><span data-stu-id="61ce7-107">The following table lists the new values that have been added for the **Description** field on the **Default descriptions** page to support Landed cost.</span></span>

| <span data-ttu-id="61ce7-108">Tipo di descrizione</span><span class="sxs-lookup"><span data-stu-id="61ce7-108">Description type</span></span> | <span data-ttu-id="61ce7-109">Note</span><span class="sxs-lookup"><span data-stu-id="61ce7-109">Notes</span></span> |
|---|---|
| <span data-ttu-id="61ce7-110">Determinazione costi di importazione - Rateo costi</span><span class="sxs-lookup"><span data-stu-id="61ce7-110">Import costing – Cost accrual</span></span> | <span data-ttu-id="61ce7-111">Quando viene registrata una fattura di ordine fornitore, viene elaborata un rateo dei costi per i costi di viaggio stimati.</span><span class="sxs-lookup"><span data-stu-id="61ce7-111">When a purchase order invoice is posted, a cost accrual is processed for estimate voyage costs.</span></span> <span data-ttu-id="61ce7-112">È possibile specificare descrizioni predefinite per aggiungere il numero di viaggio alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="61ce7-112">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="61ce7-113">Usa *%4* per il numero di spedizione.</span><span class="sxs-lookup"><span data-stu-id="61ce7-113">Use *%4* for the shipment number.</span></span> |
| <span data-ttu-id="61ce7-114">Determinazione costi di importazione - Ordine merci in transito</span><span class="sxs-lookup"><span data-stu-id="61ce7-114">Import costing – Goods in transit order</span></span> | <span data-ttu-id="61ce7-115">Se si utilizza l'elaborazione in transito, la fattura dell'ordine fornitore viene registrata e le merci vengono registrate in un conto merci in transito.</span><span class="sxs-lookup"><span data-stu-id="61ce7-115">If you're using in-transit processing, the purchase order invoice is posted, and the goods are posted to a goods in transit account.</span></span> <span data-ttu-id="61ce7-116">È possibile specificare descrizioni predefinite per aggiungere il numero dell'ordine in transito alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="61ce7-116">Default descriptions can be specified to add the in-transit order number to the description.</span></span> <span data-ttu-id="61ce7-117">Usa *%4* per il numero dell'ordine in transito.</span><span class="sxs-lookup"><span data-stu-id="61ce7-117">Use *%4* for the in-transit order number.</span></span> |
| <span data-ttu-id="61ce7-118">Magazzino - Chiusura - Rettifica</span><span class="sxs-lookup"><span data-stu-id="61ce7-118">Inventory – close – adjustment</span></span> | <span data-ttu-id="61ce7-119">Quando viene elaborata una fattura della contabilità fornitori per i costi di viaggio, viene elaborata una rettifica magazzino per i costi di viaggio stimati.</span><span class="sxs-lookup"><span data-stu-id="61ce7-119">When the accounts payable (AP) invoice is processed for a voyage cost, an inventory adjustment is processed to estimate voyage costs.</span></span> <span data-ttu-id="61ce7-120">È possibile specificare descrizioni predefinite per aggiungere il numero di viaggio alla descrizione.</span><span class="sxs-lookup"><span data-stu-id="61ce7-120">Default descriptions can be specified to add the voyage number to the description.</span></span> <span data-ttu-id="61ce7-121">Usa *%4* per il numero di spedizione.</span><span class="sxs-lookup"><span data-stu-id="61ce7-121">Use *%4* for the shipment number.</span></span> |

<span data-ttu-id="61ce7-122">Per ulteriori informazioni su come utilizzare la pagina **Descrizioni predefinite**, vedi [Impostare descrizioni predefinite per la registrazione automatica](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span><span class="sxs-lookup"><span data-stu-id="61ce7-122">For more information about how to work with the **Default descriptions** page, see [Set up default descriptions for automatic posting](../../finance/general-ledger/set-up-default-descriptions-for-automatic-posting.md).</span></span>
