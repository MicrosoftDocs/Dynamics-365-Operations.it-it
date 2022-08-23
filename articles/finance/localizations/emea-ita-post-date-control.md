---
title: Controllo unificato della data di registrazione
description: In questo articolo viene illustrato come configurare il controllo cronologico per le date di registrazione delle fatture.
author: mrolecki
ms.date: 02/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Italy
ms.author: mrolecki
ms.search.validFrom: 2021-03-15
ms.dyn365.ops.version: 10.0.17
ms.custom: 537707
ms.search.form: NumberSequenceGroup
ms.openlocfilehash: 2785b37ab7250d9515beee32929f9dff478df731
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272119"
---
# <a name="unified-posting-date-control"></a>Controllo unificato della data di registrazione

[!include [banner](../includes/banner.md)]


In questo articolo viene illustrato come configurare il controllo cronologico delle date di registrazione delle fatture all'interno di una specifica sezione del libro IVA.

## <a name="prerequisites"></a>Prerequisiti

- L'indirizzo principale della persona giuridica deve essere in Italia.
- I libri e le sezioni IVA italiani sono configurati nel sistema. Per ulteriori informazioni, vedere [Libri IVA italiani](emea-ita-fiscal-books.md).
- Nell'area di lavoro Gestione funzionalità, attiva la funzionalità **Controllo unificato della data di registrazione (Italia)**. Per ulteriori informazioni, vedere [Panoramica della gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="configure-posting-date-control"></a>Configurare il controllo unificato della registrazione
Completa i seguenti passaggi per configurare il controllo della data di registrazione.

1. Vai a **Imposta** > **Impostazione** > **IVA** > **Sezioni libro IVA italiano**. 
2. Nella colonna **Ignora controllo data di registrazione** seleziona se il controllo della data di registrazione è necessario per una sezione del libro IVA selezionata.

![Controllo della data di registrazione.](media/emea-ita-post-date-control.jpg)

 - Se il campo non è abilitato, che è l'opzione predefinita, il sistema non consente la registrazione di nuove fatture con date precedenti alla data dell'ultima fattura registrata.  
 - Se il campo è abilitato, il sistema consente la registrazione con qualsiasi data.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
