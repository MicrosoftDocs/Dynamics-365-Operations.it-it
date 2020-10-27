---
title: Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico
description: Questa argomento illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7966c6e445e0e44cd4ff8518926aa6b410502e13
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980437"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a>Pianificare i carichi e le spedizioni utilizzando il workbench di pianificazione del carico

[!include [banner](../../includes/banner.md)]

Questa argomento illustra come utilizzare il workbench di pianificazione del carico per creare un carico per un ordine cliente. Come prerequisito, è necessario creare prima l'ordine cliente. Questa procedura è parte delle attività giornaliere per il coordinatore dei trasporti. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.


## <a name="create-a-sales-order"></a>Crea un ordine cliente
1. Passare al **pannello di navigazione > Moduli > Contabilità clienti > Ordini > Tutti gli ordini cliente**.
2. Selezionare **Nuovo**.
3. Nel campo **Conto cliente** selezionare il pulsante a discesa per aprire la ricerca.
4. Selezionare il conto **US-004**.
5. Selezionare **OK**.
6. Nel campo **Numero articolo** fare clic sul pulsante a discesa per aprire la ricerca.
7. Selezionare articolo: **A0001**. **A0001** è abilitato per la gestione trasporto.  
8. Nel campo **Sito** fare clic sul pulsante a discesa per aprire la ricerca, quindi selezionare un articolo.
9. Nel campo **Quantità** immettere un numero.
10. Nel campo **Magazzino**, immettere '24' per questo esempio. Tale magazzino è abilitato per la gestione trasporto e la gestione avanzata del magazzino.  
11. Selezionare **Salva**.
12. Chiudere la pagina.

## <a name="create-a-new-load"></a>Creare un nuovo carico
1. Andare a **Pannello di navigazione > Moduli > Gestione trasporto > Pianificazione > Workbench pianificazione carico**.
2. Selezionare la scheda **Righe di vendita**. Verrà creato il carico per l'ordine cliente creato. I carichi possono essere creati in base all'offerta e alla domanda da ordini fornitore, ordini di trasferimento e ordini cliente.  
3. Nel riquadro azioni fare clic su **Domanda e offerta**.
4. Selezionare **Al nuovo carico**.
5. Nel campo **ID modello carico** fare clic sul pulsante a discesa per aprire la ricerca. Il modello di carico definisce le misure massime per il peso e il volume dell'intero carico. Ad esempio, il modello di carico può rappresentare la dimensione di un container o di un camion. Selezionare un articolo.
6. Selezionare **OK**.

## <a name="rate-and-route-the-load"></a>Assegnare una tariffa e un percorso al carico
1. Selezionare **Valutazione e distribuzione**.
2. Selezionare **Tariffa workbench ciclo di lavorazione**.
3. Selezionare **Strumento tariffe**.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Selezionare **Assegna**.
6. Chiudere la pagina.

