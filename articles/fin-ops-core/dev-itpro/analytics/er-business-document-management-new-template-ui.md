---
title: Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali
description: Questo argomento descrive come utilizzare la nuova interfaccia utente nella funzionalità Gestione documenti aziendali del framework Creazione di report elettronici.
author: v-anamir
ms.date: 04/12/2021
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
ms.openlocfilehash: e6c5081f71a18dfac83b7aea950395436b42f50e
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881038"
---
# <a name="microsoft-office-style-user-interface-in-business-document-management"></a>Interfaccia utente di tipo Microsoft Office in Gestione documenti aziendali

[!include [banner](../includes/banner.md)]

La funzionalità Gestione documenti aziendali consente agli utenti aziendali di modificare i modelli di documenti aziendali tramite un servizio Microsoft 365 o l'applicazione desktop Microsoft Office appropriata. Le modifiche potrebbero includere modifiche alla progettazione o nuove distribuzioni oppure gli utenti potrebbero aggiungere segnaposto per includere dati aggiuntivi senza dover modificare il codice sorgente. Per ulteriori informazioni su come utilizzare Gestione documenti aziendali, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).

La nuova interfaccia utente è più chiara e più facile da utilizzare. L'area **Documento aziendale** mostra solo i modelli disponibili per il provider corrente. Nell'interfaccia utente precedente, la scheda **Modello** elencava tutti i modelli disponibili per qualsiasi provider. Mostrava anche tutti i modelli creati e modificati da qualsiasi utente con lo stesso ruolo.

È possibile utilizzare il pulsante **Nuovo documento** per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider. Nell'esempio in questo argomento, il provider è Microsoft. In alternativa, è possibile creare un modello caricando il modello in formato Excel.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWAVQg]

Il video [Creare un nuovo documento aziendale utilizzando Gestione documenti aziendali](https://youtu.be/gAIYl-mM_pw) (mostrato sopra) è incluso nella [playlist Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponibile su YouTube.

## <a name="make-the-new-document-ui-in-business-document-management-available"></a>Rendere disponibile la nuova interfaccia utente per documenti in Gestione documenti aziendali

Per iniziare a utilizzare la nuova interfaccia utente per documenti in Gestione documenti aziendali, è necessario attivare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'area di lavoro **Gestione funzionalità**.

Seguire questi passaggi per attivare questa funzione per tutte le persone giuridiche.

1. Nell'area di lavoro **Gestione funzionalità**, nella scheda **Tutto**, selezionare la funzionalità **Esperienza di interfaccia utente simile a Office per Gestione documenti aziendali** nell'elenco.
2. Selezionare **Abilita ora** per attivare la funzionalità selezionata.
3. Aggiorna la pagina per accedere alla nuova funzionalità.

## <a name="edit-templates-that-are-owned-by-other-providers"></a>Modificare i modelli di proprietà di altri provider

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)

2. Nella scheda **Seleziona**, selezionare il documento da utilizzare come modello e quindi selezionare **Crea documento**.

    ![Finestra di dialogo Documenti aziendali](./media/BDM_overview_new_template2.png)

3. Nella nuova finestra di dialogo, nel campo **Titolo**, cambiare il titolo come richiesto. Il testo del titolo verrà utilizzato per assegnare un nome alla nuova configurazione in formato ER creata automaticamente. La versione bozza di questa configurazione (**Copia report FTl cliente (GER)**) conterrà il modello modificato e verrà automaticamente utilizzata per eseguire questo formato ER per l'utente corrente. Il modello originale della configurazione in formato ER di base sarà utilizzato per eseguire questo formato ER per qualsiasi altro utente.
4. Nel campo **Nome**, modificare il nome della prima revisione del modello modificabile che verrà creato automaticamente.
5. Nel campo **Commento**, aggiornare i commenti per la revisione del modello modificabile che verrà creata automaticamente.
6. Selezionare **OK** per confermare l'avvio del processo di modifica.

    ![Finestra di dialogo per la creazione di documenti](./media/BDM_overview_new_template3.png)

