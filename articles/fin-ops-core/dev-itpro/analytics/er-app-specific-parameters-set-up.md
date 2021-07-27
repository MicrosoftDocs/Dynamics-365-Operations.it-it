---
title: Impostare i parametri di un formato ER per la persona giuridica
description: In questo argomento viene descritto come impostare i parametri di un formato per la creazione di report elettronici (ER) per la persona giuridica.
author: NickSelin
ms.date: 10/29/2019
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
ms.openlocfilehash: 9276a633d560bc95c868b9c12438b4f625ed169a
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351892"
---
# <a name="set-up-the-parameters-of-an-er-format-per-legal-entity"></a>Impostare i parametri di un formato ER per la persona giuridica

[!include[banner](../includes/banner.md)]

## <a name="prerequisites"></a>Prerequisiti

Per effettuare queste operazioni, è innanzitutto necessario completare i passaggi descritti nell'argomento [Configurare i formati ER per utilizzare i parametri specificati per la persona giuridica](er-app-specific-parameters-configure-format.md).

Per completare gli esempi in questo argomento, è necessario disporre dell'accesso a Microsoft Dynamics 365 Finance (Finance) per uno dei seguenti ruoli:

- Sviluppatore per la creazione di report elettronici
- Consulente funzionale per la creazione di report elettronici
- Amministratore di sistema

## <a name="import-er-configurations"></a>Importare configurazioni ER

1.  Accedere all'ambiente.
2.  Nel dashboard predefinito, selezionare **Creazione di report elettronici**.
3.  Selezionare **Configurazioni report**.
4.  Importare, nell'istanza di Finance corrente, le configurazioni esportate da Regulatory Configuration Services (RCS) per completare i passaggi indicati nell'argomento [Configurare i formati ER per utilizzare i parametri specificati per la persona giuridica](er-app-specific-parameters-configure-format.md). Seguire questi passaggi per ogni configurazione di creazione di report elettronici (ER), nel seguente ordine: modello di dati, mapping di modello e formati.

    1. Selezionare **Scambia \> Carica da file XML**.
    2. Selezionare **Sfoglia** per selezionare il file per la configurazione ER necessaria in formato XML.
    3. Selezionare **OK**.
    
    Nella seguente figura sono riportate le configurazioni che si dovranno avere al termine del passaggio.

    ![Pagina configurazioni ER.](./media/GER-AppSpecParms-ImportedConfigurations.PNG)

## <a name="set-up-parameters-for-the-demf-company"></a>Impostare i parametri per la società DEMF

È possibile utilizzare il framework ER per impostare i parametri specifici dell'applicazione per un formato ER.

1.  Selezionare la persona giuridica **DEMF**.
2.  Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.
3.  Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm.PNG)
    
    Nella pagina **Parametri specifici dell'applicazione**, è possibile configurare le regole per l'origine dati **Selettore** del formato **Formato per ottenere ricerche di dati di persona giuridica**.
    
    Se il formato di ER di base contiene più origini dati di tipo **Ricerca**, è necessario selezionare l'origine dati desiderata nella Scheda dettaglio **Ricerche** prima di iniziare a configurare il set di regole per l'origine dati.
    
    Per ciascuna origine dati, è possibile configurare regole separate per ogni versione del formato di ER selezionato.
    
    L'intero set di regole per tutte le origini dati di ricerca disponibili nella versione selezionata del formato di ER di base costituisce i parametri specifici dell'applicazione per il formato di ER.

4.  Selezionare la versione **1.1.1** del formato di ER.
5.  Nella Scheda dettaglio **Condizioni** selezionare **Aggiungi**.
6.  Nel campo **Codice** del nuovo record selezionare la freccia a discesa per aprire la ricerca.

    La ricerca presenta l'elenco dei codici imposta per la selezione. Questo elenco viene restituito dall'origine dati **Model.Data.Tax** che è stata configurata nel formato di ER di base. Poiché l'origine dati contiene il campo **Nome**, immettere il nome di ogni codice imposta visualizzato nella ricerca.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker.PNG)
    
