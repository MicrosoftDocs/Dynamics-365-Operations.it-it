---
title: 'Definire il conteggio ciclo '
description: Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/12/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSRFMenuItemCycleCount, WHSCycleCountThreshold, WHSCycleCountPlan, WHSCycleCountPlanListPage, WHSParameters, WHSRFMenu, WHSRFMenuItem
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1424bc4c4ff0f8528d6577e80324082cb2ec7f4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977165"
---
# <a name="define-cycle-counting"></a>Definire il conteggio ciclo  

[!include [banner](../../includes/banner.md)]

Il conteggio ciclo è un processo di magazzino che è possibile utilizzare per controllare gli articoli di magazzino disponibili. Questa registrazione attività mostra come impostare la priorità predefinita di lavoro di conteggio, abilitare una voce di menu dispositivo mobile per elaborare sia le operazioni di prelievo che di conteggio, abilitare un attivatore di soglia di conteggio quando un'ubicazione diventa vuota e abilitare un piano di conteggio ciclo per un articolo specifico all'interno di un magazzino specifico. Queste attività vengono in genere svolte da un responsabile di magazzino. È possibile eseguire questa procedura nella società di dati dimostrativi USMF oppure con dati propri.


## <a name="set-the-priority-of-counting-work"></a>Definire la priorità del lavoro di conteggio
1. Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.
2. Fare clic sulla scheda **Conteggio ciclo**.
3. Nel campo **Priorità lavoro conteggio ciclo predefinita** immettere un numero. Questo passaggio cambia la priorità di conteggio ciclo rispetto ad altri tipi di lavoro nel magazzino. Se si inserisce un numero inferiore a quello di altri tipi di lavoro, la priorità di lavoro di conteggio ciclo aumenta.  
4. Fare clic su **Salva**.
5. Chiudere la pagina.

## <a name="enable-the-mobile-device"></a>Abilitare il dispositivo mobile
1. Nel **pannello di navigazione**, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.
2. Fare clic su **Nuovo**.
3. Digitare un valore nel campo **Nome voce di menu**.
4. Digitare un valore nel campo **Titolo**.
5. Selezionare "Lavoro" nel campo **Modalità**.
6. Impostare l'opzione **Utilizza lavoro esistente** su Sì. Quando questa opzione viene impostata su Sì, il sistema cercherà il lavoro esistente quando viene utilizzata la voce di menu dispositivo mobile.  
7. Nel campo **Diretto da** selezionare "Diretto dal sistema". Quando è selezionata l'opzione "Diretto dal sistema", il lavoratore del magazzino verrà indirizzato al lavoro aperto nelle classi di lavoro definite. Tali classi verranno create in seguito.  
8. Espandere la sezione **Classi di lavoro**. In seguito verranno create ora due classi di lavoro da utilizzare con la voce di menu dispositivo mobile. Quando la voce di menu viene utilizzata, verrà eseguita una ricerca in queste classi di lavoro e il lavoro con la priorità più alta verrà visualizzato all'utente.  
9. Fare clic su **Nuovo**.
10. Nel campo **ID classe lavoro** selezionare un valore.
11. Fare clic su **Nuovo**.
12. Nel campo **ID classe lavoro** selezionare un valore.
13. Nel **Riquadro azioni** fai clic su **Salva**.
14. Chiudere la pagina.
15. Nel **pannello di navigazione**, andare a **Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.
16. Nell'elenco trovare e selezionare il record desiderato.
17. Nella struttura selezionare la voce di menu appena creata.
18. Fare clic su **Modifica**.
19. Fare clic sulla freccia per aggiungere la voce al menu.
20. Fare clic su **Salva**.

## <a name="create-a-counting-threshold"></a>Creare una soglia di conteggio
1. Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Conteggio ciclo > Soglie conteggio ciclo**.
2. Fare clic su **Nuovo**.
3. Nel campo **ID soglia conteggio ciclo** immettere un valore.
4. Impostare l'opzione **Elabora immediatamente conteggio ciclo** su Sì.
5. Digitare un valore nel campo **Descrizione**
6. Fare clic su **Salva**.
7. Fare clic su **Seleziona ubicazioni**.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo **Criteri** selezionare un valore.
10. Fare clic su **OK**.
11. Chiudere la pagina.

## <a name="create-a-cycle-count-plan"></a>Creare un piano di conteggio ciclo
1. Nel **pannello di navigazione** andare a **Moduli > Gestione magazzino > Impostazioni > Conteggio ciclo > Piani di conteggio ciclo**.
2. Fare clic su **Nuovo**.
3. Nel campo **ID piano di conteggio ciclo** immettere un valore.
4. Digitare un valore nel campo **Descrizione**
5. Nel campo **Numero massimo di conteggi ciclo** immettere un numero.
6. Fare clic su **Salva**.
7. Fare clic su **Seleziona ubicazioni**.
8. Nell'elenco contrassegnare la riga selezionata.
9. Nel campo **Criteri** selezionare un valore.
10. Fare clic su **OK**.
11. Nel campo **Giorni tra conteggio ciclo** immettere un numero. Ad esempio, se il valore specificato nel campo **Giorni tra conteggio ciclo** è impostato su 5, il lavoro del conteggio ciclo verrà creato ogni cinque giorni. Tuttavia, se il lavoro di conteggio ciclo viene elaborato il terzo giorno, il lavoro di conteggio ciclo successivo verrà creato cinque giorni dopo l'elaborazione dell'ultimo conteggio ciclo, ovvero l'ottavo giorno.  
12. Fare clic su **Salva**.
13. Fare clic su **Nuovo**.
14. Immettere un numero nel campo **Numero progressivo**. L'ordinamento è crescente. Il valore deve essere maggiore di 0 (zero).  
15. Nell'elenco contrassegnare la riga selezionata.
16. Digitare un valore nel campo **Descrizione**
17. Fare clic su **Salva**.
18. Fare clic su **Definisci query prodotto**.
19. Nell'elenco contrassegnare la riga selezionata.
20. Nel campo **Criteri** immettere o selezionare un valore.
21. Fare clic su **OK**.
22. Chiudere la pagina.

