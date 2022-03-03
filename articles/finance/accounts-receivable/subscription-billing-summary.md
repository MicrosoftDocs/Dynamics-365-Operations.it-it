---
title: Informazioni generali sulla fatturazione degli abbonamenti
description: In questo argomento viene descritta la fatturazione degli abbonamenti in Microsoft Dynamics 365 Finance.
author: JodiChristiansen
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustPosting, CustVendExternalItem
audience: Application User
ms.reviewer: twheeloc
ms.custom: 24651
ms.assetid: cb82245e-8c02-429c-b36e-8db0e3e6f7e5
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-02-09
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: b94ac36e49d55ad42909877d77903cd40cb22cbe
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182686"
---
# <a name="subscription-billing-overview"></a>Informazioni generali sulla fatturazione degli abbonamenti

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

La fatturazione degli abbonamenti consente alle organizzazioni di gestire le opportunità di ricavi degli abbonamenti tramite programmi di fatturazione. I modelli complessi di tariffazione e fatturazione e l'allocazione dei ricavi sono facilmente gestiti e vengono fatturati e riconosciuti a livello di linea. L'allocazione dei ricavi ea più elementi consente l'allocazione dei ricavi in conformità con gli standard contabili internazionali (International Financial Reporting Standard 15 \[IFRS 15\]) e gli standard dei principi contabili generalmente accettati (US GAAP) (argomento di codificazione degli standard contabili 606 \[ASC 606\]).

La soluzione prevede tre moduli utilizzabili indipendentemente. In alternativa, tutti e tre i moduli possono essere utilizzati insieme.

- **Fatturazione ricorrente di contratti** – Questo modulo consente la fatturazione ricorrente e la gestione dei prezzi per fornire il controllo su parametri di fatturazione e prezzi, rinnovo del contratto e fatturazione consolidata.
- **Differimenti ricavi e spese** – Questo modulo elimina i processi manuali e la dipendenza da sistemi esterni gestendo i ricavi e consentendo una visione in tempo reale dei ricavi mensili ricorrenti.
- **Allocazione dei ricavi con più elementi** – Questo modulo agevola la conformità ai ricavi gestendo l'allocazione di ricavi e prezzi in più articoli.

La fatturazione degli abbonamenti è abilitata tramite **Gestione funzionalità**. Tuttavia, non può essere utilizzata con la funzionalità **Riconoscimento ricavi**. Pertanto, è necessario disabilitare tale funzionalità prima di abilitare la fatturazione degli abbonamenti.

1. Nell'area di lavoro **Gestione funzionalità**, nella scheda **Tutti**, immettere **Riconoscimento ricavi** nel filtro, quindi selezionare il nome della funzionalità come filtro.
2. Selezionare la funzionalità **Riconoscimento ricavi**, quindi selezionare **Disabilita**.
3. Nel filtro **Nome funzionalità**, immettere **Fatturazione abbonamento**, quindi selezionare il filtro del modulo.
4. Selezionare la funzionalità **Fatturazione abbonamento**, quindi selezionare **Abilita**.
5. Selezionare uno dei tre moduli dall'elenco precedente, quindi selezionare **Abilita**. Ripetere questo passaggio per ognuno degli altri due moduli.

    > [!IMPORTANT]
    > La funzionalità **Fatturazione abbonamento** deve essere abilitata prima di poter abilitare uno qualsiasi dei tre moduli.
