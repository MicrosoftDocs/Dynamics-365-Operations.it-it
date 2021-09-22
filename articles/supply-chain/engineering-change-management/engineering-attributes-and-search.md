---
title: Attributi di progettazione e ricerca di attributi di progettazione
description: Questo argomento spiega come utilizzare gli attributi di progettazione per specificare tutte le caratteristiche non standard al fine di garantire che tutti i dati di rappresentazione generale prodotto possano essere registrati nel sistema. Spiega inoltre come utilizzare la ricerca per attributi di progettazione per trovare facilmente i prodotti in base a tale caratteristiche registrate.
author: t-benebo
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EngChgProductAttributeSearch, EngChgMaintainAttributeInheritance, EngChgAttribute
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 5cb4c2b9b4a3c54e71f73369096d00b436079c1c
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2021
ms.locfileid: "7475014"
---
# <a name="engineering-attributes-and-engineering-attribute-search"></a>Attributi di progettazione e ricerca di attributi di progettazione

[!include [banner](../includes/banner.md)]

Per garantire che tutti i dati di rappresentazione generale prodotto possano essere registrati nel sistema, è necessario utilizzare gli attributi di progettazione per specificare tutte le caratteristiche non standard. È quindi possibile utilizzare la ricerca per attributi di progettazione per trovare facilmente i prodotti in base a tale caratteristiche registrate.

## <a name="create-engineering-attributes-and-attribute-types"></a>Creare attributi di progettazione e tipi di attributi di progettazione

In genere, i prodotti di progettazione hanno molte caratteristiche e proprietà che è necessario acquisire. Sebbene sia possibile registrare alcune proprietà utilizzando i campi del prodotto standard, è anche possibile creare nuove proprietà di progettazione come richiesto. È possibile definire i propri *attributi di progettazione* e renderli parte della definizione del prodotto.

Ogni attributo di progettazione deve appartenere a un *tipo di attributo*. Questo requisito esiste perché ogni attributo di progettazione deve avere un *tipo di dati* che definisce i tipi di valori che può contenere. Un tipo di attributo di progettazione può essere un tipo standard (come testo libero, intero o decimale) o un tipo personalizzato (come testo con set specifico di valori tra cui scegliere). È possibile riutilizzare ogni tipo di attributo con qualsiasi numero di attributi di progettazione.

### <a name="set-up-engineering-attribute-types"></a>Impostare i tipi di attributi di progettazione

Per visualizzare, creare o modificare un tipo di attributo di progettazione, seguire questi passaggi.

1. Andare a **Gestione modifiche di progettazione \> Imposta \> Attributi \> Tipi di attributo**.
1. Selezionare un tipo di attributo esistente nel riquadro dell'elenco oppure selezionare **Nuovo** nel riquadro azioni per creare un nuovo tipo di attributo.
1. Imposta i seguenti campi:

    - **Nome tipo di attributo** - Immettere un nome per il tipo di attributo.
    - **Tipo** - Selezionare un tipo di dato standard (*Valuta*, *DateTime*, *Decimale*, *Intero*, *Testo*, *Booleano* o *Riferimento*).
    - **Elenco fisso** - Questa opzione è disponibile solo se si imposta il campo **Tipo** su *Testo*. Impostare l'opzione su *Sì* per definire valori specifici per attributi di questo tipo. In questo caso, verrà creato un elenco a discesa. Utilizzare la Scheda dettaglio **Valore** per stabilire i valori disponibili per questo tipo di attributo. Impostare questa opzione su *No* per consentire agli utenti di inserire qualsiasi valore. In questo caso, verrà creato un campo di input.
    - **Intervallo di valori** - Questa opzione è disponibile solo se si imposta il campo **Tipo** su *Intero*, *Decimale* o *Valuta*. Impostare l'opzione su *Sì* per stabilire i valori minimi e massimi che verranno accettati per attributi di questo tipo. Utilizzare la Scheda dettaglio **Intervallo** per stabilire i valori minimi e massimo e (per la valuta) la valuta che si applica per i limiti immessi. Impostare questa opzione su *No* per accettare qualsiasi valore. 
    - **Unità di misura** - Questo campo è disponibile solo se si imposta il campo **Tipo** su *Intero* o *Decimale*. Selezionare l'unità di misura che si applica a questo tipo di attributo. Se non è richiesta alcuna unità, lasciare vuoto il campo.

