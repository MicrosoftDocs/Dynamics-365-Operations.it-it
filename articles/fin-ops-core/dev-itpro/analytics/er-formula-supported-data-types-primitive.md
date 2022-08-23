---
title: Tipi di dati primitivi supportati per le formule di creazione di report elettronici
description: Questo articolo fornisce informazioni sui tipi di dati primitivi supportati nelle formule di creazione di report elettronici (ER).
author: kfend
ms.date: 06/02/2021
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: 26c166744e1705baa9dcce6b93c76f110524b7d7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284576"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Tipi di dati primitivi supportati per le formule di creazione di report elettronici

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sui tipi di dati primitivi supportati nelle espressioni di [generazione di report elettronici (ER)](general-electronic-reporting.md). Di seguito è riportato un elenco di tipi di dati primitivi:

- [booleano](#boolean)
- [data](#date)
- [datetime](#datetime)
- [enumerazione](#enumeration)
- [guid](#guid)
- [numero intero](#integer)
- [int64](#int64)
- [reale](#real)
- [stringa](#string)

## <a name="boolean"></a><a name="boolean"></a>Boolean

Il tipo di dati primitivo *booleano* contiene un valore che viene valutato come *vero* o *falso*. È possibile usare le parole chiave letterali riservate **True** e **False** ogni volta che è prevista un'espressione *booleana*. Il valore predefinito è *false*.

La rappresentazione interna di un *booleano* è un *numero intero*. Il valore per il *numero intero* 0 (zero) viene valutato come *false*, mentre tutti gli altri valori di tipo *numero intero* vengono valutati come *true*. Quando si [convalida](general-electronic-reporting-formula-designer.md#TestFormula) un'espressione configurata che restituisce un *booleano* nella [soluzione di progettazione della formula ER](er-advanced-formula-editor.md), il riquadro dei risultati del test presenta *0* (zero) quando un'espressione restituisce *false*. In caso contrario, il riquadro dei risultati del test presenta *1*.

Un *booleano* non ha conversioni implicite. Tuttavia, è possibile usare la funzione [TESTO](er-functions-text-text.md) per convertire in modo esplicito un *booleano* in una *stringa*:

- Il valore *false* viene convertito in una stringa di testo **Falso**.
- Il valore *true* viene convertito in una stringa di testo **True**.

> [!NOTE]
> Questa conversione non dipende dal [contesto](er-design-multilingual-reports.md) di lingua e cultura forniti.

Gli [operatori](er-formula-language.md#Operators) di confronto sono l'unico tipo di operatore utilizzabile con il tipo di dati *booleano*. È possibile usare i due operatori seguenti per confrontare due valori *booleani*: \<\> e =.

## <a name="date"></a><a name="date"></a>Data

Il tipo di dati primitivo *data* contiene il giorno, il mese e l'anno. Le date possono essere inizializzate utilizzando le seguenti funzioni:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

Il tipo di dati *data* può contenere date comprese tra il 1 gennaio 1900 e il 31 dicembre 2154. Il valore predefinito è **null** e la rappresentazione interna è la data 1 gennaio 1900.

Una *data* non ha conversioni implicite. Tuttavia, è possibile utilizzare le seguenti funzioni di conversione esplicite:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

La funzione [ADDDAYS](er-functions-datetime-adddays.md) permette di aggiungere e sottrarre giorni dalle date. In questo modo, è possibile spostare la data di un numero specifico di giorni nel futuro e nel passato. La funzione [DAYS](er-functions-datetime-days.md) permette di sottrarre una data da un'altra e calcolare la differenza in giorni. Per maggiori informazioni sulla trasformazione dei valori *data*, vedere [Elenco delle funzioni ER nella categoria Data e ora](er-functions-category-datetime.md).

Gli [operatori](er-formula-language.md#Operators) di confronto sono l'unico tipo di operatore utilizzabile con il tipo di dati *data*. È possibile usare i due operatori seguenti per confrontare due valori *data*: \<\>, \<, \<=, =, \>, e \>=.

## <a name="datetime"></a><a name="datetime"></a>Datetime

Il tipo di dati primitivo *datetime* combina il tipo *data* e un valore che rappresenta il tempo trascorso dalla mezzanotte. Il tempo è espresso in ore, minuti, secondi e frazioni di secondo. Un valore *datetime* contiene inoltre informazioni sul fuso orario.

Il tipo di dati *datetime* può contenere date comprese tra il 1 gennaio 1900 (1900-01-01T00:00:00.0000000+00:00 nel [formato](/dotnet/standard/base-types/standard-date-and-time-format-strings)) round-trip e il 31 dicembre 2154 (2154/12/31T11:59:59.9999999+00:00 nel formato round-trip). L'unità minima di tempo in un *datetime* è un decimo di milionesimo di secondo.

> [!NOTE]
> Quando si usa l'[identificatore](/dotnet/standard/base-types/standard-date-and-time-format-strings) **hh** per le ore, i valori dell'ora superiori a 12:59:59:9999999 non possono essere interpretati come ore valide.
>
> Quando si usa l'identificatore **HH** per le ore, i valori dell'ora superiori a 23:59:59:9999999 non possono essere interpretati come ore valide.

Il valore predefinito è **null** e la rappresentazione interna è la data 1 gennaio 1900 (1900-01-01T00:00:00.0000000+00:00 nel formato round-trip).

I datetime possono essere inizializzati utilizzando le seguenti funzioni:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

Un *datetime* non ha conversioni implicite. Tuttavia, è possibile utilizzare le seguenti funzioni di conversione esplicite:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Per maggiori informazioni sulla trasformazione dei valori *datetime*, vedere [Elenco delle funzioni ER nella categoria Data e ora](er-functions-category-datetime.md).

Gli [operatori](er-formula-language.md#Operators) di confronto sono l'unico tipo di operatore utilizzabile con il tipo di dati *datetime*. È possibile usare i due operatori seguenti per confrontare due valori *datetime*: \<\>, \<, \<=, =, \>, e \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Enumerazione

Il tipo di dati primitivo *enumerazione* è un elenco di valori letterali. È possibile utilizzare enumerazioni definite nel [codice sorgente](../dev-ref/xpp-data-primitive.md#enum) dell'applicazione. È anche possibile introdurre enumerazioni personali nel modello di dati ER e nei componenti formato ER.

Un'*enumerazione* dell'applicazione può essere usata nelle espressioni di qualsiasi mapping del modello ER e formato ER.

L'illustrazione seguente mostra come aggiungere l'enumerazione del modello **CustVendCorrectiveReasonCode** nel modello dati ER modificabile.

[![Configurazione dell'enumerazione di modello nella finestra di progettazione modello di dati ER.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

L'*enumerazione* di un modello può essere utilizzata in espressioni di qualsiasi mapping del modello ER e formato ER creati in un modello di dati in cui è stata presentata l'*enumerazione*.

L'illustrazione seguente mostra come aggiungere l'enumerazione del formato **Elenco delle sottocategorie reverse charge Natura** nel formato ER modificabile.

[![Configurazione dell'enumerazione di formato nella finestra di progettazione formato ER.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

L'*enumerazione* di un formato può essere usata soltanto nelle espressioni del formato ER in cui è stata presentata l'*enumerazione*.

È necessario utilizzare il tipo appropriato di origini dati ER per portare un'enumerazione specifica a un componente ER configurato come costante o come valore definito dall'utente che esegue una soluzione ER nella finestra di dialogo in runtime.

- È possibile accedere alle enumerazioni delle applicazioni mediante le origini dati **Dynamics 365 for Operations \ Enumerazione** e **Generale \ Parametri immessi dall'utente**. L'illustrazione seguente mostra come aggiungere al formato ER modificabile le origini dati **appenumNoYes** e **uipNoYes** che fanno riferimento all'enumerazione dell'applicazione **NoYes**.

    [![Aggiunta di origini dati di enumerazione applicazione nella finestra di progettazione formato ER.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- È possibile accedere alle enumerazioni del modello di dati utilizzando le origini dati **Modello dati \ Enumerazione** e **Modello dati \ Parametri di enumerazione immessi dall'utente**. L'illustrazione seguente mostra come aggiungere al formato ER modificabile l'origine dati **CustVendCorrectiveReasonCode** che fa riferimento all'enumerazione del modello di dati **CustVendCorrectiveReasonCode**.

    [![Aggiunta di origini dati di enumerazione modello nella finestra di progettazione formato ER.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- È possibile accedere alle enumerazioni del formato utilizzando le origini dati **Formato \ Enumerazione** e **Formato \ Parametri di enumerazione immessi dall'utente**. L'illustrazione seguente mostra come aggiungere al formato ER modificabile l'origine dati **NaturaReverseCharge** che fa riferimento all'enumerazione del formato **Sottocategorie reverse charge Natura**.

    [![Aggiunta di origini dati di enumerazione formato nella finestra di progettazione formato ER.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

Un'*enumerazione* non ha conversioni implicite. Tuttavia, è possibile usare la funzione di conversione [TEXT](er-functions-text-text.md) per convertire un'*enumerazione* in una stringa di testo. Questa conversione non dipende dalla lingua. Per conoscere come associare un valore di *enumerazione* alle etichette specifiche della lingua appropriate, vedere gli esempi di utilizzo per le funzioni [LISTOFFIELDS](er-functions-list-listoffields.md) e [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

Gli [operatori](er-formula-language.md#Operators) di confronto sono l'unico tipo di operatore utilizzabile con il tipo di dati *enumerazione*. È possibile usare i due operatori seguenti per confrontare due valori *enumerazione*: \<\> e =.

## <a name="guid"></a><a name="guid"></a>Guid

Il tipo di dati primitivo *guid* contiene un valore di identificatore univoco globale (GUID). Un GUID è un valore che può essere utilizzato su tutti i computer e le reti, ovunque sia richiesto un identificatore univoco. È improbabile che il numero venga duplicato. Un GUID valido soddisfa tutte le seguenti specifiche:

- Deve essere composto da 32 cifre esadecimali.
- Inoltre, devono essere presenti quattro trattini incorporati nelle seguenti posizioni: 8-4-4-4-12.
- Inoltre, è possibile aggiungere parentesi graffe opzionali \{\} all'inizio e alla fine della stringa. Ad esempio, **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** e **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** sono entrambe stringhe GUID valide.
- Pertanto, devono essere presenti un totale di 36 o 38 caratteri, a seconda che vengano aggiunte le parentesi graffe.
- Le lettere utilizzate come cifre esadecimali possono essere maiuscole (A–F), minuscole (a–f) o miste.

È possibile utilizzare le seguenti funzioni di conversione esplicite:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

Gli [operatori](er-formula-language.md#Operators) di confronto sono l'unico tipo di operatore utilizzabile con il tipo di dati *guid*. È possibile usare i due operatori seguenti per confrontare due valori *guid*: \<\> e =.

## <a name="integer"></a><a name="integer"></a>Integer

Il tipo di dati primitivo *numero intero* rappresenta un numero senza posizioni decimali. I numeri interi vengono utilizzati come variabili di controllo in istruzioni ripetitive o come indici negli elenchi di record.

Un valore letterale *numero intero* è il numero intero così come viene immesso direttamente in un'[espressione](general-electronic-reporting-formula-designer.md#formula-designer-overview) (formula) ER, ad esempio **12345**. Un *numero intero* ha una larghezza di 32 bit. Il valore predefinito è **0** e la rappresentazione interna è un numero lungo. Un *numero intero* viene automaticamente convertito in un valore *reale*.

Inoltre, è possibile utilizzare le seguenti funzioni di conversione esplicite:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

L'intervallo di un *numero intero* è \[-2,147,483,647 : 2,147,483,647\]. Tutti i numeri interi di questo intervallo possono essere utilizzati come valori letterali.

Tutti gli [operatori](er-formula-language.md#Operators) di confronto e matematici possono essere usati con il tipo di dati *numero intero*.

## <a name="int64"></a><a name="int64"></a>Int64

Il tipo di dati primitivo *int64* rappresenta un numero senza posizioni decimali. I valori *Int64* vengono utilizzati come variabili di controllo in istruzioni ripetitive o come identificatori di record.

Un *int64* ha una larghezza di 64 bit. Il valore predefinito è **0** e la rappresentazione interna è un numero lungo. Un *int64* viene automaticamente convertito in un valore *reale*.

Inoltre, è possibile utilizzare le seguenti funzioni di conversione esplicite:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

L'intervallo di un *int64* è \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Tutti gli [operatori](er-formula-language.md#Operators) di confronto e matematici possono essere usati con il tipo di dati *int64*.

## <a name="real"></a><a name="real"></a>Real

Il tipo di dati primitivo *reale* può contenere valori decimali oltre a numeri interi. È possibile usare valori letterali decimali ovunque è previsto un valore *reale*. Un valore letterale decimale è il decimale immesso direttamente nel codice, ad esempio **2.19**.

> [!NOTE]
> Nelle espressioni ER, viene sempre utilizzato un punto (.) come separatore decimale.

I valori reali possono essere utilizzati in tutte le espressioni, sia con gli operatori di confronto che con quelli aritmetici. Un valore *reale* ha una precisione di 16 cifre significative. Il valore predefinito per un valore *reale* è **0.0** e la rappresentazione interna è un numero digitale in codice binario (BCD). La codifica BCD consente rappresentazioni esatte di valori multipli di 0.1. L'intervallo di una variabile *reale* è compreso tra -(10)<sup>127</sup> e (10)<sup>127</sup>. Tutti i valori reali in questo intervallo possono essere usati come valori letterali nelle espressioni ER.

Un *reale* non ha conversioni implicite. Tuttavia, è possibile usare le seguenti funzioni per convertire in modo esplicito un valore *reale* in altri tipi di dati e altri tipi di dati in un valore *reale*:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Tutti gli [operatori](er-formula-language.md#Operators) di confronto e matematici possono essere usati con il tipo di dati *reale*.

## <a name="string"></a><a name="string"></a>String

Il tipo di dati primitivo *stringa* rappresenta una sequenza di caratteri utilizzati come testi, numeri di conto, indirizzi e numeri di telefono.

I valori letterali *Stringa* sono caratteri racchiusi tra virgolette (""). I valori letterali *Stringa* possono essere usati ovunque sono previsti valori *stringa* nelle espressioni ER. È possibile utilizzare le stringhe nelle espressioni logiche, come i confronti. È anche possibile concatenare i valori *stringa* usando l'operatore **\&** o la funzione [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Se si concatenano due valori *stringa* e si desidera che la *stringa* risultante si estenda su più righe, usare il separatore di interruzione di riga tra i valori. Per l'output TEXT, questo separatore può essere un carattere generato usando l'espressione [CHAR](er-functions-text-char.md)(10) o CHAR(13). Per HTML, può essere il tag **\<br\>**.

Il valore predefinito per un valore *string* è una stringa di testo vuota senza caratteri e la rappresentazione interna è un elenco di caratteri.

Non ci sono conversioni automatiche per le stringhe. Tuttavia, è possibile utilizzare le seguenti funzioni di conversione esplicite:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Per maggiori informazioni sulla trasformazione dei valori *stringa*, vedere [Elenco delle funzioni ER nella categoria di testo](er-functions-category-text.md).

Un valore *stringa* può contenere un numero indefinito di caratteri.

Tutti gli [operatori](er-formula-language.md#Operators) di confronto possono essere usati con il tipo di dati *stringa*.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica sui report elettronici](general-electronic-reporting.md)
- [Linguaggio della formula nella creazione di report elettronici](er-formula-language.md)
- [Tipi di dati compositi supportati](er-formula-supported-data-types-composite.md)
