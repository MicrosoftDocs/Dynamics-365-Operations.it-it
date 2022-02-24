---
title: Iscrivere un dipendente a un piano di retribuzione variabile
description: Il responsabile di retribuzione e benefit può iscrivere i dipendenti a piani di retribuzione variabile per calcolare i premi in contanti e quelli non in contanti per i dipendenti.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 361403d61be64cfc58b3c2296937109b13a2b244
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419183"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Iscrivere un dipendente a un piano di retribuzione variabile

Il responsabile di retribuzione e benefit può iscrivere i dipendenti a piani di retribuzione variabile per calcolare i premi in contanti e quelli non in contanti per i dipendenti. In questa procedura si presuppone che un piano di retribuzione variabile sia stato creato con il campo Abilita iscrizione impostato su Sì e che le regole di idoneità siano state create per il piano di retribuzione variabile. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Per avviare la procedura, andare a Risorse umane > Lavoratori > Dipendenti > Retribuzione > Iscrizione al piano di retribuzione variabile.

1. Fare clic su Nuovo.
2. Nel campo Piano fare clic sul pulsante a discesa per aprire la ricerca.
    * La ricerca del piano verrà filtrata per indicare solo i piani di retribuzione variabile per cui il dipendente è idoneo in base alle regole di idoneità.  
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Attivare/disattivare l'espansione della sezione Generale.
5. Nel campo Data di validità, immettere una data.
6. Fare clic su Salva.
7. Attivare/disattivare l'espansione della sezione Sostituzioni.
    * Facoltativamente, la data della regola di assunzione può essere impostata per sostituire la data di assunzione di un dipendente quando la regola di assunzione specificata per il piano variabile selezione è Percentuale.  
    * Se il piano variabile è una percentuale del piano di base, la percentuale di premio può essere sostituita per il dipendente. Se il piano di retribuzione variabile è un numero di piani di unità, il numero di unità può essere sostituito per il dipendente.  
    * Se al dipendente deve essere assegnato un importo forfettario per il premio, tale importo può essere impostato qui.  
8. Attivare/disattivare l'espansione della sezione Sostituzioni organizzative.
    * Se è necessario prendere in considerazione le prestazioni del dipendente, le prestazioni dei diversi reparti o un reparto diverso da quello assegnato alla posizione del dipendente, il reparto può essere sostituito. Il totale della colonna Percentuale deve ammontare a 100.  

