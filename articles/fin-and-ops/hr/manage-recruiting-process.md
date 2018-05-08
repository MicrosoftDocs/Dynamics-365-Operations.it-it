---
title: Gestire un processo di selezione
description: "In questo articolo viene descritto un concetto che i reclutatori possono utilizzare per tenere traccia dei passaggi del processo di selezione, incluse le operazioni per annunciare le posizioni aperte e selezionare i candidati, per tenere traccia delle informazioni su candidati e domande di lavoro, per effettuare i colloqui con i candidati e per selezionare uno o più candidati per occupare le posizioni aperte nell'organizzazione."
author: rschloma
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4a7dba99c08d4dfc6afd1047130cea51b6bdab1d
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---

# <a name="manage-a-recruiting-process"></a>Gestire un processo di selezione

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto un concetto che i reclutatori possono utilizzare per tenere traccia dei passaggi del processo di selezione, incluse le operazioni per annunciare le posizioni aperte e selezionare i candidati, per tenere traccia delle informazioni su candidati e domande di lavoro, per effettuare i colloqui con i candidati e per selezionare uno o più candidati per occupare le posizioni aperte nell'organizzazione.

<a name="overview"></a>Panoramica
--------

I progetti di selezione consentono di organizzare i passaggi da completare per occupare posizioni aperte in una persona giuridica. Un candidato è una persona che si candida per un impiego nella azienda.  Una domanda di lavoro è l'espressione di interesse da parte di un candidato verso un impiego in un'azienda e può essere legata a un progetto di selezione per esprimere interesse verso una specifica apertura.  Un candidato può presentare più domande di lavoro all'interno della stessa persona giuridica o in più aziende della stessa organizzazione.

<a name="recruitment-projects"></a>Progetti di selezione
--------------------

I progetti di selezione consentono ai reclutatori di tenere traccia dei progressi nella ricerca del candidato per coprire una o più posizioni aperte.  Il progetto di selezione identifica il reparto e la mansione per una o più posizioni aperte. I progetti di selezione consentono inoltre di tenere traccia delle informazioni seguenti per le posizioni aperte:
-   Numero specifico di posizioni aperte
-   Responsabile assunzioni e un contatto alternativo per la posizione
-   Data in cui la richiesta è stata approvata
-   Scadenza della domanda di lavoro
-   Data di inizio stimata

Il progetto di selezione contiene **l'annuncio di lavoro** utilizzato nel portale **Self Service dipendenti** per comunicare l'opportunità di lavoro. Per visualizzare tale opportunità ai dipendenti, nel progetto di selezione deve essere presente un **annuncio di lavoro**, il campo **Visualizza per dipendente self-service** deve essere impostato su Sì, il campo **Scadenza domanda** deve essere impostato su una data futura e il campo **Stato progetto** del progetto di selezione deve essere Avviato. Nella tabella seguente sono elencati gli stati possibili del progetto di selezione e la relativa descrizione.

| **Stato**    | **Descrizione**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Programmato | Le iniziative di selezione sono in preparazione.  La selezione non è ancora iniziata per il progetto. |
| Avviato   | Le domande di lavoro vengono accettate per le posizioni aperte del progetto.                    |
| Completata  | Tutte le posizioni aperte per il progetto sono state occupate.                                          |
| Annullato  | La selezione è stato annullata per il progetto.                                           |

I reclutatori possono anche registrare i **media** utilizzati per comunicare l'opportunità di lavoro tramite canali esterni nonché tenere traccia degli **sviluppi** del progetto o delle domande di lavoro.

<a name="applicants"></a>Candidati
----------

Un candidato è una persona che si candida per una mansione nella azienda.  I candidati sono in condivisione tra tutte le persone giuridiche dell'organizzazione e rappresentano un ampio pool di competenze tra cui cercare. È possibile gestire competenze, referenze, richieste di facilitazione e informazioni personali per i candidati. Quando si crea un record candidato, viene creato un record per il candidato nella Rubrica globale. È possibile utilizzare la pagina **Candidato** per aggiornare le seguenti informazioni della Rubrica globale per i candidati:
-   Informazioni indirizzo
-   Informazioni di contatto
-   Informazioni di identificazione
-   Dettagli nome
-   Informazioni personali

