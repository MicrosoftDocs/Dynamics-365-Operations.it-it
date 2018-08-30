---
title: Creare e utilizzare i campi personalizzati
description: In questo argomento viene illustrato come Microsoft Dynamics 365 for Finance and Operations consente agli utenti di creare i campi personalizzati per adattare l'applicazione in base alle esigenze aziendali.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.translationtype: HT
ms.sourcegitcommit: 764d4c9049d94ebcd55c61654aa2f4133b35bae6
ms.openlocfilehash: 1ce709a4b5cce145d841b844a21a5218ba250c87
ms.contentlocale: it-it
ms.lasthandoff: 08/09/2018

---

# <a name="create-and-work-with-custom-fields"></a>Creare e utilizzare i campi personalizzati

[!include [banner](../includes/banner.md)]

Sebbene Microsoft Dynamics 365 for Finance and Operations fornisca un ampio set di campi pronti all'uso per la gestione di un'ampia gamma di processi aziendali, a volte è necessario che un'azienda tenga traccia di ulteriori informazioni nel sistema. Per soddisfare questa esigenza, Finance and Operations consente di creare campi personalizzati per personalizzare l'applicazione in base alle esigenze aziendali, a condizione di disporre delle autorizzazioni per la funzionalità. 

La possibilità di aggiungere campi personalizzati è disponibile nell'aggiornamento piattaforma 13 e successivi.

Questo video spiega quanto sia semplice aggiungere un campo personalizzato a una pagina: [Aggiunta di campi personalizzati in Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=gWSGZI9Vtnc).

## <a name="creating-custom-fields"></a>Creazione di campi personalizzati
Dopo aver identificato ulteriori informazioni che desideri monitorare nell'applicazione, è possibile creare il campo personalizzato nella tabella appropriata ed esporre il nuovo campo in una pagina.   

Nei passaggi seguenti viene descritto il processo per creare un campo personalizzato e inserirlo in un modulo.  

1.   Accedere al modulo in cui è necessario inserire il nuovo campo. 
2.   Poiché l'obiettivo finale è esporre il campo personalizzato in un modulo, il punto di ingresso per la creazione di campi personalizzati si trova all'interno dell'esperienza di personalizzazione. Aprire la barra degli strumenti di personalizzazione selezionando **Opzioni**, quindi **Personalizza modulo**. 
3.   Fare clic su **Inserisci** e **Campo**.  
4.   Selezionare l'area del modulo in cui si desidera esporre il nuovo campo. Dopo la selezione, nella finestra di dialogo **Inserisci campi** verrà visualizzato un elenco di campi esistenti che possono essere inseriti nell'area selezionata del modulo.  
5.   Assicurarsi che il campo desiderato non sia già presente nell'elenco. Se un record esiste già, è possibile scegliere semplicemente tale campo dall'elenco e fare clic su **Inserisci**.   
6.   Fare clic sul pulsante **Crea nuovo campo** sopra l'elenco per avviare il processo di creazione di un campo personalizzato. In questo modo verrà aperta la finestra di dialogo **Crea nuovo campo**. 

     Se non è presente il pulsante **Crea nuovo campo**, significa che non si dispone delle autorizzazioni necessarie per utilizzare questa funzionalità.  
     
7.   Nella finestra di dialogo **Crea nuovo campo** immettere le seguenti informazioni:
     1.   Selezionare la tabella di database in cui questo campo deve essere aggiunto. Tenere presente che solo le tabelle che supportano i campi personalizzati verranno visualizzate nell'elenco a discesa. Vedere la sezione riportata di seguito per i dettagli tecnici sulle tabelle supportate.  
     2.   Selezionare il tipo di dati per il nuovo campo. I tipi di dati disponibili sono casella di controllo, data, ora, numero decimale, elenco di selezione e testo.   
          - Se si sceglie il tipo di dati in formato testo, è possibile specificare anche la lunghezza massima del testo che può essere immesso in questo campo. 
          - Se si sceglie il tipo di dati di elenco di selezione, è inoltre possibile selezionare il set di valori validi per il campo.  
     3.   Immettere un nome, un'etichetta e un testo della Guida in linea relativa al campo. Il nome corrisponde al nome del campo fisico nel database, mentre l'etichetta e il testo della Guida sono il testo utilizzato per rappresentare questo campo nell'interfaccia utente.  
