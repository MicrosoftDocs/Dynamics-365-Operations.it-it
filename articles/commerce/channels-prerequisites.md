---
title: Prerequisiti di impostazione dei canali
description: Questo argomento fornisce una panoramica dei prerequisiti di impostazione dei canali in Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 33fcead6c0b08db17f24b638376a23b8b6024a5b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800521"
---
# <a name="channel-setup-prerequisites"></a>Prerequisiti dell'impostazione dei canali

[!include [banner](includes/banner.md)]

Questo argomento fornisce una panoramica dei prerequisiti di impostazione dei canali in Microsoft Dynamics 365 Commerce.

Prima di creare un canale di Dynamics 365 Commerce, è necessario completare varie attività preliminari. I seguenti elenchi di attività preliminari sono organizzati per tipo di canale.

> [!NOTE]
> Parte della documentazione è ancora in fase di scrittura e i collegamenti verranno aggiornati alla pubblicazione di nuovi contenuti.

## <a name="initialization"></a>Inizializzazione

- [Inizializzare i dati iniziali](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Prerequisiti globali richiesti per tutti i tipi di canali

- [Definire e configurare la struttura della persona giuridica](channels-legal-entities.md) 
- [Configurare la gerarchia organizzativa](channels-org-hierarchies.md)
- [Impostare un magazzino](channels-setup-warehouse.md)
- [Configurare l'IVA](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Impostare un profilo di notifica tramite posta elettronica](email-notification-profiles.md)
- [Imposta sequenze numeriche](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Impostare un cliente e una rubrica predefiniti](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Prerequisiti per canali di vendita al dettaglio

- [Codici di informazioni e gruppi di codici di informazioni](info-codes-retail.md)
- [Impostare un profilo funzionalità per vendità al dettaglio](retail-functionality-profile.md)
- [Impostare una rubrica di dipendenti](new-address-book.md)
- [Impostare un layout dello schermo](pos-screen-layouts.md)
- [Impostare una stazione hardware](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Prerequisiti per canali servizio clienti

- Parametri servizio clienti
- [Ordine servizio clienti e metodi di pagamento per il rimborso](work-with-payments.md)
- [Modalità del servizio clienti per spese e consegna](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Prerequisiti dei canali online

- [Creare un profilo funzionalità online](online-functionality-profile.md)

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Impostare gerarchie organizzative](channels-org-hierarchies.md)

[Creare persone giuridiche](channels-legal-entities.md)

[Impostare un canale di vendita al dettaglio](channel-setup-retail.md)
    
[Impostare un canale online](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
