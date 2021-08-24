---
title: Configurare il ruolo di responsabile dei congedi
description: Questo argomento spiega come impostare il ruolo di Responsabile dei congedi per la gestione dei congedi dei dipendenti.
author: hasrivas
ms.date: 07/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace, LeaveAbsenceManager
audience: Application User
ms.search.scope: Human Resources
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 050874628388629569751afae201ef346af020da09c81d24a69e1a4b5eb41b6f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732347"
---
# <a name="configure-the-absence-manager-role"></a>Configurare il ruolo di responsabile dei congedi

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [preview feature](./includes/preview-feature.md)]

In alcune organizzazioni, i responsabili delle persone non gestiscono i congedi per il proprio team. Il responsabile dei congedi può gestire questo processo per i membri del team in più reparti e team. I responsabili dei congedi hanno le seguenti capacità per la gestione dei congedi:

- Rivedere e approvare il permesso, in base a una gerarchia alternativa.
- Visualizzare i saldi dei membri del team.
- Visualizzare il calendario dei congedi.

## <a name="turn-on-the-feature"></a>Attivare la funzionalità

1. Nell'area di lavoro **Amministrazione sistema** seleziona **Gestione funzionalità**.

2. Nella scheda **Gestione funzionalità** abilita la funzionalità **(Anteprima) Responsabile dei congedi per la gestione dei congedi**.

## <a name="define-a-custom-hierarchy"></a>Definire una gerarchia personalizzata

La funzionalità del responsabile dei congedi utilizza una gerarchia personalizzata che deve essere configurata.

1. Nell'area di lavoro **Amministrazione organizzazione** seleziona **Tipi di gerarchia posizioni**.

2. Crea un tipo di gerarchia posizioni denominato **Congedo**.

3. Nell'area di lavoro **Congedo e assenza** sotto **Collegamenti**, seleziona **Parametri di congedo e assenza**.

4. Nella scheda **Generale** nell'elenco a discesa **Gerarchia assenze** seleziona il tipo di gerarchia **Congedo** creato in precedenza. Questa associazione della gerarchia dei congedi deve essere completata per ogni persona giuridica in cui verrà utilizzata la funzionalità del responsabile dei congedi.

Dopo aver definito il tipo di gerarchia, il report della gerarchia di posizioni deve essere assegnato alla posizione.

1. Nell'area di lavoro **Amministrazione organizzazione** seleziona **Tutte le posizioni**.

2. Seleziona la posizione da aggiungere alla gerarchia dei congedi.

3. Nella scheda **Relazioni**, seleziona **Aggiungi**.

4. Nel campo **Nome gerarchia** seleziona **Congedo**.

5. Nel campo **Subordinato a** seleziona una posizione Il nome del lavoratore viene compilato automaticamente dopo aver selezionato una posizione.

## <a name="assign-the-absence-manager-role-to-a-user"></a>Assegnare il ruolo di responsabile dei congedi a un utente

Il ruolo di Responsabile dei congedi deve essere assegnato ai dipendenti per consentire loro di approvare o rifiutare le richieste di congedo.

1. Nell'area di lavoro **Amministratore di sistema** seleziona **Collegamenti**.

2. Nella sezione **Utenti** seleziona il collegamento **Utenti**.

3. Nell'elenco degli utenti, seleziona l'utente a cui assegnare il ruolo di Gestore dei congedi.

4. Nella scheda **Ruolo utente**, seleziona **Assegna ruoli**.

5. Nell'elenco, seleziona il ruolo **Responsabile dei congedi**. Selezionare **OK**.

    > [!IMPORTANT]
    > Assicurati che il ruolo Dipendente sia stato assegnato anche all'utente a cui stai assegnando il ruolo Responsabile dei congedi. In caso contrario, il lavoratore non sarà in grado di utilizzare la funzione.

6. Dopo aver creato la gerarchia dei congedi, puoi visualizzarla seguendo questi passaggi:

    1. Nell'area di lavoro **Amministrazione organizzazione** seleziona **Gerarchia posizioni**.
    
    2. Nel campo **Tipo di gerarchia** seleziona **Congedo**.

## <a name="absence-manager-workspace"></a>Area di lavoro del responsabile delle assenze

