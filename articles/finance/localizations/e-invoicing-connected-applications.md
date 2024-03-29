---
title: Applicazioni connesse
description: Questo articolo spiega come configurare le applicazioni connesse nella fatturazione elettronica.
author: gionoder
ms.date: 02/07/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.form: ''
ms.openlocfilehash: aa6c80914301cc0403974a6acc5e95ff61c9c1a7
ms.sourcegitcommit: a5a4c45bb265758c6e5c3483c8552503b1799a89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2022
ms.locfileid: "9524691"
---
# <a name="connected-applications"></a>Applicazioni connesse

[!include [banner](../includes/banner.md)]

Le applicazioni connesse sono le istanze di Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management che è consigliabile raggiungere tramite Regulatory Configuration Services (RCS). Tramite le applicazioni connesse, puoi configurare parte della funzione di globalizzazione in Finance o Supply Chain Management per far funzionare lo scenario di fatturazione elettronica.

Quando distribuisci la funzione di globalizzazione, le informazioni di configurazione applicabili all'applicazione Finance o Supply Chain Management possono essere pubblicate direttamente da RCS all'applicazione connessa appropriata.

La disponibilità dei parametri Finance o Supply Chain Management in RCS è utile quando si hanno diversi ambienti applicativi, come test di accettazione utente (UAT) e ambienti di produzione, e si desidera mantenere la configurazione coerente distribuendo gli stessi parametri in ambienti diversi.

## <a name="create-a-connected-application"></a>Creare un'applicazione connessa

1. Accedi al tuo account RCS.
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Collegamenti correlati**, seleziona **Impostazione ambiente**.
3. Nella pagina **Configurazione ambiente**, nel riquadro Azioni, selezionare **Applicazioni connesse**.
4. Seleziona **Nuovo** per creare un'applicazione connessa.
5. Nel campo **Nome** immettere il nome dell'applicazione da connettere.
6. Nel campo **Tipo** seleziona **Dynamics 365 Finance**.
7. Nel campo **Applicazione** immetti l'URL dell'ambiente da connettere.
8. Nel campo **Tenant**, immetti il tenant dell'ambiente.
9. Seleziona **Salva**.
10. Nel riquadro azioni seleziona **Verificare connessione** per testare la connessione con l'ambiente. Quindi, chiudere la pagina.

## <a name="link-connected-applications-to-environments"></a>Collegare le applicazioni connesse agli ambienti

1. Nella pagina **Configurazione ambiente**, selezionare **Nuovo** per assegnare un'applicazione connessa a un ambiente.
2. Nel campo **Applicazione connessa** seleziona un'applicazione connessa.
3. Nel campo **Ambiente del servizio**, seleziona un ambiente del servizio.
4. Selezionare **Salva**, quindi chiudere la pagina.
