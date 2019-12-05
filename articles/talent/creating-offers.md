---
title: Creare, approvare e firmare le offerte in Attract
description: Questo argomento descrive come creare, approvare e firmare un'offerta per un candidato tramite Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 02/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-19
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: dee545b6ca5d2791dea6609b4e1b25eba128f8b7
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832909"
---
# <a name="create-approve-and-sign-offers-in-attract"></a>Creare, approvare e firmare le offerte in Attract

[!include [banner](includes/banner.md)]

In molti casi, preparare un pacchetto di offerta per un candidato deve essere un processo molto veloce.
Utilizzando i modelli configurati dall'amministratore di Attract si riduce il tempo e le risorse necessarie ai creatori di offerte per preparare e inviare offerte a un candidato.

## <a name="create-an-offer"></a>Creare un'offerta

Quando l'app Gestione offerte è abilitata, qualsiasi utente con il ruolo di responsabile assunzioni o selezionatore può preparare un pacchetto di offerta per il candidato. Per la preparazione all'offerta, effettuare la procedura seguente.

1.  Accedere alla mansione e alla domanda di lavoro del candidato per cui si sta creando l'offerta.

1.  Passare a **Fase dell'offerta** e fare clic su **Prepara offerta**.

    Si verrà reindirizzati all'app Offerta in cui è possibile visualizzare il candidato con stato **Nuovo**. È inoltre possibile visualizzare altre offerte a cui si sta contribuendo come creatore o approvatore.

1.  Fare clic su **Prepara offerta**. 
    
    Vedrete una scelta di diversi pacchetti di offerta che sono stati resi disponibili dall'amministratore.

1.  Selezionare un pacchetto e fare clic su **Fine** per avviare la preparazione dell'offerta.

    Il modello di pacchetto di offerta viene caricato con i dettagli corrispondenti della mansione e del candidato già inseriti nell'offerta.

1.  Tutti i segnaposto dei dati di offerta che fanno parte del pacchetto sono visibili nella pagina di destinazione. È possibile popolare tutti i valori del pacchetto in questa pagina.

    Nella pagina di destinazione, è inoltre possibile visualizzare tutti i modelli di documento di offerta che fanno parte del pacchetto di offerta.

1.  È ora possibile modificare il contenuto dell'offerta, a seconda di come il modello è stato configurato dall'amministratore.

1.  Se è necessario rimuovere i documenti contrassegnati come non obbligatori, è possibile effettuare questa operazione.

1. Quando tutti i segnaposto di dati di offerta vengono popolati, fare clic su **Salva** per salvare una bozza dell'offerta.

>[!NOTE]
> Dopo che una bozza viene salvata, è possibile eliminare la versione bozza di offerta o selezionare un nuovo modello di pacchetto, se necessario.


## <a name="approve-an-offer"></a>Approvare un'offerta

La maggior parte delle offerte deve passare attraverso un processo di approvazione per assicurarsi che l'offerta rispetti gli standard necessari. Se un'offerta non soddisfa gli standard, ad esempio se il creatore di offerta non seguisse le regole di dati di offerta e ignorasse i valori dell'offerta, il processo di approvazione sarà obbligatorio. Per inviare un'offerta per l'approvazione, effettuare la procedura seguente.

1.  Quando l'offerta è in uno stato di bozza, aggiungere gli approvatori nel **pannello degli approvatori**. 
    >[!NOTE]
    > I responsabili assunzioni vengono aggiunti come approvatori per impostazione predefinita. È possibile scegliere qualsiasi utente dell'organizzazione come approvatore dell'offerta.

1.  Se necessario, assegnare gli approvatori in un metodo di approvazione sequenziale o parallelo. Questa opzione è disponibile solo se è stata configurata come tale dall'amministratore.
    >[!NOTE]
    > Se il processo di approvazione è sequenziale, è possibile modificare la sequenza degli approvatori se necessario.

1.  Al termine di definire la catena di approvazione, sarà possibile modificare il contenuto del messaggio di posta elettronica di approvazione e quindi inviare la notifica agli approvatori. Fare clic su **Invia agli approvatori**.
    >[!NOTE]
    > Se l'offerta è non standard, è necessario immettere una motivazione.

1.  Se il creatore di offerta sceglie di ignorare un approvatore, possono immettere una nota e saltare all'approvatore successivo.

Gli approvatori riceveranno un messaggio di posta elettronica in cui viene chiesto di approvare l'offerta. Possono fare clic sul collegamento nel messaggio per aprire l'offerta, esaminare l'intero pacchetto di offerta e approvarla o reinviarla al creatore di offerta. Gli approvatori dell'offerta dovranno aggiungere una nota aggiuntiva se rifiutano il pacchetto di offerta per ulteriori modifiche. 

Nei casi in cui è presente una nuova versione dell'offerta creata prima dell'azione dell'approvatore, quest'ultimo non potrà approvare o rifiutare l'offerta.

## <a name="offer-versioning"></a>Versioni dell'offerta 

Quando l'offerta è stata approvata o stata restituita per ulteriori modifiche, è possibile scegliere l'opzione **Abilita modifica** per creare una nuova versione dell'offerta. La nuova versione della offerta ha tutti i valori dei dati di offerta e l'elenco degli approvatori ripresi dall'ultima versione. 

