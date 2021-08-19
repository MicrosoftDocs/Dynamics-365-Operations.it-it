---
title: Parametri non utilizzati da Ottimizzazione pianificazione
description: Questo argomento elenca i parametri che Ottimizzazione pianificazione non considera durante il funzionamento.
author: crytt
ms.date: 6/29/2021
ms.topic: article
ms.search.form: ReqParameters, ReqGroup, ReqItemTable, ReqPlanSched, EcoResProductDetailsExtended, InventItemOrderSetup, WorkCalendarTable, PdsDispositionMaster
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-06-29
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 1992523ae10f30196ebe55d7c7fe6a2549a3a12853da261bd4a129523b8e4ea2
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6714285"
---
# <a name="parameters-not-used-by-planning-optimization"></a>Parametri non utilizzati da Ottimizzazione pianificazione

[!include [banner](../../includes/banner.md)]

Questo argomento elenca i parametri che Ottimizzazione pianificazione non considera durante il funzionamento. Il servizio di pianificazione potrebbe ignorare un parametro perché, ad esempio, la funzionalità correlata non è ancora supportata. In alternativa, il parametro potrebbe essere diventato obsoleto a causa di modifiche funzionali.

Le sezioni seguenti elencano i parametri che Ottimizzazione pianificazione non utilizza in pagine specifiche. Spiegano anche perché ogni parametro non viene utilizzato.

## <a name="master-planning-parameters-page"></a>Pagina Parametri di pianificazione generale

Ottimizzazione pianificazione non utilizza i seguenti parametri o opzioni nella pagina **Parametri di pianificazione generale**:

- Scheda **Generale**:

    - **Piano di previsione attuale**: in attesa del supporto *Previsione*.
    - **Piano generale statico attuale**: in attesa del supporto *Copia piano statico in piano dinamico*.
    - **Piano generale dinamico attuale**: in attesa del supporto *Copia piano statico in piano dinamico*.
    - **Copia il piano generale statico completo e aggiornato nel piano generale dinamico**: in attesa del supporto *Copia piano statico in piano dinamico*.
    - **Ora di inizio per i ritardi calcolati**: in attesa del supporto *Ritardi calcolati*.
    - **Usa giorni negativi dinamici**: Ottimizzazione pianificazione utilizza sempre l'approccio *Giorni negativi dinamici*.
    - **Calendario data odierna**: in attesa del supporto *Programmazione*.
    - **Utilizzo della cache**: la configurazione dellabbonamento a Microsoft Azure gestisce i punti prestazioni.
    - **Numero di attività nel bundle attività helper**: la configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Pre-elaborazione: filtrare automaticamente per articoli con domanda diretta** – La configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Post-elaborazione: filtrare automaticamente per articoli con domanda diretta** – La configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Numero di ordini nel bundle stabilizzazione**: la configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Numero di thread**: la configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Timeout di processo pianificazione in minuti**: la configurazione dell'abbonamento ad Azure gestisce i punti prestazioni.
    - **Orario di inizio programmazione**: in attesa del supporto *Programmazione*.

- Scheda **Ordini pianificati**:

    - **Ora ricevuta**: in attesa del supporto *Programmazione*.
    - **Produzione**: in attesa del supporto *Programmazione*.
    - Campi nella sezione **Progetto**: in attesa del supporto *Pianificazione*.

- Scheda **Aggiornamento standard**:

    - **Aggiorna contrassegno**: in attesa del supporto *Stabilizzazione*.
    - **Interrompi stabilizzazione se si verifica un errore**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per fornitore**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per gruppo acquirenti**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per contratto di acquisto**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per periodo**: in attesa del supporto *Stabilizzazione*.
    - **Trova contratto di acquisto**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per priorità pianificazione**: in attesa del supporto *Stabilizzazione*.
    - **Raggruppa per periodo**: in attesa del supporto *Stabilizzazione*.

## <a name="coverage-groups-page"></a>Pagina Gruppi di copertura

Ottimizzazione pianificazione non utilizza i seguenti parametri o opzioni nella pagina **Gruppi di copertura**:

