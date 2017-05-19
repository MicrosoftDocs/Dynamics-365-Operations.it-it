---
title: Orario e presenze nella vendita al dettaglio
description: In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Microsoft Dynamics 365 for Operations - Retail.
author: MargoC
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 62813
ms.assetid: 821994a6-cd29-45a3-a526-ce204064f080
ms.search.region: global
ms.search.industry: Retail
ms.author: aamiral
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 6b1f91f863c8da35362ebb3036e76aa10d95ba65
ms.openlocfilehash: f256839e1fad810e24d2ed95a933fbeacee4722b
ms.contentlocale: it-it
ms.lasthandoff: 04/26/2017


---

# <a name="retail-time-and-attendance"></a>Orario e presenze nella vendita al dettaglio

[!include[banner](includes/banner.md)]


In questo argomento vengono descritti gli scenari supportati per la gestione di orario e presenze in Microsoft Dynamics 365 for Operations - Retail. 

<a name="manage-worker-setup-and-scheduling"></a>Gestire l'impostazione e la programmazione dei lavoratori
----------------------------------

### <a name="initial-configuration"></a>Configurazione iniziale

-   Eseguire la Configurazione guidata.
-   Registrare i lavoratori come lavoratori per registrazione ore

### <a name="plan-worker-schedules"></a>Pianificare le programmazioni del lavoratore

-   Applicare profili utilizzando Pianificazione lavori. Per ulteriori informazioni, vedere <https://technet.microsoft.com/en-us/library/aa551234.aspx>.

Per informazioni sui passaggi di configurazione, vedere <https://technet.microsoft.com/en-us/library/aa496971.aspx>.

### <a name="retail-specific-configuration"></a>Configurazione specifica per la vendita al dettaglio

-   Attivare un profilo funzionalità per l'orologio per i lavoratori per cui si desidera consentire le registrazioni ore. Fare clic su **Profili funzionalità POS** &gt; **Funzioni** &gt; **Registrazioni ore POS** &gt; **Abilita registrazioni ore**.
-   Configurare i gruppi di autorizzazioni POS per abilitare l'autorizzazione Visualizza voci orologio. Tale autorizzazione consente la visualizzazione delle registrazioni delle voci di entrata/uscita di altri lavoratori del punto vendita (e di qualsiasi altro punto vendita a cui l'utente è associato, tramite la Rubrica). È consigliabile consentire l'autorizzazione per un ruolo di amministratore, ma non per un ruolo di cassiere. Fare clic su **Gruppi di autorizzazioni POS** &gt; **Visualizza voci orologio**.

## <a name="register-time"></a>Ora registrazione
### <a name="cashier-and-non-cashier-time-registrations"></a>Registrazioni ore cassieri e ruoli diversi dal cassiere

-   Nel POS:
    -   Operazioni di entrata:
        -   Accedere a un'operazione non relativa al cassetto o di nuovo turno.
        -   Selezionare un'operazione di orologio.
        -   Selezionare un'operazione desiderata:
            -   Entrata
            -   Pausa dal lavoro
            -   Pausa pranzo
            -   Uscita

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>Stato corrente</th>
    <th>Operazioni disponibili</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>Entrata</td>
    <td><ul>
    <li>Pausa dal lavoro</li>
    <li>Pausa pranzo</li>
    <li>Uscita</li>
    </ul></td>
    </tr>
    <tr class="even">
    <td>Pausa dal lavoro</td>
    <td>Entrata</td>
    </tr>
    <tr class="odd">
    <td>Pausa pranzo</td>
    <td>Entrata</td>
    </tr>
    <tr class="even">
    <td>Uscita</td>
    <td>Entrata</td>
    </tr>
    </tbody>
    </table>

    [![TimeClockStates](./media/timeclockstates.png)](./media/timeclockstates.png)
-   Consente di visualizzare il messaggio di conferma e di convalidare come corretto l'orario dell'attività corrente.
-   Registro:
    -   Fare clic su **Registro** per visualizzare l'attività di orologio.
    -   Utilizzare i filtri orari per per selezionare intervalli di tempo diversi.
    -   Se si lavora in più ubicazioni del punto di vendita, è possibile visualizzare le registrazioni ore da tutti i punti vendita in cui le ore sono state registrate. È possibile utilizzare il filtro di punti vendita per visualizzare le registrazioni ore da un punto vendita selezionato.

<!-- -->

-   Fusi orari diversi:
    -   Se si visualizza l'ora da un'ubicazione diversa (per il registro del cassiere o tramite l'opzione **Visualizza voci orologio** per uno scenario di amministratore) e tale ubicazione si trova in fuso orario diverso, i record orari vengono convertiti nel fuso orario locale. Ad esempio, si è un responsabile per due punti vendita, uno in Arizona e l'altro in Nevada. Un cassiere registra l'entrata alle 9.00 del mattino in Arizona. In quel momento in Nevada sono le 8.00. Di conseguenza, per il responsabile del punto vendita in Nevada i record orari riportano 8.00 come ora di registrazione.

## <a name="view-worker-time-registrations"></a>Visualizzare le registrazioni ore dei lavoratori
### <a name="view-worker-time-registrations-and-filter-by-store-or-activity-type"></a>Visualizzare le registrazioni ore del lavoratore e filtrare per punto vendita o tipo di attività

Nel POS:

-   Selezionare **Visualizza voci orologio**.
-   Vengono visualizzate tutte le attività di registrazione orologio di tutti i lavoratori assegnati agli stessi punti vendita a cui è assegnato l'utente.
-   È possibile utilizzare i filtri per tipo di attività e punto vendita per filtrare le registrazioni ore.

## <a name="process-and-manage-time-registrations"></a>Elaborare e gestire le registrazioni ore
Un utente di Dynamics 365 for Operations - Retail segue il flusso di lavoro per calcolare, approvare e trasferire le registrazioni ore alle retribuzioni.

### <a name="primary-operations"></a>Operazioni primarie

-   Calcola
-   Approva
-   Inviare a retribuzioni

### <a name="other-common-operations"></a>Altre operazioni comuni

-   Uscita in blocco
-   Registrare le assenze

Per ulteriori informazioni su come elaborare le registrazioni di orari e presenze, vedere <https://technet.microsoft.com/en-us/library/aa573180.aspx>.




