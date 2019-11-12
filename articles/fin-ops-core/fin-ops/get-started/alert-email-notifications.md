---
title: Notifiche di avviso client tramite posta elettronica
description: In questo argomento vengono fornite informazioni su come impostare le regole per l'invio di notifiche tramite posta elettronica quando si verificano eventi predefiniti.
author: tjvass
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2019-1-29
ms.dyn365.ops.version: Platform update 24
ms.openlocfilehash: ba92c3dc1debed7e98210168d1a135e2cf567aec
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2191295"
---
# <a name="client-alert-notifications-by-email"></a>Notifiche di avvisi client tramite e-mail

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

È possibile definire regole di avviso personalizzate che monitorano visualizzazioni di dati filtrate e inviano notifiche tramite posta elettronica quando si verificano eventi predefiniti. L'opzione per inviare notifiche tramite posta elettronica è disponibile per tutti i tipi di avviso supportati e può anche essere attivata per le regole di avviso esistenti.

È possibile utilizzare controlli incorporati per creare regole di avviso che controllano le visualizzazioni filtrate di processi batch di sistema. Mediante il monitoraggio del valore del campo **Stato**, è anche possibile configurare regole di avviso che inviano messaggi di posta elettronica quando un processo batch non riesce. Dopo la creazione di tali regole di avviso, non è più necessario controllare i report per eventuali modifiche ai dati aziendali. In alternativa, è possibile effettuare il monitoraggio mediante il servizio di rilevamento delle modifiche intelligente.

Gli avvisi client dipendono dal sottosistema di posta elettronica fornito mediante l'integrazione con Microsoft Office. Si consiglia di utilizzare il provider SMTP (Simple Mail Transfer Protocol), di modo che la distribuzione della posta elettronica non utilizzi un client di posta elettronica locale.

Per inviare notifiche tramite posta elettronica, i clienti devono configurare servizi di posta elettronica integrati. Le notifiche tramite posta elettronica sono inviate ai destinatari per conto dei proprietari degli avvisi.

Per ulteriori informazioni su come configurare la posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../organization-administration/configure-email.md).

L'immagine seguente illustra la finestra di dialogo **Crea regola di avviso**, che ora include un'opzione **Invia posta elettronica**.

[![Finestra di dialogo Crea regola di avviso in cui l'opzione Invia posta elettronica è impostata su Sì](./media/Create-alert-rule-form.png)](./media/Create-alert-rule-form.png)

> [!NOTE]
> Quando l'opzione **Invia posta elettronica** è impostata su **Sì**, le notifiche di avviso continueranno a essere consegnate al centro azioni.

## <a name="alert-notification-email-templates"></a>Modelli di messaggio di posta elettronica per notifiche di avviso

Il servizio invia notifiche tramite posta elettronica utilizzando modelli di messaggio di posta elettronica predefiniti che consegnano dettagli di base della notifica di avviso.

Nell'immagine seguente viene illustrata la struttura delle notifiche di avviso ricevute tramite posta elettronica.

[![Notifiche di avviso basate su modelli per la creazione di record, le modifiche ai campi e l'eliminazione di modelli](./media/Alert-email-templates.png)](./media/Alert-email-templates.png)