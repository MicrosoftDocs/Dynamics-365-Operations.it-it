---
title: Creare un ordine cliente per un prodotto configurabile
description: Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, SalesOrderProcessingWorkspace, SalesCreateOrder, SalesTable, PCRuntimeConfigurator, PCTemplateConfigurationSelection
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8607de5705354aa58c985fb536f3e1d52acd1f37
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921291"
---
# <a name="create-a-sales-order-for-a-configurable-product"></a>Creare un ordine cliente per un prodotto configurabile

[!include [banner](../../includes/banner.md)]

Questa procedura mostra come applicare un modello di configurazione a un prodotto in un ordine cliente. Nell'esempio viene utilizzato il modello di altoparlante D0006 della società di dati dimostrativi USMF. In genere, un gestore degli ordini cliente usa questa procedura.

## <a name="create-a-sales-order"></a>Crea un ordine cliente

1. Vai a **Vendite e marketing \> Aree di lavoro \> Elaborazione e richiesta di informazioni ordini cliente**.
1. Selezionare **Nuovo**.
1. Selezionare **Ordine cliente**.
1. Nel campo **Conto cliente** selezionare *US-001*. 
1. Selezionare **OK**.
1. Nel campo **Numero articolo** selezionare *D0006*.
    * Per questa attività, selezionare un prodotto configurabile.  
1. Fare clic su **Prodotto e fornitura**.
1. Selezionare **Configura riga**.
    * Si noti che il prezzo è cambiato, in base alla configurazione selezionata, e che il campo **Includi cavo** ora è impostato su *True*.  
    * Notare il prezzo predefinito e le impostazioni selezionate per il cavo.  
1. Selezionare **Carica modello**.
    * In questo esempio viene illustrato come è possibile utilizzare un modello per selezionare una configurazione predefinita. Se si usa questa procedura come guida attività e si desidera visualizzare gli altri valori di attributo disponibili, è necessario fare clic sul pulsante **Sblocca**.  
1. Selezionare **OK**.
1. Selezionare **OK**.
1. Espandere la sezione **Dettagli riga**.
1. Selezionare la scheda **Prodotto**
    * La configurazione dell'articolo è ora elencata nelle dimensioni prodotto.  
1. Chiudere la pagina.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]