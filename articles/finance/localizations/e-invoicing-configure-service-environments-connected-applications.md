---
title: Configurare gli ambienti del servizio e le applicazioni connesse
description: Questo argomento fornisce informazioni su come configurare gli ambienti di servizio e le applicazioni connesse.
author: dkalyuzh
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: c3366e75b4a6d3f33a1aac9e444236d9ae57c829
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371613"
---
# <a name="configure-service-environments-and-connected-applications"></a>Configurare gli ambienti del servizio e le applicazioni connesse

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni su come configurare gli ambienti di servizio e le applicazioni connesse. Ci sono tre passaggi per questo processo. Il passaggio 1 è obbligatorio e i passaggi 2 e 3 sono facoltativi.

## <a name="step-1-create-a-service-environment"></a>Passaggio 1: creare un ambiente del servizio

Quando crei il tuo ambiente di servizio, definisci l'elenco di utenti che possono distribuirvi le funzionalità di globalizzazione. Facoltativamente, per alcuni scenari, definisci l'elenco delle applicazioni esterne che possono comunicare con il servizio di fatturazione elettronica. Configura le sequenze numeriche se le utilizzerai nei tuoi scenari.

Per completare questo passaggio, vedi [Ambienti di servizio](e-invoicing-service-environments.md).

## <a name="step-2-add-certificates-and-secrets"></a>Passaggio 2: aggiungere certificati e segreti

Aggiungi un riferimento a Microsoft Azure Key Vault e segreti per usarli nei tuoi scenari. Questo passaggio è obbligatorio se le azioni nelle pipeline di elaborazione utilizzano certificati e segreti per la firma digitale o la comunicazione con servizi Web esterni.

Per completare questo passaggio, vedi [Certificati e segreti del cliente](e-invoicing-customer-certificates-secrets.md).

## <a name="step-3-configure-connected-applications"></a>Passaggio 3: configurare le applicazioni connesse

Per configurare la comunicazione tra le applicazioni Dynamics 365 Finance o Dynamics 365 Supply Chain Management e la fatturazione elettronica, è necessario configurare Finance o Supply Chain Management per costruire la chiamata al servizio di fatturazione elettronica e preparare i dati aziendali in una struttura unificata che può essere trasformata nel formato elettronico richiesto. Le applicazioni devono inoltre elaborare correttamente le risposte dal servizio. Puoi completare questa configurazione direttamente nel tuo ambiente Finance o Supply Chain Management oppure puoi completarla in Regulatory Configuration Service (RCS). Se completi la configurazione in RCS, puoi quindi distribuirla al tuo ambiente Finance o Supply Chain Management. In questo passaggio, registrerai l'applicazione connessa per la distribuzione dei parametri.

Per completare questo passaggio, vedi [Applicazioni connesse](e-invoicing-connected-applications.md).
