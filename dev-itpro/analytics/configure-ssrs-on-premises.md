---
title: Configurare SQL Server Reporting Services per una distribuzione locale
description: In questo argomento vengono fornite informazioni sulla configurazione di SQL Server Reporting Services (SSRS) per una distribuzione locale.
author: kfend
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, UnifiedOperations
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanisathish
ms.search.validFrom: 2016-08-30T00:00:00.000Z
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: b0bfaadabe960f31d7609512b7ad6eaf848afddc
ms.contentlocale: it-it
ms.lasthandoff: 07/27/2017

---
# <a name="configure-sql-server-reporting-services-for-an-on-premises-deployment"></a>Configurare SQL Server Reporting Services per una distribuzione locale

Utilizzare la procedura descritta in questo argomento per configurare SQL Server Reporting Services (SSRS) per la distribuzione di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (locale).

1. Avviare l'applicazione Gestione configurazione di Reporting Services.
2. Lasciare il **Nome server** predefinito, che dovrebbe essere il nome del computer corrente, e l'**Istanza server di report**, **MSSQLSERVER**. 
3. Fare clic su **Connetti**.
   
   [![Connessione configurazione di Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)
   
4. Fare clic sulla scheda **Account servizi** e verificare che le impostazioni corrispondano al grafico seguente.

    [![Scheda Account servizi](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)
    
5. Fare clic sulla scheda **URL servizio Web** e verificare che le impostazioni corrispondano al grafico seguente. 

    [![Scheda URL servizio Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png) 
    
6. Fare clic sulla scheda **Database** e verificare che **Nome database** e **Impostazioni credenziali** corrispondano al grafico seguente. **Nota:** sarà necessario creare un nuovo database. A tale scopo, fare clic su **Cambia database**, quindi verificare che il nuovo nome del database sia: **DynamicsAxReportServer**.

    [![scheda database](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)
    
7. Fare clic sulla scheda **URL del portale Web** e verificare che le impostazioni corrispondano al grafico seguente. **Nota:** fare clic su **Applica** per creare e configurare correttamente il portale.

    [![scheda url del portale web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)
    
  Dopo la configurazione del portale, la scheda **Portale Web** corrisponderà al grafico seguente.
    [![scheda del portale web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)
    
8. Fare clic sull'URL dei report per visualizzare il portale Web di SQL Server Reporting Services. 
9.  Nel portale creare una nuova cartella **Dynamics**.

    [![cartella dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)
    
10. In **Gestione configurazione Reporting Services** fare clic sulla scheda **Impostazioni di posta elettronica** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda impostazioni di posta elettronica](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)
    
11. Fare clic sulla scheda **Account esecuzione** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda account esecuzione](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)
    
  Non cambiare le impostazioni predefinite nella scheda **Chiavi di crittografia**.
    [![scheda chiavi di crittografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)
    
12. Fare clic sulla scheda **Impostazioni sottoscrizione** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda impostazioni sottoscrizione](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)
    
  Non cambiare le impostazioni predefinite nella scheda **Distribuzione con scalabilità orizzontale**.
    [![scheda distribuzione con scalabilità orizzontale](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)
    
  Non cambiare le impostazioni predefinite nella scheda **Integrazione di Power BI**.
    [![scheda integrazione di power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png) 
    
13. Fare clic su **Esci** per chiudere l'applicazione **Gestione configurazione di Reporting Services**.

    [![chiudere gestione configurazione di reporting services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)
    