8.   Se questo è l'unico campo che devi creare per questo modulo, fare clic su **Salva**. Se è necessario creare i campi aggiuntivi, fare clic su **Salva e nuovo** e tornare al passaggio 7. Si noti che attualmente esiste un limite di **20 campi personalizzati per tabella**.
9.   Chiudendo la finestra di dialogo **Crea nuovo campo** si tornerà alla finestra di dialogo **Inserisci i campi**. Eventuali campi personalizzati appena aggiunti verranno automaticamente contrassegnati nell'elenco dei campi da inserire nel modulo.  
10.   Fare clic su **Inserisci** per inserire i campi contrassegnati nell'area selezionata del modulo. 
11.   **Facoltativo**: abilitare la modalità **Sposta** dalla barra degli strumenti di personalizzazione per spostare i nuovi campi nella posizione desiderata nell'area selezionata. Per ulteriori informazioni su come utilizzare le varie funzionalità di personalizzazione per ottimizzare un modulo per l'utilizzo personale, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md).  

## <a name="sharing-custom-fields-with-other-users"></a>Condividere campi personalizzati con altri utenti
Dopo aver creato un campo personalizzato e averlo esposto in un modulo, è possibile fornire la visualizzazione di questa pagina aggiornata che include il nuovo campo agli altri utenti nel sistema. Questo può essere realizzato in due modi diversi utilizzando le capacità di personalizzazione del prodotto:

-   La modalità consigliata è attraverso l'amministratore di sistema, che può inviare una personalizzazione a tutti gli utenti o a un sottoinsieme di utenti. Per ulteriori informazioni sulla, vedere [Personalizzare l'esperienza utente](personalize-user-experience.md). 

-   In alternativa, è possibile esportare le modifiche (dette *personalizzazioni*), inviarle a uno o più utenti e chiedere a ciascuno di questi utenti di importare le modifiche. L' opzione **Gestisci** sulla barra degli strumenti di personalizzazione consente di esportare e importare le personalizzazioni.

## <a name="managing-custom-fields"></a>Gestione di campi personalizzati

La gestione di tutti i campi personalizzati nel sistema può essere eseguita tramite la pagina **Campi personalizzati** nel modulo di amministrazione del sistema.  Questa pagina consente agli utenti l'accesso a numerose funzionalità, tra cui: 
-   Visualizzazione di un elenco di tutti i campi personalizzati nel sistema.
-   Modifica limitata dei campi personalizzati esistenti.
-   Eliminazione di campi personalizzati.
-   Esposizione di campi personalizzati in entità di dati.
-   Traduzione di etichette di campo personalizzate e testo di guida.

### <a name="viewing-all-custom-fields"></a>Visualizzazione di tutti i campi di personalizzati
La pagina **Campi personalizzati** offre visibilità su tutti i campi personalizzati definiti nel sistema. È sufficiente selezionare la tabella di interesse e la pagina si aggiornerà per mostrare un elenco dei campi personalizzati associati a quella tabella. La scelta di un campo personalizzato dall'elenco consente di visualizzare tutti i dettagli sul campo.

### <a name="editing-custom-fields"></a>Modifica di campi personalizzati.
Dopo che un campo personalizzato è stato creato, solo alcuni informazioni sul campo personalizzati possono essere modificate nella pagina **Campi personalizzati**.   

*È possibile* modificare i seguenti attributi: 
-   Etichetta 
-   Testo guida
-   Lunghezza, per i campi di testo

*Non* è possibile modificare i seguenti attributi: 
-   Nome campo
-   Tipo di dati

Inoltre, per i campi elenco di selezione, è possibile riordinare l'insieme di valori validi per il campo personalizzato e aggiungere nuovi valori; tuttavia, i valori esistenti per il campo elenco di selezione non possono essere rimossi. Ricordare di fare clic su **Applica modifiche** al termine delle modifiche dei campi per una determinata tabella in modo che le modifiche vengano salvate. 

