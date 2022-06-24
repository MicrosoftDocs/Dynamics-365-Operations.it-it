---
title: Visualizzare e aggiornare i dati entità con Excel
description: In questo articolo viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo di Excel di Microsoft Dynamics.
author: jasongre
ms.date: 05/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a05c34454e27244bb08bfff84f2ada6ff498f23
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8862157"
---
# <a name="view-and-update-entity-data-with-excel"></a>Visualizzare e aggiornare i dati entità con Excel 

[!include [applies to](../includes/applies-to-commerce-finance-scm.md)]

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]


In questo articolo viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo di Excel di Microsoft Dynamics. Per aprire i dati entità, è possibile iniziare da Excel o dalle app per finanza e operazioni.

Aprendo i dati entità in Excel, è possibile visualizzare in modo rapido e facile i dati utilizzando il componente aggiuntivo per Excel. Questo componente aggiuntivo richiede Microsoft Excel 2016 o versione successiva.

> [!NOTE]
> Se il tenant Microsoft Azure Active Directory (Azure AD) viene configurato per l'utilizzo di Active Directory Federation Services (AD FS), è necessario verificare che l'aggiornamento del mese di maggio 2016 per Office sia stato applicato, in modo che il componente aggiuntivo di Excel possa consentire correttamente l'accesso.

