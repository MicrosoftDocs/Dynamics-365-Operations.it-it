---
title: Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali (video)
description: Questo argomento descrive come utilizzare la nuova interfaccia utente nella funzionalità Gestione documenti aziendali del framework Creazione di report elettronici.
author: v-anamir
ms.date: 01/05/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERBDWorkspace, ERBDParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-anamir
ms.search.validFrom: 2019-08-01
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e33830e2147d92ad5ee53ad11da55a50613b8ef9
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8074743"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali

[!include [banner](../includes/banner.md)]

La funzionalità Gestione documenti aziendali consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite un servizio Microsoft Office 365 o l'applicazione desktop Microsoft Office appropriata. Le modifiche potrebbero includere modifiche alla progettazione o nuove distribuzioni oppure gli utenti potrebbero aggiungere segnaposto per includere dati aggiuntivi senza dover modificare il codice sorgente. Per ulteriori informazioni su come utilizzare Gestione documenti aziendali, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).

La nuova interfaccia utente è più chiara e più facile da utilizzare. L'area **Documento aziendale** mostra solo i modelli che sono di proprietà del [provider](tasks/er-configuration-provider-mark-it-active-2016-11.md)[ attivo](general-electronic-reporting.md#Provider) corrente e che si trova nell'istanza corrente di Dynamics 365 Finance. Nell'interfaccia utente precedente, la scheda **Modello** elencava tutti i modelli disponibili per qualsiasi provider. Mostrava anche tutti i modelli creati e modificati da qualsiasi utente con lo stesso ruolo.

Puoi utilizzare il pulsante **Nuovo documento** nell'area di lavoro **Gestione documenti aziendali** per creare e modificare un modello in una [configurazione](general-electronic-reporting.md#Configuration) del formato [Creazione di report elettronici (ER)](general-electronic-reporting.md) fornito da un altro provider e che si trova nell'istanza di Finance corrente o per caricare un nuovo modello da una cartella di lavoro di Excel. Inoltre, nella versione 10.0.25 e successive, puoi utilizzare il pulsante **Nuovo documento** per creare e modificare un modello in una configurazione in formato ER archiviata nel [repository globale](general-electronic-reporting.md#Repository).

Negli esempi in questo argomento, il provider attivo è Contoso e lo utilizzi per creare un modello basato su un modello fornito da Microsoft. In alternativa, è possibile creare un modello caricando il modello in formato Excel.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWAVQg]

