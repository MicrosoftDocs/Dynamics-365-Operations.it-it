---
title: Definire celle di lavoro per lean manufacturing
description: Una cella di lavoro è un modulo specifico dei gruppi di risorse che possono essere utilizzati nelle attività del processo di produzione snella.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, InventLocationIdLookup, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f1144bd9f99fef44210c2a01f71a39488354ccf
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576786"
---
# <a name="define-lean-manufacturing-work-cells"></a>Definire celle di lavoro per lean manufacturing

[!include [banner](../../includes/banner.md)]

Una cella di lavoro è un modulo specifico dei gruppi di risorse che possono essere utilizzati nelle attività del processo di produzione snella. Le celle di lavoro hanno ubicazioni di entrata e di uscita e una definizione di capacità basata su un modello di flusso di produzione. Per ulteriori informazioni sui concetti di base delle celle di lavoro di lean manufacturing e sui calcoli di capacità, vedere i white paper sulla lean manufacturing. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-work-cell"></a>Creare una cella di lavoro. 
1. Andare ad Amministrazione organizzazione > Risorse > Gruppi di risorse.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Gruppo di risorse.
    * L'ID cella di lavoro è in genere un codice sistematico e deve essere univoco per la persona giuridica.  
4. Nel campo Descrizione digitare un valore.
    * La descrizione contiene il nome o il tipo della cella di lavoro.  
5. Nel campo Sito fare clic sul pulsante a discesa per aprire la ricerca.
    * Una cella di lavoro si trova in un sito specifico. Il magazzino e l'ubicazione di entrata e di uscita devono essere presenti in questo sito.  
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo Unità di produzione fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Selezionare un'unità di produzione a cui appartiene questa cella di lavoro.  
9. Selezionare la casella di controllo Cella di lavoro.
    * Per utilizzare un gruppo di risorse come cella di lavoro produzione snella, la casella di controllo Cella di lavoro deve essere selezionata.  Si noti che la proprietà non può essere modificata dopo che il gruppo di risorse viene creato.  
10. Nel campo Magazzino di input fare clic sul pulsante a discesa per aprire la ricerca.
11. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Per la contabilità e il controllo dei materiali, il materiale organizzato nello shop floor è in genere allocato a un magazzino virtuale specifico. Tuttavia, se si desidera rifornire le ubicazioni utilizzando il lavoro magazzino, queste devono far parte del magazzino di ricezione delle materie prime.  
12. Nel campo Ubicazione di input fare clic sul pulsante a discesa per aprire la ricerca.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Si noti che per un'attività di processo, l'ubicazione di entrata può essere sovrascritta in generale o per un prodotto o una variante di prodotto specifico definendo le attività di prelievo che vengono applicate all'attività di processo. Le ubicazioni di entrata di una cella di lavoro non possono essere controllate da targa.  
14. Nel campo Magazzino di output fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco trovare e selezionare il record desiderato.
    * In più righe di produzione o flussi di produzione attività, questo è spesso il magazzino di entrata della cella di lavoro successiva o il magazzino delle vendite o di transito in cui un prodotto viene in genere trasferito dopo il processo di produzione. Quando si modellano i processi di produzione snella, il trasporto è in genere scartato, come viene dichiarato il trasporto.  
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Nel campo Ubicazione di output fare clic sul pulsante a discesa per aprire la ricerca.
    * In un flusso di produzione con più attività di elaborazione si tratta spesso dell'ubicazione di entrata della cella di lavoro successiva.  
18. Nell'elenco trovare e selezionare il record desiderato.
19. Nell'elenco fare clic sul collegamento nella riga selezionata.
20. Espandere o comprimere la sezione Operazione.
    * Una categoria del tempo di esecuzione deve essere fornita per attivare il calcolo dei costi e l'elaborazione dei processi kanban di produzione snella.  
