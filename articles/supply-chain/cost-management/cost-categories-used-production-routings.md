---
title: Categorie di costi utilizzate nei cicli di lavorazione
description: Questo articolo fornisce informazioni sulle categorie di costi applicate agli ambienti di produzione che utilizzano i cicli di lavorazione.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCategory, RouteCostCategoryPrice
audience: Application User
ms.reviewer: kamaybac
ms.custom: 78153
ms.assetid: a3fdc76c-0a27-4723-b1c7-4322f707d89e
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3f6204cfbdb56978f0b7611a38db8c23953ed83a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967712"
---
# <a name="cost-categories-used-in-production-routing"></a>Categorie di costi utilizzate nei cicli di lavorazione

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni sulle categorie di costi applicate agli ambienti di produzione che utilizzano i cicli di lavorazione.

Le categorie di costi si applicano agli ambienti di produzione in cui vengono utilizzati i cicli di lavorazione e vengono assegnate alle risorse operative e alle operazioni del ciclo di lavorazione per definire i costi orari e segmentare i contributi costi nei costi calcolati di un articolo prodotto. I gruppi di costi assegnati alle categorie di costi classificano i contributi costi di produzione in base alle risorse operative e al tipo di attività, ad esempio tempo di attrezzaggio ed esecuzione. La specificità delle assegnazioni dei gruppi di costi permette il calcolo dei costi generali di produzione secondo le informazioni del ciclo di lavorazione. 

**Nota:** negli ambienti di produzione, le categorie di costi sono note con diversi sinonimi, ad esempio codici tariffe manodopera o codici tariffe macchina. 

Ogni categoria di costi dispone di record dei costi associati e di un gruppo di costi assegnato. Sono necessarie categorie di costi diverse per scopi di produzione diversi.

-   Assegnare costi orari diversi, a seconda della risorsa operativa. Ad esempio, i costi possono differire per diversi tipi di competenze di manodopera, computer o celle di produzione.
-   Assegnare costi orari diversi per il tempo di attrezzaggio o di esecuzione associato a un'operazione del ciclo di lavorazione.
-   Assegnare i costi delle risorse operative in base alla quantità prodotta anziché ai costi orari, ad esempio le tariffe al pezzo per il pagamento della manodopera.
-   Fornire la segmentazione in base a gruppi di costi dei contributi costi al costo calcolato di un articolo prodotto. Ad esempio, è possibile segmentare i costi di manodopera e macchina.
-   Fornire la base dei gruppi di costi per le formule di calcolo dei costi generali, ad esempio le formule per i costi generali relativi alla manodopera e ai macchinari oppure ai tempi di attrezzaggio ed esecuzione.

Una categoria di costi può essere assegnata al tempo di attrezzaggio, al tempo di processo e alla quantità per un'operazione del ciclo di lavorazione. Quando ad esempio la segmentazione dei costi o dei gruppi di costi differisce tra il tempo di attrezzaggio e il tempo di processo, è necessario definire e assegnare le categorie di costi al tempo di attrezzaggio e di esecuzione. L'utilizzo selettivo delle categorie di costi per il tempo di attrezzaggio, il tempo di processo e la quantità è determinato dal gruppo di cicli di lavorazione assegnato a un'operazione. L'assegnazione delle categorie di costi a tempo e quantità può essere definita sulla base dei criteri a livello di società stabiliti nella pagina **Parametri di controllo produzione**. 

Ogni categoria di costi dispone di costi associati basati sulla definizione dei record dei costi in una versione di determinazione costi. Utilizzare la pagina **Prezzo categoria costi** per definire i record dei costi per una versione di determinazione costi e un sito specifici. Quando si immette per la prima volta il record di costo per una categoria di costi, ha uno stato **in sospeso** e una data di validità desiderata. Quando si attiva il record del costo, lo stato viene aggiornato a **Corrente attivo** e la data di validità viene aggiornata alla data di attivazione. Record dei costi diversi possono riflettere siti, date di validità o stati diversi. Nei calcoli della distinta base (DBA) per una data futura o dello storico verranno utilizzati i record dei costi con la data di validità rilevante. Il record di costo corrente attivo verrà utilizzato per la stima dei costi ordine di produzione e la valutazione del tempo rilevato a fronte di un ordine di produzione. 

Il record di costo per una categoria di costi può essere specifico del sito o a livello della società. Per rendere un record di costo specifico del sito, assegnare a esso un sito. Se invece non si imposta alcun sito, il record di costo verrà applicato a tutti i siti della società. Poiché i costi possono differire tra siti, ad esempio, i record dei costi devono essere definiti come specifici del sito. 

Un'operazione del ciclo di lavorazione in genere eredita le categorie di costi assegnate alla risorsa operativa o all'operazione principale. Quando si crea un ordine di produzione, le operazioni del ciclo di lavorazione all'interno del ciclo di lavorazione produzione riflettono la versione del ciclo selezionata. È possibile ignorare le categorie di costi assegnate alle operazioni nel ciclo di lavorazione produzione. 

Alcuni tipi di lavori di produzione possono essere utilizzati per le stime del tempo di progetto e per la relativa dichiarazione. In questo caso è necessaria una categoria di costi per gli scopi di produzione e progetto. È necessario definire ulteriori informazioni correlate al progetto quando una categoria di costi è contrassegnata per l'utilizzo nei progetti.



