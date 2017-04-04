---
title: Allineare le competenze della forza lavoro alle esigenze
description: "È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 720a1f272948eb310dc3cd02588aeec40b556d20
ms.openlocfilehash: 31dda85ff2e4a4e5380401b031b2dd74acff394b
ms.lasthandoff: 03/31/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Allineare le competenze della forza lavoro alle esigenze

È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.

Esempi di competenze di cui è possibile tenere traccia includono i seguenti:
-   Supervisione: capacità di supervisionare il lavoro svolto da altre persone.
-   Leadership: capacità di guidare dipendenti e reparti di un'azienda.
-   Pianificazione: capacità di adattarsi a nuovi scenari, di formulare visioni e di vedere oltre queste.
-   HTML: capacità di scrivere codice HTML.

Prima di poter assegnare una competenza a una persona o a una posizione lavorativa, creare una ricerca nel mapping delle competenze o un profilo competenze, è necessario immettere informazioni sulle competenze nella pagina **Competenze**. Per ogni competenza, è possibile selezionare un tipo e un modello di valutazione.

## <a name="rating-models"></a>Modelli di valutazione
La valutazione dei modelli contribuisce a valutare l'effettivo livello di competenza di una persona, il livello per cui deve lavorare o il livello di competenza necessario per una posizione lavorativa. È possibile immettere fino a 10 livelli per un modello di valutazione.  Ogni livello in un modello di valutazione verrà assegnato un fattore.  Il valore di verrà utilizzato fattore per normalizzare i punteggi di competenze che utilizzano diversi modelli di determinazione prezzo.  Fattore deve essere un numero compreso tra 0-9 e ogni livello è possibile selezionare un fattore specifico.  Livelli con valori del fattore maggiori hanno più peso in modello di valutazione.

## <a name="specify-job-skills"></a>Specificare le competenze della posizione lavorativa
Quando si immettono informazioni su un processo, è possibile specificare le competenze che una persona se deve eseguire il lavoro necessario per il processo.  È inoltre possibile specificare il livello desiderato per ogni competenza e il livello di importanza della competenza. Il livello di importanza richiesto per una determinata competenza varia in base alle diverse posizioni lavorative.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Immettere le competenze per i lavoratori, i candidati o i contatti
È possibile immettere le competenze di destinazione o le competenze effettive per i lavoratori, i candidati o i contatti. Una competenza prevista è una competenza che la persona intende raggiungere. Una competenza effettiva è una competenza che la persona ha attualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mapping delle competenze e profili di mapping delle competenze
È possibile creare una ricerca di mapping per individuare un lavoratore, un candidato o un contatto che viene qualificato eseguire uno specifico tipo di attività. Competenza- eseguendo le ricerche guardano tra le competenze, l'istruzione, certificati, ubicazioni di immettere i requisiti e di fiducia e rende i risultati corrispondenti ai criteri immessi.  Ad esempio, potrebbe essere utile conoscere i lavoratori nell'organizzazione ha guadagnato il relativo CPA.

Competenza- eseguendo il mapping dei profili che consentono si ne individua quali i candidati o con qualifiche che soddisfano direttamente le esigenze aziendali sono necessari.  Ad esempio, è possibile creare un profilo di mapping delle competenze per una posizione aperta nell'organizzazione. Creando un profilo per una posizione lavorativa specifica e copiando le competenze, il tipo di formazione e i certificati adatti a quella posizione nel profilo, è possibile trovare rapidamente lavoratori, candidati o persone di contatto che soddisfino uno o più dei criteri immessi nel profilo e visualizzare un elenco di candidati le cui competenze corrispondano il più possibile a quelle necessarie per la posizione lavorativa richiesta.

<table>
<thead>
<tr class="header">
<th><strong>Nota </strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Solo i lavoratori, i candidati o le persone di contatto selezionate per essere incluse nelle ricerche del mapping delle competenze possono essere visualizzate in un elenco di risultati del mapping delle competenze o essere incluse in un profilo competenze. Per includere un lavoratore, un candidato o una persona di contatto nelle ricerche del mapping delle competenze, impostare la selezione <strong>Includi nel mapping competenze</strong> su Sì nelle pagine seguenti:
<ul>
<li>Lavoro</li>
<li>Dipendente</li>
<li>Richiedente</li>
<li>Contatti</li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analisi della lacuna competenze e del profilo competenze
È possibile creare un'analisi profilo competenze per visualizzare un elenco di competenze di un lavoratore, un candidato o una persona di contatto a partire da una data specifica. È possibile creare un'analisi della lacuna competenze per confrontare le competenze di una persona con le competenze richieste per una posizione lavorativa specifica.  



<a name="see-also"></a>Vedere anche
--------

[Human resources](index.md)


