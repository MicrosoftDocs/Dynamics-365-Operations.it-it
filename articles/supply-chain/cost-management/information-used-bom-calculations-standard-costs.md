---
title: Informazioni utilizzate nei calcoli DBA con costi standard
description: Per i calcoli della distinta base (DBA) vengono utilizzati dati provenienti da diverse origini allo scopo di conteggiare i costi standard di un articolo prodotto. Le possibili origini includono informazioni sugli articoli, i cicli di lavorazione delle distinte base, le formule di calcolo dei costi indiretti e la versione di determinazione costi.
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMCalcDialog, BOMCalcGroup, BOMCalcTable, ProdParmBOMCalc
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 65571
ms.assetid: ca17e6dd-b16a-4bbc-8682-b16345ab9906
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ec6ffe41d6dae10693b1a1ebd6e5012c32bc2e6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "1557618"
---
# <a name="information-used-in-bom-calculations-with-standard-costs"></a>Informazioni utilizzate nei calcoli DBA con costi standard

[!include [banner](../includes/banner.md)]

Per i calcoli della distinta base (DBA) vengono utilizzati dati provenienti da diverse origini allo scopo di conteggiare i costi standard di un articolo prodotto. Le possibili origini includono informazioni sugli articoli, i cicli di lavorazione delle distinte base, le formule di calcolo dei costi indiretti e la versione di determinazione costi.

Nelle informazioni sull'articolo acquistato utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Costo - I costi di un articolo acquistato vengono gestiti come record costi specifici del sito in una versione di determinazione costi per costi standard. Ogni record ha una data di validità e la data del calcolo DBA determina il record di costo che verrà utilizzato. Ad esempio, un calcolo DBA con una data di calcolo futura può utilizzare un record di costo con stato in sospeso e una data di validità futura.
-   Gruppo di costi: il gruppo di costi assegnato a un articolo acquistato costituisce la base per la segmentazione dei costi nei costi calcolati di un articolo prodotto.
-   Le condizioni di avviso incorporate nel gruppo di calcolo DBA dell'articolo consentono l'identificazione di potenziali problemi, ad esempio un articolo acquistato con un costo uguale a zero, una quantità pari a zero in una DBA o un record di costo non aggiornato. Le condizioni di avviso applicabili possono essere sovrascritte quando si avvia un calcolo DBA.

Nelle informazioni sull'articolo prodotto utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Quantità ordine standard al magazzino - La quantità dell'ordine standard dell'articolo per il magazzino costituisce la dimensione gruppo di transazioni contabili predefinita per l'ammortamento dei costi costanti in un calcolo DBA. Tale dimensione rifletterà anche il multiplo della quantità ordine, se specificato.
-   Le condizioni di avviso incorporate nel gruppo di calcolo DBA dell'articolo consentono l'identificazione di potenziali problemi, come nel caso di un articolo prodotto senza una DBA o un ciclo di lavorazione. Le condizioni di avviso applicabili possono essere sovrascritte quando si avvia un calcolo DBA.

Nelle informazioni sulla DBA utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Versione DBA - Alla versione della DBA assegnata all'articolo prodotto sono associati date di inizio e fine validità e uno stato (approvato e attivo). Tale versione può essere a livello di società o specifica del sito e può eventualmente riflettere i punti di interruzione quantità.
-   Quantità articolo della riga DBA - Per un componente in genere è richiesta una quantità variabile, ma può anche essere costante. La quantità componente in genere viene espressa per la produzione di un articolo principale, ma può essere espressa per 100 o 1000 allo scopo di gestire eventuali problematiche connesse alla precisione decimale. La quantità componente può inoltre essere calcolata in base alle misurazioni.
-   Scarto articolo per la riga DBA: un componente può avere una quantità variabile o costante per lo scarto pianificato.
-   Date di validità articolo per la riga DBA: a un componente possono essere associate date di inizio e fine validità.
-   Tipo di produzione articolo per la riga DBA - La dimensione gruppo di transazioni di determinazione costi per l'ammortamento dei costi costanti rifletterà la quantità del calcolo DBA e la modalità di esplosione Produzione su ordine, in quanto per il calcolo DBA si presuppone che il componente prodotto verrà prodotto nella quantità esatta e non nella relativa quantità ordine standard.
-   DBA secondaria per un componente prodotto: per un componente prodotto è possibile specificare facoltativamente una versione della DBA da utilizzare al posto della versione della DBA attiva corrente dell'articolo in un calcolo DBA.
-   Ciclo di lavorazione secondario per un componente prodotto: per un componente prodotto è possibile specificare facoltativamente una versione del ciclo di lavorazione da utilizzare al posto della versione del ciclo attiva corrente dell'articolo in un calcolo DBA.
-   Numero di operazione e impatto delle relative percentuali di scarto - Tale numero collega un componente a una determinata operazione, che può avere una percentuale di scarto. Il collegamento consente durante i calcoli DBA di tenere conto delle percentuali di scarto e di scarto cumulativo tra più operazioni rispetto alla quantità richiesta del componente.
-   Articolo riga DBA ignorato nei calcoli di costo: un componente può essere ignorato ai fini dei calcoli DBA.

