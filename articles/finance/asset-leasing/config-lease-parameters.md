---
title: Configurare i parametri del leasing (anteprima)
description: Questo argomento descrive le impostazioni di configurazione per Leasing cespite, come le informazioni sulla sicurezza e le impostazioni di contabilità.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 77caf751f9baf4abef534bac97e226484df7acf7
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881278"
---
# <a name="configure-lease-parameters"></a><span data-ttu-id="2d1f7-103">Configurare i parametri del leasing</span><span class="sxs-lookup"><span data-stu-id="2d1f7-103">Configure lease parameters</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="2d1f7-104">Diverse impostazioni di configurazione influiscono sul comportamento di Leasing cespite.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-104">Several configuration settings affect how Asset leasing behaves.</span></span> <span data-ttu-id="2d1f7-105">Queste impostazioni includono nomi di giornali di registrazione, parametri generali e impostazioni del profilo di registrazione.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-105">These settings include journal names, general parameters, and posting profile settings.</span></span>

1. <span data-ttu-id="2d1f7-106">Vai a **Leasing cespite \> Imposta \> Parametri di leasing cespite**.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-106">Go to **Asset leasing \> Setup \> Asset leasing parameters**.</span></span>
2. <span data-ttu-id="2d1f7-107">Nella scheda **Leasing**, seleziona la Scheda dettaglio **Generale**.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-107">On the **Leases** tab, select the **General** FastTab.</span></span>

    <span data-ttu-id="2d1f7-108">Il parametro **Consenti l'override della classificazione manuale** determina se la classificazione del leasing può essere sovrascritta prima della conferma dello scadenziario pagamenti.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-108">The **Allow manual classification override** parameter determines whether the lease classification can be overridden before the payment schedule is confirmed.</span></span>

    <span data-ttu-id="2d1f7-109">Il parametro **Batch tra entità** determina se è possibile registrare su altre persone giuridiche dalla persona giuridica corrente.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-109">The **Cross-entity batch** parameter determines whether you can post to other legal entities from the current legal entity.</span></span> <span data-ttu-id="2d1f7-110">Se questo parametro è attivato, puoi creare registrazioni a giornale per le persone giuridiche a cui hai accesso.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-110">If this parameter is turned on, you can create journal entries for the legal entities that you have access to.</span></span>

3. <span data-ttu-id="2d1f7-111">Imposta l'opzione **Consenti l'eliminazione dei leasing confermati** su **Sì** per consentire l'eliminazione dei leasing che hanno confermato scadenziari di pagamento.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-111">Set the **Allow delete of confirmed leases** option to **Yes** to allow leases that have confirmed payment schedules to be deleted.</span></span> <span data-ttu-id="2d1f7-112">I leasing non possono essere eliminati se ad essi sono associate transazioni registrate o non registrate, indipendentemente dall'impostazione di questa opzione.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-112">Leases can't be deleted if posted or unposted transactions are associated with them, regardless of the setting of this option.</span></span> <span data-ttu-id="2d1f7-113">Non puoi ripristinare un record di leasing dopo che è stato eliminato.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-113">You can't restore a lease record after it's deleted.</span></span> <span data-ttu-id="2d1f7-114">Se carichi record per un leasing eliminato, manualmente o tramite entità di dati, le informazioni caricate vengono trattate come nuove, non come un aggiornamento di un leasing esistente.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-114">If you upload any records for a deleted lease, either manually or through data entities, the uploaded information is treated as new, not as an update to an existing lease.</span></span>

    <span data-ttu-id="2d1f7-115">Se imposti questa opzione su **Sì** e il tipo di transizione del libro è **Recupero cumulativo Opzione A o B**, il sistema imposta il campo **Tasso incrementale di prestito** sul valore del campo **Tasso incrementale di prestito durante la transizione** nella pagina **Impostazione libro**.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-115">If you set this option to **Yes**, and the transition type of the book is **Cumulative Catchup Option A or B**, the system sets the **Incremental borrowing rate** field to the value of the **Incremental borrowing rate at transition** field on the **Book setup** page.</span></span> <span data-ttu-id="2d1f7-116">Se questa opzione è impostata su **No**, il tasso sul leasing principale è impostato sul valore del campo **Tasso incrementale di prestito** nella pagina **Dettagli libro**, indipendentemente dal tipo di transizione del libro.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-116">If this option is set to **No**, the rate on the head lease is set to the value of the **Incremental borrowing rate** field on the **Book details** page, regardless of the transition type of the book.</span></span>

4. <span data-ttu-id="2d1f7-117">Imposta l'opzione **Consenti storni di ammortamento sulla versione a libro chiuso** su **Sì** per consentire lo storno delle transazioni di ammortamento.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-117">Set the **Allow depreciation reversals on closed book version** option to **Yes** to allow depreciation expense transactions to be reversed.</span></span> <span data-ttu-id="2d1f7-118">Le transazioni di spesa possono essere stornate anche quando la versione del libro è chiusa.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-118">Expense transactions can be reversed even when the book version is closed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d1f7-119">È consigliabile mantenere questa opzione impostata su **No**.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-119">We recommend that you keep this option set to **No**.</span></span> <span data-ttu-id="2d1f7-120">L'impostazione di questa opzione viene utilizzata come convalida e controllo per impedire l'ammortamento accidentale di una versione del libro chiuso.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-120">The setting of this option is used as a validation and control to prevent a closed book version from being accidently depreciated.</span></span> <span data-ttu-id="2d1f7-121">Mantenendo l'opzione impostata su **No**, contribuisci a mantenere accurati i calcoli del valore contabile netto e dell'ammortamento futuro.</span><span class="sxs-lookup"><span data-stu-id="2d1f7-121">By keeping the option set to **No**, you help keep the net book value and future depreciation calculations accurate.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
