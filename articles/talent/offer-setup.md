---
title: Impostare la gestione offerta in Attract
description: In questo argomento viene descritto come impostare le offerte in Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91a83afd5ce1627376685bcf612d6998ddbc02
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461628"
---
# <a name="set-up-offer-management-in-attract"></a>Impostare la gestione offerta in Attract

[!include [banner](includes/banner.md)]

Quando un candidato viene passato nella fase offerta in Dynamics 365 Talent: Attract, è necessario assicurarsi che le offerte possano essere create rapidamente per il candidato, essere approvate secondo le esigenze e essere inviate al candidato. Poiché la maggior parte delle offerte sono standard, è possibile crearle da modelli riutilizzabili. In Attract, tutte le offerte vengono presentate in un pacchetto di offerta, cioè una raccolta di uno o più documenti di offerta. 

Di seguito sono elencati tutti i passaggi che un amministratore di Attract deve seguire per impostare diversi modelli di pacchetti di offerta nell'ambito della funzionalità di gestione delle offerta in Attract. Gli utenti senza ruoli di amministratore non avranno accesso a tali funzionalità.

>[!NOTE]
> Le funzionalità di gestione delle offerte sono disponibili come parte del componente aggiuntivo per l'assunzione a livello globale.

## <a name="offer-data"></a>Dati dell'offerta 

I dati dell'offerta sono la più piccola unità nel modello di pacchetto di offerta. Un'offerta tipica è costituita da un testo standard e un insieme di valori. I set di valori sono le singole parti che potrebbero variare tra le offerte. Durante la creazione dell'offerta, l'aspetto più importante su cui il creatore di offerta può focalizzarsi è l'elenco dei segnaposto di dati dell'offerta presenti in un modello di pacchetto di offerta. Per impostare i dati di offerta, effettuare la procedura seguente.

1.  Andare a **Gestione offerte**.

1.  Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Dati dell'offerta**.

    >[!NOTE]
    > Nella pagina **Dati dell'offerta** si trovano le sezioni **Dettagli candidato** e **Dettagli mansione**. Attract fornisce alcuni segnaposto predefiniti per i dati di offerta.
    > 
    > Sono disponibili sezioni nella pagina per organizzare i diversi segnaposto di dati di offerta in gruppi logici. Queste sezioni possono facilitare la manutenzione dei dati di offerta e l'inserimento dei dati durante il processo di creazione di offerta.
    > 
    > Per creare un elenco di valori per un segnaposto, caricare un foglio di calcolo Excel con una colonna con il segnaposto come titolo della colonna e l'elenco delle opzioni nelle righe sottostanti. Se si fa riferimento allo stesso segnaposto in un altro set di regole dei dati, assicurarsi che abbiano un set comune di valori.
    
1.  Per creare una nuova sezione di dati dell'offerta, fare clic su **Aggiungere una sezione** e immettere un nome univoco per la sezione.

1.  Per aggiungere segnaposto di dati di offerta in una sezione, fare clic su **Aggiungi dati dell'offerta** e immettere un nome univoco per il segnaposto.

1.  Per modificare il nome della sezione, passare il mouse sul nome della sezione e aggiornare il nome.

1.  Per modificare il nome di un segnaposto di dati di offerta esistente, è innanzitutto necessario assicurarsi che il segnaposto non sia già parte di alcun modello. Quindi, passare il mouse sul nome del segnaposto di dati di oggerta e aggiornare il nome in base alle necessità.

1. Per eliminare un segnaposto di dati di offerta esistente, è innanzitutto necessario assicurarsi che il segnaposto non sia già parte di un altro modello. Quindi, passare con il mouse sul segnaposto e quando appare l'icona del cestino fare clic su tale icona per eliminare il segnaposto di dati di offerta.
    >[!NOTE]
    > È possibile vedere di quanti modelli un segnaposto di dati di offerta fa parte in dall'indicatore numerico accanto a ogni dato di offerta. 

1. Per eliminare una sezione, passare con il mouse sul suo nome. Se nessuno dei segnaposto di dati di offerta nella sezione appare in qualsiasi modello, è possibile fare clic sull'icona del cestino per eliminarla. 
    >[!NOTE]
    > L'eliminazione di una sezione implica anche l'eliminazione dei segnaposto di dati di offerta all'interno della sezione.

Dopo aver impostato i segnaposto di dati di offerta, è possibile utilizzarli in qualsiasi modello di documento. I segnaposto di dati di offerta non sono limitati a un modello specifico: lo stesso set può essere utilizzato in tutti i modelli.

## <a name="offer-data-rules"></a>Regole dati offerta

La maggior parte delle organizzazioni hanno regole per la creazione delle offerte. Ad esempio, un'organizzazione può richiedere che la massima retribuzione annuale offerta per una combinazione specifica di sede e livello di anzianità deve essere compresa in un determinato intervallo o che ci siano solo pochi valori possibili per il livello di offerta per il nuovo assunto. Attract attualmente supporta tutti questi tipi di regole di dati utilizzando un file CSV.

