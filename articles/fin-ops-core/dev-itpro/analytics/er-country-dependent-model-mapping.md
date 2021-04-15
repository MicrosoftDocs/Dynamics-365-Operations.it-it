---
title: Configurare i mapping dei modelli ER dipendenti dal contesto del paese
description: In questo argomento viene descritto come impostare i mapping di modelli ER in modo che dipendano dalle contesto del paese della persona giuridica che ne controlla l'utilizzo.
author: NickSelin
ms.date: 11/11/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.2
ms.openlocfilehash: 83cd99350f58a56d121d694393edc4eb98af728a
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753770"
---
# <a name="configure-country-context-dependent-er-model-mappings"></a>Configurare i mapping dei modelli ER dipendenti dal contesto del paese

[!include[banner](../includes/banner.md)]

È possibile configurare i mapping dei modelli per la creazione di report elettronici in modo che implementino un modello di dati ER generico ma sia specifico per Dynamics 365 Finance. In questo argomento viene descritto come pianificare più mapping del modello ER affinché un modello di dati ER verifichi come vengono utilizzati i formati ER corrispondenti che vengono eseguiti dalle società che hanno diversi contesti di paese.

## <a name="prerequisites"></a>Prerequisiti

Per completare gli esempi in questo argomento, è necessario disporre del seguente accesso:

- Accesso a Finance per uno dei seguenti ruoli:
    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

- Accesso all'istanza di Regulatory Configuration Service (RCS) di cui è stato eseguito il provisioning per lo stesso tenant di Finance per uno dei seguenti ruoli:
    - Sviluppatore per la creazione di report elettronici
    - Consulente funzionale per la creazione di report elettronici
    - Amministratore di sistema

Alcuni passaggi in questo argomento richiedono l'esecuzione di un formato ER. In alcuni casi, l'esecuzione di un formato ER è interessata dalle contesto del paese della società a cui si è attualmente collegati. È possibile eseguire un formato ER nell'istanza RCS corrente se la società con il contesto di paese richiesto è disponibile nel RCS. In caso contrario, è necessario caricare una versione completa del mapping del modello ER e delle configurazioni del formato ER che utilizzano il modello di dati ER nell'istanza di Finance, quindi eseguire il formato ER nell'istanza di Finance. Per informazioni sull'importazione delle configurazioni che risiedono nel RCS in un'istanza di Finance, vedere [Importare configurazioni da RCS](rcs-download-configurations.md).

## <a name="single-model-mapping-case"></a>Caso di mapping di modello singolo

Seguire i passaggi descritti nell'[Appendice 1](#appendix1) in questo argomento per pianificare i componenti ER necessari. È stata creata la configurazione del mapping di modello **Mapping (generale)** contenente il mapping di modello per la definizione **Punto di ingresso 1**.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-Tree.PNG)

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Esegui**.
2.  Selezionare **OK**.

Si noti che il Web browser offre il download del file di testo generato dal formato ER eseguito. Poiché questo formato è stato configurato per utilizzare la definizione **Punto di ingresso 1** e al momento è disponibile solo un mapping di modello singolo per il modello base che contiene un mapping per questa definizione, il formato ER eseguito utilizza il mapping di modello **Mapping (generale)** della configurazione **Mapping (generale)** come origine dati. Di conseguenza, il file scaricato contiene il testo **Funzionalità generica 1**.

## <a name="multiple-shared-model-mappings-case"></a>Caso di più mapping di modello condivisi

Seguire i passaggi descritti nell'[Appendice 2](#appendix2) in questo argomento per pianificare i componenti ER necessari. Ora sono disponibili le configurazioni di mapping di modello **Mapping (generale)** e **Mapping (generale) personalizzato**, ognuna delle quali contiene il mapping di modello per la definizione **Punto di ingresso 1**.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-TreeCustom.PNG)

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato per ottenere i mapping**.
2.  Nella scheda dettaglio **Versioni** selezionare **Esegui**.
3.  Selezionare **OK**.

Si noti che l'esecuzione del formato ER selezionato ha esito negativo. Un messaggio di errore informa che esiste più di un mapping di modello per il modello **Modello per ottenere i mapping** e la definizione **Entry point 1** nelle configurazioni di mapping di modello **Mapping (generale)** e **Mapping (generale) personalizzato**. Il messaggio consiglia inoltre di selezionare una delle configurazioni come configurazione predefinita.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-FormatRunCustomFailed.PNG)

