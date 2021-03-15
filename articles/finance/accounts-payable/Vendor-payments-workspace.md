---
title: Area di lavoro pagamenti fornitore
description: In questo argomento vengono fornite informazioni sull'area di lavoro Pagamenti fornitore. Nell'area di lavoro Pagamenti fornitore vengono visualizzate le informazioni correlate all'elaborazione dei pagamenti fornitore.
author: abruer
manager: AnnBe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: roschlom
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 34f4e22f571569a6276f8a801d33c6afef8480dc
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979565"
---
# <a name="vendor-payments-workspace"></a>Area di lavoro pagamenti fornitore

[!include [banner](../includes/banner.md)]

Nell'area di lavoro **Pagamenti fornitore** vengono visualizzate le informazioni correlate all'elaborazione dei pagamenti fornitore. Questa area di lavoro include una visualizzazione **Lavoro personale** e una pagina **Analisi**. Nella visualizzazione **Lavoro personale** vengono visualizzati i riquadri di riepilogo, le griglie di transazione fornitore e le informazioni correlate al fornitore. La pagina **Analisi** utilizza le funzionalità di Microsoft Power BI per visualizzare le rappresentazioni correlate ai pagamenti fornitore.

## <a name="setup-needed-to-view-power-bi-content"></a>Impostazione necessaria per visualizzare il contenuto di Power BI

La seguente impostazione deve essere completata per visualizzare i dati nelle rappresentazioni **Pagamenti fornitore** di Power BI.
1. Andare a **Amministrazione sistema > Impostazioni > Parametri di sistema** per impostare **Valuta di sistema** e **Tipo di tasso di cambio del sistema**.
2. Vai a **Contabilità generale> Calendari > Calendari fiscali** per convalidare le date del calendario fiscale assegnate al periodo di tempo attivo.
3. Passare a **Contabilità generale > Impostazioni > Contabilità generale** per impostare **Valuta di contabilizzazione** e **Tipo di tasso di cambio**. 
4. Definire i tassi di cambio tra le valute della transazioni e la valuta di contabilizzazione, la valuta di contabilizzazione e la valuta di sistema. A tale scopo, andare a **Contabilità generale > Valute > Tassi di cambio valutario**.
5. Passare in **Amministrazione sistema > Impostazioni > Archivio entità** per aggiornare la misura di aggregazione **VendPaymentBIMeasureV2**.

## <a name="my-work-view"></a>Visualizzazione Lavoro personale

### <a name="summary-tiles"></a>Sezioni Riepilogo

I riquadri nella sezione **Riepilogo** forniscono una panoramica dello stato delle informazioni di pagamento. È possibile visualizzare i giornali di registrazione pagamenti non ancora registrati, le fatture già scadute, tutti i fornitori e i fornitori in attesa. Nella sezione **Riepilogo** è possibile creare un nuovo ciclo di pagamenti.

Le informazioni nella sezione **Riepilogo** sono relative alla società cui è stato eseguito l'accesso.

### <a name="vendor-transactions-grids"></a>Griglie transazioni fornitore

La sezione **Transazioni fornitore** contiene le griglie in cui sono indicati le fatture già scadute e i pagamenti non liquidati. Nella griglia **Fatture scadute** è possibile visualizzare lo storico delle liquidazioni di una fattura selezionata. Nella griglia **Pagamenti non liquidati** è possibile visualizzare lo storico delle liquidazioni di una fattura selezionata e liquidare una fattura.

Gli addetti ai pagamenti centralizzati possono utilizzare un filtro visualizzato nella parte superiore di ciascuna griglia per selezionare una società. La griglia viene quindi filtrata in modo da mostrare solo le società che sono definite nella gerarchia organizzativa di pagamento centralizzato per visualizzare la quale l'addetto ai pagamenti centralizzati dispone dei diritti.

Nella scheda **Trova transazioni** della sezione **Transazioni fornitore** è possibile cercare una transazione fornitore.

### <a name="related-information"></a>Informazioni correlate

