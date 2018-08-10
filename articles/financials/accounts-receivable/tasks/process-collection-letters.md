--- 
title: Elaborare lettere di sollecito
description: Questa procedura indica come creare, stampare e registrare le lettere di sollecito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 10/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: dc837ea6513992a5f94e48baa366e279df297866
ms.contentlocale: it-it
ms.lasthandoff: 09/29/2017

---
# <a name="process-collection-letters"></a>Elaborare lettere di sollecito

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura indica come creare, stampare e registrare le lettere di sollecito. In questa attività viene utilizzata la società dimostrativa USMF.


## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Impostare una sequenza di lettere di sollecito nel profilo registrazione
1. Andare a Crediti e riscossioni > Impostazioni > Profili di registrazione cliente.
2. Fare clic su Modifica.
    * Selezionare una sequenza di lettere di sollecito dall'elenco a discesa. Se non si desidera generare lettere di sollecito per le transazioni che utilizzano il profilo registrazione, lasciare vuoto il campo.  
    * La scheda delle restrizioni della tabella consente di modificare la modalità per l'elaborazione delle lettere di sollecito. Se questo campo è impostato su Sì, le lettere di sollecito verranno create per il profilo registrazione.  
3. Chiudere la pagina.

## <a name="create-collection-letters"></a>Crea lettere di sollecito
1. Andare a Crediti e riscossioni > Lettera di sollecito > Crea lettere di sollecito.
    * È necessario selezionare i tipi di transazione per cui si raccoglieranno le lettere. Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.  
2. Selezionare una opzione nel campo Lettera di sollecito.
3. Immettere la data della lettera di sollecito.
    * Sono disponibili due opzioni di profilo registrazione. Conto: consente di utilizzare il profilo registrazione assegnato al conto cliente per ogni nota d'interesse.   Seleziona: consente di utilizzare il profilo di registrazione selezionato nel campo Profilo registrazione.  
    * Selezionare un profilo registrazione se "Utilizza profilo registrazione da" è stato impostato su "Seleziona".  
4. Espandere la sezione Record da includere.
5. Fare clic su Filtro.
6. Nel campo Criteri, immettere un ID cliente. Ad esempio, immettere "US-001".
7. Fare clic su OK.
8. Fare clic su OK.

## <a name="print-collection-letters"></a>Stampare le lettere di sollecito
1. Andare a Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito.
2. Nel campo Stato selezionare "Creata".
3. Nel campo Stampata selezionare "Non stampata".
4. Fare clic su Stampa.
5. Fare clic su Nota lettera di sollecito.
6. Espandere la sezione Record da includere.
7. Specificare la data limite per le registrazioni
8. Fare clic su OK per stampare la lettera di sollecito.

## <a name="post-the-collection-letter"></a>Registrare la lettera di sollecito
1. Fare clic su Registra.
2. Immettere la data di registrazione per la lettera di sollecito.
3. Espandere la sezione Record da includere.
4. Fare clic su OK.
5. Nel campo Stato selezionare "Registrata".
6. Selezionare un'opzione nel campo Stampata.


