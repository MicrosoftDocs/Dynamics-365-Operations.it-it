---
title: Creare un calendario di team
description: Visualizzare e creare calendari di team in Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2ec767a868d5c76b57465c451b8cc893b8b0a56b
ms.sourcegitcommit: ffb5998e611b83c2e4f98323f39e3e8f6419c652
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/02/2020
ms.locfileid: "4419285"
---
# <a name="view-team-and-company-calendars"></a>Visualizzare i calendari per team e società

È possibile visualizzare calendari di team e società in Dynamics 365 Human Resources. I calendari di team visualizzano solo i report diretti, come definito nella gerarchia di righe.

## <a name="view-your-team-calendar-as-an-employee"></a>Visualizzare il calendario del team come dipendente

1. Nell'area di lavoro **Self-service dipendenti**, selezionare **Calendario assenze team** in **Riepilogo**.

## <a name="view-your-team-calendar-as-a-manager"></a>Visualizzare il calendario del team come responsabile

1. Nell'area di lavoro **Self-service dipendenti**, selezionare **Team personale**.

2. Selezionare **Congedo e assenza**, quindi selezionare **Visualizza calendario assenze responsabile**.

I responsabili possono accedere al calendario del team anche da **Richieste di permesso in sospeso per il team**, **Permesso approvato** e **Richieste di permesso**. 

## <a name="view-a-company-calendar"></a>Visualizzare un calendario di società

Le persone che ricoprono ruoli nelle risorse umane possono visualizzare calendari di società. I calendari di società visualizzano tutti i dipendenti. Per impostazione predefinita, il calendario visualizza la data odierna più 28 giorni, ma è possibile modificare l'intervallo di date. Puoi anche filtrare il calendario per **Nome**, **Numero dipendente** e **Tipo di congedo**.

1. Nell'area di lavoro **Congedo e assenza**, selezionare **Collegamenti**.

2. Selezionare **Calendario congedo e assenza**.

I ruoli di Human resources possono anche accedere al calendario aziendale da **Richieste di congedo e assenza**, **Permesso approvato** e **Richieste di permesso**. 

I calendari ora contengono filtri e opzioni aggiuntive. Tutti i calendari includono opzioni di visualizzazione per:

- Richieste approvate
- Richieste in sospeso
- Dipendenti con richieste di congedo
- Dipendenti senza richieste di congedo
- Compleanni dei dipendenti
- Richieste di tempo libero 
- Richieste di congedo

La configurazione del calendario nei parametri di congedo e assenza determina le opzioni di visualizzazione disponibili.

È anche possibile filtrare i calendari per responsabile o reparto. L'assegnazione della posizione principale determina i dipendenti visualizzati quando vengono impostati questi filtri. 

>[!IMPORTANT]
>La visualizzazione dei permessi e delle assenze tra le aziende è attualmente in anteprima. È necessario abilitarla nell'ambiente **Sandbox**. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).<br><br>
>Quindi è necessario abilitare la funzione in **Parametri condivisi delle risorse umane** per visualizzare il filtro della persona giuridica nei calendari. Per ulteriori informazioni, vedere [Configurare i parametri di congedo e assenza](hr-leave-and-absence-parameters.md).<br><br>
>È possibile filtrare il calendario per persona giuridica. Se si desidera visualizzare tutti i dipendenti indipendentemente dalla persona giuridica, deselezionare la casella del filtro e selezionare Invio. 

Per informazioni sulle impostazioni del calendario, vedere [Configurare i parametri del calendario](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

