---
title: Panoramica registrazione orario e presenze
description: I lavoratori per registrazione ore possono immettere diversi tipi di registrazioni, ad esempio ora di entrata e di uscita, registrazione per attività indirette e registrazione assenze. In questo argomento vengono descritte registrazioni, calcolo, approvazione e utilizzo del flusso di lavoro per aggiungere la struttura e l'approvazione automatica al processo di approvazione delle schede attività.
author: ShylaThompson
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr, JmgRegistrationSetup, JmgStampTrans, JmgStampJournalTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom: 53351
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a13fc645560fcdbda9638d3ce9e8517d84474dce
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980883"
---
# <a name="time-and-attendance-registration-overview"></a>Panoramica registrazione orario e presenze

[!include [banner](../includes/banner.md)]

I lavoratori per registrazione ore possono immettere diversi tipi di registrazioni, ad esempio ora di entrata e di uscita, registrazione per attività indirette e registrazione assenze. In questo argomento vengono descritte registrazioni, calcolo, approvazione e utilizzo del flusso di lavoro per aggiungere la struttura e l'approvazione automatica al processo di approvazione delle schede attività. 

<a name="registrations"></a>Registrazioni
-------------

Nelle società che utilizzano Orario e presenze i lavoratori devono registrare il tempo che trascorrono a lavoro, nonché la loro presenza. In alcune società potrebbe essere richiesta solo la registrazione delle ore di entrata e di uscita. In altre società i lavoratori devono anche registrare il tempo speso sulle attività effettive che eseguono nonché le pause che prendono. Gli utenti previsti di Orario e presenze sono:
-   Lavoratori che devono registrare orario e presenza a intervalli regolari, ad esempio giornalmente, settimanalmente o bisettimanalmente.
-   Supervisori, dirigenti e responsabili delle retribuzioni che calcolano, approvano e trasferiscono le registrazioni dei lavoratori per sottoporle a ulteriore elaborazione.

| **Nota**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se si esegue Orario e presenze insieme a Esecuzione produzione, verrà presa nota di tutte le registrazioni relative a progetti, attività di progetto, attività indirette, codici assenze, straordinari e ore di flessibilità e saranno utilizzate per calcolare la retribuzione in entrambi i moduli. |

## <a name="time-registrations-workers"></a> Lavoratori per registrazione ore
Per riuscire a registrare le ore e le assenze, i lavoratori devono essere impostati come lavoratori per registrazione ore nella società in cui operano.

Dopo l'impostazione i lavoratori possono immettere tipi diversi di registrazioni.

-   Le ore di entrata e di uscita quando arrivano o lasciano il lavoro.
-   Consumo per ore e per articoli nei processi di produzione.
-   Tempo utilizzato su una macchina nel shop floor, se il computer è stato definito come risorsa.

| **Nota**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| A un lavoratore possono essere assegnate automaticamente le registrazioni delle ore effettuate su una particolare macchina nel shop floor, se il lavoratore sceglie di lavorare come assistente alla macchina quando avvia il processo di produzione. |

-   Registrazioni delle ore relative a progetti e attività di progetto.
-   Registrazione delle commissioni relative ai progetti e del consumo in base agli articoli mediante i rispettivi giornali di registrazione commissioni di progetto e giornali di registrazione articoli di progetto.
-   Assenza pianificata.
-   Assenza per arrivo in ritardo a lavoro o per uscita anticipata.
-   Pause di lavoro, registrate manualmente o calcolate automaticamente dal sistema.
-   Attività indirette, ovvero attività non produttive che un lavoratore potrebbe intraprendere nel corso di una giornata lavorativa. Esempi di queste attività comprendono le riunioni o la pulitura dell'area di lavoro.
-   Straordinario, che può essere registrato come ore aggiuntive, orario flessibile o ore straordinarie.

## <a name="adding-clock-out-registrations"></a>Aggiunta di registrazioni dell'uscita
Se un lavoratore dimentica di registrare l'uscita al termine della giornata lavorativa, è possibile aggiungere la registrazione dimenticata eseguendo un processo batch. Il sistema confronterà l'ora di entrata e l'ora di uscita in base al profilo associato del lavoratore e inserirà automaticamente la registrazione dell'ora di uscita mancante per farla corrispondere all'ora di fine del profilo. Entrambi le registrazioni di entrata e di uscita sono importanti per il calcolo e l'approvazione successivi delle registrazioni delle ore prima che vengano trasferite alle retribuzioni.

## <a name="calculating-registrations"></a>Calcolo delle registrazioni
Quando a un lavoratore della registrazione è assegnato un gruppo di calcolo che in genere si riferisce a un team, a un turno o a un gruppo di lavoro specifico. Il responsabile o il supervisore del team in genere convalida le registrazioni effettuate dai lavoratori ed è pertanto anche la persona responsabile dell'esecuzione del calcolo per i rispettivi gruppi di calcolo su base giornaliera. Durante il processo di calcolo il responsabile o il supervisore del team può:
-   Correggere registrazioni errate. Ad esempio, cambiare i codici Switch e modificare il riscontro sui processi di produzione.
-   Aggiungere registrazioni mancanti. Ad esempio, creare registrazioni delle uscite e transazioni assenze.
-   Eliminare registrazioni non corrette.

