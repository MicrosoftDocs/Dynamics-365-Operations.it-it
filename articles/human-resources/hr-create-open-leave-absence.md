---
title: Creare una richiesta di congedo a tempo indeterminato
description: Questo articolo spiega come creare un congedo a tempo indeterminato in Microsoft Dynamics 365 Human Resources.
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
ms.openlocfilehash: 08231d4139209387c3c76923fafdd2061fceb280
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805341"
---
# <a name="create-an-open-ended-leave-of-absence"></a>Creare una richiesta di congedo a tempo indeterminato

> [!IMPORTANT]
> La funzionalità descritta in questo articolo sarà disponibile nell'infrastruttura Finance come parte di una futura versione successiva a Microsoft Dynamics 365 Finance versione 10.0.31.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile inviare richieste di congedo a tempo indeterminato e visualizzare lo stato delle richieste di congedo in Dynamics 365 Human Resources.

## <a name="prerequisites"></a>Prerequisiti

1. In **Gestione funzionalità**, assicurati che la funzionalità **Congedo a tempo indeterminato** sia attivata.

    > [!IMPORTANT]
    > Questa funzionalità non può essere disattivata.

2. Creare un tipo di congedo di assenza.
3. Inserisci i dettagli come il tipo di congedo, la descrizione e l'ID del flusso di lavoro.
4. Nel campo **Tipo di richiesta**, seleziona **Richiesta di congedo**.
5. Nella sezione dei dettagli, per i congedi a tempo indeterminato, imposta l'opzione **A tempo indeterminato** su **Sì**.
6. Imposta l'opzione **Preavviso di ritorno al lavoro** su **Sì** o **No**.
7. Per le richieste di congedo a tempo indeterminato può essere richiesto facoltativamente un preavviso di ritorno al lavoro.

> [!NOTE]
> Dopo che questa funzionalità è abilitata, la funzionalità **Allegato richiesto** verrà abilitata.

## <a name="request-an-open-ended-leave-of-absence"></a>Richiedere un congedo a tempo indeterminato

1. Nell'area di lavoro **Self-service dipendenti**, nel riquadro **Saldi permessi**, seleziona **Altro (...)**.
2. Per inviare una richiesta di congedo, seleziona **Richiedi congedo**.
3. Immetti le informazioni per i campi **Tipo di congedo** e **Data di inizio**. Nel campo **Data di fine** immetti una data di fine provvisoria.
4. Se è necessario inviare documentazione di supporto, seleziona **Carica** in **Allegati**.
5. Se sei pronto a inviare la richiesta, seleziona **Invia**. Altrimenti, selezionare **Salva bozza**.
6. Per aggiornare una richiesta di congedo a tempo indeterminato, seleziona la richiesta, inserisci una data di fine nel campo **Data di fine**, imposta l'opzione **Conferma data di fine** su **Sì** e carica la documentazione.
7. Se l'opzione **Preavviso di ritorno al lavoro** è impostata su **Sì**, seleziona **Carica**, quindi seleziona la casella di controllo per confermare che è stato caricato un preavviso di rientro al lavoro valido.
8. Quando tutti i dettagli sono stati inseriti, seleziona **Invia**.
