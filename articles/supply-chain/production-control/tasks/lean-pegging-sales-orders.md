---
title: Pegging di produzione snella da ordini cliente
description: La procedura riguarda la convalida della struttura di pegging da una riga di vendita in cui l'articolo è prodotto con kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ff57169ea58a90d1113bb7ef0a581f900e62a9b2
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828564"
---
# <a name="lean-pegging-from-sales-orders"></a>Pegging di produzione snella da ordini cliente

[!include [banner](../../includes/banner.md)]

La procedura riguarda la convalida della struttura di pegging da una riga di vendita in cui l'articolo è prodotto con kanban. Dopo la convalida della struttura di pegging, tutti i processi kanban sono pianificati. Questa opzione è utile per scenari in cui l'incaricato dell'ordine cliente deve verificare che la produzione possa iniziare subito. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata per l'incaricato dell'ordine cliente avanzato che opera una società di produzione snella.


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a>Creare un ordine cliente per un articolo controllato da kanban
1. Fare clic su Tutti gli ordini cliente.
2. Fare clic su Nuovo.
3. Nel campo Conto cliente, immettere o selezionare un valore.
    * Utilizzare US-001.  
4. Fare clic su OK.
5. Nel campo Numero articolo digitare "L0001".
6. Impostare la quantità su "30".
    * È importante che la quantità sia superiore a 24 per attivare la regola kanban di evento.  

## <a name="open-a-pegging-tree"></a>Aprire una struttura di pegging 
1. Fare clic su Prodotto e fornitura.
2. Fare clic su Visualizza struttura di pegging.
    * Si noti che la struttura di pegging mostra tutti i livelli di pegging necessari per la riga ordine cliente. In questo caso, sono disponibili due livelli kanban e tutti i componenti richiesti.  

## <a name="plan-the-pegging-tree"></a>Pianificare la struttura di pegging
1. Nella struttura, selezionare 'Riga di vendita 000832\Kanban 000558'.
2. Espandere la sezione Processi kanban.
    * Si noti che lo stato del processo per il processo kanban è Non pianificato.  
3. Fare clic su Pianifica intera struttura di pegging.
    * In tal modo tutti i processi kanban vengono pianificati nella struttura di pegging, modificando lo stato del processo da Non pianificato a Pianificato.  
4. Aggiorna la pagina.
    * Si noti che lo stato del processo kanban è cambiato da Non pianificato a Pianificato.  
5. Nella struttura, selezionare 'Riga di vendita 000832\Kanban 000558\Uscita per L0001\Kanban 000559'.
    * Anche il processo per il secondo kanban viene pianificato perché l'intera struttura di pegging è pianificata. Si noti che lo stato del processo kanban è cambiato da Non pianificato a Pianificato.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]