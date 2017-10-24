---
title: Domande frequenti sui calcoli per i modelli di configurazione prodotto
description: In questo articolo vengono descritti i calcoli per i modelli di configurazione prodotto e viene spiegato come utilizzare i calcoli insieme ai vincoli.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PCConstraintEditor, PCProductConfigurationModelDetails, PCRuntimeConfigurator
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 19191
ms.assetid: 8993f9a1-d1c0-49f5-afd3-5e1077ded0fe
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: fea4e139d32c780769bafe08d603b828d366550c
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---

# <a name="calculations-for-product-configuration-models-faq"></a>Domande frequenti sui calcoli per i modelli di configurazione prodotto

[!include[banner](../includes/banner.md)]


In questo articolo vengono descritti i calcoli per i modelli di configurazione prodotto e viene spiegato come utilizzare i calcoli insieme ai vincoli.

I calcoli possono essere utilizzati per le operazioni aritmetiche o logiche e sono complementari ai vincoli di espressione nei modelli di configurazione prodotto. È possibile definire i calcoli nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**, quindi sviluppare espressioni per i calcoli nell'editor espressioni. Per ulteriori informazioni sul calcolo, vedere Creazione di calcoli.

## <a name="what-is-a-calculation"></a>Cos'è un calcolo?
Il calcolo è un elemento che è possibile utilizzare in un modello di configurazione prodotto. I calcoli completano i vincoli consentendo di calcolare i valori utilizzando numeri decimali quando si configura un prodotto. Inoltre, i calcoli dispongono di un set di operatori più ampio rispetto ai vincoli.  

Analogamente a un vincolo, un calcolo è associato a un componente specifico nel modello di configurazione prodotto e non può essere riutilizzato da un altro componente o essere condiviso con un altro componente. Una differenza importante tra i calcoli e i vincoli è che i calcoli sono imperativi (unidirezionali), mentre i vincoli sono dichiarativi (bidirezionali). Per ulteriori informazioni sui vincoli, vedere [Vincoli di espressione e vincoli di tabella](expression-constraints-table-constraints-product-configuration-models.md).  

Un calcolo è costituito da un'espressione di calcolo e da un attributo di destinazione.

## <a name="what-is-a-target-attribute"></a>Cos'è un attributo di destinazione?
Un attributo di destinazione è un attributo che riceve il risultato dell'espressione di calcolo.  

Nella seguente espressione, l'attributo di destinazione è la misurazione di una tovaglia:  

**Expressione:** If\[decimalAttribute1 &lt;= decimalAttribute2, True, False\]  

**DecimalAttribute1** è la lunghezza del tavolo e **decimalAttribute2** è la lunghezza della tovaglia. Tale espressione restituisce un valore **True** all'attributo di destinazione se **decimalAttribute2** è maggiore o uguale a **decimalAttribute1**. In caso contrario, l'espressione restituisce il valore **False**. Di conseguenza la misura della tovaglia è accettabile se la sua lunghezza è uguale o superiore alla lunghezza del tavolo.

## <a name="what-attribute-types-can-be-set-to-target-attributes"></a>Quali tipi di attributo possono essere impostati per gli attributi di destinazione?
Tutti i tipi di attributo che sono supportati per la configurazione prodotto possono essere impostati sugli attributi di destinazione ad eccezione del testo senza un elenco predefinito.

## <a name="can-the-value-of-a-target-attribute-restrict-the-values-of-the-input-attributes-in-a-calculation"></a>Il valore di un attributo di destinazione può limitare i valori per gli attributi di input in un calcolo?
No, il valore di un attributo di destinazione non può limitare i valori per gli attributi di input, poiché i calcoli sono unidirezionali. Di conseguenza, il valore dell'attributo di destinazione è impostato in base alle modifiche nel valore degli attributi di input, ma una modifica nel valore di destinazione non influisce sul valore degli attributi di input. Questo comportamento è diverso dal comportamento dei vincoli. I vincoli sono validi in entrambe le direzioni.

### <a name="example"></a>Esempio

Nella seguente espressione, la destinazione per il calcolo è la lunghezza di un cavo di alimentazione e il valore di input è un colore:  

**Espressione**: \[If Color == "Verde", 1,5, 1,0]\]  

