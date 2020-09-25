---
title: Automazione processo riscossioni
description: Questo argomento descrive il processo di impostazione delle strategie di processo di riscossione che identificano automaticamente le fatture del cliente che richiedono un promemoria tramite posta elettronica, un'attività di riscossione (come una telefonata) o una lettera di sollecito da inviare al cliente.
author: panolte
manager: AnnBe
ms.date: 08/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustomerCollectionManagerWorkspace
audience: Application User, IT Pro
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-08-26
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: db59bad2ed3caf38f22bd4d6059e57747d1d983f
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760585"
---
# <a name="collections-process-automation"></a>Automazione processo riscossioni

[!include [banner](../includes/banner.md)]

Questo argomento descrive il processo di impostazione delle strategie di processo di riscossione che identificano automaticamente le fatture del cliente che richiedono un promemoria tramite posta elettronica, un'attività di riscossione (come una telefonata) o una lettera di sollecito da inviare al cliente. 

Le organizzazioni dedicano una notevole quantità di tempo alla ricerca di report sui saldi con aging, conti clienti e fatture aperte per determinare quali clienti devono essere contattati in merito a una fattura aperta o al saldo del conto. Questa ricerca sottrae tempo a un agente di riscossione per comunicare con i clienti per riscuotere saldi scaduti o risolvere controversie sulle fatture. L'automazione del processo di riscossione consente di impostare un approccio basato sulla strategia al processo di riscossione. Ciò consente di applicare le attività di riscossione in modo coerente fornendo promemoria e-mail personalizzati o un processo programmato per l'invio di lettere di sollecito. 

## <a name="collections-process-setup"></a>Impostazione del processo di riscossione
Usare la pagina **Impostazione del processo di riscossione** (**Credito e riscossioni > Impostazione > Impostazione del processo di riscossione**) per creare un processo di riscossione automatico che pianifica le attività, invia messaggi di posta elettronica e crea e invia lettere di sollecito ai clienti. I passaggi del processo si basano sulla fattura aperta iniziale o meno recente. Ogni passaggio utilizza questa fattura per determinare quale comunicazione o attività deve avvenire per un cliente specifico.  

### <a name="process-hierarchy"></a>Gerarchia processo
Ogni pool di clienti può essere assegnato a una sola gerarchia di processi. Il grado gerarchico di questo passaggio identifica quale processo avrà la precedenza se un cliente è incluso in più di un pool a cui è assegnata una gerarchia di processo. L'ID pool determina quali clienti verranno assegnati al processo. 

I giorni non attivi vengono utilizzati per garantire che un cliente non venga contattato troppo frequentemente dal processo automatizzato.  Ad esempio, se i giorni non attivi sono impostati su due, un cliente non verrà contattato dal processo automatizzato per almeno due giorni, anche se la fattura iniziale originale è stata saldata per intero. 

Per escludere i clienti dall'automazione del processo se il saldo del conto o il saldo della fattura è inferiore a un valore definito, impostare il campo **Escludi dal processo** su **Sì** e inserire il valore dell'importo.

## <a name="process-details"></a>Dettagli processo
**Descrizione** viene utilizzato per identificare lo scopo o il nome del passaggio nella gerarchia.

**Tipo di azione** definisce se il passaggio crea un'attività, invia un'e-mail o crea una lettera di sollecito.

**Documento aziendale** definisce il modello utilizzato per creare il tipo di azione.  Può essere un modello di attività, un modello di e-mail o una lettera di sollecito per cliente. 

I tipi di azione possono essere creati prima o dopo la data di scadenza della fattura, in base all'impostazione visualizzata nella colonna **Giorni in relazione alla data di scadenza della fattura**.

Quando si seleziona il tipo di azione e-mail, il destinatario viene utilizzato per definire se si tratta di un cliente, un gruppo di vendita o un agente di recupero crediti. Il valore nel campo **Contatto per scopo commerciale** determina quindi quale contatto dall'account di quel cliente riceve la comunicazione.