Nelle informazioni sulle risorse operative utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Costi orari - I costi orari associati a una risorsa operativa sono espressi in termini di categorie di costi assegnate al tempo di impostazione e al tempo di esecuzione. Tali categorie di costi devono essere identificate per i gruppi di risorse e le risorse operative. I costi orari associati a una categoria di costi possono essere a livello di società o specifici di un sito.
-   Costi per unità - In alcuni ambienti di produzione i costi delle risorse operative vengono assegnati per unità di prodotto, da esprimere come categoria di costi diversa per la quantità. I costi relativi alla quantità possono, ad esempio, riflettere le tariffe al pezzo della manodopera oppure un produttore di vernici può assegnare i costi della risorsa operativa per chilo di prodotto.
-   Informazioni delle risorse operative ignorate nelle operazioni del ciclo di lavorazione - Le informazioni delle risorse relative alle categorie di costi verranno ereditate dalle operazioni, in cui possono essere ignorate. Per i calcoli DBA verranno utilizzate le informazioni sulle categorie di costi specificate nelle operazioni del ciclo di lavorazione.
-   Gruppo di costi per una categoria di costi - Il gruppo di costi assegnato a una categoria di costi fornisce la segmentazione dei costi nei costi calcolati di un articolo prodotto. È ad esempio possibile utilizzare gruppi di costi diversi per segmentare i costi calcolati associati ai macchinari e alla manodopera oppure al tempo di impostazione e al tempo di esecuzione.

Nelle informazioni sul ciclo di lavorazione utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Versione del ciclo di lavorazione - Alla versione del ciclo di lavorazione assegnata all'articolo prodotto sono associati date di inizio e fine validità e uno stato (approvato e attivo). Tale versione deve essere specifica del sito e può eventualmente riflettere i punti di interruzione quantità.
-   Durata dell'operazione del ciclo di lavorazione - La durata può essere specificata per il tempo di esecuzione e di impostazione. La durata in ore di solito viene espressa per la produzione di un articolo principale, ma può anche essere espressa per 100 o per 1000 allo scopo di gestire eventuali problematiche connesse alla precisione decimale.
-   Durata dell'operazione del ciclo di lavorazione per le risorse secondarie - Una risorsa secondaria ha lo stesso numero di operazione della risorsa principale e la stessa durata dell'operazione del ciclo di lavorazione. Un'operazione può ad esempio richiedere un macchinario come risorsa principale e manodopera e strumenti come risorse secondarie.
-   Percentuale di scarto dell'operazione del ciclo di lavorazione - I calcoli DBA tengono conto delle percentuali di scarto e delle percentuali di scarto cumulativo tra più operazioni. Ciò vale per il tempo necessario per le operazioni del ciclo di lavorazione e la quantità richiesta per i componenti collegati ai numeri di operazione.
-   Categorie di costi per un'operazione del ciclo di lavorazione - Le informazioni delle risorse operative relative alle categorie di costi verranno ereditate dalle operazioni, nelle quali possono essere ignorate. Per i calcoli DBA verranno utilizzate le informazioni sulle categorie di costi specificate nelle operazioni del ciclo di lavorazione.

Nelle informazioni sui costi generali di produzione utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Supplemento: una formula di calcolo del supplemento riflette una percentuale del valore, ad esempio il 100%, collegato a un gruppo di costi specifico come la manodopera.
-   Tasso: una formula di calcolo del tasso riflette una tariffa per unità, ad esempio USD 10,00 l'ora, collegato a un gruppo di costi specifico come la manodopera.
-   Costi generali basati sul tempo e basati sul materiale: i costi generali di produzione possono essere collegati alle operazioni del ciclo di lavorazione o ai componenti materiale.

Nelle informazioni sulla versione di determinazione costi utilizzate in un calcolo DBA per i costi standard è incluso quanto segue:
-   Tipo di determinazione costi: nella versione di determinazione costi devono essere contenuti costi standard. Per i calcoli DBA in cui vengono utilizzati tali costi si applicano numerose restrizioni, ad esempio secondo le quali le spese varie devono essere incluse nei costi unitari e la modalità di esplosione deve essere a livello singolo.
-   Principio di fallback da definire - La versione di determinazione costi può imporre l'utilizzo di un principio di fallback, ad esempio l'utilizzo di una determinata versione di determinazione costi o dei record dei costi attivi. Il principio di fallback imposto si applica in genere a una versione di determinazione costi che rappresenta gli aggiornamenti incrementali in un approccio basato su due versioni per gli aggiornamenti dei costi.
-   Flag di blocco per i costi in sospeso: un flag di blocco può impedire l'esecuzione dei calcoli DBA del costo in sospeso per gli articoli prodotti.
-   Data di inizio specificata: la data di inizio specificata verrà utilizzata come data di calcolo predefinita per tutti i calcoli DBA che interessano la versione di determinazione costi.
-   Sito specificato: specificando un sito si limiteranno i calcoli DBA al sito in questione.
-   Costi da includere nel contenuto della versione di determinazione costi: nel contenuto devono essere inclusi i costi e facoltativamente i prezzi di vendita per calcolare i prezzi di vendita consigliati per gli articoli prodotti.

È possibile specificare diverse fonti di informazioni quando si avvia un calcolo DBA, tra cui il sito, la data di calcolo e la versione di determinazione costi.





