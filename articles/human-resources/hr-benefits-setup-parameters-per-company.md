---
title: Configurare i parametri di gestione dei benefit per azienda
description: Configurare i parametri di gestione dei benefit per azienda in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 87d4f1e7580b333fd17d3b779aafa47c5baed424
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805660"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="ec16d-103">Configurare i parametri di gestione dei benefit per azienda</span><span class="sxs-lookup"><span data-stu-id="ec16d-103">Configure Benefits management parameters per company</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="ec16d-104">Per ogni organizzazione che offre benefit, è necessario configurare le impostazioni per i messaggi di posta elettronica di conferma dei benefit.</span><span class="sxs-lookup"><span data-stu-id="ec16d-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="ec16d-105">Configurare impostazioni di posta elettronica per la conferma</span><span class="sxs-lookup"><span data-stu-id="ec16d-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="ec16d-106">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="ec16d-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="ec16d-107">Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="ec16d-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="ec16d-108">Campo</span><span class="sxs-lookup"><span data-stu-id="ec16d-108">Field</span></span> | <span data-ttu-id="ec16d-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ec16d-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="ec16d-110">**Invia messaggio di posta elettronica di conferma**</span><span class="sxs-lookup"><span data-stu-id="ec16d-110">**Send confirmation email**</span></span> | <span data-ttu-id="ec16d-111">Quando questa funzione è attiva, verrà inviata un messaggio di posta elettronica di conferma ai dipendenti quando effettuano il check-out dall'esperienza di registrazione dei vantaggi in self-service dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="ec16d-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="ec16d-112">**Modello di messaggio di posta elettronica di conferma**</span><span class="sxs-lookup"><span data-stu-id="ec16d-112">**Confirmation email template**</span></span> | <span data-ttu-id="ec16d-113">Selezionare il modello di posta elettronica dell'organizzazione da utilizzare quando si invia la conferma di registrazione.</span><span class="sxs-lookup"><span data-stu-id="ec16d-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="ec16d-114">Se non si seleziona un modello, verrà inviata il seguente messaggio di posta elettronica generico:</span><span class="sxs-lookup"><span data-stu-id="ec16d-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="ec16d-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="ec16d-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="ec16d-116">Congratulazioni.</span><span class="sxs-lookup"><span data-stu-id="ec16d-116">Congratulations!</span></span> <span data-ttu-id="ec16d-117">L'iscrizione ai benefit è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ec16d-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="ec16d-118">Grazie,</span><span class="sxs-lookup"><span data-stu-id="ec16d-118">Thank you,</span></span><br><span data-ttu-id="ec16d-119">Benefit di <Nome azienda/Organizzazione>.</span><span class="sxs-lookup"><span data-stu-id="ec16d-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="ec16d-120">**Indirizzo mittente di posta elettronica predefinito**</span><span class="sxs-lookup"><span data-stu-id="ec16d-120">**Default email sender address**</span></span> | <span data-ttu-id="ec16d-121">L'indirizzo di posta elettronica da utilizzare quando si invia il messaggio di posta elettronica di conferma.</span><span class="sxs-lookup"><span data-stu-id="ec16d-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="ec16d-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="ec16d-122">Select **Save**.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]