Per preparare il file CSV di regole dei dati, effettuare la procedura seguente.

1.  Determinare il segnaposto di dati di offerta per il set di regole. Ad esempio, **Salario annuale**.

1.  Identificare i valori dei segnaposto di dati di offerta dipendenti. Ad esempio, **Ubicazione mansione** e **Livello**.

1.  Specificare le colonne 1 e 2 come **Ubicazione mansione** e **Livello**.

1.  Per caricare un valore di intervallo, creare le colonne 3 e 4 **Salario annuale**. Per caricare un valore specifico anziché un intervallo, creare solo la colonna 3 **Salario annuale**.

1.  Popolare il file di Microsoft Excel in base ai ruoli richiesti.

1.  Assicurarsi che ogni riga sia una combinazione univoca di tutti i valori messi insieme.

1.  Salvare il file in formato CSV.

Per caricare il file di regole dei dati di offerta, effettuare la procedura seguente.

1.  Andare a **Gestione offerte**.

1.  Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Regole dati offerta**.

1.  Fare clic su **Nuovo set di dati** per visualizzare la finestra di dialogo **Carica**.

1.  Specificare un nome univoco per il set di regole quindi caricare il file salvato CSV.

1.  Fare clic su **Aggiungi**.
    Il set di regole verrà elaborato in background e si riceverà una notifica nell'app e tramite posta elettronica una volta completata.

    Verrà notificato se sono presenti errori durante l'elaborazione del caricamento. È possibile scaricare il registro errori, correggere il file e caricarlo ancora.

1.  Utilizzare l'opzione del pulsante con i puntini di sospensione (**…**) se si desidera scaricare il set di regole e aggiornare il set di valori. Dopo l'aggiornamento, è possibile caricare di nuovo il file.

1.  È possibile eliminare un set di regole caricato corrente se il segnaposto definito non è utilizzato in un altro modello di documento.

>[!NOTE]
> - Ogni segnaposto può essere associato a un solo insieme univoco di colonne da cui dipende. Ad esempio, se **Salario annuale** dipende da **Ubicazione mansione** e **Livello**, non è possibile caricare un altro set di regole in cui **Salario annuale** dipende da un diverso set di colonne.

> - È possibile scaricare set di regole dei dati di offerta di esempio nella scheda **Esempi** della pagina **Regole dati offerta**.

> - Quando un creatore di offerte ignora i valori suggeriti dalle regole dei dati di offerta, l'offerta viene contrassegnata come non standard e il flusso di lavoro di approvazione di offerta sarà obbligatorio.

## <a name="document-templates"></a>Modelli di documento

Un modello di documento di offerta può agevolare agli amministratori nella creazione delle lettere di offerta. Il modello di documento di offerta è una combinazione di testo che fa parte dell'offerta nonché i segnaposto definiti dei dati di offerta. 

Per creare un modello di documento di offerta, effettuare la procedura seguente.

1.  Andare a **Gestione offerte**.

1.  Espandere la sezione **Raccolta** nel pannello di navigazione sinistro, quindi passare a **Modelli**.

    Nella pagina **Modelli** viene visualizzato un elenco dei modelli di documento già definiti.

1.  Per creare un nuovo modello di documento, fare clic su **Nuovo modello**.

1.  Immettere un nome univoco per il modello e fare clic su **Crea**.

1.  Utilizzare l'editor di testo avanzato per inserire o modificare il contenuto del documento di offerta. È possibile inserire tabelle, immagini e collegamenti ipertestuali utilizzando le opzioni disponibili nella parte superiore dell'editor di testo.

1.  È possibile inserire segnaposto di dati di offerta nel documento di modello di offerta in questo modi:

    - Trascinando la selezione dal riquadro a destra.

    - Posizionando direttamente l'hashtag del segnaposto di dati di offerta. Digitando **\#** quindi iniziare a immettere il nome del segnaposto di dati di offerta. Le opzioni appariranno nell'elenco a discesa. Fare clic o premere **INVIO** per inserire il segnaposto di dati di offerta.

    >[!NOTE]
    > - Per associare un segnaposto al modello di documento di offerta senza esporre il relativo valore al candidato, passare il mouse sul segnaposto di dati di offerta e fare clic sull'icona **Blocca**. Questo sposterà il segnaposto nella sezione **Dati dell'offerta aggiunti** del modello di documento di offerta. Per sbloccare, seguire la stessa procedura ma fare clic su **Sblocca** nell'elenco dei segnaposto di dati di offerta.

    > - Per visualizzare l'elenco dei segnaposto di dati di offerta attivi, passare alla scheda **Attivo** del riquadro a destra.

    > - Se si inserisce un segnaposto basato su un set di regole dei dati di offerta, è possibile visualizzare la dipendenza di tale segnaposto da altri valori.

    > - In alternativa, è possibile **Importare** il contenuto da un file .docx nel computer locale e modificarlo in base alle esigenze. In tal modo non sarà necessario digitare tutto il contenuto nell'editor.

