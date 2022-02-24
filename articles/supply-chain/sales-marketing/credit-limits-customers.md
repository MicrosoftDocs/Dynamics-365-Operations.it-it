---
title: Limiti di credito per i clienti
description: In questo articolo viene fornita una panoramica sull'utilizzo dei limiti di credito in Dynamics 365 Supply Chain Management.
author: omulvad
manager: tfehr
ms.date: 09/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e98203f03f10b3a7c530cb91211df2af025710dc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431244"
---
# <a name="credit-limits-for-customers"></a>Limiti di credito per i clienti

[!include [banner](../includes/banner.md)]

Impostare un limite di credito consente di specificare l'importo massimo di credito da estendere ai clienti. Se un limite di credito viene specificato, viene verificato automaticamente quando un utente tenta di aggiornare un documento. Se il limite di credito viene superato, viene visualizzato un messaggio all'utente. In questo articolo viene fornita una panoramica sull'utilizzo dei limiti di credito e le risposte alle domande seguenti:

-   Per quali documenti e processi posso verificare i limiti di credito?

-   Dove configuro la modalità in cui il credito rimanente del cliente viene calcolato?

-   Dove sono utilizzate le informazioni sul credito rimanente di un cliente?

-   Dove specifico se l'identificazione è necessaria per estendere il credito a un cliente e se l'importo del limite di credito richiede identificazione?

-   Dove specifico se visualizzare un avviso o un errore qualora il limite di credito venga superato?

-   Come specifico il limite di credito per un cliente specifico?

-   Come verifico manualmente i limiti di credito per gli ordini cliente?

**Per quali documenti e processi posso verificare i limiti di credito?**

Utilizzare il modulo **Parametri contabilità clienti** per specificare i documenti di cui verificare i limiti di credito. È necessario essere membri del ruolo di sicurezza Amministratore sistema (-SYSADMIN-) per apportare modifiche nel modulo. È possibile verificare i limiti di credito per i seguenti documenti e processi:

-   Fatture per gli ordini cliente, quando si registrano le fatture

-   Documenti di trasporto per gli ordini cliente, quando si aggiornano i documenti di trasporto

-   Ordini cliente, quando si aggiungono righe nel modulo **Ordine cliente**

-   Ordini cliente, quando vengono creati tramite un servizio

-   Fatture a testo libero, quando si registrano le fatture

I limiti di credito vengono automaticamente verificati se una delle seguenti opzioni è impostata:

-   Nel modulo **Parametri contabilità clienti**, il campo **Tipo di limite di credito** è impostato su **Nessuno**. I limiti di credito sono verificati per tutti i clienti.

-   Nel modulo **Parametri contabilità clienti**, il campo **Tipo di limite di credito** è impostato su **Nessuno** ma **Limite di credito obbligatorio** è selezionato per un cliente nel modulo **Clienti**. I limiti di credito sono verificati solo per clienti specifici.

Per verificare i limiti di credito per i seguenti documenti, è necessario specificare le impostazioni aggiuntive.

|    Documento                                    |    Impostazione aggiuntiva                                                                                                             |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------|
|    Fattura a testo libero                         |    Nel modulo Parametri contabilità clienti, nell'area Posizione finanziaria, selezionare Verifica limite di credito nella fattura a testo libero.     |
|    Ordine cliente (immesso manualmente)            |    Nel modulo Parametri contabilità clienti, nell'area Posizione finanziaria, selezionare Verifica limite di credito in ordini cliente.           |
|    Ordine cliente (ricevuto elettronicamente)     |    Nel modulo Parametri contabilità clienti, nell'area AIF, selezionare Verifica limite di credito per ordini cliente.                     |

**Dove configuro la modalità in cui il credito rimanente di un cliente viene calcolato?**

È possibile configurare Dynamics 365 per calcolare il credito rimanente di un cliente in uno dei seguenti modi:

-   Confrontare il limite di credito rispetto al saldo cliente.

