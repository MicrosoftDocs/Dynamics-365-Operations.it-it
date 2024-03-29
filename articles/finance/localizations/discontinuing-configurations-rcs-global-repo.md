---
title: Sospendere le configurazioni nel repository RCS Global
description: In questo articolo viene descritto come sospendere le configurazioni nel repository RCS Global.
author: gionoder
ms.date: 02/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: gionoder
ms.search.validFrom: 2021-02-02
ms.dyn365.ops.version: AX 10.0.14
ms.custom: 97423
ms.assetid: ''
ms.search.form: ERSolutionTable, ERWorkspace
ms.openlocfilehash: b0605f56058e3c93ea088ee8386ba26c4ce2b65a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9272338"
---
# <a name="discontinue-configurations-in-the-rcs-global-repository"></a>Sospendere le configurazioni nel repository RCS Global

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come sospendere la configurazione nel repository RCS Global. In precedenza era possibile eliminare solo le configurazioni non più necessarie. Tuttavia ora è possibile contrassegnare una configurazione rilasciata come **Sospesa** nel repository RCS Global. Con questa funzionalità, è inoltre possibile effettuare quanto segue: 
 
 - Fornire notifiche anticipate quando si pianifica la sospensione di una configurazione.
 - Includere i dettagli applicabili sulla configurazione sostitutiva.
 - Impostare una data in **Supportata fino al** per la configurazione specifica per informare l'utente quando verrà sospesa.

Quando si sospende una versione di configurazione, è possibile specificare le seguenti informazioni facoltative:

  - **Configurazione della sostituzione**
  - **Versione della configurazione sostitutiva**
  - **Nota a testo libero**: utilizzare questo campo per fornire collegamenti o riferimenti alla documentazione
  - **Supportata fino al**: questo campo fornisce la data proposta fino alla quale la configurazione/versione corrente sarà supportata. Questa data deve essere aggiornata manualmente.
  
Per sospendere la configurazione, completare i seguenti passaggi. 

1. Selezionare se si desidera sospendere una singola versione o tutte le versioni con le stesse impostazioni in un'unica operazione impostando **Tutte le versioni** su **Sì**. 
2. Impostare il parametro **Sospendi** su **Sì**.
3. Selezionare **OK** per sospendere le configurazioni. Il campo **Data sospensione** verrà popolato quando si salvano le modifiche.

![Informazioni sulla sospensione della configurazione.](media/Discontinue-details-2.png)
  
È possibile reimpostare la configurazione su **Condivisa** o modificare le informazioni sulla sospensione in qualsiasi momento. Se si condivide una configurazione, specificare la data **Supportata fino al** e tutte le altre informazioni relative alla sospensione per indicare i piani di una futura sospensione.

Se si desidera condividere le informazioni su una sospensione pianificata, prima di sospendere effettivamente la configurazione, l'utente può precompilare tutti i campi relativi alla sostituzione ma lasciare il parametro **Sospendi** impostato su **No**.

> [!NOTE]
> La sospensione non limita le operazioni con le configurazioni. È possibile continuare a importare, eseguire o derivare le configurazioni; questi campi sono informativi.

## <a name="finance-supports-displaying-this-information-starting-in-version-10014"></a>Finance supporta la visualizzazione di queste informazioni a partire dalla versione 10.0.14

A partire dalla versione 10.0.14, Dynamics 365 Finance supporta la visualizzazione delle informazioni sulla sospensione. Nella pagina **Repository globale**, è possibile visualizzare informazioni aggiornate relative alla sospensione. Per impostazione predefinita, le configurazioni sospese vengono filtrate.
  
La pagina **Configurazioni importate** (ERSolutionTable) mostra le configurazioni che erano già state sospese quando sono state importate. Per queste configurazioni che erano state sospese dopo l'importazione, le informazioni sulla sospensione possono essere sincronizzate eseguendo il processo **Importare aggiornamenti delle configurazioni**.


