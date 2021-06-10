---
title: Il client si disconnette
description: In questo articolo viene illustrato come procedere se il cliente viene disconnesso dall'ambiente e non sa il motivo.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fcb7e5e3230aee9f6c04e4854c8eea836ae14c7f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053421"
---
# <a name="client-disconnects"></a>Il client si disconnette

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Dettagli ambiente** 

Questo problema può verificarsi in tutti gli ambienti.
 
**Sintomo** 

Il cliente viene disconnesso dall'ambiente e non sa il motivo. Il cliente riceve uno dei seguenti messaggi di errore:

- La connessione è stata persa. Fare clic su Chiudi per continuare a lavorare.
- Connettività di rete persa. Fare clic su Riprova per riprovare.

**Flag rosso**

Questo problema si verifica in genere quando gli utenti nella fase di implementazione confrontano informazioni negli ambienti di produzione e test e dimenticano che si spostano da una sessione all'altra. Se gli utenti sono in questa fase, molto probabilmente avranno questo problema.

**Problema** 

**Tipi di browser:** Google Chrome, Internet Explorer e Microsoft Edge

Microsoft Dynamics 365 Human Resources disconnette gli utenti quando due differenti sessioni sono aperte contemporaneamente per lo stesso utente e lo stesso tipo di browser. Ad esempio, l'utente A sta visualizzando l'ambiente 1 e l'ambiente 2 in Chrome. Non è rilevante se gli utenti aprono differenti finestre di browser o schede. Se le stesse credenziali utente sono utilizzate per accedere contemporaneamente all'ambiente 1 e all'ambiente 2 e nello stesso tipo di browser, Human Resources disconnette una delle sessioni.

**Soluzione**

Assicurarsi che un solo ambiente sia aperto in uno specifico momento per un determinato tipo di browser. Gli utenti possono aprire più sessioni per lo stesso ambiente (ovvero più schede nello stesso browser).

Gli utenti che desiderano accedere a due ambienti contemporaneamente devono aprire ogni ambiente in un tipo di browser diverso. Ad esempio, l'utente A può visualizzare l'ambiente 1 in Chrome e l'ambiente 2 in Microsoft Edge.


[!INCLUDE[footer-include](../includes/footer-banner.md)]