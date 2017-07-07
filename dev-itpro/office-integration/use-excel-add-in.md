---
title: Utilizzare il componente aggiuntivo di Excel
description: "In questo argomento viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Microsoft Dynamics Office per Excel."
author: ChrisGarty
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 267914
ms.assetid: 4e6c7194-a059-4057-bd62-ec0c802c36fd
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 298ac47e2253f8add1aa3938dda15afe186afbeb
ms.openlocfilehash: f55e1e89d0e48819962c169a56f0f27dc0d792b4
ms.contentlocale: it-it
ms.lasthandoff: 06/20/2017


---

# <a name="use-the-excel-add-in"></a>Utilizzare il componente aggiuntivo di Excel

[!include[banner](../includes/banner.md)]


In questo argomento viene illustrato come aprire i dati entità in Microsoft Excel e visualizzare, aggiornare e modificare i dati utilizzando il componente aggiuntivo Microsoft Dynamics Office per Excel. Per aprire i dati entità, è possibile iniziare da Excel o da Microsoft Dynamics 365 for Finance and Operations, Enterprise edition.

Aprendo i dati entità in Microsoft Excel, è possibile visualizzare in modo rapido e facile i dati utilizzando il componente aggiuntivo Microsoft Dynamics Office per Excel. Questo componente aggiuntivo richiede Microsoft Excel 2016. **Nota:** se il tenant Microsoft Azure Active Directory (Azure AD) viene configurato per l'utilizzo di Active Directory Federation Services (AD FS), è necessario verificare che l'aggiornamento del mese di maggio 2016 sia stato applicato, in modo che il componente aggiuntivo di Excel possa consentire correttamente l'accesso.

## <a name="open-entity-data-in-excel-when-you-start-from-dynamics-365-for-finance-and-operations"></a>Aprire i dati entità in Excel quando si inizia da Dynamics 365 for Finance and Operations
1.  In una pagina in Microsoft Dynamics 365 for Finance and Operations fare clic su **Apri in Microsoft Office**. Se l'origine dati principale (tabella) della pagina è analoga a quella dell'origine dati principale di tutte le entità, le opzioni predefinite **Apri in Excel** vengono generate per la pagina. Le opzioni **Apri in Excel** possono essere individuate su pagine utilizzate di frequente, ad esempio **Tutti i fornitori** e **Tutti i clienti**.
2.  Fare clic sull'opzione **Apri in Excel** e aprire la cartella di lavoro generata. Questa cartella di lavoro contiene dati vincolanti per l'entità, un puntatore all'ambiente in uso e un puntatore al componente aggiuntivo di Excel.
3.  In Excel fare clic su **Abilita modifica** per attivare il componente aggiuntivo di Excel da eseguire. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4.  Se si esegue per la prima volta il componente aggiuntivo di Excel, fare clic su **Considera attendibile questo componente aggiuntivo**.
5.  Se viene richiesto di accedere, fare clic su **Accedi**, quindi accedere utilizzando le stesse credenziali usate per l'accesso a Dynamics 365 for Finance and Operations. Il componente aggiuntivo di Excel utilizzerà un contesto di accesso precedente rispetto a Internet Explorer e consentirà l'acceso automatico, se possibile. Di conseguenza, verificare il nome utente nell'angolo superiore destro del componente aggiuntivo di Excel.

Il componente aggiuntivo di Excel legge automaticamente i dati dell'entità selezionata. Tenere presente che non saranno disponibili dati nella cartella di lavoro finché il componente aggiuntivo di Excel la leggerà.

