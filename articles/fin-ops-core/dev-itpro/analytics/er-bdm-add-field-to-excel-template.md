---
title: Aggiungere nuovi campi a un modello di documento aziendale in Microsoft Excel
description: In questo argomento vengono fornite informazioni sull'aggiunta di nuovi campi a un modello di documento aziendale in Microsoft Excel utilizzando la funzionalità di gestione dei documenti aziendali.
author: NickSelin
ms.date: 11/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-10-01
ms.dyn365.ops.version: 10.0.7
ms.openlocfilehash: af9f3dd81b0681579c14e0afb8281706e8aa534d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6351796"
---
# <a name="add-new-fields-to-a-business-document-template-in-microsoft-excel"></a>Aggiungere nuovi campi a un modello di documento aziendale in Microsoft Excel

[!include[banner](../includes/banner.md)]

È possibile aggiungere nuovi campi a un modello utilizzato per generare i documenti aziendali nel formato Microsoft Excel. Questi campi possono essere aggiunti come segnaposto che vengono utilizzati per completare i documenti generati con le informazioni richieste dall'applicazione. Per ogni campo aggiunto, è possibile anche specificare un'associazione alle origini dati, per specificare quali dati dell'applicazione verranno inseriti nel campo quando il modello viene utilizzato per generare documenti aziendali.

Per ulteriori informazioni su questa funzionalità, completare l'esempio in questo argomento. Questo esempio mostra come aggiornare un modello per compilare i campi nei moduli di fattura a testo libero generati.

## <a name="configure-business-document-management-to-edit-templates"></a>Configurare Gestione documenti aziendali per modificare i modelli

Poiché la gestione dei documenti aziendali (BDM) si basa sul framework della [panoramica del reporting elettronico (ER)](general-electronic-reporting.md), è necessario configurare i parametri ER e BDM richiesti prima di poter iniziare a lavorare con BDM.

1.  Accedere all'istanza di Microsoft Dynamics 365 Finance come amministratore di sistema.
2.  Completare i seguenti passaggi dell'esempio nell'argomento [Panoramica di gestione dei documenti aziendali](er-business-document-management.md) :

    1.  Configurare i parametri ER.
    2.  Attivare il BDM.

È ora possibile iniziare a utilizzare BDM per modificare i modelli di documenti aziendali.

## <a name="import-er-solutions-that-contain-a-template"></a>Importare le soluzioni ER che contengono un modello

L'esempio in questa procedura utilizza la soluzione ER pubblicata ufficialmente. È necessario importare le configurazioni ER di questa soluzione nell'istanza corrente di Finance.

La configurazione del formato ER con **fattura a testo libero (Excel)** di questa soluzione contiene il modello di documento aziendale in formato Excel che può essere modificato utilizzando il BDM. Importare l'ultima versione della configurazione del formato ER da Microsoft Dynamics Lifecycle Service (LCS). Il corrispondente modello di dati ER e le configurazioni di mapping di modello ER verranno importati automaticamente.

Per ulteriori informazioni su come importare le configurazioni ER, vedere [Gestire il ciclo di vita della configurazione ER](general-electronic-reporting-manage-configuration-lifecycle.md).

![Pagina Raccolta di risorse condivise LCS.](./media/BDM-AddFldExcel-LCS.png)

### <a name="edit-the-er-solution-template"></a>Modificare il modello di soluzione ER

1.  Accedere come utente con accesso all'area di lavoro di **Gestione documenti aziendali**.
2.  Aprire l'area di lavoro di **Gestione documenti aziendali**.

    ![Area di lavoro di Gestione documenti aziendali.](./media/BDM-AddFldExcel-Workspace.png)

3.  Nella griglia, selezionare il modello **Fattura a testo libero (Excel)**.
4.  Nel riquadro a destra, selezionare **Nuovo modello** per creare un nuovo modello basato sul modello selezionato.
5.  Nel campo **Titolo** immettere **Fattura a testo libero (Excel) Contoso** come titolo del nuovo modello.
6.  Selezionare **OK** per confermare l'avvio del processo di modifica.

