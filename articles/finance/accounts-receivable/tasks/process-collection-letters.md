---
title: Elaborare lettere di sollecito
description: In questo argomento viene illustrato come creare, stampare e registrare le lettere di sollecito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustPosting, CustCollectionLetterNote
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2018-12-01
ms.dyn365.ops.version: 8.1.3
ms.openlocfilehash: 326d9375670cb4f4990a4f7070bf923a28b2c025
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "2178510"
---
# <a name="process-collection-letters"></a>Elaborare lettere di sollecito

[!include [banner](../../includes/banner.md)]

In questo argomento viene illustrato come creare, stampare e registrare le lettere di sollecito. In questa attività viene utilizzata la società dimostrativa USMF.

## <a name="set-up-a-collection-letter-sequence-on-the-posting-profile"></a>Impostare una sequenza di lettere di sollecito nel profilo registrazione
1. Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Impostazione > Profili di registrazione cliente**.
2. Fare clic su **Modifica**.
3. Selezionare una sequenza di lettere di sollecito dall'elenco a discesa. Se non si desidera generare lettere di sollecito per le transazioni che utilizzano il profilo registrazione, lasciare vuoto il campo.  
4. Espandere la scheda **Restrizioni tabella** per modificare la modalità per l'elaborazione delle lettere di sollecito. Se questo campo è impostato su **Sì**, le lettere di sollecito verranno create per il profilo registrazione.  

## <a name="create-collection-letters"></a>Crea lettere di sollecito
1. Andare a **Pannello di navigazione > Crediti e riscossioni > Lettera di sollecito > Crea lettere di sollecito**.
2. Selezionare i tipi di transazione per cui si raccoglieranno le lettere. Tutte le transazioni aperte per questi tipi verranno incluse nel calcolo.  
3. Selezionare una opzione nel campo **Lettera di sollecito**.
4. Nel campo **Data della lettera di sollecito**, immettere la data della lettera di sollecito.
5. Selezionare un profilo registrazione se **Utilizza profilo registrazione da** è stato impostato su **Seleziona**. Sono disponibili due opzioni di profilo di registrazione:   

   - **Conto**: consente di utilizzare il profilo di registrazione assegnato al conto cliente per ogni nota d'interesse.   
   - **Seleziona**: consente di utilizzare il profilo di registrazione selezionato nel campo **Profilo registrazione**.  

6. Espandere la sezione **Record da includere**.
7. Selezionare **Filtro**.
8. Nel campo **Criteri**, immettere un ID cliente. Ad esempio, immettere "US-001".
9. Selezionare **OK**.
10. Selezionare **OK**.

## <a name="print-collection-letters"></a>Stampare le lettere di sollecito
1. Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito**.
2. Nel campo **Stato** selezionare **Creata**.
3. Nel campo **Stampata** selezionare **Non stampata**.
4. Selezionare **Stampa**.
5. Selezionare **Nota lettera di sollecito**.
6. Nella sezione **Parametri**, immettere la data limite per le registrazioni.
7. Espandere la sezione **Record da includere** e immettere i dettagli della nota della lettera di sollecito.
8. Selezionare **OK** per stampare la lettera di sollecito.
9. Registrare la lettera di sollecito.

    1. Selezionare **Registra**.
    1. Immettere la data di registrazione per la lettera di sollecito.
    1. Espandere la sezione **Record da includere**.
    1. Selezionare **OK**.
    1. Nel campo **Stato** selezionare **Registrata**.
    1. Selezionare un'opzione nel campo **Stampata**.

## <a name="control-collection-letters-at-the-customer-level"></a>Controllare lettere di sollecito a livello del cliente
È anche possibile configurare lettere di sollecito a livello del cliente in modo da tenere traccia del codice di lettera di sollecito per ogni transazione, ma l'elaborazione delle lettere di sollecito sarà basata su una singola lettera di sollecito archiviata per il cliente. La singola lettera di sollecito conterrà tutte le transazioni insolute per il cliente. Poiché ora si tiene traccia dei giorni di tolleranza a livello del cliente, la lettera di sollecito successiva non verrà inviata fino a che il numero di giorni di tolleranza non è passato per la lettera di sollecito successiva nella sequenza, anche se le transazioni diventano insolute dopo l'invio dell'ultima lettera di sollecito. Questa opzione riduce il numero di lettere di sollecito inviate per cliente. 

### <a name="set-up-the-customer-to-control-collection-letters-at-the-customer-level"></a>Configurare il cliente per controllare lettere di sollecito a livello del cliente
1.  Andare a **Pannello di navigazione > Moduli > Crediti e le riscossioni > Impostazioni > Parametri contabilità clienti** e selezionare la scheda **Riscossioni**. 
2.  Impostare **Crea una lettera di sollecito per** su **Cliente**. 
3.  Andare a **Pannello di navigazione > Moduli > Crediti e riscossioni > Lettera di sollecito > Esamina ed elabora lettere di sollecito**. Per un cliente con tutte le transazioni insolute verrà generata una sola lettera di sollecito.

## <a name="ignore-payments-and-credit-memos-when-calculating-the-collection-letter-code"></a>Ignorare pagamenti e note di credito durante il calcolo del codice di lettera di sollecito
Se si includono pagamenti e note di credito nelle transazioni che saranno incluse nelle lettere di sollecito, è possibile avere pagamenti o note di credito che genereranno una lettera di sollecito. È possibile controllare il modo in cui pagamenti e note di credito controllano il codice di lettera di sollecito modificando il valore del parametro **Ignora pagamenti e note credito durante il calcolo del codice di lettera di sollecito**. 

Per ignorare pagamenti e note credito durante il calcolo del codice di lettera di sollecito, procedere come segue.

1. Andare a **Pannello di navigazione > Moduli > Crediti e le riscossioni > Impostazioni > Parametri contabilità clienti** e fare clic sulla scheda **Riscossioni**. 
2. Impostare **Ignora pagamenti e note credito durante il calcolo del codice di lettera di sollecito** su **Sì**.
