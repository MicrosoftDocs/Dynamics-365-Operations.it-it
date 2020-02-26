---
title: Configurare scenari di pagamento delle fatture
description: In questo argomento viene descritto come configurare Dynamics 365 Commerce per supportare vari scenari di pagamento delle fatture.
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
ms.openlocfilehash: 9fe8fde32549568812a724311781d3515ef7036c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004414"
---
# <a name="set-up-pay-invoice-scenarios"></a>Configurare scenari di pagamento delle fatture

[!include [banner](includes/banner.md)]

La funzionalità Paga fattura in Dynamics 365 Commerce è stata espansa in modo da supportare:

- Il pagamento di più fatture di ordini cliente in un'unica transazione POS.
- Il pagamento di vari tipi di fattura cliente incluse le fatture a testo libero, le fatture basate su progetto e le note di accredito.

Per attivare questi scenari, il profilo della funzionalità per i punti vendita deve essere configurato come illustrato di seguito.

1. Accedere a **Retail e Commerce \> Impostazione canale \> Impostazioni POS \> Profili POS \> Profili funzionalità** e selezionare un profilo collegato ai punti vendita che si desidera modificare.
2. Nella scheda **Funzioni**, configurare i seguenti parametri in base alle esigenze.

    - **Fattura ordine cliente**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture basate sugli ordini cliente in un'unica transazione POS.
    - **Fattura a testi libero**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture a testo libero in un'unica transazione POS.
    - **Fattura progetto**: selezionare **Sì** per consentire agli utenti di pagare una o più fatture progetto in un'unica transazione POS.
    - **Ordine cliente - Nota di accredito**: selezionare **Sì** per consentire agli utenti di liquidare più note di accredito basate su ordini cliente a fronte di fatture aperte o elaborare un rimborso al cliente per una nota di accredito aperta.

> [!NOTE]
> Il pagamento o la liquidazione di importi parziali non è supportato.