Per ulteriori informazioni sull'utilizzo del componente aggiuntivo di Excel, guardare il breve video su come c[reare un modello Excel per l'intestazione e allineare i modelli](https://youtu.be/RTicLb-6dbI).

## <a name="open-entity-data-in-excel-when-you-start-from-a-finance-and-operations-app"></a>Aprire i dati entità in Excel quando si inizia da un'app per finanza e operazioni
1. In una pagina in un'app per finanza e operazioni, selezionare **Apri in Microsoft Office**.

    Se l'origine dati principale (tabella) della pagina è analoga a quella dell'origine dati principale di tutte le entità, le opzioni predefinite **Apri in Excel** vengono generate per la pagina. Le opzioni **Apri in Excel** possono essere individuate su pagine utilizzate di frequente, ad esempio **Tutti i fornitori** e **Tutti i clienti**.
 
2. Selezionare l'opzione **Apri in Excel** e aprire la cartella di lavoro generata. Questa cartella di lavoro contiene dati vincolanti per l'entità, un puntatore all'ambiente in uso e un puntatore al componente aggiuntivo di Excel.
3. In Excel selezionare **Abilita modifica** per attivare il componente aggiuntivo di Excel da eseguire. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4. Se si esegue per la prima volta il componente aggiuntivo di Excel, selezionare **Considera attendibile questo componente aggiuntivo**.
5. Se viene richiesto di accedere, selezionare **Accedi**, quindi accedere utilizzando le stesse credenziali usate per l'accesso all'app per finanza e operazioni. Il componente aggiuntivo di Excel utilizzerà un contesto di accesso precedente dal browser e consentirà l'acceso automatico, se possibile. Per informazioni sul browser utilizzato in base al sistema operativo, vedere [Browser utilizzati dai componenti aggiuntivi di Office](/office/dev/add-ins/concepts/browsers-used-by-office-web-add-ins). Per assicurarti che l'accesso sia riuscito, verifica il nome utente nell'angolo in alto a destra del componente aggiuntivo di Excel. 

Il componente aggiuntivo di Excel legge automaticamente i dati dell'entità selezionata. Tenere presente che non saranno disponibili dati nella cartella di lavoro finché il componente aggiuntivo di Excel la leggerà.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Aprire i dati entità in Excel quando si inizia da Excel
1. In Excel nel gruppo **Componenti aggiuntivi** della scheda **Inserisci** selezionare **Store** per aprire l'Office Store.
2. Nell'Office Store cercare la parola chiave **Dynamics** e selezionare **Aggiungi** accanto a **Microsoft Dynamics Office Add-in** (il componente aggiuntivo di Excel).
3. Se si esegue per la prima volta il componente aggiuntivo di Excel, abilitarlo selezionando **Considera attendibile questo componente aggiuntivo**. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4. Selezionare **Aggiungi informazioni sul server** per aprire il riquadro **Opzioni**.
5. Nel browser, copiare l'URL del browser dall'app per finanza e operazioni di destinazione, incollarlo nel campo **URL server**, quindi eliminare tutto ciò che segue il nome host. L'URL risultante deve includere soltanto il nome host.

    Ad esempio, se l'URL è `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, eliminare tutto salvo `https://xxx.dynamics.com`.

6. Selezionare **OK**, quindi **Sì** per confermare la modifica. Il componente aggiuntivo di Excel viene riavviato e carica i metadati.

    Il pulsante **Progettazione** è ora disponibile. Se il componente aggiuntivo di Excel ha un collegamento **Carica applet**, è probabile che la modalità di accesso non sia corretta. Per ulteriori informazioni su come risolvere questo problema, vedere l'argomento della sezione sulla risoluzione dei problemi [Carica applet](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane).

7. Seleziona **Progettazione**. Il componente aggiuntivo di Excel recupera i metadati dell'entità.
8. Selezionare **Aggiungi tabella**. Verrà visualizzato un elenco di entità. Le entità vengono elencate nel formato "Nome - Etichetta".
9. Selezionare un'entità nell'elenco, ad esempio **Cliente - Clienti**, quindi selezionare **Avanti**.
10. Per aggiungere un campo dell'elenco **Campi disponibili** all'elenco **Campi selezionati**, selezionare il campo, quindi **Aggiungi**. In alternativa, fare doppio clic sul campo nell'elenco **Campi disponibili**.
11. Dopo aver aggiunto i campi desiderati all'elenco **Campi selezionati**, verificare che il cursore sia nella posizione corretta nel foglio di lavoro (ad esempio, cella A1), quindi selezionare **Fine**. Selezionare quindi **Fine** per chiudere la finestra di progettazione.
12. Selezionare **Aggiorna** per effettuare il pull di una serie di dati.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizzare e aggiornare i dati entità in Excel
Dopo che il componente aggiuntivo di Excel avrà letto i dati entità nella cartella di lavoro, sarà possibile aggiornarli in qualsiasi momento selezionando **Aggiorna** nel componente aggiuntivo di Excel.

## <a name="edit-entity-data-in-excel"></a>Modificare i dati entità in Excel
È possibile modificare i dati entità come richiesto, quindi pubblicarli di nuovo nelle app per finanza e operazioni selezionando **Pubblica** nel componente aggiuntivo di Excel. Per modificare un record, selezionare una cella del foglio di lavoro, quindi cambiare il valore di cella. Per aggiungere un nuovo record, effettuare uno dei seguenti passaggi:

- Fare clic in un punto qualsiasi della tabella di origini dati, quindi selezionare **Nuovo** nel componente aggiuntivo di Excel.
- Fare clic ovunque sull'ultima riga della tabella di origini dati, quindi premere il tasto TAB finché il cursore non si sposta dall'ultima colonna della riga e viene creata una nuova riga.
- Fare clic ovunque sulla riga immediatamente sotto la tabella di origini dati e iniziare a immettere dati in una cella. Quando si sposta l'elemento attivo della cella, la tabella si espande per includere la nuova riga.
- Per le associazioni del campo dei record di intestazione, selezionare uno dei campi e quindi selezionare **Nuovo** nel componente aggiuntivo di Excel.

Tenere presente che un nuovo record può essere creato solo se tutti i campi obbligatori sono associati nel foglio di lavoro o se i valori predefiniti sono stati specificati tramite la condizione di filtro.

Per eliminare un record, effettuare uno dei seguenti passaggi:

- Fare clic con il pulsante destro del mouse sul numero di riga accanto alla riga del foglio di lavoro da eliminare e selezionare **Elimina**.
- Fare clic con il pulsante destro del mouse ovunque sulla riga del foglio di lavoro da eliminare e selezionare **Elimina** &gt; **Righe tabella**.

Se le origini dati sono state aggiunte come origini dati correlate, l'intestazione viene pubblicata prima delle righe. Se ci sono dipendenze tra altre origini dati, potrebbe essere necessario modificare l'ordine di pubblicazione predefinito. Per cambiare l'ordine di pubblicazione, nel componente aggiuntivo di Excel, selezionare il pulsante **Opzioni** (il simbolo dell'ingranaggio), quindi nella scheda dettaglio **Connettore dati**, selezionare **Configura ordine di pubblicazione**.

