---
title: Abilitare la stampa di etichette targa
description: In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite.
author: perlynne
ms.date: 07/19/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SysCorpNetPrinterList, WHSParameters, NumberSequenceTableListPage, NumberSequenceDetails, WHSDocumentRoutingLayout, WHSDocumentRouting, WHSRFMenuItem, WHSRFMenu, WHSWorkTemplateTable, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: fd79abfc1029c4e0ef41d0e9b0f33ff524f50e36b70cf4fa3ed50dcdc4cb7f03
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751674"
---
# <a name="enable-license-plate-label-printing"></a>Abilitare la stampa di etichette targa

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come abilitare la stampa automatica di un'etichetta Serial Shipping Container Code (SSCC) dopo il prelievo dell'ultimo articolo dall'inventario in un processo del lavoro di prelievo vendite. È possibile eseguire questa procedura nella società di dati dimostrativi USMF. Se tale procedura è stata eseguita utilizzando i propri dati, è necessario disporre di una sequenza numerica impostata per le targhe. È necessario impostare una stampante di etichette prima di iniziare questa attività. Fare clic su Amministrazione organizzazione > Impostazioni > Stampanti di rete. Nel riquadro azioni, fai clic su Opzioni, quindi sul pulsante del programma di installazione dell'agente di distribuzione Scarica documento. Eseguire il programma di installazione e assicurarsi di disporre di una stampante di rete operativa impostata su Attiva prima di continuare con la procedura.


## <a name="set-up-the-gs1-company-prefix"></a>Imposta il prefisso della società GS1
1. Andare **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Parametri di gestione magazzino**.
2. Nel campo **Prefisso società GS1** immettere i 7 numeri per il numero di società GS1.
3. Selezionare **Salva**.
4. Chiudere la pagina.

## <a name="setup-the-sscc-license-plate-number-sequence"></a>Imposta la sequenza del numero di identificazione SSCC
1. Andare a **Pannello di navigazione > Moduli > Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche**.
2. Selezionare un'opzione nel campo **Area**.
3. Selezionare un'opzione nel campo **Riferimento**.
4. Digitare un valore nel campo **Società**.
5. Espandere la sezione **Segmenti**.
6. Selezionare **Modifica**.
7. Nella tabella **Segmenti**, selezionare la prima riga.
8. Selezione **Rimuovi**.
9. Selezione **Rimuovi**.
10. Selezionare **Salva**.
11. Chiudere la pagina.

## <a name="create-the-document-route-layout"></a>Crea il layout di distribuzione dei documenti
1. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Layout distribuzione documenti**. Attiva il layout di SSCC.  
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **ID layout**.
4. Digitare un valore nel campo **Descrizione**
5. Selezionare **Inserisci al termine del testo**.
6. Selezionare **Salva**.
7. Chiudere la pagina.

## <a name="set-up-the-document-routing"></a>Imposta la distribuzione dei documenti
1. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Distribuzione documenti > Distribuzione documenti**.
2. Nel campo **Tipo ordine di lavoro** selezionare un'opzione.
3. Selezionare **Nuovo**.
4. Digitare un valore nel campo **Magazzino**.
5. Digitare un valore nel campo **Nome**.
6. Selezionare **Nuovo**.
7. Nel campo **ID layout**, immettere o selezionare un valore.
8. Nel campo **Nome** selezionare il nome della stampante che si desidera utilizzare.
9. Selezionare **Salva**.
10. Chiudere la pagina.

## <a name="create-mobile-device-menu"></a>Crea il menu del dispositivo mobile
1. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Voci di menu del dispositivo mobile**.
2. Selezionare **Nuovo**.
3. Digitare un valore nel campo **Nome voce di menu**.
4. Digitare un valore nel campo **Titolo**.
5. Selezionare un'opzione nel campo **Modalità**.
6. Selezionare **Sì** nel campo **Utilizza lavoro esistente**.
7. Selezionare **Sì** nel campo **Genera targa**.
8. Espandere la sezione **Classi di lavoro**.
9. Selezionare **Nuovo**.
10. Nel campo **ID classe lavoro**, digitare un valore.
11. Selezionare **Salva**.
12. Chiudere la pagina.
13. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazione > Dispositivo mobile > Menu del dispositivo mobile**.
14. Nella struttura selezionare la voce di menu creata prima.
15. Selezionare **Modifica**.
16. Selezionare la freccia per aggiungere la voce di menu al menu.
17. Selezionare **Salva**.
18. Chiudere la pagina.

## <a name="update-a-work-template"></a>Aggiorna un modello di lavoro
1. Andare a **Pannello di navigazione > Moduli > Gestione magazzino > Impostazioni > Lavoro > Modelli di lavoro**.
2. Selezionare **Modifica**.
3. Selezionare **Nuovo**.
4. Nel campo **Tipo di lavoro**, selezionare **Stampa**.
5. Nel campo **ID classe lavoro** immettere o selezionare un valore.
6. Selezionare **Sposta su**.
7. Selezionare **Salva**.
8. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]