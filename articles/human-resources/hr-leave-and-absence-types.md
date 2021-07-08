---
title: Configurare tipi di congedo e assenza
description: Impostare i tipi di congedo che i dipendenti possono prendere in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39e4c4b9c83ca648c21ac20bd20b739af8a6b9ed
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271129"
---
# <a name="configure-leave-and-absence-types"></a>Configurare tipi di congedo e assenza

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

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Tipi di congedo e assenza**.

3. Selezionare **Nuovo**.

4. Immettere un nome per il tipo di congedo sotto **Tipo**, selezionare un flusso di lavoro in **ID flusso di lavoro** e immettere una descrizione sotto **Descrizione**.

5. In **Generale**, selezionare **Nessuno**, **Programmato** o **Non programmato** nell'elenco a discesa **Categoria**.

6. Seleziona un codice di reddito nell'elenco a discesa **Codice di reddito**.

7. Sotto **Codice motivo obbligatorio**, scegliere se richiedere un codice motivo o meno. Se si desidera richiedere dei codici motivo, potrebbe essere necessario aggiungerli. Sotto **Codici motivo**, selezionare **Aggiungi**, selezionare un codice motivo, quindi selezionare la casella di controllo **Abilitato** accanto allo stesso.

8. Sotto **Limitare l'accesso a ruoli selezionati**, scegliere se limitare l'accesso. Quindi selezionare i ruoli di sicurezza sotto **Ruoli di sicurezza per questo tipo di congedo**. I ruoli di sicurezza sono definiti nel flusso di lavoro selezionato sotto **ID flusso di lavoro** precedentemente in questa procedura.

9. Sotto **Colore calendario**, scegli il colore da visualizzare nei calendari di congedi e assenze per questo tipo di congedo. 

10. Sotto **Relazioni di sospensione**, scegli se questo tipo di congedo deve sospendere questo tipo di congedo o deve essere sospeso da un altro tipo di congedo. Quando una richiesta di congedo viene inviata per il tipo di congedo che provoca la sospensione, verrà automaticamente creata una sospensione del congedo per il tipo di congedo sospeso. 

10. Selezionare **Salva**.

## <a name="configure-leave-type-rules"></a>Configurare le regole del tipo di congedo

1. Impostare opzioni di arrotondamento per il tipo di congedo. Le opzioni includono **Nessuno**, **Su**, **Giù** e **Al più vicino**. È inoltre possibile impostare la precisione di arrotondamento per il tipo di congedo.

2. Impostare **Correzione giorni festivi** per il tipo di congedo. Quando si seleziona questa opzione, Human Resources utilizza il numero di giorni festivi che cadono in un giorno lavorativo per determinare come accumulare permessi per il tipo di congedo. Ad esempio, se il giorno di Natale cade di lunedì, Human Resources sottrarrà un giorno dal tipo di congedo durante l'elaborazione degli accumuli.

   i giorni festivi sono impostati nel calendario orario lavorativo. Per ulteriori informazioni, vedere [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md).
   
 3. Impostare **Tipo di congedo riportabile** per il tipo di congedo. Quando si seleziona questa opzione, tutti i saldi riportabili verranno trasferiti al tipo di congedo specificato. Anche il tipo di congedo riportabile deve essere incluso nel piano di congedo e assenza. 
 
4. Definire **Regole di scadenza** per il tipo di congedo. Quando si configura questa opzione, è possibile scegliere l'unità di giorni o mesi e impostare la durata per la scadenza. La data di validità della regola di scadenza viene utilizzata per determinare quando avviare l'esecuzione del processo batch che elabora la scadenza del congedo o la data alla quale la regola diventa effettiva. La scadenza stessa avverrà sempre alla data di inizio del periodo di accumulo. Ad esempio, se la data di inizio del periodo di accumulo è il 3 agosto 2021 e la regola di scadenza è stata impostata su 6 mesi, la regola verrà elaborata in base allo scostamento di scadenza dalla data di inizio del periodo di accumulo, quindi verrà eseguita il 3 febbraio, 2022. Eventuali saldi di congedi esistenti al momento della scadenza verranno sottratti dal tipo di congedo e si rifletteranno nel saldo di congedi.
 
## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)
- [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md)
- [Congedo sospeso](hr-leave-and-absence-suspend-leave.md)
- [Creare un flusso di lavoro di richieste di acquisto e vendita di congedi](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