## <a name="business-document-details"></a>Dettagli del documento aziendale
I dettagli del documento aziendale variano in base al tipo di azione selezionato nei dettagli del processo.  Quando il tipo di azione è un'attività, verranno visualizzati i dettagli del modello attività.  Questi dettagli includono il nome del modello attività, il tipo di attività che verrà creata, lo scopo dell'attività, il numero di giorni pianificati per completare l'attività e i dettagli dell'attività.  Questa attività si collegherà quindi alla fattura iniziale che comunica al destinatario l'azione necessaria per completare l'attività.

Se il tipo di azione è un'e-mail nei dettagli del processo, questa sezione conterrà due schede dettaglio.  La prima viene utilizzata per definire l'ID modello, la descrizione e-mail, la lingua predefinita, il nome utente che verrà assegnato ai messaggi e-mail inviati automaticamente e l'indirizzo e-mail del mittente associato. La seconda consentirà di creare il corpo dell'email dopo che i valori dei campi **Lingua** e **Oggetto** vengono salvati selezionando **Modifica**.  Si aprirà una finestra che consente di caricare il contenuto HTML. È anche possibile digitare il messaggio creato manualmente nella casella in basso a sinistra della finestra.  

> [!Note]
> È possibile salvare un'e-mail di Outlook con il corpo della comunicazione desiderato in formato HTML. Questo corpo può quindi essere caricato per implementare il modello. <br> <br> Se è selezionato il tipo di azione della lettera di sollecito, non ci sarà una sezione dei dettagli del documento commerciale nel modulo di configurazione.


## <a name="fasttab-reference"></a>Riferimento scheda dettaglio
Le seguenti tabelle elencano le pagine e i campi da cui è possibile accedere alle schede dettaglio specificate, insieme a una descrizione delle informazioni in quella scheda. 

### <a name="process-hierarchy"></a>Gerarchia processo

|     Pagina                                                  |     Campo                         |     descrizione                           |
| --------------------------------------------------------  |-------------------------------    |---------------------------------------    |
|     Impostazione del processo di riscossione <br> Automazione del processo       |                                   |     Creare e gestire i processi di riscossione in base alle assegnazioni del pool di clienti.                                                                                                                             |
|     Impostazione del processo di riscossione <br> Automazione del processo       |     Hierarchy                     |     Definisce la priorità dell'automazione del processo per assegnare un cliente se appartiene a più pool.                                                                                                   |
|     Impostazione del processo di riscossione <br> Automazione del processo       |     ID pool                       |     Query che definiscono un gruppo di record cliente.                                                                                                                                                        |
|     Impostazione del processo di riscossione <br> Automazione del processo       |     Giorni di inattività                    |     Limitare la frequenza con cui è possibile completare una fase del processo. Ad esempio, se vengono impostati due giorni di inattività, la fase di elaborazione successiva non si verificherà per almeno due giorni se la fattura iniziale cambia.     |
|     Impostazione del processo di riscossione <br> Automazione del processo       |     Escludi dal processo        |     Selezionando **Saldo di aging del cliente inferiore a** o **Importo della fattura inferiore a** si esclude un cliente dall'automazione del processo se i criteri di valore non sono soddisfatti.                                   |

### <a name="process-details"></a>Dettagli processo
|     Pagina                                                  |     Campo                                         |      descrizione                  |
|--------------------------------------------------------   |-----------------------------------------------    |----------------------------   |
|     Impostazione del processo di riscossione <br> Automazione del processo       |                                                   |     Definire i passaggi effettuati in base alla fattura iniziale.                                                                                                |
|                                                           |     descrizione                                   |     Campo di testo libero utilizzato per fornire un nome e/o una descrizione del passaggio.                                                                           |
|                                                           |     Tipo di azione                                   |     Attività, e-mail o lettera di sollecito che verrà creata dalla fase del processo.                                                                     |
|                                                           |     Documento aziendale                           |     Definisce il modello attività o e-mail utilizzato durante la fase del processo.                                                                        |
|                                                           |     Quando                                          |     Definisce se la fase del processo si verificherà prima o dopo la data di scadenza della fattura iniziale insieme al campo **Giorni in relazione alla data di scadenza della fattura**.        |
|                                                           |     Giorni in relazione alla data di scadenza fattura        |     Insieme al campo **Quando** identifica la tempistica della fase di processo.                                                                          |
|                                                           |     Destinatario                                     |     Identifica se verrà inviata un'e-mail a un cliente, un gruppo di vendita o un agente di riscossione.                                                   |
|                                                           |     Contatto per scopo aziendale                    |     Determina quale indirizzo e-mail del destinatario viene utilizzato nelle comunicazioni e-mail.                                                                                 |