- Scheda dettaglio **Generale**:

    - **Giorni positivi**: in attesa del supporto *Giorni positivi*.
    - **Consuma scorte disponibili**: in attesa del supporto *Consumo scorte disponibili*.
    - **Usa la distinta base o la versione di formula specificata**: in attesa del supporto *Versioni di formula con sotto/co-prodotti*.
    - **Usa la versione di ciclo di lavorazione specificata**: in attesa del supporto *Domanda con distinta base specifica o requisiti di ciclo di lavorazione definiti*.

- Scheda dettaglio **Azione**:

    - **Messaggio di azione**: in attesa del supporto *Azioni*.
    - **Intervallo temporale azione**: in attesa del supporto *Azioni*.
    - **Margine di posticipo**: in attesa del supporto *Azioni*.
    - **Margine di anticipo**: in attesa del supporto *Azioni*.
    - **Data base**: in attesa del supporto *Azioni*.
    - **Anticipo**: in attesa del supporto *Azioni*.
    - **Posticipo**: in attesa del supporto *Azioni*.
    - **Diminuzione**: in attesa del supporto *Azioni*.
    - **Aumento**: in attesa del supporto *Azioni*.
    - **Azioni derivate**: in attesa del supporto *Azioni*.

- Scheda dettaglio **Altro**:

    - **Intervallo temporale blocco (giorni)**: il supporto *Intervallo temporale blocco* non è previsto per Ottimizzazione pianificazione.
    - **Intervallo temporale esplosione DBA (giorni)**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale programmazione capacità (giorni)**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale richiesta approvata (giorni)**: in attesa del supporto *Richiesta*.
    - **Intervallo temporale piano previsionale**: in attesa del supporto *Previsione*.

- Scheda dettaglio **Ritardi**:

    - **Ritardi calcolati**: in attesa del supporto *Ritardi calcolati*.
    - **Intervallo temporale ritardi calcolati (giorni)**: in attesa del supporto *Ritardi calcolati*.

## <a name="item-coverage-page"></a>Pagina Copertura articoli

Ottimizzazione pianificazione non utilizza i seguenti parametri o opzioni nella pagina **Copertura articoli**:

- Scheda **Generale**:

    - **Tipo di ordine pianificato**: Ottimizzazione pianificazione non supporta l'opzione *Kanban*, in attesa del supporto *Kanban*.
    - **Intervallo temporale blocco (giorni)**: il supporto *Intervallo temporale blocco* non è previsto per Ottimizzazione pianificazione.
    - **Intervallo temporale esplosione DBA (giorni)**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale programmazione capacità (giorni)**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale richiesta approvata (giorni)**: in attesa del supporto *Richiesta*.
    - **Soddisfa minimo**: Ottimizzazione pianificazione non supporta le opzioni *Data odierna*, *Prima uscita* e *Intervallo temporale di copertura*. Utilizza sempre l'opzione *Data odierna + tempo di approvvigionamento*.
    - **Periodi minimi**: in attesa del supporto *Livello scorte minime*.
    - **Formula di pianificazione**: in attesa del supporto *Versioni formula con sotto/co-prodotti*.
    - **Priorità predefinita**: in attesa del supporto *Versioni formula con sotto/co-prodotti*.
    - **Priorità corrente**: in attesa del supporto *Versioni formula con sotto/co-prodotti*.
    - **Data modificata**: in attesa del supporto *Versioni formula con sotto/co-prodotti*.
    - **Consuma scorte disponibili**: in attesa del supporto *Consumo scorte disponibili*.

## <a name="master-plans-page"></a>Pagina Piani generali

Ottimizzazione pianificazione non utilizza i seguenti parametri o opzioni nella pagina **Piani generali**:

- Scheda dettaglio **Generale**:

    - **Includi scorte disponibili**: in attesa del supporto *Consumo scorte disponibili*.
    - **Override disponibili**: in attesa del supporto *Consumo scorte disponibili*.
    - **Consuma scorte disponibili**: in attesa del supporto *Consumo scorte disponibili*.
    - **Includi transazioni scorte**: in attesa del supporto *Consumo scorte disponibili*.
    - **Includi offerte di vendita**: in attesa del supporto *Offerte di vendita*.
    - **Includi richiesta di offerta**: in attesa del supporto *Richiesta di offerte*.
    - **Utilizza date di durata a scaffale**: in attesa del supporto *Durata a scaffale*.
    - **Includi piano di continuità**: in attesa del supporto *Programmazione continuità*.
    - **Metodo di programmazione**: in attesa del supporto *Programmazione*.
    - **Proprietà limitata**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale di capacità di programmazione a ritroso**: in attesa del supporto *Programmazione*.
    - **Capacità limitata**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale capacità limitata**: in attesa del supporto *Programmazione*.
    - **Capacità limitata per risorse collo di bottiglia**: in attesa del supporto *Programmazione*.
    - **Intervallo temporale capacità per risorse collo di bottiglia**: in attesa del supporto *Programmazione*.
    - **Ordini pianificati**: Ottimizzazione pianificazione utilizza sequenze numeriche fisse.
    - **Sessione**: Ottimizzazione pianificazione utilizza sequenze numeriche fisse.
    - **Piano di continuità**: Ottimizzazione pianificazione utilizza sequenze numeriche fisse.

