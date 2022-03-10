---
title: Genera report finanziari
description: In questo argomento sono riportate informazioni sulla generazione di un report finanziario.
author: jinniew
ms.date: 02/08/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: kfend
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 00a860089265800ca1a0058f222d5e85c360501c
ms.sourcegitcommit: 6a269db08e8bb3bb3405c9f4a512091d13c80faa
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2022
ms.locfileid: "8119529"
---
# <a name="generate-financial-reports"></a>Genera report finanziari

[!include [banner](../includes/banner.md)]

In questo argomento sono riportate informazioni sulla generazione di un report finanziario.

Per generare un report, aprire la definizione di report e selezionare il pulsante **Genera** nella barra degli strumenti. Viene visualizzata la pagina **Stato coda report** che indica la posizione del report nella coda.

Durante la generazione del report, i seguenti indicatori di stato della coda di report possono essere visualizzati nella pagina **Stato coda report**.

| Status          | Stato | Description|
|-----------------|--------|--------------------|
| Inserimento in coda        | Provvisorio |La definizione del report viene convalidata prima che il report venga inserito nella coda di generazione.                    |
| In coda          | Provvisorio | Il report entra nella coda di generazione di report e attende di essere elaborato.                      |
| Elaborazione      | Provvisorio | Questo stato segue in genere lo stato **In coda** e di solito diventa **Finale** al termine dell'elaborazione.       |
| Post-elaborazione | Provvisorio | Questo stato segue lo stato **Elaborazione** e indica che tutti i dati del report sono stati raccolti, ma che vengono eseguite azioni derivate, come il calcolo e il rollup.            |
| Annullamento      | Provvisorio | La generazione del report viene annullata su richiesta dell'utente. Questo stato risulta da un annullamento richiesto dall'utente di un report il cui stato è **In coda** o **Elaborazione**. Il sistema tenta di attivare lo stato **Annullato** per il report, a meno che il sistema non sia troppo avanti e debba finalizzarlo in un altro stato. |
| Annullata        | Finale | L'elaborazione del report è terminata ma non è stata completata a causa di un'interruzione richiesta dall'utente.            |
| Completato       | Finale | Il report è pronto per l'uso.                      |
| Non pronto          | Finale | L'elaborazione del report è terminata ma non è riuscita e il report non deve essere utilizzato. |

Per impostazione predefinita, il report generato si aprirà nel Visualizzatore Web. Per la generazione di report sono disponibili le opzioni seguenti:

- Impostare una programmazione per generare un report o un gruppo di report automaticamente
- Verificare la presenza di conti o dati mancanti in un report e convalidare l'accuratezza di un report

Quando si genera un report, vengono usate le opzioni specificate nelle schede di Definizione di report .

## <a name="generate-a-financial-report"></a>Genera un report finanziario

Per generare un report finanziario passare a **Contabilità generale** \> **Richieste di informazioni e report** \> **Report finanziari**.

- Selezionare un report da generare e selezionare **Genera**.
- Compilare il campo **Data report** e selezionare **OK**.

Dopo avere generato il report, questo sarà disponibile nella sezione **Report**.

È possibile selezionare **Visualizza** o **Elimina** per visualizzare o eliminare il report.

Per generare un report utilizzando **Progettazione report**, aprire la definizione del report e quindi selezionare il pulsante **Genera** nella barra degli strumenti. Verrà visualizzata la pagina **Stato coda report** che indica la posizione del report nella coda. Per impostazione predefinita, il report generato si aprirà nel Visualizzatore Web.

## <a name="report-groups"></a>Gruppi di report

I gruppi di report sono un modo efficace di generare vari report contemporaneamente. Ad esempio, supponiamo che a fine mese gli utenti generino otto report ogni mese. Creare un gruppo di report e anziché selezionare **Genera** per ciascuno degli otto report nel gruppo, è possibile selezionare **Genera** per il gruppo di report e gli otto report verranno generati in un unico passaggio. Quando i report nel gruppo di report selezionato sono stati generati, è possibile selezionare **Report finanziari** (**Contabilità generale > Richieste di informazioni e report > Report finanziari**) per visualizzare singoli report. Completare i seguenti passaggi per impostare un gruppo di report.

