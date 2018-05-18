--- 
title: "Calcolare l'ammortamento del cespite tra più persone giuridiche"
description: In questa procedura viene illustrato come impostare ed eseguire il processo di ammortamento per molteplici persone giuridiche.
author: saraschi2
manager: AnnBe
ms.date: 11/02/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: d804480167414cd038f8229db312dc9c52d131f8
ms.openlocfilehash: 4c45da124136b7fecb916d2ff9098c8ffeff6cb1
ms.contentlocale: it-it
ms.lasthandoff: 11/02/2017

---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcolare l'ammortamento del cespite tra più persone giuridiche

[!include [task guide banner](../../includes/task-guide-banner.md)]

L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio. In questa procedura viene illustrato come impostare ed eseguire il processo per molteplici persone giuridiche. Viene utilizzato il ruolo Ragioniere.  

Questa registrazione utilizza la società dimostrativa USMF.


Sottoattività in 16 passaggi: impostare i giornali di registrazione per l'esecuzione dell'ammortamento interaziendale. 

1. Innanzitutto, è necessario impostare i giornali di registrazione da utilizzare nell'esecuzione dell'ammortamento interaziendale in ogni persona giuridica. Passare a Cespiti > Impostazione > Parametri cespiti. 
2. Espandere l'area Proposte di cespite. 
3. Creare un record con il nome del giornale di registrazione da utilizzare per ciascun livello di registrazione nella persona giuridica. Se i registri non vengono registrati nella contabilità generale, il livello di registrazione Nessuno deve essere selezionato con il giornale di registrazione associato. Scegliere Aggiungi. 
4. Nel campo Livello registrazione, immettere o selezionare un valore. 
5. Nel campo Nome giornale di registrazione immettere o selezionare un valore. 
6. Ripetere l'impostazione del giornale di registrazione nella pagina Parametri Cespiti in ogni persona giuridica. 

Sottoattività: calcolare l'ammortamento

1. Utilizzare la pagina Crea proposta di ammortamento per iniziare l'esecuzione dell'ammortamento tra le persone giuridiche. Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento. 
2. Nel campo Livello registrazione, immettere o selezionare un valore. 
3. Per impostazione predefinita, il nome del giornale di registrazione è quello indicato in Parametri Cespiti. Può essere modificato qui per la persona giuridica corrente. 
4. Nel campo Data finale immettere una data. 
5. Selezionare le persone giuridiche da includere nell'esecuzione dell'ammortamento. Solo le persone giuridiche con giornali di registrazione impostati per le proposte cespite nella pagina Parametri Cespiti verranno visualizzate nell'elenco. 
6. Quando attivata, l'opzione Registra giornali registrerà automaticamente i giornali di registrazione ammortamento quando vengono creati. Se non è selezionata, i giornali di registrazione verranno creati, ma non registrati, di modo che sia possibile esaminare i dettagli prima della registrazione. Selezionare Sì nel campo Registra giornali. 
7. I campi di filtro includono cespiti, gruppi e registri per le persone giuridiche selezionate per questa esecuzione dell'ammortamento. 
8. L'opzione Elaborazione batch è attivata per impostazione predefinita. Quando questa opzione è attivata, la creazione e la registrazione del giornale di registrazione ammortamento vengono eseguite in background. 
9. Fare clic su Crea giornale di registrazione. 
10. È necessario visualizzare i giornali di registrazione ammortamento creati nelle rispettive persone giuridiche. Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.

