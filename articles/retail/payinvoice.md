---
title: Configurare scenari di pagamento delle fatture
description: In questo argomento viene descritto come configurare Dynamics 365 for Retail per supportare vari scenari di pagamento delle fatture.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b7132dc9b3c78fa04fcfc38ea72b5678ad08deb2
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564972"
---
# <a name="set-up-pay-invoice-scenarios"></a><span data-ttu-id="afbc7-103">Configurare scenari di pagamento delle fatture</span><span class="sxs-lookup"><span data-stu-id="afbc7-103">Set up pay invoice scenarios</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="afbc7-104">La funzionalità Paga fattura in Dynamics 365 for Retail è stata espansa in modo da supportare:</span><span class="sxs-lookup"><span data-stu-id="afbc7-104">The Pay invoice functionality in Dynamics 365 for Retail has been expanded to support:</span></span>

- <span data-ttu-id="afbc7-105">Il pagamento di più fatture di ordini cliente in un'unica transazione POS.</span><span class="sxs-lookup"><span data-stu-id="afbc7-105">Payoff of multiple sales order invoices in a single POS transaction.</span></span>
- <span data-ttu-id="afbc7-106">Il pagamento di vari tipi di fattura cliente incluse le fatture a testo libero, le fatture basate su progetto e le note di accredito.</span><span class="sxs-lookup"><span data-stu-id="afbc7-106">Payment of various customer invoice types including free text invoices, project-based invoices, and credit notes.</span></span>

<span data-ttu-id="afbc7-107">Per attivare questi scenari, il profilo della funzionalità per i punti vendita deve essere configurato come illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="afbc7-107">To enable these scenarios, the functionality profile for stores must be configured as outlined in below.</span></span>

1. <span data-ttu-id="afbc7-108">Accedere a **Vendita al dettaglio \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità** e selezionare un profilo collegato ai punti vendita che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="afbc7-108">Go to **Retail \> Channel setup \> POS setup \> POS profiles \> Functionality profiles** and select a profile that's linked to the stores that you want to make the changes for.</span></span>
2. <span data-ttu-id="afbc7-109">Nella scheda **Funzioni**, configurare i seguenti parametri in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="afbc7-109">On the **Functions** tab, configure the following parameters as needed.</span></span>

    - <span data-ttu-id="afbc7-110">**Fattura ordine cliente**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture basate sugli ordini cliente in un'unica transazione POS.</span><span class="sxs-lookup"><span data-stu-id="afbc7-110">**Sales order invoice** – Select **Yes** to allow users to pay one or more sales order-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="afbc7-111">**Fattura a testi libero**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture a testo libero in un'unica transazione POS.</span><span class="sxs-lookup"><span data-stu-id="afbc7-111">**Free text invoice** – Select **Yes** to allow users to pay one or more free text-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="afbc7-112">**Fattura progetto**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture progetto in un'unica transazione POS.</span><span class="sxs-lookup"><span data-stu-id="afbc7-112">**Project invoice** – Select **Yes** to allow users to pay one or more project-based invoices in a single POS transaction.</span></span>
    - <span data-ttu-id="afbc7-113">**Ordine cliente - Nota di accredito**: selezionare **Sì** per consentire agli utenti di liquidare più note di accredito basate su ordini cliente a fronte di fatture aperte o elaborare un rimborso al cliente per una nota di accredito aperta.</span><span class="sxs-lookup"><span data-stu-id="afbc7-113">**Sales order credit note** – Select **Yes** to allow users to settle multiple sales order-based credit notes against open invoices or process a refund to the customer for an open credit note.</span></span>

> [!NOTE]
> <span data-ttu-id="afbc7-114">Il pagamento o la liquidazione di importi parziali non è supportato.</span><span class="sxs-lookup"><span data-stu-id="afbc7-114">Payment or settlement of partial amounts is not yet supported.</span></span>