### <a name="define-a-default-mapping-configuration"></a>Definire una configurazione di mapping predefinita

Seguire questi passaggi per definire la configurazione di mapping di modello **Mapping (generale) personalizzato** come la configurazione predefinita, in modo che i mapping possano essere utilizzati come origini dati per il formato ER **Formato per ottenere i mapping**.

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping (generale) personalizzato**.
2.  Quando richiesto, scegliere **Modifica** per modificare la pagina corrente.
3.  Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.
4.  Selezionare **Salva**.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-MappingsCustomDefault.PNG)

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato per ottenere i mapping**.
2.  Nella scheda dettaglio **Versioni** selezionare **Esegui**.
3.  Selezionare **OK**.

Si noti che l'esecuzione del formato ER selezionato ha esito positivo. Il Web browser offre il download del file di testo generato dal formato ER eseguito. Poiché questo formato è stato configurato per utilizzare la definizione **Punto di ingresso 1** e la configurazione di mapping di modello **Mapping (generale) personalizzato** è stata selezionata come configurazione predefinita, il formato ER eseguito utilizza il mapping di modello **Mapping (generale) copia** della configurazione **Mapping (generale) personalizzato** come origine dati. Di conseguenza, il file scaricato contiene il testo **Funzionalità generica 1 personalizzata**.

> [!NOTE]
> Se si modifica la società a cui si è attualmente connessi ed si esegue nuovamente questo formato ER, si ottiene lo stesso contenuto nel file generato, poiché la configurazione di mapping di modello ER predefinita non contiene restrizioni dipendenti dalla società.

## <a name="multiple-mixed-model-mappings-case"></a>Caso di più mapping di modello misti

Seguire i passaggi descritti nell'[Appendice 3](#appendix3) in questo argomento per pianificare i componenti ER necessari. Ora sono disponibili le configurazioni di mapping di modello **Mapping (generale)**, **Mapping (generale) personalizzato** e **Mapping (FR)** contenenti il mapping di modello per la definizione **Punto di ingresso 1**.

Si noti che la versione 1 della configurazione di mapping di modello **Mapping (FR)** è configurata in modo che venga applicata solo ai formati ER del modello **Modello per ottenere i mapping** che vengono eseguiti nelle società Finance con il contesto del paese francese.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-TreeFR.PNG)

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Cambiare la società in **FRSI**.
2.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato per ottenere i mapping**.
3.  Nella scheda dettaglio **Versioni** selezionare **Esegui**.
4.  Selezionare **OK**.

Si noti che l'esecuzione del formato ER selezionato ha esito positivo. Il Web browser offre il download del file di testo generato dal formato ER eseguito. Poiché questo formato è stato configurato per utilizzare la definizione **Punto di ingresso 1** e la configurazione di mapping di modello **Mapping (generale) personalizzato** è stata selezionata come configurazione predefinita, il formato ER eseguito utilizza il mapping di modello **Mapping (generale) copia** della configurazione **Mapping (generale) personalizzato** come origine dati. Di conseguenza, il file scaricato contiene il testo **Funzionalità generica 1 personalizzata**.

### <a name="define-the-france-specific-mapping-configuration-as-the-default-configuration"></a>Definire la configurazione di mapping specifica della Francia come configurazione predefinita

Seguire questi passaggi per definire la configurazione di mapping di modello **Mapping (FR)** personalizzata come configurazione predefinita. Tenere presente che poiché questo mapping è specifico della Francia, verrà considerato il mapping predefinito tra tutte le configurazioni di mapping di modello con il codice paese **FR** specificato nel campo **Codici paese ISO**.

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping (FR)**.
2.  Quando richiesto, scegliere **Modifica** per modificare la pagina corrente.
3.  Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.
4.  Selezionare **Salva**.

![Pagina delle configurazioni ER](./media/RCS-Context-specific-mapping-TreeFRDefault.PNG)

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato per ottenere i mapping**.
2.  Nella scheda dettaglio **Versioni** selezionare **Esegui**.
3.  Selezionare **OK**.

