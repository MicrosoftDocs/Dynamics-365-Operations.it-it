---
title: Risolvere i problemi di configurazione della previsione del flusso di cassa
description: Questo argomento fornisce le risposte alle domande che potrebbero sorgere quando si configura la previsione del flusso di cassa. Risponde alle domande frequenti (FAQ) sulla configurazione del flusso di cassa, sugli aggiornamenti del flusso di cassa e sul flusso di cassa Power BI.
author: panolte
manager: AnnBe
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerCovParameters
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2020-12-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 89eb2f1bcfc73a6a7171a275532b2356e858e87c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985289"
---
# <a name="troubleshoot-cash-flow-forecasting-setup"></a>Risolvere i problemi di configurazione della previsione del flusso di cassa

[!include [banner](../includes/banner.md)]

Questo argomento fornisce le risposte alle domande che potrebbero sorgere quando si configura la previsione del flusso di cassa. Risponde alle domande frequenti (FAQ) sulla configurazione del flusso di cassa, sugli aggiornamenti del flusso di cassa e sul flusso di cassa Power BI.

## <a name="why-is-cash-flow-shown-for-only-one-legal-entity"></a>Perché il flusso di cassa viene mostrato per una sola persona giuridica?

La previsione del flusso di cassa è configurata e calcolata per ogni persona giuridica. I report Power BI e la funzionalità di previsioni del flusso di cassa in Finance Insights mostrano i risultati.

La previsione del flusso di cassa deve essere impostata per ogni persona giuridica per la quale desideri visualizzare una previsione. Rivedi la configurazione della previsione del flusso di cassa in tutte le persone giuridiche. In alternativa, rivedi la configurazione di tutte le persone giuridiche per la previsione del flusso di cassa e assicurati che siano impostate come previsto.

## <a name="why-doesnt-power-bi-show-all-the-cash-flow-data"></a>Perché Power BI non mostra tutti i dati del flusso di cassa?

È necessario completare diversi passaggi prima che le previsioni del flusso di cassa possano essere visualizzate in Power BI. Rivedi il seguente elenco di controllo e assicurati che ogni passaggio sia stato completato:

- Imposta il flusso di cassa per ciascuna persona giuridica.
- In Parametri di contabilità generale, imposta la valuta di sistema e il tipo di tasso di cambio di sistema.
- Imposta la valuta di contabilizzazione per la contabilità generale e il tipo di tasso di cambio.
- Immetti i tassi di cambio tra la valuta di transazione e la valuta di contabilizzazione.
- Immetti i tassi di cambio tra la valuta di contabilizzazione e la valuta di sistema.
- Immetti i tassi di cambio tra la valuta di contabilizzazione e ogni valuta di banca.

## <a name="why-did-cash-flow-power-bi-work-in-previous-versions-but-is-now-blank"></a>Perché il flusso di cassa Power BI funziona nelle versioni precedenti ma ora è vuoto?

Verifica che le misure "Misura flusso di cassa V2" e "LedgerCovLiquidityMeasurement" dall'archivio entità siano state configurate. Per ulteriori informazioni su come lavorare con i dati nell'archivio entità, vedi [Integrazione di Power BI con l'archivio entità](../../fin-ops-core/dev-itpro/analytics/power-bi-integration-entity-store.md) Verifica che tutti i passaggi necessari per visualizzare il contenuto Power BI siano stati completati. Per ulteriori informazioni, vedere [Contenuto di Power BI della panoramica situazione di cassa](Cash-Overview-Power-BI-content.md).

## <a name="have-the-entity-store-entities-been-refreshed"></a>Le entità dell'archivio entità sono state aggiornate?

È necessario aggiornare periodicamente le entità per garantire che i dati siano aggiornati e accurati. Per aggiornare manualmente un'entità specifica, vai a **Amministrazione di sistema \> Impostazione \> Archivio entità**, seleziona l'entità e quindi seleziona **Aggiorna**. I dati possono anche essere aggiornati automaticamente. Nella pagina **Archivio entità** imposta l'opzione **Aggiornamento automatico abilitato** su **Sì**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]