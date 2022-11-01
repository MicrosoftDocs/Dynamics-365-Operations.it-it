---
title: Buoni sconto
description: Questo articolo fornisce una panoramica delle funzionalità correlate al buono sconto in Microsoft Dynamics 365 Commerce.
author: boycez
ms.date: 09/06/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2017-06-30
ms.openlocfilehash: 20427a04a552ddec013daa6576ec64ab7046e95f
ms.sourcegitcommit: 87e75aa6af2c3280316d7d73eafa14a52353a5e4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2022
ms.locfileid: "9709761"
---
# <a name="coupons"></a>Buoni sconto

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica delle funzionalità correlate al buono sconto in Microsoft Dynamics 365 Commerce.

I buoni sconto sono codici e codici a barre utilizzati per aggiungere sconti alle transazioni. I rivenditori distribuiscono buoni sconto a clienti potenziali o esistenti per migliorare il riconoscimento del marchio, promuovere la conversione, mantenere la base di clienti, aumentare le vendite e, infine, aumentare le entrate. I buoni sconto sono diventati uno degli strumenti di marketing più popolari e sono una nuova norma nelle vendite di e-commerce.

In Dynamics 365 Commerce, i buoni sconto sono collegati a sconti e sono considerati una convalida aggiuntiva rispetto agli sconti. Ogni buono sconto è correlato a uno sconto e lo sconto collegato definisce l'insieme di prodotti per cui è valido il buono sconto.

I gruppi di prezzi associati a uno sconto definiscono le condizioni idonee per le quali è possibile utilizzare un buono sconto. Tali condizioni includono gruppi di clienti e canali di vendita. I buoni sconto forniscono anche le proprietà **Limite di utilizzo** e **Cliente richiesto** che possono essere utilizzate per configurare restrizioni di utilizzo facoltative.

Ogni buono sconto può avere codici buono sconto e codici a barra buono sconto e ogni codice può avere un proprio stato e intervallo di date. Se lo stato di un codice è impostato su **Non attivo**, il codice non può essere utilizzato in nessun canale.

## <a name="set-up-a-coupon"></a>Configurare un buono sconto

Prima di impostare un buono sconto, è necessario impostare il codice a barre del buono sconto e due sequenze numeriche di buoni sconto.

Per configurare un buono sconto in Commerce headquarters, segui questi passaggi.

1. Andare a **Retail e Commerce \> Gestione inventario \> Codici a barre ed etichette \> Caratteri maschera**.
1. Seleziona **Aggiungi** per creare un carattere maschera di tipo **Codice buono sconto**. Nel campo **Carattere**, puoi selezionare qualsiasi carattere non utilizzato.
1. Andare a **Retail e Commerce \> Gestione inventario \> Codici a barre ed etichette \> Impostazione maschera codice a barre**.
1. Selezionare **Nuovo** per creare una maschera codice a barra del tipo **Buono sconto**.
1. Andare a **Retail e Commerce \> Gestione inventario \> Codici a barre ed etichette \> Impostazione codice a barre**.
1. Selezionare **Nuovo** per creare un codice a barre che utilizza la maschera codice a barre appena creata.
1. Andare a **Amministrazione organizzazione \> Sequenze numeriche**.
1. Creare due sequenze numeriche:

    1. Una sequenza per il riferimento **Numero buono sconto**. Questa sequenza definisce l'identificatore univoco del buono sconto.
    1. Una sequenza per il riferimento **ID codice buono sconto**. Questa sequenza definisce l'identificatore univoco di ciascun codice buono sconto.

    Per entrambe le sequenze numeriche, è necessario impostare il campo **Ambito** su **Società**. Nella maggior parte dei casi, entrambi i numeri della sequenza devono essere generati automaticamente.

1. Andare a **Parametri di commercio \> Prezzi e sconti \> Buoni sconto**.
1. Impostare il campo **Maschera codice a barre buono sconto** sul codice a barre creato in precedenza.
1. Andare a **Parametri di commercio \> Sequenze numeriche**.
1. Selezionare le sequenze numeriche create in precedenza per i riferimenti **Numero buono sconto** e **ID codice buono sconto**.

