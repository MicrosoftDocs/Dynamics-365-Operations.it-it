---
title: Migliorare le prestazioni delle soluzioni ER riducendo il numero di campi della tabella recuperati in fase di esecuzione
description: Questo argomento spiega come migliorare le prestazioni delle soluzioni ER riducendo il numero di campi della tabella recuperati in fase di esecuzione.
author: NickSelin
ms.date: 05/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: dd192a7718ac4fd8bcb636ede6c005ca29ee5f08
ms.sourcegitcommit: 336a0ad772fb55d52b4dcf2fafaa853632373820
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/28/2022
ms.locfileid: "8811957"
---
# <a name="improve-performance-of-er-solutions-by-reducing-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Migliorare le prestazioni delle soluzioni ER riducendo il numero di campi della tabella recuperati in fase di esecuzione

[!include[banner](../includes/banner.md)]

È possibile progettare [formati](er-overview-components.md#format-components-for-outgoing-electronic-documents) di [report elettronici](general-electronic-reporting.md) (ER) per generare documenti in uscita in vari formati. Quando viene generato un documento, un formato di ER chiama le origini dati che sono state configurate in un [mapping di modelli](er-overview-components.md#model-mapping-component) di ER corrispondente. Per configurare l'accesso alle tabelle, alle query o alle entità dell'applicazione per il recupero di record, è possibile utilizzare le origini dati di ER di tipo *Record di tabella*. Per impostazione predefinita, un'origine dati di tipo *Record di tabella* recupera i valori di tutti i campi nei record richiesti. Tuttavia, puoi configurare questo tipo di origine dati in modo che recuperi solo i valori di campo richiesti per il formato ER in esecuzione. Questa configurazione consente di ridurre il consumo di memoria del server delle applicazioni che esegue il recupero dei dati e l'ulteriore memorizzazione nella cache dei record.

Per ulteriori informazioni su come limitare l'elenco dei campi recuperati delle origini dati di tipo *Record di tabella* completa l'esempio in questo argomento.

## <a name="example-reduce-the-number-of-table-fields-that-are-fetched-at-runtime"></a>Esempio: ridurre il numero di campi della tabella che vengono recuperati in fase di esecuzione

Le procedure seguenti mostrano come un utente con ruolo di amministratore di sistema o sviluppatore di report elettronici può configurare un mapping del modello ER in modo che recuperi solo i campi necessari per eseguire il formato ER, per ridurre il consumo di memoria del server delle applicazioni.

Queste procedure possono essere completate nella società **USMF** in Microsoft Dynamics 365 Finance. Non è richiesta alcuna codifica.

Per completare l'esempio in questo argomento, è necessario avere accesso alla società **USMF** per uno dei seguenti ruoli:

- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

In questo esempio verranno usate le [configurazioni](general-electronic-reporting.md#Configuration) ER fornite per la società di esempio **Litware, Inc**. Verifica che il provider di configurazione per la società di esempio **Litware, Inc.** (`http://www.litware.com`) sia elencato per il framework ER e sia contrassegnato come **Attivo**. Se questo provider di configurazione non è elencato o non è contrassegnato come **Attivo**, completare i passaggi in [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

### <a name="configure-the-er-framework"></a>Configurare il framework ER

Segui i passaggi in [Configurare il framework ER](er-quick-start2-customize-report.md#ConfigureFramework) per impostare il set minimo di parametri ER. È necessario completare questa configurazione prima di iniziare a utilizzare il framework ER per modificare le origini dati della soluzione ER fornita.

### <a name="import-the-sample-er-configurations"></a>Importare le configurazioni ER di esempio

Se non hai ancora completato l'esempio nell'argomento [Progettare una nuova soluzione ER per stampare un report personalizzato](er-quick-start1-new-solution.md), scarica e archivia localmente i file XML per le seguenti configurazioni della soluzione ER fornita.

| Descrizione contenuto            | Nome file |
|--------------------------------|-----------|
| Configurazione del modello di dati ER    | [Questionnaires model.version.1.xml](https://download.microsoft.com/download/b/6/3/b633bd34-d200-4422-96d9-8f62eb5218f8/Questionnaires_model.version.1.xml) |
| Configurazione del mapping di modello ER | [Questionnaires mapping.version.1.1.xml](https://download.microsoft.com/download/7/b/2/7b258e4e-4bd5-46a4-8114-27419ae4acd8/Questionnaires_mapping.version.1.1.xml) |
| Configurazione di formato ER        | [Questionnaires format.version.1.1.xml](https://download.microsoft.com/download/1/b/a/1ba39ec2-257a-44d8-972f-25bf7d18fb41/Questionnaires_format.version.1.1.xml) |

Quindi segui questi passaggi per caricare le configurazioni della soluzione ER fornita nella tua istanza di Finance.

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Selezionare **Configurazioni report**.
3. Nella pagina **Configurazioni** importa la configurazione del modello dati ER.

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Seleziona **Sfoglia**, trova e seleziona il file **Questionnaires model.version.1.xml** quindi seleziona **OK**.

4. Importa la configurazione del mapping del modello ER.

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Seleziona **Sfoglia**, quindi trova e seleziona il file **Questionnaires mapping.1.1.xml** e seleziona **OK**.

5. Importa la configurazione del formato ER.

    1. Selezionare **Scambia**, quindi selezionare **Carica da file XML**.
    2. Seleziona **Sfoglia**, quindi trova e seleziona il file **Questionnaires format.1.1.xml** e seleziona **OK**.

6. Nell'albero di configurazione, espandi **Modello per questionari**.
7. Esaminare l'elenco delle configurazioni ER importate nella struttura delle configurazioni.

    ![Esame dell'elenco delle configurazioni ER importate nella pagina Configurazioni.](./media/er-reduce-fetched-fields-number-configurations.png)

### <a name="review-the-provided-er-model-mapping"></a>Esaminare il mapping di modello ER fornito

1. Nella pagina **Configurazioni**, seleziona **Mapping dei questionari**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Seleziona **Progettazione** nella pagina **Modello per mapping origine dati**.
4. Sulla pagina **Progettazione mapping modello**, nel riquadro azioni, seleziona **Visualizzazione gruppo** per attivare la visualizzazione **Gruppo**.
5. Espandi **Gestione questionari** nel riquadro **Modello di dati**.

    Nota che l'origine dati **Questionario** è stata configurata per accedere alla tabella dell'applicazione `KMCollection`.

6. Nel riquadro **origini dati** espandi **Record di tabella** \> **Questionario** \> **Campi**.

    Nota quanti campi della tabella dell'applicazione `KMCollection` sono esposti dall'origine dati **Questionario** di tipo *Record di tabella*.

    ![Revisione del mapping del modello fornito nella pagina Progettazione mapping modello quando la visualizzazione gruppo è attivata.](./media/er-reduce-fetched-fields-number-mapping1.png)

7. Nel riquadro azioni seleziona **Visualizzazione gruppo** di nuovo per disattivare la visualizzazione **Gruppo** e quindi seleziona **Mostra tutto** \> **Mostra solo mappati**.

    Nota che alcuni campi della tabella dell'applicazione `KMCollection` vengono utilizzati per compilare l'elenco di record **Questionario** nel modello di dati ER:

    - `Active`
    - `Description`
    - `questionMode`
    - `kmCollectionId`

    ![Revisione del mapping del modello fornito nella pagina Progettazione mapping modello quando la visualizzazione gruppo è disattivata.](./media/er-reduce-fetched-fields-number-mapping2.png)

### <a name="turn-on-the-er-performance-trace"></a>Attivare la traccia delle prestazioni ER

Segui i passaggi in [Attivare la traccia delle prestazioni ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) per impostare i parametri utente ER che consentono di tracciare l'esecuzione dei componenti ER.

### <a name="run-the-provided-er-format-by-using-the-provided-model-mapping"></a>Eseguire il formato ER fornito utilizzando il mapping di modello fornito

Segui i passaggi in [Eseguire un formato progettato da ER](er-quick-start1-new-solution.md#RunFormatFromER) per eseguire il formato ER fornito per un singolo questionario dalla pagina **Configurazioni**.

### <a name="review-the-execution-trace-of-the-first-run"></a>Verificare la traccia di esecuzione della prima esecuzione

1. Vai in **Amministrazione organizzazione** \> **Creazione di report elettronici \> Configurazioni**.
2. Sulla pagina **Configurazioni** espandi **Modello di questionario** e seleziona **Mapping di questionario**.

    > [!NOTE]
    > I dettagli sulla Scheda dettaglio **Versioni** indicano che hai selezionato la versione bozza della configurazione **Mapping dei questionari**. Pertanto, è possibile modificare il contenuto di questo mapping di modello.

3. Nel riquadro azioni selezionare **Progettazione**.
4. Seleziona **Progettazione** nella pagina **Modello per mapping origine dati**.
5. Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
6. Nella finestra di dialogo **Impostazioni dei risultati della traccia delle prestazioni** seleziona la traccia che è stata generata durante l'ultima esecuzione della formattazione.

    ![Selezione della traccia nella finestra di dialogo Impostazioni risultati traccia delle prestazioni.](./media/er-reduce-fetched-fields-number-select-trace-1.png)

7. Seleziona **OK**. 
8. Sulla Scheda dettaglio **Dettagli**, filtra il percorso **Questionario** che punta all'origine dati **Questionario**.
9. Esamina i dettagli della query del database che è stata generata quando è stata chiamata l'origine dati **Questionario**.

    Nota che tutti i campi della tabella dell'applicazione `KMCollection` sono stati recuperati in fase di esecuzione quando l'origine dati **Questionario** è stata chiamata.

    ![Revisione dei dettagli della query del database nella pagina Progettazione mapping di modello.](./media/er-reduce-fetched-fields-number-query1.png)

### <a name="modify-the-provided-er-model-mapping"></a>Modificare il mapping di modello ER fornito

1. Nella pagina **Progettazione mapping modello**, nel riquadro **Origini dati**, seleziona l'origine dati **Questionario**.
2. Seleziona **Modifica** nel riquadro **Origini dati**.
3. Nella finestra di dialogo **Proprietà dell'origine dati**, seleziona **Seleziona campi** per specificare l'elenco dei campi della tabella dell'applicazione `KMCollection` di riferimento che verrà recuperata in fase di esecuzione quando viene chiamata l'origine dati modificabile **Questionario**.

    ![Seleziona Seleziona campi nella finestra di dialogo Proprietà origine dati per iniziare a configurare l'elenco dei campi che verranno recuperati dalla tabella dell'applicazione utilizzando l'origine dati modificabile.](./media/er-reduce-fetched-fields-number-select-fields1.png)

4. Sulla pagina **Seleziona campi** seleziona **Riempimento automatico**.

    L'elenco **Campi selezionati** viene compilato automaticamente, in base agli artefatti preconfigurati del mapping di modello. Tutti i campi e le relazioni della tabella di riferimento citati in qualsiasi associazione, formula o origine dati del mapping di modello vengono aggiunti all'elenco.

    ![Configurazione dell'elenco dei campi che verranno recuperati dalla tabella dell'applicazione nella pagina Seleziona campi.](./media/er-reduce-fetched-fields-number-select-fields2.png)

5. Seleziona **Salva** e chiudi la pagina **Seleziona campi**.
6. Seleziona **OK** per memorizzare le modifiche apportate alle impostazioni dell'origine dati.
7. Nel riquadro azioni seleziona **Mostra tutto**.

    Nota che l'origine dati **Questionario** ora mostra il testo **\<Fields are filtered\>**. Questo testo indica che l'origine dati è stata configurata per recuperare un numero limitato di campi dalla tabella dell'applicazione di riferimento.

    ![Revisione del mapping di modello aggiornato nella pagina Progettazione mapping di modello.](./media/er-reduce-fetched-fields-number-mapping3.png)

8. Seleziona **Salva** per memorizzare le modifiche apportate al mapping di modello modificabile.

    > [!NOTE]
    > In fase di esecuzione, ER analizza le relazioni aggiunte e aggiunge tutti i campi utilizzati alla query del database, anche se tali campi non sono stati aggiunti in modo esplicito all'elenco dei campi recuperati in fase di progettazione.

### <a name="run-the-provided-er-format-by-using-the-updated-model-mapping"></a>Eseguire il formato ER fornito utilizzando il mapping di modello aggiornato

Segui i passaggi in [Eseguire un formato progettato da ER](er-quick-start1-new-solution.md#RunFormatFromER) per eseguire il formato ER fornito per un singolo questionario dalla pagina **Configurazioni**.

### <a name="review-the-execution-trace-of-the-second-run"></a>Verificare la traccia di esecuzione della seconda esecuzione

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Sulla pagina **Configurazioni** espandi **Modello di questionario** e seleziona **Mapping di questionario**.
3. Nel riquadro azioni selezionare **Progettazione**.
4. Seleziona **Progettazione** nella pagina **Modello per mapping origine dati**.
5. Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
6. Nella finestra di dialogo **Impostazioni dei risultati della traccia delle prestazioni** seleziona la traccia che è stata generata durante l'ultima esecuzione della formattazione.
7. Seleziona **OK**.
8. Sulla Scheda dettaglio **Dettagli**, filtra il percorso **Questionario** che punta all'origine dati **Questionario**.
9. Esamina i dettagli della query del database che è stata generata quando è stata chiamata l'origine dati **Questionario**.

    Nota che solo i campi necessari per compilare l'origine dati sono stati recuperati in fase di esecuzione dalla tabella dell'applicazione `KMCollection` quando è stata chiamata l'origine dati **Questionario**.

    > [!NOTE]
    > Alcuni campi, come i campi per l'ID partizione, l'ID area dati e l'ID record, vengono aggiunti automaticamente dal framework di gestione dei dati dell'app Finance.

    ![Revisione dei dettagli della query del database per il mapping di modello aggiornato nella pagina Progettazione mapping di modello.](./media/er-reduce-fetched-fields-number-query2.png)

È possibile utilizzare questa tecnica per ridurre il numero di record recuperati quando è necessario ridurre il consumo di memoria mediante l'esecuzione del mapping di modello ER e del formato ER.

## <a name="limitations"></a>Limiti

Quando si limita il numero di campi recuperati per un'origine dati di tipo *Record di tabella* non è possibile utilizzare i metodi di una tabella dell'applicazione a cui fa riferimento l'origine dati, poiché i metadati dell'applicazione non forniscono informazioni sui campi di tabella necessari per chiamare tali metodi.

## <a name="usage-notes"></a>Note sull'utilizzo

Sebbene il comando **Riempimento automatico** aggiunga automaticamente i campi, non elimina automaticamente i campi aggiunti in precedenza, anche se non sono più utilizzati nelle associazioni, nelle formule e nelle origini dati del mapping di modello modificabile.

Quando selezioni **Riempimento automatico**, ER analizza le associazioni, le formule e le origini dati che aveva il mapping di modello modificabile quando l'hai aperto per la modifica. Se modifichi associazioni, formule e origini dati del mapping di modello modificabile e desideri utilizzare il comando **Riempimento automatico**, chiudi la finestra di progettazione del mapping di modello, quindi riaprila per modificare il mapping di modello. 

## <a name="additional-resources"></a>Risorse aggiuntive

- [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md)
- [Risoluzione dei problemi di prestazioni nelle configurazioni di ER](er-troubleshoot-perf-issues-in-configurations.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