### <a name="business-process-activity-template-details"></a>Dettagli del modello attività del processo aziendale 
|     Pagina                                                  |     Campo                     |      descrizione                  |
|--------------------------------------------------------   |----------------------------   |-------------------------  |
|     Impostazione del processo di riscossione <br> Automazione del processo       |                               |     Sezione del processo di impostazione che identifica i dettagli del modello attività.                                                                      |
|     Impostazione del processo di riscossione <br> Automazione del processo       |     Modello attività       |     Identifica il tipo, lo scopo, il numero di giorni da completare e fornisce dettagli sull'attività che verrà creata durante una fase del processo dell'attività.       |

### <a name="business-document-email-template-details"></a>Dettagli modello di posta elettronica per documento aziendale 
|     Pagina                                                  |     Campo     |      descrizione                  |
|--------------------------------------------------------   |-------------- |-----------------------------  |
|     Impostazione del processo di riscossione <br> Automazione del processo       |               |     Identifica la descrizione dell'e-mail, la lingua predefinita, il nome del mittente e l'indirizzo di posta elettronica che verranno creati durante una fase del processo di posta elettronica.        |


### <a name="collections-history"></a>Storico riscossioni 
|     Pagina                              |     Campo     |      descrizione                                                          |
|------------------------------------   |-------------- |---------------------------------------------------------------------  |
|     Impostazione del processo di riscossione       |               |     Visualizzare la cronologia recente per la gerarchia di processo selezionata.     |

### <a name="collection-process-assignment"></a>Assegnazione del processo di riscossione
|     Pagina                              |     Campo     |      descrizione                                                  |
|------------------------------------   |-------------- |-----------------------------------------------------------    |
|     Impostazione del processo di riscossione       |               |     Visualizzare i clienti assegnati a un processo di riscossione.  
|     Assegnazione manuale               |               |     Visualizzare i clienti che sono stati assegnati manualmente a un processo o selezionare i clienti da assegnare a un processo. |
|     Anteprima assegnazione del processo      |               |     Visualizzare in anteprima i clienti che verranno assegnati a una strategia quando viene eseguita.   |
|     Anteprima assegnazione del cliente     |               |     Visualizzare la strategia assegnata a un cliente specifico.    |
 
### <a name="parameters"></a>Parametri
|     Pagina                                                                  |     Campo                                             |      descrizione                              |
|-------------------------------------------------------------------------- |------------------------------------------------------ |-------------------------------------  |
|     Parametri contabilità clienti > Automazione del processo di riscossione     |     Percentuale di clienti per attività batch          |     Impostazione per determinare il numero di attività batch per processo di automazione.                                          |
|     Parametri contabilità clienti > Automazione del processo di riscossione     |     Registra lettere di sollecito automaticamente           |     I tipi di azione lettera di sollecito pubblicheranno la lettera durante l'automazione.                                      |
|     Parametri contabilità clienti > Automazione del processo di riscossione     |     Creare attività per l'automazione                |     Creare e chiudere le attività per i tipi di azione non attività per visualizzare tutti i passaggi automatizzati eseguiti su un account.        |
|     Parametri contabilità clienti > Automazione del processo di riscossione     |     Giorni per la conservazione dell'automazione del processo di riscossione     |     Definisce il numero di giorni in cui viene archiviata la cronologia delle riscossioni.                                                       |