1. In Progettazione report, selezionare **Gruppi di report**. 
2. Selezionare le definizioni di report esistenti da includere nel gruppo di report. 
3. Selezionare le impostazioni di override relative a società, dettagli e data di ogni report che verrà incluso nel gruppo.
   Si consiglia di impostare **Società**, **Periodo**, **Anno** e **Livello dettagli** per ogni report. 
4. Salvare il gruppo di report.

## <a name="schedule-report-generation"></a>Pianificare la generazione di report
Molte società dispongono di un set di report di base che vengono eseguiti a intervalli pianificati per l'allineamento con i processi aziendali. È possibile programmare un report in modo che sia generato regolarmente, ad esempio a frequenza giornaliera, settimanale, mensile o annuale. Può trattarsi di un singolo report o di un gruppo di report in cui sono incluse molte società. È necessario immettere le credenziali per ognuna della società specificate, ad esempio quelle incluse in una definizione di albero gerarchico. Se le credenziali non sono valide, nel report vengono visualizzate solo le informazioni per cui si dispone delle autorizzazioni di accesso, ad esempio la società a cui si è connessi al momento. Le informazioni di output vengono lette innanzitutto dal gruppo di report e quindi dai singoli report.

Quando le programmazioni report vengono create e salvate, vengono visualizzate nel pannello di navigazione in Programmazioni report. Per organizzare i report è possibile creare cartelle. Se un singolo report in una pianificazione non viene eseguito, tutti gli altri report continueranno ad esserlo.

> [!IMPORTANT]
> Per creare, modificare ed eliminare pianificazioni di report, è necessario disporre del ruolo di progettista o amministratore. Quando un report viene eseguito, le credenziali dell'utente che ha creato la programmazione vengono utilizzate per generare il report.

### <a name="create-a-report-schedule"></a>Creare una programmazione di report

1. In Progettazione report, nel menu **File** selezionare **Nuovo**, quindi selezionare **Programmazione report**. Verrà visualizzata la finestra di dialogo **Nuova programmazione report**.
2. In **Impostazioni**, selezionare un unico report o un gruppo di report da programmare. Sono disponibili solo report o gruppi di report per la società o la selezione di blocchi predefiniti a cui si è attualmente connessi.
3. Selezionare la casella di controllo **Attivo** per abilitare la programmazione dei report. Solo il creatore del report o un amministratore può attivare o disattivare una pianificazione di report.
4. Selezionare il pulsante **Autorizzazioni** per immettere le credenziali della società. Per impostazione predefinita, vengono utilizzate le informazioni di accesso per la società a cui si è connessi. Se sono incluse altre società, ad esempio nelle definizioni di albero gerarchico, selezionare **Usa credenziali distinte**, quindi immettere le credenziali per tutte le altre società incluse nella programmazione di report. È possibile selezionare **Autenticazione di Windows** o immettere un nome utente e una password per ogni società. Selezionare la casella di controllo **Salva credenziali** per salvare le credenziali per queste società e quindi selezionare **OK** per chiudere la finestra di dialogo.
5. In **Frequenza**, nel campo **Inizio ricorrenza**, selezionare la data in cui la programmazione deve iniziare. Per impostazione predefinita, viene selezionata la data di sistema corrente del computer client.
6. Nel campo **Esegui report in**, selezionare l'ora in cui eseguire il report. Se si immette un'ora precedente all'ora di sistema corrente, il report verrà eseguito alla data pianificata successiva.
7. Nell area **Criterio ricorrenza**, specificare la frequenza con cui il report viene eseguito. Per impostazione predefinita, è selezionato **Giornaliero** per un valore di intervallo (giorni) di 1. Altre opzioni includono Settimanale, Mensile e Annuale.
8. Nell'area Criterio di ricorrenza selezionare la data in cui dovrà essere arrestata la generazione del report.

    - **Nessuna data di fine** – La programmazione di report viene eseguita in modo illimitato.
    - **Imposta numero di ricorrenze** – La programmazione di report viene eseguita per il numero di volte specificato e viene quindi disattivata.
    - **Fine entro** – La programmazione di report termina alla data specificata.

