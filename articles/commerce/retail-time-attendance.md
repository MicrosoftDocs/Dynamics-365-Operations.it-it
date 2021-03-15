---
title: Gestione di Orario e presenze in Retail
description: In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Dynamics 365 Commerce.
author: aamirallaqaband
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: JMGParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: e28df09ecb592ae7df360d1b2d0bf06339c1410d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989379"
---
# <a name="time-and-attendance-management-in-retail"></a>Gestione di Orario e presenze in Retail

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Dynamics 365 Commerce.

## <a name="manage-worker-setup-and-scheduling"></a>Gestire l'impostazione e la programmazione dei lavoratori

### <a name="initial-configuration"></a>Configurazione iniziale

- Eseguire la Configurazione guidata.
- Registrare i lavoratori come lavoratori per registrazione ore

### <a name="plan-worker-schedules"></a>Pianificare le programmazioni del lavoratore

- Applicare profili utilizzando Pianificazione lavori. Per ulteriori informazioni, vedere [Applicare profili utilizzando Pianificazione lavori](https://technet.microsoft.com/library/aa551234.aspx).

Per informazioni sui passaggi di configurazione, vedere [Impostazione di orari e presenze](https://technet.microsoft.com/library/aa496971.aspx).

### <a name="commerce-specific-configuration"></a>Configurazione specifica per il commercio

- Attivare un profilo funzionalità per l'orologio per i lavoratori per cui si desidera consentire le registrazioni ore. Fare clic su **Profili funzionalità POS** &gt; **Funzioni** &gt; **Registrazioni ore POS** &gt; **Abilita registrazioni ore**.
- Configurare i gruppi di autorizzazioni POS per abilitare l'autorizzazione Visualizza voci orologio. Tale autorizzazione consente la visualizzazione delle registrazioni delle voci di entrata/uscita di altri lavoratori del punto vendita (e di qualsiasi altro punto vendita a cui l'utente è associato, tramite la Rubrica). È consigliabile consentire l'autorizzazione per un ruolo di amministratore, ma non per un ruolo di cassiere. Fare clic su **Gruppi di autorizzazioni POS** &gt; **Visualizza voci orologio**.

## <a name="register-time"></a>Ora registrazione

### <a name="cashier-and-non-cashier-time-registrations"></a>Registrazioni ore cassieri e ruoli diversi dal cassiere

- Nel POS:

    - Operazioni di entrata:

        - Accedere a un'operazione non relativa al cassetto o di nuovo turno.
        - Selezionare un'operazione di orologio.
        - Selezionare un'operazione desiderata:

            - Entrata
            - Pausa dal lavoro
            - Pausa pranzo
            - Uscita

        <table>
        <thead>
        <tr>
        <th>Stato corrente</th>
        <th>Operazioni disponibili</th>
        </tr>
        </thead>
        <tbody>
        <tr>
        <td>Entrata</td>
        <td>
        <ul>
        <li>Pausa dal lavoro</li>
        <li>Pausa pranzo</li>
        <li>Uscita</li>
        </ul>
        </td>
        </tr>
        <tr>
        <td>Pausa dal lavoro</td>
        <td>Entrata</td>
        </tr>
        <tr>
        <td>Pausa pranzo</td>
        <td>Entrata</td>
        </tr>
        <tr>
        <td>Uscita</td>
        <td>Entrata</td>
        </tr>
        </tbody>
        </table>

        [![Stati dell'orologio](./media/timeclockstates.png)](./media/timeclockstates.png)

- Consente di visualizzare il messaggio di conferma e di convalidare come corretto l'orario dell'attività corrente.
- Registro:

    - Fare clic su **Registro** per visualizzare l'attività di orologio.
    - Utilizzare i filtri orari per per selezionare intervalli di tempo diversi.
    - Se si lavora in più ubicazioni del punto di vendita, è possibile visualizzare le registrazioni ore da tutti i punti vendita in cui le ore sono state registrate. È possibile utilizzare il filtro di punti vendita per visualizzare le registrazioni ore da un punto vendita selezionato.

- Fusi orari diversi:

    - Se si visualizza l'ora da un'ubicazione diversa (per il registro del cassiere o tramite l'opzione **Visualizza voci orologio** per uno scenario di amministratore) e tale ubicazione si trova in fuso orario diverso, i record orari vengono convertiti nel fuso orario locale. Ad esempio, si è un responsabile per due punti vendita, uno in Arizona e l'altro in Nevada. Un cassiere registra l'entrata alle 9.00 del mattino in Arizona. In quel momento in Nevada sono le 8.00. Di conseguenza, per il responsabile del punto vendita in Nevada i record orari riportano 8.00 come ora di registrazione.

## <a name="view-worker-time-registrations"></a>Visualizzare le registrazioni ore dei lavoratori

### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Visualizzare le registrazioni ore del lavoratore e filtrare per punto vendita o tipo di attività

Nel POS:

- Selezionare **Visualizza voci orologio**.
- Vengono visualizzate tutte le attività di registrazione orologio di tutti i lavoratori assegnati agli stessi punti vendita a cui è assegnato l'utente.
- È possibile utilizzare i filtri per tipo di attività e punto vendita per filtrare le registrazioni ore.

## <a name="process-and-manage-time-registrations"></a>Elaborare e gestire le registrazioni ore

Un utente di Commerce segue il flusso di lavoro per calcolare, approvare e trasferire le registrazioni ore alle retribuzioni.

### <a name="primary-operations"></a>Operazioni primarie

- Calcola
- Approva
- Inviare a retribuzioni

### <a name="other-common-operations"></a>Altre operazioni comuni

- Uscita in blocco
- Registrare le assenze

Per ulteriori informazioni su come elaborare le registrazioni di orari e presenze, vedere [Elaborare le registrazioni in Orario e presenze](https://technet.microsoft.com/library/aa573180.aspx).


[!INCLUDE[footer-include](../includes/footer-banner.md)]