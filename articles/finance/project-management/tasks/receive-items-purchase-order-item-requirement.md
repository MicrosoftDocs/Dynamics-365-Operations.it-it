---
title: Ricevere articoli in un ordine fornitore da una richiesta articolo
description: In questo argomento viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.
author: KimANelson
manager: AnnBe
ms.date: 08/06/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjProjectsListPage, ProjTable, ProjSalesItemReq, InventItemIdLookupSimple, PurchCreateFromSalesOrder, VendAccountItemLookup, PurchTable, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1f288a47f952a30d98a4a5b96409dc53f880d41d
ms.sourcegitcommit: b92c3e1b3403d0455fc4e0bf9132d6bc0d7aba5e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/18/2020
ms.locfileid: "3139061"
---
# <a name="receive-items-on-purchase-order-from-item-requirement"></a>Ricevere articoli in un ordine fornitore da una richiesta articolo

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come ricevere gli articoli in un ordine fornitore da una richiesta articolo.

Le richieste articoli consentono, rispetto alle transazioni articolo, di pianificare la consegna per il momento immediatamente precedente l'utilizzo effettivo dell'articolo, di creare un ordine fornitore, di includere l'articolo all'interno di un accordo commerciale e di includere la richiesta articolo nella pianificazione della produzione. 

Questa attività utilizza il set di dati dimostrativi USSI.

1. Nel pannello di navigazione, andare a **Moduli > Gestione progetti e contabilità > Progetti > Tutti i progetti**.
2. Nell'elenco fare clic sul collegamento nella riga desiderata.
3. Nel Riquadro azioni selezionare **Pianifica**.
4. Selezionare **Richieste articoli**.
5. Selezionare **Nuovo**.
6. Nella nuova riga, immettere o selezionare un valore nel campo **Numero articolo**.
7. Nel campo **Quantità** immettere un numero.
8. Selezionare **Salva**.
9. Nel riquadro azioni, fare clic su **Gestisci**.
10. Selezionare **Funzioni**.
11. Selezionare **Crea ordine fornitore**.
12. Selezionare la casella di controllo **Includi tutto**.
13. Nel campo **Conto fornitore**, immettere o selezionare un valore.
14. Selezionare **OK**.
15. Nel pannello di navigazione, andare a **Moduli > Contabilità fornitori > Ordini fornitore > Tutti gli ordini fornitore**.
16. Nell'elenco fare clic sul collegamento nella riga desiderata.
17. Nel riquadro azioni fare clic su **Acquisto**.
18. Selezionare **Conferma**.
19. Nel riquadro azioni fare clic su **Ricevimento**.
20. Selezionare **Entrata prodotti**.
21. Nel campo **Entrata prodotti**, digitare un valore.
22. Selezionare **OK**.