Per impostare un buono sconto, è necessario creare lo sconto e il buono sconto separatamente, quindi collegarli selezionando lo sconto nel campo **Sconto** della configurazione del buono sconto. Dopo che un buono sconto è stato collegato a uno sconto, i campi **Stato**, **Data di validità**, e **Data di scadenza** dello sconto collegato diventano di sola lettura, perché i valori sono determinati dallo stato e dal periodo di validità del buono sconto. Quando lo stato di un buono sconto è impostato su **Attivo**, lo stato dello sconto collegato viene aggiornato automaticamente a **Abilitato**. Allo stesso modo, quando lo stato di un buono sconto è impostato su **Inattivo**, lo stato dello sconto collegato viene aggiornato automaticamente a **Disabilitato**.

## <a name="use-a-coupon"></a>Utilizzare un buono sconto

Per aggiungere un buono sconto a una transazione di vendita in Commerce POS, puoi utilizzare un codice buono sconto o un codice a barre buono sconto. Per utilizzare un codice buono sconto, selezionare l'operazione **Aggiungi codice buono sconto**, quindi inserire il codice. Per utilizzare un codice a barre buono sconto, è possibile scansionare il codice a barre utilizzando un dispositivo di scansione o inserirlo utilizzando la tastiera numerica nella schermata **Transazione**.

I rivenditori a volte vogliono che i cassieri possano concedere sconti di importo fisso ai clienti per motivi di conciliazione o per difetti del prodotto, ma non vogliono stampare codici buoni sconto e distribuirli ai cassieri. In questo caso, è possibile impostare l'opzione **Applica senza codice buono sconto** per il buono sconto su **Sì**. I cassieri POS possono quindi utilizzare la funzione **Applica buono sconto** all'interno dell'operazione **Visualizza sconti disponibili** per aggiungere un buono sconto a una transazione senza inserire manualmente il codice. Se esistono più codici buoni sconto per un buono sconto, il sistema seleziona automaticamente il primo codice attivo e lo applica alla transazione.

Per aggiungere un buono sconto a un ordine cliente del call center, un utente del call center deve selezionare **Buoni sconto** nella scheda **Gestisci** del riquadro Azioni nella pagina dell'ordine cliente.

Per aggiungere un buono sconto a un ordine e-commerce, l'acquirente può inserire il codice buono sconto nel campo **Codice promozionale** nel carrello.

Dopo aver aggiunto un buono sconto a un ordine cliente, il motore di determinazione del prezzo attiva immediatamente il ricalcolo per l'intero ordine, indipendentemente dal fatto che il calcolo ritardato sia abilitato.

> [!NOTE]
> In Commerce versione 10.0.30 e precedenti, dopo che gli utenti del call center hanno aggiunto un buono sconto a un ordine cliente del call center, devono selezionare **Ricalcola** nel gruppo **Calcola** della scheda **Vendi** del riquadro Azioni per applicare lo sconto associato a quel buono sconto.

## <a name="coupon-usage-limit"></a>Limite di utilizzo buono sconto

I buoni sconto possono essere configurati per un utilizzo limitato. Il limite di utilizzo può essere definito per cliente, per canale o globalmente. Il limite di utilizzo viene applicato per codice buono sconto su un buono sconto. Ad esempio, un singolo buono sconto che contiene due codici buono sconto può essere utilizzato due volte: una volta per ogni codice del buono sconto.

I buoni sconto possono essere utilizzati attraverso i canali di vendita. Per i call center, invece, i buoni sconto a utilizzo limitato possono essere applicati solo quando l'impostazione **Attiva completamento ordine** per il canale del call center è abilitata. Se l'impostazione **Attiva completamento ordine** è disabilitata, possono essere applicati solo buoni sconto a utilizzo illimitato.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
