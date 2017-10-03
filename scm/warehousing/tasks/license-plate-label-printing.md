--- 
title: Abilitare la stampa di etichette targa
description: Questa procedura consente la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.
author: perlynne
manager: AnnBe
ms.date: 11/03/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: c4ca3cd02a43692cfa9510847b460a318855fd24
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="enable-license-plate-label-printing"></a>Abilitare la stampa di etichette targa

[!include[task guide banner](../../includes/task-guide-banner.md)]

Questa procedura consente la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite. È possibile eseguire questa procedura nella società di dati dimostrativi USMF. Se tale procedura è stata eseguita utilizzando i propri dati, è necessario disporre di una sequenza numerica impostata per le targhe. È necessario impostare una stampante di etichette prima di iniziare questa attività. Fare clic su Amministrazione organizzazione > Impostazioni > Stampanti di rete. Nel riquadro azioni fare clic su Opzioni, quindi sul pulsante Scarica programma di installazione agente di distribuzione documenti. Eseguire il programma di installazione e assicurarsi di disporre di una stampante di rete operativa impostata su Attiva prima di continuare con la procedura.


## <a name="set-up-the-gs1-company-prefix"></a>Imposta il prefisso della società GS1
1. Andare a Gestione magazzino > Impostazioni > Parametri di gestione magazzino.
2. Nel campo Prefisso società GS1 immettere i 7 numeri per il numero di società GS1.
3. Fare clic su Salva.
4. Chiudere la pagina.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Imposta la sequenza del numero di identificazione SSCC
1. Andare a Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche.
2. Selezionare un'opzione nel campo Area.
3. Selezionare un'opzione nel campo Riferimento.
4. Digitare un valore nel campo Società.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Espandere la sezione Segmenti.
8. Fare clic su Modifica.
9. Nella tabella Segmenti, selezionare la prima riga
10. Fare clic su Rimuovi.
11. Fare clic su Rimuovi.
12. Fare clic su Salva.
13. Chiudere la pagina.

## <a name="create-the-document-route-layout"></a>Crea il layout di distribuzione dei documenti
1. Andare a Gestione magazzino > Impostazioni > Distribuzione documenti > Layout distribuzione documenti.
    * Attiva il layout di SSCC.  
2. Fare clic su Nuovo.
3. Digitare un valore nel campo ID layout.
4. Nel campo Descrizione digitare un valore.
5. Nell'elenco trovare e selezionare il record desiderato.
6. Fare clic su Inserisci al termine del testo.
7. Fare clic su Salva.
8. Chiudere la pagina.

## <a name="set-up-the-document-routing"></a>Imposta la distribuzione dei documenti
1. Andare a Gestione magazzino > Impostazioni > Distribuzione documenti > Distribuzione documenti.
2. Nel campo Tipo ordine di lavoro selezionare un'opzione.
3. Fare clic su Nuovo.
4. Digitare un valore nel campo Magazzino.
5. Digitare un valore nel campo Nome.
6. Fare clic su Nuovo.
7. Nel campo ID layout, immettere o selezionare un valore.
8. Nel campo Nome selezionare il nome della stampante che si desidera utilizzare.
9. Fare clic su Salva.
10. Chiudere la pagina.

## <a name="create-mobile-device-menu"></a>Crea il menu del dispositivo mobile
1. Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Voci di menu del dispositivo mobile.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome voce di menu.
4. Digitare un valore nel campo Titolo.
5. Selezionare un'opzione nel campo Modalità.
6. Selezionare Sì nel campo Utilizza lavoro esistente.
7. Selezionare Sì nel campo Genera targa.
8. Espandere la sezione Classi di lavoro.
9. Fare clic su Nuovo.
10. Nel campo ID classe, digitare un valore.
11. Fare clic su Salva.
12. Chiudere la pagina.
13. Andare a Gestione magazzino > Impostazioni > Dispositivo mobile > Menu del dispositivo mobile.
14. Nell'elenco trovare e selezionare il record desiderato.
15. Nella struttura selezionare "Nella struttura selezionare la voce di menu creata prima".
16. Fare clic su Modifica.
17. Fare clic sulla freccia per aggiungere la voce di menu al menu.
18. Fare clic su Salva.
19. Chiudere la pagina.

## <a name="update-a-work-template"></a>Aggiorna un modello di lavoro
1. Andare a Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro.
2. Nell'elenco trovare e selezionare il record desiderato.
3. Fare clic su Modifica.
4. Fare clic su Nuovo.
5. Nell'elenco contrassegnare la riga selezionata.
6. Nel campo Tipo di lavoro, selezionare 'Stampa'.
7. Nel campo ID classe lavoro immettere o selezionare un valore.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su Sposta su.
10. Fare clic su Salva.
11. Chiudere la pagina.


