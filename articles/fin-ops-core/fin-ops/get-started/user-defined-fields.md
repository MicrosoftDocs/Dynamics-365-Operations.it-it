---
title: Creare e utilizzare campi personalizzati
description: In questo articolo viene illustrato come creare i campi personalizzati tramite l'interfaccia utente per adattare l'applicazione alle esigenze aziendali.
author: jasongre
ms.date: 12/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 18e7e8525352e8fdc397621c381ed4297837e30c
ms.sourcegitcommit: 69d7dd6a2d0dc7f2661c7d1f61e8874c7bde1448
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2022
ms.locfileid: "9887289"
---
# <a name="create-and-work-with-custom-fields"></a>Creare e utilizzare campi personalizzati

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Sebbene sia fornito un ampio set di campi pronti all'uso per la gestione di un'ampia gamma di processi aziendali, a volte è necessario che un'azienda tenga traccia di ulteriori informazioni nel sistema. Mentre i programmatori possono essere utilizzati per aggiungere quei campi come estensioni negli strumenti di sviluppo, la funzione dei campi personalizzati consente di aggiungere campi direttamente dall'interfaccia utente, permettendo in tal modo di adattare l'applicazione in modo alla propria azienda utilizzando il browser Web.

*Solo gli utenti con autorizzazioni speciali hanno accesso a questa funzione.*

Questo video spiega quanto sia semplice aggiungere un campo personalizzato a una pagina: [Aggiunta di campi personalizzati](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Creazione di campi personalizzati

Dopo aver identificato ulteriori informazioni per monitorare l'applicazione, è possibile creare il campo personalizzato nella tabella appropriata ed esporre il nuovo campo in una pagina.

Nei passaggi seguenti viene descritto il processo per creare un campo personalizzato e inserirlo in una pagina.

1. Accedi alla pagina in cui vuoi inserire il nuovo campo.
2. Poiché l'obiettivo finale è esporre il campo personalizzato in un modulo, il punto di ingresso per la creazione di campi personalizzati si trova all'interno dell'esperienza di personalizzazione. Aprire la barra degli strumenti di personalizzazione selezionando **Opzioni**, quindi **Personalizza modulo**.
3. Fare clic su **Inserisci** e **Campo**.
4. Selezionare l'area del modulo in cui si desidera esporre il nuovo campo. Dopo la selezione, nella finestra di dialogo **Inserisci campi** verrà visualizzato un elenco di campi esistenti che possono essere inseriti nell'area selezionata della pagina.
5. Verifica che il campo desiderato non sia già presente nell'elenco. Se un record esiste già, è possibile scegliere semplicemente tale campo dall'elenco e fare clic su **Inserisci**.
6. Fare clic sul pulsante **Crea nuovo campo** sopra l'elenco per avviare il processo di creazione di un campo personalizzato. In questo modo verrà aperta la finestra di dialogo **Crea nuovo campo**.

    Se non è presente il pulsante **Crea nuovo campo**, significa che non hai le autorizzazioni necessarie per utilizzare questa funzionalità.

7. Nella finestra di dialogo **Crea nuovo campo** immettere le seguenti informazioni:
   
    1. Selezionare la tabella di database in cui questo campo deve essere aggiunto. Tenere presente che solo le tabelle che supportano i campi personalizzati verranno visualizzate nell'elenco a discesa. Vedere la sezione riportata di seguito per i dettagli tecnici sulle tabelle supportate.

    2. Selezionare il tipo di dati per il nuovo campo. I tipi di dati disponibili sono casella di controllo, data, ora, numero decimale, elenco di selezione e testo.

        - Se si sceglie il tipo di dati in formato testo, è possibile specificare anche la lunghezza massima del testo che può essere immesso in questo campo.
        - Se si sceglie il tipo di dati di elenco di selezione, è inoltre possibile selezionare il set di valori validi per il campo.

    3. Immettere un nome, un'etichetta e un testo della Guida in linea relativa al campo. Il nome corrisponde al nome del campo fisico nel database, mentre l'etichetta e il testo della Guida sono il testo utilizzato per rappresentare questo campo nell'interfaccia utente.

8. Se questo è l'unico campo che devi creare per questa pagina, fai clic su **Salva**. Se è necessario creare i campi aggiuntivi, fare clic su **Salva e nuovo** e tornare al passaggio 7. 

>[!Note] 
> Attualmente esiste un limite di **20 campi personalizzati per tabella**.

9. Chiudendo la finestra di dialogo **Crea nuovo campo** si tornerà alla finestra di dialogo **Inserisci i campi**. Eventuali campi personalizzati appena aggiunti verranno automaticamente contrassegnati nell'elenco dei campi da inserire nella pagina.
10. Fai clic su **Inserisci** per inserire i campi contrassegnati nell'area selezionata della pagina.
11. **Facoltativo**: abilitare la modalità **Sposta** dalla barra degli strumenti di personalizzazione per spostare i nuovi campi nella posizione desiderata nell'area selezionata. Per ulteriori informazioni su come utilizzare le varie funzionalità di personalizzazione per ottimizzare un modulo per l'utilizzo personale, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).