Gli approvatori possono passare da una versione all'altra se le versioni erano condivise con loro per l'approvazione. Inoltre, un approvatore o il creatore di offerta può scegliere di eliminare una bozza di versione specifica dell'offerta per tornare allo stato precedente.


## <a name="send-an-offer-to-a-candidate"></a>Inviare un'offerta a un candidato 

Quando l'offerta viene salvata, approvato e pronta di essere inviata al candidato, scegliere **Invia al candidato**.

Esistono vari azioni che è possibile eseguire prima dell'invio dell'offerta al candidato.
-  È possibile visualizzare l'elenco dei documenti inclusi nel pacchetto di offerta che verrà inviato al candidato.

-  È possibile specificare una data di scadenza dell'offerta. I candidati devono accettare o rifiutare l'offerta prima della data di scadenza.  Il candidato riceverà un promemoria 48 ore prima della scadenza dell'offerta.

-  Possono esserci documenti aggiuntivi che si desidera includere nel processo di accettazione. Si ha la scelta di elencare il tipo di documento richiesto.

- Opzione Firma elettronica: sono disponibili due modi per collegare il provider di firma elettronica scelto. Andare a **Impostazioni utente** in **Offerta**, sotto **Connessioni** eseguire la connessione a **Adobe Sign** o **DocuSign**. In alternativa, verrà chiesto di collegare la pagina **Invia l'offerta al candidato** se la connessione non era ancora stabilita in base alle impostazioni utente. L'account di firma elettronica deve essere connesso una sola volta. La stessa licenza utente viene utilizzata per tutti i pacchetti di offerta che verranno spediti dallo stesso utente. 

### <a name="adobe-sign"></a>Adobe Sign
Se Adobe Sign è stato scelto come metodo di firma elettronica preferito, gli autori di offerte devono connettere la licenza Adobe Sign in questa fase. 

### <a name="docusign"></a>DocuSign
Se DocuSign è stato scelto come metodo di firma elettronica preferito, gli autori di offerte devono connettere la licenza DocuSign. Dopo l'accesso, l'account predefinito e le autorizzazioni associate al profilo DocuSign dell'utente sono connessi a Talent: Attract. 

-  È possibile visualizzare e modificare il modello di messaggio di posta elettronica se necessario.

Quando l'offerta è pronta e si sceglie **Invia al candidato**, il candidato riceverà un messaggio di posta elettronica indicante un'offerta è in attesa di revisione.

>[!NOTE]
> Se si utilizza il segno Adobe Sign o DocuSign e viene visualizzato un errore durante l'invio dell'offerta al candidato, disconnettere e riconnettere l'account dell'utente della firma elettronica da **Impostazioni utenti**. Se il problema persiste, contattare il proprio supporto utilizzando il collegamento **Segnalare un problema**.

## <a name="candidates-actions-after-receiving-an-offer"></a>Le azioni del candidato dopo aver ricevuto di offerta

Dopo che il candidato è stato notificato che un'offerta è stata condivisa, può fare clic sul collegamento nel messaggio per aprire il dashboard dell'applicazione e visualizzare l'offerta. Il dashboard mostra al candidato tutte le attività che deve ancora completare.

1.  Per visualizzare l'offerta e tutti i documenti correlati, il candidato deve fare clic su **Visualizza offerta**.

    I candidati possono anche scaricare il pacchetto di offerta in formato .zip.

1.  Per accettare l'offerta, candidati devono fare clic  su **Passa alla firma** per ogni documento che fa parte del pacchetto di offerta.

1.  Quando tutti i documenti sono stati firmati e accettati individualmente, il candidato deve scegliere di completare il processo di accettazione facendo clic su **Accetta offerta** nella parte superiore della pagina.

1.  Per rifiutare l'offerta, il candidato deve fare clic sul pulsante per  **rifiutare l'offerta** nella parte superiore della pagina, selezionare un motivo appropriato, aggiungere un commento in base alle esigenze e fare clic su **Rifiuta**.

1.  Dopo che ha accettato o rifiutato l'offerta, il candidato può continuare a restare nella visualizzazione di offerta o tornare al dashboard dell'applicazione.

1.  In presenza di altri documenti richiesti durante il processo di accettazione di offerta, il candidato deve scegliere di caricare i documenti in base alle esigenze e contrassegnarli con il tipo di documento richiesto.

1.  Il creatore di offerta verrà notificato quando tutti i documenti sono stati caricati e il pacchetto di offerta è stato firmato.


## <a name="withdrawing-an-offer"></a>Ritirare un'offerta

Un'offerta può essere ritirata a un candidato in qualsiasi momento per diversi motivi. 
1.  Ritirare l'offerta facendo clic sul pulsante con i puntini di sospensione (**…**) e fare clic su **Ritira questa offerta**. 

2. Un messaggio apparirà chiedente se il candidato è stato contattato sulla modifica di stato. Se il candidato non è stato ancora contattato, è possibile scegliere di inviare un messaggio di posta elettronica al candidato che lo informa di ulteriori azioni. 

   L'offerta non sarà più accessibile al candidato.


## <a name="closing-an-offer"></a>Chiusura di un'offerta 

Quando un'offerta è stata accettata, rifiutata o ritirata senza ulteriori azioni necessarie, è possibile chiudere l'offerta in modo che non sia possibile apportare ulteriori modifiche al pacchetto di offerta.
