---
title: Genera un report finanziario
description: In questo argomento sono riportate informazioni sulla generazione di un report finanziario.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: FinancialReports
audience: Application User
ms.reviewer: ShylaThompson
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 68843
ms.assetid: 271df6f4-12b7-4b3e-b2d7-36ea98ef1871
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 9b0d8fd9f5ae9d99f299cc71d7caef021ad3fb9d
ms.contentlocale: it-it
ms.lasthandoff: 05/25/2017


---

# <a name="generate-a-financial-report"></a>Genera un report finanziario

[!include[banner](../includes/banner.md)]


In questo argomento sono riportate informazioni sulla generazione di un report finanziario. 

Per generare un report, aprire la definizione di report e quindi fare clic sul pulsante Genera nella barra degli strumenti. La finestra Stato coda report si aprirà e indicherà l'ubicazione del report nella coda. Per impostazione predefinita, il report generato si aprirà nel Visualizzatore Web.
| ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**        |
|------------------------------------------------------------------------------------------------|
| È possibile generare report solo in cartelle e ubicazioni per cui si dispone delle autorizzazioni di accesso. |

Nella seguente tabella vengono illustrate le opzioni disponibili per la generazione dei report.

| Opzione                                                                                | Ulteriori informazioni |
|---------------------------------------------------------------------------------------|----------------------|
| Impostare una programmazione per generare un report o un gruppo di report automaticamente              |                      |
| Verificare la presenza di conti o dati mancanti in un report e convalidare l'accuratezza di un report |                      |

Quando si genera un report, vengono usate le opzioni specificate nelle schede di Definizione di report . La scheda Output e distribuzione consente di specificare un'ubicazione della raccolta report, che fornisce un modo semplice di condividere il report.

## <a name="schedule-report-generation"></a> Programmare la generazione di report
Molte società hanno una serie di base di report che vengono eseguiti a intervalli programmati perché siano allineati con i relativi processi aziendali. È possibile programmare un report in modo che sia generato regolarmente, ad esempio a frequenza giornaliera, settimanale, mensile o annuale. Può essere un unico report o un gruppo di report che include più società. È necessario immettere le credenziali per ciascuna società specificata, ad esempio quelle in una definizione di albero gerarchico. Se le credenziali non sono valide, nel report vengono visualizzate solo le informazioni per cui si dispone delle autorizzazioni di accesso, ad esempio la società a cui si è connessi al momento. Le informazioni di output vengono lette innanzitutto dal gruppo di report e quindi dai singoli report.