Si noti che l'esecuzione del formato ER selezionato ha esito positivo. Il Web browser offre il download del file di testo generato dal formato ER eseguito. Poiché questo formato è stato configurato per utilizzare la definizione **Punto di ingresso 1** e la configurazione di mapping di modello **Mapping (FR)** è stata selezionata come configurazione predefinita, il formato ER eseguito utilizza il mapping di modello **Mapping (FR)** della configurazione **Mapping (FR)** come origine dati. Di conseguenza, il file scaricato contiene il testo **Funzionalità FR 1**.

> [!NOTE]
> Se si modifica la società a cui si è attualmente connessi e si esegue nuovamente questo formato ER, l'output dipenderà dal contesto del paese della società selezionata.

## <a name="other-model-mapping-cases"></a>Altri casi di mapping di modello

Come è stato illustrato, la selezione di un mapping di modello per l'esecuzione di un formato ER funziona nel modo seguente:

- La definizione di mapping di modello utilizzata da un formato ER è specificata (**Punto di ingresso 1** negli esempi di questo argomento).
- Tutte le configurazioni di mapping che contengono un mapping con la definizione specificata e che soddisfano eventuali restrizioni del contesto del paese configurate, possono essere potenzialmente utilizzate per eseguire il formato ER (**Mapping (generale)**, **Mapping (generale) personalizzato** e **Mapping (FR)** negli esempi di questo argomento).
- Qualsiasi mapping di modello predefinito che ha restrizioni di contesto del paese ha la massima priorità per la selezione (**Mapping (FR)** negli esempi di questo argomento).
- Qualsiasi mapping di modello predefinito che non ha restrizioni di contesto del paese ha la successiva massima priorità per la selezione (**Mapping (generale) personalizzato** negli esempi di questo argomento).
- Qualsiasi mapping di modello che ha restrizioni del contesto del paese ha una priorità di selezione più elevata rispetto a un mapping di modello che non ha restrizioni di contesto del paese.

La tabella seguente fornisce informazioni sui risultati della selezione del mapping di modello per tutti i possibili casi per le impostazioni del mapping di modello:

- La colonna 1 indica se il primo mapping di modello che non ha restrizioni di contesto del paese (ad esempio il mapping **Mapping (generale)** condiviso) viene mostrato e, in caso affermativo, se l'opzione **Impostazione predefinita per mapping di modello** è impostata su **Sì**.
- La colonna 2 indica se il secondo mapping di modello che non ha restrizioni di contesto del paese (ad esempio il mapping **Mapping (generale) personalizzato** condiviso) viene mostrato e, in caso affermativo, se l'opzione **Impostazione predefinita per mapping di modello** è impostata su **Sì**.
- La colonna 3 indica se il primo mapping di modello che ha restrizioni di contesto del paese A (ad esempio il mapping **Mapping (FR)** specifico della Francia) viene mostrato e, in caso affermativo, se l'opzione **Impostazione predefinita per mapping di modello** è impostata su **Sì**.
- La colonna 4 indica se il secondo mapping di modello che ha restrizioni di contesto del paese A viene mostrato e, in caso affermativo, se l'opzione **Impostazione predefinita per mapping di modello** è impostata su **Sì**.
- La colonna 5 presenta il risultato di una selezione di mapping di modello per l'esecuzione di un formato ER sotto il controllo di una società che ha il contesto di paese A.
- La colonna 6 presenta il risultato di una selezione di mapping di modello per l'esecuzione di un formato ER sotto il controllo di una società che ha il contesto di paese B.

Nella tabella, un segno più (+) indica la presenza di una configurazione di mapping di modello nell'istanza corrente del servizio Microsoft Azure utilizzata per eseguire un formato ER (Finance o RCS).

