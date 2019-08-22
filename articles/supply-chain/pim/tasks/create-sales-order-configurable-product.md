---
title: Creare un ordine cliente per un prodotto configurabile
description: Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 39ccb68ba76cd710412df6a46fc624608d02902b
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/01/2019
ms.locfileid: "1844539"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Creare un ordine cliente per un prodotto configurabile

[!include [task guide banner](../../includes/task-guide-banner.md)]

Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente. Nell'esempio viene utilizzato il modello di altoparlante D0006 della società di dati dimostrativi USMF. In genere, un gestore degli ordini cliente usa questa procedura.


## <a name="create-a-sales-order"></a>Crea un ordine cliente
1. Fare clic su Elaborazione e richiesta di informazioni ordini cliente.
2. Fare clic su Nuovo.
3. Fare clic su Ordine cliente.
4. Nel campo Conto cliente selezionare US-001. 
5. Fare clic su OK.
6. Nel campo Numero articolo selezionare D0006.
    * Per questa attività, selezionare un prodotto configurabile.  
7. Fare clic su Prodotto e fornitura.
8. Fare clic su Configura riga.
    * Si noti che il prezzo è cambiato, in base alla configurazione selezionata, e che il campo Include cable ora è impostato su True.  
    * Notare il prezzo predefinito e le impostazioni selezionate per il cavo.  
9. Fare clic su Carica modello.
    * In questo esempio viene illustrato come è possibile utilizzare un modello per selezionare una configurazione predefinita. Se si usa questa procedura come guida attività e si desidera visualizzare gli altri valori di attributo disponibili, è necessario fare clic sul pulsante Sblocca.  
10. Fare clic su OK.
11. Fare clic su OK.
12. Espandere la sezione Dettagli riga.
13. Fare clic sulla scheda Prodotto.
    * La configurazione dell'articolo è ora elencata nelle dimensioni prodotto.  
14. Chiudere la pagina.

## <a name="select-the-product-configuration"></a>Selezionare la configurazione prodotto

