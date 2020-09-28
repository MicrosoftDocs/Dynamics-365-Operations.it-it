---
title: Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate
description: Questo argomento spiega come migliorare le prestazioni delle soluzioni di creazione di report elettronici (ER) aggiungendo origini dati CAMPO CALCOLATO parametrizzato.
author: NickSelin
manager: AnnBe
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: a87098e82284a4951f3a4de050f6ba3f587fd20a
ms.sourcegitcommit: 5472005274f2f94fba82dda90de128f39d8b8390
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760084"
---
# <a name="improve-the-performance-of-er-solutions-by-adding-parameterized-calculated-field-data-sources"></a>Migliorare le prestazioni delle soluzioni ER aggiungendo origini dati CAMPO CALCOLATO parametrizzate

[!include [banner](../includes/banner.md)]

Questo argomento spiega come prendere le [tracce delle prestazioni](trace-execution-er-troubleshoot-perf.md) dei formati della [creazione di report elettronici (ER)](general-electronic-reporting.md) che vengono eseguiti e quindi utilizzare le informazioni di tali tracce per migliorare le prestazioni configurando un'origine dati **Campo calcolato**.

Nell'ambito del processo di pianificazione delle configurazioni ER per la generazione di documenti aziendali, si definisce il metodo utilizzato per recuperare i dati dall'applicazione e immetterli nell'output generato. Progettando un'origine dati ER parametrizzata di tipo **Campo calcolato** è possibile ridurre il numero di chiamate al database e ridurre notevolmente il tempo e il costo coinvolti nella raccolta dei dettagli dell'esecuzione del formato ER.

## <a name="prerequisites"></a>Prerequisiti

- Per completare gli esempi in questo argomento, è necessario disporre dell'accesso ai seguenti [ruoli](../sysadmin/tasks/assign-users-security-roles.md):

    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- La società deve essere impostata su **DEMF**.
- Seguire i passaggi nell'[Appendice 1](#appendix1) di questo argomento per scaricare i componenti della soluzione Microsoft ER di esempio richiesti per completare gli esempi in questo argomento.
- Seguire i passaggi nell'[Appendice 2](#appendix2) di questo argomento per configurare il set minimo di parametri ER necessario per utilizzare il framework ER per migliorare le prestazioni della soluzione Microsoft ER di esempio.

## <a name="import-the-sample-er-solution"></a>Importare le soluzione ER di esempio

Si supponga di dover progettare una soluzione ER per generare un nuovo report che mostra le transazioni fornitore. Attualmente, è possibile trovare le transazioni di un fornitore selezionato nella pagina **Transazioni fornitore** (accedere a **Contabilità fornitori** \> **Fornitori** \> **Tutti i fornitori**, selezionare un fornitore e quindi, nel riquadro Azioni, nella scheda **Fornitore** nel gruppo **Transazioni** selezionare **Transazioni**). Tuttavia, si desidera avere tutte le transazioni fornitore insieme in un documento elettronico in formato XML. Questa soluzione comporterà diverse configurazioni ER contenenti il modello dati, il mapping di modello e i componenti formato necessari.

Il primo passaggio consiste nell'importare la soluzione ER di esempio per generare un report delle transazioni del fornitore.

1. Accedere all'istanza di Microsoft Dynamics 365 Finance di cui è stato eseguito il provisioning per la società.
2. In questo argomento si creeranno e modificheranno configurazioni per la società di esempio **Litware, Inc**. Verificare che questo provider di configurazioni sia stato aggiunto all'istanza di Finance e sia selezionato come attivo. Per ulteriori informazioni, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).
3. Nell'area di lavoro **Creazione di report elettronici**, selezionare il riquadro **Configurazioni report**.
4. Nella pagina **Configurazioni**, importare le configurazioni ER scaricate come prerequisito in Finance, nel seguente ordine: modello dati, mapping di modello, formato. Per ogni configurazione, procedere come segue:

    1. Nella riquadro Azioni, selezionare **Scambia** \> **Carica da file XML**.
    2. Selezionare **Sfoglia** e selezionare il file appropriato per la configurazione ER in formato XML.
    3. Selezionare **OK**.

![Configurazioni importate nella pagina Configurazioni](./media/er-calculated-field-ds-performance-imported-configurations.png)

