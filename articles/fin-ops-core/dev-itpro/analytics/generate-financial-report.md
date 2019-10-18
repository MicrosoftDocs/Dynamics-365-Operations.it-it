---
title: Genera report finanziari
description: In questo argomento sono riportate informazioni sulla generazione di un report finanziario.
author: aprilolson
manager: AnnBe
ms.date: 09/26/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: c682ed96e47c718d3a9af1eb10aada75c59d3156
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2181843"
---
# <a name="generate-financial-reports"></a>Genera report finanziari

[!include [banner](../includes/banner.md)]

In questo argomento sono riportate informazioni sulla generazione di un report finanziario.

Per generare un report, aprire la definizione di report e quindi fare clic sul pulsante Genera nella barra degli strumenti. La finestra Stato coda report si aprirà e indicherà l'ubicazione del report nella coda. Per impostazione predefinita, il report generato si aprirà nel Visualizzatore Web.

Per la generazione di report sono disponibili le opzioni seguenti:

- Impostare una programmazione per generare un report o un gruppo di report automaticamente
- Verificare la presenza di conti o dati mancanti in un report e convalidare l'accuratezza di un report

Quando si genera un report, vengono usate le opzioni specificate nelle schede di Definizione di report .

## <a name="generate-a-financial-report"></a>Genera un report finanziario

Per generare un report finanziario passare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Report finanziari**.

- Selezionare un report da generare e fate clic su **Genera**.
- Compilare il campo **Data report** e fare clic su **OK**.

Dopo avere generato il report, questo sarà disponibile nella sezione **Report**.

È possibile selezionare **Visualizza** o **Elimina** per visualizzare o eliminare il report.

Per generare un report utilizzando **Progettazione report**, aprire la definizione del report e quindi fare clic sul pulsante Genera nella barra degli strumenti. La finestra Stato coda report si aprirà e indicherà l'ubicazione del report nella coda. Per impostazione predefinita, il report generato si aprirà nel Visualizzatore Web.

## <a name="schedule-report-generation"></a>Pianificare la generazione di report
Molte società dispongono di un set di report di base che vengono eseguiti a intervalli pianificati per l'allineamento con i processi aziendali. È possibile programmare un report in modo che sia generato regolarmente, ad esempio a frequenza giornaliera, settimanale, mensile o annuale. Può trattarsi di un singolo report o di un gruppo di report in cui sono incluse molte società. È necessario immettere le credenziali per ognuna della società specificate, ad esempio quelle incluse in una definizione di albero gerarchico. Se le credenziali non sono valide, nel report vengono visualizzate solo le informazioni per cui si dispone delle autorizzazioni di accesso, ad esempio la società a cui si è connessi al momento. Le informazioni di output vengono lette innanzitutto dal gruppo di report e quindi dai singoli report.

Quando le programmazioni report vengono create e salvate, vengono visualizzate nel pannello di navigazione in Programmazioni report. Per organizzare i report è possibile creare cartelle. Se un singolo report in una pianificazione non viene eseguito, tutti gli altri report continueranno ad esserlo.

> [!IMPORTANT]
> Per creare, modificare ed eliminare pianificazioni di report, è necessario disporre del ruolo di progettista o amministratore. Quando un report viene eseguito, le credenziali dell'utente che ha creato la programmazione vengono utilizzate per generare il report.

### <a name="create-a-report-schedule"></a>Creare una programmazione report

1. In Progettazione report, nel menu File fare clic su Nuovo, quindi selezionare Programmazione report. Verrà visualizzata la finestra di dialogo Nuova programmazione report.
2. In Impostazioni, selezionare un unico report o un gruppo di report da programmare. Sono disponibili solo report o gruppi di report per la società o la selezione di blocchi predefiniti a cui si è attualmente connessi.
3. Per attivare la pianificazione di report, selezionare la casella di controllo Attivo. Solo il creatore del report o un amministratore può attivare o disattivare una pianificazione di report.
4. Fare clic sul pulsante Autorizzazioni per immettere le credenziali della società. Per impostazione predefinita, vengono utilizzate le informazioni di accesso per la società a cui si è connessi. Se sono incluse altre società, ad esempio nelle definizioni di albero gerarchico, selezionare Usa credenziali distinte, quindi immettere le credenziali per tutte le altre società incluse nella pianificazione di report. È possibile selezionare Autenticazione di Windows o digitare un nome utente e una password per ogni società. Selezionare la casella di controllo Salva credenziali per salvare le credenziali per queste società e quindi fare clic su OK per chiudere la finestra di dialogo.
5. In Frequenza, nel campo Inizio ricorrenza, selezionare la data in cui la programmazione deve iniziare. Per impostazione predefinita, viene selezionata la data di sistema corrente del computer client.
6. Nel campo Esegui report in selezionare l'ora in cui dovrà essere eseguito il report. Se si immette un'ora precedente all'ora di sistema corrente, il report verrà eseguito alla data pianificata successiva.
7. Nell'area Criterio di ricorrenza specificare la frequenza di esecuzione del report. Per impostazione predefinita, è selezionato Giornaliero per un valore di intervallo (giorni) di 1. Altre opzioni includono Settimanale, Mensile e Annuale.
8. Nell'area Criterio di ricorrenza selezionare la data in cui dovrà essere arrestata la generazione del report.

    - Nessuna data di fine: la pianificazione del report viene eseguita all'infinito.
    - Imposta numero di occorrenze: la pianificazione del report viene eseguita per il numero di volte specificato, quindi viene disattivata.
    - Termina entro: la pianificazione del report termina alla data specificata.

