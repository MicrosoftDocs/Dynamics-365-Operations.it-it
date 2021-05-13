---
title: Non puoi confermare una spedizione a causa di un problema con il calendario
description: Non puoi confermare una spedizione a causa di un problema con il calendario
author: perlynne
ms.date: 04/21/2021
ms.topic: troubleshooting
ms.search.form: WHSLoadTable_WHSShipConfirm,WHSLoadPlanningListPage_WHSShipConfirm,WHSLoadPlanningWorkbench_WHSShipConfirm,WHSTransportLoad_WHSShipConfirm,WHSShipPlanningListPage_WHSShipConfirm,WHSShipmentDetails_WHSShipConfirm,WHSWorkTable_WHSShipConfirm,WHSWorkTableListPage_WHSShipConfirm,Dialog_WHSOutboundShipConfirmController_WHSOutboundShipConfirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: lbc
ms.search.validFrom: 2021-04-21
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: f1fccd10d8867252f32b37c77f9a3bad54157bdd
ms.sourcegitcommit: cd9016e9787169cb800889d335b9c5919ddbe4af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "5938499"
---
# <a name="you-cant-confirm-a-shipment-because-of-an-issue-with-the-calendar"></a><span data-ttu-id="7c4e8-103">Non puoi confermare una spedizione a causa di un problema con il calendario</span><span class="sxs-lookup"><span data-stu-id="7c4e8-103">You can't confirm a shipment because of an issue with the calendar</span></span>

<span data-ttu-id="7c4e8-104">Codice errore: TRX2716</span><span class="sxs-lookup"><span data-stu-id="7c4e8-104">Error code: TRX2716</span></span>

## <a name="symptoms"></a><span data-ttu-id="7c4e8-105">Sintomi</span><span class="sxs-lookup"><span data-stu-id="7c4e8-105">Symptoms</span></span>

<span data-ttu-id="7c4e8-106">Quando si tenta di confermare una spedizione, il sistema mostra il seguente messaggio di errore:</span><span class="sxs-lookup"><span data-stu-id="7c4e8-106">When you try to confirm a shipment, the system shows the following error message:</span></span>

> <span data-ttu-id="7c4e8-107">Il tipo di calendario %1 richiede il check-in e il check-out per l'appuntamento %2.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-107">The calendar type %1 requires the appointment %2 to be checked in and out.</span></span>

<span data-ttu-id="7c4e8-108">Pertanto, non è possibile confermare la spedizione per il carico.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-108">Therefore, you can't confirm the shipment for the load.</span></span>

## <a name="cause"></a><span data-ttu-id="7c4e8-109">Causa</span><span class="sxs-lookup"><span data-stu-id="7c4e8-109">Cause</span></span>

<span data-ttu-id="7c4e8-110">Esistono appuntamenti attivi per il carico.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-110">Active appointments for the load exist.</span></span> <span data-ttu-id="7c4e8-111">Ad esempio, esiste una regola che richiede il check-in del conducente.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-111">For example, there is a rule that requires driver check-in.</span></span> <span data-ttu-id="7c4e8-112">Pertanto il carico si trova attualmente in uno stato in cui la conferma della spedizione non riesce.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-112">Therefore, the load is currently in a state where shipment confirmation fails.</span></span>

## <a name="resolution"></a><span data-ttu-id="7c4e8-113">Risoluzione</span><span class="sxs-lookup"><span data-stu-id="7c4e8-113">Resolution</span></span>

<span data-ttu-id="7c4e8-114">È necessario esaminare e risolvere eventuali problemi con gli appuntamenti attivi collegati al carico.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-114">You must investigate and fix any issues with the active appointments that are linked to the load.</span></span>

1. <span data-ttu-id="7c4e8-115">Passare a **Gestione magazzino \> Carichi \> Tutti i carichi**.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-115">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="7c4e8-116">Seleziona il carico per cui la spedizione non può essere confermata.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-116">Select the load that the shipment can't be confirmed for.</span></span>
1. <span data-ttu-id="7c4e8-117">Nel riquadro azioni, nel gruppo **Appuntamenti** della scheda **Trasporto**, selezionare **Programmazione appuntamenti**.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-117">On the Action Pane, on the **Transportation** tab, in the **Appointments** group, select **Appointment scheduling**.</span></span>
1. <span data-ttu-id="7c4e8-118">Eseguire uno dei passaggi riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-118">Follow one of these steps:</span></span>

    - <span data-ttu-id="7c4e8-119">Assicurati che il check-in/check-out del conducente sia completato per l'appuntamento.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-119">Make sure that driver check-in/check-out is completed for the appointment.</span></span>
    - <span data-ttu-id="7c4e8-120">Completa o annulla l'appuntamento.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-120">Complete or cancel the appointment.</span></span>
    - <span data-ttu-id="7c4e8-121">Disabilita l'opzione **Check-in conducente richiesto** per la regola dell'appuntamento correlato.</span><span class="sxs-lookup"><span data-stu-id="7c4e8-121">Disable the **Driver check-in required** option for the related appointment rule.</span></span>
