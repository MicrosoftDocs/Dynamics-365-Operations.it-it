---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 09/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: ffd7a4c01810578b4abb6942aeff76e5147fafa9
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173041"
---
# <a name="switch-between-vendor-designs"></a>Passa tra strutture fornitore

[!include [banner](../../includes/banner.md)]



## <a name="vendor-data-flow"></a>Flusso di dati fornitore 

Se si sceglie di utilizzare l'entità **Conto** per memorizzare i fornitori di tipo **Organizzazione** e l'entità **Contatto** per memorizzare i fornitori di tipo **Persona**, configurare i seguenti flussi di lavoro. In caso contrario, questa configurazione non è richiesta.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utilizzare il progetto del fornitore esteso per i fornitori di tipo Organizzazione

Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro. Verrà creato un flusso di lavoro per ogni modello.

+ Creare fornitori nell'entità Conto
+ Creare fornitori nell'entità fornitori
+ Aggiornare fornitori nell'entità Conto
+ Aggiornare fornitori nell'entità fornitori

Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.

1. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nell'entità conto**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.

    ![Creare fornitori nel processo flusso di lavoro entità conto](media/create_process.png)

2. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nell'entità conto**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**.
3. Creare un nuovo processo del flusso di lavoro per l'entità **Conto** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nell'entità fornitore**.
4. Creare un nuovo processo del flusso di lavoro per l'entità **Conto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nell'entità fornitore**.
5. È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti. Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.

    ![Pulsante Converti in flusso di lavoro in background](media/background_workflow.png)

6. Attivare i flussi di lavoro creati sulle entità **Conto** e **Fornitore** per iniziare a utilizzare l'entità **Conto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Organizzazione**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utilizzare il progetto del fornitore esteso per i fornitori di tipo Persona

Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro. Verrà creato un flusso di lavoro per ogni modello.

+ Creare fornitori di tipo Persona nell'entità fornitori
+ Creare fornitori di tipo Persona nell'entità contatti
+ Aggiornare fornitori di tipo Persona nell'entità contatti
+ Aggiornare fornitori di tipo Persona nell'entità fornitori

Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.

1. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori di tipo Persona nell'entità contatti**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Contatto**.
2. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nell'entità contatti**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Contatto**.
3. Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello **Creare fornitori di tipo Persona nell'entità fornitore**.
4. Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nell'entità fornitore**.
5. È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti. Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.
6. Attivare i flussi di lavoro creati sulle entità **Contatto** e **Fornitore** per iniziare a utilizzare l'entità **Contatto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Persona**.
