---
title: Panoramica degli snapshot (anteprima)
description: Questo argomento descrive la funzionalità di snapshot, che consente di salvare una previsione di cassa per l'analisi o il confronto con i valori effettivi in un secondo momento. Quando si genera una previsione di cassa, è possibile salvarla come "snapshot". Puoi quindi utilizzare tali snapshot per modificare i conti inclusi nella previsione o confrontare la previsione nello snapshot con i valori effettivi.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-19
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f0d0bdde8b69148c72b8c645e040f0e596ecba92
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645627"
---
# <a name="snapshots-overview-preview"></a>Panoramica degli snapshot (anteprima)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Gli snapshot consentono alle organizzazioni di modificare e salvare le informazioni sulla loro posizione di cassa e le previsioni di cassa in un determinato momento. Puoi confrontare lo snapshot con i dati finanziari effettivi, esaminare la varianza e utilizzare tali informazioni per migliorare le previsioni di cassa nel tempo. In particolare, gli snapshot possono essere utilizzati nei seguenti modi:

- Tieni traccia della posizione di cassa e delle previsioni di cassa nel tempo.
- Filtra i dati per mostrare un sottoinsieme di persone giuridiche per cui è stato creato lo snapshot.
- Modifica la posizione di cassa e la previsione di cassa generate dal sistema.
- Esegui analisi di tipo what-if per considerare visioni ottimistiche, pessimistiche e molto probabili del flusso di cassa.
- Confronta le prestazioni finanziarie effettive con la previsione salvata nello snapshot.

Puoi creare uno snapshot selezionando **Nuovo snapshot** sulla scheda **Posizione di cassa** o **Previsione di cassa** nell'area di lavoro **Previsioni di cassa**. Dopo aver creato uno snapshot, è possibile modificare e salvare i flussi in entrata e in uscita in esso contenuti. Tutti gli snapshot salvati sono disponibili nella scheda **Snapshot**. Per aprire uno snapshot, selezionane il nome.

I flussi di cassa in entrata e in uscita negli snapshot possono essere modificati in qualsiasi momento. Quando un importo in entrata o un importo in uscita viene modificato, l'importo aggiornato viene ripartito proporzionalmente ai conti di liquidità che hanno effettuato il saldo originale. Dopo avere modificato uno snapshot, seleziona **Salva** per salvare le modifiche.

Per confrontare più snapshot, seleziona **Confronta snapshot**. Puoi confrontare due snapshot alla volta. Seleziona i due snapshot da confrontare, quindi seleziona **OK**. La pagina **Confronta snapshot** mostrerà un confronto degli snapshot selezionati. Il grafico nella sezione superiore della pagina mostra un confronto dei flussi di cassa in entrata, in uscita e dei saldi bancari nei periodi sovrapposti tra i due snapshot. La griglia nella sezione inferiore mostra un confronto dettagliato delle due previsioni per ciascun importo di liquidità. La colonna **Varianza** nella griglia mostra la differenza tra i saldi in un periodo.

Per confrontare i risultati finanziari effettivi con una previsione salvata come snapshot, seleziona **Confronta con i valori effettivi**. La pagina **Confronta snapshot** mostrerà un confronto tra gli importi effettivi e la previsione. Il grafico nella sezione superiore della pagina mostra un confronto dei flussi di cassa in entrata, in uscita e dei saldi bancari nei periodi sovrapposti tra i due snapshot. La griglia nella sezione inferiore mostra un confronto dettagliato dei saldi effettivi per periodo e il saldo previsto per ciascun importo di liquidità. La colonna **Varianza** nella griglia mostra la differenza tra il saldo effettivo in un periodo e il saldo previsto.

#### <a name="privacy-notice"></a>Informativa sulla privacy
Le anteprime (1) potrebbero utilizzare meno misure di sicurezza e di privacy rispetto al servizio Dynamics 365 Finance and Operations, (2) non sono incluse nel contratto di servizio di questo servizio, (3) non devono essere utilizzate per elaborare i dati personali o altri dati soggetti a requisiti legati e normativi, e (4) hanno supporto limitato.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]