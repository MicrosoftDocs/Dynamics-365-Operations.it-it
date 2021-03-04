---
title: Aggiornare la struttura di un modello di documento aziendale
description: In questo argomento viene illustrato come aggiornare la struttura di un modello di documento aziendale utilizzando la funzionalità Gestione documenti aziendali.
author: NickSelin
manager: AnnBe
ms.date: 11/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters, ERBDTemplateEditor
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-12-01
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: fd279b28c43e22bec6bf814845fe97828bc96d81
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4681330"
---
# <a name="update-the-structure-of-a-business-document-template"></a>Aggiornare la struttura di un modello di documento aziendale 

[!include[banner](../includes/banner.md)]

Nel riquadro **Struttura del modello** dell'editor di modelli [Gestione documenti aziendali](er-business-document-management.md), è possibile modificare un modello di documento aziendale [aggiungendo nuovi campi](er-bdm-add-field-to-excel-template.md) a un modello in Microsoft Excel. La struttura del modello viene quindi aggiornata automaticamente in Dynamics 365 Finance, in modo che rifletta le modifiche apportate nel riquadro **Struttura del modello**.

È inoltre possibile modificare un modello utilizzando funzionalità online Office 365. Ad esempio, puoi aggiungere un nuovo elemento con nome, come un'immagine o una forma, al foglio di lavoro modificabile. In questo caso, la struttura del modello non viene aggiornata automaticamente in Finance e l'elemento aggiunto non viene visualizzato nel riquadro **Struttura del modello**. Aggiorna manualmente la struttura del modello in Finance selezionando **Aggiorna struttura** nella pagina dell'editor del modello.

Per ulteriori informazioni su questa funzionalità, completare l'esempio riportato di seguito.

## <a name="example-update-the-structure-of-a-business-document-template"></a>Esempio: aggiornare la struttura di un modello di documento aziendale

Questo esempio mostra come un amministratore di sistema può aggiornare la struttura di un modello di documento aziendale in Finance dopo che il modello è stato modificato in Office Online. Le sezioni seguenti spiegano i passaggi coinvolti.

### <a name="prepare-a-business-document-template-for-editing"></a>Prepara un modello di documento aziendale per la modifica

Completare le seguenti procedure in [Panoramica di gestione dei documenti aziendali](er-business-document-management.md).

1. [Configurare i parametri ER](er-business-document-management.md#configure-er-parameters)
2. [Importare soluzioni ER](er-business-document-management.md#import-er-solutions)
3. [Abilitare Gestione documenti aziendali](er-business-document-management.md#enable-business-document-management)
4. [Configurare i parametri](er-business-document-management.md#configure-parameters)

### <a name="edit-a-business-document-template"></a>Modificare un modello di documento aziendale

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.
2. Nella pagina **Crea un nuovo modello**, selezionare il modello **Fattura a testo libero (campione ER) (Excel)**.
3. Selezionare **Crea documento**.
4. Nel campo **Titolo**, immettere **campione FTI Litware**.
5. Selezionare **OK** per creare il nuovo modello.

    > [!NOTE]
    > Se non hai ancora effettuato l'accesso a Office Online, [verrai reindirizzato alla Office 365 pagina di accesso](er-business-document-management.md#i-selected-edit-document-but-instead-of-opening-the-bdm-template-editor-page-in-finance-and-operations-i-have-been-sent-to-the-microsoft-365-web-page). Per tornare al tuo ambiente finanziario, selezionare il pulsante **Indietro** nel browser.

    Il nuovo modello viene aperto per la modifica nel controllo incorporato di Excel Online nella pagina dell'editor del modello.

[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per iniziare a modificare un modello di documento aziendale](./media/er-bdm-update-structure1.gif)](./media/er-bdm-update-structure1.gif)

### <a name="review-the-current-structure-of-the-editable-template"></a>Rivedi la struttura corrente del modello modificabile

1. In Excel Online, nella barra multifunzione, nella scheda **Visualizza**, nel gruppo **Mostra**, selezionare **Linee della griglia**.
2. Nel modello modificabile, seleziona il rettangolo sopra il titolo del modello. Questo rettangolo è un'immagine denominata **rptHeaderCompLogo**.
3. Se il riquadro **Struttura del modello** è nascosto, selezionare **Mostra struttura**.
4. Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.
5. Si noti che, nella struttura del modello in Finance, l'elemento **rptHeaderCompLogo** viene presentato come elemento secondario di **Report \> Fattura \> rptHeader \> rptHeaderPart1**.

[![Utilizzo dell'area di lavoro Gestione documenti aziendali per rivedere la struttura corrente di un modello modificabile](./media/er-bdm-update-structure2.gif)](./media/er-bdm-update-structure2.gif)

### <a name="update-the-structure-of-a-business-document-template-by-deleting-a-picture"></a>Aggiornare la struttura di un modello di documento aziendale eliminando un'immagine

1. In Excel Online, nel modello modificabile, selezionare l'immagine **rptHeaderCompLogo**.
2. Segui uno di questi passaggi per eliminare l'immagine selezionata dal modello modificabile:

    - Selezionare il tasto **Elimina** sulla tastiera.
    - Selezionare e tenere premuto (o fare clic con il pulsante destro del mouse) sull'immagine, quindi selezionare **Taglia**.

    > [!NOTE]
    > L'elemento **rptHeaderCompLogo** è attualmente ancora presente nella struttura del modello in Finance, anche se l'immagine non è più inclusa nel modello Excel.

3. Selezionare **Aggiorna struttura** per sincronizzare la struttura del modello modificabile in Excel e Finance.
4. Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.
5. Si noti che l'elemento **rptHeaderCompLogo** non è più incluso nella struttura del modello in Finance.

[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per eliminare un'immagine da un modello di documento aziendale](./media/er-bdm-update-structure3.gif)](./media/er-bdm-update-structure3.gif)

### <a name="update-the-structure-of-a-business-document-template-by-adding-a-picture"></a>Aggiornare la struttura di un modello di documento aziendale aggiungendo un'immagine

1. In Excel Online, nella barra multifunzione, nella scheda **Inserisci**, nel gruppo **Figure**, selezionare **Immagine**.
2. Selezionare **Scegli il file**, individuare l'immagine che si desidera aggiungere, selezionarla e quindi selezionare **OK**.
3. Selezionare **Inserisci**.
4. Sposta la nuova immagine finché non si trova nella posizione corretta. Per impostazione predefinita, Excel assegna un nome all'immagine. Ad esempio, potrebbe denominare l'immagine **Immagine 2**.
5. Selezionare **Aggiorna struttura** per sincronizzare la struttura del modello modificabile in Excel e Finance.
6. Nel riquadro **Struttura del modello**, espandere **Report \> Fattura \> rptHeader \> rptHeaderPart1**.
7. Si noti che la nuova immagine è ora inclusa come un elemento nella struttura del modello in Finance.

[![Utilizzo dell'area di lavoro di Gestione documenti aziendali per aggiungere un'immagine a un modello di documento aziendale](./media/er-bdm-update-structure4.gif)](./media/er-bdm-update-structure4.gif)

## <a name="related-links"></a>Collegamenti correlati

[Panoramica dei report elettronici](general-electronic-reporting.md)

[Panoramica di gestione dei documenti aziendali](er-business-document-management.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]