---
title: Automazione processo riscossioni
description: Questo articolo descrive il processo di impostazione delle strategie di processo di riscossione che identificano automaticamente le fatture del cliente che richiedono un promemoria tramite posta elettronica, un'attività di riscossione o una lettera di sollecito da inviare al cliente.
author: JodiChristiansen
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9ec749db197b4d04ee2e99ac7a16f4f2120c6707
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946180"
---
# <a name="collections-process-automation"></a>Automazione processo riscossioni

[!include [banner](../includes/banner.md)]

Questo articolo descrive il processo di impostazione delle strategie di processo di riscossione che identificano automaticamente le fatture del cliente che richiedono un promemoria tramite posta elettronica, un'attività di riscossione (come una telefonata) o una lettera di sollecito da inviare al cliente. 

Le organizzazioni spesso dedicano molto tempo alla ricerca di report sui saldi con aging, conti clienti e fatture aperte per determinare quali clienti devono essere contattati in merito a una fattura aperta o al saldo del conto. Questa ricerca sottrae tempo a un agente di riscossione per comunicare con i clienti per riscuotere saldi scaduti o risolvere controversie sulle fatture. L'automazione del processo di riscossione consente di impostare un approccio basato sulla strategia al processo di riscossione. Ciò consente di applicare le attività di riscossione in modo coerente fornendo promemoria e-mail personalizzati o un processo programmato per l'invio di lettere di sollecito. 

## <a name="collections-process-setup"></a>Impostazione del processo di riscossione
Usare la pagina **Impostazione del processo di riscossione** (**Credito e riscossioni > Impostazione > Impostazione del processo di riscossione**) per creare un processo di riscossione automatico che pianifica le attività, invia messaggi di posta elettronica e crea e invia lettere di sollecito ai clienti. I passaggi del processo si basano sulla fattura aperta iniziale o meno recente. Ogni passaggio utilizza questa fattura per determinare quale comunicazione o attività deve avvenire per un cliente specifico.  

I team di recupero crediti in genere inviano un avviso anticipato relativo a ciascuna fattura in sospeso in modo che un cliente venga informato quando la fattura sta per scadere. L'opzione **Sollecito preleminare** può essere impostata per consentire l'esecuzione di un passaggio in ciascuna gerarchia di processo per ogni fattura man mano che la tempistica della fattura raggiunge tale passaggio.

### <a name="process-hierarchy"></a>Gerarchia di processo
Ogni pool di clienti può essere assegnato a una sola gerarchia di processi. Il grado gerarchico di questo passaggio identifica quale processo avrà la precedenza se un cliente è incluso in più di un pool a cui è assegnata una gerarchia di processo. L'ID pool determina quali clienti verranno assegnati al processo. Ogni gerarchia configurata può essere assegnata a un solo processo di automazione.

I giorni non attivi vengono utilizzati per garantire che un cliente non venga contattato troppo frequentemente dal processo automatizzato. Ad esempio, se i giorni non attivi sono impostati su due, un cliente non verrà contattato dal processo automatizzato per almeno due giorni, anche se la fattura iniziale originale è stata saldata per intero. 

Per escludere i clienti dall'automazione del processo se il saldo di aging del cliente o l'importo della fattura è inferiore a un valore definito, seleziona **Saldo di aging del cliente inferiore a** o **Importo della fattura inferiore a** nel campo **Escludi dal processo** e immetti il valore dell'importo.

Seleziona **Usa la previsione** per creare attività di riscossione utilizzando le previsioni di pagamento del cliente. Le attività create utilizzeranno il modello di attività da **Previsioni di pagamento** sulla pagina **Parametri contabilità clienti**, scheda **Automazione processo di riscossione**. 

### <a name="process-details"></a>Dettagli processo
Fai clic su **Nuovo** per aggiungere un nuovo dettaglio di processo alla gerarchia. La **Descrizione** viene utilizzata per identificare lo scopo o il nome del passaggio nella gerarchia. Seleziona il **Tipo di azione** per definire se il passaggio crea un'attività, invia un'e-mail o crea una lettera di sollecito. 

- Il **Documento aziendale** definisce il modello utilizzato per creare il tipo di azione. Può essere un modello di attività, un modello di e-mail o una lettera di sollecito inviata a ogni cliente. L'automazione del processo di riscossione crea solo lettere di sollecito per cliente, indipendentemente da come sono impostati altri parametri di riscossione.
- **Quando** definisce la fase del processo che si verifica prima o dopo la data di scadenza della fattura principale (più vecchia) e viene utilizzata insieme al numero visualizzato nella colonna **Giorni in relazione alla data di scadenza della fattura**. 
- Seleziona l'opzione **Sollecito preliminare** per creare un'azione per ogni fattura in un passaggio in una gerarchia di processo. Le azioni di sollecito preliminare in genere inviano un avviso anticipato relativo alle fatture in sospeso in modo che un cliente venga informato quando la fattura sta per scadere. Il sollecito preliminare può essere contrassegnato per una sola attività per gerarchia. Quando selezioni il tipo di azione e-mail, il destinatario viene utilizzato per definire se il messaggio e-mail viene inviato a un cliente, un gruppo di vendita o un agente di recupero crediti. 
- Il valore nel campo **Contatto per scopo commerciale** determina quindi quale contatto dall'account di quel cliente riceve la comunicazione.

### <a name="business-document-details"></a>Dettagli del documento aziendale
I dettagli del documento aziendale variano in base al tipo di azione selezionato nei dettagli del processo. Quando il tipo di azione è un'attività, verranno visualizzati i dettagli del modello attività. Questi dettagli includono il nome del modello attività, il tipo di attività che verrà creata, lo scopo dell'attività, il numero di giorni pianificati per completare l'attività e i dettagli dell'attività. Questa attività si collegherà quindi alla fattura iniziale che comunica al destinatario l'azione necessaria per completare l'attività.

Se il tipo di azione è un'e-mail nei dettagli del processo, questa sezione conterrà due schede dettaglio. La prima viene utilizzata per definire l'ID modello, la descrizione e-mail, la lingua predefinita, il nome utente che verrà assegnato ai messaggi e-mail inviati automaticamente e l'indirizzo e-mail del mittente associato. La seconda consentirà di creare il corpo dell'email dopo che i valori dei campi **Lingua** e **Oggetto** vengono salvati selezionando **Modifica**. Si aprirà una finestra che consente di caricare il contenuto HTML. 

> [!Note]
> Puoi salvare un messaggio e-mail di Outlook che contiene il testo del corpo della comunicazione in formato HTML. Quindi puoi caricare il contenuto del messaggio per implementare il modello. <br> <br> Se è selezionato il tipo di azione della lettera di sollecito, non ci sarà una sezione dei dettagli del documento commerciale nella pagina di configurazione.

Utilizza il pulsante **Cronologia processo riscossioni** per visualizzare la cronologia recente per la gerarchia dei processi selezionata. 

Fai clic sull'azione **Assegnazione processo riscossioni** per visualizzare i clienti assegnati a un processo di riscossione. Usa **Anteprima assegnazione cliente** per visualizzare la gerarchia assegnata a un cliente specifico. Usa **Anteprima assegnazione processo** per visualizzare in anteprima i clienti che verranno assegnati a una gerarchia quando viene eseguita. Fai clic su **Assegnazione manuale** per visualizzare i clienti che sono stati assegnati manualmente a un processo o selezionare i clienti da assegnare a un processo.

Fai clic sull'azione **Simulazione processo** per visualizzare in anteprima le azioni che verranno create se l'automazione del processo selezionata viene eseguita in questo momento. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
