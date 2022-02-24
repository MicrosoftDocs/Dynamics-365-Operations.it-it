---
title: Creare modelli di messaggio di posta elettronica in Attract
description: In questo argomento vengono fornite informazioni sui modelli di messaggio di posta elettronica che è possibile creare e utilizzare in Microsoft Dynamics 365 Talent - Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/19/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 55c12010cfd055ee6977f50e566b70f76a2e1682
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461598"
---
# <a name="create-email-templates-in-attract"></a>Creare modelli di messaggio di posta elettronica in Attract

[!include [banner](includes/banner.md)]

Utilizzando la raccolta di modelli di messaggio di posta elettronica, gli amministratori possono creare un tema e un marchio uniforme per tutti i messaggi di posta elettronica inviati tramite Microsoft Dynamics 365 Talent: Attract and Offer. Gli amministratori possono anche curare una raccolta di modelli di contenuto dei messaggi di posta elettronica che altri utenti possono utilizzare. Il team di assunzione può utilizzare questi modelli nel flusso di lavoro per inviare più efficientemente messaggi di posta elettronica. Alcuni messaggi di posta elettronica sono configurati per essere inviati automaticamente e il amministratore può utilizzare la raccolta di modelli di messaggio di posta elettronica per personalizzare il contenuto per tale posta elettronica.

> [!NOTE]
> Per utilizzare modelli di messaggio di posta elettronica, l'organizzazione deve avere il componente aggiuntivo per l'assunzione a livello globale.

## <a name="global-template-configurations"></a>Configurazioni di modello globali

Per creare un marchio coerente per tutte le comunicazioni via posta elettronica, un amministratore deve innanzitutto configurare l'intestazione e il piè di pagina globali per tutti i modelli di messaggio di posta elettronica. Nell'Interfaccia di amministrazione, nella scheda **Impostazioni del modello di messaggio di posta elettronica**, sezione **Intestazione**, un amministratore può caricare un'immagine da utilizzare come intestazione o banner per tutti i messaggi di posta elettronica. Immagine può essere costituita da un logo della società, una carta intestata, o altre immagini rappresentative. Si consiglia della larghezza sia compresa tra 25 e 800 pixel e l'altezza compreso tra 25 e 150 pixel, in quanto queste dimensioni sono ottimali per la maggior parte dei client di posta, ad esempio Microsoft Outlook. Immagine deve essere un file JPEG, JPG, PNG, o SVG e la dimensione del file deve essere inferiore a 1 megabyte (MB). Dopo che un'immagine verrà caricata, un'anteprima dell'intestazione viene generata e visualizzata. Se l'immagine di intestazione deve essere sostituita o rimossa, il amministratore può utilizzare l'opzione **Rimuovi** sopra l'anteprima.

Nella sezione **Piè di pagina**, il amministratore può fornire i collegamenti all'informativa sulla privacy per le comunicazioni e alle condizioni delle società. Questi collegamenti vengono incorporati in un piè di pagina generato automaticamente. Un'anteprima di questo piè di pagina verrà visualizzata. L'amministratore può anche scegliere una lingua particolare in cui i piè di pagina di posta elettronica verranno inviati come parte di tutti i messaggi di posta elettronica. La stessa configurazione di lingua verrà utilizzata anche per la tabella di riepilogo del colloquio. 

Assicurarsi di salvare le modifiche prima di chiudere l'Interfaccia di amministrazione.

> [!NOTE] 
> L'intestazione e il piè di pagina sono impostazioni globali per tutti i messaggi di posta elettronica. Di conseguenza, verranno visualizzati in tutti i messaggi di posta elettronica inviati tramite Attract. Se le impostazioni non sono configurate, l'intestazione e il piè di pagina non verranno inclusi in nessun messaggi di posta elettronica.

## <a name="email-template-library"></a>Raccolta di modelli di messaggio di posta elettronica 

Dopo che le configurazioni complessive del modello vengono impostate, l'amministratore può iniziare a creare e gestire i modelli per tutti i messaggi di posta elettronica inviati da Attract and Offer. La raccolta di modelli di messaggio di posta elettronica è disponibile solo per gli amministratori. Per aprire la raccolta, nel menu principale di navigazione, fare clic sulla scheda **Modelli di messaggio di posta elettronica**. La raccolta è categorizzata per le varie attività in Attract che richiedono l'invio di messaggi di posta elettronica, ad esempio programmazione, la valutazione, la creazione di mansioni e l'offerta. Il amministratore può selezionare un qualsiasi categoria per visualizzare tutti i tipi di messaggio di posta elettronica associati all'attività. Ad esempio, selezionare **Programmazione** per visualizzare i diversi tipi di posta elettronica inviati durante il processo di programmazione e tutti i modelli disponibili per ciascun tipo di messaggio di posta elettronica. Ogni sottosezione in una categoria rappresenta un tipo di messaggio di posta elettronica.