> [!WARNING]
> La possibilità di inserire valori in un campo personalizzato aggiunto a una pagina dipende dal fatto che la tabella associata al campo personalizzato sia modificabile o di sola lettura. Quando la tabella associata è di sola lettura, anche tutti i campi collegati a quella tabella, inclusi i campi personalizzati, saranno di sola lettura.


## <a name="sharing-custom-fields-with-other-users"></a>Condividere campi personalizzati con altri utenti

Dopo aver creato un campo personalizzato e averlo esposto in una pagina, è possibile fornire la visualizzazione di questa pagina aggiornata che include il nuovo campo agli altri utenti nel sistema. Questo può essere realizzato in due modi diversi utilizzando le capacità di personalizzazione del prodotto:

- Il percorso consigliato è quello di **pubblicare una [visualizzazione salvata](saved-views.md)** con il campo personalizzato aggiunto alla pagina al gruppo di utenti appropriato. Se la funzione delle visualizzazioni salvate non è abilitata, l'amministratore di sistema può applicare la personalizzazione agli utenti desiderati dalla pagina **Personalizzazione**. Per ulteriori informazioni, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).
- In alternativa, è possibile esportare le modifiche (dette *personalizzazioni*), inviarle a uno o più utenti e chiedere a ciascuno di questi utenti di importare le modifiche. L' opzione **Gestisci** sulla barra degli strumenti di personalizzazione consente di esportare e importare le personalizzazioni.

## <a name="managing-custom-fields"></a>Gestione di campi personalizzati

La gestione di tutti i campi personalizzati può essere eseguita tramite la pagina **Campi personalizzati** nel modulo di amministrazione del sistema. Questa pagina consente agli utenti l'accesso a numerose funzionalità, tra cui:

- Visualizzazione di un elenco di tutti i campi personalizzati nel sistema.
- Modifica limitata dei campi personalizzati esistenti.
- Eliminazione di campi personalizzati.
- Esposizione di campi personalizzati in entità di dati.
- Traduzione di etichette di campo personalizzate e testo di guida.

### <a name="viewing-all-custom-fields"></a>Visualizzazione di tutti i campi di personalizzati

La pagina **Campi personalizzati** offre visibilità su tutti i campi personalizzati definiti nel sistema. Seleziona la tabella di interesse e la pagina si aggiornerà per mostrare un elenco dei campi personalizzati associati a quella tabella. La scelta di un campo personalizzato dall'elenco consente di visualizzare tutti i dettagli sul campo.

### <a name="editing-custom-fields"></a>Modifica di campi personalizzati.

Dopo che un campo personalizzato è stato creato, solo alcuni informazioni sul campo personalizzati possono essere modificate nella pagina **Campi personalizzati**.

*È possibile* modificare i seguenti attributi:

- Etichetta
- Testo guida
- Lunghezza, per i campi di testo

*Non* è possibile modificare i seguenti attributi:

- Nome campo
- Tipo di dati

Inoltre, per i campi elenco di selezione, è possibile riordinare l'insieme di valori validi per il campo personalizzato e aggiungere nuovi valori; tuttavia, i valori esistenti per il campo elenco di selezione non possono essere rimossi. Fai clic su **Applica modifiche** al termine delle modifiche dei campi per una determinata tabella in modo che le modifiche vengano salvate.

### <a name="exposing-custom-fields-on-data-entities"></a>Esposizione di campi personalizzati in entità di dati

