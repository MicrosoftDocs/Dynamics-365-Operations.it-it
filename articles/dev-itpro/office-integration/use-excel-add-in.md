---
title: Utilizzare il componente aggiuntivo di Excel
description: "In questo argomento viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Microsoft Dynamics Office per Excel."
author: ChrisGarty
manager: AnnBe
ms.date: 11/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 002c3bea2803fdf43b0c35620c8d46fc9400fafc
ms.openlocfilehash: 9db4f7ed9cba0d91a9a8507a33882a9114bdb1f5
ms.contentlocale: it-it
ms.lasthandoff: 01/04/2018

---

# <a name="use-the-excel-add-in"></a>Utilizzare il componente aggiuntivo di Excel

[!include[banner](../includes/banner.md)]

In questo argomento viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Microsoft Dynamics Office per Excel. Per aprire i dati entità, è possibile iniziare da Excel o da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Aprendo i dati entità in Excel, è possibile visualizzare in modo rapido e facile i dati utilizzando il componente aggiuntivo per Excel. Questo componente aggiuntivo richiede Microsoft Excel 2016.

> [!NOTE]
> Se il tenant Microsoft Azure Active Directory (Azure AD) viene configurato per l'utilizzo di Active Directory Federation Services (AD FS), è necessario verificare che l'aggiornamento del mese di maggio 2016 per Office sia stato applicato, in modo che il componente aggiuntivo di Excel possa consentire correttamente l'accesso.

## <a name="open-entity-data-in-excel-when-you-start-from-finance-and-operations"></a>Aprire i dati entità in Excel quando si inizia da Finance and Operations
1. In una pagina in Finance and Operations, selezionare **Apri in Microsoft Office**.

    Se l'origine dati principale (tabella) della pagina è analoga a quella dell'origine dati principale di tutte le entità, le opzioni predefinite **Apri in Excel** vengono generate per la pagina. Le opzioni **Apri in Excel** possono essere individuate su pagine utilizzate di frequente, ad esempio **Tutti i fornitori** e **Tutti i clienti**.
 
2. Selezionare l'opzione **Apri in Excel** e aprire la cartella di lavoro generata. Questa cartella di lavoro contiene dati vincolanti per l'entità, un puntatore all'ambiente in uso e un puntatore al componente aggiuntivo di Excel.
3. In Excel selezionare **Abilita modifica** per attivare il componente aggiuntivo di Excel da eseguire. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4. Se si esegue per la prima volta il componente aggiuntivo di Excel, selezionare **Considera attendibile questo componente aggiuntivo**.
5. Se viene richiesto di accedere, selezionare **Accedi**, quindi accedere utilizzando le stesse credenziali usate per l'accesso a Finance and Operations. Il componente aggiuntivo di Excel utilizzerà un contesto di accesso precedente rispetto a Internet Explorer e consentirà l'acceso automatico, se possibile. Di conseguenza, verificare il nome utente nell'angolo superiore destro del componente aggiuntivo di Excel.

Il componente aggiuntivo di Excel legge automaticamente i dati dell'entità selezionata. Tenere presente che non saranno disponibili dati nella cartella di lavoro finché il componente aggiuntivo di Excel la leggerà.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Aprire i dati entità in Excel quando si inizia da Excel
1. In Excel nel gruppo **Componenti aggiuntivi** della scheda **Inserisci** selezionare **Store** per aprire l'Office Store.
2. Nell'Office Store cercare la parola chiave **Dynamics** e selezionare **Aggiungi** accanto a **Microsoft Dynamics Office Add-in** (il componente aggiuntivo di Excel).
3. Se si esegue per la prima volta il componente aggiuntivo di Excel, abilitarlo selezionando **Considera attendibile questo componente aggiuntivo**. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4. Selezionare **Aggiungi informazioni sul server** per aprire il riquadro **Opzioni**.
5. Nel browser, copiare l'URL del browser dall'istanza Finance and Operations di destinazione, incollarlo nel campo **URL server**, quindi eliminare tutto ciò che segue il nome host. L'URL risultante deve includere soltanto il nome host.

    Ad esempio, se l'URL è `https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage`, eliminare tutto salvo `https://xxx.dynamics.com`.

