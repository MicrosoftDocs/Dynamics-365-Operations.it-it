---
title: Impostare un profilo di notifica tramite posta elettronica
description: In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413369"
---
# <a name="set-up-an-email-notification-profile"></a>Impostare un profilo di notifica tramite posta elettronica


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare un profilo di notifica tramite posta elettronica in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Prima di creare canali, è consigliabile impostare un profilo per garantire l'invio di notifiche tramite posta elettronica per vari eventi, come la creazione di ordini, lo stato della spedizione dell'ordine e il mancato pagamento.

Per ulteriori informazioni di configurazione della posta elettronica, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Creare un profilo di notifica tramite posta elettronica

Per creare un profilo di notifica tramite posta elettronica, attenersi alla seguente procedura.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.
1. Fare clic su **Nuovo** nel riquadro azioni.
1. Nel campo **Profilo di notifica tramite posta elettronica**, immettere un nome per identificare il profilo.
1. Nel campo **Descrizione** immettere una descrizione pertinente.
1. Impostare **Attivo** su **Sì**.

### <a name="create-an-email-template"></a>Crea un modello di messaggio di posta elettronica

Prima di poter creare una notifica tramite posta elettronica, è necessario creare un modello e-mail per l'organizzazione che contenga le informazioni di posta elettronica del mittente e il modello e-mail.

Per creare un modello e-mail attenersi alla procedura seguente.

1. Nel pannello di navigazione, selezionare **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Parametri \> Modelli di posta elettronica a livello di organizzazione**.
1. Nel Riquadro azioni selezionare **Nuovo**.
1. Nel campo **ID posta elettronica**, immettere un ID per facilitare l'identificazione di questo modello.
1. Nel campo **Nome mittente** immettere il nome del mittente.
1. Nel campo **Descrizione messaggio di posta elettronica** immettere una descrizione pertinente.
1. Nel campo **Indirizzo di posta elettronica del mittente** immettere l'indirizzo di posta elettronica del mittente.
1. Nella sezione **Generale**, immettere tutte le informazioni facoltative necessarie (come la priorità di posta elettronica).
1. Espandere la sezione **Contenuto messaggio posta elettronica** e selezionare **Nuovo** per creare il contenuto del modello. Per ogni elemento di contenuto, selezionare la lingua e fornire la riga dell'oggetto dell'e-mail. Se l'e-mail avrà un corpo, assicurarsi che la casella **Con corpo** è selezionata.
1. Nel riquadro azioni, selezionare **Messaggio di posta elettronica** per fornire un modello di corpo dell'email.

L'immagine seguente mostra alcune impostazioni di esempio del modello e-mail.

![Impostazioni del modello di messaggio di posta elettronica](media/email-template.png)

### <a name="create-an-email-event"></a>Creare un evento e-mail

Per creare un evento e-mail attenersi alla procedura seguente.

1. Nel pannello di navigazione, andare a **Moduli \> Vendita al dettaglio e commercio \> Impostazione sedi centrali \> Profilo di notifica tramite posta elettronica per Commerce**.
1. Nell'elenco trovare e selezionare il record desiderato. 
1. Selezionare il modello e-mail dall'elenco a discesa **ID posta elettronica**.
1. Selezionare il **Tipo di notifica tramite posta elettronica** appropriato dall'elenco a discesa.
1. Selezionare la casella di controllo **Attiva**.
1. Nel riquadro azioni selezionare **Salva**.

L'immagine seguente mostra alcune impostazioni di esempio della notifica di evento.

![Impostazioni notifica di eventi](media/email-notification-profile.png)

### <a name="next-steps"></a>Passaggi successivi

Prima di poter inviare e-mail, è necessario configurare il servizio di posta in uscita e impostare un processo batch. Per ulteriori informazioni, vedere [Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare e inviare messaggi di posta elettronica](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Panoramica dei canali](channels-overview.md)

[Prerequisiti di impostazione dei canali](channels-prerequisites.md)

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]