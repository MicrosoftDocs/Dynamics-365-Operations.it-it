---
title: Configurare SQL Server Reporting Services per una distribuzione locale
description: In questo argomento vengono fornite informazioni sulla configurazione di SQL Server Reporting Services (SSRS) per una distribuzione locale.
author: sarvanisathish
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core
ms.custom: 55651
ms.assetid: 
ms.search.region: Global
ms.author: sarvanis
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2a1f11641a2ec055cfaa0157ac9a40525daa4006
ms.contentlocale: it-it
ms.lasthandoff: 11/03/2017

---
# <a name="configure-sql-server-reporting-services-for-an-on-premises-deployment"></a><span data-ttu-id="ada17-103">Configurare SQL Server Reporting Services per una distribuzione locale</span><span class="sxs-lookup"><span data-stu-id="ada17-103">Configure SQL Server Reporting Services for an on-premises deployment</span></span>

<span data-ttu-id="ada17-104">Utilizzare la procedura descritta in questo argomento per configurare SQL Server Reporting Services (SSRS) per la distribuzione di Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (locale).</span><span class="sxs-lookup"><span data-stu-id="ada17-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises) deployment.</span></span>

1. <span data-ttu-id="ada17-105">Avviare l'applicazione Gestione configurazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ada17-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="ada17-106">Lasciare il **Nome server** predefinito, che dovrebbe essere il nome del computer corrente, e l'**Istanza server di report**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="ada17-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span> 
3. <span data-ttu-id="ada17-107">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="ada17-107">Click **Connect**.</span></span>
   
   <span data-ttu-id="ada17-108">[![Connessione configurazione di Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>
   
4. <span data-ttu-id="ada17-109">Fare clic sulla scheda **Account servizi** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ada17-110">[![Scheda Account servizi](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>
    
5. <span data-ttu-id="ada17-111">Fare clic sulla scheda **URL servizio Web** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span> 

    <span data-ttu-id="ada17-112">[![Scheda URL servizio Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span> 
    
6. <span data-ttu-id="ada17-113">Fare clic sulla scheda **Database** e verificare che **Nome database** e **Impostazioni credenziali** corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span> <span data-ttu-id="ada17-114">**Nota:** sarà necessario creare un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="ada17-114">**Note:** You will need to create a new database.</span></span> <span data-ttu-id="ada17-115">A tale scopo, fare clic su **Cambia database**, quindi verificare che il nuovo nome del database sia: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="ada17-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="ada17-116">[![scheda database](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>
    
7. <span data-ttu-id="ada17-117">Fare clic sulla scheda **URL del portale Web** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span> <span data-ttu-id="ada17-118">**Nota:** fare clic su **Applica** per creare e configurare correttamente il portale.</span><span class="sxs-lookup"><span data-stu-id="ada17-118">**Note:** You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="ada17-119">[![scheda url del portale web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>
    
  <span data-ttu-id="ada17-120">Dopo la configurazione del portale, la scheda **Portale Web** corrisponderà al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>
    <span data-ttu-id="ada17-121">[![scheda del portale web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>
    
8. <span data-ttu-id="ada17-122">Fare clic sull'URL dei report per visualizzare il portale Web di SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ada17-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span> 
9.  <span data-ttu-id="ada17-123">Nel portale creare una nuova cartella **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="ada17-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="ada17-124">[![cartella dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>
    
10. <span data-ttu-id="ada17-125">In **Gestione configurazione Reporting Services** fare clic sulla scheda **Impostazioni di posta elettronica** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ada17-126">[![scheda impostazioni di posta elettronica](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>
    
11. <span data-ttu-id="ada17-127">Fare clic sulla scheda **Account esecuzione** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ada17-128">[![scheda account esecuzione](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>
    
  <span data-ttu-id="ada17-129">Non cambiare le impostazioni predefinite nella scheda **Chiavi di crittografia**. [![scheda Chiavi di crittografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-129">Don’t change the default settings on the **Encryption Keys** tab. [![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>
    
12. <span data-ttu-id="ada17-130">Fare clic sulla scheda **Impostazioni sottoscrizione** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ada17-130">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ada17-131">[![scheda impostazioni sottoscrizione](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-131">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>
    
  <span data-ttu-id="ada17-132">Non cambiare le impostazioni predefinite nella scheda **Distribuzione con scalabilità orizzontale**. [![scheda Distribuzione con scalabilità orizzontale](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-132">Don’t change the default settings on the **Scale-out Deployment** tab. [![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>
    
  <span data-ttu-id="ada17-133">Non cambiare le impostazioni predefinite nella scheda **Integrazione di Power BI**. [![scheda Integrazione di Power BI](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-133">Don’t change the default settings on the **Power BI Integration** tab. [![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span> 
    
13. <span data-ttu-id="ada17-134">Fare clic su **Esci** per chiudere l'applicazione **Gestione configurazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="ada17-134">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="ada17-135">[![chiudere gestione configurazione di reporting services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="ada17-135">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
    