Quando le programmazioni report vengono create e salvate, vengono visualizzate nel pannello di navigazione in Programmazioni report. È possibile creare cartelle per organizzare i report. Se un singolo report in una programmazione non viene eseguito, l'esecuzione continuerà per tutti gli altri report.
| ![Importante](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Importante")**Importante**                                                                                                           |
|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Per creare, modificare ed eliminare programmazioni report, è necessario disporre del ruolo di designer o amministratore. Quando un report viene eseguito, le credenziali dell'utente che ha creato la programmazione vengono utilizzate per generare il report. |

### <a name="create-a-report-schedule"></a>Creare una programmazione report

1.  In Progettazione report, nel menu File fare clic su Nuovo, quindi selezionare Programmazione report. Verrà visualizzata la finestra di dialogo Nuova programmazione report.
2.  In Impostazioni, selezionare un unico report o un gruppo di report da programmare. Solo i report o gruppi di report per la società o la selezione di blocco predefinito a cui si è attualmente connessi sono disponibili.
3.  Selezionare la casella di controllo Attivo per abilitare la programmazione report. Solo l'autore del report o un amministratore può attivare o disattivare una programmazione report.
4.  Fare clic sul pulsante Autorizzazioni per immettere le credenziali della società. Per impostazione predefinita, vengono utilizzate le informazioni di accesso per la società a cui si è connessi. Se altre società sono incluse, ad esempio in definizioni di albero gerarchico, selezionare Usa credenziali separate quindi immettere le credenziali per qualsiasi altra società inclusa nella programmazione report. È possibile selezionare Autenticazione di Windows o immettere un nome utente e una password per ogni società. Selezionare la casella di controllo Salva credenziali per salvare le credenziali per queste società e quindi fare clic su OK per chiudere la finestra di dialogo.
5.  In Frequenza, nel campo Inizio ricorrenza, selezionare la data in cui la programmazione deve iniziare. Per impostazione predefinita, la data di sistema corrente del computer client è selezionata.
6.  Nel campo Esegui report alle, selezionare l'ora in cui eseguire il report. Se si immette un'ora precedente all'ora di sistema corrente, il report viene eseguito alla data programmata successiva.
7.  Nell area Criterio ricorrenza, specificare la frequenza con cui il report viene eseguito. Per impostazione predefinita, è selezionato Giornaliero per un valore di intervallo (giorni) di 1. Altre opzioni includono Settimanale, Mensile e Annuale.
8.  Nell'area Intervallo di ricorrenza, specificare quando la generazione del report deve essere interrotta.
    -   Nessuna data di fine – la programmazione report viene eseguita in modo illimitato.
    -   Imposta numero di ricorrenze – la programmazione report viene eseguita per il numero di volte specificato e viene quindi disattivata.
    -   Fine entro – la programmazione report termina alla data specificata.

9.  Fare clic su Salva nella barra degli strumenti. Nella finestra di dialogo Salva con nome specificare un nome univoco e una descrizione per la programmazione report.

Per copiare una programmazione report, è necessario disporre del ruolo di designer o amministratore. Anche se un amministratore modifica la programmazione report, il report mantiene le credenziali dell'utente che ha creato il report.
### <a name="copy-a-report-schedule"></a>Copiare una programmazione report

1.  In Progettazione report, fare clic su Programmazioni report nel pannello di navigazione e aprire una programmazione report da copiare.
2.  Nel menu File, fare clic su Salva con nome e immettere un nome e una descrizione nuovi per la programmazione nella finestra di dialogo Salva con nome. Fare clic su OK e la nuova programmazione apparirà nel pannello di navigazione.
3.  Nella nuova programmazione, modificare i campi e le informazioni in base alle necessità quindi fare clic su Salva sulla barra degli strumenti oppure fare clic su Salva nel menu File.

Per eliminare una programmazione report, è necessario essere il proprietario della programmazione report o disporre del ruolo di amministratore.
### <a name="delete-a-report-schedule"></a>Eliminare una programmazione report

1.  In Progettazione report, nel pannello di navigazione, fare clic su Programmazioni report.
2.  Selezionare la programmazione report da eliminare e fare clic su Elimina o premere il tasto Canc.
3.  Nella finestra di dialogo di verifica dell'eliminazione, fare clic su Sì per definitivamente eliminare la programmazione report. Se non si dispone delle autorizzazioni per eliminare la programmazione, verrà visualizzato un messaggio e il report non verrà eliminato.

### <a name="credentials-and-report-schedules"></a>Credenziali e programmazioni report

Se non si immettono le credenziali necessarie per tutte le società incluse nei report, si riceve un messaggio di questo tipo quando si salva la programmazione report: "È necessario immettere le credenziali per le società che sono contenute nella programmazione report. Selezionare il pulsante Autorizzazioni per immettere le credenziali".

Ad esempio, Phyllis accede alla Società A utilizzando il proprio nome di accesso e relativa password. Crea una programmazione per un report che utilizza una definizione di albero gerarchico per raccogliere i dati da più società. Quando la programmazione del report viene salvata, Phyllis riceve la richiesta di immettere le credenziali per le altre società specificate nella definizione di albero gerarchico. Quando le credenziali scadono, i report interessati nella programmazione report non vengono generati fino all'aggiornamento delle credenziali. Verrà visualizzato un messaggio nella coda di report per indicare che le autorizzazioni devono essere aggiornate. La programmazione report ha esito negativo se uno dei seguenti scenari si verifica (perché richiedono le credenziali):
-   Una società è stata aggiunta a un albero gerarchico per un singolo report.
-   Un report in un gruppo di report è stato modificato.
-   Un nuovo report per una società aggiuntiva è stato aggiunto a un gruppo di report.

Per continuare, fare clic sul pulsante Autorizzazioni nella finestra di dialogo Progammazione report, quindi immettere le credenziali appropriate.

## <a name="missing-account-analysis-feature"></a> Funzionalità di analisi dei conti mancanti
È possibile individuare i conti finanziari e le dimensioni che potrebbero mancare in tutte le definizioni di riga, definizioni di albero gerarchico e definizioni di report in un gruppo di blocchi predefiniti. Questa funzione è utile quando si creano o si aggiornano diversi conti o blocchi predefiniti in un breve periodo e si desidera verificare che tutte le nuove informazioni siano incluse nei report.

I conti mancanti vengono determinati utilizzando i valori minimo e massimo dalla definizione di riga o la definizione di albero gerarchico e quindi viene visualizzato un elenco dei conti che non sono nella definizione di riga o la definizione di albero gerarchico, ma sono nei dati finanziari. Se un conto mancante è maggiore o minore dei valori nella definizione di riga, il conto non è incluso nell'elenco dei conti mancanti.
| ![Suggerimento](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Suggerimento")**Suggerimento**                                             |
|----------------------------------------------------------------------------------------------------------------------------------|
| A fini di convalida, questo processo deve essere eseguito prima di generare i report mensili e quando si creano nuovi blocchi predefiniti. |

Report con intervalli di valori hanno minori probabilità di avere conti mancanti. Quando possibile, utilizzare gli intervalli nel blocco predefinito per includere i nuovi conti quando vengono creati. Se una definizione di report viene impostata su @ANY società, è possibile accedere a una società specifica ed eseguire un'analisi di conto mancante per la società.
| ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**                                                                                           |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se una nuova società è stata aggiunta, è necessario aggiungere la nuova società agli alberi gerarchici in tutti i report esistenti o la società non verrà inclusa nell'analisi dei conti mancanti. |

### <a name="run-missing-account-analysis"></a>Eseguire l'analisi dei conti mancanti

1.  In Progettazione report, fare clic su Strumenti, quindi fare clic su Analisi conti mancanti.
2.  Nel campo Filtro società, selezionare una società per la quale filtrare i risultati, o selezionare Tutto (senza filtro) per visualizzare i risultati di tutte le società disponibili.
3.  Nel campo Filtro dimensioni, selezionare una dimensione in base a cui filtrare i risultati o selezionare Tutto (senza filtro) per visualizzare tutte le informazioni sulle dimensioni per tutte le dimensioni disponibili.
4.  Nel campo Raggruppa per selezionare un'opzione per ordinare i risultati. È possibile ordinare i risultati in base al blocco predefinito interessato o è possibile ordinare i risultati per dimensione e set di valori.
5.  Esaminare i risultati visualizzati. Quando si seleziona un elemento nel riquadro superiore, nel riquadro inferiore vengono visualizzate informazioni aggiuntive sull'eccezione. Sono incluse le dimensioni correlate, i valori e i report.
6.  Per aprire l'elemento interessato, fare clic sull'icona associata visualizzata nel riquadro dell'elenco, o fare clic con il pulsante destro del mouse sull'elemento e selezionare Apri. Per selezionare più elementi, tenere premuto il tasto Ctrl mentre si selezionano gli elementi nel riquadro inferiore.
7.  Se vengono restituiti valori, blocchi predefiniti, o report che non devono essere inclusi nell'analisi, fare clic con il pulsante destro del mouse sull'elemento e selezionare Escludi o selezionare la casella di controllo Escludi accanto all'elemento per rimuoverlo dall'elenco. Gli elementi esclusi non vengono inclusi quando l'elenco viene aggiornato. Per selezionare più elementi, tenere premuto il tasto Ctrl mentre si selezionano gli elementi nel riquadro inferiore. Per visualizzare tutti gli elementi, inclusi tutti i risultati selezionati in precedenza per escluderli dall'analisi, selezionare la casella di controllo Mostra blocchi predefiniti e valori esclusi quindi fare clic su Aggiorna.
8.  Fare clic su Aggiorna per aggiornare le eccezioni gestite. Fare clic su Sì per eseguire un aggiornamento completo di tutti risultati, o fare clic su No per eseguire un aggiornamento parziale degli elementi gestiti.
    | ![Nota](https://i-technet.sec.s-msft.com/areas/global/content/clear.gif "Nota")**Nota**                    |
    |------------------------------------------------------------------------------------------------------------|
    | Il modulo viene automaticamente aggiornato quando si apre, a meno che sia stato aperto negli ultimi 15 minuti. |

9.  Quando i problemi sono risolti, fare clic su OK per chiudere la finestra di dialogo.

## <a name="keyboard-shortcuts-for-missing-account-analysis"></a>Tasti di scelta rapida per l'analisi dei conti mancanti
Quando si esegue un'analisi dei conti mancanti, sono disponibili i seguenti tasti di scelta rapida.

| Operazione da eseguire                           | Utilizzare questo tasto di scelta rapida |
|--------------------------------------|----------------------------|
| Filtrare per società                    | Alt+C                      |
| Filtrare per dimensione                  | Alt+D                      |
| Selezionare il campo Raggruppa per            | Alt+G                      |
| Mostrare i blocchi e i valori esclusi      | Alt+S                      |
| Aggiornare i risultati                      | Alt+R                      |
| Escludere il blocco predefinito selezionato  | Alt+X                      |
| Escludere la definizione di riga selezionata  | Ctrl+B                     |
| Escludere il valore di dimensione selezionato | Ctrl+D                     |
| Aprire la definizione di report selezionata  | Ctrl+R                     |
| Aprire la definizione di riga selezionata     | Ctrl+O                     |

 
<a name="see-also"></a>Vedere anche
--------

[Creazione di report finanziari](financial-reporting-intro.md)

[Interfaccia Progettazione report](report-designer-interface.md)