Quando si configura l'articolo, la lunghezza del cavo di alimentazione viene impostata su **1,5** se si specifica **Verde** come valore dell'attributo colore. Se si specifica un qualsiasi altro colore, la lunghezza diventa **1,0**. Tuttavia, poiché i calcoli sono unidirezionali, il calcolo non fissa il valore dell'attributo colore su **Verde** se si specifica prima la lunghezza di **1,5**.

## <a name="what-happens-if-a-calculation-has-a-target-attribute-of-the-integer-type-but-a-calculation-generates-a-decimal-number"></a>Cosa succede se un calcolo dispone di un attributo di destinazione di tipo intero ma un calcolo genera come risultato un numero decimale?
Se un attributo di destinazione è di tipo intero, ma un calcolo genera un numero decimale, solo la parte intera del risultato del calcolo viene restituita. La parte decimale viene rimossa e il risultato non viene arrotondato. Ad esempio, il risultato di 12,70 verrà visualizzato come 12.

## <a name="when-do-calculations-occur"></a>Quando si verificano i calcoli?
I calcoli si verificano quando si immette un valore per tutti gli attributi di input.

## <a name="can-i-overwrite-the-value-that-is-calculated-for-the-target-attribute"></a>È possibile sovrascrivere il valore calcolato per l'attributo di destinazione?
È possibile sovrascrivere il valore calcolato per l'attributo di destinazione, a meno che l'attributo di destinazione non sia impostato come nascosto o di sola lettura.

## <a name="how-do-i-set-a-target-attribute-as-hidden-or-readonly"></a>Come si imposta un attributo di destinazione come nascosto o di sola lettura?
Per impostare un attributo come nascosto o di sola lettura, effettuare le operazioni seguenti:

1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Comune** &gt; **Modelli di configurazione prodotto**.
2.  Selezionare un modello di configurazione prodotto e quindi nel Riquadro azioni fare clic su **Modifica**.
3.  Nella pagina **Dettagli modello di configurazione prodotto basato su vincoli**, selezionare l'attributo da utilizzare come attributo di destinazione.
4.  Nella scheda dettaglio **Attributi** selezionare **Nascosto** o **Sola lettura**.

## <a name="can-a-calculation-overwrite-the-values-that-i-set"></a>Può un calcolo sovrascrivere i valori impostati dall'utente?
N. I valori impostati quando si configura un prodotto sono i valori che vengono utilizzati. Il calcolo che si verifica quando i valori di input nel calcolo vengono modificati non può sovrascrivere i valori che sono stati immessi per un attributo specifico.

## <a name="what-happens-if-i-remove-an-input-value-in-a-calculation"></a>Cosa succede se si rimuove un valore di input nel calcolo?
Se si rimuove un valore di input nel calcolo, anche il valore dell'attributo di destinazione verrà rimosso.

## <a name="why-do-i-receive-an-error-message-that-says-that-my-model-is-in-contradiction"></a>Perché viene visualizzato un messaggio di errore indicante che il modello è in conflitto?
Questo messaggio viene visualizzato quando un calcolo include un errore o quando è presente un conflitto in uno o più vincoli. Per ulteriori informazioni sui conflitti nei vincoli, vedere [Vincoli di espressione e vincoli di tabella](expression-constraints-table-constraints-product-configuration-models.md). Di seguito sono elencate alcune situazioni in cui gli errori possono verificarsi nei calcoli:

-   Un valore viene suddiviso per 0 (zero.
-   È presente un conflitto tra i due seguenti elementi:
    -   I valori disponibili per un attributo e che vengono limitati da un vincolo.
    -   Un valore generato da un calcolo.
-   I valori restituiti dal calcolo sono al di fuori del dominio dell'attributo. Un esempio è un intero da  \[1..10\] che viene calcolato in 0.

## <a name="why-do-i-receive-an-error-message-even-though-i-successfully-validated-my-product-model"></a>Poiché viene generato un messaggio di errore anche se il modello prodotto è stato convalidato correttamente?
I calcoli non sono inclusi nella convalida. È necessario eseguire il test del modello di configurazione prodotto per individuare gli errori nei calcoli. Nei passaggi seguenti viene descritto come eseguire i test di un modello di configurazione prodotto:

1.  Fare clic su **Gestione informazioni sul prodotto** &gt; **Comune** &gt; **Modelli di configurazione prodotto**.
2.  Selezionare un modello di configurazione prodotto e quindi nel gruppo **Esecuzione** del Riquadro azioni fare clic su **Test**.





