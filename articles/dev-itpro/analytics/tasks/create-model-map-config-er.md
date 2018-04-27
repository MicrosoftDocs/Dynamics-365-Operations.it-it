--- 
title: Crea una nuova configurazione del mapping di modello (ER)
description: Utilizzare questa procedura per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 74606b1378e94e8a6945a408520c8b68648970d8
ms.openlocfilehash: f7206126bfa6150078f1bfb4f7e07c1cf2819ce0
ms.contentlocale: it-it
ms.lasthandoff: 02/07/2018

---
# <a name="create-a-model-mapping-configuration-er"></a>Crea una nuova configurazione del mapping di modello (ER)

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Utilizzare questa procedura per progettare una nuova configurazione di mapping di modello (ER) per la creazione di report elettronici e usare le funzioni ER incorporate per i calcoli aggregati efficienti. In questa procedura verrà creata una configurazione per la società di esempio Litware, Inc. 

Questa procedura viene creata per utenti con il ruolo di amministratore di sistema o di sviluppatore di report elettronici.

Tali passaggi possono essere completati mediante un set di dati. Per completare questi passaggi, è necessario completare i passaggi della procedura "Creare un provider di configurazione e contrassegnarlo come attivo".

1. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
    * Verificare che il provider di configurazione per la società di esempio Litware, Inc. sia disponibile e contrassegnato come attivo. Se il provider di configurazione non è visualizzato, è necessario innanzitutto completare i passaggi della procedura "Creazione di report elettronici: creare e attivare un provider di configurazione".  
2. Fare clic su Configurazioni report.
3. Fare clic su Mostra filtri.
4. Immettere il valore di filtro "Intrastat" nel campo "Nome" e utilizzare l'operatore di filtro "inizia con".
    * Applicare questo filtro per individuare la configurazione del modello dati "Intrastat". Questo modello potrebbe essere già presente nella struttura di configurazioni. In tal caso, ignorare la sottoattività successiva.   

## <a name="get-the-intrastat-model-configuration-provided-by-microsoft"></a>Ottenere la configurazione di modello Intrastat fornita da Microsoft
1. Chiudere la pagina.
2. Chiudere la pagina.
3. Andare ad Amministrazione organizzazione > Aree di lavoro > Creazione di report elettronici.
4. Nell'elenco trovare e selezionare il record desiderato.
    * Selezionare il riquadro Provider Microsoft.  
5. Fare clic su Archivi.
    * Fare clic su Archivi nel riquadro Provider Microsoft.  
6. Fare clic su Mostra filtri.
7. Immettere il valore di filtro "risorse" nel campo "Nome del tipo" e utilizzare l'operatore di filtro "contiene". 
8. Fare clic su Apri.
9. Nella struttura selezionare "Modello Intrastat".
10. Fare clic su Importa.
11. Fare clic su Sì.
    * È stata importata la configurazione del modello ER contenente il modello dati che verrà utilizzato per esplorare come le nuove funzionalità ER possono essere utilizzate.  
12. Chiudere la pagina.
13. Chiudere la pagina.
14. Fare clic su Configurazioni report.

## <a name="add-a-new-model-mapping-configuration"></a>Aggiungere una nuova configurazione del mapping di modello
1. Nella struttura selezionare "Modello Intrastat".
2. Fare clic su Crea configurazione per aprire la finestra di dialogo a discesa .
3. Nel campo Nuovo immettere 'Mapping di modello basato sul modello dati Intrastat'.
4. Nel campo Nome digitare "Mapping di esempio Intrastat".
    * Mapping di esempio Intrastat  
5. Fare clic su Crea configurazione.


