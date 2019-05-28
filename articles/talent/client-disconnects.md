---
title: Disconnessione del client Talent
description: In questo argomento viene illustrato come procedere se il cliente viene disconnesso dal relativo ambiente e non sa il motivo.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 885e2d743cd2b01588546327840508f6f7e95958
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1518329"
---
# <a name="talent-client-disconnects"></a>Disconnessione del client Talent

[!include [banner](includes/banner.md)]

**Dettagli ambiente** 

Questo problema può verificarsi in tutti gli ambienti.
 
**Sintomo** 

Il cliente viene disconnesso dal relativo ambiente e non sa il motivo. Il cliente riceve uno dei seguenti messaggi di errore:

- La connessione è stata persa. Fare clic su Chiudi per continuare a lavorare.
- Connettività di rete persa. Fare clic su Riprova per riprovare.

**Flag rosso**

Questo problema si verifica in genere quando gli utenti nella fase di implementazione confrontano informazioni negli ambienti di produzione e test e dimenticano che si spostano da una sessione all'altra. Se gli utenti sono in questa fase, molto probabilmente avranno questo problema.

**Uscita** 

**Tipi di browser:** Google Chrome, Internet Explorer e Microsoft Edge

La piattaforma Microsoft Dynamics 365 for Talent disconnette gli utenti quando due differenti sessioni sono aperte contemporaneamente per lo stesso utente e lo stesso tipo di browser. Ad esempio, l'utente A sta visualizzando l'ambiente 1 e l'ambiente 2 in Chrome. Non è rilevante se gli utenti aprono differenti finestre di browser o schede. Se le stesse credenziali utente sono utilizzate per accedere contemporaneamente all'ambiente 1 e all'ambiente 2 e nello stesso tipo di browser, Talent disconnette una delle sessioni.

**Soluzione**

Assicurarsi che un solo ambiente sia aperto in uno specifico momento per un determinato tipo di browser. Gli utenti possono aprire più sessioni per lo stesso ambiente (ovvero più schede nello stesso browser).

Gli utenti che desiderano accedere a due ambienti contemporaneamente devono aprire ogni ambiente in un tipo di browser diverso. Ad esempio, l'utente A può visualizzare l'ambiente 1 in Chrome e l'ambiente 2 in Microsoft Edge.
