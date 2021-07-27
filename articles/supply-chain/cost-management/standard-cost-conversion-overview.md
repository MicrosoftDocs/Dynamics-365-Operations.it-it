---
title: Panoramica sulla conversione in costo standard
description: Questo articolo fornisce una panoramica del processo per impostare ed eseguire una conversione in costo standard. I passaggi elencati devono essere completati dopo il completamento dei prerequisiti per una conversione in costo standard.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventStdCostConv
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "78212"
- intro-internal
ms.assetid: d601d9d5-1de3-4868-aff4-534dca01d624
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 85f2c623255b8fec17acfcf7da7adbb105e921c7
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6336537"
---
# <a name="standard-cost-conversion-overview"></a>Panoramica sulla conversione in costo standard

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del processo per impostare ed eseguire una conversione in costo standard. I passaggi elencati devono essere completati dopo il completamento dei prerequisiti per una conversione in costo standard. 

Utilizzare la pagina **Conversioni costo standard** per convertire il modello inventariale utilizzato per un batch di articoli selezionati in modo da basarlo sulla determinazione dei costi standard anziché sulla determinazione dei costi effettivi. Il processo di conversione comporta l'esecuzione di una chiusura dell'inventario, il completamento dei passaggi previsti dal periodo di transizione (definito da una data di inizio transizione e da una data prevista per la conversione) e di una conversione, nonché l'inclusione di una chiusura dell'inventario associata.

-   Chiusura dell'inventario prima del periodo di transizione: una chiusura dell'inventario è un passaggio necessario poiché consente di liquidare le transazioni aperte di un articolo utilizzando il metodo di valutazione precedente. Durante il periodo di transizione è possibile immettere e registrare transazioni retrodatate, ad esempio fatture, per chiudere il periodo precedente. Affinché il nuovo metodo di valutazione risulti nettamente separato da quello precedente, la data di chiusura dell'inventario deve precedere di un giorno quella di inizio della transizione.
-   Passaggi di conversione durante il periodo di transizione: utilizzare la pagina **Conversioni costo standard** per creare un record di conversione che contenga anche l'identificatore definito dall'utente per una nuova versione di determinazione dei costi. È necessario identificare gli articoli che richiedono la conversione e immettere i costi standard in sospeso dell'articolo nella nuova versione di determinazione costi creata. Gli articoli selezionati devono quindi essere verificati per identificare eventuali problemi che impedirebbero la conversione. I problemi riscontrati devono essere risolti e deve quindi essere eseguita un'ulteriore verifica. Una volta ottenuti risultati positivi da tutte le verifiche alle quali sono stati sottoposti gli articoli, modificare lo stato del record di conversione in **Pronto**. Al decorrere della data di conversione pianificata, eseguire la conversione e, se si desidera, includere una chiusura dell'inventario. Gli spostamenti a cui un articolo viene sottoposto durante il periodo di transizione vengono registrati e valutati in base al modello inventariale precedente. Una volta eseguita la conversione, i movimenti delle scorte vengono rivalutati in base al costo standard.
-   Chiusura dell'inventario dopo la conversione: la chiusura dell'inventario può essere effettuata durante la conversione, al decorrere della data pianificata per la conversione, oppure prima della conversione, come passaggio separato.

Una volta completato correttamente il processo di conversione, ogni articolo risulterà associato a un modello inventariale di tipo Costo standard e i relativi costi standard saranno pertanto attivati. Le transazioni di magazzino successive verranno valutate in base al costo standard dell'articolo. Le transazioni di magazzino fisiche dell'articolo relative alle entrate e alle uscite verranno convertite automaticamente in base al costo standard in vigore alla data della conversione. La conversione in costo standard verrà eseguita automaticamente anche per le scorte finanziarie disponibili dell'articolo. La differenza tra i valori verrà registrata come rivalutazione delle scorte. Qualsiasi transazione eseguita dopo la conversione verrà valutata in base al costo standard dell'articolo. Poiché è necessario eseguire una chiusura dell'inventario esattamente un giorno prima della data di conversione, non è possibile immettere transazioni retrodatate precedenti la data della conversione. È possibile eseguire una conversione solo il giorno successivo a quello in cui è stata eseguita una chiusura dell'inventario, che non può essere annullata.