6. Selezionare **OK**, quindi **Sì** per confermare la modifica. Il componente aggiuntivo di Excel viene riavviato e carica i metadati.

    Il pulsante **Progettazione** è ora disponibile. Se il componente aggiuntivo di Excel è un pulsante **Carica applet**, è probabile che la modalità di accesso non sia corretta. Per ulteriori informazioni, vedere "Viene visualizzato il pulsante Carica applet" nella sezione [Risoluzione dei problemi](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/office-integration/use-excel-add-in#troubleshooting) di questo argomento.

7. Selezionare **Struttura**. Il componente aggiuntivo di Excel recupera i metadati dell'entità.
8. Selezionare **Aggiungi tabella**. Verrà visualizzato un elenco di entità. Le entità vengono elencate nel formato "Nome - Etichetta".
9. Selezionare un'entità nell'elenco, ad esempio **Cliente - Clienti**, quindi selezionare **Avanti**.
10. Per aggiungere un campo dell'elenco **Campi disponibili** all'elenco **Campi selezionati**, selezionare il campo, quindi **Aggiungi**. In alternativa, fare doppio clic sul campo nell'elenco **Campi disponibili**.
11. Dopo aver aggiunto i campi desiderati all'elenco **Campi selezionati**, verificare che il cursore sia nella posizione corretta nel foglio di lavoro (ad esempio, cella A1), quindi selezionare **Fine**. Selezionare quindi **Fine** per chiudere la finestra di progettazione.
12. Selezionare **Aggiorna** per effettuare il pull di una serie di dati.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizzare e aggiornare i dati entità in Excel
Dopo che il componente aggiuntivo di Excel avrà letto i dati entità nella cartella di lavoro, sarà possibile aggiornarli in qualsiasi momento selezionando **Aggiorna** nel componente aggiuntivo di Excel.

## <a name="edit-entity-data-in-excel"></a>Modificare i dati entità in Excel
È possibile modificare i dati entità come richiesto, quindi pubblicarli selezionando **Pubblica** nel componente aggiuntivo di Excel. Per modificare un record, selezionare una cella del foglio di lavoro, quindi cambiare il valore di cella. Per aggiungere un nuovo record, effettuare uno dei seguenti passaggi:

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

## <a name="copy-environment-data"></a>Copia dati dell'ambiente

I dati letti nella cartella di lavoro di un ambiente possono essere copiati in un altro ambiente. Tuttavia, non è possibile modificare semplicemente la connessione URL, poiché la cache di dati nella cartella di lavoro continuerà a elaborare i dati come dati esistenti. Utilizzare invece la funzionalità Copia dati dell'ambiente per pubblicare i dati in un nuovo ambiente come nuovi dati.

1. Selezionare il pulsante **Opzioni** (il simbolo dell'ingranaggio), quindi nella scheda Dettaglio **Connettore dati**, selezionare **Copia dati dell'ambiente**. 
2. Immettere l'URL del server per il nuovo ambiente. 
3. Selezionare **OK**, quindi **Sì** per confermare l'azione. Il componente aggiuntivo di Excel viene riavviato e connesso al nuovo ambiente. Tutti i dati esistenti nella cartella di lavoro vengono elaborati come nuovi dati.

    Dopo il riavvio del componente aggiuntivo di Excel, una finestra di messaggio indica che la cartella di lavoro è in modalità di copia dell'ambiente.

4. Per copiare i dati nel nuovo ambiente come nuovi dati, selezionare **Pubblica**. Per annullare l'operazione di copia dell'ambiente ed esaminare i dati esistenti nel nuovo ambiente, selezionare **Aggiorna**.

## <a name="troubleshooting"></a>Risoluzione dei problemi
Sono disponibili alcuni problemi che possono essere risolti attraverso alcuni semplici passaggi.

- **Viene visualizzato il pulsante Carica applet** - Se il componente aggiuntivo di Excel mostra un pulsante **Carica applet** dopo l'accesso, è probabile che la modalità di accesso non sia corretta. Per risolvere questo problema, verificare che il nome utente corretto sia visualizzato nell'angolo superiore destro del componente aggiuntivo di Excel. Se viene visualizzato un nome utente errato, selezionarlo, disconnettersi e accedere di nuovo.
- **Viene visualizzato un messaggio "Non consentito"** - Se si riceve un messaggio "Non consentito" mentre il componente aggiuntivo di Excel sta caricando i metadati, l'account cui si accede nel componente aggiuntivo di Excel non dispone dell'autorizzazione a utilizzare il servizio, l'istanza o il database di destinazione. Per risolvere questo problema, verificare che il nome utente corretto sia visualizzato nell'angolo superiore destro del componente aggiuntivo di Excel. Se viene visualizzato un nome utente errato, selezionarlo, disconnettersi e accedere di nuovo.
- **Una pagina Web vuota viene visualizzata sopra Excel** - Se una pagina Web vuota viene aperta durante il processo di accesso, l'account richiede AD FS, ma la versione di Excel in cui è in esecuzione il componente aggiuntivo di Excel non è abbastanza recente per caricare la finestra di dialogo di accesso. Per risolvere questo problema, aggiornare la versione di Excel in uso. Per aggiornare la versione di Excel quando si è in un'azienda che si trova sul canale differito, utilizzare lo [strumento di distribuzione di Office](https://technet.microsoft.com/library/jj219422.aspx) per [spostare dal canale differito al canale corrente](https://technet.microsoft.com/library/mt455210.aspx).

