---
title: Gestire diversi mapping derivati per una singola radice del modello
description: Questo argomento spiega come gestire diversi mapping derivati configurati per una singola radice del modello.
author: NickSelin
manager: AnnBe
ms.date: 01/04/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERModelMappingTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: bb4fcda42361b0f14e37027d21739dfc42b44cb1
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5565493"
---
# <a name="manage-several-derived-mappings-for-a-single-model-root"></a>Gestire diversi mapping derivati per una singola radice del modello

[!include [banner](../includes/banner.md)]

Un [modello](general-electronic-reporting.md#data-model-and-model-mapping-components) di dati [Creazione di report elettronici (ER)](general-electronic-reporting.md) viene utilizzato in ogni componente [formato](general-electronic-reporting.md#FormatComponentOutbound) di report elettronico configurato come origine dati per generare documenti in uscita. Per descrivere un singolo dominio aziendale, configura un componente del modello di dati che abbia molte definizioni radice. 

Ogni definizione radice consente di rappresentare i dati di quel dominio nel modo più adatto a scopi di creazione di report specifici. Per ogni definizione di radice, puoi configurare un componente di [mapping dei modelli](general-electronic-reporting.md#data-model-and-model-mapping-components) di creazione di report elettronici come Microsoft Dynamics 365 Finance, implementazione specifica del modello di dati. In questo modo, descrivi come verrà compilato il tuo modello di dati in fase di esecuzione.

I componenti di mapping del modello di creazione di report elettronici (ER) possono risiedere nelle [configurazioni](general-electronic-reporting.md#Configuration)del modello di dati ER e nelle configurazioni del mapping del modello ER. Una singola configurazione ER può contenere molti componenti di mapping, ognuno dei quali è configurato per una singola definizione di radice. In alternativa, una singola configurazione ER può contenere un solo componente di mapping configurato per una singola definizione di radice.

Molti provider di configurazione potrebbero offrire configurazioni di mapping del modello ER per lo stesso modello di dati ER. Tali configurazioni di mapping del modello potrebbero contenere componenti di mapping per diverse definizioni di root. È consigliabile utilizzare un mapping del modello per una definizione radice offerta da un [provider](general-electronic-reporting.md#Provider) e utilizzare un mapping del modello per un'altra definizione di radice offerta da un altro provider.

Le procedure in questo argomento spiegano come gestire più configurazioni di mapping del modello ER di un modello di dati ER quando contengono diversi componenti di mapping del modello configurati per la stessa definizione radice. 

Per completare la procedura di questo argomento, devi avere il ruolo di amministratore di sistema o di sviluppatore per la creazione di report elettronici assegnato.

Tutte le seguenti procedure possono essere eseguite nell'azienda USMF. Non è richiesta alcuna codifica.

## <a name="configure-the-er-framework"></a>Configurare il framework ER

Come utente che dispone del ruolo di sviluppatore per la creazione di report elettronici, [configura il set minimo](er-quick-start2-customize-report.md#ConfigureFramework) di parametri ER prima di poter iniziare a utilizzare il framework ER per generare documenti aziendali.

## <a name="import-the-standard-er-format-configurations"></a>Importare le configurazioni del formato ER standard

Per aggiungere le configurazioni ER standard all'istanza corrente di Finance, è necessario importarle dall'archivio ER che era configurato per quell'istanza. Segui i passaggi in [Scaricare configurazioni ER dall'archivio globale del servizio di configurazione](er-download-configurations-global-repo.md) per importare le seguenti configurazioni di formato ER:

- **Fattura a testo libero (Excel)** versione 220.106
- **Fattura di progetto (Excel)** versione 226.27

## <a name="review-the-imported-er-configurations"></a>Rivedere le configurazioni ER importate

1. Andare a **Amministrazione organizzazione** \> **Aree di lavoro** \> **Creazione di report elettronici**.
2. Nella pagina **Configurazioni localizzazione**, nella sezione **Configurazioni**, selezionare il riquadro **Configurazioni report**.
3. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, espandi **Modello di fattura**.

    ![Revisione delle configurazioni importate nella pagina Configurazioni](./media/er-multiple-model-mappings-image1.png)

4. Rivedi il formato **Fattura a testo libero (Excel)**:

    1. Nell'albero di configurazione nel riquadro sinistro, seleziona **Fattura a testo libero (Excel)**.
    2. Nel riquadro azioni selezionare **Progettazione**.
    3. Nella pagina **Progettazione formati**, nella scheda **Mapping**, nell'elenco delle origini dati, seleziona **Modello**.
    4. Seleziona **Visualizza**.
    
       Il formato ER corrente è configurato per utilizzare la definizione di radice **InvoiceCustomer** di **Modello di fattura**. Quando viene eseguito questo formato, e viene chiamata l'origine dati **Modello**, il mapping del modello configurato per la definizione di radice **InvoiceCustomer** viene utilizzato per accedere ai dati dell'applicazione e compilare il modello di dati.

        ![Revisione dell'origine dati del modello nella pagina di progettazione del formato](./media/er-multiple-model-mappings-image2.png)

    6. Chiudere la pagina **Progettazione formati**.

5. Rivedi il contenuto della configurazione **Mapping di modello di fattura**:

    1. Nell'albero di configurazione nel riquadro sinistro, seleziona **Mapping di modello di fattura**.
    2. Nel riquadro azioni selezionare **Progettazione**.
    3. Nella pagina **Modello per mapping origine dati** si noti che l'attuale configurazione del mapping del modello ER contiene diversi componenti del mapping del modello:

        + Il mapping del modello **Fattura cliente** è configurato per la definizione radice **InvoiceCustomer** di **Modello di fattura**. Pertanto, quando viene eseguito il formato ER **Fattura a testo libero (Excel)**, il mapping del modello **Fattura cliente** di questa configurazione ER può essere scelto per accedere ai dati dell'applicazione e compilare il modello di dati.
        + Il mapping del modello **Fattura progetto** è configurato per la definizione radice **InvoiceProject** di **Modello di fattura**. Pertanto, quando viene eseguito il formato ER **Fattura progetto(Excel)**, il mapping del modello **Fattura progetto** di questa configurazione ER può essere scelto per accedere ai dati dell'applicazione e compilare il modello di dati.

        ![Mapping del modello di fattura nella pagina Modello per mapping origine dati](./media/er-multiple-model-mappings-image3.png)

    4. Chiudere la pagina **Modello per mapping origine dati**.
    5. Nella Scheda dettaglio **Versioni**, seleziona **Elimina** per eliminare tutte le versioni di questa configurazione ER che sono successive alla versione 240.175.

6. Rivedi il contenuto della configurazione **Mapping del modello di fattura di progetto (RDP)**:

    1. Nell'albero di configurazione nel riquadro sinistro, seleziona **Mapping del modello di fattura di progetto (RDP)**.
    2. Nel riquadro azioni selezionare **Progettazione**.
    3. Nella pagina **Modello per mapping origine dati** si noti che l'attuale configurazione del mapping del modello ER contiene il mapping del modello **InvoiceProject** e che questo mapping del modello è configurato per la definizione radice **InvoiceProject** di **Modello di fattura**. Quando viene eseguito il formato ER **Fattura progetto(Excel)**, seleziona il mapping del modello **InvoiceProject** di questa configurazione ER per accedere ai dati dell'applicazione e compilare il modello di dati.

        ![Mapping del modello di fattura di progetto nella pagina Modello per mapping origine dati](./media/er-multiple-model-mappings-image4.png)

    4. Chiudere la pagina **Modello per mapping origine dati**.
    5. Nella Scheda dettaglio **Versioni**, seleziona **Elimina** per eliminare tutte le versioni di questa configurazione ER che sono successive alla versione 226.35.

## <a name="customize-the-imported-er-configurations"></a>Personalizzare le configurazioni ER importate

Questa sezione spiega come [personalizzare](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration) i mapping del modello forniti da Microsoft. Ad esempio, potrebbe essere necessaria la personalizzazione per implementare la logica personalizzata o aggiungere binding mancanti.

### <a name="customize-the-invoice-model-mapping-configuration"></a>Personalizzare la configurazione del mapping del modello di fattura

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Mapping di modello di fattura**.
2. Nel riquadro azioni, selezionare **Crea configurazione**.
3. Nella finestra di dialogo a discesa **Crea configurazione**, nel gruppo di campi **Nuovo**, selezionare **Deriva da nome: Mapping del modello di fattura, Microsoft**.
4. Nel campo **Nome** digitare **Mapping di modello di fattura Litware**.
5. Selezionare **Crea configurazione**.
6. [Contrassegna](er-quick-start2-customize-report.md#MarkFormatRunnable) la versione [bozza](general-electronic-reporting.md#component-versioning) del mapping derivato disponibile per l'uso in fase di esecuzione:

    1. Nel riquadro azioni, scheda **Configurazioni**, gruppo **Impostazioni avanzate**, selezionare **Parametri utente**.
    2. Nella finestra di dialogo **Parametri utente**, imposta l'opzione **Esegui impostazioni** su **Sì**, quindi seleziona **OK**.
    3. Seleziona **Modifica** per rendere la pagina modificabile come richiesto.
    4. Per la configurazione **Mapping di modello di fattura Litware** attualmente selezionata nell'albero di configurazione, imposta l'opzione **Esegui bozza** su **Sì**.

7. Nel riquadro azioni seleziona **Progettazione** per rivedere i mapping del modello di questa configurazione.

    ![Revisione dei mapping del modello di fattura di progetto nella pagina Modello per mapping origine dati](./media/er-multiple-model-mappings-image5.png)

    > [!TIP]
    > È ora possibile aprire uno qualsiasi dei componenti di mapping del modello ER di questa configurazione ER nella finestra di progettazione per configurare la logica personalizzata. Per ulteriori informazioni, vedere [Personalizzare la configurazione del mapping di modello](er-quick-start3-customize-report.md#customize-the-model-mapping-configuration).

8. Chiudere la pagina **Modello per mapping origine dati**.

Adesso hai le configurazioni **Mapping del modello di fattura** e **Mapping del modello fattura Litware**, ognuna delle quali ha un mapping del modello configurato per la definizione radice **InvoiceCustomer**. Assegna esplicitamente uno dei mapping del modello come mapping del modello predefinito che viene utilizzato da uno qualsiasi dei formati ER, come il formato **Fattura a testo libero (Excel)** che contiene un'origine dati del modello con definizione radice **InvoiceCustomer**. Altrimenti, quando esegui, modifichi o convalidi uno dei formati ER, viene generata la seguente eccezione per avvisarti che nessun mapping del modello predefinito è stato assegnato esplicitamente:
 
> Esiste più di un mapping del modello per il modello di dati "\<model name\> (\<root descriptor\>)" nelle configurazioni \<configuration names separated by commas\>. Imposta una delle configurazioni come predefinita.

![Apertura del formato per la modifica nella pagina Configurazioni](./media/er-multiple-model-mappings-image6.gif)

### <a name="customize-the-project-invoice-model-mapping-rdp-configuration"></a>Personalizzare la configurazione del mapping del modello di fattura di progetto (RDP)

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Mapping di modello di fattura di progetto**.
2. Nel riquadro azioni, selezionare **Crea configurazione**.
3. Nella finestra di dialogo a discesa **Crea configurazione**, nel gruppo di campi **Nuovo**, selezionare **Deriva da nome: Mapping del modello di fattura di progetto (RDP), Microsoft**.
4. Nel campo **Nome** digitare **Mapping di modello di fattura di progetto Litware**.
5. Selezionare **Crea configurazione**.
6. Per la configurazione **Mapping del modello fattura di progetto** attualmente selezionata nell'albero di configurazione, imposta l'opzione **Esegui bozza** su **Sì**.
7. Nel riquadro azioni seleziona **Progettazione** per rivedere i mapping del modello di questa configurazione.

    ![Rivedere i mapping del modello di fattura di progetto personalizzati nella pagina Modello per mapping origine dati](./media/er-multiple-model-mappings-image7.png)

8. Chiudere la pagina **Modello per mapping origine dati**.

Adesso hai a disposizione le configurazioni **Mapping del modello di fattura**, **Mapping del modello di fattura di progetto (RDP)** e **Mapping del modello fattura di progetto Litware**. Ciascuna di queste configurazioni ha un mapping del modello configurato per la definizione radice **InvoiceProject**. Assegna in modo esplicito uno dei mapping del modello come mapping del modello predefinito utilizzato da qualsiasi formato ER. Ad esempio, usa il formato **Fattura progetto (Excel)** che contiene un'origine dati del modello con definizione radice **InvoiceProject**. Altrimenti, quando esegui o modifichi uno dei formati ER, viene generata un'eccezione per avvisarti che nessun mapping del modello predefinito è stato assegnato esplicitamente.

## <a name="select-the-derived-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Seleziona la configurazione del mapping del modello di fattura Litware derivata come configurazione che contiene mapping di modello predefinite

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Mapping di modello di fattura Litware**.
2. Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.

    ![Impostazione del mapping del modello come mapping del modello predefinita nella pagina Configurazioni](./media/er-multiple-model-mappings-image8.png)

    A causa di questa impostazione, il mapping del modello **Copia fattura cliente** viene utilizzato quando si esegue **Fattura a testo libero (Excel)** o quando lo modifichi o lo convalidi. Il mapping del modello **Fattura cliente** dalla configurazione **Mapping del modello di fattura** viene ignorato.

    È ora possibile aprire il formato **Fattura a testo libero (Excel)** per la revisione nella finestra d progettazione del formato.

## <a name="select-the-derived-project-invoice-model-mapping-litware-configuration-as-the-configuration-that-contains-default-model-mappings"></a>Seleziona la configurazione del mapping del modello di fattura di progetto Litware derivata come configurazione che contiene mapping di modello predefinite

1. Nella pagina **Configurazioni**, nella struttura delle configurazioni del riquadro sinistro, selezionare **Mapping di modello di fattura di progetto Litware**.
2. Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.

    In questo caso, a differenza del caso descritto per la configurazione **Mapping del modello di fattura Litware** nella sezione precedente, non è possibile iniziare a utilizzare il mapping del modello **Copia InvoiceProject** dalla configurazione **Mapping del modello di fattura progetto Litware**. Due configurazioni che contengono una mapping del modello per la definizione radice **InvoiceProject** sono attualmente contrassegnate come configurazione predefinita. Pertanto, hanno uguale priorità per l'uso. Per risolvere questo problema, completare i passaggi rimanenti di questa procedura.

3. Nell'albero di configurazione nel riquadro sinistro, seleziona **Mapping di modello di fattura Litware**.
4. Nel riquadro azioni selezionare **Progettazione**.
5. Nella pagina **Modello per mapping origine dati**, seleziona **Modifica** per rendere la pagina modificabile, come richiesto.
6. Seleziona il mapping del modello **Copia fattura progetto**, quindi seleziona la casella di controllo **Eliminato** per esso.

    ![Impostazione del mapping del modello come virtualmente eliminato nella pagina Modello per mapping origine dati](./media/er-multiple-model-mappings-image9.png)

    A causa di questa impostazione, la configurazione **Mapping di modello di fattura Litware** viene considerata come se non avesse alcun mapping del modello per la definizione radice **InvoiceProject**. Il mapping del modello **Copia InvoiceProject** rilasciato per impostazione predefinita. La configurazione **Mapping del modello di fattura di progetto Litware** che contiene il mapping del modello, è contrassegnata come configurazione predefinita. Poiché è contrassegnata come predefinito, ha una priorità maggiore rispetto al modello di mapping **InvoiceProject** dalla configurazione **Mapping del modello di fattura di progetto (RDP)**.

## <a name="other-considerations"></a>Altre considerazioni

Il mapping del modello **Copia InvoiceProject Copy** della configurazione **Mapping del modello di fattura di Litware** è progettato per utilizzare l'origine dati **ReportDataProvider**. L'origine dati fa parte del tipo di *Oggetto* che fa riferimento alla classe di applicazione **PsaProjInvoiceDP**. Questa classe viene implementata come provider di dati per il report SQL Server Reporting Services (SSRS) della fattura del progetto del framework di gestione della stampa. Seleziona questa origine dati come [punto di integrazione](er-apis-app10-0-11.md#api-to-run-a-format-mapping-for-the-generation-of-outbound-documents) ER. L'attuale implementazione ER per i report di gestione della stampa tiene conto di questa impostazione. Per maggiori dettagli, rivedi il codice sorgente della classe di applicazione **ERPrintMgmtDataProviderReport**. In fase di esecuzione, l'assegnazione dell'origine dati **ReportDataProvider** come punto di integrazione del mapping del modello obbliga Finance a trattare questo componente di mapping con una priorità maggiore rispetto al componente di mapping **InvoiceProject** dalla configurazione **Mapping del modello di fattura del progetto (RDP)**.

## <a name="see-also"></a>Vedere anche

- [Gestire il mapping dei modelli ER in configurazioni ER separate](./tasks/er-manage-model-mapping-configurations-july-2017.md)
- [Configurare i mapping del modello di report elettronici dipendenti dal contesto del paese](er-country-dependent-model-mapping.md)
- [Modifiche all'API del framework di report elettronici](er-apis-app10-0-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]