--- 
title: "Creare un prodotto rilasciato per una singola società"
description: "Questa procedura descrive come creare un unico prodotto rilasciato nel contesto di un'unica unità legale."
author: ShylaThompson
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResProductCreate, UnitOfMeasureLookup, DimensionLookup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 042eafc29e377e0ad6fb8dc1499daf8eb105b7ed
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-released-product-for-a-single-company"></a>Creare un prodotto rilasciato per una singola società

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura descrive come creare un unico prodotto rilasciato nel contesto di un'unica unità legale. Dopo la creazione, il prodotto rilasciato viene immediatamente reso disponibile solo in questa unità. È possibile eseguire questa procedura nella società di dati dimostrativi USMF. Questa attività viene in genere eseguita da un responsabile di design prodotto.


## <a name="create-a-released-product"></a>Creare un prodotto rilasciato
1. Fare clic su Prodotti rilasciati.
2. Fare clic su Nuovo.
3. Nel campo Numero prodotto, digitare un valore.
    * Se un numero prodotto non è immesso automaticamente nel campo relativo al numero prodotto, immettere un numero prodotto univoco. Questo passaggio è obbligatorio solo se nessuna sequenza numerica è stata impostata per i numeri prodotto.  
4. Digitare un valore nel campo Nome prodotto.
    * Il nome prodotto è impostato come valore predefinito sul nome di ricerca. Se necessario, è possibile scegliere di modificare il nome di ricerca.  
5. Nel campo Gruppo di modelli di articoli fare clic sul pulsante a discesa per aprire la ricerca.
    * I gruppi di modelli articolo contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita. Le impostazioni determinano anche la modalità di calcolo del consumo di articoli.  
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.
    * I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi basati sulle relative caratteristiche. Ad esempio, per gestire la modalità con cui le informazioni vengono registrate nei conti principali, è possibile creare una serie di gruppi di articoli diversi associati a conti principali specifici. In questo modo è possibile tenere traccia del valore di inventario degli articoli nelle diverse fasi.  
9. Nell'elenco trovare e selezionare il record desiderato.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Nel campo Gruppo di dimensioni di immagazzinamento fare clic sul pulsante a discesa per aprire la ricerca.
    * Le dimensioni di immagazzinamento consentono di controllare il modo in cui gli articoli vengono immagazzinati e prelevati dal magazzino. Ad esempio, una dimensione di immagazzinamento può essere il sito e il magazzino.  
12. Nell'elenco trovare e selezionare il record desiderato.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.
14. Nel campo Gruppo di dimensioni di tracciabilità fare clic sul pulsante a discesa per aprire la ricerca.
    * Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è possibile aggiungere a un prodotto. Ad esempio, numero batch e numero di serie vengono utilizzati per tenere traccia degli articoli di magazzino.  
15. Nell'elenco trovare e selezionare il record desiderato.
16. Nell'elenco fare clic sul collegamento nella riga selezionata.
17. Nel campo Unità di magazzino fare clic sul pulsante a discesa per aprire la ricerca.
    * L'unità di magazzino determina la modalità in cui il prodotto viene quantificato quando è archiviato in magazzino.  
18. Nell'elenco trovare e selezionare il record desiderato.
19. Nell'elenco fare clic sul collegamento nella riga selezionata.
20. Nel campo Unità di acquisto fare clic sul pulsante a discesa per aprire la ricerca.
    * L'unità di acquisto determina la modalità in cui prodotto viene quantificato quando viene acquistato da un fornitore.  
21. Nell'elenco trovare e selezionare il record desiderato.
22. Nell'elenco fare clic sul collegamento nella riga selezionata.
23. Nel campo Unità di vendita fare clic sul pulsante a discesa per aprire la ricerca.
    * L'unità di vendita determina la modalità in cui il prodotto viene quantificato quando è venduto a un cliente.  
24. Nell'elenco trovare e selezionare il record desiderato.
25. Nell'elenco fare clic sul collegamento nella riga selezionata.
26. Nel campo Unità DBA fare clic sul pulsante a discesa per aprire la ricerca.
    * L'unità DBA determina la modalità in cui il prodotto viene quantificato quando viene incluso in una distinta base (BOM).  
27. Nell'elenco trovare e selezionare il record desiderato.
28. Nell'elenco fare clic sul collegamento nella riga selezionata.
29. Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.
    * La fascia IVA articoli nel gruppo di commissioni di vendita determina come viene calcolata l'IVA per ogni articolo.  
30. Nell'elenco trovare e selezionare il record desiderato.
31. Nell'elenco fare clic sul collegamento nella riga selezionata.
32. Nel campo Fascia IVA fare clic sul pulsante a discesa per aprire la ricerca.
    * La fascia IVA articoli nel gruppo di commissioni di acquisto determina come viene calcolata la tassa sull'acquisto per ogni articolo.  
33. Nell'elenco trovare e selezionare il record desiderato.
34. Nell'elenco fare clic sul collegamento nella riga selezionata.
35. Fare clic su OK.

## <a name="add-product-characteristics"></a>Aggiungere le caratteristiche del prodotto
1. Espandere o comprimere la sezione Gestione articoli.
2. Immettere un numero nel campo Peso netto.
3. Immettere un numero nel campo Tara.
4. Nel campo Profondità lorda immettere un numero.
5. Nel campo Larghezza lorda immettere un numero.
6. Nel campo Altezza lorda immettere un numero.
7. Nel campo Volume immettere un numero.

## <a name="add-financial-dimensions"></a>Aggiungere dimensioni finanziarie
1. Espandere o comprimere la sezione Dimensioni finanziarie.
2. Nel campo Business Unit fare clic sul pulsante a discesa per aprire la ricerca.
3. Trovare e selezionare il record desiderato nell'elenco.
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Nel campo Centro di costo fare clic sul pulsante a discesa per aprire la ricerca.
6. Trovare e selezionare il record desiderato nell'elenco.
7. Nell'elenco fare clic sul collegamento nella riga selezionata.
8. Nel campo Reparto fare clic sul pulsante a discesa per aprire la ricerca.
9. Trovare e selezionare il record desiderato nell'elenco.
10. Nell'elenco fare clic sul collegamento nella riga selezionata.
11. Nel campo Gruppo di articoli fare clic sul pulsante a discesa per aprire la ricerca.
12. Trovare e selezionare il record desiderato nell'elenco.
13. Nell'elenco fare clic sul collegamento nella riga selezionata.


