---
title: Archiviare le fatture cliente stampate con numeri hash
description: In questo argomento viene descritto come abilitare l'archiviazione per archiviare le fatture cliente stampate con numeri hash.
author: ilyako
manager: AnnBe
ms.date: 03/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: ilyako
ms.search.validFrom: 2021-03-05
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: d502ec5d286573c72e207419b66f283183009c09
ms.sourcegitcommit: 08ac570bece3e4ee4a0f632f51623e328536dfcf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2021
ms.locfileid: "5557482"
---
# <a name="archive-printed-customer-invoices-with-hash-numbers"></a><span data-ttu-id="65770-103">Archiviare le fatture cliente stampate con numeri hash</span><span class="sxs-lookup"><span data-stu-id="65770-103">Archive printed customer invoices with hash numbers</span></span>

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

<span data-ttu-id="65770-104">In alcuni paesi, esiste un requisito legale per memorizzare i numeri hash calcolati nel sistema insieme alla stampa di alcuni documenti.</span><span class="sxs-lookup"><span data-stu-id="65770-104">In some countries, there is a legal requirement to store calculated hash numbers in the system together with printouts of some documents.</span></span> <span data-ttu-id="65770-105">I numeri hash possono essere utilizzati per il reporting alle autorità e durante gli audit.</span><span class="sxs-lookup"><span data-stu-id="65770-105">Hash numbers can be used for reporting to authorities and during audits.</span></span>

<span data-ttu-id="65770-106">In questo argomento viene descritto come configurare l'archiviazione per archiviare fatture cliente stampate con numeri hash.</span><span class="sxs-lookup"><span data-stu-id="65770-106">This topic explains how to configure archiving in order to store printed customer invoices with hash numbers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="65770-107">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="65770-107">Prerequisites</span></span>

- <span data-ttu-id="65770-108">Nell'area di lavoro **Gestione funzionalità**, attivare la funzionalità **Archivia fatture cliente stampate con numeri hash**.</span><span class="sxs-lookup"><span data-stu-id="65770-108">In the **Feature management** workspace, turn on the feature, **Archive printed customer invoices with hash numbers**.</span></span> <span data-ttu-id="65770-109">Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="65770-109">For more information, see [Feature management overview](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).</span></span>
- <span data-ttu-id="65770-110">Configurare i formati stampabili dei documenti necessari in **Gestione stampa**.</span><span class="sxs-lookup"><span data-stu-id="65770-110">Configure the printable formats of required documents in **Print management**.</span></span>

<span data-ttu-id="65770-111">Questa funzionalità è applicabile ai seguenti documenti.</span><span class="sxs-lookup"><span data-stu-id="65770-111">This functionality is applicable to the following documents.</span></span>

<span data-ttu-id="65770-112">**Contabilità clienti**</span><span class="sxs-lookup"><span data-stu-id="65770-112">**Accounts receivable**</span></span>
- <span data-ttu-id="65770-113">Fattura cliente</span><span class="sxs-lookup"><span data-stu-id="65770-113">Customer invoice</span></span>
- <span data-ttu-id="65770-114">Nota di credito cliente</span><span class="sxs-lookup"><span data-stu-id="65770-114">Customer credit note</span></span>
- <span data-ttu-id="65770-115">Fattura a testo libero</span><span class="sxs-lookup"><span data-stu-id="65770-115">Free text invoice</span></span>
- <span data-ttu-id="65770-116">Nota di accredito a testo libero</span><span class="sxs-lookup"><span data-stu-id="65770-116">Free text credit note</span></span>

<span data-ttu-id="65770-117">**Gestione progetti e contabilità**</span><span class="sxs-lookup"><span data-stu-id="65770-117">**Project management and accounting**</span></span>
- <span data-ttu-id="65770-118">Fattura progetto</span><span class="sxs-lookup"><span data-stu-id="65770-118">Project invoice</span></span>
- <span data-ttu-id="65770-119">Nota di accredito progetto</span><span class="sxs-lookup"><span data-stu-id="65770-119">Project credit note</span></span>

## <a name="configure-customer-master-data"></a><span data-ttu-id="65770-120">Configurare i dati master dei clienti</span><span class="sxs-lookup"><span data-stu-id="65770-120">Configure customer master data</span></span>
<span data-ttu-id="65770-121">Completare i seguenti passaggi per configurare i dati del cliente e attivare la possibilità di salvare automaticamente le fatture stampate come allegati.</span><span class="sxs-lookup"><span data-stu-id="65770-121">Complete the following steps to configure customer data and turn on the ability to automatically save printed invoices as attachments.</span></span>

1. <span data-ttu-id="65770-122">Selezionare **Contabilità clienti** > **Tutti i clienti**.</span><span class="sxs-lookup"><span data-stu-id="65770-122">Go to **Accounts receivable** > **All customers**.</span></span> 
2. <span data-ttu-id="65770-123">Seleziona un cliente e nella Scheda dettaglio **Fattura e consegna**, nella sezione **FATTURA ELETTRONICA**, nel campo **Allegato fattura elettronica**, selezionare **Sì**.</span><span class="sxs-lookup"><span data-stu-id="65770-123">Select a customer, and on the **Invoice and delivery** FastTab, in the **E-INVOCE** section, in the **eInvoice attachment** field, select **Yes**.</span></span>

## <a name="print-invoices"></a><span data-ttu-id="65770-124">Stampare fatture</span><span class="sxs-lookup"><span data-stu-id="65770-124">Print invoices</span></span>
<span data-ttu-id="65770-125">È possibile registrare e stampare qualsiasi nota di accredito o fattura a testo libero, cliente e di progetto per il cliente configurato nella procedura precedente.</span><span class="sxs-lookup"><span data-stu-id="65770-125">You can post and print any free text, customer, and project invoice or credit note for the customer configured in the previous procedure.</span></span>

<span data-ttu-id="65770-126">Aprire la pagina **Allegati** per la fattura stampata.</span><span class="sxs-lookup"><span data-stu-id="65770-126">Open the **Attachments** page for the printed invoice.</span></span> <span data-ttu-id="65770-127">Nella Scheda dettaglio **Allegato**, nel gruppo di campi **Dettagli aggiuntivi**, nel campo **Numero hash documento** trovare il numero hash memorizzato calcolato per la fattura stampata.</span><span class="sxs-lookup"><span data-stu-id="65770-127">On the **Attachment** FastTab, in the **Additional details** field group, in **Document hash number** field, find the stored hash number calculated for the printed invoice.</span></span>

![Numero hash allegato](media/attach-hash-num.jpg)

