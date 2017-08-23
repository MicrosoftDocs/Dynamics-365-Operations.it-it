--- 
title: Impostazione guidata sequenze numeriche
description: Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono.
author: sericks007
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
ms.author: sericks
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 5fe6e54b4ebcf6cd611af54e7066a3e39d0e677d
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-number-sequences-by-using-a-wizard"></a>Impostazione guidata sequenze numeriche

[!include[task guide banner](../../includes/task-guide-banner.md)]

Le sequenze numeriche vengono utilizzate per generare identificatori univoci e leggibili per record anagrafica e record transazioni che li richiedono. Un record transazioni o dati master che richiede un identificatore viene definito riferimento. Prima di poter creare nuovi record per un riferimento, è necessario impostare una sequenza numerica e associarla al riferimento. In questa procedura verrà illustrato come impostare contemporaneamente tutte le sequenze numeriche richieste utilizzando la procedura guidata. La società di dati dimostrativi utilizzata per creare questa procedura è USMF.

1. Andare a Amministrazione organizzazione > Sequenze numeriche > Sequenze numeriche.
2. Fare clic su Genera.
3. Scegliere Avanti.
    * Da questa pagina è possibile modificare il codice identificativo, il valore minimo e il valore massimo. Inoltre, è possibile Indicare se la sequenza numerica deve essere continua.   
    * Non selezionare l'opzione Continua se si devono preallocare numeri per la sequenza numerica.     Per aggiungere un segmento ambito al formato di una sequenza numerica, selezionare il formato nell'elenco, quindi fare clic su Includi ambito nel formato.     Per eliminare un segmento ambito dal formato di una sequenza numerica, selezionare il formato nell'elenco, quindi fare clic su Rimuovi ambito dal formato.     Per escludere una sequenza numerica dalla generazione automatica, selezionare la sequenza numerica nell'elenco, quindi fare clic su Elimina.  
4. Scegliere Avanti.
5. Scegliere Fine.


