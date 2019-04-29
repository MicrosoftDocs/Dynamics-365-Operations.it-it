---
title: Novità o modifiche in Dynamics 365 for Talent Core HR (23 gennaio 2019)
description: Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 for Talent Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 01/23/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-01-23
ms.dyn365.ops.version: Talent
ms.openlocfilehash: f27698c257301f52e5c77eaa8a04ca13a0315825
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2019
ms.locfileid: "859621"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-january-23-2019"></a><span data-ttu-id="ef48a-103">Novità o modifiche in Dynamics 365 for Talent Core HR (23 gennaio 2019)</span><span class="sxs-lookup"><span data-stu-id="ef48a-103">What's new or changed in Dynamics 365 for Talent Core HR (January 23, 2019)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ef48a-104">**Build 8.1.2121**</span><span class="sxs-lookup"><span data-stu-id="ef48a-104">**Build 8.1.2121**</span></span>

<span data-ttu-id="ef48a-105">Questo argomento descrive le funzionalità nuove o modificate di Core HR.</span><span class="sxs-lookup"><span data-stu-id="ef48a-105">This topic describes features that are either new or changed in Core HR.</span></span>

## <a name="changes"></a><span data-ttu-id="ef48a-106">Modifiche</span><span class="sxs-lookup"><span data-stu-id="ef48a-106">Changes</span></span>

### <a name="import-of-employee-fixed-compensation-not-working-when-creating-new-fixed-compensation-records"></a><span data-ttu-id="ef48a-107">L'importazione della retribuzione fissa del dipendente non funziona durante la creazione di nuovi record di retribuzione fissa</span><span class="sxs-lookup"><span data-stu-id="ef48a-107">Import of employee fixed compensation not working when creating new fixed compensation records</span></span>
<span data-ttu-id="ef48a-108">È stata apportata una modifica all'entità di retribuzione fissa del dipendente per recuperare il livello retributivo all'importazione.</span><span class="sxs-lookup"><span data-stu-id="ef48a-108">A change has been made to the employee fixed compensation entity to retrieve the compensation level upon import.</span></span> <span data-ttu-id="ef48a-109">Nelle versioni precedenti, viene visualizzato un messaggio indicante che il livello è necessario.</span><span class="sxs-lookup"><span data-stu-id="ef48a-109">Prior to this release, a message was displayed indicating that the level was required.</span></span>

### <a name="remove-the-minimum-balance-field-from-the-time-off-request-dialog-box"></a><span data-ttu-id="ef48a-110">Rimozione del campo Saldo minimo dalla finestra di dialogo Richiesta permessi</span><span class="sxs-lookup"><span data-stu-id="ef48a-110">Remove the minimum balance field from the time off request dialog box</span></span>
<span data-ttu-id="ef48a-111">Il campo **Saldo minimo** è stato rimosso dalla finestra di dialogo **Richiesta permessi**.</span><span class="sxs-lookup"><span data-stu-id="ef48a-111">The **Minimum balance** field has been removed from the **Time off request** dialog box.</span></span> <span data-ttu-id="ef48a-112">Questa modifica influisce su tutte le aree in cui è possibile richiedere dei permessi.</span><span class="sxs-lookup"><span data-stu-id="ef48a-112">This change affects all areas where time off can be requested.</span></span>

### <a name="data-upgrade-for-compensation-levels-not-updating-in-all-scenarios"></a><span data-ttu-id="ef48a-113">L'aggiornamento dei dati per i livelli retributivi non viene eseguito in tutti gli scenari</span><span class="sxs-lookup"><span data-stu-id="ef48a-113">Data upgrade for compensation levels not updating in all scenarios</span></span>
<span data-ttu-id="ef48a-114">È stata effettuata una modifica per aggiornare il livello retributivo nei piani di retribuzione fissa.</span><span class="sxs-lookup"><span data-stu-id="ef48a-114">A change has been made to update the compensation level on fixed compensation plans.</span></span> <span data-ttu-id="ef48a-115">Questa modifica popolerà il livello retributivo nei piani fissi per la mansione assegnata al dipendente.</span><span class="sxs-lookup"><span data-stu-id="ef48a-115">This change will populate the compensation level on fixed plans for the job assigned to the employee.</span></span>

