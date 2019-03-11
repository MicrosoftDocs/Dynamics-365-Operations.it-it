---
title: Creazione di criteri di acquisto
description: Questa procedura vi mostra come creare criteri acquisto da allineare con i vostri processi aziendali per acquistare.
author: mkirknel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysPolicyListPage, SysPolicyParameters, SysPolicy, RequisitionPurposeRule
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3bd4d6f8625c91f2190e994f04cbec4548272f04
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "312901"
---
# <a name="create-purchasing-policies"></a>Creazione di criteri di acquisto

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura vi mostra come creare criteri acquisto da allineare con i vostri processi aziendali per acquistare. Prima di creare criteri di acquisto, è necessario impostare i parametri dei criteri di acquisto. È possibile creare, modificare e ritirare criteri di acquisto, ma non eliminarli. In genere questa procedura sarà svolta da un responsabile acquisti. È necessario impostare le classificazioni del contratto di acquisto prima di iniziare.


## <a name="set-up-policy-parameters"></a>Impostazione dei parametri di criteri
1. Andare a Criteri di acquisto.
2. Fare clic su Parametri.
    * Le regole di precedenza dei criteri si applicano ai livelli differenti nella vostra organizzazione. Le unità organizzative visualizzate dipendono dalla vostra gerarchia organizzativa e da a quali livelli nella gerarchia è stato assegnato lo scopo di controllo interno di approvvigionamento. Per esempio, la vostra organizzazione potrebbe avere persone giuridiche, centri di costo, regioni e reparti, ma può essere che soltanto alcuni di questi abbiano uno scopo di gerarchia di controllo interno di approvvigionamento. Come impostazione predefinita, l'organizzazione di tipo Società è disponibile.  
3. Fare clic sulla scheda Parametri tipo di regola dei criteri.
4. Nella struttura, selezionare 'Regola di controllo criteri di acquisto/richiesta di acquisto'.
    * L'ordine di precedenza per la risoluzione dei criteri viene definito a livello dei criteri. Tuttavia, per alcuni tipi di criteri è possibile sostituire l'ordine di precedenza per singoli tipi di regole dei criteri. Per esempio, potreste definire l'ordine di precedenza affinchè i criteri di acquisto siano: centro di costo, reparto, società. Per la regola dei criteri di catalogo l'ordine di precedenza potrebbe essere il seguente: reparto, centro di costo, società. È possibile modificare l'ordine di precedenza per la regola dei criteri di catalogo. Quando un lavoratore crea una richiesta, il catalogo che viene visualizzato varia in base ai criteri associati al reparto del lavoratore, al centro di costo e infine alla società.  
    * Se c'è più di un livello organizzativo elencato, potete usare le frecce su/giù per impostare l'ordine di precedenza per la regola di controllo di richiesta di acquisto.  
5. Chiudere la pagina.

## <a name="create-a-new-policy"></a>Crea nuovi criteri
1. Fare clic su Nuovo.
2. Digitare un valore nel campo Nome.
3. Nel campo Descrizione digitare un valore.
    * I singoli criteri di acquisto possono solo essere applicati a una gerarchia organizzativa. Per esempio, potreste avere una gerarchia chiamata "Geografica" e una "Reparto" e avere criteri di acquisto diversi per ciascuna.  
    * Selezionare un'organizzazione a cui il criterio dovrebbe applicarsi.  
4. Fare clic sulla freccia per aggiungere l'organizzazione selezionata.
    * Potete ripetere questo processo per aggiungere più organizzazioni.  

## <a name="add-a-policy-rule"></a>Aggiungere una regola dei criteri
1. Nell'elenco Tipo di regola dei criteri, selezionare Regola scopo richiesta.
    * Creerete una regola che fissa lo scopo richiesta predefinito sul tipo Consumo ma che permette che il tipo Rifornimento sia selezionato invece.  
2. Fare clic su Crea regola dei criteri.
3. Selezionare Sì nel campo Consenti forzatura manuale.
4. Fare clic su Chiudi.
    * Ora è possibile impostare altre regole dei criteri per i criteri di acquisto.   Si noti che un tipo di regola di criteri non può avere regole sovrapposte attive allo stesso tempo all'interno di un singolo criterio di approvvigionamento.  
5. Chiudere la pagina.
6. Chiudere la pagina.