## <a name="add-or-remove-columns"></a>Aggiungi o rimuovi colonne
È possibile utilizzare la finestra di progettazione per modificare le colonne aggiunte automaticamente al foglio di lavoro.

> [!NOTE]
> Se il pulsante **Struttura** non è visualizzato sotto il pulsante **Filtro** nel componente aggiuntivo di Excel, è necessario attivare la finestra di progettazione dell'origine dati. Selezionare il pulsante **Opzioni** (il simbolo dell'ingranaggio) quindi selezionare la casella di controllo **Abilita progettazione**.

1. Nel componente aggiuntivo di Excel, fare clic su **Progettazione**. Tutte le origini dati sono elencate.
2. Accanto all'origine dati selezionare il pulsante **Modifica** (il simbolo della matita).
3. Nell'elenco **Campi selezionati**, modificare l'elenco dei campi come necessario:

    - Per aggiungere un campo dell'elenco **Campi disponibili** all'elenco **Campi selezionati**, selezionare il campo, quindi **Aggiungi**. In alternativa, fare doppio clic sul campo nell'elenco **Campi disponibili**.
    - Per rimuovere un campo dall'elenco **Campi selezionati** selezionare il campo, quindi **Rimuovi**. In alternativa, fare doppio clic nel campo.
    - Per modificare l'ordine dei campi nell'elenco **Campi selezionati**, selezionare un campo e quindi selezionare **Su** o **Giù**.

4. Per applicare le modifiche all'origine dati selezionare **Aggiorna**. Selezionare quindi **Fine** per chiudere la finestra di progettazione.
5. Se è stato aggiunto un campo (colonna), selezionare **Aggiorna** per effettuare il pull di una serie aggiornata di dati.

## <a name="change-the-publish-batch-size"></a>Modificare la dimensione del batch di pubblicazione
Quando gli utenti pubblicano le modifiche ai record di dati utilizzando il componente aggiuntivo di Excel, gli aggiornamenti vengono inviati in batch. La dimensione del batch di pubblicazione predefinita (e massima) è 100 righe; in ogni caso, la funzionalità **Consenti configurazione della dimensione batch di pubblicazione nel componente aggiuntivo di Excel** offre flessibilità nel ridurre le dimensioni del batch di pubblicazione, soprattutto se si verificano dei timeout quando si tenta di pubblicare gli aggiornamenti da Excel.

Gli amministratori di sistema possono specificare un limite a livello di sistema per le dimensioni del batch di pubblicazione per le cartelle di lavoro "Apri in Excel" impostando il campo **Pubblica limite batch** nella sezione **Parametri dell'app** della pagina **Parametri dell'app di Office**.

La dimensione del batch di pubblicazione può essere modificata anche per una singola cartella di lavoro utilizzando il componente aggiuntivo di Excel.

1. Apri la cartella di lavoro in Excel.
2. Selezionare il pulsante **Opzione** (icona a forma di rotella) nell'angolo in alto a destra del componente aggiuntivo di Excel.
3. Impostare il campo **Pubblica dimensione batch** come desiderato. Il valore impostato deve essere inferiore al limite di batch di pubblicazione a livello di sistema.
4. Selezionare **OK**.
5. Salva la cartella di lavoro. Se non si salva la cartella di lavoro dopo aver apportato modifiche alle impostazioni del componente aggiuntivo, tali modifiche non verranno mantenute quando la cartella di lavoro viene riaperta.

