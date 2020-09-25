---
title: Funzione ER NUMSEQVALUE
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione NUMSEQVALUE della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 70e07fe429472b703f739baa09f700fb8970d34e
ms.sourcegitcommit: 445f6d8d0df9f2cbac97e85e3ec3ed8b7d18d3a2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2020
ms.locfileid: "3744025"
---
# <a name="numseqvalue-er-function"></a>Funzione ER NUMSEQVALUE

[!include [banner](../includes/banner.md)]

La funzione `NUMSEQVALUE` restituisce un valore *Stringa* che rappresenta il nuovo valore generato di una sequenza numerica, in base alla sequenza numerica, all'ambito e all'ID ambito specificati. L'ID ambito equivale al codice società fornito dal contesto in cui viene eseguito il formato creazione di report elettronici (ER).

## <a name="syntax-1"></a>Sintassi 1

```vb
NUMSEQVALUE (number sequence code)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
NUMSEQVALUE (number sequence record ID)
```

## <a name="syntax-3"></a>Sintassi 3

```vb
NUMSEQVALUE (number sequence code, scope type, scope ID)
```

## <a name="arguments"></a>Argomenti

`number sequence code`: *Stringa*

Un valore di testo che rappresenta il codice della sequenza numerica in cui è richiesto un nuovo valore.

`number sequence record ID`: *Int64*

Un valore *Int64* che rappresenta l'ID record di un record nella tabella NumberSequenceTable che contiene la definizione della sequenza numerica in cui è richiesto un nuovo valore.

`scope type`: *Valore enumerazione*

Un valore di enumerazione dell'enumerazione **ERExpressionNumberSequenceScopeType** che definisce l'ambito della sequenza numerica in cui è richiesto un nuovo valore. I tipi di ambito disponibili sono **Condiviso**, **Persona giuridica** e **Società**.

`scope ID`: *Stringa*

Un valore *Stringa* che identifica l'ambito, in base al tipo di ambito specificato.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Per il tipo di ambito **Condiviso**, specificare una stringa vuota come ID ambito.

Per i tipi di ambiti **Persona giuridica** e **Società**, specificare il codice società come ID ambito. Se si specifica una stringa vuota come ID ambito per questi tipi di ambito, il codice corrente della società viene utilizzato.

Quando si utilizza la sintassi 1, la sequenza numerica è richiesta per il tipo di ambito **Società** e il codice società viene fornito dal contesto in cui viene eseguito il formato ER.

## <a name="example-1"></a>Esempio 1

Nel formato ER, si definisce l'origine dati **AskNumSeq** del tipo *Parametro di input utente*. Questa origine dati fa riferimento all'Extended Data Type (EDT) **Descrizione**. Successivamente, si definisce l'origine dati **NumSeq** del tipo *Campo calcolato*. Questa origine dati contiene l'espressione `NUMSEQVALUE (AskNumSeq)`. Quando viene chiamata l'origine dati **NumSeq**, restituisce il nuovo valore generato della sequenza numerica che è stata specificata in fase di esecuzione immettendo il relativo codice nella finestra di dialogo. La sequenza numerica è richiesta per il tipo di ambito **Società**. Il codice società viene fornito dal contesto in cui viene eseguito il formato ER.

## <a name="example-2"></a>Esempio 2

Le origini dati seguenti sono definite nel mapping di modello:

- L'origine dati **LedgerParms** del tipo *Tabella*. Questa origine dati fa riferimento alla tabella LedgerParameters.
- L'origine dati **NumSeq** del tipo *Campo calcolato*. Questa origine dati contiene l'espressione `NUMSEQVALUE ( LedgerParameters.'numRefJournalNum()'.NumberSequenceId)`.

Se l'origine dati **NumSeq** viene chiamata, restituisce il nuovo valore generato della sequenza numerica che è stata configurata nei parametri di contabilità generaòe per la società che fornisce il contesto in cui il formato ER viene eseguito. Questa sequenza numerica identifica univocamente giornali di registrazione e funge da numero batch per collegare insieme le transazioni.

## <a name="example-3"></a>Esempio 3

Le origini dati seguenti sono definite nel mapping di modello:

- L'origine dati **enumScope** del tipo di *enumerazione* Microsoft Dynamics 365 Finance. Questa origine dati fa riferimento all'enumerazione **ERExpressionNumberSequenceScopeType**.
- L'origine dati **NumSeq** del tipo *Campo calcolato*. Questa origine dati contiene l'espressione `NUMSEQVALUE ("Gene_1", enumScope.Company, "")`.

Se l'origine dati **NumSeq** viene chiamata, restituisce il nuovo valore generato della sequenza numerica **Gene\_1** che è stata configurata per la società che fornisce il contesto in cui il formato ER viene eseguito.

## <a name="additional-resources"></a>Risorse aggiuntive

[Altre funzioni (specifiche del dominio aziendale)](er-functions-category-other.md)