9. Fare clic su Salva sulla barra degli strumenti. Nella finestra di dialogo Salva con nome specificare un nome univoco e una descrizione per la programmazione report.

Per copiare una programmazione report, è necessario disporre del ruolo di designer o amministratore. Anche se un amministratore modifica la programmazione report, il report mantiene le credenziali dell'utente che ha creato il report.

### <a name="copy-a-report-schedule"></a>Copiare una programmazione report

1. In Progettazione report, fare clic su Programmazioni report nel pannello di navigazione e aprire una programmazione report da copiare.
2. Scegliere Salva con nome dal menu File, quindi immettere un nuovo nome e una descrizione per la pianificazione nella finestra di dialogo Salva con nome. Fare clic su OK. La nuovo pianificazione verrà visualizzata nel riquadro di spostamento.
3. Nella nuova programmazione, modificare i campi e le informazioni in base alle necessità quindi fare clic su Salva sulla barra degli strumenti oppure fare clic su Salva nel menu File.

Per eliminare una programmazione report, è necessario essere il proprietario della programmazione report o disporre del ruolo di amministratore.

### <a name="delete-a-report-schedule"></a>Eliminare una programmazione report

1. In Progettazione report, nel pannello di navigazione, fare clic su Programmazioni report.
2. Selezionare la pianificazione di report da eliminare, quindi fare clic su Elimina o premere CANC.
3. Nella finestra di dialogo di verifica dell'eliminazione scegliere Sì per eliminare definitivamente la pianificazione di report. Se non si dispone delle autorizzazioni per eliminare la programmazione, verrà visualizzato un messaggio e il report non verrà eliminato.

### <a name="credentials-and-report-schedules"></a>Credenziali e pianificazioni di report

Se non si immettono le credenziali necessarie per tutte le società incluse nei report, si riceve un messaggio di questo tipo quando si salva la programmazione report: "È necessario immettere le credenziali per le società che sono contenute nella programmazione report. Fare clic sul pulsante Autorizzazioni per immettere le credenziali".

Un utente esegue ad esempio l'accesso alla società A con il proprio account di accesso e la propria password. Crea una programmazione per un report che utilizza una definizione di albero gerarchico per raccogliere i dati da più società. Quando salva la pianificazione di report, all'utente viene richiesto di immettere le credenziali per le altre società specificate nella definizione di albero gerarchico. Quando le credenziali scadono, i report interessati nella programmazione report non vengono generati fino all'aggiornamento delle credenziali. Verrà visualizzato un messaggio nella coda di report per indicare che le autorizzazioni devono essere aggiornate. La programmazione report ha esito negativo se uno dei seguenti scenari si verifica (perché richiedono le credenziali):

- Una società è stata aggiunta a un albero gerarchico per un singolo report.
- Un report in un gruppo di report è stato modificato.
- Un nuovo report per una società aggiuntiva è stato aggiunto a un gruppo di report.

Per continuare, fare clic sul pulsante Autorizzazioni nella finestra di dialogo Progammazione report, quindi immettere le credenziali appropriate.

## <a name="missing-account-analysis-feature"></a>Funzionalità di analisi dei conti mancanti
È possibile individuare i conti finanziari e le dimensioni che potrebbero mancare in tutte le definizioni di riga, definizioni di albero gerarchico e definizioni di report in un gruppo di blocchi predefiniti. Questa funzione è utile quando si creano o si aggiornano diversi conti o blocchi predefiniti in un breve periodo e si desidera verificare che tutte le nuove informazioni siano incluse nei report.

