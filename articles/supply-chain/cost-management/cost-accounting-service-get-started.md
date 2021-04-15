---
title: Introduzione al servizio di contabilità industriale (anteprima privata)
description: Questo argomento fornisce dettagli sulla licenza e istruzioni di installazione per il servizio di contabilità industriale.
author: AndersGirke
ms.date: 04/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-17
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: b6756e3745aa4596bd5d63ad15aaf4385cfc4813
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813197"
---
# <a name="get-started-with-the-cost-accounting-service-private-preview"></a>Introduzione al servizio di contabilità industriale (anteprima privata)

[!INCLUDE [banner](../includes/banner.md)]

> [!IMPORTANT]
> La funzionalità descritta in questo argomento è disponibile nell'ambito di una versione di anteprima privata. Il contenuto di questo argomento e le funzionalità che descrive sono soggetti a modifiche. Per ulteriori informazioni sui rilasci di anteprima, vedi [Domande frequenti aggiornamenti del servizio versione uno](../../fin-ops-core/fin-ops/get-started/one-version.md).

Il servizio di contabilità industriale consente di eseguire più contabilità di inventario nei movimenti CoGe di contabilità industriale impostati. Associare ogni movimento CoGe di contabilità industriale a una *convenzione*. Una convenzione è la raccolta dei seguenti tipi di principi contabili:

- Oggetto di costo
- Base di misura di input
- Presupposto per flussi di costo
- Elemento di costo

> [!NOTE]
> Anche dopo aver attivato il servizio di contabilità industriale, è ancora possibile eseguire la contabilità di inventario in Microsoft Dynamics 365 Supply Chain Management, come di consueto.

Il servizio di contabilità industriale è un componente aggiuntivo. Per rendere disponibili le funzionalità, è necessario installarlo da Microsoft Dynamics Lifecycle Services (LCS). Pertanto, è possibile scegliere di valutarlo in un ambiente di test prima di attivarlo per gli ambienti di produzione.

Il servizio di contabilità industriale non supporta attualmente tutte le funzionalità di gestione dei costi integrate in Dynamics 365 Supply Chain Management. Pertanto, è importante valutare se il set di funzionalità attualmente disponibile soddisfa i requisiti.

## <a name="how-to-get-the-cost-accounting-service-private-preview"></a><a name="sign-up"></a>Come ottenere il servizio di contabilità industriale (anteprima privata)

> [!IMPORTANT]
> Per utilizzare il servizio di contabilità industriale, è necessario disporre di un ambiente ad alta disponibilità abilitato per LCS (non un ambiente OneBox) e deve essere in esecuzione Dynamics 365 Supply Chain Management versione 10.0.11 o successiva.

Per iscriversi all'anteprima privata del servizio di contabilità dei costi, invia l'ID dell'ambiente LCS via e-mail a [Servizio di contabilità industriale (anteprima privata)](mailto:aevengir@microsoft.com?subject=Cost%20accounting%20service%20%28private%20preview%29). Dopo aver approvato il programma, ti invieremo un'email di follow-up che contiene una chiave beta del servizio di contabilità industriale. Alla ricezione della chiave beta, puoi procedere all'[installazione del componente aggiuntivo](#install).

## <a name="licensing"></a>Licenze

Il servizio di contabilità industriale è concesso in licenza insieme alle funzionalità standard della contabilità di magazzino disponibili per Supply Chain Management. Non è necessario acquistare una licenza aggiuntiva per utilizzare il servizio di contabilità industriale.

## <a name="install-the-add-in"></a><a name="install"></a>Installare il componente aggiuntivo

Per utilizzare il servizio di contabilità industriale, installare il componente aggiuntivo del servizio di contabilità industriale per Supply Chain Management come descritto nella seguente procedura.

1. [Iscriviti](#sign-up) al servizio di contabilità industriale (anteprima privata).

1. Accedere a LCS.

1. Accedere a **Gestione funzionalità di anteprima**.

1. Selezionare il segno più (**+**).

1. Nel campo **Codice**, inserire la chiave beta del componente aggiuntivo per il servizio di contabilità industriale. La chiave viene ricevuta tramite posta elettronica.

1. Selezionare **Sblocca**.

1. Aprire l'ambiente LCS in cui si desidera aggiungere il servizio.

1. Andare a **Dettagli completi**.

1. Scorrere verso il basso fino alla scheda dettaglio **Componenti aggiuntivi dell'ambiente**.

1. Selezionare **Installare un nuovo componente aggiuntivo**.

1. Selezionare **Servizio di contabilità industriale**.

1. Seguire la guida all'installazione e accettare le condizioni.

1. Selezionare **Installa**.

1. Nella scheda dettaglio **Componenti aggiuntivi dell'ambiente** viene indicato che il servizio di contabilità industriale è stato installato. Dopo alcuni minuti, lo stato cambia da **Installazione in corso** in **Installato**. Potrebbe essere necessario aggiornare la pagina per vedere questa modifica. A quel punto, il servizio di contabilità industriale è pronto per l'uso.

## <a name="set-up-the-integration"></a>Impostare l'integrazione

Per impostare l'integrazione tra il servizio di contabilità industriale e Dynamics 365 Supply Chain Management:

1. Andare a **Amministrazione sistema > Gestione funzionalità**.

1. Selezionare **Controlla aggiornamenti**.

1. Aprire la scheda **Tutto** e cercare la funzionalità denominata *Servizio di contabilità industriale*.

1. Selezionare **Abilita ora**.

1. Andare a **Gestione costi> Servizio contabilità industriale > Impostazione > Parametri servizio contabilità industriale > Parametri integrazioni**.

1. Nel campo **ID applicazione** immettere il seguente codice:<br> 08231eb2-a501-4edb-b3c5-aede5e5e0c3f

1. Nel campo **Endpoint del servizio dati** immettere il seguente URL:<br>https://operationsdataservice.operations365.dynamics.com/

1. Nel campo **Endpoint del servizio contabilità industriale** immettere il seguente URL:<br>https://costaccountingservice.operations365.dynamics.com/

1. Il servizio di contabilità industriale è ora pronto per l'uso.

## <a name="related-resources"></a>Risorse correlate

[Home page del servizio contabilità industriale](cost-accounting-service-home.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]