Il pulsante **Nuovo documento** è utilizzato per creare e modificare un modello in una configurazione in formato ER fornita da un altro provider. In questo esempio, il provider è Microsoft. Quando si seleziona **Nuovo documento**, è possibile visualizzare tutti i modelli di proprietà del provider corrente e di altri provider. Dopo aver selezionato il modello, questo viene aperto per la modifica. Il modello modificato verrà archiviato in una nuova configurazione in formato ER generato automaticamente.

## <a name="upload-a-template-that-uses-an-existing-excel-format"></a>Caricare un modello che utilizza un formato Excel esistente
Seguire questi passaggi per fornire le informazioni necessarie prima di caricare un modello.

1. Nell'area di lavoro **Gestione documenti aziendali**, selezionare **Nuovo documento**.

    ![Area di lavoro di Gestione documenti aziendali](./media/BDM_overview_new_template1.png)
    
2. Nella pagina **Crea un nuovo modello**, nella scheda **Carica**, nella scheda **Modello**, selezionare **Sfoglia** per trovare e selezionare il file Excel che si desidera utilizzare come modello. Nella sezione **Modello**, i campi **Titolo** e **Descrizione** vengono compilati automaticamente. Questi specificano il nome e la descrizione della nuova configurazione in formato ER che viene creata automaticamente. È possibile modificare questi campi secondo le necessità.
3. Nella sezione **Tipo di documento**, nel campo **Nome**, specificare il tipo di documento aziendale. Questo valore verrà utilizzato per cercare l'origine dati corretta (ovvero la configurazione del modello ER).

    ![Scheda Modello](./media/BDM_overview_new_UI_import_21.jpg)

4. Nella scheda **Origine dati**, nella Scheda dettaglio **Filtro**, selezionare **Applica filtro**. Nella sezione **Origine dati**, il campo **Nome** viene compilato automaticamente oppure è possibile selezionare manualmente un valore. È possibile utilizzare il filtro per cercare il nome dell'origine dati appropriata per nome, descrizione, codice paese/regione e tipo di documento aziendale.

    ![Scheda Origine dati](./media/BDM_overview_new_UI_import_31.jpg)
    
    > [!NOTE]
    > Questa Scheda dettaglio **Filtro** viene utilizzata per cercare nell'origine dati corretta (ovvero la configurazione del modello ER). È possibile modificare tutti i campi del filtro per trovare l'origine dati più appropriata per il documento che si sta caricando.
    > 
    > Le condizioni nella Scheda dettaglio **Filtro** sono usate come condizioni **OR**.
    
5. Nella scheda **Mapping**, selezionare **Rilevamento automatico**. Il campo **Definizione radice** viene automaticamente riempito oppure è possibile selezionare manualmente un valore. Questa scheda mostra il mapping finale per gli elementi del modello.

    ![Scheda Mapping](./media/BDM_overview_new_UI_import_41.jpg)
    
   > [!NOTE]
   > Il mapping nella sezione **Struttura del modello** utilizza la corrispondenza completa delle etichette o delle descrizioni nell'origine dati nella lingua dell'utente e nel nome di cella nel modello.

6. Selezionare **Crea documento** per confermare che si desidera creare un modello e avviare il processo di modifica.

Per ulteriori informazioni, vedere [Panoramica di Gestione documenti aziendali](er-business-document-management.md).

Se non è presente un provider in Creazione di report elettronici, è possibile crearne uno. Se non c'è un provider attivo, è possibile scegliere di attivarne uno.

- Per creare un provider, modificare il nome del provider nel campo **Nome**, aggiornare l'indirizzo Internet del nuovo provider nel campo **Indirizzo Internet** e selezionare **OK** per confermare.

    ![Creare un nuovo provider in Gestione documenti aziendali](./media/bdm_create_provider.png)
    
- Per attivare il provider esistente, scegliere il nome del provider nel campo **Provider di configurazioni** e selezionare **OK** per impostare il provider come attivo.

    ![Attivare il provider in Gestione documenti aziendali](./media/bdm_choose_provider.png)

> [!NOTE]
> Ogni modello di Gestione documenti aziendali fa riferimento al provider come autore della configurazione. Questo è il motivo per cui un provider attivo è necessario per il modello.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