I conti mancanti vengono determinati utilizzando i valori minimo e massimo dalla definizione di riga o la definizione di albero gerarchico e quindi viene visualizzato un elenco dei conti che non sono nella definizione di riga o la definizione di albero gerarchico, ma sono nei dati finanziari. Se il numero di un conto mancante è maggiore o minore di quello dei valori nella definizione di riga, tale conto non viene incluso nell'elenco di conti mancanti.

> [!TIP]
> Ai fini della convalida, questo processo deve essere eseguito prima di generare i report mensili e quando si creano nuovi blocchi predefiniti.

Report con intervalli di valori hanno minori probabilità di avere conti mancanti. Quando possibile, utilizzare gli intervalli nel blocco predefinito per includere i nuovi conti quando vengono creati. Se una definizione di report è impostata sulla società @ANY, è possibile accedere a una società specifica ed eseguire per quest'ultima un'analisi dei conti mancanti.

> [!NOTE]
> Se una nuova società è stata aggiunta, è necessario aggiungere la nuova società agli alberi gerarchici in tutti i report esistenti o la società non verrà inclusa nell'analisi dei conti mancanti.

### <a name="run-missing-account-analysis"></a>Eseguire l'analisi dei conti mancanti

1. In Progettazione report, fare clic su Strumenti, quindi fare clic su Analisi conti mancanti.
2. Nel campo Filtro società selezionare una società per la quale filtrare i risultati oppure selezionare Tutto (nessun filtro) per visualizzare i risultati di tutte le società disponibili.
3. Nel campo Filtro dimensioni selezionare una dimensione per la quale filtrare i risultati oppure selezionare Tutto (nessun filtro) per visualizzare le informazioni per tutte le dimensioni disponibili.
4. Nel campo Raggruppa per selezionare un'opzione per l'ordinamento dei risultati. È possibile ordinare i risultati in base al blocco predefinito interessato oppure in base ai set di dimensioni o di valori.
5. Esaminare i risultati visualizzati. Quando si seleziona un elemento nel riquadro superiore, nel riquadro inferiore vengono visualizzate informazioni aggiuntive sull'eccezione, compresi dimensioni, valori e report.
6. Per aprire l'elemento interessato, fare clic sull'icona associata visualizzata nel riquadro dell'elenco, o fare clic con il pulsante destro del mouse sull'elemento e selezionare Apri. Per selezionare più elementi, tenere premuto il tasto Ctrl mentre si selezionano gli elementi nel riquadro inferiore.
7. Se vengono restituiti valori, blocchi predefiniti, o report che non devono essere inclusi nell'analisi, fare clic con il pulsante destro del mouse sull'elemento e selezionare Escludi o selezionare la casella di controllo Escludi accanto all'elemento per rimuoverlo dall'elenco. Gli elementi esclusi non vengono inclusi quando l'elenco viene aggiornato. Per selezionare più elementi, tenere premuto CTRL mentre si selezionano gli elementi desiderati nel riquadro inferiore. Per visualizzare tutti gli elementi, inclusi eventuali risultati che in precedenza si è scelto di escludere dall'analisi, selezionare la casella di controllo Mostra blocchi predefiniti e valori esclusi, quindi fare clic su Aggiorna.
8. Fare clic su Aggiorna per aggiornare le eccezioni risolte. Fare clic su Sì per eseguire un aggiornamento completo di tutti i risultati oppure su No per eseguire un aggiornamento parziale degli elementi risolti.

    > [!NOTE]
    > Il modulo viene aggiornato automaticamente quando si apre, a meno che non sia stato aperto negli ultimi 15 minuti.

9. Quando i problemi sono risolti, fare clic su OK per chiudere la finestra di dialogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Tasti di scelta rapida per l'analisi dei conti mancanti
Quando si esegue un'analisi dei conti mancanti, sono disponibili i seguenti tasti di scelta rapida.

| Operazione da eseguire                           | Utilizzare questo tasto di scelta rapida |
|--------------------------------------|----------------------------|
| Filtrare per società                    | Alt+C                      |
| Filtro per dimensioni                  | ALT+D                      |
| Selezione del campo Raggruppa per            | Alt+G                      |
| Visualizzazione di blocchi e valori esclusi      | Alt+S                      |
| Aggiornamento dei risultati                      | Alt+R                      |
| Esclusione del blocco predefinito selezionato  | Alt+X                      |
| Esclusione della definizione di riga selezionata  | Ctrl+B                     |
| Esclusione del valore di dimensione selezionato | Ctrl+D                     |
| Apertura della definizione di report selezionata  | Ctrl+R                     |
| Apertura della definizione di riga selezionata     | Ctrl+O                     |


## <a name="additional-resources"></a>Risorse aggiuntive

[Creazione di report finanziari](financial-reporting-intro.md)

[Interfaccia di Progettazione report](report-designer-interface.md)
