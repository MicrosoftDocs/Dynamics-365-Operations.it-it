---
title: Passa tra strutture fornitore
description: In questo argomento viene descritto come passare tra l'integrazione dei dati dei fornitori tra le app Finance and Operations e Dataverse.
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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-09-20
ms.openlocfilehash: 731efd3ae841960f3a2c0b9be210c5c68ac835f5
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685511"
---
# <a name="switch-between-vendor-designs"></a>Passa tra strutture fornitore

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



## <a name="vendor-data-flow"></a>Flusso di dati fornitore 

Se si sceglie di utilizzare l'entità **Conto** per memorizzare i fornitori di tipo **Organizzazione** e l'entità **Contatto** per memorizzare i fornitori di tipo **Persona**, configurare i seguenti flussi di lavoro. In caso contrario, questa configurazione non è richiesta.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-organization-type"></a>Utilizzare il progetto del fornitore esteso per i fornitori di tipo Organizzazione

Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro. Verrà creato un flusso di lavoro per ogni modello.

+ Creare fornitori nella tabella Conto
+ Creare fornitori nella tabella Fornitori
+ Aggiornare fornitori nella tabella Conto
+ Aggiornare fornitori nella tabella Fornitori

Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.

1. Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nella tabella conto**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Conto**.

    ![Creare fornitori nel processo flusso di lavoro tabella conto](media/create_process.png)

2. Creare un nuovo processo del flusso di lavoro per la tabella **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nella tabella conto**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Conto**.
3. Creare un nuovo processo del flusso di lavoro per la tabella **Conto** e selezionare il modello di processo del flusso di lavoro **Creare fornitori nella tabella fornitori**.
4. Creare un nuovo processo del flusso di lavoro per la tabella **Conto** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori nella tabella fornitori**.
5. È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti. Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.

    ![Pulsante Converti in flusso di lavoro in background](media/background_workflow.png)

6. Attivare i flussi di lavoro creati sulle tabelle **Conto** e **Fornitore** per iniziare a utilizzare l'entità **Conto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Organizzazione**.

## <a name="use-the-extended-vendor-design-for-vendors-of-the-person-type"></a>Utilizzare il progetto del fornitore esteso per i fornitori di tipo Persona

Il pacchetto di soluzione **Dynamics365FinanceExtended** contiene i seguenti modelli di processo del flusso di lavoro. Verrà creato un flusso di lavoro per ogni modello.

+ Creare fornitori di tipo Persona nella tabella fornitori
+ Creare fornitori di tipo Persona nella tabella Contatti
+ Aggiornare fornitori di tipo Persona nella tabella Contatti
+ Aggiornare fornitori di tipo Persona nella tabella fornitori

Per creare nuovi processi del flusso di lavoro utilizzando i modelli del processo del flusso di lavoro, seguire la seguente procedura.

1. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Creare fornitori di tipo Persona nella tabella contatti**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di creazione del fornitore per l'entità **Contatto**.
2. Creare un nuovo processo del flusso di lavoro per l'entità **Fornitore** e selezionare il modello di processo del flusso di lavoro **Aggiornare fornitori di tipo Persona nella tabella contatti**. Selezionare **OK**. Questo flusso di lavoro gestisce lo scenario di aggiornamento del fornitore per l'entità **Contatto**.
3. Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello **Creare fornitori di tipo Persona nella tabella fornitore**.
4. Creare un nuovo processo del flusso di lavoro per l'entità **Contatto** e selezionare il modello **Aggiornare fornitori di tipo Persona nella tabella fornitore**.
5. È possibile configurare i flussi di lavoro come flussi di lavoro in tempo reale o in background, in base ai requisiti. Per configurare un flusso di lavoro come flusso di lavoro in background, selezionare **Converti in flusso di lavoro in background**.
6. Attivare i flussi di lavoro creati sulle entità **Contatto** e **Fornitore** per iniziare a utilizzare le tabelle **Contatto** di Customer Engagement per archiviare le informazioni sui fornitori di tipo **Persona**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]