Nell'area di lavoro **Self-service dipendenti** la scheda **Gestione dei congedi** mostra le informazioni sui congedi dei dipendenti assegnati al responsabile dei congedi nella gerarchia dei congedi. Ci sono alcune opzioni disponibili per il responsabile dei congedi: 
 - Esaminare richieste di permesso.</br>
 - Inviare una richiesta di permesso per conto di un dipendente.</br>
 - Visualizzare tutti i dipendenti a loro assegnati come parte della gerarchia di congedi.</br>
 - Visualizza il calendario del responsabile dei congedi.</br>

L'area di lavoro **Gestione dei congedi** include due schede:
 - **Richieste di permesso** : questa scheda elencherà tutte le richieste di permesso in sospeso che il responsabile dei congedi può approvare. Il responsabile dei congedi può selezionare più record e agire sugli stessi contemporaneamente. Se è abilitata la visualizzazione congedo interaziendale, questo elenco mostrerà le richieste di permesso in sospeso per tutte le persone giuridiche a cui hanno accesso. In caso contrario, mostrerà le richieste di permesso in sospeso per la persona giuridica attualmente selezionata. </br>
 - **Tutti i dipendenti**: questa scheda elencherà tutti i dipendenti assegnati al responsabile dei congedi nella gerarchia dei congedi. Sono disponibili un paio di opzioni per ogni dipendente:
    - **Richiedi permesso**: invia una nuova richiesta di permesso per il dipendente selezionato.</br>
    - **Permesso** – Visualizza i totali, i permessi approvati e le richieste di permesso per il dipendente selezionato.</br>

## <a name="approve-time-off-requests"></a>Approvare le richieste di permesso

I responsabili dei congedi possono approvare o negare le richieste di permesso per i dipendenti. 

> [!IMPORTANT]
> Prima che i responsabili dei congedi possano approvare o negare le richieste di permesso, il flusso di lavoro della richiesta di congedo deve essere configurato per assegnare loro gli elementi di lavoro della richiesta di congedo per la revisione.
>
> 1. Nella pagina **Flussi di lavoro risorse umane**, seleziona o crea il flusso di lavoro per la richiesta di congedo.
> 2. Seleziona l'opzione **Associa gerarchia** e poi, nel campo **Nome gerarchia** seleziona **Congedo**.
> 3. Aggiorna il flusso di lavoro nella finestra di progettazione del flusso di lavoro. In **Tipo di assegnazione**, seleziona l'opzione **Gerarchia** e poi, nella scheda **Selezione gerarchia** seleziona **Gerarchia configurabile**.
>
> Per informazioni su come creare il flusso di lavoro delle richieste di congedo, vedi [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md).

1. Nell'area di lavoro **Self-service dipendenti** seleziona la scheda **Gestione dei congedi**.

2. Nella scheda **Richieste di permesso**, seleziona le richieste di permesso su cui desideri intervenire. Puoi selezionare più record in questa visualizzazione elenco.

3. Utilizza i pulsanti di azione nella parte superiore della griglia per approvare, negare o delegare la richiesta di permesso. 

In alternativa, l'utente può anche utilizzare il riquadro **Richieste di permesso** a sinistra per accedere all'elenco di tutti gli elementi di lavoro delle richieste di permesso. 

## <a name="view-time-off-in-the-calendar"></a>Visualizzare il permesso nel calendario

Gli utenti con il ruolo di responsabile dei congedi possono visualizzare le richieste di permessi nel proprio calendario. Per accedere al calendario dei congedi segui questi passaggi.

> [!IMPORTANT]
> Un amministratore di sistema deve configurare le opzioni di visualizzazione per il calendario del responsabile dei congedi. Nella pagina **Parametri congedi e assenze** nella scheda **Calendario** ci sono le opzioni per nascondere o mostrare compleanni, assenze senza dettagli, congedi, e richieste di congedo in sospeso. C'è anche un'opzione per filtrare l'opzione di visualizzazione del calendario per tipo di lavoratore.

1. Nell'area di lavoro **Self-service dipendenti** seleziona **Gestone dei congedi** e **Calendario responsabile dei congedi**.

2. Immetti la data desiderata nel campo **Data**.

3. Aggiorna le opzioni di visualizzazione come richiesto.

Il calendario del responsabile dei congedi mostra tutti i record per i dipendenti che riportano al responsabile dei congedi nella gerarchia dei congedi.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un flusso di lavoro richiesta di congedo](hr-leave-and-absence-workflow.md)
- [Visualizzare i calendari per team e società](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