9. Selezionare **Salva**. Nella finestra di dialogo **Salva con nome** specificare un nome univoco e una descrizione per la programmazione di report.

Per copiare una programmazione di report, è necessario disporre del ruolo di designer o amministratore. Anche se un amministratore modifica la programmazione di report, il report mantiene le credenziali dell'utente che ha creato il report.

### <a name="copy-a-report-schedule"></a>Copiare una programmazione di report

1. In Progettazione report, selezionare **Programmazioni report** nel pannello di navigazione e aprire una programmazione di report da copiare.
2. Nel menu **File**, selezionare **Salva con nome** e immettere un nuovo nome e una nuova descrizione per la programmazione nella finestra di dialogo **Salva con nome**. Selezionare **OK** e la nuova programmazione apparirà nel pannello di navigazione.
3. Nella nuova programmazione, modificare i campi e le informazioni in base alle necessità quindi selezionare **Salva** nella barra degli strumenti oppure selezionare **Salva** nel menu **File**.

Per eliminare una programmazione di report, è necessario essere il proprietario della programmazione di report o disporre del ruolo di amministratore.

### <a name="delete-a-report-schedule"></a>Eliminare una programmazione di report

1. In Progettazione report, nel pannello di navigazione, selezionare **Programmazioni report**.
2. Selezionare la programmazione di report da eliminare e selezionare **Elimina** o premere il tasto **CANC**.
3. Nella finestra di dialogo di verifica dell'eliminazione, selezionare **Sì** per definitivamente eliminare la programmazione di report. Se non si dispone delle autorizzazioni per eliminare la programmazione, verrà visualizzato un messaggio e il report non verrà eliminato.

### <a name="credentials-and-report-schedules"></a>Credenziali e pianificazioni di report

Se non si immettono le credenziali necessarie per tutte le società incluse nei report, si riceve un messaggio di questo tipo quando si salva la programmazione di report: "È necessario immettere le credenziali per le società che sono contenute nella programmazione di report. Fare clic sul pulsante Autorizzazioni per immettere le credenziali".

Un utente esegue ad esempio l'accesso alla società A con un account di accesso e una password. L'utente crea una programmazione per un report che utilizza una definizione di albero gerarchico per raccogliere i dati da più società. Quando salva la pianificazione di report, all'utente viene richiesto di immettere le credenziali per le altre società specificate nella definizione di albero gerarchico. Quando le credenziali scadono, i report interessati nella programmazione di report non vengono generati fino all'aggiornamento delle credenziali. Verrà visualizzato un messaggio nella coda di report per indicare che le autorizzazioni devono essere aggiornate. La programmazione di report ha esito negativo se uno dei seguenti scenari si verifica (perché richiedono le credenziali):

- Una società è stata aggiunta a un albero gerarchico per un singolo report.
- Un report in un gruppo di report è stato modificato.
- Un nuovo report per una società aggiuntiva è stato aggiunto a un gruppo di report.

Per continuare, selezionare il pulsante **Autorizzazioni** nella finestra di dialogo **Progammazione report**, quindi immettere le credenziali appropriate.

## <a name="missing-account-analysis-feature"></a>Funzionalità di analisi dei conti mancanti
È possibile individuare i conti finanziari e le dimensioni che potrebbero mancare in tutte le definizioni di riga, definizioni di albero gerarchico e definizioni di report in un gruppo di blocchi predefiniti. Questa funzione è utile quando si creano o si aggiornano diversi conti o blocchi predefiniti in un breve periodo e si desidera verificare che tutte le nuove informazioni siano incluse nei report.