21. Nel campo Categoria tempo di esecuzione fare clic sul pulsante a discesa per aprire la ricerca.
22. Nell'elenco trovare e selezionare il record desiderato.
    * La categoria di costi per il tempo di esecuzione viene utilizzata nel calcolo dei costi standard e per la determinazione dei costi di tipo backflush.  
23. Nell'elenco fare clic sul collegamento nella riga selezionata.
24. Espandere o comprimere la sezione Calendari.
25. Scegliere Aggiungi.
26. Nel campo Calendario fare clic sul pulsante a discesa per aprire la ricerca.
27. Nell'elenco trovare e selezionare il record desiderato.
    * In genere le celle di lavoro di un sito specifico utilizzano lo stesso calendario dell'orario di lavoro. Se le celle di lavoro hanno diversi orari di lavoro, potrebbe essere necessario creare un calendario dell'orario di lavoro specifico per la cella di lavoro. Si noti che il calendario deve avere un orario di lavoro standard definito quando viene utilizzato per una cella di lavoro di produzione snella perché la definizione di capacità è in genere correlata all'orario di lavoro standard di un giorno lavorativo.  
28. Nell'elenco fare clic sul collegamento nella riga selezionata.
29. Espandere o comprimere la sezione Capacità cella di lavoro.
30. Scegliere Aggiungi.
31. Nel campo Modello di flusso di produzione fare clic sul pulsante a discesa per aprire la ricerca.
32. Nell'elenco trovare e selezionare il record desiderato.
    * Questa procedura richiede il tipo di modello di flusso di produzione Produttività, per visualizzare la definizione della capacità di produttività.  
33. Nell'elenco fare clic sul collegamento nella riga selezionata.
34. Selezionare un'opzione nel campo Periodo di capacità.
    * Le opzioni sono: Giorno lavorativo standard, la capacità è espressa dalla lunghezza del giorno lavorativo standard del calendario dell'orario di lavoro per la cella di lavoro. Per ciascun giorno, l'orario di lavoro effettivo è determinato dal calendario e la capacità disponibile effettiva viene calcolata in base a tale valore.   Settimana, per autorizzare una capacità settimanale. Non esiste alcuna rettifica effettuata dall'orario lavorativo effettivo.   Mese, per autorizzare una capacità mensile. Non esiste alcuna rettifica effettuata dalla capacità effettiva.   In genere, il giorno lavorativo standard viene utilizzato per i periodi giornalieri e la capacità settimanale viene utilizzata per i periodi di capacità settimanali.  
35. Nel campo Quantità di produttività media, immettere un numero.
    * Si noti che un'operazione di produzione snella non è mai impostata per la capacità massima possibile in un ambiente ideale. La capacità deve essere sempre definita per le operazioni in esecuzione in condizioni normali.  
36. Nel campo Unità fare clic sul pulsante a discesa per aprire la ricerca.
37. Nell'elenco fare clic sul collegamento nella riga selezionata.
38. ResolveChanges per l'unità.

## <a name="add-a-financial-dimension"></a>Aggiungere una dimensione finanziaria
1. Espandere o comprimere la sezione Dimensioni finanziarie.
    * Si noti che le dimensioni finanziarie definite nel flusso di produzione sostituiscono la dimensione finanziaria di una cella di lavoro specifica.    Le dimensioni finanziarie che è possibile selezionare dipendono dalla configurazione delle dimensioni finanziarie del sistema. I passaggi seguenti si riferiscono al set di dati dimostrativi della società USMF. Se si utilizzano dati diversi, i passaggi potrebbero non essere applicabili.  
2. Nel campo Centro di costo fare clic sul pulsante a discesa per aprire la ricerca.
3. Nell'elenco trovare e selezionare il record desiderato.
    * Le dimensioni da selezionare per le celle di lavoro di produzione snella dipendono dall'implementazione delle dimensioni finanziarie nel modello di contabilità per una persona giuridica specifica.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="save"></a>Salva
1. Fare clic su Salva.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]