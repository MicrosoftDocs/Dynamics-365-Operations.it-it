---
title: Configurare SQL Server Reporting Services per le distribuzioni locali
description: In questo argomento vengono fornite informazioni sulla configurazione di SQL Server Reporting Services (SSRS) per una distribuzione locale.
author: PeterRFriis
manager: AnnBe
ms.date: 06/23/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 55651
ms.assetid: ''
ms.search.region: Global
ms.author: perahlff
ms.search.validFrom: 2016-08-30
ms.dyn365.ops.version: Platform update 8
ms.openlocfilehash: 2577705b04beef1f8b03f83ed8536be2e6ab6e83
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683923"
---
# <a name="configure-sql-server-reporting-services-for-on-premises-deployments"></a><span data-ttu-id="ea5d6-103">Configurare SQL Server Reporting Services per le distribuzioni locali</span><span class="sxs-lookup"><span data-stu-id="ea5d6-103">Configure SQL Server Reporting Services for on-premises deployments</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ea5d6-104">Utilizzare la procedura descritta in questo argomento per configurare SQL Server Reporting Services (SSRS) per la distribuzione di Microsoft Dynamics 365 Finance + Operations (locale).</span><span class="sxs-lookup"><span data-stu-id="ea5d6-104">Use the steps in this topic to configure SQL Server Reporting Services (SSRS) for your Microsoft Dynamics 365 Finance + Operations (on-premises) deployment.</span></span>

