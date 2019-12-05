---
title: Utilizzare le modifiche ai dati del personale
description: La funzione di controllo del processo consente di tenere traccia quando i candidati, le offerte di lavoro o le domande di lavoro cambiano per ragioni di conformità o di segnalazione.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: trkeya
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: 0b0be541416d2e4be78da223ec8e95c195d90bbc
ms.sourcegitcommit: 9cc6a011bfdd1b0fe505760b6bf429eb6c65862a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/25/2019
ms.locfileid: "2832642"
---
# <a name="track-changes-in-recruiting-data"></a>Utilizzare le modifiche ai dati del personale

[!include [banner](includes/banner.md)]

È possibile tenere traccia delle modifiche apportate ai candidati, alle posizioni di lavoro o alle domande di lavoro utilizzando l'elaborazione di controllo. Questa opzione è utile per motivi di conformità o report.

È possibile visualizzare i dati aggiornati in Power BI mediante il connettore OData. Per ulteriori informazioni, vedere [Connettersi ai feed OData in Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Tieni traccia delle modifiche
Per impostare le modifiche di tenere traccia dei dati del personale, effettuare le seguenti operazioni:

1. In [Power Apps](https://web.powerapps.com), selezionare l'ambiente appropriato.

2. Selezionare **Impostazioni** (icona a forma di ingranaggio), scegliere **Personalizzazioni avanzate** e quindi selezionare **Risorse** in **Risorse per sviluppatori**. 

3. Nella pagina **Risorse per sviluppatori**, copiare il valore nel campo **Valore API Web istanza**. Ad esempio, il valore può risultare simile al seguente: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. È quindi possibile eseguire query sui dati di una delle seguenti entità:
  - Storico posizione aperta (msdyn_jobopeninghistories)
  - Storico domanda di lavoro (msdyn_jobapplicationhistories) 
  - Storico candidato (msdyn_candidatehistories)

## <a name="data-reported"></a>Dati di segnalazione

I seguenti dati sono disponibili con il controllo dei processi.

| Dati di segnalazione | Descrizione |
| --- | --- |
| Autore modifica (msdyn_ChangedbyId) | Riferimento all'utente |
| Data creazione (createdon) |  Data e ora nel formato UTC relative alla modifica |
| Tipo di modifica (msdyn_changetype) | Modifica apportata |
| Valori comuni per i candidati, posizioni aperte <br></br>e domande di lavoro | Data creazione<br></br>Aggiornati |
| Storico domanda di lavoro | Elemento aggiunto <br></br>Elemento rimosso |
| Storico posizione aperta | TODO: post aggiunto <br></br>TODO: post rimosso <br></br>TODO: post aggiornato <br></br>TODO: partecipante aggiunto <br></br>TODO: partecipante rimosso |
| Storico candidato | Elemento aggiunto <br></br>Elemento rimosso <br></br>Esperienza di lavoro aggiunta <br></br>Esperienza di lavoro rimossa <br></br>Percorso formativo aggiunto <br></br>Percorso formativo rimosso <br></br>Competenza aggiunta <br></br>Competenza rimossa <br></br>Tag aggiunto <br></br>Tag rimosso <br></br>Social Network aggiunto <br></br>Social Network rimosso <br></br>Dettagli personali aggiunti <br></br>Dettagli personali aggiornati<br></br> |
| Campi modificati (msdyn_changedfields) | I campi modificati dell'elenco di oggetti JSON potrebbero non memorizzare i valori per tutti i campi.<br></br><br></br>Per le modifiche "Creato" e "Aggiornato", verranno elencati i campi nel record creato o modificato.<br></br><br></br>Per i tipi di modifica "Aggiunto", verranno elencati i campi nel record figlio.<br></br><br></br>**Esempio**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Storico domanda di lavoro | Domanda di lavoro (msdyn_JobapplicatonId)<br></br>Stato (msdyn_status) <br></br>Motivo stato (msdyn_statusreason) <br></br>Motivo rifiuto (msdyn_rejectionreason) |
| Storico posizione aperta | Posizione aperta (msdyn_JobopeningId) <br></br>Stato (msdyn_jobopeningstatus) <br></br>Motivo stato (msdyn_jobopeningstatusreason) |
| Storico candidato | Candidato (msdyn_CandidateId) |