### <a name="payroll-information-in-the-manage-changes-page-is-only-available-when-logged-in-as-system-administrator"></a><span data-ttu-id="ef48a-116">Le informazioni sulle retribuzioni nella pagina di gestione delle modifiche sono disponibili solo dopo l'accesso come amministratore di sistema</span><span class="sxs-lookup"><span data-stu-id="ef48a-116">Payroll information in the Manage changes page is only available when logged in as System Administrator</span></span>
<span data-ttu-id="ef48a-117">Questa modifica consente ai dipendenti con ruolo Amministratore retribuzioni di accedere alle informazioni sulle retribuzioni nella pagina **Sequenza temporale modifiche > Gestione modifiche** per la posizione.</span><span class="sxs-lookup"><span data-stu-id="ef48a-117">This change allows employees with the Payroll Administrator role access to the payroll information on the **Changes timeline > Manage changes** page for the position.</span></span>

### <a name="job-fields-default-to-positions"></a><span data-ttu-id="ef48a-118">Per impostazione predefinita i campi della mansione sono impostati sulle posizioni</span><span class="sxs-lookup"><span data-stu-id="ef48a-118">Job fields default to positions</span></span>
<span data-ttu-id="ef48a-119">Quando si modifica la mansione in una posizione, per impostazione predefinita i campi della mansione sono impostati sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="ef48a-119">When changing the job on a position, job fields will default to the position.</span></span> <span data-ttu-id="ef48a-120">Verrà visualizzato un messaggio di avviso con un'opzione per accettare i valori predefiniti o mantenere i valori esistenti per tali campi.</span><span class="sxs-lookup"><span data-stu-id="ef48a-120">An alert message will appear giving an option to accept the default values or keep the existing values for those fields.</span></span>

### <a name="probation-period-and-calendar-are-not-displayed-for-future-hired-employees"></a><span data-ttu-id="ef48a-121">Il periodo di prova e il calendario non sono visualizzati per i dipendenti assunti in futuro</span><span class="sxs-lookup"><span data-stu-id="ef48a-121">Probation period and calendar are not displayed for future hired employees.</span></span>
<span data-ttu-id="ef48a-122">Con questa modifica, i campi **Periodo di prova** e **Calendario** sono stati aggiunti alla pagina **Gestione modifiche** per consentire l'immissione di dati per dipendenti futuri e passati.</span><span class="sxs-lookup"><span data-stu-id="ef48a-122">With this change, **Probation period** and **Calendar** fields have been added to the **Manage changes** page to allow for data entry for future and past employees.</span></span>

### <a name="platform-update-23"></a><span data-ttu-id="ef48a-123">Update 23 della piattaforma</span><span class="sxs-lookup"><span data-stu-id="ef48a-123">Platform update 23</span></span>
<span data-ttu-id="ef48a-124">Correzioni di bug secondarie sono state incluse nell'aggiornamento 23 della piattaforma.</span><span class="sxs-lookup"><span data-stu-id="ef48a-124">Minor bug fixes have been included as part of Platform update 23.</span></span> <span data-ttu-id="ef48a-125">Per ulteriori informazioni, vedere [Novità o modifiche nell'aggiornamento 23 della piattaforma Dynamics 365 for Finance and Operations (gennaio 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span><span class="sxs-lookup"><span data-stu-id="ef48a-125">For more information, see [What's new or changed in Dynamics 365 for Finance and Operations platform update 23 (January 2019)](https://docs.microsoft.com/en-us/dynamics365/unified-operations/fin-and-ops/get-started/whats-new-platform-update-23).</span></span> 
