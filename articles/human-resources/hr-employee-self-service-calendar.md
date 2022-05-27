---
title: Creare un calendario di team
description: Visualizzare e creare calendari di team in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0679a69b4d607f9d466474026d5dd0ceef0dad6f
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8692200"
---
# <a name="view-team-and-company-calendars"></a>Visualizzare i calendari per team e società

>[!Important]
>La funzionalità indicata in questo argomento è attualmente disponibile per i clienti di Dynamics 365 Human Resources standalone. Alcune o tutte le funzionalità saranno disponibili come parte di una versione futura dell'infrastruttura Finance dopo la versione Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile visualizzare calendari di team e società in Dynamics 365 Human Resources. I calendari di team visualizzano solo i report diretti, come definito nella gerarchia di righe.

## <a name="view-your-team-calendar-as-an-employee"></a>Visualizzare il calendario del team come dipendente

- Nell'area di lavoro **Self-service dipendenti**, selezionare **Calendario assenze team** in **Riepilogo**.

## <a name="view-your-team-calendar-as-a-manager"></a>Visualizzare il calendario del team come responsabile

1. Nell'area di lavoro **Self-service dipendenti**, selezionare **Team personale**.

2. Selezionare **Congedo e assenza**, quindi selezionare **Visualizza calendario assenze responsabile**.

I responsabili possono accedere al calendario del team anche da **Richieste di permesso in sospeso per il team**, **Permesso approvato** e **Richieste di permesso**. 

## <a name="view-your-absence-manager-calendar-as-the-absence-manager"></a>Visualizzare il calendario del responsabile dei congedi come responsabile dei congedi

> [!NOTE]
> Per visualizzare il calendario del responsabile dei congedi devi prima attivare la funzionalità **(Anteprima) Responsabile dei congedi per la gestione dei congedi** in Gestione funzionalità. Per ulteriori informazioni su come attivare le funzionalità di anteprima, vedi [Gestire le funzionalità](hr-admin-manage-features.md).

Gli utenti con il ruolo di responsabile dei congedi possono visualizzare le richieste di permessi nel proprio calendario. Per accedere al calendario dei congedi segui questi passaggi.

1. Nell'area di lavoro **Self-service dipendenti** seleziona **Gestone dei congedi** e **Calendario responsabile dei congedi**.

2. Immetti la data desiderata nel campo **Data**.

3. Aggiorna le opzioni di visualizzazione come richiesto.

Il calendario del responsabile dei congedi mostra tutti i record per i dipendenti che riportano al responsabile dei congedi nella gerarchia dei congedi.

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

La configurazione del calendario nella pagina **Parametri di congedo e assenza** determina le opzioni di visualizzazione disponibili.

È anche possibile filtrare i calendari per responsabile o reparto. L'assegnazione della posizione principale determina i dipendenti visualizzati quando vengono impostati questi filtri. 

> [!IMPORTANT]
> Puoi attivare la funzionalità **visualizzazione congedo interaziendale** in Gestione funzionalità. È necessario abilitare la funzione nella pagina **Parametri condivisi delle risorse umane** per visualizzare il filtro della persona giuridica nei calendari. Per ulteriori informazioni, vedere [Configurare i parametri di congedo e assenza](hr-leave-and-absence-parameters.md).
> 
> È possibile filtrare il calendario per persona giuridica. Per visualizzare tutti i dipendenti indipendentemente dalla persona giuridica, deseleziona la casella del filtro e seleziona **Invio**. 

Per informazioni sulle impostazioni del calendario, vedere [Configurare i parametri del calendario](hr-leave-and-absence-parameters.md?configure-calendar-parameters).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
