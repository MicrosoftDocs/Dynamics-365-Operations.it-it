---
title: Principio di contabilità generale di registrazione nel conto di addebito
description: In questo articolo viene fornita una panoramica del principio di contabilità Registra nel conto di addebito.
author: rachel-profitt
ms.date: 05/02/2022
ms.topic: article
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-05-02
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 998a30786b3f457b24b6e3c755b2c00967adbd4b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2022
ms.locfileid: "8879165"
---
# <a name="post-to-charge-account-accounting-principle"></a>Principio di contabilità generale di registrazione nel conto di addebito

Il principio contabile *Registra nel conto di addebito* consente di contabilizzare e riconciliare più facilmente le differenze che si verificano nel prezzo unitario tra una registrazione fisica e una registrazione finanziaria, i costi indiretti sugli articoli acquistati o gli addebiti su un ordine di acquisto. 

Due configurazioni per i codici spese Contabilità fornitori nella pagina **Codice spese** (**Contabilità fornitori \> Impostazione spese \> Codice spese**) possono far sì che un ordine di acquisto influisca sulla valutazione delle attività di magazzino:

- Per i codici spese in cui il campo **Tipo di addebito** è impostato su *Elemento* e il campo **Tipo di credito** è impostato su *Conto CoGe*, il conto CoGe selezionato come conto di assorbimento funge da conto variazione stock.
- Per i codici spese in cui il campo **Tipo di addebito** è impostato su *Elemento* e il campo **Tipo di accredito** è impostato su *Cliente/Fornitore*, l'addebito verrà contabilizzato come costo del materiale e verrà utilizzato il conto variazione stock dell'articolo.

## <a name="european-special-accounting-rule"></a>Regola contabile speciale europea

In Europa, il principio contabile *Registra nel conto di addebito* è spesso utilizzato per incorporare una regola contabile speciale. Ad esempio, uno dei seguenti metodi viene in genere utilizzato per tenere conto delle modifiche all'inventario:

- **Metodo del costo di vendita**: la configurazione del profilo di registrazione inventario standard supporta questo metodo. Il principio contabile *Registra nel conto di addebito* non è obbligatorio.
- **Metodo della natura della spesa**: le organizzazioni più piccole utilizzano spesso questo metodo. In genere comporta i seguenti passaggi:

    1. Beni o servizi sono interamente calcolati come spese al momento del ricevimento.
    2. Alla fine del periodo, viene eseguito un conteggio dei cicli.
    3. Una rettifica manuale per le quantità e il valore viene registrata nel magazzino. (Il conto di contropartita è un conto variazione stock che compensa la spesa registrata nel passaggio 1. Pertanto, vedi la variazione del valore delle scorte solo su questo conto.)

Il principio *Registra nel conto di addebito* consente di automatizzare completamente le due registrazioni. In questo modo è possibile eliminare una registrazione manuale di rettifica di chiusura di fine periodo.

## <a name="enable-the-post-to-charge-account-accounting-principle"></a>Abilitare il principio di contabilità generale di registrazione nel conto di addebito

Per abilitare il principio contabile *Registra nel conto di addebito*, attenersi alla seguente procedura.

1. Passare a **Contabilità fornitori \> Impostazioni \> Parametri contabilità fornitori**.
2. Nella scheda **Fattura**, nella scheda Dettaglio **Fattura**, imposta l'opzione **Registra nel conto di addebito nella contabilità generale** su *Sì*.
3. Chiudi la pagina.

## <a name="prerequisites-and-recommended-parameters-for-the-post-to-charge-account-accounting-principle"></a>Prerequisiti e parametri consigliati per il principio di contabilità Registra nel conto di addebito

Se prevedi di tenere conto delle spese di acquisto e delle variazioni delle scorte, devono essere presenti i seguenti prerequisiti:

