---
title: Componenti della funzionalità di globalizzazione
description: In questo articolo viene fornita una panoramica dei componenti della funzionalità di globalizzazione.
author: gionoder
ms.date: 02/11/2022
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
ms.openlocfilehash: 94e2d118c332a15f41f33184f5e44b0fdaccd000
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275228"
---
# <a name="globalization-feature-components"></a>Componenti della funzionalità di globalizzazione

[!include [banner](../includes/banner.md)]

Una funzionalità di globalizzazione è un insieme di componenti che definiscono le regole per la trasformazione dei dati nelle configurazioni di reporting elettronico (ER). Questi componenti includono istruzioni per l'elaborazione di documenti elettronici e per l'invio o la ricezione degli stessi da canali esterni. Includono anche condizioni che definiscono quando una funzionalità deve essere eseguita per i dati aziendali in entrata.

Tutti i componenti dipendono l'uno dall'altro. Le funzionalità di globalizzazione semplificano la creazione e il mantenimento di questa dipendenza e il supporto per la gestione del ciclo di vita e il controllo delle versioni del set di componenti.

## <a name="access-electronic-invoicing-feature-components"></a>Accedere ai componenti delle funzionalità di fatturazione elettronica 

1. Accedi al tuo account Regulatory Configuration Service (RCS).
2. Nell'area di lavoro **Funzionalità di globalizzazione**, nella sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.

    Le funzionalità di globalizzazione hanno vari componenti. La pagina **Funzionalità di fatturazione elettronica** include una scheda separata per ogni componente.

    - **Versione** – Questo componente supporta la gestione del ciclo di vita della funzionalità. Puoi usarlo per gestire lo stato per diverse versioni della funzione.
    - **Configurazioni** – Questo componente consente di gestire, visualizzare e modificare il formato ER correlato e le configurazioni di mapping del formato utilizzate nella pipeline di elaborazione.
    - **Impostazioni** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'impostazione della versione della funzionalità correlata. Pertanto, supporta la costruzione flessibile delle regole di comunicazione e risposta.
    - **Ambienti** - Questo componente consente agli utenti dei servizi di globalizzazione, come un servizio di fatturazione elettronica, di gestire l'ambiente in cui viene utilizzata l'impostazione delle versioni della funzionalità. Consente inoltre di concedere l'autorizzazione agli utenti che avranno accesso alla configurazione della versione della funzionalità.
    - **Organizzazioni** - Questo componente consente agli utenti di condividere la funzionalità con organizzazioni esterne.
    - **Tag** – Questo componente consente di contrassegnare le funzioni che possono essere utilizzate nel progetto di globalizzazione come riferimento.
