---
title: Area di lavoro Gestione personale
description: Questo argomento descrive gli elementi concettuali dell'area di lavoro Gestione personale.
author: twheeloc
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmPosition, HcmPersonnelManagementWorkspace
audience: Application User
ms.author: twheeloc
ms.reviewer: twheeloc
ms.search.scope: Human Resources
ms.custom: 269054
ms.assetid: 889a8fab-0eef-45c2-91fc-ff2f4d44d54f
ms.search.region: Global
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 4332be972ab3dc81e7e4f3cc297a91cd247e721e
ms.sourcegitcommit: 7e0e2a266d9a9473df72e207554d9bd150e17ce3
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/05/2021
ms.locfileid: "7771340"
---
# <a name="personnel-management-workspace"></a>Area di lavoro Gestione personale

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L'area di lavoro **Gestione personale** include una grande quantità di contenuti. Contiene i movimenti del personale, tiene traccia delle modifiche dei dipendenti, delle posizioni aperte, delle variazioni degli indirizzi, dei record in scadenza e delle analisi e fornisce collegamenti a informazioni specifiche. Questo argomento fornisce informazioni dettagliate su ogni parte dell'area di lavoro.

## <a name="activity-tab"></a>Scheda Attività

La scheda **Attività** contiene sezioni che raggruppano i lavoratori in base alla fase raggiunta nel processo di assunzione:

- **Candidati da assumere**
- **Inizio a breve**
- **Assunti di recente**
- **Uscita**
- **Usciti**

Quando un lavoratore si trova in una di queste fasi, sono disponibili azioni specifiche come pulsanti sulla scheda o nel menu che appare quando si selezionano i puntini di sospensione (**...**) nell'angolo in alto a destra. Le seguenti sottosezioni descrivono le sezioni della scheda **Attività** ed elencano le azioni disponibili.

### <a name="candidates-to-hire"></a>Candidati da assumere

La sezione **Candidati da assumere** dell'area di lavoro viene compilata da più origini:

- Un'entità Open Data Protocol (OData)
- Integrazione di LinkedIn
- Dati inseriti manualmente nel prodotto

Quando i candidati vengono visualizzati nella sezione **Candidati da assumere**, è possibile eseguire le seguenti azioni selezionando i puntini di sospensione sulla carta del candidato:

- **Chiudi il candidato**
- **Non assumere**
- **Assumi**

> [!NOTE]
> Se la lista dei candidati viene compilata da Microsoft Dataverse, gli stessi candidati verranno visualizzati in tutte le persone giuridiche perché una persona giuridica non è stata associata al candidato.

### <a name="starting-soon"></a>Inizio a breve

La sezione **Inizio imminente** elenca i lavoratori con una data di inizio futura. L'elenco viene ordinato in base alla data di inizio. Viene elencata per prima la data di inizio più vicina alla data odierna.

Se il responsabile non compare sulla scheda, non è stata assegnata una posizione per il lavoratore.

> [!NOTE] 
> È consigliabile assegnare una posizione a un lavoratore prima di applicare un elenco di controllo. A volte, le attività di onboarding vengono assegnate al responsabile di un dipendente appena assunto. Tuttavia, se non viene assegnata alcuna posizione, non è possibile determinare il responsabile del nuovo dipendente. In tal caso, le attività di onboarding destinate al responsabile verranno invece assegnate al proprietario della lista di controllo.

Quando i lavoratori compaiono nella sezione **Inizio imminente**, sono disponibili le seguenti azioni:

- Assegna posizione
- Verifica impiego
- Assegna retribuzione fissa
- Assegna retribuzione variabile
- Visualizza nella gerarchia
- Applica elenco di controllo\*\*

\*\*Questa è l'azione predefinita. È disponibile come pulsante nella scheda.

### <a name="recent-hires"></a>Assunti di recente

La sezione **Assunzioi recenti** elenca i lavoratori con una data di inizio nel recente passato. L'elenco viene ordinato in base alla data di inizio. Viene elencata per prima la data di inizio più vicina alla data odierna.

Per impostazione predefinita, l'elenco mostra i lavoratori assunti negli ultimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, definire un intervallo di tempo per **Assunzioni recenti**. I dati nella sezione **Assunzioni recenti** possono essere visualizzati per un numero specifico di giorni, mesi o anni. Ad esempio, per visualizzare l'elenco dei lavoratori assunti negli ultimi 14 giorni, impostare il campo **Periodo** su **14** e il campo **Unità** su **giorni**.