-   Confrontare il limite di credito rispetto al saldo e agli importi del documento di trasporto del cliente.

-   Confrontare il limite di credito rispetto al saldo cliente e tutte le attività di transazione aperte. Ciò include gli importi del documento di trasporto e gli importi dell'ordine cliente.

Utilizzare il modulo **Parametri contabilità clienti** per specificare le informazioni per il confronto. È necessario essere membri del ruolo di sicurezza Amministratore sistema (-SYSADMIN-) per apportare modifiche nel modulo. Nel campo **Tipo di limite di credito**, selezionare se effettuare i controlli del limite di credito e quali informazioni sulle transazioni includere quando il limite di credito viene verificato. Scegliere una delle seguenti opzioni:

-   **Nessuno**: limiti di credito non vengono controllati. È possibile ignorare questa opzione per un cliente specifico selezionando la casella di controllo **Limite di credito obbligatorio** nel modulo **Clienti**. In questo caso, il limite di credito viene verificato rispetto al saldo cliente.

-   **Saldo**: il limite di credito viene verificato rispetto al saldo cliente.

-   **Saldo+Documento di trasporto o entrata prodotti**: il limite di credito viene verificato rispetto al saldo e alle consegne del cliente.

-   **Saldo+Tutto**: la verifica del limite di credito viene eseguita in base al saldo del cliente, alle consegne e agli ordini aperti.

**Dove sono utilizzate le informazioni sul credito rimanente di un cliente?**

Le informazioni sull'importo in Avere rimanente e del saldo del cliente vengono calcolate e salvate quando si crea lo snapshot di aging e sono visualizzate nel modulo **Riscossioni**. Gli importi visualizzati nel modulo **Riscossioni** potrebbero non includere tutte le attività di transazione fino a che non viene creato un nuovo snapshot di aging. Per ulteriori informazioni, vedere [Riscossioni e crediti in Contabilità clienti](https://technet.microsoft.com/library/hh209221.aspx).

In base ai documenti selezionati, le informazioni sull'importo in Avere rimanente e del saldo del cliente vengono calcolati quando gli ordini cliente, i documenti di trasporto e le fatture cliente vengono aggiornati. Se l'importo del documento su cui si sta lavorando causasse il superamento del limite di credito, viene visualizzato un messaggio.

**Dove specifico se l'identificazione è necessaria per estendere il credito a un cliente e se anche il limite di credito richiede identificazione?**

Utilizzare il modulo **Parametri contabilità clienti** per specificare se richiedere l'identificazione e se l'importo del limite di credito richiede identificazione.
È necessario essere membri del ruolo di sicurezza Amministratore sistema (-SYSADMIN-) per apportare modifiche nel modulo.

|    Campo                                    |    descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|---------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Richiedi numero identificazione con credito     |    Selezionare il tipo di identificazione da immettere per i clienti ai quali la propria persona giuridica concede credito. L'opzione selezionata in questo campo determina quali informazioni sono necessarie nei campi di identificazione del modulo Clienti e quando.        No: non è necessario immettere un'identificazione indipendentemente dal limite di credito accordato al cliente.     Sì: è        necessario immettere il numero di patente o un'altra identificazione        se il limite di credito accordato al cliente è maggiore o        uguale a zero.     Limite minimo: è        necessario immettere un numero di patente o un'altra identificazione        se il limite di credito accordato al cliente è maggiore        o uguale al limite immesso nel campo Limite di questo        modulo.        |
|    Limite                                    |    Immettere il limite di credito per il quale i clienti devono specificare il numero di patente o un'altra identificazione.    Digitare ad esempio 2000 per rendere obbligatoria l'immissione di un numero di identificazione, ad esempio il numero di patente, per i clienti con un limite di credito pari o superiore a 2000.    Questo campo è disponibile se nel campo Richiedi numero identificazione con credito è selezionata l'opzione Limite minimo.                                                                                                                                                                                                                                                                                                                                                                                                                                         |