## <a name="applications"></a>Applicazioni
Per registrare le informazioni derivanti dalle domande di lavoro ricevute, utilizzare la pagina **Domanda di lavoro**. La domanda di lavoro è l'espressione di interesse da parte del candidato verso l'apertura a una mansione nell'organizzazione.  Per creare una domanda di lavoro, il candidato deve essere già presente come un candidato o persona nel sistema.
Le domande di lavoro inviate dai candidati via Web sono domande di lavoro sollecitate in risposta a un annuncio di lavoro oppure sono non sollecitate. Le domande di lavoro sollecitate vengono associate automaticamente al progetto di selezione per cui era stato creato l'annuncio di lavoro. Le domande di lavoro non sollecitate vengono associate al progetto di selezione specificato nell'area **Selezione del personale** della pagina **Parametri Risorse umane**.
### <a name="application-status"></a>Stato domanda di lavoro

Lo stato della domanda di lavoro indica la fase in cui si trova la domanda nel processo di selezione. Nella tabella seguente sono elencati gli stati possibili delle domande di lavoro e la relativa descrizione.

| Stato    | Descrizione                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Ricevuto  | La domanda di lavoro è stata ricevuta.                                                             |
| Confermata | È possibile inviare al candidato una notifica in cui viene confermata la ricezione della domanda di lavoro.            |
| Colloquio | Al candidato può essere inviato un invito per un colloquio.                                     |
| Rifiuto | È possibile inviare al candidato una lettera di rifiuto alla domanda di lavoro.                                          |
| Annullato  | È possibile inviare al candidato una conferma di revoca. Questo stato viene assegnato manualmente. |
| Assunto  | È possibile inviare al candidato un'offerta di lavoro.                                         |

### <a name="correspondence-actions"></a>Azioni di corrispondenza

L'azione di corrispondenza di una **domanda di lavoro** determina il documento o il modello di messaggio di posta elettronica che si utilizza per comunicare con il candidato che ha inviato la domanda. È possibile associare **Segnalibri per domande di lavoro** con azioni di corrispondenza per consentire di utilizzare i valori nelle pagine Domanda di lavoro, Candidato, Colloquio e Progetto di selezione nelle comunicazioni con i candidati.  È possibile creare **Modelli di messaggio di posta elettronica per domande di lavoro** per le azioni di corrispondenza per inviare rapidamente messaggi di posta elettronica ai candidati che hanno una domanda di lavoro con una determinata combinazione di stato e azione di corrispondenza. È ad esempio possibile inviare un messaggio di posta elettronica di conferma a tutte le domande di lavoro con lo **Stato** impostato su Ricevuto e un'**azione di corrispondenza** impostata su Ricevuta.  Dopo l'invio del messaggio di posta elettronica, è possibile scegliere di aggiornare automaticamente lo stato delle domande di lavoro.

## <a name="application-routing"></a>Reindirizzamento domande di lavoro

Se una domanda di lavoro deve essere rivista da più lavoratori, è possibile utilizzare la pagina **Reindirizzamento domande di lavoro** per creare un elenco di lavoratori per gestire il processo.

## <a name="interviews"></a>Colloqui

È possibile programmare i **Colloqui candidati** dalla pagina **Domande di lavoro**.  Utilizzare il pulsante **Invia informazioni riunione** per inviare un file calendario con le informazioni di programmazione del colloquio al candidato e al responsabile del colloquio.

## <a name="skill-mapping"></a>Mapping competenze

I campi **Mapping competenze** e **Profili mapping competenze** possono essere utilizzati per identificare i candidati che possono rispondere alle esigenze di una posizione aperta.

## <a name="hiring-applicants"></a>Assunzione di candidati

Utilizzare la pagina **Domande di lavoro** per assumere un candidato. Quando si assume un candidato, il record della domanda di lavoro avrà lo stato di **Assunto** e il record del candidato nella Rubrica globale verrà associato al nuovo record lavoratore. Le modifiche alle informazioni della Rubrica globale per il nuovo record lavoratore saranno visualizzate anche nel record candidato. Ciò consente di ridurre l'immissione di dati se il nuovo lavoratore si propone per una mansione differente all'interno dell'azienda.  Per assumere un lavoratore esistente per una posizione nuova, fare clic su **Modifica posizione** nel menu a discesa **Stato domanda di lavoro** per avviare il processo di trasferimento.