| Caso | Mapping di modello 1 senza contesto del paese (MM1) | Mapping di modello 2 senza contesto del paese (MM2) | Mapping di modello 1 con il contesto del paese A (MM1A) | Mapping di modello 2 con il contesto del paese A (MM2A) | Eseguire sotto il controllo di una società con un contesto di paese A. | Eseguire sotto il controllo di una società con un contesto di paese B. |
|---------|---------|---------|---------|---------|---------------------------|----------------------------|
|         |     1   |     2   |    3    |    4    |           5               |            6               |
|     1   |         |         |         |         | Errore (mapping mancante)   | Errore (mapping mancante)    |
|     2   |     +   |         |         |         | MM1                       | MM1                        |
|     3   |     +   |     +   |         |         | Errore (più mapping) | Errore (più mapping)  |
|     4   |     +   |         |    +    |         | MM1A                      | MM1                        |
|     5   |     +   |         |    +    |    +    | Errore (più mapping) | MM1                        |
|     6   |     +   | predefinito |    +    |    +    | MM2                       | MM2                        |
|     7   |     +   |         | predefinito |         | MM1A                      | MM1                        |
|     8   |     +   |         | predefinito |    +    | MM1A                      | MM1                        |
|     9   |     +   |         | predefinito | predefinito | Errore (più mapping) | MM1                        |
|    10   | predefinito |         |         |         | MM1                       | MM1                        |
|    11   | predefinito |    +    |         |         | MM1                       | MM1                        |
|    12   | predefinito |         |    +    |         | MM1                       | MM1                        |
|    13   | predefinito | predefinito |         |         | Errore (più mapping) | Errore (più mapping)  |
|    14   | predefinito |         | predefinito |         | MM1A                      | MM1                        |
|    15   | predefinito |         | predefinito | predefinito | MM1A                      | MM2A                       |
|    16   |         |         |    +    |    +    | MM1A                      | MM2A                       |
|    17   |         |         | predefinito | predefinito | MM1A                      | MM2A                       |

## <a name="learn-what-mapping-was-used-in-the-execution-of-an-er-format"></a>Informazioni sul mapping utilizzato per l'esecuzione di un formato di ER

### <a name="configure-er-user-parameters"></a>Configurare i parametri utente ER

1.  Nella pagina **Configurazioni**, nel Riquadro azioni, nella scheda **CONFIGURAZIONI**, selezionare **Parametri utente**.
2.  Impostare l'opzione **Esegui in modalità di debug** su **Sì**.
4.  Selezionare **OK**.

### <a name="run-the-configured-format"></a>Eseguire il formato configurato

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Formato per ottenere i mapping**.
2.  Nella scheda dettaglio **Versioni** selezionare **Esegui**.
3.  Selezionare **OK**.

### <a name="review-the-er-debug-log"></a>Esaminare il registro di debug ER

1.  Nel pannello di navigazione andare a **Moduli \> Amministrazione organizzazione \> Creazione di report elettronici \> Registri debug configurazione**.
2.  Fare clic sul pulsante **Ricaricare la pagina**.

![Pagina dei log di esecuzione ER](./media/RCS-Context-specific-mapping-DebugLog.PNG)

Si noti che un nuovo record è stato aggiunto al registro di debug ER per il formato ER eseguito. Poiché il campo **Livello** del record è impostato su **Informazioni**, il record è informativo. Poiché il campo Componente formato è impostato su **Configurazione del mapping**, il record comunica che un mapping di modello è stato utilizzato durante l'esecuzione del formato ER **Formato per ottenere i mapping** (selezionato nel campo **Nome configurazione** ). Il contenuto del campo **Testo generato** comunica che il componente di mapping **Mapping (FR)** che si trova nella configurazione **Mapping (FR)** è stato utilizzato per eseguire il report.

## <a name="appendix-1"></a><a name="appendix1"></a> Appendice 1

### <a name="configure-a-sample-data-model"></a>Configurare un modello di dati di esempio

Accedere all'istanza RCS.

In questo esempio si creerà una configurazione per la società di esempio Litware, Inc. Per eseguire questi passaggi, è necessario completare prima in RCS i passaggi della procedura [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md).

#### <a name="create-an-er-data-model-configuration"></a>Creare una configurazione del modello di dati ER

1.  Nel dashboard predefinito, selezionare **Creazione di report elettronici**.
2.  Selezionare il riquadro **Configurazioni report**.
3.  Nella pagina **Configurazioni**, selezionare **Crea configurazione**.
4.  Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Modello per ottenere i mapping**.
5.  Selezionare **Crea configurazione**.
6.  Selezionare la Scheda dettaglio **Componenti di configurazione**.