## <a name="open-entity-data-in-excel-when-you-start-from-excel"></a>Aprire i dati entità in Excel quando si inizia da Excel
1.  In Excel nel gruppo **Componenti aggiuntivi** della scheda **Inserisci** fare clic su **Store** per aprire l'Office Store.
2.  Nell'Office Store cercare la parola chiave "Dynamics" e fare clic su **Aggiungi** accanto a **Microsoft Dynamics Office Add-in** (il componente aggiuntivo di Excel).
3.  Se si esegue per la prima volta il componente aggiuntivo di Excel, abilitarlo facendo clic su **Considera attendibile questo componente aggiuntivo**. Il componente aggiuntivo di Excel viene eseguito nel riquadro a destra della finestra di Excel.
4.  Fare clic su **Aggiungi informazioni sul server** per aprire il riquadro **Opzioni**.
5.  Copiare l'URL del browser dall'istanza Dynamics 365 for Finance and Operations di destinazione, incollarlo nel campo **URL server**, quindi eliminare tutto ciò che segue il nome host. L'URL risultante deve includere soltanto il nome host.
Ad esempio, se l'URL è https://xxx.dynamics.com/?cmp=usmf&amp;mi=CustTableListPage, eliminare tutto ad eccezione di **https://xxx.dynamics.com**.
6.  Fare clic su **OK**, quindi su **Sì** per confermare la modifica. Il componente aggiuntivo di Excel si riavvia e carica i metadati. Il pulsante **Progettazione** è ora disponibile. Se il componente aggiuntivo di Excel è un pulsante **Carica applet**, è probabile che la modalità di accesso non sia corretta. Per ulteriori informazioni, vedere "Viene visualizzato il pulsante Carica applet" nella sezione "Risoluzione dei problemi" di questo argomento.
7.  Fare clic su **Progettazione**. Il componente aggiuntivo di Excel recupera i metadati dell'entità.
8.  Fare clic su **Aggiungi tabella**. Verrà visualizzato un elenco di entità. Le entità vengono elencate nel formato "Nome - Etichetta".
9.  Selezionare un'entità nell'elenco, ad esempio **Cliente - Clienti**, quindi fare clic su **Avanti**.
10. Per aggiungere un campo dell'elenco **Campi disponibili** all'elenco **Campi selezionati**, fare clic sul campo, quindi su **Aggiungi**. In alternativa, fare doppio clic nel campo.
11. Dopo aver aggiunto i campi desiderati all'elenco **Campi selezionati**, verificare che il cursore sia nella posizione corretta nel foglio di lavoro (ad esempio, cella A1), quindi fare clic su **Fine**. Fare quindi clic su **Fine** per chiudere la finestra di progettazione.
12. Fare clic su **Aggiorna** per effettuare il pull di una serie di dati.

## <a name="view-and-update-entity-data-in-excel"></a>Visualizzare e aggiornare i dati entità in Excel
Dopo che il componente aggiuntivo di Excel avrà letto i dati entità nella cartella di lavoro, sarà possibile aggiornarli in qualsiasi momento facendo clic su **Aggiorna** nel componente aggiuntivo di Excel.

## <a name="edit-entity-data-in-excel"></a>Modificare i dati entità in Excel
È possibile modificare i dati entità come richiesto, quindi pubblicarli facendo clic su **Pubblica** nel componente aggiuntivo di Excel. Per modificare un record, selezionare una cella del foglio di lavoro, quindi cambiare il valore di cella. Per aggiungere un nuovo record, effettuare uno dei seguenti passaggi:

-   Fare clic in un punto qualsiasi della tabella di origini dati, quindi su **Nuovo** nel componente aggiuntivo di Excel.
-   Fare clic sull'ultima riga della tabella di origini dati, quindi premere il tasto TAB finché il cursore non si sposta dall'ultima colonna della riga e viene creata una nuova riga.
-   Fare clic sulla riga immediatamente sotto la tabella di origini dati e iniziare a immettere dati in una cella. Quando si sposta l'elemento attivo della cella, la tabella si espande per includere la nuova riga.
-   Per le associazioni del campo dei record di intestazione, fare clic su uno dei campi e quindi fare clic su **Nuovo** nel componente aggiuntivo di Excel.

Tenere presente che un nuovo record può essere creato solo se tutti i campi obbligatori sono associati nel foglio di lavoro o se i valori predefiniti sono stati specificati tramite la condizione di filtro.
Per eliminare un record, effettuare uno dei seguenti passaggi:

