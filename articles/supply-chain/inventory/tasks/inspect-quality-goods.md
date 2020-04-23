---
title: Verificare la qualità delle merci
description: In questo argomento viene descritto come elaborare un ordine di controllo qualità.
author: perlynne
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventQualityOrderTable, InventQualityOrderLineResults, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ee5f83b2dad60567341f33a73ce63d01e9da8289
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213977"
---
# <a name="inspect-the-quality-of-goods"></a>Verificare la qualità delle merci

[!include [banner](../../includes/banner.md)]

In questo argomento viene descritto come elaborare un ordine di controllo qualità. È possibile eseguire questa guida nella società di dati dimostrativi USMF. Prima di iniziare questa procedura di esempio, è necessario confermare l'ordine fornitore "000016" e registrare un'entrata prodotti. In questo modo verrà automaticamente creato un ordine di controllo qualità. Le ispezioni di controllo qualità sono in genere effettuati da un addetto al controllo qualità.


## <a name="select-a-quality-order"></a>Selezionare un ordine di controllo qualità.
1. Nel pannello di navigazione andare a **Moduli > Gestione articoli > Attività periodiche > Gestione qualità > Ordini di controllo qualità**.
2. Selezionare l'ordine di controllo qualità creato prima di aver avviato questa procedura.  

## <a name="record-test-results"></a>Registrazione dei risultati dei test
1. Selezionare **Risultati**.
2. Selezionare **Modifica**.
3. Nel campo **Quantità risultante** immettere un numero.
4. Nel campo **Risultato** fare clic sul record desiderato del menu a discesa.  
- In questo esempio il risultato è basato su un risultato predefinito. In genere viene registrato un risultato del test più specifico, ad esempio una dimensione o un altro valore simile.  
5. Selezionare **Salva**.
6. Chiudere la pagina.

## <a name="validate-the-quality-order"></a>Convalida l'ordine di controllo qualità
1. Selezionare **Convalida**.
2. Nel campo **Convalidato da**, selezionare l'utente che esegue l'ispezione dal menu a discesa.  
3. Fare clic su **Seleziona**.
4. Selezionare **OK**.
5. Chiudere la pagina.

