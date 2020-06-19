---
title: Configurare i parametri di congedo e assenza
description: Definire i parametri delle risorse umane per congedo e assenza in Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e4d3b3e4b373631bed5e2d7e3c3a4e14f0c5c98
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "3428946"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurare i parametri di congedo e assenza

Prima di impostare i piani di congedo e assenza in Dynamics 365 Human Resources, è una buona idea verificare le impostazioni per tutti i parametri delle risorse umane correlati, tra cui:

- La sequenza numerica per richieste di congedo
- Impostazioni relative alla normativa per il congedo per motivi medici e familiari (FMLA)
- Impostazioni di Dipendente self-service per richieste di congedo e assenza
- Parametri di congedi e assenze

## <a name="view-and-change-human-resources-parameters"></a>Visualizzare e modificare parametri delle risorse umane

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri Risorse umane**.

3. Nella scheda **Sequenze numeriche**, verificare il **Codice sequenza numerica** per **ID richiesta congedo** e modificare come necessario. Questa impostazione determina la sequenza utilizzata per assegnare automaticamente gli ID alle richieste di congedo.

4. Nella scheda **FMLA**, verificare le impostazioni FMLA e modificare come necessario.

5. Nella scheda **Dipendente self-service**, indicare se i manager possono immettere richieste di congedo e assenza per conto dei propri dipendenti.

6. Nella scheda **Congedo e assenza**, verificare le impostazioni e modificare come necessario.

7. Selezionare **Salva**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Visualizzare e modificare i parametri di congedo e assenza

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.

3. Nella scheda **Generale**, impostare i seguenti parametri:
 
    - Impostare **Unità per ferie e assenze** su ore o giorni. Se in giorni, è possibile selezionare **Abilita la definizione di mezza giornata** per consentire ai dipendenti di scegliere la prima o la seconda metà del giorno nelle richieste di permesso. 

    - Selezionare **Mesi della data di entrata in servizio** per stabilire quando il coefficiente di accumulo diventa effettivo per i piani di congedo che utilizzano mesi di servizio.

    - Selezionare **Calcolo del saldo** per visualizzare i saldi visualizzati a partire dalla data odierna o dal periodo di competenza. Se viene selezionato **Saldo dalla data odierna**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste all data odierna. Se viene selezionato **Saldo dal periodo di competenza**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste dal periodo di competenza definito dalla frequenza nel piano di ferie. 

## <a name="configure-calendar-parameters"></a>Configurare i parametri del calendario

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.

3. Nella scheda **Calendario**, modificare le impostazioni del calendario come necessario.

4. Selezionare **Salva**.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)