Poiché il tempo registrato deve corrispondere al profilo del lavoratore prima del calcolo delle registrazioni, è necessario sostituire il profilo orario di lavoro di qualsiasi lavoratore con un'eccezione al relativo profilo orario di lavoro standard. Nel caso in cui il profilo del lavoratore sia turno diurno e il lavoratore abbia accettato di lavorare durante un turno notturno senza retribuzione dello straordinario, il responsabile o il supervisore del team deve sostituire il profilo predefinito del lavoratore per calcolare l'orario di lavoro con la tariffa notturna standard e non come straordinario. Nel calcolo verrà inoltre visualizzato un errore se manca una registrazione assenze. Deve essere aggiunta prima che il calcolo venga completato.

## <a name="approving-registrations"></a>Approvazione delle registrazioni
Non appena si assegna un gruppo di calcolo a un lavoratore con registrazione ore, è necessario assegnare anche un gruppo di approvazione. Il gruppo sarà in genere specifico di un team, un turno o un gruppo di lavoro. È necessario approvare le registrazioni ore calcolate correttamente (ciò significa eseguire un calcolo senza errori) prima che possano essere generati articoli di retribuzione che in seguito è possibile trasferire a un sistema di gestione delle retribuzioni. L'amministratore delle retribuzioni effettuerà in genere l'approvazione delle registrazioni e prima dell'approvazione potrà:
-   Sostituire gli accordi salariali relativi a singoli lavoratori.
-   Aggiungere premi manuali.
-   Immettere informazioni aggiuntive sulle registrazioni delle assenze.

| **Nota**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Se per determinati lavoratori è stato calcolato uno straordinario, è possibile allocare tale straordinario a processi specifici eseguiti durante la giornata. Questo aspetto è particolarmente importante se i costi dei processi vengono calcolati sulla base della retribuzione del lavoratore. |

## <a name="approving-registrations-using-workflow"></a> Approvazione delle registrazioni utilizzando il flusso di lavoro
È possibile impostare un processo di approvazione del flusso di lavoro per l'approvazione automatica delle registrazioni conformi alle regole del flusso di lavoro lasciando da approvare manualmente solo le deviazioni. Se è attivata l'approvazione del flusso di lavoro, il responsabile o il supervisore del team invia le registrazioni calcolate per l'approvazione. Nel corso del processo del flusso di lavoro verranno generate le approvazioni e le attività appropriate che verranno quindi assegnate agli utenti e ai ruoli appropriati identificati nel flusso di lavoro. Sono disponibili due approvazioni del flusso di lavoro per orario e presenza.

| Flusso di lavoro                                  | Scopo                                                                                                   | Tipo di registrazione                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Totale giorni Orario e presenze            | Il flusso di lavoro convalida le registrazioni in base, ad esempio, al numero previsto di ore di lavoro per giornata. |                                                                                                                                                                                                                                                       |
| Registrazione giornale per Orario e presenze | Il flusso di lavoro convalida ogni tipo di registrazione per la data di registrazione.                           | Orario e presenze • Entrata • Uscita • Assenza • Pausa • Codice Switch • Progetto • Attività di progetto • Processi di produzione di attività indiretta • Coda prima • Impostazioni • Processo • Sovrapposizione • Trasporto • Coda dopo • Inizia assistenza • Interrompi assistenza |



## <a name="transferring-approved-registrations"></a>Trasferimento delle registrazioni approvate
Una volta approvate, le registrazioni possono essere trasferite a un processo periodico di gestione delle retribuzioni. Una registrazione trasferita viene registrata per l'attività o processo a cui si riferisce, ad esempio un ordine di produzione o un progetto. Le transazioni relative alla retribuzioni vengono generate per ciascun lavoratore in base alle registrazioni.  

## <a name="reversing-transferred-registrations"></a>Annullamento delle registrazioni trasferite
L'attività di annullamento delle transazioni, il rollback, può essere effettuata fino al momento dell'esecuzione del trasferimento della retribuzione per il periodo retributivo, ovvero il momento in cui i dati di retribuzione vengono trasferiti in un file esterno. Quando si effettua l'annullamento, tutte le registrazioni vengono ritirate e le transazioni registrate in specifici progetti o ordini di produzione vengono compensate e quindi revocate.

| **Nota**                                                 |
|----------------------------------------------------------|
| Il file esterno può essere importato in un sistema di gestione delle retribuzioni. |

## <a name="registrations-in-electronic-timecards"></a>Registrazioni in schede elettroniche dipendente
I lavoratori con mansioni di lavoro che non richiedono un riscontro immediato, come nel caso dei processi di produzione, ma che lavorano su attività di progetto, possono trarre vantaggi dall'utilizzo della scheda elettronica dipendente. Le schede elettroniche dipendenti offrono la flessibilità di immettere le registrazioni in qualsiasi momento e nel modo più vantaggioso per la programmazione aziendale, giornaliera, settimanale o quando un lavoratore torna in ufficio dopo un periodo di assenza. Per utilizzare schede elettroniche dipendenti o questi lavoratori, è necessario specificare Utilizza scheda dipendente nei dettagli del lavoratore. Le schede elettroniche dipendenti consentono al lavoratore di registrare:

-   Data
-   Tipo di registrazione
-   Riferimento del processo, ovvero progetto, attività indiretta o ordine di produzione
-   Identificazione processo
-   Consumo di tempo
-   Commissioni progetto
-   Articoli progetto






[!INCLUDE[footer-include](../../includes/footer-banner.md)]