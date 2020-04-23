---
title: Configurare tipi di congedo e assenza
description: Impostare i tipi di congedo che i dipendenti possono prendere in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: df6e34fe6a23e6f0a8307a035752a35a15a3431c
ms.sourcegitcommit: 79f8aa2c0b166a423db9b8503da53e96e3fc43dc
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2020
ms.locfileid: "3198052"
---
# <a name="configure-leave-and-absence-types"></a>Configurare tipi di congedo e assenza

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

6. Seleziona un codice di reddito nell'elenco a discesa**Codice di reddito**.

7. Sotto **Codice motivo obbligatorio**, scegliere se richiedere un codice motivo o meno. Se si desidera richiedere dei codici motivo, potrebbe essere necessario aggiungerli. Sotto **Codici motivo**, selezionare **Aggiungi**, selezionare un codice motivo, quindi selezionare la casella di controllo **Abilitato** accanto allo stesso.

8. Sotto **Limitare l'accesso a ruoli selezionati**, scegliere se limitare l'accesso. Quindi selezionare i ruoli di sicurezza sotto **Ruoli di sicurezza per questo tipo di congedo**. I ruoli di sicurezza sono definiti nel flusso di lavoro selezionato sotto **ID flusso di lavoro** precedentemente in questa procedura.

9. Selezionare **Salva**.

## <a name="configure-leave-type-rules"></a>Configurare le regole del tipo di congedo

1. Impostare opzioni di arrotondamento per il tipo di congedo. Le opzioni includono **Nessuno**, **Su**, **Giù** e **Al più vicino**. È inoltre possibile impostare la precisione di arrotondamento per il tipo di congedo.

2. Impostare **Correzione giorni festivi** per il tipo di congedo. Quando si seleziona questa opzione, Human Resources utilizza il numero di giorni festivi che cadono in un giorno lavorativo per determinare come accumulare permessi per il tipo di congedo. Ad esempio, se il giorno di Natale cade di lunedì, Human Resources sottrarrà un giorno dal tipo di congedo durante l'elaborazione degli accumuli.

   i giorni festivi sono impostati nel calendario orario lavorativo. Per ulteriori informazioni, vedere [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md).
   
## <a name="configure-preview-features"></a>Configurare funzionalità di anteprima

Se le funzionalità di anteprima per Congedo e assenza sono state abilitate, è necessario configurare le impostazioni anche per tali funzionalità.

[!include [banner](includes/preview-feature-leave-absence.md)]

1. Scegliere il tipo di congedo per i saldi del riporto in cui vengono trasferiti. È anche possibile creare un nuovo tipo di congedo per il riporto. 

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
- [Creare un piano di congedo e assenza](hr-leave-and-absence-plans.md)
- [Creare un calendario orario di lavoro](hr-leave-and-absence-working-time-calendar.md)