> [!NOTE]
> Le impostazioni nella pagina **Parametri di Human Resources** sono specifiche dell'azienda. Pertanto, l'intervallo di tempo per cui si visualizzano le assunzioni recenti può variare in base all'azienda. Ad esempio, nella società USMF, è possibile visualizzare tutte le nuove assunzioni degli ultimi sette giorni. Tuttavia, nella società USSI, è consigliabile visualizzare tutte le nuove assunzioni degli ultimi 14 giorni. In questo caso, apri la pagina **Parametri di Human Resources** in ogni azienda e impostare i parametri come richiesto.

Se il responsabile non compare sulla scheda, non è stata assegnata una posizione per il lavoratore.

Quando i lavoratori vengono visualizzati nella sezione **Assunzioni recenti**, sono disponibili le seguenti azioni:

- Assegna posizione
- Verifica impiego
- Retribuzione fissa
- Assegna retribuzione variabile
- Visualizza in gerarchia
- Applica elenco di controllo\*\*

\*\*Questa è l'azione predefinita. È disponibile come pulsante nella scheda.

### <a name="exiting"></a>Uscita

La sezione **Fine rapporto** elenca i lavoratori con una data di fine rapporto nel futuro. L'elenco viene ordinato in base alla data di fine rapporto. Viene elencata per prima la data di fine rapporto più vicina alla data odierna. 

Per impostazione predefinita, l'elenco mostra i lavoratori con una data di fine rapporto nei prossimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, definire un intervallo di tempo per **Visualizza lavoratori prossimi alla data di fine rapporto**. I dati nella sezione **Fine rapporto** possono essere visualizzati per un numero specifico di giorni, mesi o anni. Ad esempio, per visualizzare l'elenco dei lavoratori che giungeranno a fine rapporto negli ultimi 14 giorni, impostare il campo **Periodo** su **14** e il campo **Unità** su **Giorni**.

Quando i lavoratori compaiono nella sezione **Fine rapporto**, sono disponibili le seguenti azioni:

- Applica elenco di controllo\*\*
- Verifica impiego
- Visualizza nella gerarchia

\*\*Questa è l'azione predefinita. È disponibile come pulsante nella scheda.

### <a name="exited"></a>Usciti

La sezione **Giunti a fine rapporto** elenca i lavoratori con una data di fine rapporto nel recente passato. L'elenco viene ordinato in base alla data di fine rapporto. Viene elencata per prima la data di fine rapporto più vicina alla data odierna.

Per impostazione predefinita, l'elenco mostra i lavoratori con una data di fine rapporto negli ultimi sette giorni. Per modificare questa impostazione, nella pagina **Parametri di Human Resources**, nella scheda **Generale**, definire un intervallo di tempo per **Visualizza lavoratori giunti alla data di fine rapporto**. I dati nella sezione **Giunti a fine rapporto** possono essere visualizzati per un numero specifico di giorni, mesi o anni. Ad esempio, per visualizzare l'elenco dei lavoratori giunti a fine rapporto negli ultimi 14 giorni, impostare il campo **Periodo** su **14** e il campo **Unità** su **Giorni**.

Quando i lavoratori compaiono nella sezione **Giunti a fine rapporto**, sono disponibili le seguenti azioni:

- Applica elenco di controllo\*\*
- Verifica impiego
- Visualizza in gerarchia

\*\*Questa è l'azione predefinita. È disponibile come pulsante nella scheda.

## <a name="employee-changes-tab"></a>Scheda Modifiche dipendenti

La scheda **Modifiche dipendenti** fornisce un elenco di tutte le azioni del personale. Questo elenco non è disponibile per impostazione predefinita. Per abilitare la funzionalità, nella pagina **Parametri condivisi di Human Resources**, nella scheda **Azioni del personale**, impostare l'opzione **Abilita azioni lavoratore** su **Sì**.

## <a name="position-changes-tab"></a>Scheda Modifiche di posizione

La scheda **Modifiche di posizione** fornisce un elenco di tutte le azioni del personale associate alla posizione. Questo elenco non è disponibile per impostazione predefinita. Per abilitare la funzionalità, nella pagina **Parametri condivisi di Human Resources**, nella scheda **Azioni del personale**, impostare l'opzione **Abilita azioni posizione** su **Sì**.

