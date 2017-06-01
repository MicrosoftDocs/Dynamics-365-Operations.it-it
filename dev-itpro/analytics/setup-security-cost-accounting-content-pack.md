---
title: "Impostare la sicurezza per il contenuto Power BI per l&quot;analisi della contabilità industriale"
description: "In questo argomento viene descritto come propagare la protezione a livello di accesso nella contabilità industriale alla protezione a livello di riga in Microsoft Power BI. Questa funzionalità assicura che gli utenti visualizzino solo i dati Power BI ai quali sono autorizzati ad accedere."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270294
ms.assetid: 3a7ba8b0-ac57-4159-9cd8-4308f6021f36
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: cd9e85a54335f321d78a480d1f8ab345b9c8a00b
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-security-for-the-cost-accounting-analysis-power-bi-content"></a>Impostare la sicurezza per il contenuto Power BI per l'analisi della contabilità industriale

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come propagare la protezione a livello di accesso nella contabilità industriale alla protezione a livello di riga in Microsoft Power BI. Questa funzionalità assicura che gli utenti visualizzino solo i dati Power BI ai quali sono autorizzati ad accedere.

<a name="overview"></a>Panoramica
--------

Il contenuto Microsoft Power BI per l'**Analisi della contabilità industriale** utilizza la protezione a livello di riga di Power BI per limitare l'accesso di un utente. La protezione è basata sulla gerarchia organizzativa a livello di accesso impostata nei parametri della contabilità industriale. Per ulteriori informazioni sul contenuto Power BI per l'**Analisi della contabilità industriale**, vedere [Contenuto Power BI per l'analisi della contabilità industriale](cost-accounting-analysis-content-pack.md).

## <a name="setup"></a>Imposta
Per propagare la protezione a livello di accesso a Power BI, il proprietario del contenuto Power BI deve attenersi alla procedura seguente. **Nota:** l'utente che pubblica il contenuto Power BI per l'**Analisi della contabilità industriale** ne diventa automaticamente il proprietario. Solo un proprietario può impostare la protezione in Power BI. Inoltre, finché il proprietario non aggiunge altri utenti su PowerBI.com, nessuno tranne il proprietario può visualizzare alcun dato nel contenuto Power BI per l'**Analisi della contabilità industriale**.

1.  Pubblicare il file di definizioni su Power BI.
2.  Accedere a PowerBI.com.
3.  Individuare il set di dati per il contenuto Power BI per l'**Analisi della contabilità industriale**.
4.  Aprire la pagina di protezione. 

    [![Apertura della pagina di protezione](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-1.png)

5.  Il ruolo **Controller oggetto di costo** è già creato. Aggiungere altri membri che fanno parte della gerarchia organizzativa a livello di accesso della contabilità industriale. 

    [![Aggiunta di membri](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)](https://msdynamics.blob.core.windows.net/media/2017/02/CA-picture-2.png)

Gli utenti aggiunti al ruolo **Controller oggetto di costo** visualizzeranno solo i dati sono autorizzati a visualizzare, in base alla definizione della gerarchia organizzativa a livello di accesso della contabilità industriale. **Nota:** la protezione a livello di riga si applica ai riquadri e ai report in Microsoft Dynamics 365 for Operations incorporati da Power BI.

## <a name="updating-security"></a>Aggiornamento della protezione
Se vengono eseguiti aggiornamenti alla protezione a livello di accesso nella contabilità industriale e si desidera che Power BI rifletta tali aggiornamenti, è necessario aggiornare l'archivio entità per il contenuto Power BI per l'**Analisi della contabilità industriale**. Dopo aver completato l'aggiornamento dell'archivio entità da Dynamics 365 for Operations, è necessario aggiornare gli elementi in PowerBI.com. Per ulteriori informazioni sull'aggiornamento dell'archivio entità, vedere [Aggiornare l'archivio entità](power-bi-integration-entity-store.md#update-entity-store). Il proprietario dei contenuti Power BI per l'**Analisi della contabilità industriale** deve inoltre effettuare un aggiornamento dell'archivio entità se a nuovi utenti viene concesso l'accesso alla gerarchia organizzativa. Inoltre, il proprietario deve aggiungere i nuovi utenti al ruolo **Controller oggetto di costo** in PowerBI.com, in modo che la protezione a livello di riga venga applicata a tali utenti.

## <a name="disabling-security"></a>Disabilitazione della protezione
Supponiamo che l'organizzazione desideri limitare l'accesso ai dati. Se, per qualsiasi motivo, i parametri di protezione sono disabilitati quando si esegue la contabilità industriale, il proprietario deve invece aggiungere gli utenti al ruolo **Contabilità industriale** in Power BI. Se si modifica la protezione da uno stato abilitato a uno stato disabilitato, è consigliabile rimuovere gli utenti dal ruolo **Controller oggetto di costo**. Se si abilita nuovamente la protezione, è opportuno aggiungere gli utenti a tale ruolo. Gli utenti possono appartenere a entrambi i ruoli. L'accesso congiunto è l'unione di entrambi i ruoli. Nel caso del contenuto Power BI per l'**Analisi della contabilità industriale**, gli utenti che dispongono dell'accesso congiunto hanno accesso ai dati senza limitazioni. Se l'obiettivo è applicare un accesso limitato, è necessario assegnare agli utenti solo il ruolo **Controller oggetto di costo**. Questi aggiornamenti della protezione a livello di riga hanno effetto immediato. Gli utenti interessati devono aggiornare il proprio browser.

## <a name="additional-resources"></a>Risorse aggiuntive
Per ulteriori informazioni sulla protezione a livello di riga di Power BI, vedere [Gestire la protezione sul proprio modello in Power BI](https://powerbi.microsoft.com/en-us/documentation/powerbi-admin-rls/#manage-security-on-your-model).




