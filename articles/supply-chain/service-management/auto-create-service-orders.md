---
title: Creare ordini di assistenza automaticamente
description: È possibile generare ordini di assistenza in base a un contratto di assistenza per il periodo di validità del contratto stesso.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 33de4746b8011f4e7fc0ce2929c967870eeebae9
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3203022"
---
# <a name="automatically-create-service-orders"></a>Creare ordini di assistenza automaticamente 

[!include [banner](../includes/banner.md)]


È possibile generare ordini di assistenza in base a un contratto di assistenza per il periodo di validità del contratto stesso.

Tutti gli ordini di assistenza generati a partire da un contratto di assistenza sono collegati a tale contratto.

Gli ordini di assistenza vengono generati automaticamente in base alle seguenti impostazioni:

  - Impostazione dell'intervallo del contratto di assistenza nelle righe del contratto. L'intervallo del contratto di assistenza indica la frequenza con la quale vengono create le righe dell'ordine di assistenza. Per ulteriori informazioni, consultare [Intervalli assistenza](service-intervals.md).

  - Il periodo specificato per definire il periodo di assistenza nei campi **Dal** e **Al** del modulo **Crea ordini di assistenza**. Per ulteriori informazioni, vedere [Creare ordini di assistenza automaticamente](create-service-orders-automatically.md).

  - L'opzione **Combina ordini di assistenza** nell'intestazione del contratto di assistenza. Questa opzione indica se verranno generate righe di ordine di assistenza da un contratto di assistenza e consente di combinare gli ordini di assistenza in base al dipendente, all'attività di assistenza tecnica, all'oggetto assistenza o al contratto di assistenza. Per ulteriori informazioni, vedere [Combina ordini di assistenza](combine-service-orders.md).

  - L'opzione **Intervallo di tempo** nella riga del contratto di assistenza. L'intervallo di tempo definisce il periodo entro il quale una riga dell'ordine di assistenza può essere spostata in relazione alla relativa data calcolata. Per ulteriori informazioni, vedere [Intervalli di tempo](time-windows.md)..


> [!NOTE]
> <P>Se nel calendario selezionato nel modulo <STRONG>Parametri di gestione assistenza</STRONG> il giorno specificato per un ordine di assistenza non è aperto, verrà visualizzato un messaggio per segnalare che si è verificato un conflitto tra calendari. È possibile ignorare il messaggio senza conseguenze. L'ordine di assistenza verrà creato anche se nel calendario il giorno è chiuso.</P>

## <a name="example-1"></a>Esempio 1

La durata del contratto di assistenza è compresa tra il 1 gennaio 2012 e il 31 dicembre 2012. Se il periodo di assistenza specificato nel modulo **Crea ordini di assistenza** è compreso tra il 1 novembre 2012 e il 1 febbraio 2013, gli ordini di assistenza verranno creati dal 1 novembre 2012 al 31 dicembre 2012.

## <a name="example-2"></a>Esempio 2

La durata del contratto di assistenza è compresa tra il 1 gennaio 2012 e il 31 dicembre 2012. Al contratto di assistenza sono collegate due righe. Per la prima riga del contratto di assistenza la data di inizio è il 2 gennaio 2010 e la data di fine è il 1 marzo 2012. Per la seconda riga la data di inizio è il 1 aprile 2012 e la data di fine è il 31 dicembre 2012. Nel modulo **Crea ordini di assistenza** si specifica un periodo compreso tra il 1 ottobre 2012 e il 31 dicembre 2012. Gli ordini di assistenza vengono pertanto creati solo per la seconda riga del contratto di assistenza, poiché la data di inizio e di fine della prima riga sono anteriori al periodo specificato per l'ordine di assistenza.

  