7.  Selezionare il codice imposta **VAT19**.
8.  Nel campo **Risultato della ricerca** del nuovo record selezionare la freccia a discesa per aprire la ricerca. La ricerca presenta l'elenco dei valori dell'enumerazione di formato TaxationLevel per la selezione.

    Si noti che, se il tedesco è selezionato come la lingua preferita dell'utente attualmente collegato, le etichette dei valori della ricerca saranno in tedesco, a condizione che siano state tradotte nel formato di ER di base. Inoltre, se l'etichetta di un'origine dati di ricerca è stata tradotta, l'etichetta verrà visualizzata nella lingua preferita dall'utente nella scheda **Ricerche**.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm-LookupFldPicker.PNG)

9.  Selezionare il valore **Tassazione regolare**.

    Aggiungendo questo record, si definisce la seguente regola: ogni volta che viene richiesta l'origine dati di ricerca **Selector** e il codice imposta **VAT19** viene passato come argomento, **Tassazione regolare** sarà restituito come livello fiscale richiesto.

10. Selezionare **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice** selezionare il codice imposta **InVAT19**.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione regolare**.
    
11. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice** selezionare il codice imposta **VAT7**.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione ridotta**.
    
12. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice** selezionare il codice imposta **InVAT7**.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Tassazione ridotta**.
    
13. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice** selezionare il codice imposta **THIRD**.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Nessuna tassazione**.
    
14. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice** selezionare il codice imposta **InVAT0**.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Nessuna tassazione**.
    
15. Selezionare di nuovo **Aggiungi** e quindi effettuare le seguenti operazioni:

    1. Nel campo **Codice**, selezionare l'opzione **\*Non vuoto\***.
    2. Nel campo **Risultato della ricerca**, selezionare il valore **Altro**.
    
    Aggiungendo questo record, si definisce la seguente regola: ogni volta che il codice imposta che viene passato come argomento non soddisfa nessuna delle regole precedenti, l'origine dati di ricerca restituirà **Altro** come livello di tassazione richiesto.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm-RulesSet.PNG)
    
16. Nel campo **Stato** selezionare **Completato**.

    Quando si esegue una versione di formato di ER con stato **Completato** o **Condiviso**, il set di regole deve essere nello stato **Completato**. In caso contrario, l'esecuzione del formato di ER di base viene interrotta quando il formato tenta di caricare i dati del set di regole mentre l'origine dati di ricerca **Selettore** è in esecuzione.
    
    Quando si esegue una versione di formato di ER con stato **Bozza**, il formato di ER di base può accedere a questo set di regole, indipendentemente dallo stato.
    
17. Selezionare **Salva**.
18. Chiudere la pagina **Parametri specifici dell'applicazione**.

## <a name="run-the-er-format-in-the-demf-company"></a>Eseguire il formato di ER nella società DEMF

1.  Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.
2.  Nel Riquadro azioni selezionare **Esegui**.
3.  Nella finestra di dialogo visualizzata, selezionare **OK**.
4.  Scaricare il rendiconto generato e memorizzarlo in locale.

    Nel rendiconto generato, notare che il riepilogo del codice imposta **InVAT7** è nel livello **Ridotta** e i riepiloghi dei codici imposta **InVA19** e **VAT19** sono stati inseriti nel livello **Regolare**. Questo comportamento dipende dalla configurazione nel set di regole dipendenti dalla persona giuridica.
    
5.  Passare a **Imposta \> Imposte indirette \> IVA \> Codici IVA**.
6.  Selezionare il codice imposta **InVAT7**.
7.  Nel riquadro azioni, nella scheda **Codice IVA**, nel gruppo **Richieste di informazioni**, selezionare **IVA registrata** per visualizzare le informazioni sul valore di imposta e sull'aliquota di imposta applicata per codice IVA.

    ![Pagina IVA registrata.](./media/GER-AppSpecParms-Statement.PNG)

8.  Chiudere la pagina IVA registrata.

## <a name="set-up-parameters-for-the-usmf-company"></a>Impostare i parametri per la società USMF

