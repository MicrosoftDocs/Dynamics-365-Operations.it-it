---
title: Configurare i parametri di gestione dei benefit per azienda
description: Configurare i parametri di gestione dei benefit per azienda in Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: 2943d0095e4c9421725b90e579b7cbb841038ab7
ms.sourcegitcommit: d02fae79d5c02a4bc4f4b16a410c2f5ce026c204
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "4984602"
---
# <a name="configure-benefits-management-parameters-per-company"></a><span data-ttu-id="e4c90-103">Configurare i parametri di gestione dei benefit per azienda</span><span class="sxs-lookup"><span data-stu-id="e4c90-103">Configure Benefits management parameters per company</span></span>

<span data-ttu-id="e4c90-104">Per ogni organizzazione che offre benefit, è necessario configurare le impostazioni per i messaggi di posta elettronica di conferma dei benefit.</span><span class="sxs-lookup"><span data-stu-id="e4c90-104">For each organization that offers benefits, you must configure settings for benefits confirmation emails.</span></span>

## <a name="configure-confirmation-email-settings"></a><span data-ttu-id="e4c90-105">Configurare impostazioni di posta elettronica per la conferma</span><span class="sxs-lookup"><span data-stu-id="e4c90-105">Configure confirmation email settings</span></span>

1. <span data-ttu-id="e4c90-106">Nell'area di lavoro **Gestione benefit**, sotto **Impostazione**, selezionare **Parametri Risorse umane**.</span><span class="sxs-lookup"><span data-stu-id="e4c90-106">In the **Benefits management** workspace, under **Setup**, select **Human Resources Parameters**.</span></span>

2. <span data-ttu-id="e4c90-107">Nella scheda **Gestione benefit** specificare i valori per i seguenti campi:</span><span class="sxs-lookup"><span data-stu-id="e4c90-107">In the **Benefits management** tab, specify values for the following fields:</span></span> 

   | <span data-ttu-id="e4c90-108">Campo</span><span class="sxs-lookup"><span data-stu-id="e4c90-108">Field</span></span> | <span data-ttu-id="e4c90-109">descrizione</span><span class="sxs-lookup"><span data-stu-id="e4c90-109">Description</span></span> |
   | --- | --- |
   | <span data-ttu-id="e4c90-110">**Invia messaggio di posta elettronica di conferma**</span><span class="sxs-lookup"><span data-stu-id="e4c90-110">**Send confirmation email**</span></span> | <span data-ttu-id="e4c90-111">Quando questa funzione è attiva, verrà inviata un messaggio di posta elettronica di conferma ai dipendenti quando effettuano il check-out dall'esperienza di registrazione dei vantaggi in self-service dei dipendenti.</span><span class="sxs-lookup"><span data-stu-id="e4c90-111">When this feature is on, a confirmation email will be sent to employees when they check out from the benefits enrollment experience in Employee self-service.</span></span> |
   | <span data-ttu-id="e4c90-112">**Modello di messaggio di posta elettronica di conferma**</span><span class="sxs-lookup"><span data-stu-id="e4c90-112">**Confirmation email template**</span></span> | <span data-ttu-id="e4c90-113">Selezionare il modello di posta elettronica dell'organizzazione da utilizzare quando si invia la conferma di registrazione.</span><span class="sxs-lookup"><span data-stu-id="e4c90-113">Select the organization email template to use when sending the enrollment confirmation.</span></span> <span data-ttu-id="e4c90-114">Se non si seleziona un modello, verrà inviata il seguente messaggio di posta elettronica generico:</span><span class="sxs-lookup"><span data-stu-id="e4c90-114">If you don't select a template, the following generic email will be sent:</span></span><br><br><span data-ttu-id="e4c90-115">%EmployeeFirstName%,</span><span class="sxs-lookup"><span data-stu-id="e4c90-115">%EmployeeFirstName%,</span></span><br><br><span data-ttu-id="e4c90-116">Congratulazioni.</span><span class="sxs-lookup"><span data-stu-id="e4c90-116">Congratulations!</span></span> <span data-ttu-id="e4c90-117">L'iscrizione ai benefit è stata completata.</span><span class="sxs-lookup"><span data-stu-id="e4c90-117">You’ve successfully completed benefits enrollment.</span></span><br><br><span data-ttu-id="e4c90-118">Grazie,</span><span class="sxs-lookup"><span data-stu-id="e4c90-118">Thank you,</span></span><br><span data-ttu-id="e4c90-119">Benefit di <Nome azienda/Organizzazione>.</span><span class="sxs-lookup"><span data-stu-id="e4c90-119"><Company/Org name> Benefits.</span></span> |
   | <span data-ttu-id="e4c90-120">**Indirizzo mittente di posta elettronica predefinito**</span><span class="sxs-lookup"><span data-stu-id="e4c90-120">**Default email sender address**</span></span> | <span data-ttu-id="e4c90-121">L'indirizzo di posta elettronica da utilizzare quando si invia il messaggio di posta elettronica di conferma.</span><span class="sxs-lookup"><span data-stu-id="e4c90-121">The email address to use when sending the confirmation email.</span></span> |

3. <span data-ttu-id="e4c90-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e4c90-122">Select **Save**.</span></span>