---
title: Gestire le informazioni sull'infortunio e la malattia del dipendente
description: Si consiglia di completare prima la guida di attività 'Impostazione infortunio e malattia' perché alcune informazioni di impostazione vengono utilizzate qui.
author: ShielaSogge
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shielas
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 03d1e7f7b648e65cbe628aa4ff8b39dfa03ce96b
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "332612"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Gestire le informazioni sull'infortunio e la malattia del dipendente

[!include [task guide banner](../../includes/task-guide-banner.md)]

Si consiglia di completare prima la guida di attività 'Impostazione infortunio e malattia' perché alcune informazioni di impostazione vengono utilizzate qui. 



Questa registrazione attività copre i passaggi fondamentali per la creazione di un caso di infortunio o malattia. Oltre a tracciare i dettagli dell'infortunio o della malattia, viene tracciato anche lo stato del caso.  Per il caso viene utilizzato il valore predefinito 'aperto' per lo stato.  Gli stati possono essere gestiti dalla voce di menu 'Stato caso' nella barra dell'applicazione nella parte superiore del modulo.

1. Andare a Risorse umane > Lavoratori > Infortunio e malattia > Eventi imprevisti di infortunio o malattia.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Descrizione caso.
    * Esempio: infortunio al polso  
4. Nel campo Lavoratore immettere o selezionare un valore.
    * Esempio: Ahmed Barnett  
5. Nel campo Data e ora evento imprevisto immettere una data e un'ora.
    * Esempio: 20/01/2016 10.00  
6. Nel campo Tipo di infortunio o malattia, immettere o selezionare un valore.
    * Esempio: frattura  
7. Nel campo Parte del corpo immettere o selezionare un valore.
    * Esempio: polso  
8. Nel campo Tipo di esito immettere o selezionare un valore.
    * Esempio: terapia  
9. Nel campo Data e ora restituite immettere una data e un'ora.
    * La data e l'ora restituite devono essere successive alla data e all'ora dell'incidente.  
10. Nel campo Persona che ha segnalato il caso, immettere o selezionare un valore.
    * Potrebbe essere il dipendente o un altro testimone dell'incidente.  Esempio: Ahmed Barnett  
11. Espandere la sezione Evento imprevisto.
12. Nel campo Luogo dell'evento imprevisto, immettere un valore.
    * Esempio: Magazzino  
13. Selezionare Sì nel campo Sul posto di lavoro.
    * Se l'evento imprevisto si è verificato sul posto di lavoro, selezionare sì.  
14. Nel campo Data e ora di inizio lavoro immettere una data e un'ora.
    * Immettere la data e l'ora in cui l'utente interessato ha iniziato a lavorare, prima che si verificasse l'incidente.  
15. Nel campo Posizione lavorativa o attività del dipendente, immettere un valore.
    * Immettere la mansione o l'attività che il lavoratore stava svolgendo quando si è verificato l'incidente.  Esempio: caricamento scatole  
16. Digitare un valore nel campo Causa dell'evento imprevisto.
    * Immettere la causa dell'incidente.  Esempio: scivolato sul pavimento bagnato  
17. Nel campo Livello di gravità immettere o selezionare un valore.
18. Nel campo Azione da eseguire, immettere un valore.
    * Esempio: pulire subito le perdite  
19. Nel campo Giorni di assenza dal lavoro previsti, immettere un numero.
    * Consente di immettere il numero di giorni di assenza che si prevede siano necessari per l'utente.  Quando l'utente torna al lavoro, aggiornare il campo 'Giorni di assenza dal lavoro' con il numero effettivo di giorni di assenza.  
20. Espandere la sezione Costi infortunio o malattia.
21. Scegliere Aggiungi.
22. Nel campo Data immettere una data.
23. Nel campo Tipo di costo immettere o selezionare un valore.
    * Esempio: terapia. È inoltre possibile immettere un importo e allegare al costo qualsiasi documentazione di supporto, ad esempio fatture o certificati medici.  
24. Scegliere Aggiungi.
25. Nel campo Data immettere una data.
26. Nel campo Tipo di costo immettere o selezionare un valore.
    * Esempio: Medico  
27. Espandere la sezione Trattamenti per infortunio o malattia.
28. Scegliere Aggiungi.
29. Nel campo Data trattamento immettere una data e un'ora.
30. Nel campo Tipo di trattamento, immettere o selezionare un valore.
    * Esempio: Stampella  
31. Facoltativamente, impostare la sezione Visita al Pronto soccorso su Sì.
32. Nel campo Commenti trattamento, digitare un valore.
    * Esempio: Stampella per 2 settimane  
33. Digitare un valore nel campo Nome medico.
    * Esempio: Dott. Anderson  
34. Nel campo Struttura e luogo del trattamento, digitare un valore.
    * Esempio: Pronto soccorso di via Olmo  
35. Nel campo Dettagli trattamento, digitare un valore.
    * Esempio: i raggi x confermano la frattura, indossare stampella  
36. Fare clic su Salva.
    * Lo stato del caso può essere aggiornato in qualsiasi momento.  Impostare il caso su In corso se l'elaborazione dell'infortunio o della malattia è ancora in corso.  Una volta chiuso l'incidente, è possibile solo aggiungere o rimuovere solo i costi, i trattamenti o le archiviazioni relative all'incidente.  Per modificare altre informazioni, riaprire il caso.  

