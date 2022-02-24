---
title: Abilitare il calcolo IVA differito nei giornali di registrazione
description: In questo argomento viene descritto come attivare la funzionalità del calcolo IVA differito per migliorare le prestazioni di calcolo dell'IVA quando il numero delle righe del giornale di registrazione è molto elevato.
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
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2019-09-18
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: 4ea79747e8e7c078baa6e270ecebf88c4832e079
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968806"
---
# <a name="enable-delayed-tax-calculation-on-journals"></a>Abilitare il calcolo IVA differito nei giornali di registrazione
[!include [banner](../includes/banner.md)]


In questo argomento viene descritto come è possibile effettuare il calcolo IVA dei giornali di registrazione. Questa funzionalità consente di migliorare le prestazioni dei calcoli IVA quando sono presenti molte righe del giornale di registrazione.

Per impostazione predefinita, gli importi IVA nelle righe del giornale di registrazione vengono calcolati quando i campi relativi all'IVA vengono aggiornati. Tra questi campi sono inclusi i campi delle fasce IVA e delle fasce IVA articoli. Qualsiasi aggiornamento a una riga del giornale di registrazione comporta il ricalcolo degli importi IVA per tutte le righe del giornale di registrazione. Sebbene questo comportamento aiuti l'utente a visualizzare gli importi IVA calcolati in tempo reale, può anche influire sulle prestazioni se il numero di righe del giornale di registrazione è molto elevato.

La funzionalità Calcolo IVA differito consente di posticipare il calcolo IVA nei giornali di registrazione e in modo da ovviare ai problemi relativi alle prestazioni. Quando questa funzionalità è attivata, gli importi IVA vengono calcolati solo quando un utente seleziona **IVA** o registra il giornale di registrazione.

È possibile ritardare il calcolo dell'IVA a tre livelli:

- Persona giuridica
- Nome giornale di registrazione
- Intestazione giornale di registrazione

Il sistema assegna la priorità all'impostazione dell'intestazione del giornale di registrazione. Per impostazione predefinita, questa impostazione viene ricavata dal nome del giornale di registrazione. Per impostazione predefinita, l'impostazione del nome del giornale di registrazione viene ricavata dall'impostazione della pagina **Parametri di contabilità generale** quando il nome del giornale di registrazione viene creato. Nelle seguenti sezioni viene descritto come abilitare il calcolo IVA differito per le persone giuridiche, i nomi dei giornali di registrazione e le intestazioni dei giornali di registrazione.

## <a name="turn-on-delayed-tax-calculation-at-the-legal-entity-level"></a>Attivare il calcolo IVA differito a livello di persona giuridica

1. Passare a **Contabilità generale \> Impostazione contabilità generale \> Parametri di contabilità generale**.
2. Nella scheda **IVA**, nella scheda dettaglio **Generale**, impostare l'opzione **Calcolo IVA differito** su **Sì**.

![Immagine dei parametri di contabilità generale](media/delayed-tax-calculation-gl.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-name-level"></a>Attivare il calcolo IVA differito a livello di nome del giornale di registrazione

1. Passare a **Contabilità generale \> Impostazione giornale di registrazione \> Nomi giornale di registrazione**.
2. Nella scheda dettaglio **Generale**, nella sezione **IVA**, impostare l'opzione **Calcolo IVA differito** su **Sì**.

![Immagine dei nomi del giornale di registrazione](media/delayed-tax-calculation-journal-name.png)

## <a name="turn-on-delayed-tax-calculation-at-the-journal-header-level"></a>Attivare il calcolo IVA differito a livello di intestazione del giornale di registrazione

1. Fare clic su **Contabilità generale \> Inserimenti nel giornale di registrazione \> Giornali di registrazione generali**.
2. Selezionare **Nuovo**.
3. Selezionare un nome di giornale di registrazione.
4. Nella scheda **Impostazione**, impostare l'opzione **Calcolo IVA differito** **Sì**.

![Immagine della pagina del giornale di registrazione generale](media/delayed-tax-calculation-journal-header.png)