È possibile visualizzare il report **Aging fornitore** e il report **Riepilogo pagamenti per data** utilizzando i collegamenti nella sezione **Informazioni correlate** dell'area di lavoro.

## <a name="analytics-page"></a>Pagina Analisi

La pagina **Analisi** mostra metriche importanti, ad esempio fatture fornitore già scadute e fatture fornitore che scadono in futuro. Questa pagina contiene nove pagine di report. In una pagina viene fornita una panoramica e nelle altre otto pagine vengono fornite informazioni dettagliate sulle metriche di pagamento della contabilità fornitori.

Nella seguente tabella vengono illustrate le visualizzazioni disponibili in ciascuna pagina del report.


|            Pagina di report            |                                                                                                                                                                                Visualizzazione                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Panoramica pagamenti fornitore      | <ul><li>Fatture scadute</li><li>Fatture con scadenza odierna</li><li>Sconti applicati e sconti persi</li><li>Fatture in scadenza in base alla data dello sconto di cassa</li><li>Fatture in scadenza in base alla data di scadenza</li><li>Fatture pagate in ritardo e fatture pagate puntualmente</li><li>Assegnazione del flusso di lavoro dei pagamenti</li><li>Saldo fornitore/cliente</li><li>Fatture aperte con sospensione pagamento</li></ul> |
|         Fatture scadute         |                                                                                             <ul><li>Fatture scadute</li><li>Dettagli fatture scadute</li><li>Totale fatture aperte</li><li>Fatture scadute per gruppo fornitori</li><li>Fatture scadute per società</li></ul>                                                                                              |
|        Fatture con scadenza odierna         |                                                                                                         <ul><li>Fatture con scadenza odierna</li><li>Dettagli fatture con scadenza odierna</li><li>Fatture con scadenza odierna per società</li><li>Fatture con scadenza odierna per gruppo fornitori</li></ul>                                                                                                          |
| Sconti applicati e sconti persi |                                                                             <ul><li>Sconti applicati e sconti persi</li><li>Dettagli sconti applicati e sconti persi</li><li>Dettagli sconti applicati e sconti persi per società</li><li>Dettagli sconti applicati e sconti persi per gruppo fornitori</li></ul>                                                                              |
|      Fatture in scadenza       |                                                 <ul><li>Fatture in scadenza</li><li>Dettagli fatture in scadenza</li><li>Fattura in scadenza per società</li><li>Fatture in scadenza per gruppo fornitori</li><li>Fatture in scadenza in base alla data dello sconto di cassa</li><li>Fatture in scadenza in base alla data di scadenza</li></ul>                                                  |
|        Fatture pagate in ritardo         |                                                         <ul><li>Fatture pagate dopo la data di scadenza</li><li>Dettagli fatture pagate dopo la data di scadenza</li><li>Fatture pagate dopo la data di scadenza per società</li><li>Fatture pagate dopo la data di scadenza per gruppo fornitori</li><li>Fatture pagate in ritardo e fatture pagate puntualmente</li></ul>                                                          |
|         Flusso di lavoro pagamenti          |                                                                                <ul><li>Istanze del flusso di lavoro di pagamento dei fornitori</li><li>Istanze del flusso di lavoro di pagamento dei fornitori per approvatore</li><li>Istanze del flusso di lavoro di pagamento dei fornitori per società</li><li>Giorni impiegati in media nel flusso di lavoro per approvatore</li></ul>                                                                                |
|    Saldo fornitore/cliente     |                                                                                                                   <ul><li>Saldo fornitore/cliente</li><li>Saldo fornitore/cliente per società</li><li>Dettagli saldo fornitore/cliente</li></ul>                                                                                                                    |
|    Fatture con sospensione pagamento     |                                                                                         <ul><li>Fatture con sospensione pagamento</li><li>Dettagli fatture con sospensione pagamento</li><li>Fatture con sospensione pagamento per società</li><li>Fatture con sospensione pagamento per gruppo fornitori</li></ul>                                                                                          |



[!INCLUDE[footer-include](../../includes/footer-banner.md)]