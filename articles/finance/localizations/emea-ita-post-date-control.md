---
title: Controllo unificato della data di registrazione
description: In questo argomento viene illustrato come configurare il controllo cronologico per le date di registrazione delle fatture.
author: ikond
manager: AnnBe
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: NumberSequenceGroup
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 537707
ms.search.region: Italy
ms.author: ilyako
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 2269c2fa333647c7e2a5c1d3da08f9d1a60f0597
ms.sourcegitcommit: e88c96d1cb817a22db81856cadb563c095ab2671
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/02/2021
ms.locfileid: "5104455"
---
# <a name="unified-posting-date-control"></a>Controllo unificato della data di registrazione

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

In questo argomento viene illustrato come configurare il controllo cronologico delle date di registrazione delle fatture all'interno di una specifica sezione del libro IVA.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- I libri e le sezioni IVA italiani sono configurati nel sistema. Per ulteriori informazioni, vedere [Libri IVA italiani](emea-ita-fiscal-books.md).
- Nell'area di lavoro Gestione funzionalità, attiva la funzionalità **Controllo unificato della data di registrazione (Italia)**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-posting-date-control"></a>Configurare il controllo unificato della registrazione
Completa i seguenti passaggi per configurare il controllo della data di registrazione.

1. Vai a **Imposta** > **Impostazione** > **IVA** > **Sezioni libro IVA italiano**. 
2. Nella colonna **Ignora controllo data di registrazione** seleziona se il controllo della data di registrazione è necessario per una sezione del libro IVA selezionata.

![Controllo della data di registrazione](media/emea-ita-post-date-control.jpg)

 - Se il campo non è abilitato, che è l'opzione predefinita, il sistema non consente la registrazione di nuove fatture con date precedenti alla data dell'ultima fattura registrata.  
 - Se il campo è abilitato, il sistema consente la registrazione con qualsiasi data.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]