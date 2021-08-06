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
ms.openlocfilehash: e8a8250b36d2774ac308637253b780592df316cd
ms.sourcegitcommit: 86d38cf57abe768e5bccde48b28280bc2224080c
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/19/2021
ms.locfileid: "6639608"
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

Nell'area di lavoro **Self-service dipendenti** la scheda **Responsabile dei congedi** mostra le informazioni sui congedi dei dipendenti assegnati al responsabile dei congedi nella gerarchia dei congedi.

Nella scheda **Congedo e assenza** per ogni dipendente sono disponibili le seguenti opzioni:

- **Permesso** – Visualizza i totali, i permessi approvati e le richieste di permesso per il dipendente selezionato.
- **Totali dei congedi** – Visualizza un elenco dei totali per i diversi piani di congedo per il dipendente selezionato.

## <a name="approve-time-off-requests"></a>Approvare le richieste di permesso

I responsabili dei congedi possono approvare o negare le richieste di permesso per i dipendenti. Possono anche creare richieste per conto dei dipendenti, se necessario.

> [!IMPORTANT]
> Prima che i responsabili dei congedi possano approvare o negare le richieste di permesso, il flusso di lavoro della richiesta di congedo deve essere configurato per assegnare loro gli elementi di lavoro della richiesta di congedo per la revisione.
>
> 1. Nella pagina **Flussi di lavoro risorse umane**, seleziona o crea il flusso di lavoro per la richiesta di congedo.
> 2. Seleziona l'opzione **Associa gerarchia** e poi, nel campo **Nome gerarchia** seleziona **Congedo**.
> 3. Aggiorna il flusso di lavoro nella finestra di progettazione del flusso di lavoro. In **Tipo di assegnazione**, seleziona l'opzione **Gerarchia** e poi, nella scheda **Selezione gerarchia** seleziona **Gerarchia configurabile**.
>
> Per informazioni su come creare il flusso di lavoro delle richieste di congedo, vedi [Creare un flusso di lavoro di richieste di congedo](hr-leave-and-absence-workflow.md).

1. Nell'area di lavoro **Self-Service dipendenti** seleziona la scheda **Responsabile dei congedi**.

2. Nella scheda **Responsabile dei congedi** seleziona il dipendente desiderato.

3. Seleziona **Dettagli** e poi **Permesso**.

4. Trova la richiesta di permesso e seleziona l'opzione **Approvazione**. È quindi possibile selezionare un'opzione per approvare o annullare la richiesta di permesso.

Lo stato **Annullato** indica che la richiesta è stata respinta. Lo stato **Completato** indica che la richiesta è stata approvata.

## <a name="view-time-off-in-the-calendar"></a>Visualizzare il permesso nel calendario

Gli utenti con il ruolo di responsabile dei congedi possono visualizzare le richieste di permessi nel proprio calendario. Per accedere al calendario dei congedi segui questi passaggi.

> [!IMPORTANT]
> Un amministratore di sistema deve configurare le opzioni di visualizzazione per il calendario del responsabile dei congedi. Nella pagina **Parametri congedi e assenze** nella scheda **Calendario** ci sono le opzioni per nascondere o mostrare compleanni, assenze senza dettagli, congedi, e richieste di congedo in sospeso. C'è anche un'opzione per filtrare l'opzione di visualizzazione del calendario per tipo di lavoratore.

1. Nell'area di lavoro **Self-service dipendenti** seleziona **Responsabile dei congedi** e **Calendario responsabile dei congedi**.

2. Immetti la data desiderata nel campo **Data**.

3. Aggiorna le opzioni di visualizzazione come richiesto.

Il calendario del responsabile dei congedi mostra tutti i record per i dipendenti che riportano al responsabile dei congedi nella gerarchia dei congedi.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un flusso di lavoro richiesta di congedo](hr-leave-and-absence-workflow.md)
- [Visualizzare i calendari per team e società](hr-employee-self-service-calendar.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