### <a name="set-up-engineering-attributes"></a>Impostare gli attributi di progettazione

Per visualizzare, creare o modificare un attributo di progettazione, seguire questi passaggi.

1. Andare a **Gestione modifiche di progettazione \> Imposta \> Attributi \> Attributi di progettazione**.
1. Selezionare un attributo esistente nel riquadro dell'elenco oppure selezionare **Nuovo** nel riquadro azioni per creare un nuovo attributo.
1. Imposta i seguenti campi:

    - **Nome** - Immettere un nome per l'attributo. Questo nome viene visualizzato solo nella pagina **Attributi di progettazione**. In qualsiasi altro punto del sistema, il valore del campo **Nome descrittivo** viene visualizzato in genere per identificare l'attributo.
    - **Tipo di attributo** - Selezionare un tipo di attributo definito nella sezione precedente.
    - **Nome descrittivo** - Immettere un nome che identificherà l'attributo nel sistema (ad eccezione della pagina **Attributi di progettazione**). 
    - **Descrizione** - Immettere una descrizione dell'attributo.
    - **Testo guida** - Immettere il testo della guida che indichi agli altri utenti lo scopo dell'attributo.
    - **Valore predefinito** - Immettere un valore predefinito per l'attributo. Le opzioni presentate dipendono dal tipo di attributo selezionato.
    - **Valuta** - Se il tipo di attributo selezionato è una valuta, selezionare la valuta accettata dall'attributo e in cui verranno visualizzati i valori.

1. Se il tipo di attributo selezionato è un numero intero o un decimale, viene visualizzata la Scheda dettaglio **Intervallo**. Nella Scheda dettaglio impostare i seguenti campi, in base alle esigenze:

    - **Azione tolleranza** - Selezionare la modalità di risposta del sistema se un utente immette un valore al di fuori dell'intervallo specificato. Se si seleziona *Avviso*, viene visualizzato un avviso, ma l'utente può salvare il valore. Se si seleziona *Non consentito*, viene visualizzato un avviso e il valore non può essere salvato fino a quando l'utente non lo corregge.
    - **Minimo** - Immettere il valore minimo consigliato o accettato.
    - **Massimo** - Immettere il valore massimo consigliato o accettato.

### <a name="engineering-attribute-inheritance"></a>Ereditarietà degli attributi di progettazione

Per le strutture di prodotto, come distinte base (BOM) o formule, gli attributi selezionati possono essere trasferiti dagli articoli figlio fino agli articoli padre. Questo processo può essere definito "ereditarietà inversa".

#### <a name="turn-on-this-feature-for-your-system"></a>Attivare questa funzionalità per il sistema

Se il sistema in uso non include già le funzionalità descritte in questa sezione, vedere [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) e attivare la funzionalità *Ereditarietà di attributi migliorata per la gestione della modifica della progettazione*.

#### <a name="attribute-inheritance-example"></a>Esempio di ereditarietà degli attributi

Per un prodotto alimentare, ad esempio una torta alle carote, il sistema deve registrare ogni allergene contenuto nel prodotto. La torta alle carote può essere modellata nel sistema come un prodotto di progettazione che dispone di una formula. Questa formula contiene gli ingredienti della torta alle carote, ad esempio farina, latte, carote e frutta a guscio. In questo esempio, la società fornisce due modelli di torta alle carote: uno che contiene lattosio e uno che non lo contiene.

La torta che contiene lattosio ha i seguenti attributi a livello di ingredienti:

- Ingrediente "farina": attributo "glutine" = sì
- Ingrediente "latte": attributo "lattosio" = sì
- Ingrediente "frutta a guscio": attributo "frutta a guscio" = sì

