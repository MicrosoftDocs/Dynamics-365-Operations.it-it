---
title: Conti per transazioni automatiche
description: Questo argomento spiega come vengono utilizzati i conti per le transazioni automatiche per la registrazione tramite Microsoft Dynamics 365, e fornisce esempi di conti chiave per le transazioni automatiche.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemAccounts
audience: Application User
ms.reviewer: roschlom
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cecbeb769235e525390cc7a66800a9b0d55d78a9
ms.sourcegitcommit: 5bfd6511d710deb539b4030eb0e9c48d25513595
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2022
ms.locfileid: "8014064"
---
# <a name="accounts-for-automatic-transactions"></a>Conti per transazioni automatiche

La pagina **Conti per transazioni automatiche** (**Contabilità generale &gt; Impostazione di registrazione &gt; Conti per transazioni automatiche**) viene usata per definire il conto principale predefinito che viene utilizzato per ogni tipo di registrazione nel sistema. Sebbene la maggior parte dei tipi di registrazione possa essere configurata su una pagina specifica del modulo o di una funzione, alcuni tipi di registrazione possono essere configurati solo nella pagina **Conti per transazioni automatiche**.

Ad esempio, puoi specificare l'account principale utilizzato per il tipo di registrazione **Saldo cliente** nel campo **Riepilogo** della pagina **Profilo registrazione cliente** e utilizzare un conto principale diverso per ciascun profilo cliente. In questo modo, hai un controllo più granulare delle registrazioni. D'altra parte, puoi specificare il conto di errore solo nella pagina **Conti per transazioni automatiche**.

Quando apri la pagina **Conti per transazioni automatiche** in una nuova persona giuridica, l'elenco dei conti sarà vuoto. È possibile aggiungere i tipi di registrazione più comuni che devono essere configurati nella pagina selezionando il pulsante **Crea tipi predefiniti**. Quindi, per ogni riga, puoi selezionare il conto principale nel campo **Conto principale**. Se lasci il campo **Conto principale** vuoto per un tipo di registrazione e non hai configurato un conto principale in una pagina specifica del modulo o della funzionalità, riceverai un messaggio di errore quando registri una transazione che utilizza il tipo di registrazione. In genere, il messaggio sarà "Impossibile trovare il conto per \[tipo di registrazione\]".

## <a name="default-posting-types"></a>Tipi di registrazione predefiniti

La tabella seguente mostra degli esempi dei tipi di registrazione predefiniti che vengono creati quando selezioni **Crea tipi predefiniti** nella pagina **Conti per transazioni automatiche**. Mostra i conti principali e ke descrizioni di esempio. La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, una transazione può registrare un addebito o un credito. La colonna "Conto di compensazione" indica se il tipo di registrazione è un conto di compensazione. Se il tipo di registrazione è un contro di compensazione, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Differenza in centesimi nella valuta di dichiarazione | 618160 | Spese varie | Spese | Entrambi | No | Questo tipo di registrazione viene utilizzato se si verifica una differenza di centesimi quando l'importo di una transazione in una valuta estera viene convertito nella valuta di dichiarazione. |
| Differenza in centesimi nella valuta di contabilizzazione | 618160 | Spese varie | Spese | Entrambi | No | Questo tipo di registrazione viene utilizzato se si verifica una differenza di centesimi quando l'importo di una transazione in una valuta estera viene convertito nella valuta contabile. |
| Conto errori | 999999 | Conto errori | Spese | Entrambi | No | Questo tipo di registrazione viene utilizzato quando si verifica un errore nel sistema. Il conto essere convalidato per ogni periodo e tutti gli errori devono essere risolti. |
| Risultato di fine anno | 300160 | Utili non distribuiti | Capitale netto | Entrambi | No | Questo tipo di registrazione viene utilizzato quando viene eseguito il processo di chiusura di fine anno per spostare il saldo dei conti di tipo **Profitti e perdite** nel conto principale selezionato per il risultato di fine anno. |
| Sconto di cassa cliente | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No | Il tipo di registrazione definito nella pagina **Conti per transazioni automatiche** non viene utilizzato. Un conto principale è richiesto quando gli sconti di cassa sono configurati in Contabilità clienti.|
| Sconto di cassa fornitore | Non applicabile | Non applicabile | Non applicabile | Non applicabile | No | Il tipo di registrazione definito nella pagina **Conti per transazioni automatiche** non viene utilizzato. Un conto principale è richiesto quando gli sconti di cassa sono configurati in Contabilità fornitori. |

## <a name="additional-posting-types"></a>Tipi di registrazione aggiuntivi

La tabella seguente mostra esempi di tipi di registrazione aggiuntivi che devono essere configurati se si prevede di utilizzare le funzionalità correlate. Per questi tipi di registrazione, non è disponibile alcuna configurazione del profilo di registrazione in un altro modulo. La colonna "Dare/Avere" indica se la transazione in genere registra un addebito o un credito. In alcuni casi, una transazione può registrare un addebito o un credito. La colonna "Conto di compensazione" indica se il tipo di registrazione è un conto di compensazione. Se il tipo di registrazione è un contro di compensazione, l'importo registrato in questo conto viene automaticamente stornato quando viene registrata una transazione successiva.

| Tipo di registrazione | Esempio di conto principale | Esempio nome di conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Description |
|--------------|----------------------|---------------------------|--------------|---------------|------------------|-------------|
| Conto saldo per differenza di consolidamento | 801200 | Profitti e perdite - Rivalutazione | Spese | Entrambi | No | Questo tipo di registrazione viene utilizzato quando si esegue un consolidamento che comporta una rivalutazione valutaria e durante la rivalutazione si verificano differenze di centesimo. |
| Conto profitti e perdite per differenze di consolidamento | 801200 | Profitti e perdite - Rivalutazione | Spese | Entrambi | No | Questo tipo di registrazione viene utilizzato quando si esegue un consolidamento che comporta una rivalutazione valutaria e durante la rivalutazione si verificano differenze di centesimo. |
| Interunità - Dare | 133500 | Interunità - Credito | AttivitÃ  | Dare | No | Questo tipo di registrazione viene utilizzato quando si seleziona una dimensione di bilanciamento nella pagina **Libro mastro** e la dimensione non è in pareggio in una transazione registrata. |
| Interunità - Avere | 233500 | Interunità - Debito | Passività | Credito | No | Questo tipo di registrazione viene utilizzato quando si seleziona una dimensione di bilanciamento nella pagina **Libro mastro** e la dimensione non è in pareggio in una transazione registrata. |