## <a name="review-the-sample-er-solution"></a>Esaminare le soluzione ER di esempio

### <a name="review-the-model-mapping"></a>Esaminare il mapping di modello

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di miglioramento delle prestazioni**, quindi selezionare **Mapping miglioramento delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Selezionare **Progettazione** nel riquadro azioni della pagina **Modello per mapping origine dati**.

    Questo mapping di modello ER esegue le azioni seguenti:

    - Recupera l'elenco delle transazioni del fornitore archiviate nella tabella VendTrans (origine dati **Transazioni**).
    - Per ogni transazione, recuperare, dalla tabella VendTable, il record di un fornitore per il quale è stata registrata la transazione (origine dati **\#Vend**).

    > [!NOTE]
    > L'origine dati **\#Vend** è configurata per recuperare il record del fornitore corrispondente utilizzando la relazione molti-a-uno esistente **\@.'\>Relations'.VendTable\_AccountNum**.

    Il mapping di modello in questa configurazione implementa il modello di dati di base per qualsiasi formato ER creato per questo modello ed eseguito in Finance. Di conseguenza, il contenuto dell'origine dati **Transazioni** viene esposto per i formati ER, ad esempio origini dati **modello**.

    ![Origine dati transazioni nella pagina di progettazione del mapping del modello](media/er-calculated-field-ds-performance-mapping-1.png)

4. Chiudere la pagina **Progettazione mapping modello**.
5. Chiudere la pagina **Modello per mapping origine dati**.

### <a name="review-format"></a>Esaminare il formato

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni, espandere **Modello di miglioramento delle prestazioni**, quindi selezionare **Formato miglioramento delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Nella pagina **Progettazione formati** nella scheda **Mapping** selezionare **Espandi/Comprimi**.
4. Espandere gli elementi **Modello**, **Dati** e **Transazione**.

    Questo formato ER è progettato per generare un report sulle transazioni del fornitore in formato XML.

    ![Formattare le origini dati e le associazioni configurate degli elementi di formato nella pagina Progettazione formati](media/er-calculated-field-ds-performance-format.png)

5. Chiudere la pagina **Progettazione formati**.

## <a name="run-the-sample-er-solution-to-trace-execution"></a>Eseguire la soluzione ER di esempio per generare la traccia dell'esecuzione

Immaginiamo di aver completato la progettazione della prima versione della soluzione ER. Ora si desidera testare la soluzione nell'istanza di Finance e analizzare le prestazioni di esecuzione.

### <a name="turn-on-the-er-performance-trace"></a>Attivare la traccia delle prestazioni ER

1. Selezionare la società **DEMF**.
2. Seguire i passaggi in [Attivare la traccia delle prestazioni ER](trace-execution-er-troubleshoot-perf.md#turn-on-the-er-performance-trace) per generare una traccia delle prestazioni durante l'esecuzione di un formato ER.

    ![Finestra di dialogo Parametri dell'utente](media/er-calculated-field-ds-performance-format-user-parameters.png)

### <a name="run-the-er-format"></a><a id="run-format"></a>Eseguire il formato ER

1. Andare a **Amministrazione organizzazione** \> **Creazione di report elettronici** \> **Configurazioni**.
2. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato miglioramento delle prestazioni**.
3. Nel Riquadro azioni selezionare **Esegui**.

## <a name="use-the-performance-trace-to-analyze-model-mapping-performance"></a>Utilizzare la traccia delle prestazioni per analizzare le prestazioni del mapping di modello

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.
4. Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
5. Selezionare la traccia più recente generata, quindi selezionare **OK**.

Le nuove informazioni sono ora disponibili per alcuni elementi dell'origine dati del mapping di modello corrente:

- Il tempo effettivo impiegato per acquisire dati utilizzando l'origine dati
- Lo stesso tempo espresso come percentuale del tempo totale impiegato per l'esecuzione dell'intero mapping di modello

![Dettagli sul tempo di esecuzione nella pagina Progettazione mapping di modello](./media/er-calculated-field-ds-performance-mapping-2.png)

La griglia **Statistiche delle prestazioni** mostra che l'origine dati **Transazioni** chiama la tabella VendTrans una volta. Il valore **\[265\]\[Q:265\]** dell'origine dati **Transazioni** indica che 265 transazioni del fornitore sono state recuperate dalla tabella dell'applicazione e restituite al modello di dati.

La griglia **Statistiche delle prestazioni** mostra anche che il mapping di modello corrente duplica le richieste del database mentre l'origine dati **\#Vend** viene eseguita. Questa duplicazione di verifica per i seguenti motivi:

- La tabella del fornitore viene richiamata due volte per ciascuna delle 265 transazioni fornitore iterate, per un totale di 530 chiamate:

    - Viene effettuata una chiamata per inserire il numero di conto del fornitore.
    - Viene effettuata una chiamata per inserire il nome del fornitore.

- La tabella del fornitore viene richiamata per ciascuna transazione fornitore iterata, anche se le transazioni recuperate sono state registrate solo per cinque fornitori. Delle 530 chiamate, 525 sono duplicate. La figura seguente mostra il messaggio ricevuto sulle chiamate duplicate (richieste di database).

![Messaggio sulle richieste di database duplicate nella pagina Progettazione mapping modello](./media/er-calculated-field-ds-performance-mapping-2a.png)

Del tempo totale di esecuzione del mapping di modello (circa otto secondi), notare che più dell'80 percento (circa sei secondi) è stato impiegato per recuperare i valori dalla tabella dell'applicazione VendTable. Questa percentuale è troppo grande per due attributi di cinque fornitori, rispetto al volume di informazioni dalla tabella dell'applicazione VendTrans.

Per ridurre il numero di chiamate effettuate per ottenere i dettagli del fornitore per ogni transazione e migliorare le prestazioni del mapping di modello, è possibile utilizzare la memorizzazione nella cache per l'origine dati **\#Vend**.

> [!NOTE]
> L'origine dati **Transazioni\\\#Vend** verrà memorizzata nella cache nell'ambito della transazione corrente dell'origine dati **Transazioni** in fase di esecuzione.

Memorizzando nella cache l'origine dati **\#Vend** si riduce il numero di chiamate duplicate da 525 a 260, ma non si elimina completamente la duplicazione. Per eliminare completamente la duplicazione, è possibile configurare una nuova origine dati parametrizzata di tipo **Campo calcolato**.

## <a name="improve-the-model-mapping-based-on-information-from-the-execution-trace"></a>Migliorare il mapping di modello basato sulle informazioni della traccia dell'esecuzione

### <a name="change-the-logic-of-the-model-mapping"></a>Modificare la logica del mapping di modello

Attenersi alla seguente procedura per utilizzare la memorizzazione nella cache e un'origine dati di tipo **Campo calcolato** per evitare chiamate duplicate al database.

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.
4. Nella pagina **Progettazione mapping di modello**, seguire questi passaggi per aggiungere un'origine dati di tipo **Record di tabella** per accedere ai record nella tabella dell'applicazione VendTable:

    1. Nel riquadro **Tipi di origine dati**, espandere **Dynamics 365 for Operations** e selezionare **Record di tabella**.
    2. Selezionare **Aggiungi radice**.
    3. Nella finestra di dialogo, nel campo **Nome**, immettere **Vend**.
    4. Nel campo **Tabella**, immettere **VendTable**.
    5. Selezionare **OK**.

5. È possibile parametrizzare le chiamate alle origini dati di tipo **Campo calcolato** solo se tali origini dati risiedono in un contenitore. Pertanto, attenersi alla seguente procedura per aggiungere un'origine dati di tipo **Contenitore vuoto** per contenere una nuova origine dati parametrizzata di tipo **Campo calcolato**:

    1. Nel riquadro **Tipi di origine dati**, espandere **Generale** e selezionare **Contenitore vuoto**.
    2. Selezionare **Aggiungi radice**.
    3. Nella finestra di dialogo, nel campo **Nome**, immettere **Casella**.
    3. Selezionare **OK**.

    ![Origine dati casella nella pagina di progettazione del mapping del modello](./media/er-calculated-field-ds-performance-mapping-3.png)

6. Attenersi alla seguente procedura per aggiungere un'origine dati parametrizzata di tipo **Campo calcolato**:

    1. Selezionare **Casella** nel riquadro **Origini dati**.
    2. Nel riquadro **Tipi di origine dati**, espandere **Funzioni** e selezionare **Campo calcolato**.
    3. Selezionare **Aggiungi**.
    4. Nella finestra di dialogo, nel campo **Nome**, immettere **Vend**.
    5. Selezionare **Modifica formula**.
    6. Nella pagina **Designer formula** selezionare **Parametri** per specificare i parametri che devono essere forniti quando viene chiamata questa origine dati.
    7. Nella finestra di dialogo **Parametri** selezionare **Nuovo**.
    8. Nel campo **Nome**, immettere **parmVendAccNumber**.
    9. Nel campo **Tipo** selezionare **Stringa**.
    10. Selezionare **OK**.
    11. Nel campo **Formula** immettere **FIRSTORNULL(FILTER(Vend, Vend.AccountNum=parmVendAccNumber))**.
    12. Selezionare **Salva** e chiudere la pagina **Designer formula**.
    13. Selezionare **OK** per aggiungere la nuova origine dati.

7. Seguire questi passaggi per contrassegnare l'origine dati aggiunta come memorizzata nella cache durante l'esecuzione:

    1. Nel riquadro **Origini dati** selezionare **Casella\\Vend**.
    2. Selezionare **Cache**.

    > [!NOTE]
    > L'origine dati **Casella\\Vend** verrà memorizzata nella cache nell'ambito di tutte le transazioni fornitore dell'origine dati **Transazioni** in fase di esecuzione.

8. Seguire questi passaggi per aggiornare l'origine dati **Transazioni\\\#Vend** nidificata in modo che utilizzi l'origine dati **Casella\\Vend**:

    1. Nel riquadro **Origini dati**, espandere **Transazioni**.
    2. Selezionare l'origine dati **Trans\\\#Vend** e selezionare **Modifica** \> **Modifica formula**.
    3. Nella pagina **Designer formula** nel campo **Formula** inserire **Box.Vend(\@.AccountNum)**.
    4. Selezionare **Salva** quindi chiudere la pagina **Designer formula**.
    5. Selezionare **OK** per completare le modifiche all'origine dati selezionata.

9. Selezionare **Salva**.

    ![Origine dati Vend nella pagina di progettazione del mapping del modello](./media/er-calculated-field-ds-performance-mapping-4.png)

10. Chiudere la pagina **Progettazione mapping modello**.
11. Chiudere la pagina **Mapping modello**.

### <a name="complete-the-modified-version-of-the-er-model-mapping"></a>Completare la versione modificata del mapping di modello ER

1. Nella pagina **Configurazioni**, nella Scheda dettaglio **Versioni**, selezionare la versione **1.2** della configurazione **Mapping miglioramento delle prestazioni**.
2. Selezionare **Cambia stato** \> **Completa** e selezionare **OK**.

## <a name="run-the-modified-er-solution-to-trace-execution"></a>Eseguire la soluzione ER modificata per generare la traccia dell'esecuzione

Ripetere i passaggi nella sezione [Eseguire il formato ER](#run-format) vista in precedenza in questo argomento per generare una nuova traccia delle prestazioni.

## <a name="use-the-performance-trace-to-analyze-adjustments-to-the-model-mapping"></a>Utilizzare la traccia delle prestazioni per analizzare le modifiche al mapping di modello 

1. Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping miglioramento delle prestazioni**.
2. Nel riquadro azioni selezionare **Progettazione**.
3. Selezionare **Progettazione** nel riquadro azioni della pagina **Mapping di modello**.
4. Nella pagina **Progettazione mapping modello**, nel riquadro azioni, selezionare **Traccia delle prestazioni**.
5. Selezionare la traccia più recente generata, quindi selezionare **OK**.

Si noti che le rettifiche apportate al mapping di modello hanno eliminato le query duplicate al database. Anche il numero di chiamate alle tabelle di database e alle origini dati per questo mapping di modello sono state ridotti.

![Informazioni di traccia nella pagina di progettazione del mapping del modello 1](./media/er-calculated-field-ds-performance-mapping-5.png)

Il tempo di esecuzione totale è stato ridotto di circa 20 volte (da circa 8 secondi a circa 400 millisecondi). Di conseguenza, le prestazioni dell'intera soluzione ER sono state migliorate.

![Informazioni di traccia nella pagina di progettazione del mapping del modello 2](./media/er-calculated-field-ds-performance-mapping-5a.png)

## <a name="appendix-1-download-the-components-of-the-sample-microsoft-er-solution"></a><a name="appendix1"></a>Appendice 1: scaricare i componenti della soluzione Microsoft ER di esempio

È necessario scaricare e archiviare localmente i file seguenti.

| File                                        | Contenuto |
|---------------------------------------------|---------|
| Performance improvement model.version.1     | [Configurazione del modello di dati ER di esempio](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Performance improvement mapping.version.1.1 | [Configurazione del mapping di modello ER di esempio](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |
| Performance improvement format.version.1.1  | [Configurazione di formato ER di esempio](https://mbs.microsoft.com/customersource/Global/AX/downloads/hot-fixes/365optelecrepeg) |

## <a name="appendix-2-configure-the-er-framework"></a><a name="appendix2"></a>Appendice 2: configurare il framework ER

Prima di poter iniziare a utilizzare il framework ER per migliorare le prestazioni della soluzione Microsoft ER di esempio, è necessario configurare il set minimo di parametri ER.

### <a name="configure-er-parameters"></a><a id="ConfigureParameters"></a>Configurare i parametri ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Parametri per la creazione di report elettronici**.
3. Nella pagina **Parametri per la creazione di report elettronici**, nella scheda **Generale**, imposta l'opzione **Abilita integrazione fiscale** su **Sì**.
4. Nella scheda **Allegati**, imposta i seguenti parametri:

    - Nel campo **Configurazioni**, seleziona il tipo **File** per l'azienda **DEMF**.
    - Nei campi **Archivio processi**, **Temporaneo**, **Base** e **Altri**, seleziona il tipo **File**.

Per ulteriori informazioni sui parametri ER, vedi [Configurare il framework ER](electronic-reporting-er-configure-parameters.md).

### <a name="activate-an-er-configuration-provider"></a><a id="ActivateProvider"></a>Attivare un provider di configurazioni ER

Ogni configurazione ER aggiunta viene contrassegnata come di proprietà di un provider di configurazione ER. Il provider di configurazione ER che è attivato nell'area di lavoro **Creazione di report elettronici** viene utilizzato per questo scopo. Pertanto, è necessario attivare un provider di configurazione ER nell'area di lavoro **Creazione di report elettronici** prima di iniziare ad aggiungere o modificare le configurazioni ER.

> [!NOTE]
> Solo il proprietario di una configurazione ER può modificare la configurazione. Pertanto, prima di poter modificare una configurazione ER, è necessario attivare il provider di configurazione ER appropriato nell'area di lavoro **Creazione di report elettronici**.

#### <a name="review-the-list-of-er-configuration-providers"></a><a id="ReviewProvidersList"></a>Rivedere l'elenco dei provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Tabella del provider di configurazione**, ogni record del provider ha un nome e un URL univoci. Rivedi il contenuto della pagina. Se un record per **Litware, Inc.** esiste già, andare alla procedura successiva, [Aggiungere un nuovo provider di configurazione ER](#ActivateProvider).

#### <a name="add-a-new-er-configuration-provider"></a><a id="ActivateProvider"></a>Aggiungere un nuovo provider di configurazione ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Collegamenti correlati**, seleziona **Provider di configurazione**.
3. Nella pagina **Provider di configurazione**, seleziona **Nuovo**.
4. Nel campo **Nome**, immetti **Litware, Inc.**
5. Nel campo **Indirizzo Internet** immetti `https://www.litware.com`.
6. Selezionare **Salva**.

#### <a name="activate-an-er-configuration-provider"></a><a id="ActivateAddedProvider"></a>Attivare un provider di configurazioni ER

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Provider di configurazione**, seleziona il riquadro **Litware, Inc.**, quindi seleziona **Imposta attivo**.

Per ulteriori informazioni sui provider di configurazione ER, vedi [Creare provider di configurazioni e contrassegnarli come attivi](tasks/er-configuration-provider-mark-it-active-2016-11.md).

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Tenere traccia dell'esecuzione dei formati di creazione di report elettronici per risolvere i problemi di prestazioni](trace-execution-er-troubleshoot-perf.md)
- [Supporto per le chiamate parametrizzate delle origini dati ER di tipo Campo calcolato](er-calculated-field-type.md)