Si noti che la versione bozza 1 della configurazione ER è pronta per la modifica. Questa versione contiene il componente del modello di dati.

#### <a name="design-a-sample-data-model"></a>Progettare un modello di dati di esempio

1.  Nella pagina **Configurazioni**, selezionare **Progettazione**.
2.  Selezionare **Nuovo**.
3.  Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Punto di ingresso 1**.
4.  Selezionare **Aggiungi**.
5.  Selezionare **Nuovo**.
6.  Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Descrizione funzionalità**.
7.  Selezionare **Aggiungi**.
8.  Selezionare **Nuovo**.
9.  Nella finestra di dialogo a discesa, nel campo **Nuovo nodo**, selezionare **Radice modello**.
10. Nel campo **Nome**, immettere **Punto di ingresso 2**.
11. Selezionare **Punto di ingresso 2**.
12. Selezionare **Aggiungi**.
13. Selezionare **Nuovo**.
14. Nella finestra di dialogo a discesa, nel campo **Nome**, immettere **Descrizione funzionalità**.
15. Selezionare **Aggiungi**.

    ![Pagina della progettazione del modello di dati ER](./media/RCS-Context-specific-mapping-Model.PNG)

16. Selezionare **Salva**.
17. Chiudere la pagina.

#### <a name="complete-the-modified-version-of-the-model-configuration"></a>Completare la versione modificata della configurazione del modello

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Cambia stato**.

    > Modificare lo stato della configurazione del modello progettato da **Bozza** a **Completato**, in modo che possa essere utilizzato per progettare i mapping e i formati del modello richiesti.

2.  Selezionare **Completa**.
3.  Selezionare **OK**.

Si noti che la configurazione creata viene salvata come versione completata 1.

### <a name="configure-a-sample-model-mapping"></a>Configurare un mapping di modello di esempio

#### <a name="create-an-er-model-mapping-configuration"></a>Crea una configurazione del mapping di modello ER

1.  Nella pagina **Configurazioni**, selezionare **Crea configurazione**.
2.  Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare l'opzione **Mapping di modello basato sul modello di dati Modello per ottenere mapping**.
3.  Nel campo **Nome**, immettere **Mapping (generale)**.
4.  Selezionare **Punto di ingresso 1** nel campo **Definizione modello dati**.
5.  Selezionare **Crea configurazione**.

Si noti che la versione bozza 1 della configurazione ER è pronta per la modifica. Questa versione contiene il componente mapping di modello.

#### <a name="design-a-sample-model-mapping"></a>Progettare un mapping di modello di esempio

1.  Nella pagina **Configurazioni**, selezionare **Progettazione**.

    Si noti che il mapping di modello con il tipo di direzione **A modello** è stato aggiunto automaticamente a questo componente per la definizione **Punto di ingresso 1**.
    
2.  Selezionare **Progettazione** per avviare la modifica del mapping di modello aggiunto.
3.  Selezionare **Modifica** nella sezione **Modello dati**.
4.  Nel campo **Formula** immettere **"Funzionalità generica 1"**.
5.  Selezionare **Salva**.
6.  Chiudere la pagina **Designer formula**.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping1.PNG)

7.  Selezionare **Salva**.
8.  Chiudere la pagina **Progettazione mapping modello**.
9.  Selezionare **Nuovo**.
10. Selezionare **Punto di ingresso 2** nel campo **Definizione**.
11. Nel campo **Nome**, immettere **Mapping (generale) 2**.
12. Selezionare **Progettazione**.
13. Selezionare **Modifica** nella sezione **Modello dati**.
14. Nel campo **Formula** immettere **"Funzionalità generica 2"**.
15. Selezionare **Salva**.
16. Chiudere la pagina **Designer formula**.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping2.PNG)

17. Selezionare **Salva**.
18. Chiudere la pagina **Progettazione mapping modello**.

    ![Pagina dei mapping di modello ER](./media/RCS-Context-specific-mapping-Mappings.PNG)

19. Chiudere la pagina **Mapping modello**.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completare la versione modificata della configurazione del mapping di modello

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Cambia stato**.

    > Modificare lo stato della configurazione del mapping di modello progettato da **Bozza** a **Completato**, in modo che possa essere utilizzato dai formati ER.

2.  Selezionare **Completa**.
3.  Selezionare **OK**.

