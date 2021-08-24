---
title: Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro
description: È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro.
author: jasongre
ms.date: 06/01/2020
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysUserManagement, SysUserSetup
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c6fe79fe3daca0cf9f6651a6b59c85be80c2f12021b9b7078fd23bf53571a34
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6749462"
---
# <a name="enable-users-to-receive-workflow-related-email-messages"></a>Consentire agli utenti di ricevere messaggi di posta elettronica correlati ai flussi di lavoro

[!include [banner](../../includes/banner.md)]

È possibile configurare il sistema per inviare messaggi di posta elettronica agli utenti quando si verificano eventi correlati ai flussi di lavoro. Ad esempio, i messaggi di posta elettronica possono essere inviati agli utenti quando i documenti vengono loro assegnati per l'approvazione. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Pannello di navigazione > Moduli > Amministrazione sistema > Utenti > Utenti**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nel **riquadro azioni** fare clic su **Opzioni utente**.
4. Fare clic sulla scheda **Flusso di lavoro**. Assicurarsi che la sezione **Notifiche** sia espansa. Nella sezione **Notifiche** è possibile specificare il modo in cui si desidera che l'utente riceva la notifica circa gli eventi correlati ai flussi di lavoro.  
5. Nel campo **Tipo di notifica del flusso di lavoro voci**, selezionare un'opzione.
    - Raggruppato: notifiche per voci raggruppate in un unico messaggio di posta elettronica.
    - Singolo: viene inviato un messaggio di posta elettronica per ogni voce.  
    - Se si desidera che l'utente riceva notifiche nel client, selezionare la casella di controllo **Invia notifiche tramite posta elettronica**.  
6. Fare clic su **Salva**.
7. Chiudere la pagina.

> [!NOTE]
> I modelli di messaggio di posta elettronica per il flusso di lavoro verranno forniti da modelli di messaggio di posta elettronica del sistema o modelli di messaggio di posta elettronica dell'organizzazione a seconda che il flusso di lavoro sia un flusso di lavoro a livello di sistema (non specifico dell'azienda) o a livello di organizzazione (specifico dell'azienda).


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]