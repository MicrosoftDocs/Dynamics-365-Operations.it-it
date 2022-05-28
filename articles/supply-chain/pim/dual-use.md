---
title: Beni a duplice uso
description: Questo argomento spiega come tenere traccia dei prodotti identificati come beni a duplice uso, memorizzare i numeri di certificato per ciascun prodotto e paese di destinazione e stampare numeri di certificato validi su fatture, documenti di trasporto e/o ordini cliente pertinenti.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COODualUseCerts, COORules, COODualUseCountries
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 787d0c4ebcf83d6bfec05943f2bb0ddc5961a93a
ms.sourcegitcommit: e18ea2458ae042b7d83f5102ed40140d1067301a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2022
ms.locfileid: "8736035"
---
# <a name="dual-use-goods"></a>Beni a duplice uso

[!include [banner](../includes/banner.md)]

I beni a duplice uso sono in genere articoli che hanno applicazioni sia civili che militari. Ad esempio, una sostanza chimica potrebbe essere utilizzata come fertilizzante o esplosivo. Molti paesi hanno normative speciali che si applicano all'esportazione, all'importazione e al trasporto di beni a duplice uso. Pertanto, è importante che le aziende coinvolte nel commercio internazionale di beni a duplice uso tengano traccia delle varie politiche e certificati.

La funzionalità per beni a duplice uso consente alle aziende di tenere traccia dei prodotti identificati come beni a duplice uso, di memorizzare i numeri di certificato per ciascun prodotto e paese di destinazione e di stampare numeri di certificato validi su fatture, documenti di trasporto e/o ordini cliente pertinenti. Garantisce inoltre che i prodotti spediti includano sempre certificazioni aggiornate.

Prendiamo in considerazione lo scenario seguente:

1. La pagina **Configurazione paese per duplice uso** nel sistema indica che le spedizioni in Francia richiedono una certificazione.
2. La pagina **Dettagli prodotto rilasciato** per il prodotto X-100 indica che si tratta di un bene a duplice uso. Insieme, il codice, la categoria, il gruppo e il regime indicano la classificazione del controllo delle esportazioni a cui appartiene il prodotto.
3. La pagina **Certificati per duplice uso** include un certificato per il prodotto X-100 quando viene spedito in Francia. Questo certificato scade il 1 gennaio 2020.
4. Il 17 giugno 2020, si crea un ordine cliente per un'azienda cliente con sede in Francia e l'ordine include il prodotto X-100.
5. Quando si conferma l'ordine cliente, il sistema determina le seguenti informazioni:

    1. L'ordine include prodotti che sono beni a duplice uso?
    2. Se l'ordine include beni a duplice uso, il paese di destinazione richiede certificati per duplice uso?
    3. Se il paese richiede certificati per duplice uso, esiste un certificato valido per ciascun bene a duplice uso per il paese di destinazione?

6. L'ordine include il prodotto X-100, il prodotto viene spedito in Francia ed esiste un certificato francese per il prodotto. Tuttavia, il certificato è scaduto. Pertanto, viene visualizzato il seguente messaggio di avviso: "I certificati per duplice uso per uno o più articoli a duplice uso in questo ordine cliente non sono validi. Procedere con la conferma?"

Questo argomento spiega come configurare tutte le impostazioni necessarie per impostare beni a duplice uso e supportare questo scenario.

## <a name="define-dual-use-requirements-for-each-relevant-country"></a>Definire i requisiti di duplice uso per ciascun paese rilevante

Ogni paese ha requisiti diversi per i beni a duplice uso. Per tenere traccia dei paesi che richiedono e non richiedono un certificato, si utilizza la pagina **Configurazione paese per duplice uso**. Le informazioni specificate in questa pagina vengono verificate quando si creano gli ordini cliente e verrà richiesto di fornire le certificazioni richieste.

Per impostare le informazioni sui requisiti di duplice uso per vari paesi, attenersi alla seguente procedura.

1. Andare a **Gestione informazioni sul prodotto \> Impostazioni \> Conformità prodotto \> Prodotti a duplice uso \> Configurazione paese per duplice uso**.
2. Selezionare una configurazione di paese esistente per modificarla oppure selezionare **Nuova** nel riquadro azioni per creare una nuova configurazione.
3. Impostare i seguenti valori per la configurazione selezionata o creata.

    | Campo | Descrizione |
    |---|---|
    | Paese | Selezionare il paese per il quale si verificano i requisiti. |
    | Certificato obbligatorio | Selezionare questa casella di controllo per i paesi che richiedono una certificazione per beni a duplice uso. Deselezionarla per i paesi che non richiedono questa certificazione. |