Si noti che la configurazione creata viene salvata come versione completata 1.

### <a name="configure-a-sample-format"></a>Configurare un formato di esempio

#### <a name="create-an-er-format-configuration"></a>Creare una configurazione di formato ER

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Modello per ottenere i mapping**.
2.  Selezionare **Crea configurazione**.
3.  Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare l'opzione **Formato basato sul modello di dati Modello per ottenere mapping**.
4.  Nel campo **Nome**, immettere **Formato per ottenere mapping**.
5.  Selezionare **Punto di ingresso 1** nel campo **Definizione modello dati**.
6.  Selezionare **Crea configurazione**.

Si noti che la versione bozza 1 della configurazione ER è pronta per la modifica. Questa versione contiene il componente del formato.

#### <a name="design-a-sample-format"></a>Progettare un formato di esempio

1.  Nella pagina **Configurazioni**, selezionare **Progettazione**.
2.  Selezionare **Aggiungi radice**.
3.  Nel gruppo **Testo** selezionare la voce **Stringa**.
4.  Selezionare **OK**.

#### <a name="bind-format-elements-to-a-data-source"></a>Associare gli elementi di formato a un'origine dati

1.  Nella pagina **Progettazione formati**, nella scheda **Mapping**, espandere l'origine dati del modello.
2.  Selezionare il campo **Descrizione funzionalità**.
3.  Selezionare **Associa**.

    ![Pagina della progettazione del formato ER](./media/RCS-Context-specific-mapping-Format.PNG)

4.  Selezionare **Salva**.
5.  Chiudere la pagina.

## <a name="appendix-2"></a><a name="appendix2"></a> Appendice 2

### <a name="configure-a-sample-model-mapping-for-general-customization"></a>Configurare un mapping di modello di esempio per la personalizzazione generale

È possibile personalizzare un mapping di modello fornito da un provider di configurazione (partner) e quindi utilizzare la versione personalizzata come origine dei dati per i formati ER. In questo caso, è necessario creare una configurazione di mapping di modello ER personalizzata per apportare le modifiche necessarie nei mapping di modello esistenti. Le procedure in questa appendice utilizzano il mapping di modello **Mapping (generale)** come esempio.

#### <a name="create-an-er-model-mapping-configuration"></a>Crea una configurazione del mapping di modello ER

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping (generale)**.
2.  Selezionare **Crea configurazione**.
3.  Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare **Deriva da nome: Mapping (generale), Litware, Inc.**
4.  Nel campo **Nome**, immettere **Mapping (generale) personalizzato**.
5.  Selezionare **Crea configurazione**.

Si noti che la versione bozza 1 della configurazione ER è pronta per la modifica.

#### <a name="design-a-sample-model-mapping"></a>Progettare un mapping di modello di esempio

1.  Nella pagina **Configurazioni**, selezionare **Progettazione**.

    > Si noti che i mapping di modello della configurazione di base sono stati copiati automaticamente in questa configurazione.

2.  Selezionare il mapping **Mapping (generale) copia**.
3.  Selezionare **Progettazione**.
4.  Selezionare **Modifica** nella sezione **Modello dati**.
5.  Nel campo **Formula** immettere **"Funzionalità generica 1 personalizzata"**.
6.  Selezionare **Salva**.
7.  Chiudere la pagina.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping1Custom.PNG)

8.  Selezionare **Salva**.
9.  Chiudere la pagina.
10. Selezionare il mapping **Mapping (generale) 2 copia**.
11. Selezionare **Progettazione**.
12. Selezionare **Modifica** nella sezione **Modello dati**.
13. Nel campo **Formula** immettere **"Funzionalità generica 2 personalizzata"**.
14. Selezionare **Salva**.
15. Chiudere la pagina.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping2Custom.PNG)

16. Selezionare **Salva**.
17. Chiudere la pagina.

    ![Pagina dei mapping di modello ER](./media/RCS-Context-specific-mapping-MappingsCustom.PNG)

18. Chiudere la pagina.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completare la versione modificata della configurazione del mapping di modello

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Cambia stato**.

    > Modificare lo stato della configurazione del mapping di modello progettato da **Bozza** a **Completato**, in modo che possa essere utilizzato dai formati ER.

