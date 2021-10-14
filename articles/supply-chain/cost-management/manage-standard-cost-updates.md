---
title: Gestire gli aggiornamenti di costo standard
description: "Gli aggiornamenti dei dati di costo standard possono essere gestiti utilizzando due metodi diversi: il metodo basato su un'unica versione oppure il metodo basato su due versioni."
author: AndersGirke
ms.date: 01/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CostingVersion, InventItemPrice, InventParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: 69992
ms.assetid: 468de7af-c7b5-4345-bd5a-ba3aa5a900cc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 942b144c78176e9a00cdc12101e2948e8aa4685e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579762"
---
# <a name="manage-standard-cost-updates"></a>Gestire gli aggiornamenti di costo standard

[!include [banner](../includes/banner.md)]

Gli aggiornamenti dei dati di costo standard possono essere gestiti utilizzando due metodi diversi: il metodo basato su un'unica versione oppure il metodo basato su due versioni.

Il metodo a una versione utilizza un'unica versione di determinazione costi contenente tutti i record costi. Questi record includono i costi originali e tutti gli aggiornamenti costi.

Il metodo basato su due versioni utilizza una versione contenente i record dei costi originali e una seconda versione contenente i record di tutti gli aggiornamenti costi. L'approccio basato su due versioni offre come vantaggio principale la possibilità di delineare in modo chiaro e di tenere traccia degli aggiornamenti dei costi in una versione di determinazione costi separata, senza modificare la versione di determinazione costi originale. Il concetto di un approccio basato su due versioni può essere utilizzato per identificare più aggiornamenti incrementali, in cui ciascun aggiornamento incrementale è associato a una versione di determinazione costi separata contenente i record dei costi incrementali.

## <a name="example"></a>Esempio

Nell'esempio seguente viene illustrato come i metodi basati su una o due versioni possono essere utilizzati per aggiornare i costi standard in un ambiente di produzione, ad esempio, per aggiornamenti che riflettono i nuovi articoli o correzioni di errori. Si supponga che una singola versione di determinazione costi rappresenti i costi standard per l'anno in corso. L'identificatore per questa versione è 2020-STD. La versione 2020-STD contiene i costi attivi correnti per tutti gli articoli. In questa versione sono inoltre contenuti i costi attivi correnti di tutti gli articoli, tutte le categorie di costi correlate ai cicli di lavorazione e le formule di calcolo dei costi generali noti all'inizio del 2020. 2020-STD è la versione di determinazione costi originale.

- **Approccio basato su una sola versione per gli aggiornamenti dei dati relativi ai costi**: con l'approccio basato su una sola versione, nella versione di determinazione costi 2020-STD saranno contenuti tutti i record dei costi. Gli aggiornamenti di costo vengono registrati in 2020-STD e il relativo stato è impostato su In sospeso. I costi in sospeso possono essere immessi manualmente per nuovi articoli acquistati, oppure possono essere calcolati per un articolo prodotto in modo da riflettere le correzioni. Per i calcoli DBA con l'approccio basato su una sola versione non è richiesta un'origine dati di fallback, poiché tutti i costi attivi sono contenuti nella versione di determinazione costi. Dopo l'attivazione dei costi in sospeso, nella versione di determinazione costi originale 2020-STD saranno di nuovo contenuti tutti i costi attivi correnti.
- **Approccio basato su due versioni per gli aggiornamenti dei dati relativi ai costi**: per l'approccio basato su due versioni è richiesta un'ulteriore versione di determinazione costi in cui saranno contenuti solo gli aggiornamenti costi. L'identificatore per questa versione è 2020-STD-CHANGES. Gli aggiornamenti di costo vengono registrati in 2020-STD e il relativo stato è impostato su In sospeso. Con l'approccio basato su due versioni, per i calcoli DBA dei costi in sospeso per gli articoli prodotti è richiesta un'origine dati di fallback, poiché nella versione di determinazione costi aggiuntiva di 2020-STD-CHANGES è contenuto solo un sottoinsieme di dati relativi ai costi. Il fallback può essere espresso come costi attivi o come la versione di determinazione costi 2020-STD, poiché entrambi identificano l'origine dei dati relativi ai costi non presenti in 2020-STD-CHANGES. Dopo l'attivazione dei costi in sospeso, nella versione di determinazione costi aggiuntiva 2020-STD-CHANGES saranno contenuti i costi attivi correnti che riflettono gli aggiornamenti, mentre la versione di determinazione costi originale 2020-STD resterà invariata. Utilizzando l'approccio basato su due versioni, è necessario impostare criteri di bloccaggio per la versione di determinazione costi originale al fine di impedirne l'aggiornamento. Per la versione di determinazione costi aggiuntiva devono essere impostati esattamente gli stessi criteri di bloccaggio impiegati per la versione di determinazione costi originale, ad eccezione della data di inizio specificata e dell'utilizzo selettivo dei criteri di bloccaggio per consentire gli aggiornamenti. La data di inizio specificata deve essere aggiornata con ciascun batch di modifiche in modo da riflettere la data di attivazione programmata.

Nell'esempio è stata utilizzata una versione di determinazione costi aggiuntiva per la gestione degli aggiornamenti durante l'anno 2020. È possibile utilizzare più versioni di determinazione costi aggiuntive, ad esempio una per ciascun batch di aggiornamenti. Quando si utilizza più di una determinazione costi aggiuntiva, il fallback deve essere espresso come costi attivi, poiché questi vengono distribuiti su più versioni di determinazione costi.

## <a name="financial-dimensions-for-the-standard-cost-revaluation"></a>Dimensioni finanziarie per la rivalutazione dei costi standard

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

L'attivazione di un nuovo prezzo standard rivaluterà in genere il valore delle scorte disponibili mediante transazioni di rivalutazione dei costi standard. Di solito, le dimensioni finanziarie dell'articolo vengono quindi registrate nelle transazioni. Tuttavia, se si desidera controllare se e come vengono registrate le dimensioni finanziarie, utilizzare la [gestione delle funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per attivare la funzionalità denominata *Opzioni di dimensioni finanziarie predefinite per la rivalutazione del costo standard dell'inventario*. Dopo aver abilitato questa funzionalità, vai a **Gestione costi> Impostazione criteri contabili inventario > Parametri** e imposta il nuovo elenco a discesa **Origine della dimensione finanziaria** con uno dei seguenti valori:

- **Nessuno**: nelle transazioni di rivalutazione non viene registrata alcuna dimensione finanziaria. Se nella struttura dei conti è presente una dimensione finanziaria obbligatoria, il processo di rivalutazione viene comunque eseguito e crea le voci contabili prive di dimensioni finanziarie. In questo caso, gli utenti riceveranno prima un messaggio di avviso, in modo che possano annullare la rivalutazione se necessario.
- **Tabella**: le dimensioni finanziarie dell'articolo vengono registrate nelle transazioni di rivalutazione. Questa è l'impostazione predefinita ed è coerente con il comportamento del sistema originale senza attivare la funzionalità *Opzioni di dimensioni finanziarie predefinite per la rivalutazione del costo standard dell'inventario*.
- **Registrazioni**: nelle transazioni di rivalutazione vengono registrate le dimensioni finanziarie della transazione da rivalutare. Per impostazione predefinita, le dimensioni finanziarie del conto inventario della transazione originale verranno utilizzate sia per il conto inventario che per il conto di rivalutazione.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]