---
title: Configurare i parametri di congedo e assenza
description: Questo articolo descrive come definire i parametri delle risorse umane per i congedi e le assenze in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
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
ms.openlocfilehash: 3a39c74eef3865c03ccb9dd5aa2fece7f25e639a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891381"
---
# <a name="configure-leave-and-absence-parameters"></a>Configurare i parametri di congedo e assenza

>[!Important]
>La funzionalità indicata in questo articolo è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.


[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Prima di impostare i piani di congedo e assenza in Dynamics 365 Human Resources, è una buona idea verificare le impostazioni per tutti i **parametri delle risorse umane** correlati, tra cui:

- La sequenza numerica per richieste di congedo
- Impostazioni relative alla normativa per il congedo per motivi medici e familiari (FMLA)
- Impostazioni di Self-service dipendenti per richieste di congedo e assenza
- Parametri di congedi e assenze

## <a name="view-and-change-human-resources-parameters"></a>Visualizzare e modificare parametri delle risorse umane

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri Risorse umane**.

3. Nella scheda **Sequenze numeriche**, verificare il **Codice sequenza numerica** per **ID richiesta congedo** e modificare come necessario. Questa impostazione determina la sequenza utilizzata per assegnare automaticamente gli ID alle richieste di congedo.

4. Nella scheda **FMLA**, verificare le impostazioni FMLA e modificare come necessario.

5. Nella scheda **Self-service dipendenti**, indicare se i manager possono immettere richieste di congedo e assenza per conto dei propri dipendenti.

7. Selezionare **Salva**.

>[!IMPORTANT]
>La visualizzazione dei permessi e delle assenze tra le aziende è attualmente in anteprima. È necessario abilitarlo nell'ambiente **Sandbox** per visualizzare l'opzione per congedo e assenza. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).

## <a name="view-and-change-human-resources-shared-parameters"></a>Visualizzare e modificare parametri condivisi delle risorse umane

1. Nella pagina **Gestione personale** selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri condivisi di risorse umane**.

3. Nella scheda **Accesso anticipato**, selezionare **Sì** per **Abilita la visualizzazione dei permessi della società** per consentire la visualizzazione dei permesso di tutta l'azienda.

4. Selezionare **Salva**.

## <a name="view-and-change-leave-and-absence-parameters"></a>Visualizzare e modificare i parametri di congedo e assenza

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.

3. Nella scheda **Generale**, impostare i seguenti parametri:
 
    - Impostare **Unità per ferie e assenze** su ore o giorni. Se in giorni, è possibile selezionare **Abilita la definizione di mezza giornata** per consentire ai dipendenti di scegliere la prima o la seconda metà del giorno nelle richieste di permesso. 

    - Selezionare **Mesi della data di entrata in servizio** per stabilire quando il coefficiente di accumulo diventa effettivo per i piani di congedo che utilizzano mesi di servizio.

    - Selezionare **Calcolo del saldo** per visualizzare i saldi a partire dalla data odierna o dal periodo di competenza. Se viene selezionato **Saldo dalla data odierna**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste all data odierna. Se viene selezionato **Saldo dal periodo di competenza**, il saldo mostra il totale di tutti gli accumuli, rettifiche e richieste dal periodo di competenza definito dalla frequenza nel piano di ferie. 

    - Impostare l'**ora di inizio** per il processo batch con **scadenza di riporto**.  
    
    - Selezionare **Sì** per **Consenti a dipendenti di acquistare congedi** e **Consenti a dipendenti di vendere congedi**. Se si seleziona **Sì** per queste opzioni, è possibile creare criteri di acquisto e vendita di congedi e consentire ai dipendenti di inviare richieste di acquisto e vendita di congedi.

## <a name="configure-calendar-parameters"></a>Configurare i parametri del calendario

1. Nella pagina **Congedo e assenza**, selezionare la scheda **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri di congedo e assenza**.

3. Nella scheda **Calendario**, modificare le impostazioni del calendario come necessario.

4. Selezionare **Salva**.

## <a name="see-also"></a>Vedere anche

- [Panoramica di congedo e assenza](hr-leave-and-absence-overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