2.  Selezionare **Completa**.
3.  Selezionare **OK**.

Si noti che la configurazione creata viene salvata come versione completata 1.

## <a name="appendix-3"></a><a name="appendix3"></a> Appendice 3

### <a name="configure-a-sample-model-mapping-for-countryregion-specific-customization"></a>Configurare un mapping di modello di esempio per la personalizzazione specifica del paese

Per alcuni formati ER, è possibile che vi siano requisiti specifici del paese per la preparazione dei dati. In questo caso, è possibile gestire una configurazione di mapping di modello ER separata e isolare l'implementazione di questi requisiti specifici del paese dall'implementazione generale. Le procedure in questa appendice utilizzano il formato ER **Formato per ottenere i mapping** e i requisiti specifici della Francia, come esempio.

#### <a name="create-an-er-model-mapping-configuration"></a>Crea una configurazione del mapping di modello ER

Innanzitutto, creare una nuova configurazione di mapping di modello ER per implementare i requisiti specifici del paese. Utilizzare la configurazione di mapping di modello ER personalizzata come base.

1.  Nella pagina **Configurazioni**, nella struttura della configurazione, selezionare **Mapping (generale) personalizzato**.
2.  Selezionare **Crea configurazione**.
3.  Nella finestra di dialogo a discesa, nel gruppo di campi **Nuovo**, selezionare **Deriva da nome: Mapping (generale) personalizzato, Litware, Inc.**
4.  Nel campo **Nome**, immettere **Mapping (FR)**.
5.  Selezionare **Crea configurazione**.

Si noti che la versione bozza 1 della configurazione ER è pronta per la modifica.

#### <a name="design-a-sample-model-mapping"></a>Progettare un mapping di modello di esempio

1.  Nella pagina **Configurazioni**, selezionare **Progettazione**.

    > Si noti che i mapping di modello della configurazione di base sono stati copiati automaticamente in questa configurazione.

2.  Selezionare il mapping **Mapping (generale) copia copia**.
3.  Ridenominarla in **Mapping (FR)**.
4.  Selezionare **Progettazione**.
5.  Selezionare **Modifica** nella sezione **Modello dati**.
6.  Nel campo **Formula** immettere **"Funzionalità FR 1"**.
7.  Selezionare **Salva**.
8.  Chiudere la pagina.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping1FR.PNG)

9.  Selezionare **Salva**.
10. Chiudere la pagina.
11. Selezionare il mapping **Mapping (generale) 2 copia copia**.
12. Ridenominarla in **Mapping (FR) 2**.
13. Selezionare **Progettazione**.
14. Selezionare **Modifica** nella sezione **Modello dati**.
15. Nel campo **Formula** immettere **"Funzionalità FR 2"**.
16. Selezionare **Salva**.
17. Chiudere la pagina.

    ![Pagina della progettazione mapping modello di ER](./media/RCS-Context-specific-mapping-Mapping2FR.PNG)

18. Selezionare **Salva**.
19. Chiudere la pagina.

    ![Pagina dei mapping di modello ER](./media/RCS-Context-specific-mapping-MappingsFR.PNG)

20. Chiudere la pagina.

#### <a name="specify-countryregion-context-restrictions-for-use"></a>Specificare le restrizioni del contesto del paese per l'utilizzo

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Codici paese ISO**, selezionare **Nuovo**.
2.  Nel campo **ISO** selezionare **FR**.
3.  Selezionare **Salva**.

Si noti che è necessario accedere a una società specifica in Finance per eseguire un formato ER. Di conseguenza, la società può essere considerata una parte che controlla l'esecuzione del formato ER e la selezione del mapping di modello ER corretto del modello dati ER di base. Aggiungendo il codice paese **FR**, si specifica che il mapping di modello è disponibile per la selezione per un un formato ER del modello di dati di base solo quando il formato viene eseguito sotto il controllo di una società con il contesto di paese francese.

È possibile aggiungere più codici paese per una singola versione della configurazione di mapping di modello ER. In questo modo, i mapping di modello inclusi nella configurazione di mapping di modello possono essere utilizzati per un formato ER eseguito sotto il controllo delle società con un contesto di paese diverso.