## <a name="1-define-a-standard-cost-conversion-record-and-the-associated-costing-version"></a>1. Definire un record di conversione in costo standard e la versione di determinazione costi associata.
Utilizzare la pagina **Conversioni costo standard** per creare un record di conversione. È possibile creare un nuovo record di conversione solo se i record di conversione esistenti sono stati completati. La durata del periodo di transizione pianificato viene definita dalla data di inizio della transizione e dalla data di conversione pianificata. La durata di un periodo di transizione pianificato può essere anche di un solo giorno. Un periodo di transizione pianificato contribuisce a garantire che il processo di conversione disponga di tempo sufficiente per completare tutti i passaggi. Un giorno prima della data di inizio della transizione è necessario effettuare una chiusura di inventario, in modo da completare le liquidazioni prima dell'avvio del processo di conversione. Per verificare che la data di inizio sella transizione e la data di chiusura di inventario siano allineate correttamente, è possibile modificare la data di inizio della transizione in modo che corrisponda al giorno successivo alla chiusura di inventario oppure eseguire una chiusura di inventario. Durante l'immissione di un record di conversione, è inoltre necessario immettere un identificatore definito dall'utente per la nuova versione di determinazione costi contenente i costi standard per gli articoli convertiti. La versione di determinazione costi viene generata automaticamente al salvataggio del record di conversione.

## <a name="2-review-and-change-the-new-costing-version-for-the-conversion-record"></a>2. Rivedere e modificare la nuova versione di determinazione costi per il record di conversione.
La nuova versione di determinazione costi è dedicata al record di conversione, come indicato dal tipo di determinazione costi **Conversione**. La versione di determinazione costi dedicata è simile alla versione di determinazione costi standard e contiene i record relativi al costo degli articoli associati al record di conversione. La versione di determinazione costi dedicata di un record di conversione ha le seguenti impostazioni, che è possibile rivedere e modificare nelle varie schede, se necessario.

-   **Tipo di costo:** questo campo deve essere impostato su **Costo standard**.
-   **Versione:** l'identificatore riflette le informazioni immesse nel record di conversione per l'ID della versione di determinazione costi.
-   **Nome:** per impostazione predefinita, il nome è vuoto. È possibile immettere un nome, se lo si desidera.
-   **Blocco:** questo campo deve essere impostato su **No**. È possibile immettere record di costi nella versione di determinazione costi finché lo stato del record di conversione non viene cambiato in **Pronto**. Lo stato di **Pronto** indica che gli articoli selezionati sono stati verificati e non devono essere consentite modifiche ai record di costi.
-   **Blocca attivazione:** questo campo deve essere impostato su **Sì**. Non è possibile attivare manualmente un record di costi in sospeso nella versione di determinazione costi dedicata. L'attivazione avviene quando la conversione viene eseguita.
-   **Data iniziale:** riflette la data di conversione pianificata immessa nel record di conversione.
-   **Sito:** lasciare il campo vuoto, per consentire l'immissione di record costi per qualsiasi sito.
-   **Gruppo di campi Consenti tipo di prezzo:** impostare il campo su **Sì**, in modo che solo i record dei prezzi di costo possono essere immessi.
-   **Principio di fallback:** questo campo è impostato su **Nessuno**. Impostare il principio di fallback su **Attivo** se sono necessarie informazioni sui costi attivate in altre versioni di determinazione costi. Le informazioni sui costi relative a componenti, categorie costi e costi indiretti, ad esempio, possono essere necessarie per calcolare i costi degli articoli prodotti.
-   **Versione di determinazione costi fallback:** lasciare vuoto questo campo.

