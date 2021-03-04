---
title: Installare lo strumento di progettazione layout POS
description: È possibile utilizzare lo strumento di progettazione con un clic per progettare layout di Modern POS (MPOS) e POS cloud diversi, con orientamento orizzontale o verticale, per punti vendita, registratori di cassa, cassieri e responsabili.
author: athinesh99
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 219684
ms.assetid: 2e2c4eea-c6e2-4912-9832-a6b22416e39f
ms.search.region: Global
ms.search.industry: Retail
ms.author: athinesh
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: f9882ae895de926e0da3579ab65a988f2b97f7be
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4413445"
---
# <a name="install-the-pos-layout-designer"></a>Installare lo strumento di progettazione layout POS

[!include [banner](includes/banner.md)]

È possibile utilizzare lo strumento di progettazione con un clic per progettare layout di Modern POS (MPOS) e POS cloud diversi, con orientamento orizzontale o verticale, per punti vendita, registratori di cassa, cassieri e responsabili.

L'interfaccia di progettazione grafica per MPOS o POS cloud viene controllata tramite il layout cassetto. Un layout controlla la posizione di diversi oggetti. Gli esempi includono il layout totale, il layout griglia articoli, il layout cliente, il layout pagamento, e il layout di diversi pulsanti di menu. I layout includono anche l'aspetto generale dell'interfaccia relativa alle vendite presentata ai lavoratori.

## <a name="install-the-one-click-designer"></a>Installare lo strumento di progettazione con un clic

1. In Commerce, utilizzare il menu in alto a sinistra per accedere a **Retail e Commerce** &gt; **Impostazione canale** &gt; **Impostazioni POS** &gt; **POS** &gt; **Layout schermo**.
2. Selezionare il layout con tipo applicazione **Modern POS per Windows** o **POS cloud**, quindi fare clic su **Progettazione layout**.
3. Nella barra di notifica visualizzata nella parte inferiore della finestra di Internet Explorer, fare clic su **Apri** per avviare l'installazione della progettazione con un clic. (La barra di notifica potrebbe essere visualizzata in un posto diverso in altri browser).
4. Nella finestra di messaggio **Esecuzione applicazione - Avviso di sicurezza** visualizzata, fare clic su  **Esegui** per installare l'host della progettazione Retail. Un indicatore di stato mostra lo stato di avanzamento di installazione.
5. Dopo che l'installazione è stata completata, nella pagina **Accedi** immettere nome utente e password di Commerce e quindi fare clic **Accedi** per avviare lo strumento di progettazione.
6. Dopo che le credenziali vengono convalidate e si avvia la progettazione, è possibile iniziare a progettare il proprio layout o modificare il layout esistente.

    [![Layout nello strumento di progettazione con un clic](./media/screenlayoutdesign_mposdownload-1024x664.png)](./media/screenlayoutdesign_mposdownload.png)

## <a name="troubleshoot-the-installation-of-the-layout-designer"></a>Risolvere i problemi relativi all'installazione della progettazione layout

- Quando si fa clic su **Progettazione**, la richiesta per scaricare (o eseguire) il programma di installazione non appare o le impostazioni di sicurezza correnti non consentono il download del file. 

    **Soluzioni:**

    - In Internet Explorer, assicurarsi che il blocco popup è disabilitato per il sito. Fare clic su **Impostazioni** &gt; **Opzioni** &gt; **Privacy** &gt; **Trova blocco popup** e modificare le impostazioni, se sono necessarie modifiche.
    - In Internet Explorer, aggiungere l'URL di Commerce ai siti attendibili. Fare clic su **Impostazioni** &gt; **Opzioni** &gt; **Sicurezza** &gt; **Siti attendibili** &gt; **Siti** &gt; **Aggiungi**.

- Il programma non viene avviato o viene richiesto di contattare il fornitore.

    **Soluzione:** In Internet Explorer, aggiungere l'URL di Commerce ai siti attendibili. Fare clic su **Impostazioni** &gt; **Opzioni** &gt; **Sicurezza** &gt; **Siti attendibili** &gt; **Siti** &gt; **Aggiungi**.

**Problema noto:** lo strumento di progettazione attualmente non funziona nei browser Google Chrome e Mozilla Firefox Stiamo lavorando per risolvere questo problema.

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare, installare e attivare Retail Modern POS (MPOS)](retail-modern-pos-device-activation.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]