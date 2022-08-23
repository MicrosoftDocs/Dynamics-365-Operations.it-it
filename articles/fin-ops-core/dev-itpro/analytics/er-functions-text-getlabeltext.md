---
title: Funzione GETLABELTEXT ER
description: In questo articolo sono riportate le informazioni sull'utilizzo della funzione GETLABELTEXT della creazione di report elettronici (ER).
author: kfend
ms.date: 03/18/2022
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2022-01-01
ms.dyn365.ops.version: AX 10.0.25
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: dad87548518b77f2def1cf2383a21607f45170e1
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9285941"
---
# <a name="getlabeltext-er-function"></a>Funzione GETLABELTEXT ER

[!include [banner](../includes/banner.md)]

La funzione `GETLABELTEXT` cerca un'etichetta specifica da restituire al valore *[Stringa](er-formula-supported-data-types-primitive.md#string)* che rappresenta la traduzione dell'etichetta specificata nella lingua specificata.

## <a name="syntax"></a>Sintassi

```vb
GETLABELTEXT (label id, language)
```

## <a name="arguments"></a>Argomenti

### <a name="label-id"></a>ID etichetta

`label id`: *Stringa* o *ID etichetta*

L'ID valido di uno dei seguenti tipi di etichetta:

- Etichetta [Creazione di report elettronici (ER)](general-electronic-reporting.md)
- Etichetta Microsoft Dynamics 365 Finance

#### <a name="usage-notes"></a>Note sull'utilizzo

Questo argomento può essere definito solo come una costante, utilizzando uno dei seguenti modelli supportati:

- Per le etichette ER:

    - `@"GER_LABEL:<LABEL ID>"`
    - `"GER_LABEL:<LABEL ID>"`

- Per le etichette Finance:

    - `@"<LABEL ID>"`
    - `"<LABEL ID>"`

> [!NOTE]
> In fase di progettazione, viene visualizzato un messaggio di errore di convalida nella pagina **[Designer formula](er-advanced-formula-editor.md)** se non è possibile trovare alcuna etichetta utilizzando l'ID etichetta fornito.

### <a name="language"></a>Lingua

`language`: *Stringa*

Stringa che rappresenta un codice lingua.

#### <a name="usage-notes"></a>Note sull'utilizzo

Questo argomento può essere definito come una costante di testo o come il percorso di un campo dell'origine dati che restituisce un valore *Stringa*.

> [!NOTE]
> In fase di progettazione, viene visualizzato un messaggio di errore di convalida se non è possibile trovare il codice della lingua utilizzando l'argomento `language` fornito quando è stato definito come una costante di testo.
>
> In fase di esecuzione, la traduzione per la lingua del sistema `EN-US` viene restituita per un'etichetta specificata se non è stato trovato alcun codice lingua utilizzando l'argomento `language` fornito.

## <a name="return-values"></a>Valori restituiti

*String*

Il valore di testo risultante.

## <a name="example-1-system-label"></a><a name=example-1></a>Esempio 1: etichetta di sistema

Le espressioni `GETLABELTEXT (@"SYS70894", "en-us")` e `GETLABELTEXT ("SYS70894", "en-us")` restituiscono la traduzione inglese "Niente da stampare" per l'etichetta dell'applicazione `@SYS70894`.

## <a name="example-2-er-label"></a><a name=example-2></a>Esempio 2: etichetta ER

Inizia a modificare una [configurazione](general-electronic-reporting.md#Configuration) ER che è stata [derivata](er-quick-start2-customize-report.md#DeriveProvidedFormat) dalla configurazione **Bonifico ISO20022 (DE)**, immetti una nuova origine dati del tipo *[Campo calcolato](er-calculated-field-ds-performance.md)* e configura l'espressione `GETLABELTEXT(@"GER_LABEL:VendorName", "de")` per questa origine dati. In questo caso, in fase di esecuzione, l'origine dati restituisce la traduzione tedesca "Kreeditorenname" per l'etichetta ER `@GER_LABEL:VendorName` inizialmente configurata nella configurazione ER **ISO20022 Bonifico (DE)**.

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)

[Progettare report multilingue nella creazione di report elettronici](er-design-multilingual-reports.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