È possibile effettuare la gestione delle informazioni sui costi degli articoli nella versione di determinazione costi dedicata solo dalla pagina **Conversioni costo standard**. Non è possibile utilizzare la pagina **Impostazione versione di determinazione costi** o la pagina **Gestione versione di determinazione costi** per calcolare i costi per la versione di determinazione costi durante la conversione. È tuttavia possibile utilizzare queste pagina per la gestione della versione di determinazione costi dedicata dopo il completamento del processo di conversione.

## <a name="3-identify-the-items-to-convert-to-standard-cost"></a>3. Identificare gli articoli da convertire in costo standard
Utilizzare la pagina **Conversioni costo standard** per identificare i singoli articoli che dovranno essere convertiti in costo standard. È possibile aggiungere più articoli utilizzando la pagina **Aggiunge articoli alla conversione in costo standard**. In generale, per garantire la correttezza del calcolo dei costi è consigliabile includere tutti gli articoli prodotti in un unico record di conversione.

## <a name="4-enter-or-calculate-the-pending-standard-cost-for-each-item-that-is-being-converted"></a>4. Immettere o calcolare il costo standard in sospeso per ogni articolo in corso di conversione.
Utilizzare la pagina **Prezzo articolo** per immettere i costi standard in sospeso nella versione di determinazione costi dedicata per gli articoli acquistati e gli articoli trasferimento. I record di costi sono specifici del sito. È quindi necessario immettere i costi in sospeso di ogni articolo per ogni sito. Utilizzare la pagina **Prezzo articolo** per calcolare i costi standard in sospeso per gli articoli prodotti. È consigliabile calcolare i costi in sospeso di ogni articolo prodotto per ogni sito di produzione, a meno che il sito non corrisponda a un sito di trasferimento. In questo caso, i costi in sospeso devono essere immessi manualmente. Alcuni articoli possono avere le dimensioni prodotto del colore, delle dimensioni o della configurazione. Nella pagina **Conversioni costo standard** la casella di controllo **Usa prezzo di costo per variante** mostra il costo standard per ciascuna combinazione di dimensioni prodotto. Se la casella di controllo è deselezionata, per l'articolo è necessario immettere solo un costo in sospeso.

## <a name="5-check-and-resolve-any-issues-for-the-items-that-are-being-converted"></a>5. Verificare gli articoli in corso di conversione e risolvere gli eventuali problemi.
Utilizzare il report **Verifiche conversione in costo standard** per identificare le uscite di articoli in corso di conversione. Se per un articolo non sussistono problemi, il relativo stato nel record di conversione passa a **Verificato**. In caso di problemi, è necessario risolverli e rieseguire il report finché lo stato dell'articolo non passa a **Verificato**. Se non è possibile risolvere un problema di un articolo in modo tempestivo, è possibile eliminare l'articolo dal record di conversione e convertirlo in seguito.

## <a name="6-change-the-status-of-the-conversion-record-to-ready"></a>6. Cambiare lo stato del record di conversione in Pronto
Quando lo stato del record di conversione viene cambiato in **Pronto**, viene eseguita una verifica finale prima dell'esecuzione della conversione in costo standard. Lo stato passa a **Pronto** solo se vengono soddisfatte le seguenti condizioni:

-   Lo stato di ogni articolo nel record di conversione è **Verificato**.
-   Una chiusura di inventario è stata eseguita in una data corrispondente a un giorno prima della data di inizio della transizione. Per verificare che la data di inizio sella transizione e la data di chiusura di inventario siano allineate correttamente, è possibile modificare la data di inizio della transizione in modo che corrisponda al giorno successivo alla chiusura di inventario oppure eseguire una chiusura di inventario.

