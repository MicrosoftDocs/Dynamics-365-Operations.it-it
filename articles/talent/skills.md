---
title: Allineare le competenze della forza lavoro alle esigenze
description: "È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica."
author: kherr75
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2b76064049daccdcdff04c9f2fdde9a8b9c9e8e0
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="align-workforce-skills-with-business-needs"></a>Allineare le competenze della forza lavoro alle esigenze

[!include[banner](includes/banner.md)]


È possibile tenere traccia delle competenze che hanno o dovranno avere i lavoratori, i candidati o le persone di contatto per svolgere i loro ruoli in modo efficace. È inoltre possibile specificare le competenze necessarie per una posizione lavorativa specifica.

Esempi di competenze di cui è possibile tenere traccia includono i seguenti:
-   Supervisione: capacità di supervisionare il lavoro svolto da altre persone.
-   Leadership: capacità di guidare dipendenti e reparti di un'azienda.
-   Pianificazione: capacità di adattarsi a nuovi scenari, di formulare visioni e di vedere oltre queste.
-   HTML: capacità di scrivere codice HTML.

Prima di poter assegnare una competenza a una persona o a una posizione lavorativa, creare una ricerca nel mapping delle competenze o un profilo competenze, è necessario immettere informazioni sulle competenze nella pagina **Competenze**. Per ogni competenza, è possibile selezionare un tipo e un modello di valutazione.

## <a name="rating-models"></a>Modelli di valutazione
La valutazione dei modelli contribuisce a valutare l'effettivo livello di competenza di una persona, il livello per cui deve lavorare o il livello di competenza necessario per una posizione lavorativa. È possibile immettere fino a 10 livelli per un modello di valutazione.  Ogni livello in un modello di valutazione viene assegnato a un fattore.  Il valore del fattore verrà utilizzato per normalizzare i punteggi di competenze che utilizzano modelli di valutazione diversi.  Il fattore deve essere un numero compreso tra 0 e 9 e ogni livello deve avere un fattore univoco.  Livelli con valori del fattore maggiori hanno più peso in modello di valutazione.

## <a name="specify-job-skills"></a>Specificare le competenze della posizione lavorativa
Quando si immettono informazioni su una mansione, è possibile specificare le competenze che una persona deve avere per poter svolgere tale mansione.  È inoltre possibile specificare il livello desiderato per ogni competenza, nonché il livello di importanza della competenza. Il livello di importanza richiesto per una determinata competenza varia in base alle diverse posizioni lavorative.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Immettere le competenze per i lavoratori, i candidati o i contatti
È possibile immettere le competenze di destinazione o le competenze effettive per i lavoratori, i candidati o i contatti. Una competenza prevista è una competenza che la persona intende raggiungere. Una competenza effettiva è una competenza che la persona ha attualmente.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Mapping delle competenze e profili di mapping delle competenze
È possibile creare una ricerca del mapping delle competenze per individuare un lavoratore, un candidato o un contatto che sia qualificato a svolgere un tipo specifico di attività. Le ricerche di mapping delle competenze cercano tra competenze, istruzione, certificati, posizioni di fiducia ed esperienze di progetto e restituiscono i risultati che corrispondono ai criteri immessi.  Ad esempio, potrebbe essere utile conoscere i lavoratori nell'organizzazione che hanno ottenuto la Canadian Payments Association (CPA).

I profili di mapping delle competenze consentono di trovare i dipendenti o i candidati con qualifiche che corrispondono direttamente alle esigenze dell'azienda.  È possibile ad esempio creare un profilo di mapping delle competenze per una posizione aperta nell'organizzazione. Creando un profilo per una posizione lavorativa specifica e copiando le competenze, il tipo di formazione e i certificati adatti a quella posizione nel profilo, è possibile trovare rapidamente lavoratori, candidati o persone di contatto che soddisfino uno o più dei criteri immessi nel profilo e visualizzare un elenco di candidati le cui competenze corrispondano il più possibile a quelle necessarie per la posizione lavorativa richiesta.

>**Nota**: solo i lavoratori, i candidati o le persone di contatto selezionate per essere incluse nelle ricerche del mapping delle competenze possono essere visualizzate in un elenco di risultati del mapping delle competenze o essere incluse in un profilo competenze. Per includere un lavoratore, un candidato o una persona di contatto nelle ricerche del mapping delle competenze, impostare la selezione **Includi nel mapping competenze** su Sì nelle pagine seguenti:

> + Lavoro
> + Dipendente
> + Richiedente
> + Contatti

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analisi della lacuna competenze e del profilo competenze
È possibile creare un'analisi profilo competenze per visualizzare un elenco di competenze di un lavoratore, un candidato o una persona di contatto a partire da una data specifica. È possibile creare un'analisi della lacuna competenze per confrontare le competenze di una persona con le competenze richieste per una posizione lavorativa specifica.  



<a name="see-also"></a>Vedere anche
--------

[Risorse umane](index.md)