Gli autori dei modelli di cartelle di lavoro di Excel possono utilizzare la stessa procedura per impostare la dimensione del batch di pubblicazione per i modelli prima di caricarli nel sistema.

## <a name="copy-environment-data"></a>Copia dati dell'ambiente

I dati letti nella cartella di lavoro di un ambiente possono essere copiati in un altro ambiente. Tuttavia, non è possibile modificare semplicemente la connessione URL, poiché la cache di dati nella cartella di lavoro continuerà a elaborare i dati come dati esistenti. Utilizzare invece la funzionalità Copia dati dell'ambiente per pubblicare i dati in un nuovo ambiente come nuovi dati.

1. Selezionare il pulsante **Opzioni** (il simbolo dell'ingranaggio), quindi nella scheda Dettaglio **Connettore dati**, selezionare **Copia dati dell'ambiente**. 
2. Immettere l'URL del server per il nuovo ambiente. 
3. Selezionare **OK**, quindi **Sì** per confermare l'azione. Il componente aggiuntivo di Excel viene riavviato e connesso al nuovo ambiente. Tutti i dati esistenti nella cartella di lavoro vengono elaborati come nuovi dati.

    Dopo il riavvio del componente aggiuntivo di Excel, una finestra di messaggio indica che la cartella di lavoro è in modalità di copia dell'ambiente.

4. Per copiare i dati nel nuovo ambiente come nuovi dati, selezionare **Pubblica**. Per annullare l'operazione di copia dell'ambiente ed esaminare i dati esistenti nel nuovo ambiente, selezionare **Aggiorna**.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Sono disponibili alcuni problemi che possono essere risolti attraverso alcuni semplici passaggi.

- **Viene mostrato il collegamento "Carica applet"** - Per ulteriori informazioni su questo problema, vedere l'argomento della sezione sulla risoluzione dei problemi [Carica applet](../office-integration/office-integration-troubleshooting.md#issue-the-excel-add-in-loads-but-instead-of-showing-data-it-displays-load-applets-in-the-task-pane). 
- **Viene visualizzato un messaggio "Non consentito"** - Se si riceve un messaggio "Non consentito" mentre il componente aggiuntivo di Excel sta caricando i metadati, l'account cui si accede nel componente aggiuntivo di Excel non dispone dell'autorizzazione a utilizzare il servizio, l'istanza o il database di destinazione. Per risolvere questo problema, verificare che il nome utente corretto sia visualizzato nell'angolo superiore destro del componente aggiuntivo di Excel. Se viene visualizzato un nome utente errato, selezionarlo, disconnettersi e accedere di nuovo.
- **Una pagina Web vuota viene visualizzata sopra Excel** - Se una pagina Web vuota viene aperta durante il processo di accesso, l'account richiede AD FS, ma la versione di Excel in cui è in esecuzione il componente aggiuntivo di Excel non è abbastanza recente per caricare la finestra di dialogo di accesso. Per risolvere questo problema, aggiornare la versione di Excel in uso. Per aggiornare la versione di Excel quando si è in un'azienda che si trova sul canale differito, utilizzare lo [strumento di distribuzione di Office](/deployoffice/overview-office-deployment-tool) per [spostare dal canale differito al canale corrente](/deployoffice/overview-update-channels).
- **Si riceve un timeout durante la pubblicazione delle modifiche ai dati** - Se ricevi messaggi di timeout mentre stai tentando di pubblicare le modifiche ai dati in un'entità, valuta la possibilità di ridurre le dimensioni del batch di pubblicazione per la cartella di lavoro interessata. Le entità che attivano quantità maggiori di logica sulle modifiche ai record potrebbero richiedere l'invio di aggiornamenti in batch più piccoli per evitare timeout.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