## <a name="create-dual-use-categories"></a>Creare categorie a duplice uso

I beni a duplice uso devono spesso essere classificati in base al numero di classificazione del controllo delle esportazioni (ECCN). L'ECCN è un codice alfanumerico che classifica gli articoli in base a fattori come la merce e la tecnologia. La pagina **Categorie a duplice uso** consente di creare un elenco delle categorie utilizzate, a fini di reporting.

Per impostare categorie a duplice uso, procedere come segue.

1. Andare a **Gestione informazioni sul prodotto \> Impostazioni \> Conformità prodotto \> Prodotti a duplice uso \> Categorie a duplice uso**.
2. Selezionare una categoria esistente per modificarla oppure selezionare **Nuova** nel riquadro azioni per creare una nuova categoria.
3. Impostare i seguenti valori per la categoria selezionata o creata.

    | Campi | Descrizione |
    |---|---|
    | Codice a duplice uso | Immettere il codice ECCN completo (ad esempio, *3A001*).|
    | Categoria a duplice uso | Immettere la parte di categoria CCL del codice ECCN. Ad esempio, per il codice ECCN *3A001*, questo valore è *3*. |
    | Gruppo a duplice uso | Immettere la parte di gruppo di prodotti del codice ECCN. Ad esempio, per il codice ECCN *3A001*, questo valore è *A*. |
    | Regime a duplice uso | Immettere il codice regime per l'articolo. Questo codice identifica il motivo per cui l'articolo è classificato come bene a duplice uso. Ad esempio, per il codice ECCN *3A001*, questo valore è *001*. |

## <a name="apply-dual-use-categories-to-products"></a>Applicare categorie a duplice uso ai prodotti

Per identificare un prodotto come bene a duplice uso e applicarvi una categoria a duplice uso, seguire questi passaggi.

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Selezionare o creare un prodotto per aprire la relativa pagina **Dettagli prodotto rilasciato**.
1. Nella Scheda dettaglio **Commercio estero**, impostare l'opzione **Prodotti a duplice uso** su **Sì** per identificare il prodotto attuale come un bene a duplice uso.
1. Impostare il campo **Codice a doppio uso** sul codice che si applica al prodotto corrente (questo codice è stato definito nella pagina **Categorie a duplice uso**).

Questa impostazione viene verificata quando si crea un ordine cliente.

## <a name="set-up-dual-use-certificates"></a>Impostare certificati per duplice uso

La pagina **Certificati per duplice uso** è utilizzata per impostare e gestire i certificati per duplice uso necessari per ciascun prodotto e paese. È possibile tenere traccia dei dettagli di ciascun certificato, come il paese e le date di validità. È inoltre possibile impostare opzioni per specificare dove stampare queste informazioni. Ad esempio, le informazioni possono essere stampate sulla fattura, sul documento di trasporto e/o sull'ordine cliente. Questa impostazione viene verificata quando si crea un ordine cliente.

1. Andare a **Gestione informazioni sul prodotto \> Impostazioni \> Conformità prodotto \> Prodotti a duplice uso \> Certificati per duplice uso**.
2. Selezionare un certificato esistente per modificarlo o selezionare **Nuovo** nel riquadro azioni per creare un nuovo certificato.
3. Impostare i seguenti valori per il certificato selezionato o creato.

    | Campo | Descrizione |
    |---|---|
    | Numero articolo | Selezionare il numero di articolo del bene a duplice uso a cui si applica questo certificato. |
    | Paese | Il paese in cui è necessario utilizzare questo certificato. |
    | Numero certificato | Il numero che appare sul certificato rilasciato al venditore o al cliente. |
    | Validità | Selezionare la data di inizio della validità del certificato corrente.|
    | Scadenza | Selezionare la data di fine della validità del certificato corrente. |
    | Stampa su fattura | Selezionare questa casella di controllo per stampare il numero di certificato sulle fatture indirizzate al paese specificato durante l'intervallo di date specificato. |
    | Stampa su documento di trasporto | Selezionare questa casella di controllo per stampare il numero di certificato sui documenti di trasporto indirizzati al paese specificato durante l'intervallo di date specificato. |
    | Stampa su ordine cliente | Selezionare questa casella di controllo per stampare il numero di certificato su ordini cliente indirizzati al paese specificato durante l'intervallo di date specificato. |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