### <a name="exposing-custom-fields-on-data-entities"></a>Esposizione di campi personalizzati in entità di dati
Potrebbe anche essere importante consentire ai campi personalizzati di essere visibili sulle entità dati. Le entità dati sono utilizzate nella funzionalità [Apri in Office](../../dev-itpro/office-integration/office-integration.md), nonché per gli scenari di importazione / esportazione dei dati.  

Seguire questi passaggi per esporre un campo personalizzato in un'entità di dati: 
1.   Selezionare il campo personalizzato nel modulo **Campi personalizzati**. 
2.   Espandere l'area **Entità** per visualizzare l'insieme di entità rilevanti.  
3.   Fare clic sul pulsante **Modifica**.
4.   Modificare il campo **Abilitato** da selezionare per ciascuna entità che dovrà esporre questo campo.  
5.   Fare clic su **Applica modifiche** per salvare le selezioni.  

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a>Consentire la visualizzazione dei campi personalizzati in altre lingue
Poiché i campi personalizzati possono richiedere l'accesso da parte degli utenti in una varietà di lingue, la pagina **Campi personalizzati** fornisce un meccanismo che consente di tradurre in altre lingue l'etichetta e il testo della guida per un campo personalizzato.  

I seguenti passaggi descrivono il processo per la traduzione di campi personalizzati in altre lingue: 
1.   Selezionare il campo personalizzato nella pagina **Campi personalizzati**. 
2.   Selezionare il pulsante **Traduzioni** nel riquadro azioni. Verrà aperto un menu a discesa con le traduzioni esistenti per questo campo.
3.   Il menu a discesa **Lingua** mostra il set di lingue per cui le traduzioni sono già state fornite. 
     1.   Se si desidera modificare una traduzione esistente, selezionare la lingua desiderata dal menu e modificare i valori per l'etichetta e il testo della guida.  
     2.   In caso contrario, fare clic sul pulsante **Aggiungi lingua**, selezionare la lingua desiderata dal menu quindi immettere i valori di conversione per il testo guida e etichette.  
4.   Al termine, fare clic su **OK**.  

### <a name="deleting-custom-fields"></a>Eliminazione di campi personalizzati
In alcuni rari casi, si potrebbe decidere che un campo personalizzato non è più necessario. In questo caso, un amministratore di sistema può scegliere di eliminare il campo dalla pagina **Campi personalizzati**. Per fare ciò, assicurarsi che sia selezionato il campo corretto, fare clic su **Elimina**, quindi su **Sì** per confermare l'eliminazione e infine fare clic su **Applica modifiche**. 

> [!Note]
> Questa azione non può essere annullata e determinerà l'eliminazione definitiva dei dati associati al campo dal database. 

## <a name="appendix"></a>Appendice 
### <a name="who-can-create-custom-fields"></a>Chi può creare campi personalizzati?
Come salvaguardia per il sistema, solo gli amministratori di sistema possono creare campi personalizzati per impostazione predefinita. Tuttavia, gli utenti esperti, power user, che l'organizzazione ritiene necessari possono ottenere da un amministratore di sistema i diritti per creare campi personalizzati utilizzando il ruolo di sicurezza **Power user personalizzazione runtime**. Gli utenti senza questo ruolo di sicurezza non potranno creare campi personalizzati, ma potranno comunque vedere e interagire con i campi personalizzati aggiunti da altri utenti nel sistema.    

### <a name="what-tables-support-custom-fields"></a>Quali tabelle supportano i campi personalizzati?
Per motivi tecnici e di prestazioni, solo le tabelle che soddisfano le seguenti condizioni consentono attualmente l'aggiunta di campi personalizzati.

- La tabella deve essere contrassegnata come uno di questi gruppi: 
     -   Raggruppa
     -   WorksheetHeader
     -   Principale
     -   Varie
     -   Parametro
     -   Riferimento
     -   TransactionHeader
- La tabella non può estendere un'altra tabella.
- La tabella non può essere contrassegnata come tabella di sistema.
- La tabella non può essere una tabella temporanea.