Tenere presente che l'elenco dei codici paese è specificato per ogni versione della configurazione di mapping di modello ER e può variare da versione a versione.

#### <a name="complete-the-modified-version-of-the-model-mapping-configuration"></a>Completare la versione modificata della configurazione del mapping di modello

1.  Nella pagina **Configurazioni**, nella scheda dettaglio **Versioni**, selezionare **Cambia stato**.

    > Modificare lo stato della configurazione del mapping di modello progettato da **Bozza** a **Completato**, in modo che possa essere utilizzato dai formati ER.

2.  Selezionare **Completa**.
3.  Selezionare **OK**.

Si noti che la configurazione creata viene salvata come versione completata 1.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md)

[Gestire il mapping dei modelli ER in configurazioni ER separate](./tasks/er-manage-model-mapping-configurations-july-2017.md)

[Applicare il contesto del paese](../lcs-solutions/apply-country-context.md)

## <a name="frequently-asked-questions"></a>Domande frequenti

#### <a name="i-configured-two-shared-er-model-mapping-configurations-in-rcs-and-marked-one-of-them-as-the-default-model-mapping-configuration-i-successfully-ran-an-er-format-that-was-created-for-the-same-base-er-data-model-configuration-to-test-model-mappings-i-then-imported-the-whole-er-solution-er-data-model-two-er-model-mapping-configurations-and-er-format-configuration-into-finance-why-do-i-receive-an-error-message-when-i-try-to-run-the-same-er-format-in-finance"></a>Sono state configurate due configurazioni di mapping di modello ER condivise in RCS e ne è stata contrassegnata una come configurazione di mapping di modello predefinita. È stato eseguito un formato ER creato per la stessa configurazione del modello di dati ER di base, per testare i mapping di modello. Quindi è stata importata l'intera soluzione ER (modello di dati ER, due configurazioni di mapping di modello ER e la configurazione del formato ER) in Finance. Perché viene restituito un messaggio di errore quando si prova a eseguire lo stesso formato ER in Finance?
L'impostazione del mapping di modello predefinita è specifica per l'ambiente. È stata configurata in RCS ma non è stata esportata in Finance. Per eseguire correttamente questo formato ER, è necessario contrassegnare una delle configurazioni di mapping di modello ER come configurazione di mapping di modello predefinita anche per Finance.

#### <a name="i-configured-one-model-mapping-as-a-shared-model-mapping-and-completed-the-draft-version-of-it-i-then-added-a-new-model-mapping-configuration-for-same-data-model-and-configured-it-as-french-specific-why-is-the-shared-model-mapping-selected-when-i-run-an-er-format-even-though-this-er-format-uses-the-correct-root-definition-and-execution-is-done-under-the-control-of-the-company-that-has-french-countryregion-context"></a>È stato configurato un mapping di modello come mapping di modello condiviso ed è stato completato in bozza. È stata quindi aggiunta una nuova configurazione di mapping di modello per lo stesso modello di dati ed è stata configurata come specifica per il francese. Perché il mapping di modello condiviso viene selezionato quando si esegue un formato ER, anche se questo formato ER utilizza la definizione radice corretta e l'esecuzione viene eseguita sotto il controllo della società che ha un contesto di paese francese?
Verificare che la configurazione di mapping di modello condivisa non sia contrassegnata come configurazione di mapping di modello predefinita. In caso contrario, avrà una priorità più alta durante la selezione del mapping. Controllare inoltre che la configurazione di mapping di modello specifica del francese venga considerata quando un mapping viene selezionato durante l'esecuzione del formato ER. Una configurazione di mapping di modello ER è disponibile per la selezione solo se almeno una delle seguenti condizioni viene soddisfatta:
- Almeno una versione della configurazione del mapping di modello ER è nello stato **Completato** o **Condiviso**. In questo caso, la versione con il numero più alto verrà utilizzata per l'esecuzione del formato ER.
- L'opzione **Esegui bozza** per la configurazione di mapping di modello ER è abilitata. In questo caso, la versione con lo stato **Bozza** verrà utilizzata per l'esecuzione del formato ER.
> L'opzione **Esegui bozza** diventa disponibile nella pagina **Configurazioni** per ogni configurazione di mapping di modello ER quando il parametro dell'utente ER **Esegui impostazione** è abilitato.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]