- Nella scheda **Fattura** della pagina **Parametri contabilità fornitori** (**Contabilità fornitori \> Imposta \> Parametri contabilità fornitori**), l'opzione **Registra nel conto di addebito nella contabilità generale** deve essere impostata su *Sì*.
- Nella pagina **Gruppi di modelli di articoli** (**Gestione costi \> Impostazione criteri contabili inventario \> Gruppi di modelli di articoli**), tutte le seguenti opzioni devono essere impostate su *Sì* per ogni relativo gruppo di modelli che contiene articoli inclusi in un ordine di acquisto:

    - Registra inventario fisico
    - Registra inventario finanziario
    - Passività ratei all'entrata prodotti

- Nella scheda **Consegna** della pagina **Parametri di approvvigionamento** (**Approvvigionamento \> Imposta \> Parametri di approvvigionamento**), l'opzione **Genera spese sull'entrata prodotti** deve essere impostata su *Sì*.
- Nella scheda **Contabilità inventario** della pagina **Parametri di gestione articoli e magazzino** (**Gestione inventario \> Imposta \> Parametri di gestione articoli e magazzino**), l'opzione **Registra il documento di trasporto nella contabilità generale** deve essere impostata su *Sì*.
- Nella scheda **Ordine fornitore** della pagina **Registrazione** (**Gestione inventario \> Imposta \> Registrazione \> Registrazione**), i conti principali che si applicano a ogni relativa voce devono essere specificati per ciascuno dei seguenti tipi di registrazione:

    - Spese acquisto, non fatturate
    - Spese acquisto per prodotto
    - Variazione scorte

## <a name="example-scenario-1-change-in-unit-cost-price"></a>Scenario di esempio 1: variazione del prezzo di costo unitario

Questo scenario di esempio ha i seguenti prerequisiti.

- Modello di costo FIFO (first in, first out)

La procedura seguente fornisce un esempio che mostra cosa succede quando si modifica il prezzo di costo unitario in un ordine di acquisto.

1. Crea un ordine fornitore per una quantità pari a 1 di un articolo e un prezzo unitario di 100,00.
2. Conferma l'ordine fornitore.
3. Registra l'entrata del prodotto per l'ordine fornitore.
4. Convalida il giustificativo sullo scontrino del prodotto. La tabella seguente mostra un esempio di giustificativo.

    | Tipo di registrazione | Conto principale | Nome conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Fisico/finanziario? | Importo |
    |---|---|---|---|---|---|---|---|
    | Acquisti, variazione scorte | 600170 | Materiali variazione scorte | Spese | Credito | Numero | Fisica | -100,00 |
    | Costo dei materiali acquistati ricevuti | 140100 | Inventario dei materiali | Cespite | Dare | Sì | Fisica | 100.00 |
    | Spese acquisto, non fatturate | 600180 | Entrate materiali | Spese | Dare | Sì | Fisica | 100.00 |
    | Acquisto, rateo | 200140 | Acquisti accumulati | Passività | Credito | Sì | Fisica | -100,00 |

5. Registra la fattura per l'ordine fornitore che ha un prezzo unitario aggiornato di 110,00.
6. Convalida il giustificativo sulla fattura. La tabella seguente mostra un esempio di giustificativo.

    | Tipo di registrazione | Conto principale | Nome conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Fisico/finanziario? | Importo |
    |---|---|---|---|---|---|---|---|
    | Acquisti, variazione scorte | 600170 | Materiali variazione scorte | Spese | Credito | Numero | Finanziario | -10.00 |
    | Costo dei materiali acquistati ricevuti | 140100 | Inventario dei materiali | Cespite | Dare | Sì | Finanziario | -100,00 |
    | Spese acquisto, non fatturate | 600180 | Entrate materiali | Spese | Dare | Sì | Finanziario | -100,00 |
    | Acquisto, rateo | 200140 | Acquisti accumulati | Passività | Credito | Sì | Finanziario | 100.00 |
    | Costo dei materiali acquistati fatturati | 140100 | Inventario dei materiali | Cespite | Dare | Numero | Finanziario | 110.00 |
    | Spese acquisto per prodotto | 600180 | Entrate materiali | Spese | Credito | Numero | Finanziario | 110.00 |
    | Saldo fornitore | 211000 | Commerciale Contabilità fornitori | Passività | Credito | Numero | Finanziario | -110,00 |

