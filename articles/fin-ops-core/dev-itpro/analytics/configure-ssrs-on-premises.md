---
title: Configurare SQL Server Reporting Services per le distribuzioni locali
description: In questo articolo vengono fornite informazioni sulla configurazione di SQL Server Reporting Services (SSRS) per una distribuzione locale.
author: PeterRFriis
ms.date: 06/23/2017
ms.topic: article
ms.prod: dynamics-365
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: peterfriis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.custom: 55651
ms.assetid: ''
ms.service: ''
ms.openlocfilehash: 9acb681ce07c3a7da82a630c7a87a4271a411b51
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275429"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a>Configurare SQL Server Reporting Services per le distribuzioni locali

[!include [banner](../includes/banner.md)]

Utilizza la procedura descritta in questo articolo per configurare SQL Server Reporting Services (SSRS) per la distribuzione di Microsoft Dynamics 365 Finance + Operations (on-premises).

1. Avviare l'applicazione Gestione configurazione di Reporting Services.
2. Lasciare il **Nome server** predefinito, che dovrebbe essere il nome del computer corrente, e l'**Istanza server di report**, **MSSQLSERVER**.
3. Fare clic su **Connetti**.

    [![Connessione configurazione di Reporting Services.](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)

4. Fare clic sulla scheda **Account servizi** e verificare che le impostazioni corrispondano al grafico seguente.

    [![Scheda Account servizi.](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)

5. Fare clic sulla scheda **URL servizio Web** e verificare che le impostazioni corrispondano al grafico seguente.

    [![Scheda URL servizio Web.](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)

6. Fare clic sulla scheda **Database** e verificare che **Nome database** e **Impostazioni credenziali** corrispondano al grafico seguente.

    > [!NOTE]
    > Sarà necessario creare un nuovo database. A tale scopo, fare clic su **Cambia database**, quindi verificare che il nuovo nome del database sia: **DynamicsAxReportServer**.

    [![scheda database.](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)

7. Fare clic sulla scheda **URL del portale Web** e verificare che le impostazioni corrispondano al grafico seguente.

    > [!NOTE]
    > Fare clic su **Applica** per creare e configurare correttamente il portale.

    [![scheda url del portale Web.](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)

    Dopo la configurazione del portale, la scheda **Portale Web** corrisponderà al grafico seguente.

    [![scheda del portale web.](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)

8. Fare clic sull'URL dei report per visualizzare il portale Web di SQL Server Reporting Services.
9. Nel portale creare una nuova cartella **Dynamics**.

    [![cartella dynamics.](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)

10. In **Gestione configurazione Reporting Services** fare clic sulla scheda **Impostazioni di posta elettronica** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda impostazioni di posta elettronica.](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)

11. Fare clic sulla scheda **Account esecuzione** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda account esecuzione.](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)

    Non cambiare le impostazioni predefinite nella scheda **Chiavi di crittografia**.

    [![scheda chiavi di crittografia.](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)

12. Fare clic sulla scheda **Impostazioni sottoscrizione** e verificare che le impostazioni corrispondano al grafico seguente.

    [![scheda impostazioni sottoscrizione.](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)

    Non cambiare le impostazioni predefinite nella scheda **Distribuzione con scalabilità orizzontale**.

    [![scheda distribuzione con scalabilità orizzontale.](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)

    Non cambiare le impostazioni predefinite nella scheda **Integrazione di Power BI**.

    [![scheda integrazione di power bi.](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)

13. Fare clic su **Esci** per chiudere l'applicazione **Gestione configurazione di Reporting Services**.

    [![chiudere gestione configurazione di reporting services.](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