Viene visualizzata la pagina dell'editor di modelli BDM. È possibile utilizzare Microsoft 365 per modificare il modello selezionato online nel controllo incorporato.

![Pagina dell'editor di modelli BDM.](./media/BDM-AddFldExcel-EditableTemplate.png)

### <a name="add-the-label-for-a-new-field-to-the-template"></a>Aggiungere l'etichetta per un nuovo campo al modello

1.  Nella pagina dell'editor di modelli BDM, sulla barra multifunzione di Excel, nella scheda **Visualizza**, selezionare le caselle di controllo **Intestazioni e Linee della griglia** per il modello di Excel modificabile.

    ![Caselle di controllo Intestazioni e Linee della griglia selezionate.](./media/BDM-AddFldExcel-EditableTemplate2.png)

2.  Selezionare le celle **E8:F8**.
3.  Sulla barra multifunzione di Excel, nella scheda **Home**, selezionare **Unisci e centra** per unire le celle selezionata in una nuova cella **E8:F8** unita.
4.  Nella cella unita **E8:F8**, immettere **URL**.
5.  Selezionare la cella unita **E7:F7**, selezionare **Copia formato** e quindi selezionare la cella unita **E8: 8** per formattarla come la cella unita **E7:F7**.

    ![Etichetta del nuovo campo aggiunta al modello.](./media/BDM-AddFldExcel-EditableTemplate3.png)

### <a name="format-the-template-to-reserve-space-for-a-new-field"></a>Formattare il modello in modo da riservare spazio per un nuovo campo

1.  Nella pagina dell'editor dei modelli BDM, selezionare la cella unita **G8:H8**.
2.  Sulla barra multifunzione di Excel, nella scheda **Home**, selezionare **Unisci e centra** per unire le celle selezionata in una nuova cella **G8:H8** unita.
3.  Selezionare la cella unita **G7:H7**, selezionare **Copia formato** e quindi selezionare la cella unita **G8:H8** per formattarla come la cella unita **G7:H7**.

    ![Spazio riservato per il nuovo campo.](./media/BDM-AddFldExcel-EditableTemplate4.png)

4.  Nel campo **Nome** selezionare **CompanyInfo**.

    L'intervallo **CompanyInfo** del modello corrente di Excel contiene tutti i campi utilizzati per completare l'intestazione di un report generato con i dettagli della società corrente come parte venditore.

    ![Intervallo CompanyInfo selezionato.](./media/BDM-AddFldExcel-SelectCompanyInfoRange.png)

### <a name="add-a-new-field-to-the-template"></a>Aggiungere un nuovo campo al modello

1.  Nella pagina **Editor di modelli BDM**, nel riquadro azioni, selezionare **Mostra formato**.
2.  Nel riquadro **Struttura del modello**, selezionare **Aggiungi**.

    > [!NOTE]
    > È necessario modificare la sezione del modello che si desidera utilizzare come nuovo campo. Questa modifica è già stata applicata per formattare la cella unita **G8:H8**.

    ![Aggiunta di un nuovo campo al modello.](./media/BDM-AddFldExcel-AddCell.png)

3.  Selezionare **Excel\Cella** per aggiungere un nuovo campo come cella nel modello.

    È possibile selezionare **Excel\Intervallo** per aggiungere un nuovo intervallo al modello. L'intervallo immesso può contenere più celle. È possibile aggiungere le celle anche successivamente.
    
    Si noti che il componente del modello **CompanyInfo** è selezionato automaticamente nel riquadro **Struttura del modello** perché è il componente principale più adatto nella struttura del modello corrente per il campo da aggiungere.
    
4.  Nel campo **Intervallo Excel**, immettere **CompanyURL_Value**.
5.  Selezionare **OK**.

    ![Il campo CompanyURL_Value aggiunto alla struttura del modello.](./media/BDM-AddFldExcel-EditableTemplate5.png)

6.  Nel riquadro **Struttura del modello**, selezionare il pulsante con i puntini di sospensione (...) e scegliere **Mostra associazioni**.

    ![Mostra associazioni selezionato.](./media/BDM-AddFldExcel-ShowBindings.png)

    Nel riquadro **Struttura del modello** verranno visualizzate le origini dati disponibili nel formato ER sottostante.

7.  Selezionare **CompanyInfo_Value** come campo che si prevede di associare a un'origine dati del formato ER sottostante.
8.  Nella sezione **Origini dati** del riquadro **Struttura del modello**, espandere **Modello \> InvoiceBase \> CompanyInfo**.
9.  In **CompanyInfo**, selezionare la voce **WebsiteURI**.

    ![Voce WebsiteURI selezionata.](./media/BDM-AddFldExcel-BindURL.png)

10. Selezionare **Associa**.
11. Nel riquadro **Struttura del modello** selezionare **Salva**, quindi chiudere la pagina dell'editor di modelli BDM.

Nell'area di lavoro **Gestione documenti aziendali**, nella scheda **Modello** nel riquadro destro viene visualizzato il modello aggiornato. Nella griglia, notare che il campo **Stato** per il modello modificato è diventato **Bozza** e il campo **Revisione** non è più vuoto. Queste modifiche indicano che il processo di modifica del modello è stato avviato.

![Modello modificato nell'area di lavoro di Gestione documenti aziendali.](./media/BDM-AddFldExcel-Workspace2.png)

## <a name="review-company-settings"></a>Esaminare le impostazioni aziendali

1.  Andare a **Amministrazione organizzazione \> Organizzazioni \> Persone giuridiche**.
2.  Nella Scheda dettaglio **Informazioni sul contatto**, verificare che l'URL della società sia immesso.

![URL della società immesso nella pagina delle persone giuridiche.](./media/BDM-AddFldExcel-CompanyInfo.png)

## <a name="generate-business-documents-to-test-the-updated-template"></a>Generare documenti aziendali per verificare il modello aggiornato

1.  Nell'applicazione, modificare la società in **USMF** e passare **Contabilità clienti \> Fatture \> Tutte le fatture a testo libero**.
2.  Selezionare la fattura **FTI-00000002** e quindi selezionare **Gestione stampa**.
3.  Nel riquadro a sinistra, espandere **Modulo - Contabilità clienti \> Documenti \> Fattura a testo libero**.
4.  In **Fattura a testo libero** selezionare il livello **Documento originale** per specificare l'ambito delle fatture per l'elaborazione.
5.  Nel riquadro a destra, nel campo **Formato report**, selezionare il modello **Fattura a testo libero (Excel) Contoso** per il livello di documento specificato.

    ![Modello Fattura a testo libero (Excel) Contoso selezionato.](./media/BDM-AddFldExcel-PrintMngtSetting.png)

6.  Premere **ESC** per chiudere la pagina corrente.
7.  Selezionare **Stampa \> Selezionato**.
8.  Scaricare il documento generato e aprirlo in Excel.

    ![Fattura a testo libero in Excel.](./media/BDM-AddFldExcel-PreviewReport.png)

Il modello modificato viene utilizzato per generare il report delle fatture a testo libero per l'articolo selezionato. Per analizzare il modo in cui questo report viene modificato in seguito ai cambiamenti al modello, eseguire il report in una sessione dell'applicazione subito dopo aver modificato il modello in un'altra sessione dell'applicazione.

## <a name="related-links"></a>Collegamenti correlati

[Panoramica dello strumento di creazione di report elettronici](general-electronic-reporting.md)

[Panoramica di gestione dei documenti aziendali](er-business-document-management.md)

[Progettare una configurazione per la creazione di report nel formato OPENXML](tasks/er-design-reports-openxml-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]