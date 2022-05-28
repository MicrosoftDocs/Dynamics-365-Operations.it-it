---
title: Progetti di assunzione collettiva
description: Questo argomento descrive i progetti di assunzione collettiva che consentono ai responsabili delle risorse umane di creare più posizioni e assumere in modo efficiente i lavoratori per tali posizioni.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ecc181f21c1502b8174765af5a2f2ef738e8477
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717001"
---
# <a name="mass-hire-projects"></a>Progetti di assunzione collettiva


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



I progetti di assunzione collettiva consentono ai responsabili delle risorse umane di creare più posizioni e assumere in modo efficiente i lavoratori per tali posizioni.

## <a name="overview"></a>Panoramica

Quando si assumono più lavoratori contemporaneamente, ad esempio per soddisfare una domanda stagionale, utilizzare progetti di assunzione collettiva. La creazione del progetto di assunzione collettiva è utile poiché è possibile creare record per le posizioni, i lavoratori e le assegnazioni dei lavoratori per le posizioni contemporaneamente. Quando si creano posizioni per un progetto di assunzione collettiva, è possibile specificare le seguenti informazioni:

- Numero di posizioni da creare
- Il tipo di lavoratore per le persone che saranno assunte per le posizioni
- Il reparto e la mansione associati alle posizioni
- Il valore equivalente al tempo pieno della posizione

## <a name="example"></a>Esempio

In estate, in genere si assumono 15-20 studenti universitari part-time per coprire le posizioni interne disponibili nella società. Quest'anno, si desidera assumere cinque ragionieri, cinque elaboratori di ordini e cinque cassieri. Anziché creare ogni record lavoratore e ogni record di posizione separatamente, creare un progetto di assunzione collettiva denominato "SummerInterns". Le date di inizio e di fine del progetto sono correlate alle date di inizio e di fine delle durate delle posizioni create per il progetto di assunzione collettiva.

Nella pagina **Progetti di assunzione collettiva** seleziona il progetto **SummerInterns**, quindi seleziona **Apri progetto**. Nel progetto di assunzione collettiva aperto, seleziona **Crea posizioni** e immetti le informazioni sulla posizione contabile. È possibile indicare che si desidera creare cinque posizioni contabili che utilizzano le stesse informazioni. Selezionare **OK**. Ripetere questo processo per le posizioni di elaboratore di ordini e di cassiere.

Dopo aver selezionato gli studenti da assumere per le posizioni interne, immetti le informazioni degli studenti in Dettagli posizioni per la posizione per cui vengono assunti. Dopo aver immesso in tutti i dettagli della posizione, selezionare la posizione nella pagina **Progetti di assunzione collettiva**, quindi selezionare **Assumi**. Un record posizione verrà creato per ogni posizione e un record lavoratore verrà creato e assegnato alla posizione corretta per ogni persona che si assume.

## <a name="mass-hire-project-statuses"></a>Stati del progetto di assunzione collettiva

Un progetto di assunzione collettiva può includere i seguenti stati.

- Data creazione
- Apri
- Chiuso

Nella pagina **Progetto di assunzione collettiva** selezionare **Apri progetto** o **Chiudi progetto** per modificare lo stato di un progetto di assunzione collettiva. Nella tabella riportata di seguito sono descritte le operazioni che è possibile effettuare in un progetto in base al relativo stato.

<table>
<thead>
<tr>
<th>Stato</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Creata</td>
<td>È possibile creare e modificare informazioni, ma non creare posizioni per il progetto. Questo è lo stato predefinito dei nuovi progetti.</td>
</tr>
<tr>
<td>Aperto</td>
<td>È possibile modificare i dettagli del progetto, creare posizioni per il progetto di assunzione collettiva e assumere le persone per le posizioni. Questo è lo stato dei progetti attivi.</td>
</tr>
<tr>
<td>Chiuso</td>
<td><p>Non è possibile aggiungere posizioni al progetto. Per aggiungere posizioni al progetto di assunzione collettiva, aprire di nuovo il progetto. Questo è lo stato dei progetti completati.</p>
<p><strong>Nota:</strong> prima di chiudere un progetto di assunzione collettiva, a tutte le posizioni del progetto deve essere assegnato lo stato <b>Creato</b> o <b>Chiuso</b>.</p>
</td>
</tr>
</tbody>
</table>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