I conti mancanti vengono determinati utilizzando i valori minimo e massimo dalla definizione di riga o la definizione di albero gerarchico e quindi viene visualizzato un elenco dei conti che non sono nella definizione di riga o la definizione di albero gerarchico, ma sono nei dati finanziari. Se il numero di un conto mancante è maggiore o minore di quello dei valori nella definizione di riga, tale conto non viene incluso nell'elenco di conti mancanti.

> [!TIP]
> Ai fini della convalida, questo processo deve essere eseguito prima di generare i report mensili e quando si creano nuovi blocchi predefiniti.

Report con intervalli di valori hanno minori probabilità di avere conti mancanti. Quando possibile, utilizzare gli intervalli nel blocco predefinito per includere i nuovi conti quando vengono creati. Se una definizione di report è impostata sulla società @ANY, è possibile accedere a una società specifica ed eseguire per quest'ultima un'analisi dei conti mancanti.

> [!NOTE]
> Se una nuova società è stata aggiunta, è necessario aggiungere la nuova società agli alberi gerarchici in tutti i report esistenti o la società non verrà inclusa nell'analisi dei conti mancanti.

### <a name="run-missing-account-analysis"></a>Eseguire l'analisi dei conti mancanti

1. In Progettazione report, selezionare **Strumenti**, quindi selezionare **Analisi conti mancanti**.
2. Nel campo **Filtro società**, selezionare una società per la quale filtrare i risultati, o selezionare **Tutto (senza filtro)** per visualizzare i risultati di tutte le società disponibili.
3. Nel campo **Filtro dimensioni**, selezionare una dimensione in base a cui filtrare i risultati o selezionare **Tutto (senza filtro)** per visualizzare tutte le informazioni sulle dimensioni per tutte le dimensioni disponibili.
4. Nel campo **Raggruppa per** selezionare un'opzione per ordinare i risultati. È possibile ordinare i risultati in base al blocco predefinito interessato oppure in base ai set di dimensioni o di valori.
5. Esaminare i risultati visualizzati. Quando si seleziona un elemento nel riquadro superiore, nel riquadro inferiore vengono visualizzate informazioni aggiuntive sull'eccezione, compresi dimensioni, valori e report.
6. Per aprire l'elemento interessato, selezionare l'icona associata visualizzata nel riquadro dell'elenco, o fare clic con il pulsante destro del mouse sull'elemento e selezionare **Apri**. Per selezionare più elementi, tenere premuto il tasto **CTRL** mentre si selezionano gli elementi nel riquadro inferiore.
7. Se vengono restituiti valori, blocchi predefiniti, o report che non devono essere inclusi nell'analisi, fare clic con il pulsante destro del mouse sull'elemento e selezionare **Escludi** o selezionare la casella di controllo **Escludi** accanto all'elemento per rimuoverlo dall'elenco. Gli elementi esclusi non vengono inclusi quando l'elenco viene aggiornato. Per selezionare più elementi, tenere premuto il tasto **CTRL** mentre si selezionano gli elementi nel riquadro inferiore. Per visualizzare tutti gli elementi, inclusi eventuali risultati che in precedenza si è scelto di escludere dall'analisi, selezionare la casella di controllo **Mostra blocchi predefiniti e valori esclusi**, quindi selezionare **Aggiorna**.
8. Selezionare **Aggiorna** per aggiornare le eccezioni gestite. Selezionare **Sì** per eseguire un aggiornamento completo di tutti risultati, o selezionare **No** per eseguire un aggiornamento parziale degli elementi gestiti.

    > [!NOTE]
    > Il modulo viene aggiornato automaticamente quando si apre, a meno che non sia stato aperto negli ultimi 15 minuti.

9. Quando i problemi sono risolti, selezionare **OK** per chiudere la finestra di dialogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Tasti di scelta rapida per l'analisi dei conti mancanti
Quando si esegue un'analisi dei conti mancanti, sono disponibili i seguenti tasti di scelta rapida.

| Azione                           | Premere  |
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


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
