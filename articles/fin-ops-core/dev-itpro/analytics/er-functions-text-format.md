---
title: Funzione ER FORMAT
description: In questo argomento sono riportate le informazioni sull'utilizzo della funzione FORMAT della creazione di report elettronici (ER).
author: NickSelin
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
ms.openlocfilehash: 6ee53ef3c1a8820f75580e2f9fbd48575d6a828f
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5746461"
---
# <a name="format-er-function"></a>Funzione ER FORMAT

[!include [banner](../includes/banner.md)]

La funzione `FORMAT` restituisce la stringa specificata come un valore *Stringa* dopo che è stata formattata sostituendo tutte le occorrenze di **%N** con l'argomento *n*-esimo.

## <a name="syntax"></a>Sintassi

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argomenti

`string`: *Stringa*

Un riferimento a un'origine dati di tipo *Stringa* che deve essere formattata. Questo argomento è obbligatorio.

`argument 1`: *Stringa*

Il primo argomento, che viene utilizzato per sostituire le occorrenze di **%1**. Questo argomento è obbligatorio.

`argument N`: *Stringa*

L'argomento *n*-esimo, che viene utilizzato per sostituire le occorrenze di **%2**, **%3** e così via. Questi argomenti aggiuntivi sono facoltativi.

## <a name="return-values"></a>Valori restituiti

*Stringa*

Il valore di testo risultante.

## <a name="usage-notes"></a>Note sull'utilizzo

Se un argomento non viene fornito per un parametro, il parametro viene restituito come **"%N"** nella stringa. Per i valori di tipo *Reale*, la conversione di stringhe predefinita è limitata a due posizioni decimali.

## <a name="example"></a>Esempio

Nell'illustrazione seguente, l'origine dati **PaymentModel** restituisce un elenco di record dei clienti utilizzando il componente **Customer**. Restituisce il valore della data di elaborazione utilizzando il campo **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

Nel formato creazione di report elettronici (ER) che è progettato per generare un file elettronico per i clienti selezionati, **PaymentModel** è selezionato come origine dati e controlla il flusso di processo. Se un cliente selezionato viene interrotto per la data in cui il report viene elaborato, viene generata un'eccezione per informare l'utente. La formula che è stata progettata per questo tipo di controllo di processo può utilizzare le risorse indicate di seguito:

- Etichetta SYS70894, con il testo seguente:

    - **Per la lingua EN-US:** "Nothing to print"
    - **Per la lingua DE:** "Nichts zu drucken"

- Etichetta SYS18389, con il testo seguente:

    - **Per la lingua EN-US:** "Customer %1 is stopped for %2."
    - **Per la lingua DE:** "Debitor '%1' wird für %2 gesperrt."

Questa è l'espressione che può essere progettata.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Se un report viene elaborato per il cliente **Litware Retail** il 17 dicembre 2015, nelle impostazioni cultura **EN-US** e la lingua **EN-US**, questa formula restituisce il seguente testo, che può essere presentato all'utente come un messaggio di eccezione:

*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*

Se lo stesso viene elaborato per il cliente **Litware Retail** il 17 dicembre 2015, nelle impostazioni culture **DE** e la lingua **DE**, la formula restituisce il seguente testo, che utilizza un formato della data diverso:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> La seguente sintassi si applica nelle formule ER per le etichette:
>
> - **Per le etichette di risorse nell'app Microsoft Dynamics 365 Finance:** **\@X**, dove **X** è l'ID etichetta nell' Application Object Tree (AOT)
> - **Per le etichette che si trovano in configurazioni ER:** **@"GER_LABEL:X"**, dove **X** è l'ID etichetta nella configurazione ER

## <a name="additional-resources"></a>Risorse aggiuntive

[Funzioni di testo](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]