Il video [Creare un nuovo documento aziendale utilizzando Gestione documenti aziendali](https://youtu.be/gAIYl-mM_pw) (mostrato sopra) è incluso nella [playlist Finanza e operazioni](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendere disponibile la nuova interfaccia utente per documenti in Gestione documenti aziendali

Per iniziare a utilizzare la nuova interfaccia utente per documenti in Gestione documenti aziendali, è necessario attivare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'area di lavoro **Gestione funzionalità**.

Seguire questi passaggi per attivare questa funzione per tutte le persone giuridiche.

1. Nell'area di lavoro **Gestione funzionalità**, nella scheda **Tutto**, selezionare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'elenco.
2. Selezionare **Abilita ora** per attivare la funzionalità selezionata.
3. Aggiorna la pagina per accedere alla nuova funzionalità.

## <a name="add-or-activate-a-provider"></a>Aggiungere o attivare un provider

Ciascun modello di un documento aziendale viene archiviato in una configurazione in formato ER contrassegnata come di proprietà di un provider di configurazione specifico. Quando crei un nuovo modello, viene creata una nuova configurazione del formato ER per contenerlo. Pertanto, è necessario identificare un provider per quella configurazione. A tale scopo viene utilizzato il provider attivo del framework ER. Se non ci sono provider in ER, puoi crearne uno. Se non esiste un provider *attivo*, è possibile attivare uno dei provider esistenti. Una finestra di dialogo per l'aggiunta o l'attivazione di un provider viene aperta quando è necessario mentre si inizia ad aggiungere un nuovo modello.

### <a name="add-a-new-provider"></a>Aggiungi un nuovo provider

Per creare un nuovo provider, segui questi passaggi nella finestra di dialogo **Provider di configurazione**:

1.  Nella scheda **Scegli il provider di configurazione**, nel campo **Nome**, immetti il nome del nuovo provider.
2.  Nel campo **Indirizzo Internet** immetti l'indirizzo Internet (URL) del nuovo provider. 
3.  Seleziona **OK**.

    ![Creazione di un nuovo provider in Gestione documenti aziendali.](./media/bdm_create_provider.png)

Il provider aggiunto verrà attivato automaticamente.

### <a name="activate-a-provider"></a>Attivare un provider

Per attivare un provider, segui questi passaggi nella finestra di dialogo **Provider di configurazione**:

1.  Nella scheda **Scegli il provider di configurazione**, nel campo **Provider configurazione**, seleziona il provider.
2.  Seleziona **OK**.

    ![Attivazione di un nuovo provider in Gestione documenti aziendali.](./media/bdm_choose_provider.png)

Il provider selezionato verrà attivato.

> [!NOTE]
> Ciascun modello di gestione dei documenti aziendali si trova in una configurazione in formato ER che fa riferimento al provider come autore della configurazione. Pertanto, un provider attivo è necessario per ogni modello.

## <a name="edit-a-template-that-is-owned-by-another-provider"></a>Modificare un modello di proprietà di un altro provider

Questo esempio mostra come utilizzare il pulsante **Nuovo documento** nell'area di lavoro **Gestione documenti aziendali** per creare e modificare un modello in una configurazione del formato Creazione di report elettronici (ER) fornito da un altro provider e che si trova nell'istanza di Finance corrente. In questo esempio, il provider attivo è Contoso, che usa la configurazione del formato ER fornita da Microsoft. Dopo aver selezionato **Nuovo documento**, la scheda **Seleziona** nella pagina **Crea un nuovo modello** mostra tutti i modelli dell'istanza Finance corrente di proprietà del provider corrente e di altri provider. Seleziona un modello per aprirlo. È quindi possibile creare una nuova copia modificabile del modello. Il modello modificato viene archiviato in una nuova configurazione in formato ER generato automaticamente.

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.

    ![Area di lavoro di Gestione documenti aziendali.](./media/BDM_overview_new_template1.png)

2. Nella pagina **Crea un nuovo modello**, nella scheda **Seleziona**, seleziona il documento da utilizzare come modello, quindi seleziona **Crea documento**.

    ![Finestra di dialogo Documenti aziendali.](./media/BDM_overview_new_template2.png)

3. Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto. Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente. La versione bozza di questa configurazione (**Copia report FTl cliente (GER)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente. Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.
4. Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.
5. Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.
6. Selezionare **OK** per confermare l'avvio del processo di modifica.

    ![Finestra di dialogo per la creazione di documenti.](./media/BDM_overview_new_template3.png)

## <a name="upload-a-template-that-uses-an-existing-excel-workbook"></a>Caricare un modello che utilizza una cartella di lavoro Excel esistente

Questo esempio mostra come utilizzare il pulsante **Nuovo documento** nell'area di lavoro **Gestione documenti aziendali** per creare e modificare un modello in una configurazione del formato Creazione di report elettronici (ER) in base alla cartella di lavoro Excel disponibile. In questo esempio, il provider attivo è Contoso e utilizzi le configurazioni del [modello di dati](er-overview-components.md#data-model-component) ER e del [mapping del modello](er-overview-components.md#model-mapping-component) ER fornite da Microsoft. Dopo aver selezionato **Nuovo documento**, seleziona scheda **Carica** nella pagina **Crea un nuovo modello**. Qui puoi specificare i dettagli di un caricamento di una cartella di lavoro di Excel. Dopo aver caricato la cartella di lavoro di Excel, viene trasformata in un modello di documento aziendale che viene aperto per la modifica. Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.

Seguire questi passaggi per fornire le informazioni necessarie prima di caricare un modello.

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.
2. Nella pagina **Crea un nuovo modello**, nella scheda **Carica**, nella scheda **Modello**, selezionare **Sfoglia** per trovare e selezionare il file Excel che si desidera utilizzare come modello. Nella sezione **Modello**, i campi **Titolo** e **Descrizione** vengono compilati automaticamente. Questi specificano il nome e la descrizione della nuova configurazione in formato ER che viene creata automaticamente. È possibile modificare questi campi secondo le necessità.
3. Nella sezione **Tipo di documento**, nel campo **Nome**, specificare il tipo di documento aziendale. Questo valore verrà utilizzato per cercare l'origine dati corretta (ovvero la configurazione del modello ER).

    ![Scheda Modello nella scheda Carica della pagina Crea un nuovo modello.](./media/BDM_overview_new_UI_import_21.jpg)

4. Nella scheda **Origine dati**, nella Scheda dettaglio **Filtro**, selezionare **Applica filtro**. Nella sezione **Origine dati**, il campo **Nome** viene compilato automaticamente oppure è possibile selezionare manualmente un valore. È possibile utilizzare il filtro per cercare il nome dell'origine dati appropriata per nome, descrizione, codice paese/regione e tipo di documento aziendale.

    ![Scheda Origine dati nella scheda Carica della pagina Crea un nuovo modello.](./media/BDM_overview_new_UI_import_31.jpg)

    > [!NOTE]
    > Questa Scheda dettaglio **Filtro** viene utilizzata per cercare nell'origine dati corretta (ovvero la configurazione del modello ER). È possibile modificare tutti i campi del filtro per trovare l'origine dati più appropriata per il documento che si sta caricando.
    > 
    > Le condizioni nella Scheda dettaglio **Filtro** sono usate come condizioni **OR**.

5. Nella scheda **Mapping**, selezionare **Rilevamento automatico**. Il campo **Definizione radice** viene automaticamente riempito oppure è possibile selezionare manualmente un valore. Questa scheda mostra il mapping finale per gli elementi del modello.

    ![Scheda Mapping nella scheda Carica della pagina Crea un nuovo modello.](./media/BDM_overview_new_UI_import_41.jpg)

    > [!NOTE]
    > Il mapping nella sezione **Struttura del modello** utilizza la corrispondenza completa delle etichette o delle descrizioni nell'origine dati nella lingua dell'utente e nel nome di cella nel modello.

6. Selezionare **Crea documento** per confermare che si desidera creare un modello e avviare il processo di modifica.

Per ulteriori informazioni, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).

## <a name="upload-a-template-from-the-global-repository"></a>Carica un modello dal repository globale

Questo esempio mostra come utilizzare il pulsante **Nuovo documento** nell'area di lavoro **Gestione documenti aziendali** per creare e modificare un modello in una configurazione del formato ER fornito da Microsoft e che si trova nel repository globale. In questo esempio, il provider attivo è Contoso, che usa la configurazione del formato ER fornita da Microsoft. Dopo aver selezionato **Nuovo documento**, la scheda **Importa da repository globale** nella pagina **Crea un nuovo modello** mostra tutti i modelli di documenti aziendali archiviati nel repository globale ma mancanti nell'istanza Finance corrente. Dopo aver selezionato un modello, viene importato dal repository globale nell'istanza Finance corrente per creare una nuova copia modificabile. Il modello modificato viene archiviato in una nuova configurazione in formato ER generato automaticamente.

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.
2. Nella pagina **Crea un nuovo modello**, nella scheda **Importa da repository globale**, seleziona il documento da utilizzare come modello, quindi seleziona **Crea documento**.

    ![Importa dalla scheda repository globale nella pagina Crea un nuovo modello.](./media/BDM_overview_new_template22.png)

3. Nella finestra del messaggio, seleziona **Sì** per confermare che desideri importare il documento selezionato dal repository globale nell'istanza Finance corrente. Se viene richiesta l'autorizzazione, seguire le istruzioni sullo schermo.
4. Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto. Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente. La versione bozza di questa configurazione (**Nota lettera di sollecito (Excel)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente. Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.
5. Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.
6. Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.
7. Selezionare **OK** per confermare l'avvio del processo di modifica.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
