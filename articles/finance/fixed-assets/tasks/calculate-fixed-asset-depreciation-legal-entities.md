---
title: Calcolare l'ammortamento del cespite tra più persone giuridiche
description: L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 074a1b80584050302920a95c20fb547523a4866c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4444641"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Calcolare l'ammortamento del cespite tra più persone giuridiche

[!include [banner](../../includes/banner.md)]

L'ammortamento del cespite può essere eseguito tra persone giuridiche in un unico passaggio. In questa procedura viene illustrato come impostare ed eseguire il processo per molteplici persone giuridiche. Utilizza il ruolo Ragioniere e i dati dimostrativi della persona giuridica USMF.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Impostare i giornali di registrazione per l'esecuzione dell'ammortamento interaziendale
1. Passare a Cespiti > Impostazione > Parametri cespiti.
2. Espandere l'area Proposte di cespite.
3. Scegliere Aggiungi.
4. Nel campo Livello registrazione, immettere o selezionare un valore.
5. Nel campo Nome giornale di registrazione immettere o selezionare un valore.
    * Ripetere l'impostazione del giornale di registrazione nella pagina Parametri Cespiti in ogni persona giuridica.  

## <a name="depreciation-run"></a>Esecuzione ammortamento
1. Andare a Cespiti > Scritture contabili > Crea proposta di ammortamento.
2. Nel campo Livello registrazione, immettere o selezionare un valore.
    * Per impostazione predefinita, il nome del giornale di registrazione è quello indicato in Parametri Cespiti. Può essere modificato qui per la persona giuridica corrente.  
3. Nel campo Data finale immettere una data.
    * Selezionare le persone giuridiche da includere nell'esecuzione dell'ammortamento.  
    * Solo le persone giuridiche con giornali di registrazione impostati per le proposte cespite nella pagina Parametri Cespiti verranno visualizzate nell'elenco.  
4. Selezionare Sì nel campo Registra giornali.
    * I campi di filtro includono cespiti, gruppi e registri per le persone giuridiche selezionate per questa esecuzione dell'ammortamento.  
    * L'opzione Elaborazione batch è attivata per impostazione predefinita. Quando questa opzione è attivata, la creazione e la registrazione del giornale di registrazione ammortamento vengono eseguite in background.  
5. Fare clic su Crea giornale di registrazione.
6. Andare a Cespiti > Inserimenti nel giornale di registrazione > Giornale di registrazione cespiti.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]