1. <span data-ttu-id="ea5d6-105">Avviare l'applicazione Gestione configurazione di Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-105">Open the Reporting Services Configuration Manager application.</span></span>
2. <span data-ttu-id="ea5d6-106">Lasciare il **Nome server** predefinito, che dovrebbe essere il nome del computer corrente, e l'**Istanza server di report**, **MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-106">Leave the default **Server name**, which should be the name of the current machine, and the **Report Server Instance**, **MSSQLSERVER**.</span></span>
3. <span data-ttu-id="ea5d6-107">Fare clic su **Connetti**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-107">Click **Connect**.</span></span>

    <span data-ttu-id="ea5d6-108">[![Connessione configurazione di Reporting Services](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-108">[![Reporting services configuration connection](./media/ssrs-config-manager-01.png)](./media/ssrs-config-manager-01.png)</span></span>

4. <span data-ttu-id="ea5d6-109">Fare clic sulla scheda **Account servizi** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-109">Click the **Service Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-110">[![Scheda Account servizi](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-110">[![Service account tab](./media/ssrs-config-manager-02.png)](./media/ssrs-config-manager-02.png)</span></span>

5. <span data-ttu-id="ea5d6-111">Fare clic sulla scheda **URL servizio Web** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-111">Click the **Web Service URL** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-112">[![Scheda URL servizio Web](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-112">[![Web service URL tab](./media/ssrs-config-manager-03.png)](./media/ssrs-config-manager-03.png)</span></span>

6. <span data-ttu-id="ea5d6-113">Fare clic sulla scheda **Database** e verificare che **Nome database** e **Impostazioni credenziali** corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-113">Click the **Database** tab and verify that the **Database Name** and **Credential settings** match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea5d6-114">Sarà necessario creare un nuovo database.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-114">You will need to create a new database.</span></span> <span data-ttu-id="ea5d6-115">A tale scopo, fare clic su **Cambia database**, quindi verificare che il nuovo nome del database sia: **DynamicsAxReportServer**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-115">To do this, click **Change Database**, and then verify that the new database name is: **DynamicsAxReportServer**.</span></span>

    <span data-ttu-id="ea5d6-116">[![scheda database](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-116">[![database tab](./media/ssrs-config-manager-04.png)](./media/ssrs-config-manager-04.png)</span></span>

7. <span data-ttu-id="ea5d6-117">Fare clic sulla scheda **URL del portale Web** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-117">Click the **Web Portal URL** tab and verify that the settings match the following graphic.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ea5d6-118">Fare clic su **Applica** per creare e configurare correttamente il portale.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-118">You must click **Apply** to create and properly configure the Portal.</span></span>

    <span data-ttu-id="ea5d6-119">[![scheda url del portale web](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-119">[![web portal url tab](./media/ssrs-config-manager-05.png)](./media/ssrs-config-manager-05.png)</span></span>

    <span data-ttu-id="ea5d6-120">Dopo la configurazione del portale, la scheda **Portale Web** corrisponderà al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-120">After the Portal is configured, the **Web Portal** tab will match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-121">[![scheda del portale web](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-121">[![web portal tab](./media/ssrs-config-manager-06.png)](./media/ssrs-config-manager-06.png)</span></span>

8. <span data-ttu-id="ea5d6-122">Fare clic sull'URL dei report per visualizzare il portale Web di SQL Server Reporting Services.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-122">Click the reports URL to view the SQL Server Reporting Services web portal.</span></span>
9. <span data-ttu-id="ea5d6-123">Nel portale creare una nuova cartella **Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-123">When you are in the portal, create a new folder named **Dynamics**.</span></span>

    <span data-ttu-id="ea5d6-124">[![cartella dynamics](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-124">[![dynamics folder](./media/ssrs-config-manager-07.png)](./media/ssrs-config-manager-07.png)</span></span>

10. <span data-ttu-id="ea5d6-125">In **Gestione configurazione Reporting Services** fare clic sulla scheda **Impostazioni di posta elettronica** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-125">In the **Reporting Services Configuration Manager**, click the **E-mail Settings** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-126">[![scheda impostazioni di posta elettronica](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-126">[![email settings tab](./media/ssrs-config-manager-08.png)](./media/ssrs-config-manager-08.png)</span></span>

11. <span data-ttu-id="ea5d6-127">Fare clic sulla scheda **Account esecuzione** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-127">Click the **Execution Account** tab and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-128">[![scheda account esecuzione](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-128">[![execution account tab](./media/ssrs-config-manager-09.png)](./media/ssrs-config-manager-09.png)</span></span>

    <span data-ttu-id="ea5d6-129">Non cambiare le impostazioni predefinite nella scheda **Chiavi di crittografia**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-129">Don't change the default settings on the **Encryption Keys** tab.</span></span>

    <span data-ttu-id="ea5d6-130">[![scheda chiavi di crittografia](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-130">[![encryption keys tab](./media/ssrs-config-manager-10.png)](./media/ssrs-config-manager-10.png)</span></span>

12. <span data-ttu-id="ea5d6-131">Fare clic sulla scheda **Impostazioni sottoscrizione** e verificare che le impostazioni corrispondano al grafico seguente.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-131">Click the **Subscription Settings** tab, and verify that the settings match the following graphic.</span></span>

    <span data-ttu-id="ea5d6-132">[![scheda impostazioni sottoscrizione](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-132">[![subscription settings tab](./media/ssrs-config-manager-11.png)](./media/ssrs-config-manager-11.png)</span></span>

    <span data-ttu-id="ea5d6-133">Non cambiare le impostazioni predefinite nella scheda **Distribuzione con scalabilità orizzontale**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-133">Don't change the default settings on the **Scale-out Deployment** tab.</span></span>

    <span data-ttu-id="ea5d6-134">[![scheda distribuzione con scalabilità orizzontale](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-134">[![scale-out deployment tab](./media/ssrs-config-manager-12.png)](./media/ssrs-config-manager-12.png)</span></span>

    <span data-ttu-id="ea5d6-135">Non cambiare le impostazioni predefinite nella scheda **Integrazione di Power BI**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-135">Don't change the default settings on the **Power BI Integration** tab.</span></span>

    <span data-ttu-id="ea5d6-136">[![scheda integrazione di power bi](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-136">[![power bi integration tab](./media/ssrs-config-manager-13.png)](./media/ssrs-config-manager-13.png)</span></span>

13. <span data-ttu-id="ea5d6-137">Fare clic su **Esci** per chiudere l'applicazione **Gestione configurazione di Reporting Services**.</span><span class="sxs-lookup"><span data-stu-id="ea5d6-137">Click **Exit** to close the **Reporting Services Configuration Manager**.</span></span>

    <span data-ttu-id="ea5d6-138">[![chiudere gestione configurazione di reporting services](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span><span class="sxs-lookup"><span data-stu-id="ea5d6-138">[![close reporting services configuration manager](./media/ssrs-config-manager-14.png)](./media/ssrs-config-manager-14.png)</span></span>
