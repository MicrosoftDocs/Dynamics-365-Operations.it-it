---
title: Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata
description: Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.
author: ShylaThompson
manager: AnnBe
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventTableInventoryDimensionGroups, InventItemOrderSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f93f3db022b7b338bfa18ff6aea79f8086ea997f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3147941"
---
# <a name="complete-basic-setup-of-a-released-product-master"></a>Completare l'impostazione di base di una rappresentazione generale prodotto rilasciata

[!include [banner](../../includes/banner.md)]

Questo argomento procedura mostra come completare la configurazione minima necessaria prima che la rappresentazione generale prodotto possa essere utilizzata nelle versioni DBA.

Questa è la terza procedura di otto che illustra come sviluppare le combinazioni per la configurazione basata su dimensioni. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Prodotti rilasciati**.
2. Nell'elenco trovare e selezionare il record desiderato. Selezionare la rappresentazione generale prodotto che è stata rilasciata nella seconda procedura. La rappresentazione generale prodotto viene creata con la tecnologia di configurazione basata su dimensioni.  
3. Nel riquadro azioni fare clic su **Prodotto**.
4. Fare clic su **Gruppi di dimensioni** per aprire la finestra di dialogo a discesa.
5. Nel campo **Gruppo di dimensioni di immagazzinamento** selezionare il pulsante a discesa per aprire la ricerca.
6. Nell'elenco trovare e selezionare il record desiderato. Il gruppo dimensione di immagazzinamento determina quali dimensioni di immagazzinamento vengono utilizzate per la transazione del prodotto. Selezionare **Sito** per questa procedura.  
7. Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca.
8. Nell'elenco trovare e selezionare il record desiderato. Il gruppo dimensione di tracciabilità determina quali dimensioni di tracciabilità vengono utilizzate per la transazione del prodotto. Selezionare **Nessuna** per questa procedura.  
9. Fare clic su **OK**.
10. Fare clic su **Modifica**.
11. Nel campo **Gruppo di modelli di articoli** fare clic sul pulsante a discesa per aprire la ricerca.
12. Nell'elenco trovare e selezionare il record desiderato. I gruppi di modelli di articoli contengono impostazioni che determinano la modalità in cui gli articoli vengono controllati e gestiti all'entrata e all'uscita. Determinano inoltre in che modo viene calcolato il consumo di articoli. Selezionare **FIFO** per questa procedura.  
13. Espandere la sezione **Gestisci costi**.
14. Nel campo **Gruppo di articoli** fare clic sul pulsante a discesa per aprire la ricerca.
15. Nell'elenco trovare e selezionare il record desiderato. I gruppi di articoli vengono utilizzati per la gestione delle scorte mediante la divisione degli articoli di magazzino in gruppi. Selezionare **CarAudio** per questa procedura.  
16. Nel Riquadro azioni selezionare **Pianifica**.
17. Selezionare **Impostazioni ordine predefinite**.
18. Nel campo **Tipo di ordine predefinito** selezionare un'opzione. Selezionare **Produzione** per specificare che l'opzione di rifornimento predefinita per la rappresentazione generale prodotto è di produrla.  
19. Selezionare **Salva**.
20. Chiudere la pagina.
21. Chiudere il modulo **Dettagli prodotto rilasciato**.