La torta che non contiene lattosio utilizza latte senza lattosio e ha i seguenti attributi a livello di ingredienti:

- Ingrediente "farina": attributo "glutine" = sì
- Ingrediente "latte": attributo "lattosio" = no
- Ingrediente "frutta a guscio": attributo "frutta a guscio" = sì

Poiché questi prodotti sono per lo più simili, potrebbe essere conveniente trasferire questi attributi dai figli (le due varianti) al prodotto padre (la torta alle carote di base). Per implementare questa "ereditarietà inversa", è possibile utilizzare la funzionalità *Ereditarietà degli attributi*. Questa funzionalità è definita per ciascuna [versione di progettazione](engineering-versions-product-category.md).

## <a name="connect-engineering-attributes-to-an-engineering-product-category"></a>Collegare attributi di progettazione a una categoria di prodotti di progettazione

Alcuni attributi di progettazione si applicano a tutti i prodotti, mentre altri sono specifici per singoli prodotti o categorie di prodotti. Ad esempio, gli attributi elettrici non sono richiesti per i prodotti meccanici. Pertanto, è possibile configurare *categorie di prodotti di progettazione*. Una categoria di prodotti di progettazione stabilisce la raccolta di attributi di progettazione che devono far parte della definizione dei prodotti che appartengono a tale categoria. È inoltre possibile specificare quali attributi di progettazione sono obbligatori e se è presente un valore predefinito.

Per ulteriori informazioni su come utilizzare le categorie di prodotti di progettazione, incluse le informazioni su come collegare gli attributi alle categorie, vedere [Versioni di progettazione e categorie di prodotti di progettazione](engineering-versions-product-category.md).

## <a name="set-attribute-values-for-engineering-attributes"></a>Impostare i valori degli attributi per gli attributi di progettazione

Gli attributi di progettazione collegati a una categoria di prodotti di progettazione vengono presentati quando si crea un nuovo prodotto di progettazione basato su quella categoria. A quel punto, è possibile impostare i valori per gli attributi. Successivamente, questi valori possono essere modificati nella pagina **Versione di progettazione** o nell'ambito della gestione delle modifiche di progettazione in un ordine di modifiche di progettazione. Per ulteriori informazioni, vedere [Gestire le modifiche ai prodotti di progettazione](engineering-change-management.md).

## <a name="create-an-engineering-product"></a>Creare un prodotto di progettazione

Per creare un prodotto di progettazione, aprire il la pagina **Prodotti rilasciati**. Quindi, nel riquadro azioni, nella scheda **Prodotto**, nel gruppo **Nuovo** selezionare **Prodotto di progettazione**.

È necessario specificare la categoria di progettazione a cui appartiene il prodotto. La categoria imposterà tutti i valori e le caratteristiche predefiniti per il prodotto. Inoltre, imposterà gli attributi applicabili al prodotto. Dopo che la categoria è stata selezionata, verranno impostati i valori per gli attributi. È quindi possibile modificare questi valori.

## <a name="search-for-products-by-using-engineering-attribute-values"></a>Cercare i prodotti utilizzando i valori degli attributi di progettazione

È possibile utilizzare la ricerca degli attributi di progettazione per trovare i prodotti cercandone i valori. Pertanto, è possibile trovare facilmente i prodotti di progettazione in base alle loro caratteristiche. È possibile cercare i prodotti che appartengono a una categoria di prodotti di progettazione oppure eseguire la ricerca in tutti i prodotti di progettazione.

La ricerca è disponibile nelle pagine dei dati di rappresentazione generale prodotto e negli articoli transazionali nel sistema, come gli ordini cliente. Per un articolo transazionale, è possibile utilizzare la pagina **Ricerca attributi di progettazione** per cercare un prodotto. È quindi possibile utilizzare il pulsante **Aggiungi come nuova riga** per aggiungere il prodotto alle righe dell'ordine cliente. I prodotti nei risultati di ricerca possono anche essere aggiunti direttamente all'ordine.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
