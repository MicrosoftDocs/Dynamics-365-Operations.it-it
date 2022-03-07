---
title: Gestire le informazioni sull'infortunio e la malattia del dipendente
description: Questa attività descrive come creare un caso di infortunio o malattia.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06307331db4d420e99de21c0eb0b3cf1c233f0d5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066652"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Gestire le informazioni sull'infortunio e la malattia del dipendente


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Si consiglia di completare prima la guida di attività 'Impostazione infortunio e malattia' perché alcune informazioni di impostazione vengono utilizzate qui. 



Questa registrazione attività descrive i passaggi fondamentali per la creazione di un caso di infortunio o malattia. Oltre ai dettagli dell'infortunio o della malattia, viene tracciato lo stato di un caso. Per impostazione predefinita, i casi hanno lo stato di **Aperto**. Puoi gestire lo stato utilizzando la voce di menu **Stato caso** nella parte superiore della pagina.

1. Passa a **Risorse umane \> Lavoratori \> Infortunio e malattia \> Eventi imprevisti di infortunio o malattia**.
2. Selezionare **Nuovo**.
3. Nel campo **Descrizione caso**, immetti un valore (ad esempio, **Infortunio al polso**).
4. Nel campo **Lavoratore**, immetti o seleziona un valore (ad esempio, **Ana Bowman**).
5. Nel campo **Data e ora dell'incidente**, immetti una data e un'ora (ad esempio, 20 gennaio 2016, alle 10:00).
6. Nel campo **Tipo di infortunio o malattia**, immetti o seleziona un valore (ad esempio **Frattura**).
7. Nel campo **Parte del corpo**, immetti o seleziona un valore (ad esempio, **Polso**).
8. Nel campo **Tipo di esito** immetti o seleziona un valore (ad esempio, **Terapia**).
9. Nel campo **Data e ora restituite** immetti una data e un'ora.

    La data e l'ora restituite devono essere successive alla data e all'ora dell'incidente.

10. Nel campo **Persona che ha segnalato il caso**, immetti o seleziona un valore (ad esempio, **Ana Bowman**).

    La persona specificata potrebbe essere il dipendente o un altro testimone dell'incidente.

11. Nella sezione **Incidente**, nel campo **Luogo dell'evento imprevisto**, immetti un valore (ad esempio, **Magazzino**).
12. Nel campo **Sul posto di lavoro**, seleziona **Sì** se l'incidente si è verificato nei locali di lavoro.
13. Nel campo **Data e ora di inizio lavoro**, immetti la data e l'ora in cui la persona interessata ha iniziato a lavorare prima che si verificasse l'incidente.
14. Nel campo **Posizione lavorativa o attività del dipendente**, immetti il lavoro o l'attività che il lavoratore stava eseguendo quando si è verificato l'incidente (ad esempio, **Caricamento scatole**). 
15. Nel campo **Causa dell'incidente**, immetti la causa dell'incidente (ad esempio, **Scivolato sul pavimento bagnato**).
16. Nel campo **Livello di gravità** immetti o seleziona un valore.
17. Nel campo **Azione da eseguire**, immetti un valore (ad esempio, **Pulire subito le perdite**).
18. Nel campo **Giorni di assenza dal lavoro previsti**, immetti il numero di giorni previsti per l'assenza dal lavoro dell'individuo.

    Quando l'utente torna al lavoro, aggiorna il campo **Giorni di assenza dal lavoro** con il numero effettivo di giorni di assenza dell'individuo.

19. Nella sezione **Costi infortunio o malattia**, seleziona **Aggiungi**.
20. Nel campo **Data** immettere una data.
21. Nel campo **Tipo di costo** immetti o seleziona un valore (ad esempio, **Terapia**).

    È inoltre possibile immettere un importo e allegare al costo qualsiasi documentazione di supporto al costo (ad esempio fatture o certificati medici).

22. Seleziona **Aggiungi**.
23. Nel campo **Data** immettere una data.
24. Nel campo **Tipo di costo** immetti o seleziona un valore (ad esempio, **Medico**).
25. Nella sezione **Trattamenti per infortunio o malattia**, seleziona **Aggiungi**.
26. Nel campo **Data trattamento** immetti una data e un'ora.
27. Nel campo **Tipo di trattamenti** immetti o seleziona un valore (ad esempio, **Stampella**).
28. Facoltativo: imposta la sezione **Visita al Pronto soccorso** su **Sì**.
29. Nel campo **Commenti trattamento** immetti o seleziona un valore (ad esempio, **Stampella per 2 settimane**).
30. Nel campo **Nome medico**, immetti un valore (ad esempio **Dr. Anderson**).
31. Nel **Struttura e luogo di trattamento** campo, immettere un valore (ad esempio, **Elm St. Emergenza**).
32. Nel campo **Dettagli trattamento**, immetti un valore (ad esempio, **I raggi x confermano la frattura, indossare stampella**).
33. Seleziona **Salva**.

Lo stato del caso può essere aggiornato in qualsiasi momento. Se l'elaborazione dell'infortunio o della malattia è ancora in corso, imposta lo stato su **In elaborazione**. Una volta chiuso l'incidente, è possibile solo aggiungere o rimuovere solo i costi, i trattamenti o le archiviazioni relative all'incidente. Per modificare altre informazioni, devi riaprire il caso.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
