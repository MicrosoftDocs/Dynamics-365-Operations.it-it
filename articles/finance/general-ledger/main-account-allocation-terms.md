---
title: Termini di allocazione
description: Questo articolo fornisce informazioni sull'utilizzo dei termini di allocazione su un conto principale.
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: twheeloc
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d62c0cc79c9d61e0ebb1c2c62a345ad47412d0d2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859829"
---
# <a name="allocation-terms"></a>Termini di allocazione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sull'utilizzo dei termini di allocazione su un conto principale. I termini di allocazione vengono utilizzati per distribuire importi tra più combinazioni di conti CoGe. Consentono di garantire che le spese o i ricavi vengano contabilizzate in relazione all'oggetto corretto.

Ogni termine di allocazione creato su un conto principale definisce la percentuale di un giustificativo da allocare da un conto principale a origine singola e una combinazione di dimensioni finanziarie. Inoltre, si definiscono il conto principale di destinazione e le dimensioni finanziarie in cui verrà allocato l'importo. 

Quando si definisce la dimensione finanziaria di origine per l'allocazione, è possibile selezionare se ciascuna dimensione è specifica o non specifica. Specifica indica che la dimensione finanziaria per la transazione di origine deve corrispondere alla dimensione selezionata. Quando si seleziona non specifica, indica che qualsiasi valore per la dimensione finanziaria può contribuire a una corrispondenza.

Quando si definisce il conto CoGe di destinazione per un termine di allocazione, è necessario specificare il conto principale a cui si sta allocando l'importo. È possibile utilizzare lo stesso conto principale in cui è registrata la transazione di origine o un conto principale diverso. Se si utilizza lo stesso conto principale, viene visualizzato un avviso quando si salva il record. Oltre a specificare il conto principale, è necessario specificare anche le dimensioni di destinazione. Per ogni dimensione, è possibile specificare se si desidera mantenere il valore della dimensione finanziaria di origine o modificarlo. Se si seleziona no, è necessario selezionare un nuovo valore per la dimensione finanziaria. Se si seleziona sì, non vengono specificate ulteriori informazioni e il sistema manterrà le dimensioni finanziarie originali al momento della registrazione.

Non vi è alcun limite al numero di termini di allocazione che è possibile aggiungere a un conto principale; tuttavia, la somma della percentuale da allocare in un termine di allocazione non può superare 100. È possibile creare allocazioni per meno del 100 percento se una parte dell'importo del giustificativo originale deve rimanere nelle dimensioni finanziarie di origine. I termini di allocazione possono essere aggiunti a un conto principale come sostituzione di persona giuridica. Se si utilizza un piano dei conti condiviso, i termini di allocazione devono essere definiti per ciascuna persona giuridica. Per accedere al pulsante **Termini di allocazione**, è necessario prima selezionare la casella di controllo **Allocazione** nella sostituzione di persona giuridica.

## <a name="allocation-term-example"></a>Esempio di termine di allocazione
È stato definito un centro di costo per l'organizzazione chiamato CORPORATE e numerato come 000. Quando le fatture vengono registrate per le spese di servizio, vengono codificate in questo centro di costo CORPORATE. L'azienda ha definito una regola secondo la quale tutte le spese di servizio devono essere allocate in percentuale a ciascuno dei singoli centri di costo. Le altre dimensioni finanziarie per reparto e Business Unit rimarranno invariate.

Con questo esempio, verrà creato un nuovo termine di allocazione per il conto principale delle spese di servizio. Verrà creata una riga per ciascun centro di costo con la percentuale da allocare. I **Criteri di selezione** per le dimensioni finanziarie di origine per ogni riga sarà **Specifico** per il **Centro di costo** e il valore sarà impostato su 000: CORPORATE. Per il reparto e la Business Unit, i **Criteri di selezione** saranno **Non specifico**.

Nella Scheda dettaglio **Conto CoGe di destinazione**, il conto principale sarà lo stesso conto delle spese di servizio e **Mantieni dimensioni finanziarie di origine** sarà impostato su **Sì** per **Business Unit** e **Reparto**. **Mantieni dimensioni finanziarie di origine** sarà impostato su **No** per **Centro di costo** e il valore selezionato sarà ciascun rispettivo centro di costo a cui si sta effettuando l'allocazione. Se ci sono tre centri di costo a cui allocare, verranno creati tre record dei termini di allocazione. L'unica differenza tra ciascun termine di allocazione è il centro di costo specificato nel conto CoGe di destinazione.

## <a name="create-an-allocation-term-on-a-main-account"></a>Creare un termine di allocazione su un conto principale

1. Nel **Pannello di navigazione**, andare a **Moduli > Contabilità generale > Piano dei conti > Conti > Conti principali**.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Nella Scheda dettaglio **Sostituzioni persona giuridica**, selezionare **Aggiungi**.
4. Selezionare la **Società** e quindi selezionare **Aggiungi**.
5. Selezionare la casella di controllo **Allocazione**.
6. Selezionare **Termini di allocazione**.
7. Selezionare **Modifica** per modificare il record predefinito o selezionare **Nuovo** per aggiungere un record.
8. Nel campo **Percentuale**, immettere la percentuale di transazioni giustificativo che si desidera allocare.
9. Nella Scheda dettaglio **Dimensione finanziaria di origine**, in **Criteri di selezione** per ciascuna dimensione finanziaria selezionare un'opzione.
    - Se si seleziona **Specifico**, selezionare il valore della dimensione finanziaria nella casella a discesa a destra.
    - Se si seleziona **Non specifico**, non sono richieste ulteriori informazioni per la dimensione finanziaria.
10. Nella Scheda dettaglio **Conto CoGe di destinazione** nel campo **Al conto** selezionare il conto principale in cui si desidera allocare la percentuale della transazione giustificativo.
11. In **Mantieni dimensioni finanziarie di origine** per ciascuna dimensione finanziaria selezionare un'opzione.
    - Se si seleziona **No**, selezionare il valore della dimensione finanziaria nella casella a discesa a destra in cui si desidera allocare la transazione giustificativo.
    - Se si seleziona **Sì**, non sono necessarie ulteriori informazioni. Il sistema manterrà il valore sul giustificativo originale durante la registrazione dell'allocazione.
12. Ripetere i passaggi da 7 a 11 per ciascuna allocazione aggiuntiva. La somma di tutte le allocazioni è indicata nel campo **Percentuale totale**. Questo importo non può superare 100.
13. Chiudere tutte le pagine.

>[!NOTE] 
> Facoltativamente è possibile usare il pulsante **Copia** per duplicare l'allocazione selezionata.

Quando viene creato un termine di allocazione per un conto principale, il sistema registrerà automaticamente un nuovo giustificativo quando viene registrato un giustificativo che corrisponde alle dimensioni finanziarie di origine nei termini di allocazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