- Scheda dettaglio **Intervalli temporali in giorni**:

    - **Blocco**: il supporto *Intervallo temporale blocco* non è previsto in Ottimizzazione pianificazione.
    - **Esplosione**: in attesa del supporto *Programmazione*.
    - **Piano previsionale**: in attesa del supporto *Previsione* aggiuntivo.
    - **Capacità**: in attesa del supporto *Programmazione*.
    - **Piano di continuità**: in attesa del supporto *Programmazione continuità*.
    - **Messaggio di azione**: in attesa del supporto *Azioni*.
    - **Ritardi calcolati**: in attesa del supporto *Ritardi calcolati* aggiuntivo.
    - **Sequenza**: in attesa del supporto *Produzione*.

- Scheda dettaglio **Ritardi calcolati**:

    - **Assicurarsi che gli ordini pianificati non vengano creati prima della data di esecuzione della pianificazione generale**: in attesa del supporto *Ritardi calcolati*.
    - **Aggiungere il ritardo calcolato alla data del fabbisogno** (nella sezione **Ordini fornitore pianificati**): in attesa del supporto *Ritardi calcolati*.
    - **Aggiungere il ritardo calcolato alla data del fabbisogno** (nella sezione **Ordini di produzione pianificati**): in attesa del supporto *Ritardi calcolati*.
    - **Aggiungere il ritardo calcolato alla data del fabbisogno** (nella sezione **Trasferimento pianificato**): in attesa del supporto *Ritardi calcolati*.
    - **Aggiungere il ritardo calcolato alla data del fabbisogno** (nella sezione **Kanban pianificato**): in attesa del supporto *Ritardi calcolati*.

- Scheda dettaglio **Sequenza**:

    - **Ordini pianificati sequenza dopo pianificazione generale**: in attesa del supporto *Sequenza*.
    - **Tipo bucket**: in attesa del supporto *Sequenza*.
    - **Tipo periodo**: in attesa del supporto *Sequenza*.
    - **Numero di bucket nel ciclo della campagna**: in attesa del supporto *Sequenza*.

## <a name="released-product-details-page"></a>Pagina Dettagli prodotto rilasciato

Ottimizzazione pianificazione non utilizza il seguente parametro o opzione nella pagina **Dettagli prodotto rilasciato**:

- Scheda dettaglio **Tecnico**:

    - **Tipo di produzione**: Ottimizzazione pianificazione non supporta l'opzione *Elemento di pianificazione*. In attesa del supporto *Elementi di pianificazione*.

## <a name="default-order-settings-page"></a>Pagina Impostazioni ordine predefinite

Ottimizzazione pianificazione non utilizza il seguente parametro o opzione nella pagina **Impostazioni ordine predefinite**:

- Scheda dettaglio **Scorte**:

    - **Controllo data di consegna**: Ottimizzazione pianificazione non supporta l'opzione *CTP*, in attesa del supporto *CTP*.

## <a name="working-time-calendars-page"></a>Pagina Calendari orario di lavoro

Ottimizzazione pianificazione non utilizza il seguente parametro nella pagina **Calendari orario di lavoro**:

- **Calendario di base**: in attesa del supporto *Calendari di base*.

## <a name="batch-disposition-master-page"></a>Pagina Smaltimento generale batch

Ottimizzazione pianificazione non utilizza il seguente parametro nella pagina **Smaltimento generale batch**:

- Scheda dettaglio **Impostazione**:

    - **Nettificabile**: in attesa del supporto *Codici smaltimento batch*.
