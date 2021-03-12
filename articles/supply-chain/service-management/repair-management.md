---
title: Gestione delle riparazioni
description: Raggruppare i problemi sistematicamente per semplificare l'individuazione delle soluzioni di problemi analoghi avvenuti in passato.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAConditionTable, SMASymptomArea, SMADiagnosisArea, SMAResolutionTable, SMARepairStage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8ebb9833be5e51fe59e9895e67cd8e55058078aa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001350"
---
# <a name="repair-management"></a>Gestione delle riparazioni       

[!include [banner](../includes/banner.md)]


Per la gestione delle riparazioni è possibile raggruppare i problemi in modo sistematico. Ciò agevola l'individuazione di soluzioni rivelatesi utili in passato.

È necessario definire le impostazioni di sintomi, diagnosi e soluzioni. Queste potranno essere applicate in un secondo momento quando si riceve un articolo simile per la riparazione. È inoltre possibile impostare fasi di riparazione, allo scopo di seguire l'avanzamento della riparazione stessa.

## <a name="setting-up-repair-management"></a>Impostazione della gestione riparazione

Utilizzare i seguenti moduli di impostazione per immettere informazioni che verranno utilizzate per specificare i sintomi, la diagnosi e la soluzione per la riparazione.

1.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Condizioni**.

2.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Aree sintomo**.

3.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Aree diagnosi**.

4.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Soluzioni**.

5.  Fare clic su **Gestione assistenza** \> **Impostazione** \> **Riparazione** \> **Fasi riparazione**.

## <a name="symptoms-and-conditions"></a>Sintomi e condizioni

Per sintomi si intendono le caratteristiche del problema così come vengono indicate dal cliente. I sintomi comprendono anche le osservazioni del cliente che indicano la necessità della riparazione.

È possibile impostare aree sintomo, codici sintomo e condizioni. L'area sintomo riguarda l'area del malfunzionamento e il codice sintomo riguarda il sintomo del malfunzionamento. Le condizioni descrivono la situazione o ambiente in cui si è verificato il problema.

**Esempio**

Un computer viene inviato in riparazione a causa di un malfunzionamento del disco rigido che si verifica in seguito a lunghi periodi di utilizzo. L'errore del disco rigido causa la visualizzazione di una schermata blu. Il tecnico che riceve il computer immette i seguenti sintomi e condizioni:

1.  L'area sintomo è il disco rigido

2.  Il codice sintomo è la visualizzazione della schermata blu

3.  Le condizioni sono l'utilizzo prolungato che dà origine all'errore del disco rigido

## <a name="diagnosis-and-resolutions"></a>Diagnosi e soluzioni

I campi relativi alla diagnosi e alle soluzioni contengono descrizioni di carattere tecnico, ovvero i diversi passaggi attraverso i quali il tecnico ha individuato il problema.

L'area diagnostica riguarda l'operazione che deve essere effettuata per risolvere il problema. Il codice diagnostico indica come è stato gestito il problema, mentre la soluzione può indicare che l'articolo è stato riparato, sostituito o che l'ordine è stato annullato dal cliente. Se ad esempio il computer viene riparato, l'area diagnostica, il codice diagnostico e la soluzione potrebbero corrispondere rispettivamente a "componente difettoso", "nuova scheda video installata" e "sostituito".

## <a name="repair-stages"></a>Fasi di riparazione

Le fasi di riparazione indicano l'avanzamento del processo di riparazione. Ogni fase di riparazione dispone del parametro di approvazione **Completato**, che indica il completamento della riga di riparazione e nel quale vengono registrate la data e l'ora di completamento.

## <a name="applying-repair-management"></a>Applicazione della gestione delle riparazioni

Per applicare la gestione delle riparazioni a un articolo, quest'ultimo deve essere impostato con una relazione oggetto assistenza in un ordine di assistenza. Dall'ordine di assistenza è quindi possibile creare una riga di riparazione con le informazioni relative al problema. Nella riga di riparazione è necessario definire l'oggetto assistenza in riparazione e inserire le informazioni relative ai sintomi, alla diagnosi e all'esecuzione. È inoltre possibile creare una nota per la riga di riparazione.

È possibile creare righe di riparazione per ogni fase del processo di riparazione.

## <a name="create-a-repair-line-on-a-service-order"></a>Creazione di una riga di riparazione in un ordine di assistenza

1.  Fare clic su **Gestione assistenza** \> **Comune** \> **Ordini di assistenza** \> **Ordini di assistenza**.

2.  Selezionare l'ordine di assistenza con l'oggetto assistenza per il quale è necessaria una riparazione.

3.  Fare clic su **Riparazione** \> **Righe riparazione** per aprire il modulo **Righe riparazione**.

4.  Premere CTRL+N per creare una nuova riga.

5.  Selezionare un oggetto assistenza. È possibile selezionare qualsiasi oggetto assistenza impostato con una relazione oggetto nell'ordine di servizio.

6.  Selezionare i valori appropriati tra quelli predefiniti relativi a sintomi, diagnosi ed esecuzione per la riga di riparazione e, se necessario, fare clic sulla scheda **Nota** per creare una nota nella riga di riparazione.

7.  Premere CTRL+S per salvare la nuova riga di riparazione. Il campo **Data e ora creazione** nella scheda **Generale** del modulo **Righe riparazione** viene aggiornato con la data e l'ora del salvataggio.

## <a name="tracking-progress-and-resolving-a-repair-issue"></a>Stato di avanzamento e risoluzione di una riparazione

Per seguire l'avanzamento di una riparazione, è possibile impostare le relative fasi in modo da seguire l'avanzamento della riparazione stessa.

Quando una riparazione è risolta, è possibile chiudere la relativa riga di riparazione. Impostare la fase di riparazione su una fase con la proprietà **Completato** abilitata. La data e l'ora correnti vengono registrate nella riga come data e ora di conclusione.

## <a name="close-a-repair-line-for-a-resolved-issue"></a>Chiusura di una riga di riparazione per un problema risolto

1.  Apri il modulo **Righe riparazione**. Seguire la procedura di creazione di una riga di riparazione, descritta in precedenza in questo argomento.

2.  Selezionare la riga di riparazione contenente il problema che si desidera chiudere.

3.  Nel campo **Fase riparazione** selezionare una fase con la proprietà **Completato** attivata.

  


