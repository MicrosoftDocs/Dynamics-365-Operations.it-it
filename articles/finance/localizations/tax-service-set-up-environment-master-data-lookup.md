---
title: Abilitare la ricerca dei dati anagrafici per la configurazione del calcolo delle tasse
description: In questo argomento viene descritto come configurare e abilitare a funzionalità di ricerca di dati master per il calcolo delle imposte.
author: kai-cloud
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: kfend
ms.custom: ''
ms.search.region: Global
ms.author: pashao
ms.search.validFrom: 2021-04-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 7640144b1687fc64e55f659d49cdb0817c17294a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686713"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Abilitare la ricerca dei dati anagrafici per la configurazione del calcolo delle tasse 

[!include [banner](../includes/banner.md)]

In questo argomento viene descritto come configurare e abilitare a funzionalità di ricerca di dati master per il calcolo delle imposte. È disponibile un elenco a discesa per selezionare i valori nella configurazione del calcolo dell'imposta per campi quali **Persona giuridica**, **Conto fornitore**, **Codice articolo**, e **Termini di consegna**. Questi valori provengono dall'ambiente Microsoft Dynamics 365 Finance connesso utilizzando l'origine dati Microsoft Dataverse.

> [!NOTE] 
> La funzionalità di ricerca dei dati master del calcolo delle imposte è una funzionalità facoltativa. Puoi saltare i seguenti passaggi se disabiliti la funzionalità **Supporto per origini dati Dataverse del servizio imposte** in Regulatory Configuration Service (RCS). Tuttavia, in tal caso, l'elenco a discesa non sarà disponibile nella configurazione del calcolo delle imposte.

1. Imposta l'integrazione di Microsoft Power Platform in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Panoramica di Integrazione di Microsoft Power Platform - Componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Dopo aver completato questo passaggio, il nome dell'ambiente Microsoft Power Platform apparirà nella sezione **Integrazione di Power Platform**.
2. Vai all'[interfaccia di amministrazione di Microsoft Power Platform](https://admin.powerplatform.microsoft.com/environments) e seleziona il nome dell'ambiente. Viene fornito l'URL dell'ambiente.
3. Configura Dynamics 365 Finance e Dataverse. Per ulteriori informazioni, vedi [Ottenere la soluzione dell'entità virtuale](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution) e [Autenticazione e autorizzazione](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#authentication-and-authorization).
4. Impostare le seguenti entità. Per ulteriori informazioni, vedi [Abilitare entità virtuali di Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCityEntity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity

5. Imposta il Regulatory Configuration Service (RCS). Apri l'area di lavoro **Gestione funzionalità** e abilita le seguente funzionalità:

    - Supporto origini dati Dataverse per creazione di report elettronici
    - Supporto origini dati Dataverse per servizio imposte
    - Funzionalità di globalizzazione

6. Accedere a RCS utilizzando un account amministratore tenant.
7. Selezionare **Creazione di report elettronici** > **Applicazioni connesse**. 
8. Selezionare **Nuovo** per aggiungere un record e immettere le seguenti informazioni sul campo. 

    - Nel campo **Nome** immettere un nome.
    - Nel campo **Tipo** selezionare **Dataverse**.
    - Nel campo **Applicazione**, immettere l'URL di Dataverse.
    - Nel campo **Tenant**, immettere il tenant.
    - Nel campo **URL personalizzato**, immettere l'URL di Dataverse e aggiungilo con "/api/data/v9.1".

9. Selezionare **Verifica connessione** e terminare il processo di connessione. 

    [![Pulsante Verifica connessione.](./media/tax-service-setup-environment-for-mater-date-pic1.png)](./media/tax-service-setup-environment-for-mater-date-pic1.png)

10. Selezionare **Creazione di report elettronici** > **Configurazioni fiscali** e importare le configurazioni fiscali da [Configurazioni fiscali](https://go.microsoft.com/fwlink/?linkid=2158352).

    [![Pagina Configurazioni fiscali, albero del modello di dati fiscali.](./media/tax-service-setup-environment-for-mater-date-pic2.png)](./media/tax-service-setup-environment-for-mater-date-pic2.png)

11. Selezionare **Mapping modello di documento tassabile**, o **Mapping modello di Dataverse** se si utilizza una configurazione Microsoft e nel campo **Applicazione connessa** selezionare il record creato nel passaggio 7.
12. Impostare **Impostazione predefinita per mapping di modello** su **Sì**.

    [![Pagina Mapping modello.](./media/tax-service-setup-environment-for-mater-date-pic3.png)](./media/tax-service-setup-environment-for-mater-date-pic3.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