1. Per visualizzare l'anteprima del documento di offerta, utilizzare l'opzione **Anteprima** nella parte superiore della pagina.

1. Per determinare se un creatore di offerte può modificare il contenuto del documento di offerta, utilizzare l'opzione **Gestisci autorizzazione** nella parte superiore della pagina. Se si desidera che il creatore di offerta possa solo inserire i valori dei segnaposto e non modificare il testo, impostare il valore dell'autorizzazione su **No**.

1. Scegliere **Salva** per salvare l'avanzamento. Il modello verrà salvato con stato di bozza.

1. Per finalizzare e contrassegnare il documento come pubblicato, fare clic su **Fine**.

1. È possibile visualizzare quali modelli di documento sono attualmente attivi, in modalità bozza e archiviati e non più in uso nell'esperienza di destinazione della raccolta dei modelli di documento.

>[!NOTE]
> È possibile eliminare qualsiasi modello di documento di offerta che non fa parte di un modello di pacchetto di offerta esistente.


## <a name="offer-package-templates"></a>Modelli di pacchetti di offerta

I pacchetti di offerta sono gli elementi di offerta condivisi con il candidato e sono costituiti da una combinazione di uno o più modelli di documento di offerta. Per creare un pacchetto di offerta, effettuare la procedura seguente.

1.  Andare a **Gestione offerte**.

1.  Passare a **Pacchetti** dal pannello di navigazione sinistro.

    Un elenco dei modelli di pacchetto attivi disponibili per i creatori di offerta viene visualizzato.

1.  Per creare un nuovo pacchetto di offerta, scegliere **Nuovo pacchetto**.

1.  Immettere un nome univoco e fare clic su **Crea**.

1.  Fare clic su **Aggiungi modello**.

    >[!NOTE]
    > - È possibile creare un nuovo modello o sceglierne uno esistente.

    > - Se si sceglie di aggiungere un modello esistente, verificare che il modello di documento di offerta sia stato salvato, finalizzato e contrassegnato come attivo.
    
    > - È possibile scegliere tutti i modelli di documento desiderati. 
    
1.  Fare clic su **Fatto** per tornare **Gestione pacchetti**.

    È possibile configurare la sequenza dei documenti e anche contrassegnare se il documento di offerta specifico viene richiesto durante la creazione di offerta. Il creatore di offerta avrà una opzione per eliminare i documenti contrassegnati **Non obbligatorio**.

1. Per salvare il modello di pacchetto di offerta in modo che sia utilizzabile da tutti i creatori di offerta, clic su **Salva e pubblica**.

   Per visualizzare le bozze di modelli di pacchetto dell'offerta, passare alla scheda **Bozze**. Se si apportano modifiche al modello di pacchetto di offerta, deve essere salvato e ripubblicato.

## <a name="configure-an-offer-process"></a>Configurare un processo di offerta

Diverse parti del processo di creazione dell'offerta possono essere configurate da un amministratore di Attract.

- **Approvazioni di offerta** - Scegliere se le approvazioni di offerta sono obbligatorie affinché l'offerta possa essere inviata al candidato. In qualità di amministratore, è possibile decidere se tutte le approvazioni di offerta accadranno in modo sequenziale o in un flusso di lavoro di approvazione parallela. È inoltre possibile rendere obbligatorio che gli approvatori di offerta devono aggiungere un commento all'approvazione di offerta. Le approvazioni di offerta sono obbligatorie per tutte le offerte non standard.

- **Esperienza dell'offerta del candidato** - Come amministratore, è possibile scegliere di impostare se tutte le offerte abbiano una data di scadenza e in caso affermativo, quale deve essere l'offset predefinito per la data di scadenza. È inoltre possibile configurare se i candidati possono rifiutare un'offerta.

- **Firme elettroniche** - Come amministratore, è inoltre possibile selezionare il metodo che i candidati possono utilizzare per firmare le offerte.
    - Adobe Sign - Tutti i pacchetti di offerta saranno inviati e firmati via Adobe Sign. Ogni creatore di offerte che pubblica l'offerta deve avere il relativo account Adobe Sign collegato a Attract. Per le licenze di Adobe Sign e una versione di prova gratuita, visitare la pagina a questo [collegamento](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).

    - DocuSign - Tutti i pacchetti di offerta saranno inviati e firmati via DocuSign. Ogni creatore di offerte che pubblica l'offerta deve avere il relativo account DocuSign collegato a Attract. 
    
    - ESign – Questa è l'opzione predefinita, dove l'utente può firmare un'offerta digitando il relativo nome e le iniziali.


Per ulteriori informazioni sul processo di creazione dell'offerta, vedere [Creare, approvare e firmare le offerte](./creating-offers.md).
