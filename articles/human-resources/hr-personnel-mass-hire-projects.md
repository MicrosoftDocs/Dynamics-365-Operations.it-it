---
title: Progetti di assunzione collettiva
description: I progetti di assunzione collettiva consentono ai responsabili delle risorse umane di creare più posizioni e assumere in modo efficiente i lavoratori per tali posizioni.
author: andreabichsel
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMMassHireProject, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7481
ms.assetid: 5f5eb271-76eb-4305-bd1c-5d171dafccc9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 83937c8aa9edf065e3a22cee9eeea5333341d403
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "5127729"
---
# <a name="mass-hire-projects"></a>Progetti di assunzione collettiva



I progetti di assunzione collettiva consentono ai responsabili delle risorse umane di creare più posizioni e assumere in modo efficiente i lavoratori per tali posizioni.

## <a name="overview"></a>Panoramica

Quando si assumono più lavoratori contemporaneamente, ad esempio per soddisfare una domanda stagionale, utilizzare progetti di assunzione collettiva. La creazione del progetto di assunzione collettiva è utile poiché è possibile creare record per le posizioni, i lavoratori e le assegnazioni dei lavoratori per le posizioni contemporaneamente. Quando si creano posizioni per un progetto di assunzione collettiva, è possibile specificare le seguenti informazioni:

- Numero di posizioni da creare
- Il tipo di lavoratore per le persone che saranno assunte per le posizioni
- Il reparto e la mansione associati alle posizioni
- Il valore equivalente al tempo pieno della posizione

## <a name="example"></a>Esempio

In estate, in genere si assumono 15-20 studenti universitari part-time per coprire le posizioni interne disponibili nella società. Quest'anno, si desidera assumere cinque ragionieri, cinque elaboratori di ordini e cinque cassieri. Anziché creare ogni record lavoratore e ogni record di posizione separatamente, creare un progetto di assunzione collettiva denominato "SummerInterns". Le date di inizio e di fine del progetto sono correlate alle date di inizio e di fine delle durate delle posizioni create per il progetto di assunzione collettiva.

Nella pagina **Progetti di assunzione collettiva** selezionare il progetto "SummerInterns", quindi fare clic su **Apri progetto**. Nel progetto di assunzione collettiva aperto, fare clic su **Crea posizioni** e immettere le informazioni sulla posizione contabile. È possibile indicare che si desidera creare cinque posizioni contabili che utilizzano le stesse informazioni e quindi fare clic su OK. Ripetere questo processo per le posizioni di elaboratore di ordini e di cassiere.

Dopo aver selezionato gli studenti da assumere per le posizioni interne, immettere le informazioni degli studenti in **Dettagli posizioni** per la posizione per cui vengono assunti. Dopo aver immesso in tutti i dettagli della posizione, selezionare la posizione nella pagina Progetti di assunzione collettiva, quindi fare clic su **Assumi**. Un record posizione verrà creato per ogni posizione e un record lavoratore verrà creato e assegnato alla posizione corretta per ogni persona che si assume.

## <a name="mass-hire-project-statuses"></a>Stati del progetto di assunzione collettiva

Un progetto di assunzione collettiva può includere i seguenti stati.

- Creata
- Aperto
- Chiuso

Nella pagina **Progetto di assunzione collettiva** fare clic su **Apri progetto** o **Chiudi progetto** per modificare lo stato di un progetto di assunzione collettiva. Nella tabella riportata di seguito sono descritte le operazioni che è possibile effettuare in un progetto in base al relativo stato.

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
<td>Non è possibile aggiungere posizioni al progetto. Per aggiungere posizioni al progetto di assunzione collettiva, aprire di nuovo il progetto. Questo è lo stato dei progetti completati.
<blockquote>[!NOTE] Prima di chiudere un progetto di assunzione collettiva, a tutte le posizioni del progetto deve essere assegnato lo stato Creato o Chiuso.</blockquote>
</td>
</tr>
</tbody>
</table>