Potrebbe anche essere importante consentire ai campi personalizzati di essere visibili sulle entità dati. Le entità dati sono utilizzate nella funzionalità [Panoramica dell'integrazione di Office](../../dev-itpro/office-integration/office-integration.md) e per gli scenari di importazione / esportazione dei dati.

Seguire questi passaggi per esporre un campo personalizzato in un'entità di dati:

1. Selezionare il campo personalizzato nella pagina **Campi personalizzati**.
2. Espandere l'area **Entità** per visualizzare l'insieme di entità rilevanti.
3. Fare clic sul pulsante **Modifica**.
4. Modificare il campo **Abilitato** da selezionare per ciascuna entità che dovrà esporre questo campo.
5. Fare clic su **Applica modifiche** per salvare le selezioni.

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Consentire la visualizzazione dei campi personalizzati in altre lingue

Poiché i campi personalizzati possono richiedere l'accesso da parte degli utenti in una varietà di lingue, la pagina **Campi personalizzati** fornisce un meccanismo che consente di tradurre in altre lingue l'etichetta e il testo della guida per un campo personalizzato.

I seguenti passaggi descrivono il processo per la traduzione di campi personalizzati in altre lingue:

1. Selezionare il campo personalizzato nella pagina **Campi personalizzati**.
2. Selezionare il pulsante **Traduzioni** nel riquadro azioni. Verrà aperto un menu a discesa con le traduzioni esistenti per questo campo.
3. Il menu a discesa **Lingua** mostra il set di lingue per cui le traduzioni sono già state fornite.

    Per modificare una traduzione esistente, seleziona la lingua dal menu e modifica i valori per l'etichetta e il testo della guida.

    In caso contrario, fare clic sul pulsante **Aggiungi lingua**, selezionare la lingua desiderata dal menu quindi immettere i valori di conversione per il testo guida e etichette.

4. Al termine, fare clic su **OK**.

### <a name="deleting-custom-fields"></a>Eliminazione di campi personalizzati

Quando decidi che un campo personalizzato non è più necessario, un amministratore di sistema può scegliere di eliminare il campo dalla pagina **Campi personalizzati**. Per eliminare un campo personalizzato, seleziona il campo da eliminare, fai clic su **Elimina**, quindi su **Sì** per confermare l'eliminazione e infine fai clic su **Applica modifiche**.

> [!NOTE]
> Questa azione non può essere annullata e determinerà l'eliminazione definitiva dei dati associati al campo dal database.

## <a name="appendix"></a>Appendice

### <a name="why-cant-i-enter-a-value-in-my-custom-field"></a>Perché non posso inserire un valore nel mio campo personalizzato? 

Se non è possibile digitare un valore nel campo personalizzato quando la pagina è in modalità **Modifica**, ciò potrebbe essere dovuto al fatto che la tabella a cui è stato aggiunto il campo è attualmente di sola lettura. Tutti i campi in una tabella diventano di sola lettura solo se la tabella di supporto è attualmente configurata come sola lettura nella pagina.   

### <a name="who-can-create-custom-fields"></a>Chi può creare campi personalizzati?

Solo gli amministratori di sistema possono creare campi personalizzati per impostazione predefinita. Tuttavia, gli utenti esperti, power user, che l'organizzazione ritiene necessari possono ottenere da un amministratore di sistema i diritti per creare campi personalizzati utilizzando il ruolo di sicurezza **Power user personalizzazione runtime**. Gli utenti senza questo ruolo di sicurezza non potranno creare campi personalizzati, ma potranno comunque vedere e interagire con i campi personalizzati aggiunti da altri utenti nel sistema.

### <a name="what-tables-support-custom-fields"></a>Quali tabelle supportano i campi personalizzati?

Per motivi tecnici e di prestazioni, solo le tabelle che soddisfano le seguenti condizioni consentono attualmente l'aggiunta di campi personalizzati.

- La tabella deve essere contrassegnata come uno di questi gruppi:

    - Raggruppa
    - WorksheetHeader
    - Principale
    - Varie
    - Parametro
    - Riferimento
    - TransactionHeader

- La tabella non può estendere un'altra tabella.
- La tabella non può essere contrassegnata come tabella di sistema.
- La tabella non può essere una tabella temporanea.

### <a name="can-i-reference-custom-fields-from-the-developer-tools"></a>È possibile fare riferimento a campi personalizzati dagli strumenti di sviluppo?  

I campi personalizzati possono essere gestiti solo attraverso l'interfaccia utente e non è possibile farvi riferimento dal codice. 

### <a name="how-can-i-move-custom-fields-between-environments"></a>Come posso spostare i campi personalizzati tra gli ambienti? 

L'attuale raccomandazione per lo spostamento di campi personalizzati tra ambienti è ricreare manualmente i campi personalizzati nell'ambiente di destinazione. Per visualizzare l'elenco completo dei campi personalizzati su una particolare tabella:
1. Vai alla pagina **Campi personalizzati** e seleziona la tabella dal menu a discesa. 
2. Nell'ambiente di destinazione, segui il processo descritto in precedenza in questo articolo per ricreare ogni campo. 
3. Una volta creati tutti i campi, fai clic su **Applica modifiche**.  
4. Sposta tutte le personalizzazioni contenenti campi personalizzati esportandole dall'ambiente originale e importandole nell'ambiente di destinazione.  


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
