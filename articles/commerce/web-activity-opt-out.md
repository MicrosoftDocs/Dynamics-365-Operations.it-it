---
title: Disattiva la raccolta eventi per attività Web
description: Questo argomento spiega come consentire ai visitatori del tuo sito Web di annullare la raccolta di eventi di attività Web in Microsoft Dynamics 365 Commerce.
author: aamiral
ms.date: 05/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 86f475cc0b78c620309301516b6c3b525b640637
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5791559"
---
# <a name="opt-out-of-web-activity-event-collection"></a>Rifiutare esplicitamente la raccolta eventi di attività Web
[!include [banner](includes/banner.md)]

Questo argomento descrive come è possibile consentire di disattivare la raccolta eventi per l'attività Web in Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce consente agli amministratori del sito di analizzare l'attività Web degli utenti dei loro siti di e-commerce. In questo modo, possono comprendere meglio come vengono utilizzati i loro siti e possono ottimizzare i siti per fornire una migliore esperienza utente e soddisfare gli obiettivi aziendali.


## <a name="ways-for-administrators-to-implement-an-opt-out-experience"></a>Metodi di implementazione di un'esperienza di rifiuto esplicito per gli amministratori

Gli amministratori hanno a disposizione 3 metodi di implementazione di un'esperienza di rifiuto esplicito.

### <a name="opt-out-on-behalf-of-users"></a>Rifiuto esplicito per conto degli utenti

Nella gestione degli account in Commerce headquarters (HQ), gli amministratori possono attivare il rifiuto esplicito per conto degli utenti.

1. Nel client HQ, nella pagina **Tutti i clienti**, cerca e seleziona un cliente.
1. Nella pagina dei dettagli del cliente, nella Scheda dettaglio **Retail**, sezione **Privacy**, imposta l'opzione **Non eseguire la traccia dell'attività Web** su **Sì**.

    ![Impostazioni di privacy](media/Disablepersonalizationpart2.png)

1. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="module-based-opt-out-experience"></a>Esperienza di rifiuto basata su moduli

Gli amministratori possono consentire agli utenti autenticati di rinunciare autonomamente alla raccolta di eventi di attività Web. Per fornire questa esperienza di rifiuto, aggiungere il modulo di rifiuto esplicito dell'utente alle pagine del profilo dell'account cliente.

### <a name="custom-extensions"></a>Estensioni personalizzate

Gli amministratori possono creare estensioni personalizzate per gestire l'esperienza di rifiuto per gli utenti. Per ulteriori informazioni, vedere [Chiamare API Retail Server](e-commerce-extensibility/call-retail-server-apis.md)e [Estendibilità del canale online](e-commerce-extensibility/overview.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
