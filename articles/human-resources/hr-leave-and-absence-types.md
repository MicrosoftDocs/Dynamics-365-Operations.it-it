---
title: Configurare tipi di congedo e assenza
description: Impostare i tipi di congedo che i dipendenti possono prendere in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e35c5fed886ebf9a453c22b3e04ca9ffe50b6d70
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805206"
---
# <a name="configure-leave-and-absence-types"></a>Configurare tipi di congedo e assenza

[!include [preview banner](../includes/preview-banner.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

I tipi di congedo in Dynamics 365 Human Resources definiscono i tipi di assenze che i dipendenti possono segnalare. È possibile adattare i tipi di congedo in base alle esigenze della propria organizzazione. Di seguito sono riportati alcuni esempi di tipi di congedo:

- Permessi retribuiti
- Congedo non retribuito
- Ferie pagate
- Congedo per malattia
- Congedo per motivi medici
- Congedo per motivi familiari
- Disabilità a breve termine
- Congedo per lutto

## <a name="add-a-leave-type"></a>Aggiungere un tipo di congedo

1. Nell'area di lavoro **Congedo e assenza**, selezionare la scheda **Collegamenti**.
2. Sotto **Impostazione**, selezionare **Tipi di congedo e assenza**.
3. Selezionare **Nuovo**.
4. Immetti un nome per il tipo di congedo in **Tipo**, immetti una descrizione in **Descrizione** e seleziona un flusso di lavoro nel campo **ID flusso di lavoro**. In base al tipo di congedo, seleziona un tipo di richiesta nel campo **Tipo di richiesta**. Ad esempio, seleziona **Tempo libero** o **Congedo**.
5. In **Generale**, selezionare **Nessuno**, **Programmato** o **Non programmato** nell'elenco a discesa **Categoria**.
6. Seleziona un codice di reddito nell'elenco a discesa **Codice di reddito**.
7. In **Codice motivo obbligatorio**, scegli se richiedere un codice motivo o meno. Se si desidera richiedere dei codici motivo, potrebbe essere necessario aggiungerli. Sotto **Codici motivo**, selezionare **Aggiungi**, selezionare un codice motivo, quindi selezionare la casella di controllo **Abilitato** accanto allo stesso.
8. Se il tipo di richiesta è **Richiesta di congedo**, effettua le seguenti operazioni:

      1. In **A tempo indeterminato**, seleziona se gli utenti devono essere in grado di creare congedi a tempo indeterminato.
      2. Se **A tempo indeterminato** è abilitato, è possibile selezionare se i lavoratori devono inviare un avviso di rientro al lavoro quando rientrano da un congedo.
      3. Se i lavoratori devono inviare un avviso di rientro al lavoro, è possibile abilitare **Abilita avviso di ritorno al lavoro**. Se **Abilita avviso di ritorno al lavoro** è abilitata, **Allegato richiesto** è abilitata automaticamente e non può essere disabilitata.

9. Se gli utenti devono caricare documenti quando creano o aggiornano le richieste di congedo, puoi abilitare **Allegato richiesto**.
10. In **Limitare l'accesso a ruoli selezionati**, scegli se limitare l'accesso. Quindi in **Ruoli di sicurezza per questo tipo di congedo**, seleziona i ruoli di sicurezza. I ruoli di sicurezza sono definiti nel flusso di lavoro selezionato sotto **ID flusso di lavoro** precedentemente in questa procedura.
11. In **Colore calendario**, seleziona il colore da visualizzare nei calendari di congedi e assenze per questo tipo di congedo.
11. In **Relazioni di sospensione**, scegli se questo tipo di congedo deve sospendere questo tipo di congedo o deve essere sospeso da un altro tipo di congedo. Quando una richiesta di congedo viene inviata per il tipo di congedo che provoca la sospensione, verrà automaticamente creata una sospensione del congedo per il tipo di congedo sospeso.
12. Seleziona **Salva**.

## <a name="configure-leave-type-rules"></a>Configurare le regole del tipo di congedo

1. Impostare opzioni di arrotondamento per il tipo di **congedo e assenza**. Le opzioni includono **Nessuno**, **Su**, **Giù** e **Al più vicino**. È inoltre possibile impostare la precisione di arrotondamento per il tipo di congedo.
2. Impostare **Correzione giorni festivi** per il tipo di congedo. Quando si seleziona questa opzione, il numero di giorni festivi che cadono in un giorno lavorativo viene usato per determinare come accumulare permessi per il tipo di congedo. Ad esempio, se il giorno di Natale cade di lunedì, Human Resources sottrarrà un giorno dal tipo di congedo durante l'elaborazione degli accumuli.

   i giorni festivi sono impostati nel calendario orario lavorativo. Per ulteriori informazioni, vedi [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md).
   
 3. Impostare **Tipo di congedo riportabile** per il tipo di congedo. Quando si seleziona questa opzione, tutti i saldi riportabili verranno trasferiti al tipo di congedo specificato. Anche il tipo di congedo riportabile deve essere incluso nel piano di congedo e assenza. 
 
4. Definire **Regole di scadenza** per il tipo di congedo. Quando si configura questa opzione, è possibile scegliere l'unità di giorni o mesi e impostare la durata per la scadenza. La data di validità della regola di scadenza viene utilizzata per determinare quando avviare l'esecuzione del processo batch che elabora la scadenza del congedo o la data alla quale la regola diventa effettiva. La scadenza stessa avverrà sempre alla data di inizio del periodo di accumulo. Ad esempio, se la data di inizio del periodo di accumulo è il 3 agosto 2021 e la regola di scadenza è stata impostata su 6 mesi, la regola verrà elaborata in base allo scostamento di scadenza dalla data di inizio del periodo di accumulo, quindi verrà eseguita il 3 febbraio, 2022. Eventuali saldi di congedi esistenti al momento della scadenza verranno sottratti dal tipo di congedo e si rifletteranno nel saldo di congedi.
 
## <a name="configure-the-required-attachment-per-leave-type"></a>Configurare l'allegato richiesto per tipo di congedo

> [!NOTE]
> Per usare il campo **Allegato richiesto**, è necessario prima attivare la funzione **Configura l'allegato richiesto per le richieste di congedo** in Gestione funzionalità. Per ulteriori informazioni su come attivare le funzionalità, vedi [Gestire le funzionalità](hr-admin-manage-features.md).

1. Nella pagina **Congedo e assenza** nella scheda **Collegamenti** sotto **Impostazioni**, seleziona **Tipi di congedo e assenza**.

2. Nell'elenco seleziona un **Tipo di congedo e assenza**. Nella sezione **Generale**, usa il campo **Allegato richiesto** per specificare se è necessario caricare un allegato quando un dipendente invia una nuova richiesta di congedo per il tipo di congedo selezionato. 

Ai dipendenti sarà richiesto di caricare un allegato quando inviano una nuova richiesta di congedo con un tipo di congedo in cui il campo **Allegato richiesto** è abilitato. Per visualizzare l'allegato che è stato caricato come parte di una richiesta di congedo, gli approvatori delle richieste di congedo possono utilizzare l'opzione **Allegati** per gli elementi di lavoro loro assegnati. Se si accede a una richiesta di congedo utilizzando l'app Human Resources in Microsoft Teams, l'opzione **Visualizza dettagli** per la richiesta di congedo può essere utilizzata per visualizzarne i dettagli e gli eventuali allegati.

## <a name="configure-leave-units-hoursdays-per-leave-type"></a>Configurare le unità di congedo (ore/giorni) per il tipo di congedo

> [!NOTE]
> Per utilizzare la funzionalità unità di congedo per tipo di congedo, è necessario prima attivare la funzione **Configurare unità di congedo per tipo di congedo** in Gestione funzionalità. Per ulteriori informazioni su come attivare le funzionalità, vedi [Gestire le funzionalità](hr-admin-manage-features.md).

> [!IMPORTANT]
> Per impostazione predefinita, i tipi di congedo in una persona giuridica utilizzano le unità di congedo della configurazione dei parametri di congedo a livello di persona giuridica.
> 
> L'unità di congedo di un tipo di congedo e assenze può essere modificata solo se non sono presenti transazioni di congedo per quel tipo di congedo.
> 
> Una volta attivata, la funzionalità non può essere disattivata.

1. Nella pagina **Congedo e assenza** nella scheda **Collegamenti** sotto **Impostazioni**, seleziona **Tipi di congedo e assenza**.

2. Nell'elenco seleziona un tipo di congedo e assenza. Poi, nella sezione **Generale**, nel campo **Unità** seleziona l'unità di congedo. Puoi selezionare **Ore** o **Giorni**.

3. Facoltativo: se hai selezionato **Ore** nel campo **Unità** puoi usare il campo **Abilita la definizione di mezza giornata** per specificare se i dipendenti possono selezionare la prima mezza giornata o la seconda mezza giornata libera se richiedono una mezza giornata di congedo.

I dipendenti che inviano una nuova richiesta di congedo possono selezionare diversi tipi di congedo per creare la propria richiesta di congedo. Tuttavia, tutti i tipi di congedo selezionati come parte di una singola richiesta di congedo devono avere la stessa unità di congedo. I dipendenti possono visualizzare l'unità di congedo per ogni tipo di congedo nel modulo **Richiedi permesso**.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)
- [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md)
- [Congedo sospeso](hr-leave-and-absence-suspend-leave.md)
- [Creare un flusso di lavoro di richieste di acquisto e vendita di congedi](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
