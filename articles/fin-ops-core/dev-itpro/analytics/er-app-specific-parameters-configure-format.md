---
title: Configurare i formati di ER per utilizzare i parametri specifici per la persona giuridica
description: In questo argomento viene descritto come configurare i formati per la creazione di report elettronici (ER) specifici per la persona giuridica.
author: NickSelin
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, EROperationDesigner, ERLookupDesigner, ERComponentLookupStructureEditing
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-01-01
ms.dyn365.ops.version: Release 8.1.3
ms.openlocfilehash: 0af3e1d589fd99cc722d8aedeb9596388a9e2e8c
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018288"
---
# <a name="configure-er-formats-to-use-parameters-that-are-specified-per-legal-entity"></a>Configurare i formati di ER per utilizzare i parametri specifici per la persona giuridica

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Panoramica

In molti dei formati di creazione di report elettronici (ER) che verranno progettati, è necessario filtrare i dati utilizzando un set di valori specifici per ciascuna persona giuridica della propria istanza (ad esempio, un set di codici imposta per filtrare le transazioni fiscali). Attualmente, quando il filtro di questo tipo è configurato in un formato ER, i valori che dipendono dalla persona giuridica (ad esempio, codici imposta) vengono utilizzati nelle espressioni del formato ER per specificare le regole di filtro dei dati. Pertanto, il formato ER è specifico per la persona giuridica e per generare i report richiesti, è necessario creare copie derivate del formato ER originale per ciascuna persona giuridica in cui è necessario eseguire il formato ER. Ogni formato ER derivato deve essere modificato in modo da includere i valori specifici della persona giuridica, riformulato ogni volta che la versione (base) originale viene aggiornata, esportato da un ambiente di test e importato in un ambiente di produzione quando deve essere distribuito per l'uso in produzione e così via. Pertanto, la manutenzione di questo tipo di soluzione ER configurata è complessa e richiede molto tempo per diversi motivi:

-   Più sono le persone giuridiche, più configurazioni di formato ER devono essere mantenute.
-   La manutenzione delle configurazioni ER richiede che gli utenti aziendali abbiano conoscenze di ER.

La funzione dei parametri specifici dell'applicazione ER consente agli utenti esperti di configurare il filtro dati in un formato ER in modo che sia basato su un set di regole astratte. Questo set di regole può essere configurato per utilizzare le origini dati disponibili in un formato ER. Gli utenti aziendali possono quindi specificare regole reali oltre il framework ER utilizzando l'interfaccia utente (UI) che viene generata automaticamente in base alle impostazioni del formato ER corrispondente e ai dati della persona giuridica corrente a cui accederanno le origini dati del formato ER. Il set di regole specificato per un formato ER può essere esportato dall'entità legale corrente dell'istanza Dynamics 365 Finance (Finance). Può quindi essere importato in un'altra persona giuridica della stessa istanza di Finance o in un'istanza diversa come set di regole per lo stesso formato ER.

## <a name="prerequisites"></a>Prerequisiti

Per completare gli esempi in questo argomento è necessario disporre dell'accesso all'istanza di Regulatory Configuration Service (RCS) di cui è stato eseguito il provisioning per lo stesso tenant di Finance per uno dei seguenti ruoli:

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

Si consiglia di completare i passaggi descritti nell'argomento [Supportare le chiamate con parametri di origini dati ER del tipo di campo calcolato](er-calculated-field-type.md). Se sono già stati completati questi passaggi, è possibile ignorare i passaggi nella sezione **Importare le configurazioni di ER in RCS** che segue.

## <a name="import-er-configurations-into-rcs"></a>Importare le configurazioni di ER in RCS

Scarica e archivia localmente le seguenti configurazioni ER.

