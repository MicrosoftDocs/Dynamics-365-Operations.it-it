--- 
title: Impostare le firme elettroniche
description: Utilizzare questa procedure per configurare le firme elettroniche.
author: maertenm
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: maertenm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 43ac3aecd9290e496fc8dd237c0d09b60638f442
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-electronic-signatures"></a>Impostare le firme elettroniche

[!include[task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedure per configurare le firme elettroniche. Una firma elettronica consente di confermare l'identità di una persona che sta per avviare o approvare un processo di elaborazione. La società di dati dimostrativi utilizzata per creare questa procedura è DAT.


## <a name="enable-the-electronic-signature-configuration-key"></a>Attivare la chiave di configurazione Firma elettronica (SysSign)
1. Andare ad Amministrazione sistema > Impostazioni > Configurazione licenza.
2. Nella struttura espandere "Amministrazione".
    * Verificare che la casella di controllo Firma elettronica sia selezionata.  
    * Se la casella di controllo della firma elettronica non è selezionata, è necessario attivare la modalità manutenzione. È possibile attivare la modalità manutenzione in questo ambiente eseguendo un processo di manutenzione da LCS oppure utilizzando lo strumento Deployment.Setup in locale.  
3. Chiudere la pagina.

## <a name="set-up-electronic-signature-parameters"></a>Impostare i parametri di firma elettronica
1. Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Parametri firma elettronica.
2. Fare clic su Modifica.
3. Digitare un valore nel campo Preavviso.
    * Immettere il testo dell'avviso che verrà inviato ai firmatari quando è richiesta una firma. È possibile immettere qualsiasi testo. Nel testo sono di solito indicate le implicazioni correlate alla firma elettronica di un documento.  
    * Fare clic sul pulsante Traduzioni per immettere il testo dell'avviso in altre lingue.  
4. Fare clic su Salva.
5. Chiudere la pagina.

## <a name="set-up-reason-codes-for-electronic-signatures"></a>Impostare i codici motivo per le firme elettroniche
1. Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Codici motivo firma elettronica.
2. Fare clic su Nuovo.
    * È necessario impostare i codici motivo prima di utilizzare le firme elettroniche. Per la firma di un documento è richiesto un codice motivo valido.     I codici motivo vengono selezionati dai firmatari per indicare lo scopo di una firma elettronica. È ad esempio possibile utilizzare un codice motivo per indicare un'approvazione legale.  
3. Digitare un valore nel campo Codice motivo.
4. Nel campo Descrizione digitare un valore.
    * Immettere i codici motivo aggiuntivi, se necessario.  
5. Fare clic su Salva.
6. Chiudere la pagina.

## <a name="require-electronic-signatures-for-existing-processes"></a>Richiedere le firme elettroniche per un processo esistente
1. Andare ad Amministrazione organizzazione > Impostazioni > Firma elettronica > Requisiti firma elettronica.
2. Nell'elenco trovare e selezionare il record desiderato.
    * Scegliere un processo per il quale sono richieste le firme elettroniche.  
3. Selezionare o deselezionare la casella di controllo Firma richiesta.
    * Ripetere questi passaggi per ogni processo che richiede le firme elettroniche.  
4. Fare clic su Salva.

## <a name="create-a-custom-requirement-for-electronic-signatures"></a>Creare un requisito personalizzato per le firme elettroniche
1. Fare clic su Nuovo.
2. Selezionare o deselezionare la casella di controllo Firma richiesta.
3. Nel campo Nome immettere un nome per il processo che richiede le firme elettroniche.
4. Nel campo Nome tabella fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare la tabella in cui devono essere archiviati i dati da firmare.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.
7. Nel campo Nome campo fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco trovare e selezionare il campo della tabella che si desidera monitorare.
9. Nell'elenco fare clic sul collegamento nella riga selezionata.
    * Specificare le situazioni in cui è necessaria una firma.     Selezionare Sempre se è necessaria una firma ogni volta che i dati nel campo cambiano.     Selezionare Solo se la firma è necessaria solo a certe condizioni. Se si seleziona Solo, è necessario selezionare anche una delle seguenti opzioni: Inserimento di un record, Aggiornamento di un record o Eliminazione di un record.  
10. Fare clic su Salva.
11. Chiudere la pagina.


