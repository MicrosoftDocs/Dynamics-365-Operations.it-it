---
title: Tenere traccia delle provvigioni nel POS utilizzando gruppi di vendite
description: È pratica comune nella vendita al dettaglio tenere traccia delle vendite di un assistente che ha lavorato con il cliente fornendo assistenza, eseguendo l'up-selling ed elaborando la transazione.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.industry: Retail
ms.openlocfilehash: 5a5cdf57d8c920b105e7f4a457b064cb2ceba242
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272797"
---
# <a name="track-commissions-in-the-point-of-sale-pos-by-using-sales-groups"></a>Tenere traccia delle provvigioni nel POS utilizzando gruppi di vendite

[!include [banner](includes/banner.md)]

È pratica comune nella vendita al dettaglio tenere traccia delle vendite di un assistente che ha lavorato con il cliente fornendo assistenza, eseguendo l'up-selling e il cross-selling ed elaborando la transazione.

La traccia delle vendite per rappresentante è una misura dell'abilità di vendita dell'assistente alla vendita, mentre le vendite per cassiere è una misura della velocità e di efficienza. La traccoa delle vendite per rappresentante viene spesso utilizzata anche per il calcolo delle provvigioni o altri incentivi.

## <a name="configuring-a-worker-to-be-a-sales-representative-in-pos"></a>Configurazione di un lavoratore come rappresentante di vendita nel POS

Quando un lavoratore viene aggiunto a un gruppo di vendite, diventa idoneo per la provvigione e può essere identificato come rappresentante di vendita nel sistema. Un lavoratore che non è incluso in un gruppo di vendite non è idoneo per la provvigione e non verrà elencato come rappresentante di vendita dell'applicazione POS. Nel POS, l'elenco dei rappresentanti viene derivato da tutti i gruppi vendite contenenti almeno un lavoratore assegnato al punto vendita. L'elenco viene visualizzato nel POS come combinazione di ID gruppo vendite e Nome (ID : Nome). Un gruppo di vendite predefinito può essere assegnato ai lavoratori per supportare scenari in cui il rivenditore sceglie di impostare automaticamente il rappresentante nelle righe POS. Gli utenti possono effettuare selezioni da qualsiasi gruppo vendite di cui il lavoratore è membro.

## <a name="functionality-profile-settings"></a>Impostazioni profili di funzionalità

Sono presenti una serie di impostazioni di profili di funzionalità per un punto vendita che determinerà il flusso e il processo in POS che coinvolgono i rappresentanti.

<table>
<thead>
<tr>
<th>Profilo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr>
<td>Valore predefinito impostato su cassiere, se disponibile</td>
<td>Se l'opzione è abilitata, il POS popola automaticamente le righe di transazione con il gruppo vendite predefinito del cassiere corrente. Se un cassiere non ha un gruppo vendite predefinito specificato, il valore non verrà impostato. Un utente può comunque impostare manualmente il gruppo vendite tramite un pulsante della griglia dei pulsanti POS.</td>
</tr>
<tr>
<td>Richiesta per il rappresentante</td>
<td>Questa opzione ha tre valori possibili:
<ul>
<li><strong>No</strong> – Se è selezionata questa opzione, all'utente non verrà chiesto di selezionare un gruppo vendite. Il valore può comunque essere impostato utilizzando il gruppo vendite predefinito di un cassiere o manualmente tramite un pulsante della griglia dei pulsanti POS.</li>
<li><strong>Inizio della transazione</strong> – Se questa opzione è selezionata e l'opzione <strong>Valore predefinito impostato su cassiere</strong> non è abilitata o il cassiere corrente non è associato a un gruppo di vendite predefinito, all'utente verrà chiesto di selezionare un gruppo vendite all'inizio di ciascuna transazione. Se si seleziona il gruppo di vendite da questo prompt, tutte le righe successive assumerano come valore predefinito il gruppo di vendite selezionato. Un utente può comunque impostare manualmente il gruppo vendite tramite un pulsante della griglia dei pulsanti POS.</li>
<li><strong>Per ogni riga</strong> – Se questa opzione è selezionata e l'opzione <strong>Valore predefinito impostato su cassiere</strong> non è abilitata o il cassiere corrente non è associato a un gruppo di vendite predefinito, all'utente verrà chiesto di selezionare un gruppo vendite dopo l'aggiunta di ogni riga. Un utente può comunque impostare manualmente il gruppo vendite tramite un pulsante della griglia dei pulsanti POS.</li>
</ul>
</td>
</tr>
<tr>
<td>Richiedi</td>
<td>Questa opzione può essere utilizzata solo quando il POS è configurato per richiedere un rappresentante. Se abilitata, all'utente verrà chiesto di selezionare un gruppo vendite prima di continuare. In caso contrario, all'utente verrà chiesto, ma può annullare e continuare senza effettuare una selezione. Dopo che la riga viene aggiunta, un utente con autorizzazioni sufficienti può comunque rimuovere il gruppo vendite dalla riga. "Richiedi rappresentante" non viene applicato in questo caso.</td>
</tr>
</tbody>
</table>

## <a name="displaying-the-sales-representative-information-on-the-pos-transactions-screen"></a>Visualizzazione delle informazioni relative al rappresentante sullo schermo delle transazioni POS

Il layout e il contenuto dello schermo della transazione POS sono configurabili mediante la funzionalità di progettazione layout dello schermo e layout dello schermo assegnati a punti vendita, registratori di cassa o lavoratori. Il campo **Rappresentante** può essere aggiunto alla scheda Righe del riquadro Entrata.  Ciò visualizzerà l'ID del gruppo di vendite specificato per ogni riga sullo schermo di transazione.

## <a name="adding-sales-representative-operations-to-pos-button-grids"></a>Aggiunta delle operazioni di un rappresentante alle griglie di pulsanti POS

Il POS consente agli utenti di configurare griglie dei pulsanti, comprese nei layout dello schermo per fornire l'accesso alle operazioni POS. Le seguenti operazioni POS possono essere assegnate ai pulsanti della griglia di pulsanti relativi ai rappresentanti.

| Operazione                                 | Descrizione |
|-------------------------------------------|-------------|
| Imposta rappresentante su riga          | L'operazione POS visualizza un elenco di gruppi di vendite idonei (UD : Nome) per il punto vendita. Se si seleziona un gruppo di vendite dall'elenco, il valore verrà impostato sulla riga di transazione corrente. |
| Cancella rappresentante su riga        | L'operazione POS rimuove il valore del gruppo di vendite corrente della riga di transazione corrente. |
| Impostare il rappresentante sulla transazione   | L'operazione POS visualizza un elenco di gruppi di vendite idonei (UD : Nome) per il punto vendita. Se si seleziona un gruppo di vendite dall'elenco, il valore predefinito verrà impostato sulla transazione corrente. Tutte le righe esistenti senza un gruppo vendite assegnato verranno impostate nonché eventuali righe aggiunte successivamente. |
| Cancellare il rappresentante sulla transazione | Questa operazione POS rimuove il valore del gruppo di vendite predefiito corrente dalla transazione corrente. Non influisce sulle righe già esistenti nella transazione. |

## <a name="calculating-commissions"></a>Calcolo delle provvigioni

La provvigione viene calcolata per i lavoratori nei gruppi di vendite specificati al momento della registrazione del rendiconto o dell'ordine cliente. Importo della provvigione viene determinato in base alla quota di provvigione del lavoratore, come definito nel gruppo vendite e nelle impostazioni di calcolo della provvigione associate per il cliente e/o i prodotti nella transazione.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
