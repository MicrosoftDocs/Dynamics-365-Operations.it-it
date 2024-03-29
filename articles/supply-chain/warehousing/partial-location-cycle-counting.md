---
title: Conteggio ciclo ubicazioni parziale
description: I piani di conteggio ciclo definiscono le operazioni di conteggio effettivo. È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.
author: perlynne
ms.date: 09/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSCycleCountPlan, WHSWorkLineCycleCount, WHSWorkTemplateLineGroup, WHSWorkTemplateTable, WHSRFMenuItemCycleCount, WHSCycleCountPlanListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f06b39f3c2d2f5a0bdfef1da9395c71686ed46968a1143305b5a10787f7e85f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778436"
---
# <a name="partial-location-cycle-counting"></a>Conteggio ciclo ubicazioni parziale

[!include [banner](../includes/banner.md)]

I piani di conteggio ciclo definiscono le operazioni di conteggio effettivo. È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione.

Utilizzando i piani di conteggio ciclo per creare il lavoro di conteggio, è possibile definire le operazioni di conteggio effettivo. È possibile fare in modo che solo prodotti specifici e varianti di prodotto vengano conteggiati anziché tutte le scorte disponibili in un'ubicazione. Filtrando per prodotti specifici, il responsabile del magazzino può ridurre i costi generali di revisione, evitare errori di consolidamento e risparmiare tempo.

## <a name="how-to-configure-partial-location-cycle-counting"></a>Istruzioni per configurare il conteggio ciclo dell'ubicazione

Quando si utilizza il processo di lavoro di magazzino per le operazioni di conteggio, un'intestazione di lavoro viene creata per ogni ubicazione. Quando si definisce il piano di conteggio ciclo, è possibile utilizzare la query **Seleziona ubicazioni** per limitare il lavoro di conteggio ciclo creato. Quando si selezionano i prodotti per il piano di conteggio ciclo, è possibile selezionare le query per il prodotto e le varianti di prodotto per perfezionare il conteggio.

È possibile associare un **modello di lavoro** a un piano di conteggio ciclo per definire in che modo il lavoro di conteggio ciclo deve essere creato. Il modello di lavoro per le operazioni di conteggio è un riferimento diretto per il piano di conteggio ciclo.

Quando si definiscono i dettagli del modello di lavoro, è possibile utilizzare l'opzione **Interruzioni riga lavoro** per specificare se le righe del lavoro di conteggio devono essere raggruppate in base al numero di articolo o al numero di variante prodotto. Questa impostazione è necessaria se si desidera conteggiare le scorte disponibili solo per i prodotti specifici di un'ubicazione. Le righe del lavoro di conteggio ciclo create avranno il livello di informazioni definito qui e l'operazione di conteggio guidata verrà gestita in base a tale livello.

Se si associano i piani di conteggio ciclo ai modelli di lavoro mediante l'opzione **Interruzioni riga lavoro**, il campo **Conteggio ciclo parziale** viene selezionato per il lavoro di conteggio ciclo creato e più righe del lavoro di conteggio ciclo verranno create in base alla definizione del modello di lavoro.

Prima che il lavoro di conteggio ciclo parziale possa essere elaborato, è necessario, come minimo, selezionare **Visualizza numero articolo** per la voce di menu del dispositivo mobile come parte della configurazione del conteggio ciclo. All'operatore di magazzino verrà chiesto di registrare solo le informazioni di conteggio correlate alle righe di conteggio (numeri articolo e dimensioni prodotto). Tutte le altre scorte disponibili verranno ignorate in questo processo di conteggio.

Per il processo di conteggio parziale dei cicli, la data/ora **Ultimo conteggio ciclo** non viene aggiornata per la posizione, anche se vengono conteggiati tutti gli articoli disponibili in una determinata posizione. Il conteggio parziale dei cicli non considera il parametro **Giorni tra conteggio ciclo** della pagina **Piani di conteggio ciclo**. Il conteggio del ciclo parziale non supporta il conteggio simultaneo di più articoli nella stessa posizione. La funzionalità di conteggio del ciclo parziale può comportare il conteggio della stessa posizione più volte per un articolo quando **Elabora piano di conteggio ciclo** è eseguito. Per evitare questo scenario, specificare i filtri nel campo **Seleziona ubicazioni**.

> [!NOTE]
> L'app per dispositivi mobili Gestione magazzino non fornisce il pulsante **Aggiungi targa o articolo** quando si utilizza il processo di conteggio parziale ciclo.

## <a name="example"></a>Esempio

Per questo esempio, solo il numero di articolo A0001 deve essere conteggiato nel magazzino 61.

1. Viene creato un nuovo modello di lavoro per il conteggio ciclo. L'opzione **Interruzioni riga lavoro** viene utilizzata per raggruppare le righe del lavoro di conteggio per numero di articolo. Di conseguenza, il lavoro di conteggio ciclo creato avrà righe per numero di articolo. È inoltre possibile raggruppare le righe per numero di varianti prodotto.
1. Viene creato un nuovo piano di conteggio ciclo che fa riferimento al modello di lavoro appena creato. Il piano di conteggio ciclo include tutte le ubicazioni nel magazzino 61 (query **Seleziona ubicazioni** ) che dispongono di scorte per il numero di articolo A0001. La selezione di prodotti specifici viene definita nella sezione **Selezioni del prodotto del piano di conteggio ciclo**.
1. È possibile selezionare i prodotti per i piani di conteggio ciclo impostando il campo **Ubicazioni vuote** su **Escludi ubicazioni vuote**. Quando il piano di conteggio ciclo viene elaborato, viene creato il lavoro di conteggio ciclo parziale per il numero di articolo A0001. Il processo di conteggio effettivo può essere eseguito mediante una voce di menu del dispositivo mobile per il conteggio ciclo guidato.

## <a name="additional-resources"></a>Risorse aggiuntive

[Conteggio ciclo](cycle-counting.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]