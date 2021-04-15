---
title: Profili registrazione configurabili per banche e tipi di rimessa
description: Questo argomento fornisce informazioni su come configurare i profili di registrazione per banche e tipi di rimesse.
author: ilkond
ms.date: 03/09/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: 44ec0629e9a32dad63d6864eb8d552fe287284fd
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814944"
---
# <a name="configurable-posting-profiles-for-banks-and-remittance-types"></a><span data-ttu-id="0b5d6-103">Profili registrazione configurabili per banche e tipi di rimessa</span><span class="sxs-lookup"><span data-stu-id="0b5d6-103">Configurable posting profiles for banks and remittance types</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0b5d6-104">Oltre a definire le impostazioni di funzionalità generali, è possibile impostare diversi profili di registrazione per la rimessa di un effetto attivo (rimessa per incasso e rimessa per sconto) e la rimessa di un effetto passivo nei conti bancari dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-104">In addition to defining general functionality settings, you can set up different posting profiles for the remittance of a bill of exchange (remit for collection and remit for discount) and the remittance of a promissory note in company bank accounts.</span></span> <span data-ttu-id="0b5d6-105">Per ulteriori informazioni, vedere [Impostare gli effetti attivi](../accounts-receivable/set-up-bills-exchange.md).</span><span class="sxs-lookup"><span data-stu-id="0b5d6-105">For more information, see [Set up bills of exchange](../accounts-receivable/set-up-bills-exchange.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b5d6-106">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="0b5d6-106">Prerequisites</span></span>

<span data-ttu-id="0b5d6-107">Prima di poter utilizzare diversi profili di registrazione per la rimessa di un effetto attivo e la rimessa di un effetto passivo nei conti bancari della società, devono essere soddisfatti i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="0b5d6-107">Before you can use different posting profiles for the remittance of a bill of exchange and the remittance of a promissory note in company bank accounts, the following prerequisites must be met:</span></span>

- <span data-ttu-id="0b5d6-108">L'indirizzo principale della persona giuridica deve essere in Italia.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-108">The primary address of the legal entity must be in Italy.</span></span>
- <span data-ttu-id="0b5d6-109">La funzionalità **Profili di registrazione configurabili per banche e tipi di rimesse** deve essere attivata nell'area di lavoro **Gestione funzionalità**.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-109">The **Configurable posting profiles for banks and remittance types** feature must be turned on in the **Feature management** workspace.</span></span> <span data-ttu-id="0b5d6-110">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="0b5d6-110">For more information, see [Feature management overview](../../fin-and-ops/get-started/feature-management/feature-management-overview.md).</span></span>

## <a name="set-up-a-posting-profile-for-a-remittance-journal-line-offset-account"></a><span data-ttu-id="0b5d6-111">Impostare un profilo di registrazione per un conto di contropartita della riga del giornale di registrazione rimesse</span><span class="sxs-lookup"><span data-stu-id="0b5d6-111">Set up a posting profile for a remittance journal line offset account</span></span>

<span data-ttu-id="0b5d6-112">Per impostare i profili di registrazione, è necessario aprire un conto bancario aziendale.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-112">To set up posting profiles, you must open a company bank account.</span></span> <span data-ttu-id="0b5d6-113">Quando il sistema registra un effetto attivo o un effetto passivo nel giornale di registrazione rimesse, utilizza i profili di registrazione nelle righe giornale di registrazione rimesse per un conto di contropartita.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-113">When the system posts a bill of exchange or a promissory note remittance journal, it will use the posting profiles on remittance journal lines for an offset account.</span></span>

1. <span data-ttu-id="0b5d6-114">Per impostare il profilo di pubblicazione, andare a **Gestione cassa e banche** \> **Conti bancari** \> **Conti bancari**.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-114">To set up the posting profile, go to **Cash and bank management** \> **Bank accounts** \> **Bank accounts**.</span></span>
2. <span data-ttu-id="0b5d6-115">Nella scheda dettaglio **Generale**, nella sezione **Profili di registrazione**, nei campi **Rimessa per incasso**, **Rimessa per sconto** e **Rimessa effetto passivo**, selezionare un profilo di registrazione, come richiesto.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-115">On the **General** FastTab, in the **Posting profiles** section, in the **Remit for collection**, **Remit for discount**, and **Remit promissory note** fields, select a posting profile, as you require.</span></span>

![Impostazione del conto bancario](media/emea-ita-exil-different-accounts-per-company-bank.png)

## <a name="use-posting-profiles-in-remittance-journal-posting"></a><span data-ttu-id="0b5d6-117">Utilizzare i profili di registrazione nella registrazione del giornale di registrazione rimesse</span><span class="sxs-lookup"><span data-stu-id="0b5d6-117">Use posting profiles in remittance journal posting</span></span>

<span data-ttu-id="0b5d6-118">Se i profili di registrazione sono stati impostati nel conto bancario, il sistema li utilizzerà per specificare il conto di contropartita quando viene registrato un giornale di registrazione rimesse.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-118">If posting profiles have been set up in the bank account, the system will use them to specify the offset account when a remittance journal is posted.</span></span> <span data-ttu-id="0b5d6-119">Se i profili di registrazione non sono stati impostati, il sistema seleziona il profilo di registrazione nella scheda **Contabilità generale e IVA** delle pagine **Parametri contabilità clienti** e **Parametri contabilità fornitori**.</span><span class="sxs-lookup"><span data-stu-id="0b5d6-119">If posting profiles haven't been set up, the system selects the posting profile from the **Ledger and sales tax** tab on the **Accounts receivable parameters** and **Accounts payable parameters** pages.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]