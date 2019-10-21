---
title: Abilitare il calcolo IVA differito nel giornale di registrazione
description: In questo argomento viene descritto come utilizzare la funzionalità **Abilita calcolo IVA differito nel giornale di registrazione** per migliorare le prestazioni di calcolo dell'IVA quando il volume delle righe del giornale di registrazione è enorme.
author: ericwang
manager: Ann Beebe
ms.date: 09/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 5a8ae30a007d3e2b8b7a9bc9eb7786f6e58246d0
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178432"
---
# <a name="enable-delayed-tax-calculation-on-journal"></a>Abilitare il calcolo IVA differito nel giornale di registrazione
[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

In questo argomento viene descritto come utilizzare la funzionalità **Abilita calcolo IVA differito nel giornale di registrazione** per migliorare le prestazioni di calcolo dell'IVA quando il volume delle righe del giornale di registrazione è enorme.

Il comportamento corrente del calcolo dell'IVA nel giornale di registrazione è attivato in tempo reale quando l'utente aggiorna i campi relativi all'IVA, ad esempio Fascia IVA/Fascia IVA articoli. Qualsiasi aggiornamento a livello di riga del giornale di registrazione ricalcolerà l'importo IVA in tutte le righe del giornale di registrazione. Ciò consente all'utente di ottenere il calcolo dell'importo IVA in tempo reale ma può anche generare un problema di prestazioni se il volume delle righe del giornale di registrazione è enorme.

Questa funzionalità fornisce un'opzione per differire il calcolo dell'IVA e risolvere il problema di prestazioni. Se questa funzionalità è attivata, l'importo IVA verrà calcolato solo quando l'utente fa clic sul comando "IVA" o registra il giornale di registrazione.

L'utente può attivare/disattivare il parametro a tre livelli:
- In base all'entità giuridica
- In base al nome del giornale di registrazione
- In base all'intestazione del giornale di registrazione

Il sistema considererà il valore del parametro nell'intestazione del giornale di registrazione come finale. Per impostazione predefinita, il valore del parametro nell'intestazione del giornale di registrazione è il nome del giornale di registrazione. Per impostazione predefinita, il valore del parametro nel nome del giornale di registrazione è il parametro di contabilità generale quando il nome del giornale di registrazione viene creato.

I campi "Importo IVA effettiva" e "Importo IVA calcolato" nel giornale di registrazione non saranno visibili se questo parametro è abilitato. Lo scopo è di non confondere l'utente in quanto il valore di questi due campi sarà sempre pari a 0 prima che l'utente attivi il calcolo dell'IVA.

## <a name="enable-delayed-tax-calculation-by-legal-entity"></a>Abilitare il calcolo IVA differito in base alla persona giuridica

1. Selezionare **Contabilità generale > Impostazione contabilità generale > Parametri di contabilità generale**.
2. Fare clic sulla scheda **Fascia IVA**.
3. Nella Scheda dettaglio **Generale**, individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo

![](media/delayed-tax-calculation-gl.png)



## <a name="enable-delayed-tax-calculation-by-journal-name"></a>Abilitare il calcolo IVA differito in base al nome del giornale di registrazione

1. Selezionare **Contabilità generale > Impostazione giornale di registrazione > Nomi giornale di registrazione**.
2. Nella Scheda dettaglio **Generale**, individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo

![](media/delayed-tax-calculation-journal-name.png)

## <a name="enable-delayed-tax-calculation-by-journal"></a>Abilitare il calcolo IVA differito in base al giornale di registrazione

1. Selezionare **Contabilità generale > Scritture contabili > Giornali di registrazione generali**.
2. Fare clic su **Nuovo**.
3. Selezionare un nome di giornale di registrazione.
4. Fare clic su **Imposta**.
5. Individuare il parametro **Calcolo IVA differito** e attivarlo/disattivarlo.

![](media/delayed-tax-calculation-journal-header.png)