| **Descrizione contenuto**                        | **Nome file**                                        |
|------------------------------------------------|------------------------------------------------------|
| File di configurazione del **modello di dati ER** di esempio    | [Model to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/2/d/b/2db913a0-3622-494e-91a2-97fc494af9b9/Modeltolearnparameterizedcalls.version.1.xml)     |
| File di configurazione dei **metadati ER** di esempio      | [Metadata to learn parameterized calls.version.1.xml](https://download.microsoft.com/download/1/b/3/1b343968-5a47-4000-b5a8-6487698ef4c0/Metadatatolearnparameterizedcalls.version.1.xml)  |
| File di configurazione del **mapping di modello ER** di esempio | [Mapping to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/8/6/6/866e0ab6-2e05-4d98-9d52-d2da2038f6e4/Mappingtolearnparameterizedcalls.version.1.1.xml) |
| Configurazione di **formato ER** di esempio             | [Format to learn parameterized calls.version.1.1.xml](https://download.microsoft.com/download/e/3/9/e392eadc-b9b4-4834-95c3-b8066dd00b9c/Formattolearnparameterizedcalls.version.1.1.xml)  |

Accedere all'istanza RCS.

In questo esempio verrà creata una configurazione per la società di esempio Litware, Inc. Per poter eseguire questa procedura, è necessario completare i passaggi descritti nell'argomento [Creare un provider di configurazione e contrassegnarlo come attivo](tasks/er-configuration-provider-mark-it-active-2016-11.md) in RCS.

1.  Nel dashboard predefinito, selezionare **Creazione di report elettronici**.
2.  Selezionare **Configurazioni report**.
3.  Importare le configurazioni ER scaricate precedentemente in RCS nel seguente ordine: modello di dati, metadati, mapping di modello e formato. Per ogni configurazione ER, procedere come segue:

    1.  Selezionare **Scambia**.
    2.  Selezionare **Carica da file XML**.
    3.  Selezionare **Sfoglia** per selezionare il file per la configurazione ER necessaria in formato XML.
    4.  Selezionare **OK**.

## <a name="review-the-er-solution-that-is-provided"></a>Esaminare la soluzione ER fornita

1.  Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2.  Selezionare l'elemento **Formato per ottenere chiamate parametrizzate**.
3.  Selezionare **Progettazione**.
4.  Selezionare **Espandi/Comprimi**.

    Il formato ER **Formato per ottenere chiamate parametrizzate** è progettato per generare una dichiarazione fiscale in formato XML che presenti diversi livelli di tassazione (regolare, ridotta e nessuna). Ogni livello ha un numero diverso di dettagli.

    ![Più livelli di formato ER, formato per apprendere le chiamate parametrizzate](./media/RCS-AppSpecParms-ReviewFormat.PNG)

5.  Nella scheda **Mapping**, espandere le voci **Modello**, **Dati** e **Riepilogo**.

    L'origine dati **Model.Data.Summary** restituisce l'elenco delle transazioni fiscali. Le transazioni vengono riepilogate in base al codice imposta. Per questa origine dati, il campo calcolato **Model.Data.Summary.Level** è stato configurato per restituire il codice del livello di tassazione di ciascun record di riepilogo. Per qualsiasi codice imposta che può essere recuperato dall'origine dati **Model.Data.Summary** in fase di esecuzione, il campo calcolato restituisce il codice a livello di tassazione (**Regolare**, **Ridotto**, **Nessuno** o **Altro**) come valore di testo. Il campo calcolato **Model.Data.Summary.Level** viene utilizzato per filtrare i record dell'origine dati **Model.Data.Summary** e immettere i dati filtrati in ciascun elemento XML che rappresenta un livello di tassazione utilizzando i campi **Model.Data2.Level1**, **Model.Data2.Level2** e **Model.Data2.Level3**.

    ![L'elenco delle origine dati Model.Data.Summary delle transazioni fiscali](./media/RCS-AppSpecParms-ReviewFormat-Data2Fld.PNG)

    Il campo calcolato **Model.Data.Summary.Level** è stato configurato in modo che contenesse un'espressione ER. I codici imposta (**VAT19**, **InVAT19**, **VAT7**, **InVAT7**, **THIRD** e **InVAT0**) sono hardcoded nella configurazione. Di conseguenza, il formato di ER dipende dalla persona giuridica in cui i codici imposta sono stati configurati.

    ![Il campo calcolato Model.Data.Summary.Level con codici IVA hardcoded](./media/RCS-AppSpecParms-ReviewFormat-LevelFld.PNG)

    Per supportare un set di codici imposta diverso per ciascuna persona giuridica, è necessario completare i seguenti passaggi:

    - Creare una versione derivata del formato di ER per ogni persona giuridica.
    - Aggiornare i codici imposta nel campo calcolato **Model.Data.Summary.Level**, in base alle impostazioni della persona giuridica.

6.  Chiudere la pagina **Progettazione formati**.

## <a name="create-a-derived-format"></a>Creare un formato derivato

Successivamente, viene utilizzata la funzione dei parametri specifici dell'applicazione ER per supportare un diverso set di codici imposta per ciascuna entità legale in un unico formato ER.

1.  Nella struttura delle configurazioni, espandere il contenuto dell'elemento **Modello per ottenere chiamate parametrizzate**.
2.  Selezionare l'elemento **Formato per ottenere chiamate parametrizzate**.
3.  Selezionare **Crea configurazione**.
4.  Selezionare l'opzione **Deriva da nome: Formato per ottenere chiamate parametrizzate, Microsoft**.
5.  Nel campo **Nome**, immettere **Formato per ottenere ricerche di dati di persona giuridica**.
6.  Selezionare **Crea configurazione**.

## <a name="configure-a-derived-format"></a>Configurare un formato derivato

### <a name="add-a-format-enumeration"></a>Aggiungere un'enumerazione di formato

A questo punto, si aggiunge una nuova enumerazione di formato ER. I valori dell'enumerazione di formato vengono presentati agli utenti aziendali che specificano i set dipendenti dalla persona giuridica dei codici imposta per diversi livelli di tassazione utilizzati nel formato di ER.

1.  Selezionare **Progettazione**.
2.  Selezionare **Enumerazioni di formato**.
3.  Selezionare **Aggiungi**.
4.  Nel campo **Nome**, immettere **Elenco di livelli di tassazione**.
5.  Selezionare **Salva**.
6.  Nella scheda **Valori di enumerazione di formato**, scegliere **Aggiungi**.
7.  Nel campo **Nome**, immettere **Tassazione regolare**.
8.  Selezionare **Aggiungi** nuovamente.
9.  Nel campo **Nome**, immettere **Tassazione ridotta**.
10. Selezionare **Aggiungi** nuovamente.
11. Nel campo **Nome**, immettere **Nessuna tassazione**.
12. Selezionare **Aggiungi** nuovamente.
13. Nel campo **Nome** immettere **Altro**.

    ![Nuovo record nella pagina Enumerazioni di formato](./media/RCS-AppSpecParms-ConfigureFormat-Enum.PNG)

    Poiché gli utenti aziendali potrebbero utilizzare lingue diverse per specificare i set di codici imposta dipendenti dall'entità legale, si consiglia di tradurre i valori di questo elenco nelle lingue configurate come lingue preferite per gli utenti in Finance.

14. Selezionare il record **Nessuna tassazione**.
15. Fare clic nel campo **Etichetta**.
16. Selezionare **Traduci**.
17. Nel riquadro **Traduzione del testo**, nel campo **ID etichetta**, immettere **LBL_LEVELENUM_NO**.
18. Nel campo **Testo in lingua predefinita**, immettere **Nessuna tassazione**.
19. Nel campo **Lingua** selezionare **DE**.
20. Nel campo **Testo tradotto** immettere **keine Besteuerung**.
21. Selezionare **Traduci**.

    ![Dispositivo di scorrimento della traduzione del testo](./media/RCS-AppSpecParms-ConfigureFormat-EnumTranslate.PNG)

22. Selezionare **Salva**.
23. Chiudere la pagina **Enumerazioni di formati**.

### <a name="add-a-new-lookup-data-source"></a>Aggiungere una nuova origine dati di ricerca

A questo punto, si aggiunte una nuova origine dati per specificare in che modo gli utenti aziendali specificano le regole dipendenti dalla persona giuridica per riconoscere il livello di tassazione corretto per ciascun record di transazione del riepilogo.

1.  Nella scheda **Mapping**, selezionare **Aggiungi**.
2.  Selezionare **Enumerazione di formato\Ricerca**.

    È stato appena identificato che ogni regola specificata dagli utenti aziendali per il riconoscimento del livello di tassazione restituisce un valore di un'enumerazione di formato ER. Si noti che è possibile accedere al tipo di origine dati **Ricerca** dai blocchi **Dynamics 365 for Operations** e **Modello dati** oltre al blocco **Enumerazione di formato**. Di conseguenza, le enumerazioni del modello di dati ER e le enumerazioni dell'applicazione possono essere utilizzate per specificare il tipo di valori che vengono restituiti per le origini dati di questo tipo. Per saperne di più sulle origini dati di tipo **Ricerca**, vedere la [funzionalità Configurare le origini dati di ricerca per utilizzare i parametri specifici dell'applicazione ER](er-lookup-data-sources.md).
    
3.  Nel campo **Nome** immettere **Selettore**.
4.  Nel campo **Enumerazione di formato**, selezionare **Elenco di livelli di tassazione**.

    È stato specificato che, per ciascuna regola specificata in questa origine dati, un utente aziendale deve selezionare uno dei valori dell'enumerazione di formato **Elenco di livelli di tassazione** come valore restituito.
    
5.  Selezionare **Modifica ricerca**.
6.  Selezionare **Colonne**.
7.  Espandere l'elemento **Model**.
8.  Espandere l'elemento **Dati**.
9.  Espandere l'elemento **Imposta**.
10. Selezionare l'elemento **Model.Data.Tax.Code**.
11. Fare clic sul pulsante **Aggiungi** (la freccia a destra).

    ![Dispositivo di scorrimento dell colonne](./media/RCS-AppSpecParms-ConfigureFormat-Lookup1.PNG)

    È stato appena specificato che, per ciascuna regola specificata in questa origine dati per l'individuazione del livello di tassazione, un utente aziendale deve selezionare uno dei codici imposta come condizione. L'elenco dei codici imposta che l'utente aziendale può selezionare viene restituito dall'origine dati **Model.Data.Tax**. Poiché l'origine dati contiene il campo **Nome**, il nome del codice imposta viene visualizzato per ogni valore di codice imposta nella ricerca che viene presentata all'utente aziendale.
    
12. Selezionare **OK**.

    ![Pagina Progettazione ricerca](./media/RCS-AppSpecParms-ConfigureFormat-Lookup2.PNG)

    Gli utenti aziendali possono aggiungere più regole come record dell'origine dati. Ogni record viene numerato da un codice riga. Le regole vengono valutate per numero di riga crescente.

    Poiché il campo **Codice imposta** è stato selezionato come condizione per le regole dell'origine dati di ricerca e poiché il **Codice imposta** è impostato come campo di tipo di dati **Stringa**, ciascuna regola verrà valutata in fase di esecuzione confrontando il codice imposta che viene passato all'origine dati con il codice imposta definito nel record dell'origine dati.

    Quando viene trovata una regola che soddisfa la condizione configurata, questa origine dati restituisce il valore di ricerca della regola definita nel campo **Risultato della ricerca**. Se non viene trovata alcuna regola, viene generata un'eccezione per avvisare l'utente che l'origine dati corrente non può restituire un valore corretto.

13. Selezionare **Salva**.
14. Chiudere la pagina **Progettazione ricerca**.
15. Selezionare **OK**.

    Si noti che è stata aggiunta una nuova origine dati che restituisce il livello di tassazione come valore dell'enumerazione di formato **Elenco dei livelli di tassazione** per ogni codice imposta che viene passato all'origine dati come argomento del parametro **Codice** del tipo di dati **Stringa**.
    
    ![Pagina Progettazione formato con una nuova origine dati](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld.PNG)

    La valutazione delle regole configurate dipende dal tipo di dati dei campi selezionati per definire le condizioni di tali regole. Quando si seleziona un campo configurato come campo di tipo di dati **Numerico** o **Data**, i criteri differiranno dai criteri che sono stati descritti in precedenza per il tipo di dati **Stringa**. Per i campi di tipo **Dati** e **Numerico**, la regola deve essere specificata come intervallo di valori. La condizione della regola viene quindi considerata soddisfatta quando un valore che viene passato all'origine dati è compreso nell'intervallo configurato.
    
    Di seguito viene illustrato un esempio di questo tipo di impostazione. Oltre al campo **Model.Data.Tax.Code** del tipo di dati **Stringa**, il campo **Model.Tax.Summary.Base** del tipo di dati **Reale** viene utilizzato per specificare le condizioni di un'origine dati di ricerca.
    
    ![Pagina Progettazione ricerca con colonne aggiuntive](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFld2.PNG)

    Poiché i campi **Model.Tax.Summary.Base** e **Model.Data.Tax.Code** sono selezionati per l'origine dati di ricerca, ogni regola dell'origine dati viene configurata nel seguente modo:
    
    -   Nell'elenco presentato, il valore dell'enumerazione di formato **Elenco dei livelli di tassazione** deve essere selezionato come valore restituito.
    -   Il codice imposta deve essere immesso come condizione della regola. Solo i codici imposta forniti dall'origine dati **Model.Data.Tax** sono applicabili.
    -   I valori minimo e massimo dell'importo imponibile devono essere immessi come condizioni della regola.

    Di seguito viene illustrato come ogni regola dell'origine dati viene valutata in fase di esecuzione:
    -   Il codice del tipo di dati **Stringa** passato all'origine dati corrisponde al codice imposta della regola?
    -   Il valore del tipo di dati **Reale** passato all'origine dati è compreso tra il valore minimo e il valore massimo specificati?

    Una regola verrà considerata applicabile quando entrambe le condizioni sono soddisfatte.

### <a name="translate-the-label-of-the-lookup-data-source-that-was-added"></a>Tradurre l'etichetta dell'origine dati di ricerca aggiunta

Poiché gli utenti aziendali potrebbero utilizzare lingue diverse per specificare i set di codici imposta dipendenti dall'entità legale, si consiglia di tradurre l'etichetta di qualsiasi origine dati di ricerca che si aggiunge in modo che sia presentata nella lingua preferita di ciascun utente nella pagina corrispondente.

1.  Selezionare l'origine dati **Model.Data.Selector**.
2.  Selezionare **Modifica**.
3.  Fare clic nel campo **Etichetta**.
4.  Selezionare **Traduci**.
5.  Nel riquadro **Traduzione del testo**, nel campo **ID etichetta**, immettere **LBL_SELECTOR_DS**.
6.  Nel campo **Testo in lingua predefinita**, immettere **Selezionare il livello di tassazione per codice imposta**.
7.  Nel campo **Lingua** selezionare **DE**.
8.  Nel campo **Testo tradotto**, immettere **Steuerebene für Steuerkennzeichen auswählen**.
9.  Selezionare **Traduci**.
10. Selezionare **OK**.

    ![Dispositivo di scorrimento delle proprietà dell'origine dati](./media/RCS-AppSpecParms-ConfigureFormat-SelectorFldTranslate.PNG)

### <a name="add-a-new-field-to-consume-the-configured-lookup"></a>Aggiungere un nuovo campo per utilizzare la ricerca configurata

1.  Espandere l'elemento **Model.Data**.
2.  Selezionare l'elemento **Model.Data.Summary**.
3.  Selezionare **Aggiungi**.
4.  Selezionare **Funzioni/Campo calcolato**.
5.  Nel campo **Nome**, immettere **LevelByLookup**.
6.  Selezionare **Modifica formula**.
7.  Nel **campo Formula**, immettere **Model.Selector(Model.Data.Summary.Code)**.
8.  Selezionare **Salva**.

    ![Aggiunta di Model.Selector(Model.Data.Summary.Code) alla pagina Progettazione formula](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld.PNG)

9.  Chiudere la pagina **Editor formule**.
10. Selezionare **OK**.

    ![Pagina Progettazione formato con una nuova formula aggiunta](./media/RCS-AppSpecParms-ConfigureFormat-AddLevelByLookupFld2.PNG)

    Si noti che il campo calcolato **LevelByLookup** aggiunto restituisce il livello di tassazione come valore dell'enumerazione di formato **Elenco dei livelli di tassazione** per ciascun record di riepilogo delle transazioni fiscali. Il codice imposta del record viene passato all'origine dati di ricerca **Model.Selector** e il set di regole per l'origine dati viene utilizzato per selezionare il livello di tassazione corretto.

### <a name="add-a-new-format-enumeration-based-data-source&quot;></a>Aggiungere una nuova origine dati basata sull'enumerazione di formato

A questo punto si aggiunge una nuova origine dati che fa riferimento all'enumerazione di formato aggiunta in precedenza. I valori dell'origine dati verranno utilizzati più avanti in un'espressione di formato ER.

1.  Selezionare **Aggiungi radice**.
2.  Selezionare **Enumerazioni di formato\Enumerazione**.
3.  Nel campo **Nome**, immettere **TaxationLevel**.
4.  Nel campo **Enumerazione di formato**, selezionare **Elenco di livelli di tassazione**.
5.  Selezionare **Salva**.

### <a name=&quot;modify-an-existing-field-to-start-to-use-the-lookup&quot;></a>Modificare un campo esistente per iniziare a utilizzare la ricerca

A questo punto si modifica il campo calcolato esistente in modo da utilizzare l'origine dati di ricerca configurata per restituire il valore corretto del livello di tassazione, a seconda del codice imposta.

1.  Selezionare l'elemento **Model.Data.Summary.Level**.
2.  Selezionare **Modifica**.
3.  Selezionare **Modifica formula**.

    Si noti che l'espressione corrente del campo **Model.Data.Summary.Level** include i seguenti codici imposta hardcoded:
    
    CASE (@.Code, &quot;VAT19&quot;, &quot;Regolare&quot;, &quot;InVAT19&quot;, &quot;Regolare&quot;, &quot;VAT7&quot;, &quot;Regolare&quot;, &quot;InVAT7&quot;, &quot;Regolare&quot;, &quot;THIRD&quot;, &quot;Nessuna&quot;, &quot;InVAT0&quot;, &quot;Nessuna&quot;, &quot;Altro")

4.  Nel campo **Formula**, immettere **CASE(@.LevelByLookup, TaxationLevel.'Regular taxation', "Regolare", TaxationLevel.'Reduced taxation', "Ridotta", TaxationLevel.'No taxation', "Nessuna", "Altro")**.

    ![Pagina della progettazione dell'operazione ER](./media/RCS-AppSpecParms-ConfigureFormat-ChangeLookupFld.PNG)
    
    Si noti che l'espressione del campo **Model.Data.Summary.Level** ora restituisce il livello di tassazione in base al codice imposta del record corrente e del set di regole che un utente aziendale configura nell'origine dati di ricerca **Model.Data.Selector**.
    
5.  Selezionare **Salva**.
6.  Chiudere la pagina **Designer formula**.
7.  Selezionare **OK**.
8.  Selezionare **Salva**.
9.  Chiudere la pagina **Progettazione formati**.

## <a name="complete-the-draft-version-of-a-derived-format"></a>Completare la versione in bozza di un formato derivato

1.  Nella scheda dettaglio **Versioni**, seleziona **Cambia stato**.
2.  Selezionare **Completa**.
3.  Selezionare **OK**.

## <a name="export-completed-version-of-modified-format"></a>Esportare la versione completata di un formato modificato

1.  Nell'albero delle configurazioni, selezionare l'elemento **Formato per ottenere ricerche di dati di persona giuridica**.
2.  Nella scheda dettaglio **Versioni**, seleziona il record che lo stato **Completato**.
3.  Selezionare **Scambia**.
4.  Selezionare **Esporta come file XML**.
5.  Selezionare **OK**.
6.  Il Web browser scarica il file **Formato per ottenere ricerche di dati di persona giuridica.xml**. Archiviare questo file in locale.

Ripetere i passaggi di questa sezione per gli elementi padre del formato **Formato per ottenere ricerche di dati di persona giuridica** e archiviare i seguenti file localmente:

-   Formato per ottenere chiamate parametrizzate.xml
-   Mapping per ottenere chiamate parametrizzate.xml
-   Modello per ottenere chiamate parametrizzate.xml

Per informazioni su come utilizzare il formato ER configurato **Formato per ottenere ricerche di dati di persona giuridica** per impostare set di codici imposta dipendenti dalla persona giuridica per filtrare le transazioni fiscali per livelli diversi di tassazione, completare i passaggi descritti nell'argomento [Impostare i parametri di un formato ER per la persona giuridica](er-app-specific-parameters-set-up.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Impostare i parametri di un formato ER per la persona giuridica](er-app-specific-parameters-set-up.md)

[Funzionalità Configurare le origini dati di ricerca per utilizzare i parametri specifici dell'applicazione ER](er-lookup-data-sources.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
