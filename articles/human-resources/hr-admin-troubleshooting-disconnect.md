---
title: Il client si disconnette
description: Questo argomento spiega cosa fare se il cliente è disconnesso dall'ambiente.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b15c5db19f1b07e3d469986ac700138ecb1d1525
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8071137"
---
# <a name="client-disconnects"></a>Il client si disconnette


[!INCLUDE [PEAP](../includes/peap-2.md)]

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