-   Fare clic con il pulsante destro del mouse sul numero di riga accanto alla riga del foglio di lavoro da eliminare e fare clic su **Elimina**.
-   Fare clic con il pulsante destro del mouse nella riga del foglio di lavoro da eliminare, quindi su **Elimina** &gt; **Righe tabella**.
Se le origini dati sono state aggiunte come correlate, l'intestazione viene pubblicata prima delle righe. Se ci sono dipendenze tra altre origini dati, potrebbe essere necessario modificare l'ordine di pubblicazione predefinito. Per cambiare l'ordine di pubblicazione, nel componente aggiuntivo di Excel, fare clic sul pulsante **Opzioni** (simbolo di ingranaggio). Quindi, nella scheda dettaglio **Connettore dati**, fare clic su **Configura ordine di pubblicazione**.

## <a name="add-or-remove-columns"></a>Aggiungi o rimuovi colonne
È possibile utilizzare la finestra di progettazione per modificare le colonne aggiunte automaticamente al foglio di lavoro.

1.  Avviare la finestra di progettazione dell'origine dati del componente aggiuntivo di Excel facendo clic sul pulsante **Opzioni** (il simbolo dell'ingranaggio), quindi selezionando la casella di controllo **Abilita progettazione**.
2.  Fare clic su **Progettazione** nel componente aggiuntivo di Excel. Tutte le origini dati sono elencate.
3.  Accanto all'origine dati fare clic sul pulsante **Modifica** (il simbolo della matita).
4.  Modificare l'elenco **Campi selezionati** in base alle esigenze:
    -   Per aggiungere un campo dell'elenco **Campi disponibili** all'elenco **Campi selezionati**, fare clic sul campo, quindi su **Aggiungi**. In alternativa, fare doppio clic nel campo.
    -   Per rimuovere un campo dall'elenco **Campi selezionati** fare clic sul campo, quindi su **Rimuovi**. In alternativa, fare doppio clic nel campo.
    -   Per modificare l'ordine dei campi, fare clic sul campo nell'elenco **Campi selezionati**, fare clic su un campo quindi su **Su** o **Giù**.

5. Per applicare le modifiche all'origine dati fare clic su **Aggiorna**. Fare quindi clic su **Fine** per chiudere la finestra di progettazione. 
6. Se è stato aggiunto un campo (colonna), scegliere **Aggiorna** per effettuare il pull di una serie aggiornata di dati.

## <a name="httpspowerappsmicrosoftcomenustutorialsdataplatforminteractiveexceltroubleshootingtroubleshooting"></a>[](https://powerapps.microsoft.com/enus/tutorials/dataplatforminteractiveexcel/#troubleshooting)Risoluzione dei problemi
Sono disponibili alcuni problemi che possono essere risolti attraverso alcuni semplici passaggi.

-   **Viene visualizzato il pulsante Carica applet.** Se il componente aggiuntivo di Excel mostra un pulsante **Carica applet** dopo l'accesso, è probabile che la modalità di accesso non sia corretta. Per risolvere questo problema, verificare che il nome utente corretto sia visualizzato nell'angolo superiore destro del componente aggiuntivo di Excel. Se viene visualizzato un nome utente errato, fare clic su di esso, disconnettersi e riaccedere.
-   **Viene visualizzato un messaggio "Non consentito".** Se si riceve un messaggio "Non consentito" mentre il componente aggiuntivo di Excel sta caricando i metadati, l'account cui si accede nel componente aggiuntivo di Excel non dispone dell'autorizzazione a utilizzare il servizio, l'istanza o il database di destinazione. Per risolvere questo problema, verificare che il nome utente corretto sia visualizzato nell'angolo superiore destro del componente aggiuntivo di Excel. Se viene visualizzato un nome utente errato, fare clic su di esso, disconnettersi e riaccedere.
-   **Una pagina Web vuota viene visualizzata sopra Excel.** Se una pagina Web vuota viene visualizzata durante il processo di accesso, l'account richiede AD FS, ma la versione di Excel in cui è in esecuzione il componente aggiuntivo non è abbastanza recente per caricare la finestra di dialogo di accesso. Per risolvere questo problema, aggiornare la versione di Excel in uso. Per aggiornare la versione di Excel quando si è in un'azienda che si trova sul canale differito, utilizzare lo [strumento di distribuzione di Office](https://technet.microsoft.com/library/jj219422.aspx) per [spostare dal canale differito al canale corrente](https://technet.microsoft.com/library/mt455210.aspx).