## <a name="open-positions-tab"></a>Scheda Posizioni aperte

La scheda **Posizioni aperte** elenca tutte le posizioni aperte. Per essere presenti nell'elenco, le posizioni devono avere una data di attivazione odierna o precedente e non devono avere un'assegnazione di lavoratore corrente.

> [!NOTE]
> L'elenco considera l'assegnazione del lavoratore alla data odierna. Qualsiasi posizione con un'assegnazione di lavoratore con data futura continuerà a essere visualizzata nell'elenco. Tuttavia, una volta raggiunta la data di decorrenza dell'incarico lavoratore, la posizione verrà rimossa dall'elenco.

## <a name="expiring-records-tab"></a>Scheda Record in scadenza

La scheda **Record in scadenza** elenca tutti gli elementi scaduti o che scadranno per i lavoratori dell'azienda a cui l'utente ha effettuato l'accesso. I seguenti elementi vengono visualizzati nell'elenco:

- **Attestati**
- **Identificazione**
- **Periodi di prova**
- **Screening**
- **Test**

Per specificare se l'elenco mostra i record scaduti o i record in scadenza, nella pagina **Parametri di Human Resources**, nella pagina **Generale** definire un intervallo di tempo per **Record in scadenza** o **Record scaduti**. I dati nella scheda **Record in scadenza** possono essere mostrati per un numero specifico di giorni. Ad esempio, per visualizzare l'elenco dei record che scadranno nei prossimi 14 giorni, impostare il campo **Numero di giorni** su **14**.

> [!NOTE] 
> Se l'intervallo di tempo per **Record scaduti** o **Record in scadenza** viene impostato su **0** nella pagina **Parametri di Human Resources** l'elenco non mostrerà nessuno di questi record.

## <a name="employees-tile"></a>Riquadro Dipendenti

Il riquadro **Dipendenti** fornisce un conteggio di tutti i dipendenti impiegati nell'azienda a cui l'utente è attualmente connesso. Quando si seleziona il riquadro **Dipendenti**, una nuova pagina mostra i dettagli dei dipendenti.

## <a name="contractors-tile"></a>Riquadro Terzisti

Il riquadro **Terzisti** fornisce un conteggio di tutti i terzisti impiegati nell'azienda a cui l'utente è attualmente connesso. Quando si seleziona il riquadro **Terzisti**, una nuova pagina mostra i dettagli dei terzisti.

## <a name="open-positions-tile"></a>Riquadro Posizioni aperte

Il riquadro **Posizioni aperte** fornisce un conteggio di tutte le posizioni aperte. Quando si seleziona il riquadro **Posizioni aperte**, una nuova pagina mostra i dettagli delle posizioni aperte. Per essere incluse nel conteggio, le posizioni devono avere una data di attivazione odierna o precedente e non devono avere un'assegnazione di lavoratore corrente.

> [!NOTE]
> Il riquadro considera l'assegnazione del lavoratore alla data odierna. Qualsiasi posizione con un'assegnazione di lavoratore con data futura continuerà a essere inclusa nel conteggio. Tuttavia, una volta raggiunta la data di decorrenza dell'assegnazione lavoratore, la posizione verrà esclusa dal conteggio.

## <a name="approvals-tile"></a>Riquadro Approvazioni

Il riquadro **Approvazioni** fornisce un conteggio di tutti gli elementi del flusso di lavoro in attesa dell'approvazione dell'utente corrente. Quando si seleziona il riquadro **Approvazioni**, una nuova pagina mostra i dettagli degli elementi del flusso di lavoro che richiedono l'approvazione.

## <a name="address-changes-tile"></a>Riquadro Modifiche agli indirizzi

Il riquadro **Modifiche agli indirizzi** fornisce un conteggio di tutte le modifiche agli indirizzi avvenute durante il numero di giorni specificato nella pagina **Parametri di Human Resources**. Quando si seleziona il riquadro **Modifiche agli indirizzi**, una nuova pagina mostra i dettagli di eventuali modifiche agli indirizzi. Nell'angolo in alto a destra della pagina, è possibile selezionare **Includi future modifiche agli indirizzi future** per visualizzare le modifiche con una data futura.

Per ulteriori informazioni su come visualizzare e gestire le modifiche agli indirizzi, vedere [Visualizzare e gestire le modifiche agli indirizzi](hr-personnel-view-address-changes.md).