## <a name="7-back-up-the-database-before-conversion"></a>7. Eseguire il backup del database prima della conversione
Il backup consente di ripristinare il database in caso di errori durante la conversione.

## <a name="8-perform-the-conversion-when-the-conversion-record-has-a-ready-status"></a>8. Eseguire la conversione quando lo stato del record di conversione è Pronto.
Il processo di conversione richiede l'esecuzione di una chiusura di inventario in una data corrispondente a un giorno prima della data pianificata per la conversione. Questo requisito consente di evitare l'immissione di transazioni retrodatate durante il periodo di transizione. Se non è stata eseguita la chiusura di inventario, viene chiesto se si desidera eseguire la chiusura durante il processo di conversione. Il processo di conversione gestisce un articolo alla volta. Inizia con gli articoli più in basso in una struttura di prodotto, in base al codice di basso livello dell'articolo. Quando un articolo è stato convertito, il relativo stato nel record di conversione passa a **Convertito**. Se il processo di conversione viene interrotto, lo stato di qualsiasi articolo di cui non è stata completata la conversione rimarrà impostato su **Verificato**. Il completamento del processo di conversione comporta quanto segue:

-   Lo stato del record di conversione passa da **Pronto** a **Completato** e lo stato di ogni articolo selezionato passa da **Verificato** a **Convertito**.
-   Il gruppo di modelli degli articoli convertiti viene modificato in base a un nuovo gruppo con un modello inventariale Costo standard.
-   I costi standard per gli articoli convertiti vengono attivati nella versione di determinazione costi dedicata.
-   Il tipo di determinazione costi della versione di determinazione costi passa da **Conversione** a **Costo standard** e la versione di determinazione costi è ora uguale alle altre versioni di determinazione costi standard.

## <a name="9-validate-and-reconcile-the-inventory-values-for-the-converted-items"></a>9. Convalidare e riconciliare i valori di magazzino per gli articoli convertiti
Il report **Rendiconto analisi scostamento** consente di analizzare lo scostamento di rivalutazione e il report **Valore di magazzino** consente di visualizzare il valore di magazzino in una data specifica.

-   Analizzare gli scostamenti di rivalutazione. Utilizzare il report **Rendiconto analisi scostamento** per visualizzare gli scostamenti di rivalutazione per gli articoli convertiti. È inoltre possibile utilizzare la pagina **Transazioni di costo standard** per visualizzare le transazioni di rivalutazione delle scorte per gli articoli convertiti con inventario.
-   Analizzare il valore di magazzino precedente alla data di inizio della transizione. Utilizzare il report **Valore di inventario** per visualizzare i valori di inventario per gli articoli convertiti. Per la Data finale del report, utilizzare una data che precede di un giorno la data di inizio della transizione.
-   Analizzare il valore di magazzino precedente alla data della conversione. Utilizzare il report **Valore di inventario** per visualizzare i valori di inventario per gli articoli convertiti. Come Data finale per il report, utilizzare una data che preceda di un giorno la data di conversione.
-   Analizzare il valore di magazzino nella data della conversione. Utilizzare il report **Valore di inventario** per visualizzare i valori di magazzino in corrispondenza della data della conversione. Sia la Data iniziale che la Data finale per il report devono corrispondere alla data della conversione. I criteri di selezione del report devono dare come risultato gli articoli convertiti.
-   Analizzare i movimenti di scorte retrodatati. Utilizzare il report **Valore inventario** per visualizzare i movimenti delle scorte retrodatati immessi dopo la conversione. La Data iniziale e la Data finale per il report devono corrispondere alla data di inizio della transizione e alla data di conversione, meno un giorno. I criteri di selezione del report devono dare come risultato gli articoli convertiti. Nel report sono visualizzati i movimenti delle scorte effettuati a costo standard durante il periodo di transizione.


## <a name="additional-resources"></a>Risorse aggiuntive

[Prerequisiti per la conversione in costo standard](prerequisites-standard-cost-conversion.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]