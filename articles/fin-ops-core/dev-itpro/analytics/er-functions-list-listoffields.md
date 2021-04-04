---
title: Funzione ER LISTOFFIELDS
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione LISTOFFIELDS della creazione di report elettronici (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 494dc347fadf44121c7eae0acf8c30768c58f035
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "5567666"
---
# <a name="listoffields-er-function"></a>Funzione ER LISTOFFIELDS

[!include [banner](../includes/banner.md)]

La funzione `LISTOFFIELDS` restituisce un valore *Elenco di record* creato in base alla struttura dell'argomento specificato del tipo *Enumerazione* o *Contenitore (record)*.

## <a name="syntax-1"></a>Sintassi 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Sintassi 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argomenti

`path`: riferimento origine dati

Il percorso di riferimento valido di un'origine dati di uno dei seguenti tipi di dati:

- Enumerazione modello
- Enumerazione formato
- Enumerazione dell'applicazione
- Contenitore (record)

`language`: *Stringa*

Testo che rappresenta un codice lingua.

## <a name="return-values"></a>Valori restituiti

*Elenco di record*

L'elenco risultante di record.

## <a name="usage-notes"></a>Note sull'utilizzo

L'elenco creato contiene record con i seguenti campi:

- **Nome** (tipo di dati *Stringa*)
- **Etichetta** (tipo di dati *Stringa*)
- **Descrizione** (tipo di dati *Stringa*)
- **IsTranslated** (tipo di dati *Booleano*)

Se l'argomento `path` si riferisce a un'origine dati di tipo *Contenitore (Record)*, per ogni campo del record contenitore di riferimento all'elenco creato viene aggiunto un nuovo record. Per ogni record creato, il campo **Nome** restituisce il nome del campo del record contenitore di riferimento per cui è stato creato il record corrente.

Se l'argomento `path` si riferisce a un'origine dati uno dei tipi *Enumerazione*, per ogni valore di enumerazione dell'enumerazione di riferimento all'elenco creato viene aggiunto un nuovo record. Per ogni record creato, il campo **Nome** restituisce il valore dell'enumerazione di riferimento per cui è stato creato il record corrente, il campo **Descrizione** restituisce la descrizione dell'enumerazione e il campo **Etichetta** restituisce l'etichetta dell'enumerazione.

In fase di runtime, quando viene utilizzata la sintassi 1, i campi **Etichetta** e **Descrizione** devono restituire valori basati sulle impostazioni della lingua del formato creazione di report elettronici (ER) in esecuzione:

- Se sono disponibili le etichette e le descrizioni per la lingua richiesta, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua e il campo **IsTranslated** restituisce **True**.
- Se le etichette e le descrizioni per la lingua richiesta non sono disponibili, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua **EN-US** predefinita e il campo **IsTranslated** restituisce **False**.

In fase di runtime, quando viene utilizzata la sintassi 2, i campi **Etichetta** e **Descrizione** devono restituire valori basati sulle impostazioni della lingua definite come secondo argomento della funzione chiamata:

- Se sono disponibili le etichette e le descrizioni per la lingua richiesta, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua e il campo **IsTranslated** restituisce **True**.
- Se le etichette e le descrizioni per la lingua richiesta non sono disponibili, i campi **Etichetta** e **Descrizione** restituiscono valori basati su quella lingua **EN-US** e il campo **IsTranslated** restituisce **False**.

## <a name="example-1"></a>Esempio 1

Nella seguente figura viene illustrata l'enumerazione introdotta in un modello dati ER.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

La figura di seguito mostra questi dettagli:

- L'enumerazione del modello viene inserita in un report come origine dei dati.
- Un'espressione ER utilizza l'enumerazione modello come parametro della funzione `LISTOFFIELDS`.
- Un'origine dati del tipo *Elenco di record* viene inserita in un report mediante l'espressione ER creata.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

L'esempio seguente illustra gli elementi di formato ER che sono collegati all'origine dati del tipo *Elenco di record* creato utilizzando la funzione `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

Nella figura seguente è illustrato il risultato dell'esecuzione del formato progettato.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Il testo tradotto per le etichette e le descrizioni viene immesso nell'output del formato ER in base alle impostazioni di lingua configurate per gli elementi di formato **FILE** e **FOLDER** padre.

## <a name="example-2"></a>Esempio 2

Utilizzare il tipo di origine dati *Campo calcolato* per configurare le origini dati **enumType\_de** e **enumType\_deCH** per l'enumerazione del modello dati **enumType**.

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

In questo caso, è possibile utilizzare la seguente espressione per visualizzare l'etichetta del valore enumerato in svizzero tedesco, se la traduzione è disponibile. Se la traduzione tedesca svizzera non è disponibile, l'etichetta è in tedesco.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di elenco](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]