## <a name="example-2-charges-and-indirect-costs-on-the-purchase-order"></a>Esempio 2: addebiti e costi indiretti sull'ordine fornitore

Questo scenario di esempio ha i seguenti prerequisiti.

- Modello di costo FIFO
- **Codice spese 1:** voce di debito e conto di credito per il 10%
- **Codice spese 2:** voce di debito e cliente/fornitore del credito per il 10.00 proporzionale
- **Costo indiretto:** 2,00% aggiunto al prezzo di acquisto

La procedura seguente fornisce un esempio che mostra cosa succede quando si includi spese e costi indiretti su un ordine fornitore.

1. Crea un ordine fornitore per una quantità pari a 1 di un articolo e un prezzo unitario di 100,00.
2. Aggiungi un codice spese per il 10 percento che addebita l'articolo e accredita il libro mastro.
3. Aggiungi un codice spese per il 10.00 che addebita l'articolo e accredita il cliente/fornitore.
4. Assegna le spese alle righe dell'ordine fornitore.
5. Conferma l'ordine fornitore.
6. Registra l'entrata del prodotto per l'ordine fornitore.
7. Convalida il giustificativo sullo scontrino del prodotto. La tabella seguente mostra un esempio di giustificativo.

    | Tipo di registrazione | Conto principale | Nome conto principale | Tipo di account | Dare/Avere? | Conto di compensazione | Fisico o finanziario | Importo |
    |---|---|---|---|---|---|---|---|
    | Acquisti, variazione scorte | 600170 | Materiali variazione scorte | Spese | Credito | Numero | Fisica | -110,00 |
    | Costi indiretti assorbiti stimati | 600520 | Costi indiretti assorbiti | Spese | Credito | Sì | Fisica | -2,40 |
    | Spese di trasporto sulle merci acquistate | 600120 | Costi di trasporto | Spese | Credito | Numero | Fisica | -10.00 |
    | Costo dei materiali acquistati ricevuti | 140100 | Inventario dei materiali | Cespite | Dare | Sì | Fisica | 122.40 |
    | Spese acquisto, non fatturate | 600180 | Entrate materiali | Spese | Dare | Sì | Fisica | 110.00 |
    | Acquisto, rateo | 200140 | Acquisti accumulati | Passività | Credito | Sì | Fisica | -110,00 |

8. Registra la fattura relativa all'ordine fornitore.
9. Convalida il giustificativo sulla fattura. La tabella seguente mostra un esempio di giustificativo.

    | Tipo di registrazione | Conto principale | Nome conto principale | Tipo di account | Dare/Avere | Conto di compensazione | Fisico/finanziario? | Importo |
    |---|---|---|---|---|---|---|---|
    | Acquisti, variazione scorte | 600170 | Materiali variazione scorte | Spese | Credito | Numero | Finanziario | 0,00 |
    | Costi indiretti assorbiti stimati | 600520 | Costi indiretti assorbiti | Spese | Dare | Sì | Finanziario | 2.40 |
    | Costi indiretti assorbiti | 600520 | Costi indiretti assorbiti | Spese | Dare | Numero | Finanziario | -2,40 |
    | Costo dei materiali acquistati ricevuti | 140100 | Inventario dei materiali | Cespite | Credito | Sì | Finanziario | -110,00 |
    | Spese acquisto, non fatturate | 600180 | Entrate materiali | Spese | Credito | Sì | Finanziario | -110,00 |
    | Acquisto, rateo | 200140 | Acquisti accumulati | Passività | Dare | Sì | Finanziario | 110.00 |
    | Costo dei materiali acquistati fatturati | 140100 | Inventario dei materiali | Cespite | Dare | Numero | Finanziario | 110.00 |
    | Spese acquisto per prodotto | 600180 | Entrate materiali | Spese | Credito | Numero | Finanziario | 110.00 |
    | Saldo fornitore | 211000 | Commerciale Contabilità fornitori | Passività | Credito | Numero | Finanziario | -110,00 |