**Dove specifico se visualizzare un avviso o un errore qualora il limite di credito venga superato?**

Utilizzare il modulo **Parametri contabilità clienti** per specificare se visualizzare un avviso o un errore qualora il limite di credito venga superato. Questo errore o avviso viene visualizzato quando un utente immette o registra informazioni oppure viene incluso in un registro se i documenti vengono elaborati da un servizio elettronico. È necessario essere membri del ruolo di sicurezza Amministratore sistema (-SYSADMIN-) per apportare modifiche nel modulo.

|    Campo                                                               |    descrizione                                                                                                                                                                                                                                                                                                                                                                                        |
|------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|    Notifica in caso di superamento limite di credito (nell'area Posizione finanziaria)     |    Selezionare la modalità di visualizzazione dei messaggi sui limiti di credito superati. Selezionare una delle opzioni descritte di seguito.        Errore: viene        visualizzato un messaggio di errore. In genere si interrompe l'operazione corrente e        il conflitto deve essere risolto prima che il processo possa continuare.     Avviso: viene        visualizzato un messaggio di avviso, ma il processo può continuare.                     |
|    Notifica in caso di superamento limite di credito (nell'area AIF)               |    Selezionare la modalità di invio in un registro dei messaggi che notificano il superamento dei limiti di credito. Selezionare una delle opzioni descritte di seguito.        Errore: un        messaggio di errore viene visualizzato nel modulo Eccezioni e il        documento non viene elaborato fino alla risoluzione dell'errore.     Avviso: un        messaggio di avviso viene visualizzato nel modulo Eccezioni, ma il        processo può continuare.        |

**Come specifico l'importo del limite di credito per un cliente specifico?**

Utilizzare il modulo **Clienti** per specificare l'importo del limite di credito per un cliente specifico. È necessario essere membri di un ruolo di sicurezza con il compito Gestisci dati master cliente (CustCustomersMaintain) assegnato per apportare modifiche nel modulo.

1.  Fare clic su **Contabilità clienti** \> **Comune** \> **Clienti** \> **Tutti i clienti**. Fare doppio clic su un conto cliente.

2.  Nel modulo **Clienti**, nel riquadro azioni, fare clic su **Modifica**.

3.  Immettere un importo in valuta nel campo **Limite di credito**. Il valore deve essere maggiore di zero (0) e verrà utilizzato come importo del limite di credito.

4.  Se necessario, immettere un numero di licenza o un'altra identificazione nel campo **Codice fiscale/Partita IVA**.

> [!NOTE]
> In genere, un tipo di limite di credito è selezionato nel modulo **Parametetri contabilità clienti**. Tuttavia, se il tipo di limite di credito è impostato su **Nessuno**, è necessario selezionare anche la casella di controllo **Limite di credito obbligatorio** nel modulo **Clienti** per verificare il limite di credito del cliente in base al saldo del cliente. Per ulteriori informazioni sui tipi di limite di credito, vedere "Per quali documenti e processi posso verificare i limiti di credito?" in questo argomento. 

**Come verifico manualmente i limiti di credito per gli ordini cliente?**

Talvolta, potrebbe essere necessario verificare manualmente il limite di credito di un cliente. Ad esempio, è possibile verificare manualmente il limite di credito di un cliente prima di iniziare a immettere un ordine cliente. È possibile utilizzare il modulo **Ordine cliente** per controllare manualmente i limiti di credito. È necessario essere membri di un ruolo di sicurezza con il compito Gestisci ordine cliente (SalesOrderMaintain) assegnato per apportare modifiche nel modulo.

1.  Fare clic su **Vendite e marketing** \> **Comune** \> **Ordini cliente** \> **Tutti gli ordini cliente**. Fare doppio clic su un ordine cliente.

2.  Nella scheda **Gestione** del riquadro azioni del modulo **Ordine cliente**, fare clic su **Verifica limite di credito**.