Alcuni tipi di posta elettronica possono avere più destinatari. Ad esempio, nella categoria **Programmazione**, i messaggi di posta elettronica inviati quando il riepilogo del programma di colloqui è necessario, vengono inviati sia ai candidati sia ai responsabili dei colloqui. Ogni sezione sono presenti due colonne principali: **Titolo modello** e **Destinatario**. Ogni riga di una sezione rappresenta un singolo modello per un tipo di posta elettronica. Inizialmente, un simbolo di blocco verrà visualizzato nella riga per ciascun modello. Il simbolo indica che il modello è il modello standard fornito con Attract e che non può essere eliminato. Per ogni modello, un amministratore può utilizzare il pulsante con i puntini di sospensione  (**...**) per duplicare il modello, per impostarlo come predefinito, o per eliminarlo. Quando un modello è impostato come predefinito, uno di due comportamenti può verificarsi. Il comportamento è indicato dal badge o i badge visualizzati nella riga relativa al modello:

- **Predefinito** - Il badge indica che il modello è il modello predefinito per il messaggio di posta elettronica inviato e che le informazioni vi verranno inserite quando un utente invia messaggi di posta elettronica di quel tipo specifico.
- **Predefinito** + **Invio automatico** - questa combinazione di badge indica che il modello è il modello attivo per i messaggi di posta elettronica generati dal sistema e inviati automaticamente.

Per modificare un modello, selezionare la riga e apportare le modifiche al modello.

> [!NOTE]
> Ogni destinatario di un tipo specifico di posta elettronica ha un modello predefinito. Tutti i modelli Attract standard sono impostato come modelli predefiniti finché l'amministratore non crea un nuovo modello per uno specifico tipo di posta elettronica e lo imposta come predefinito.

## <a name="create-a-template"></a>Creare un modello

Per creare un modello, nell'angolo superiore destro della raccolta di modelli di messaggio di posta elettronica, selezionare **+ Nuovo modello**. Per selezionare il tipo di posta elettronica per cui viene creato il modello, selezionare il destinatario, il processo e l'evento per cui il messaggio di posta elettronica dovrà essere inviato. Selezionare **Crea**.

Il modello viene aperto in visualizzazione di modifica ed è possibile denominare il modello. Ad esempio, se il modello serve ai candidati da università negli Stati Uniti, ma il contenuto verrà scritto in francese, è possibile specificare **Università\_Stati Uniti\_Francese** come titolo. Il titolo, la riga dell'oggetto e il contenuto del corpo per qualsiasi modello possono supportare le lingue oltre all'inglese.

Il campo **A** di un modello non può essere modificato, poiché è già stato selezionato il destinatario durante la fase di creazione del modello.

È possibile aggiungere altre persone come **Selezionatore** o **Responsabile assunzioni** nella riga in copia (Cc). Quando il messaggio viene inviato, questi ruoli vengono sostituiti automaticamente con gli utenti appropriati, in base al contesto della mansione.

La riga dell'oggetto e il contenuto del corpo supportano segnaposto. È possibile inserire segnaposto digitando **\#** quindi selezionando il segnaposto appropriato nell'elenco a discesa di completamento automatico. L'elenco dei segnaposto disponibili viene visualizzato a destra della pagina. Quando il messaggio viene inviato, i segnaposto vengono sostituiti automaticamente, in base al contesto della mansione e al destinatario. Ad esempio, un modello per un messaggio di posta elettronica da inviare ai candidati contiene il segnaposto \#{Candidate\_Name}. Quando il messaggio viene inviato a un candidato denominato Cameron, il segnaposto verranno sostituiti con il nome di Cameron.

L'editor del contenuto del corpo è un editor di testo avanzato che consente di scegliere stile e formato del testo. Consente anche di inserire i collegamenti ipertestuali e le ancore.

Dopo che un modello viene creata per uno specifico tipo di messaggio di posta elettronica, selezionare il pulsante con i puntini di sospensione (**...**) nella riga relativa al modello e impostarlo come predefinito.

## <a name="consume-templates"></a>Utilizzare modelli

Quando il team di assunzione invia un messaggio di posta elettronica, può utilizzare i modelli che un amministratore ha creato. Se più modelli sono stati creati per il messaggio di posta elettronica che un utente sta creando, un elenco a discesa appare nel flusso di lavoro di composizione nel messaggio. Il modello predefinito viene inserito automaticamente, ma l'utente può selezionare un altro modello.

> [!NOTE] 
> Per i messaggi di posta elettronica inviati automaticamente, più modelli possono essere creati. Tuttavia, solo un modello può essere impostato come modello attivo. Poiché questo processo viene attivato da eventi, solo l'amministratore può determinare il modello da utilizzare, in base alla combinazione di badge **Predefinito** e **Invio automatico** nella raccolta di modelli.
