---
title: Utilizzare i report analitici per informazioni dettagliate sul processo di assunzione
description: In questo argomento vengono descritti i report analitici di Attract
author: fewatson
manager: AnnBe
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: fewatson
ms.search.validFrom: 2019-04-30
ms.dyn365.ops.version: Talent April 2019 update
ms.openlocfilehash: 33ed6072a9ad99144fb96ad19389a57461324f71
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "1516562"
---
# <a name="use-analytic-reports-for-hiring-process-insights"></a>Utilizzare i report analitici per informazioni dettagliate sul processo di assunzione

I report analitici in Attract offrono una soluzione pronta all'uso per informazioni sul processo di assunzione. Le funzionalità disponibili includono:

- **Analisi posizione**: fare clic sulla scheda **Analisi** in una mansione per visualizzare le metriche su un candidato per la mansione.
- **Hub analisi**: fare clic su **Analisi** nel riquadro di spostamento sinistro per visualizzare le metriche aggregate di tutte le posizioni lavorative.
- **Sicurezza specifica per l'utente**: l'accesso ai report è controllato dal [ruolo](security-attract.md) di Attract e dal ruolo di partecipante alla posizione lavorativa.
- **Filtro incrociato**: fare clic sugli oggetti visivi in un report per visualizzare altre metriche filtrate in base ai dati selezionati.

>[!NOTE] 
>- Questa funzionalità è attualmente in [anteprima](access-preview-feature.md). Per provarla, è necessario il [**Componente aggiuntivo per l'assunzione a livello globale**](attract-comprehensive-hiring.md).
>- Tutti i report pubblici in anteprima vengono visualizzati in inglese.
>- Segnala l'aggiornamento ogni 3 ore. Ultimo aggiornamento (ora in base al fuso orario locale) si trova nella parte superiore del report. I tempi di aggiornamento sono un'approssimazione e variano in base al volume di dati e al carico di risorse nell'area.

## <a name="job-analytics"></a>Analisi posizione

I report Analisi posizione sono uno snapshot del processo di assunzione per una posizione lavorativa.  Le metriche chiave includono:

- Candidati attivi per fase
- Origine del candidato
- Tipo di candidato (interno o esterno)

## <a name="analytics-hub"></a>Hub analisi

Report dell'Hub analisi aggregano i dati relativi alle posizioni lavorative per individuare le tendenze nel processo di assunzione. Attract include due report pronti all'uso: Riepilogo pipeline e Analisi del flusso di conversione.

### <a name="pipeline-summary"></a>Riepilogo pipeline

Il report di riepilogo della pipeline raggruppa i dati per le posizioni aperte. Le metriche chiave includono:

- Candidati per tutte le posizioni lavorative in base alla fase
- Origine del candidato
- Posizioni lavorative aperte in base al livello di anzianità

### <a name="funnel-analysis"></a>Analisi del flusso di conversione

Il report di Analisi del flusso di conversione raggruppa i dati per le posizioni lavorative che sono stati chiuse come completate. Le metriche chiave includono:

- Tempi di assunzione
- Metriche di conversione (al passaggio del mouse)
- Tasso di accettazione dell'offerta

Nota: per report più precisi sui tempi di assunzione, si consiglia di utilizzare [Gestione offerte](offer-setup.md), una funzionalità disponibile come parte del Componente aggiuntivo per l'assunzione a livello globale.

>[!TIP] 
>Provare a passare il mouse sopra le immagini per ulteriori informazioni. Ad esempio, passando il mouse su **Candidati attivi** verranno visualizzata la media in giorni per la fase. L'analisi di queste informazioni può fornire informazioni fondamentali per ridurre i tempi di assunzione e consentire ai selezionatori di concentrarsi su come ridurre il tempo dedicato per ciascuna fase.

## <a name="user-specific-security"></a>Sicurezza specifica dell'utente

I report Attract sono accessibili per i [ruoli](security-attract.md) di Amministratore, Leggi tutto, Selezionatore e Responsabile assunzioni. Gli utenti senza ruolo non possono accedere alle pagine dei report analitici Analisi posizione o Hub analisi.

Nei report Analisi posizione vengono visualizzati i dati relativi alla posizione lavorativa selezionata. L'hub analisi riporta i dati aggregati per tutte le posizioni che un utente può visualizzare. Gli utenti che possono visualizzare sia Mansioni personali che Tutti le mansioni nella pagina Posizioni possono accedere alle stesse visualizzazioni disponibili nell'Hub analisi.

## <a name="cross-filter"></a>Filtro incrociato

Una delle interessanti caratteristiche di Power BI è il modo in cui tutte le immagini in una pagina di report sono interconnesse. Se si seleziona un punto dati su una delle immagini, tutte le altre immagini della pagina che contengono tali dati cambiano, in base a tale selezione. Ulteriori informazioni e un esempio sono disponibili qui: [In che modo le immagini si filtrano a vicenda in un report di Power BI](https://docs.microsoft.com/en-us/power-bi/consumer/end-user-interactions).

## <a name="export-to-excel"></a>Esporta in Excel

Per visualizzare i dati del report in Excel, è possibile fare clic sul menu di opzioni (tre punti) su un'immagine e selezionare **Esporta i dati sottostanti**. I dati esportati verranno esportati come filtrati, rispettando le autorizzazioni degli utenti in Attract. Per ulteriori informazioni, vedere [Esportare dati dalle visualizzazioni](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-export-data).