1.  Selezionare la persona giuridica **USMF**.
2.  Andare a **Amministrazione organizzazione\> Creazione di report elettronici \> Configurazioni**.
3.  Nella struttura di configurazioni, espandere la voce **Modello per ottenere chiamate parametrizzate**, espandere **Formato per ottenere chiamate parametrizzate** e selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.
4.  Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.
5.  Selezionare la versione **1.1.1** del formato di ER selezionato.
6.  Nella Scheda dettaglio **Condizioni** selezionare **Aggiungi**.
7.  Nel campo **Codice** del nuovo record selezionare la freccia a discesa per aprire la ricerca.

    La ricerca ora presenta l'elenco dei codici imposta per l'imposta della società **USMF** per la selezione.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm-CodeFldPicker2.PNG)
    
8.  Selezionare il codice imposta **ESENTE**.
9.  Nel campo **Risultato della ricerca** del nuovo record, selezionare il valore **Nessuna tassazione**.
10. Selezionare **Aggiungi** nuovamente.
11. Nel campo **Codice** del nuovo record, selezionare l'opzione **\*Non vuoto\***.
12. Nel campo **Risultato della ricerca** del nuovo record, selezionare il valore **Tassazione regolare**.
13. Nel campo **Stato** selezionare **Completato**.
14. Selezionare **Salva**.

    ![Pagina Parametri specifici dell'applicazione ER.](./media/GER-AppSpecParms-LookupForm-RulesSet2.PNG)
    
15. Chiudere la pagina **Parametri specifici dell'applicazione**.

## <a name="run-the-er-format-in-the-usmf-company"></a>Eseguire il formato di ER nella società USMF

1.  Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.
2.  Nel Riquadro azioni selezionare **Esegui**.
3.  Nella finestra di dialogo visualizzata, selezionare **OK**.
4.  Scaricare il rendiconto generato e memorizzarlo in locale.

    Nel rendiconto generato, notare che è stato riutilizzato lo stesso formato di ER per una persona giuridica diversa, senza effettuare modifiche al formato di ER.

## <a name="reuse-legal-entitydependent-parameters"></a>Riutilizzo dei parametri dipendenti dalla persona giuridica

### <a name="export-parameters"></a>Esportare parametri

1.  Andare a **Amministrazione organizzazione \> Aree di lavoro \> Creazione di report elettronici**.
2.  Selezionare **Configurazioni report**.
3.  Nell'albero delle configurazioni, selezionare il formato **Formato per ottenere ricerche di dati di persona giuridica**.
4.  Nel riquadro azioni, scheda **Configurazioni**, gruppo **Parametri specifici dell'applicazione**, selezionare **Imposta**.
5.  Selezionare la versione **1.1.1** del formato di ER.
6.  Nel riquadro azioni, selezionare **Esporta**.
7.  Scaricare il file generato e memorizzarlo in locale.

    Il set configurato dei parametri specifici dell'applicazione è stato esportato come file XML.

### <a name="import-parameters"></a>Importare parametri

1.  Selezionare la versione **1.1.2** del formato di ER.
2.  Nel riquadro azioni, selezionare **Importa**.
3.  Selezionare **Sì** per confermare che si desidera sostituire i parametri specifici dell'applicazione esistenti per questa versione di formato.
4.  Selezionare **Sfoglia** per individuare il file contenente i parametri specifici dell'applicazione esportati per la versione **1.1.1**.
5.  Selezionare **OK**.

    Versione **1.1.2** del formato di ER ora con gli stessi parametri specifici dell'applicazione originariamente configurati per la versione **1.1.1**.
    
    Si noti che i parametri specifici dell'applicazione di un formato di ER sono dipendenti dalla persona giuridica. Per riutilizzare i parametri specifici dell'applicazione configurati per una persona giuridica in una persona giuridica diversa, è necessario esportarli mentre si è collegati alla prima persona giuridica e quindi importarli dopo aver effettuato l'accesso all'altra persona giuridica.

    È inoltre possibile utilizzare questo approccio per trasferire i parametri specifici di un'applicazione relativi al formato ER originariamente configurati in un'istanza di Finance in un'altra istanza di Finance.

    Tenere presente che se si configurano i parametri specifici dell'applicazione per una versione di un formato ER e si importa una versione superiore dello stesso formato nell'istanza di Finance corrente, i parametri specifici dell'applicazione esistenti non verranno applicati per la versione importata.
    
    Inoltre, tenere presente che, quando si seleziona un file per l'importazione, la struttura dei parametri specifici dell'applicazione in quel file viene confrontata con la struttura dell'origine dati corrispondente del tipo **Ricerca** nel formato ER selezionato per l'importazione. L'importazione viene eseguita quando la struttura di ciascun parametro specifico dell'applicazione corrisponde alla struttura dell'origine dati corrispondente nel formato ER selezionato per l'importazione. Se le strutture non corrispondono, viene visualizzato un messaggio di avviso che informa che non è possibile eseguire l'importazione. Se si forza l'esecuzione dell'importazione, i parametri specifici dell'applicazione esistenti per il formato ER selezionato verranno cancellati e sarà necessario configurarli dall'inizio.

## <a name="relationship-between-application-specific-parameters-and-an-er-format"></a>Relazione tra parametri specifici dell'applicazione e un formato ER

La relazione tra un formato ER e i parametri specifici dell'applicazione è stabilita dal codice identificativo univoco indipendente dall'istanza del formato ER. Pertanto, quando si rimuove un formato ER da Finance, i parametri specifici dell'applicazione configurati per il formato ER vengono mantenuti nell'istanza corrente di Finance. È possibile accedervi ogni volta che il formato ER di base viene reimportato in questa istanza di Finance.

## <a name="access-application-specific-parameters-by-using-the-er-framework"></a>Accedere ai parametri specifici dell'applicazione utilizzando il framework ER

Nell'esempio precedente, è stato effettuato l'accesso ai parametri specifici dell'applicazione di un formato ER utilizzando il framework ER. Questo approccio non consente di limitare l'accesso ai parametri specifici dell'applicazione di un formato ER specifico. Se è necessario applicare tali restrizioni, attenersi alla seguente procedura. 

1.  Riutilizzare la voce di menu esistente **ERSolutionAppSpecificParametersDesigner** oppure implementare la propria voce di menu **ERSolutionAppSpecificParametersDesigner**.

    ![Pagina Visual Studio.](./media/GER-AppSpecParms-LookupForm-Access1.PNG)
    
2.  Eseguire uno dei passaggi riportati di seguito.

    1.  Creare un nuovo pulsante voce di menu e collegarlo al record corrispondente dalla tabella **ERSolutionTable** impostando la proprietà **Origine dati** su **ERSolutionTable**.
    
        ![Pagina Visual Studio.](./media/GER-AppSpecParms-LookupForm-Access2.PNG)
        
    2.  Creare un pulsante semplice ed eseguire l'override del metodo **selezionato** come illustrato nell'esempio riportato di seguito.
    
        Utilizzando questo metodo, è possibile specificare un ID univoco della soluzione (definito tramite il valore **GUID** ) per consentire l'accesso ai parametri specifici dell'applicazione di un solo formato specifico di ER e delle copie discendenti che ne derivano.
        
        ```xpp
        public void clicked()
            {
                super();

                ERSolutionTable solutionTableRecord = ERSolutionTable::findByGUID(str2Guid('ADACCB2F-EFD1-4C90-877D-7E1E5D1AEE92'));

                Args args = new Args();
                args.record(solutionTableRecord);
                args.caller(this);

                new MenuFunction(menuItemDisplayStr(ERSolutionAppSpecificParametersDesigner), MenuItemType::Display)
                    .run(args);
            }
        ```

## <a name="additional-resources"></a>Risorse aggiuntive

[Designer formula nella creazione di report elettronici](general-electronic-reporting-formula-designer.md)

[Configurare i formati di ER per utilizzare i parametri specifici per la persona giuridica](er-app-specific-parameters-configure-format.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]