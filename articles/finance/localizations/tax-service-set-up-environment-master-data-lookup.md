---
title: Configurare un ambiente per la ricerca dei dati master
description: In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.
author: kai-cloud
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eda093a75898bace2f3c7968933b83ccafa7fabb
ms.sourcegitcommit: 66095f1b7e0fd2756aa29fd7deb9ce5392b7e0b2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2021
ms.locfileid: "5869076"
---
# <a name="set-up-an-environment-for-master-data-lookup"></a>Configurare un ambiente per la ricerca dei dati master

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

In questo argomento viene descritto come configurare l'ambiente per l'utilizzo della funzionalità di ricerca di dati master Calcolo imposte.

1. Configurare l'integrazione di Power Platform in Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Panoramica di Integrazione di Microsoft Power Platform - Componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md).
2. Configurare Dynamics 365 Finance e Microsoft Dataverse. Per ulteriori informazioni, vedere [Ottenere la soluzione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#getting-the-solution) e [Autenticazione e autorizzazione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
3. Importare la *soluzione per entità virtuale del servizio fiscale prerequisito* da [Entità virtuale servizio fiscale](https://go.microsoft.com/fwlink/?linkid=2158160).
4. Configurare Dynamics 365 Regulatory Configuration Service (RCS). 
5. Creare una richiesta di servizio per Microsoft per abilitare le versioni di anteprima delle seguenti funzionalità:

      - ERCdsFeature
      - TaxServiceCDSFeature

6. In Finance, accedere all'area di lavoro **Gestione funzionalità** e abilitare le seguente funzionalità:

      - (Anteprima) Supporto origini dati Dataverse per creazione di report elettronici
      - (Anteprima) Supporto origini dati Dataverse per servizio imposte
      - (Anteprima) Funzionalità di globalizzazione

5. Accedere a RCS utilizzando un account amministratore tenant.
6. Selezionare **Creazione di report elettronici** > **Applicazioni connesse**. 
7. Selezionare **Nuovo** per aggiungere un record e immettere le seguenti informazioni sul campo. 

   - Nel campo **Nome** immettere un nome.
   - Nel campo **Tipo** selezionare **Dataverse**.
   - Nel campo **Applicazione**, immettere l'URL di Dataverse.
   - Nel campo **Tenant**, immettere il tenant.
   - Nel campo **URL personalizzato**, immettere l'URL di Dataverse e aggiungilo con "/api/data/v9.1".

8. Selezionare **Verifica connessione** e terminare il processo di connessione. 

   [![Pulsante Verifica connessione](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

9. Selezionare **Creazione di report elettronici** > **Configurazioni fiscali** e importare le configurazioni fiscali da [Configurazioni fiscali](https://go.microsoft.com/fwlink/?linkid=2158352).

   [![Pagina Configurazioni fiscali, albero del modello di dati fiscali](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

10. Selezionare **Mapping modello di documento tassabile**, o **Mapping modello di Dataverse** se si utilizza una configurazione Microsoft e nel campo **Applicazione connessa** selezionare il record creato nel passaggio 7.
11. Impostare **Impostazione predefinita per mapping di modello** su **Sì**.

   [![Pagina Mapping modello](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
