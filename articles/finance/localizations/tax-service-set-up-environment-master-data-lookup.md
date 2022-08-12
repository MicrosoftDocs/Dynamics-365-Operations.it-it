---
title: Abilitare la ricerca dei dati anagrafici per la configurazione del calcolo delle tasse
description: In questo articolo viene descritto come configurare e abilitare a funzionalità di ricerca di dati master per il calcolo delle imposte.
author: kai-cloud
ms.date: 07/14/2022
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
ms.openlocfilehash: 3642bb88d5b0570014513b64eef5fdab6d1ee9d3
ms.sourcegitcommit: 5b721f6fc1ba4350b5bd0eae457f71d80246db42
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/20/2022
ms.locfileid: "9181126"
---
# <a name="enable-master-data-lookup-for-tax-calculation-configuration"></a>Abilitare la ricerca dei dati anagrafici per la configurazione del calcolo delle tasse 

[!include [banner](../includes/banner.md)]

In questo articolo viene descritto come configurare e abilitare a funzionalità di ricerca di dati master per il calcolo delle imposte. È disponibile un elenco a discesa per selezionare i valori nella configurazione del calcolo dell'imposta per campi quali **Persona giuridica**, **Conto fornitore**, **Codice articolo**, e **Termini di consegna**. Questi valori provengono dall'ambiente Microsoft Dynamics 365 Finance connesso utilizzando l'origine dati Microsoft Dataverse.

> [!NOTE] 
> La funzionalità di ricerca dei dati master del calcolo delle imposte è una funzionalità facoltativa. Puoi saltare i seguenti passaggi se disabiliti la funzionalità **Supporto per origini dati Dataverse del servizio imposte** in Regulatory Configuration Service (RCS). Tuttavia, in tal caso, l'elenco a discesa non sarà disponibile nella configurazione del calcolo delle imposte.

Per abilitare l'elenco a discesa nella configurazione della versione della funzionalità di Calcolo imposte, completa i passaggi seguenti.

1. [Abilitare l'integrazione Microsoft Power Platform e aprire l'ambiente Dataverse.](#enable)
2. [Installare le entità virtuali di finanza e operazioni.](#install)
3. [Registrare un'applicazione Azure Active Directory (Azure AD).](#register)
4. [Concedere le autorizzazioni per le app nelle app per la finanza e le operazioni.](#grant)
5. [Configurare l'origine dati delle entità virtuali.](#configure)
6. [Abilitare le entità virtuali Dataverse.](#virtual)
7. [Impostare l'applicazione connessa per Calcolo imposte.](#set-up)
8. [Importare e impostare la configurazione di mapping del modello Dataverse.](#import)

## <a name="enable-microsoft-power-platform-integration-and-open-the-dataverse-environment"></a><a name='enable'></a>Abilitare l'integrazione Microsoft Power Platform e aprire l'ambiente Dataverse

L'integrazione delle app per la finanza e le operazioni con Microsoft Power Platform può essere abilitata al momento della creazione di un nuovo ambiente delle app per la finanza e le operazioni in Microsoft Dynamics Lifecycle Services (LCS). Per ulteriori informazioni, vedere [Panoramica di Integrazione di Microsoft Power Platform - Componenti aggiuntivi](../../fin-ops-core/dev-itpro/power-platform/add-ins-overview.md). Al termine dell'operazione, il nome dell'ambiente Microsoft Power Platform apparirà nella sezione **Integrazione di Power Platform**.

1. In LCS, nell'ambiente di finanza e operazioni, nella sezione **Integrazione di Power Platform**, trova e annota il valore di **Nome ambiente** per l'ambiente collegato.

    [![Valore del nome dell'ambiente.](./media/tcs-dataverse-master-data-lookup-1.png)](./media/tcs-dataverse-master-data-lookup-1.png)

2. Nell'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/environments), nella scheda **Ambienti**, seleziona l'ambiente che corrisponde al valore **Nome ambiente** annotato.
3. Nella pagina **Dettagli**, trova il valore **URL ambiente** dell'ambiente Dataverse. Prendi nota di questo valore, perché ti occorrerà nel [Passaggio 7. Impostazione dell'applicazione connessa per Calcolo imposte](#set-up).
4. Assicurati che sia possibile aprire l'ambiente Dataverse nel browser selezionando il valore **URL ambiente**.

    [![Pagina dell'ambiente Dataverse.](./media/tcs-dataverse-master-data-lookup-2.png)](./media/tcs-dataverse-master-data-lookup-2.png)

    > [!NOTE]
    > Mantieni l'ambiente Dataverse aperto nel browser. Ne avrai bisogno nel [Passaggio 5. Configurazione dell'origine dati dell'entità virtuale](#configure).

Per ulteriori informazioni, vedere [Abilitazione dell'integrazione di Microsoft Power Platform](../../fin-ops-core/dev-itpro/power-platform/enable-power-platform-integration.md).

## <a name="install-finance-and-operations-virtual-entities"></a><a name='install'></a>Installare le entità virtuali di finanza e operazioni

La soluzione Dataverse per le entità virtuali di finanza e operazioni deve essere installata dalla soluzione dell'entità virtuale Microsoft AppSource.

1. In AppSource, trova l'[Entità virtuale di finanza e operazioni](https://appsource.microsoft.com/product/dynamics-365/mscrm.finance_and_operations_virtual_entity).
2. Seleziona **Prova adesso**.
3. Nel campo **Seleziona un ambiente**, immetti il valore **Nome ambiente** annotato in precedenza.
4. Seleziona le caselle di controllo, quindi seleziona **Installa**.

Al termine dell'installazione, troverai l'app **Entità virtuale per finanza e operazioni** nell'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com/), in **Risorse** \> **App Dynamics 365**.

Per ulteriori informazioni, vedere [Ottenere la soluzione dell'entità virtuale](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#get-virtual-entity-solution).

## <a name="register-an-azure-ad-application"></a><a name='register'></a>Registrare un'applicazione Azure AD

L'applicazione Azure AD deve essere registrata sullo stesso tenant delle app per la finanza e le operazioni, in modo che possa essere chiamata da Dataverse.

1. Nel [portale di Azure](https://portal.azure.com), vai a **Azure Active Directory \> Registrazioni app**.
2. Seleziona **Nuova registrazione**, quindi inserisci le seguenti informazioni:

    - **Nome**: immetti un nome univoco.
    - **Tipo di account**: immetti **Qualsiasi directory Azure AD** (a tenant singolo o multi-tenant).
    - **URI di reindirizzamento**: lascia vuoto questo campo.

3. Seleziona **Registro**.
4. Annota il valore nel campo **ID applicazione (client)**, poiché sarà necessario in seguito.

    [![Valore ID applicazione Azure AD (client).](./media/tcs-dataverse-master-data-lookup-3.png)](./media/tcs-dataverse-master-data-lookup-3.png)

5. Crea una chiave simmetrica per l'applicazione.
6. Nella nuova applicazione, seleziona **Certificati e segreti**.
7. Seleziona **Nuovo segreto client**.
8. Immetti una descrizione, seleziona una data di scadenza e quindi seleziona **Salva**. Verrà creata e visualizzata una chiave. Copia il valore per un successivo utilizzo.

Per ulteriori informazioni, vedere [Registrare un'applicazione Azure AD](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#register-the-app-in-the-azure-portal).

## <a name="grant-app-permissions-in-finance-and-operations-apps"></a><a name='grant'></a>Concedere le autorizzazioni per le app nelle app per la finanza e le operazioni

Dataverse usa l'applicazione Azure AD creata per chiamare le app per la finanza e le operazioni. Pertanto, l'applicazione deve essere ritenuta affidabile dalle app per la finanza e le operazioni e associata a un account utente con i diritti appropriati. Nelle app per la finanza e le operazioni, devi creare un utente del servizio speciale con diritti **solo** per la funzionalità di entità virtuale. L'utente del servizio non deve avere altri diritti. Una volta portato a termine questo passaggio, qualsiasi applicazione che dispone del segreto dell'applicazione Azure AD creata potrà chiamare l'ambiente delle app per la finanza e le operazioni e accedere alla funzionalità dell'entità virtuale.

1. Nell'ambiente, vai ad **Amministrazione del sistema** \> **Utenti** \> **Utenti**.
2. Seleziona **Nuovo** per aggiungere un nuovo utente e immetti le seguenti informazioni:

    - **ID utente**: immetti **integrazionedataverse** o un altro valore.
    - **Nome utente**: immetti **integrazione dataverse** o un altro valore.
    - **Provider**: imposta questo campo su **NonAAD**.
    - **E-mail**: immetti **integrazionedataverse** o un altro valore. (Il valore non deve necessariamente essere un account di posta elettronica valido.)

3. Assegna all'utente il ruolo di sicurezza **Applicazione entità virtuale CDS**.
4. Rimuovi tutti gli altri ruoli, incluso **Utente di sistema**.
5. Vai ad **Amministrazione del sistema** \> **Impostazione** \> **Applicazioni Azure Active Directory** per registrare Dataverse. 
6. Aggiungi una riga, quindi, nel campo **ID client**, immetti il valore **ID applicazione (client)** annotato in precedenza.
7. Nel campo **Nome** immettere un nome. Ad esempio, immetti **Integrazione Dataverse**.
8. Nel campo **ID utente**, immetti l'ID utente che creato in precedenza.

Per ulteriori informazioni, vedere [Concedere le autorizzazioni per le app nelle app per la finanza e le operazioni](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#grant-app-permissions-in-finance-and-operations-apps).

## <a name="configure-the-virtual-entity-data-source"></a><a name='configure'></a>Configurare l'origine dati delle entità virtuali

Devi fornire a Dataverse l'istanza dell'app per la finanza e le operazioni cui connettersi.

1. L'ambiente Dataverse deve essere ancora aperto nel browser dal [Passaggio 1. Abilitare l'integrazione Microsoft Power Platform e aprire l'ambiente Dataverse](#enable). Seleziona il pulsante delle impostazioni (simbolo dell'ingranaggio) in alto a destra, quindi seleziona **Impostazioni avanzate**.

    [![Apertura delle impostazioni avanzate nell'ambiente Dataverse.](./media/tcs-dataverse-master-data-lookup-4.png)](./media/tcs-dataverse-master-data-lookup-4.png)

2. Nel menu a discesa **Impostazioni**, seleziona **Amministrazione**.

    [![Amministrazione.](./media/tcs-dataverse-master-data-lookup-5.png)](./media/tcs-dataverse-master-data-lookup-5.png)

3. Seleziona **Origini dati entità virtuali**.

    [![Origini dati entità virtuali.](./media/tcs-dataverse-master-data-lookup-6.png)](./media/tcs-dataverse-master-data-lookup-6.png)

4. Seleziona l'origine dati denominata **Finanza e operazioni**.

    [![Origine dati per la finanza e le operazioni.](./media/tcs-dataverse-master-data-lookup-7.png)](./media/tcs-dataverse-master-data-lookup-7.png)

5. Immetti le seguenti informazioni dai passaggi precedenti:

    - **URL di destinazione**: immetti l'URL da cui puoi accedere alle app per la finanza e le operazioni.
    - **URL OAuth**: immetti `https://login.windows.net/`.
    - **ID tenant**: specifica il tenant. Questo valore può essere il nome di dominio dell'indirizzo di posta elettronica della società (ad es. contoso.com).
    - **ID applicazione AAD**: immetti l'**ID applicazione (client)** creato in precedenza.
    - **Segreto applicazione AAD**: immetti il segreto generato in precedenza.
    - **Risorsa AAD**: immetti **00000015-0000-0000-c000-000000000000**. Questo valore è l'applicazione Azure AD che rappresenta le app per la finanza e le operazioni. Deve essere sempre questo stesso valore.

6. Salvare le modifiche.
7. Chiudi la pagina e torna alla pagina **Amministrazione**, dove inizierai il [Passaggio 6. Abilitare le entità virtuali Dataverse](#virtual).

    [![Chiusura dell'entità per la modifica.](./media/tcs-dataverse-master-data-lookup-8.png)](./media/tcs-dataverse-master-data-lookup-8.png)

Per ulteriori informazioni, vedere [Configurare l'origine dati entità virtuale](../../fin-ops-core/dev-itpro/power-platform/admin-reference.md#configure-the-virtual-entity-data-source).

## <a name="enable-dataverse-virtual-entities"></a><a name='virtual'></a>Abilitare le entità virtuali Dataverse

La visibilità delle entità virtuali dalle app per la finanza e le operazioni deve essere impostata su **Sì** prima che queste possano essere usate dalla configurazione di Calcolo imposte.

> [!NOTE]
> Puoi ignorare questo passaggio abilitando le entità virtuali correlate a Calcolo imposte in un solo clic nel [Passaggio 8. Impostare l'applicazione connessa per Calcolo imposte](#import). Tuttavia, consigliamo di abilitare manualmente almeno un'entità virtuale, per indicare che la connessione tra le app per la finanza e le operazioni e Dataverse sia correttamente stabilita.

1. Nell'ambiente Dataverse, nella pagina **Amministrazione**, seleziona il pulsante di filtro (simbolo di imbuto) nell'angolo superiore destro.

    [![Pulsante di filtro.](./media/tcs-dataverse-master-data-lookup-9.png)](./media/tcs-dataverse-master-data-lookup-9.png)

2. Nella finestra **Ricerca avanzata**, nel campo **Cerca**, seleziona **Entità di finanza e operazioni disponibili**.
3. Aggiungi la seguente regola: **Nome** – **Contiene** – **CompanyInfoEntity**. Quindi, seleziona **Risultati**.

    [![Finestra di ricerca avanzata.](./media/tcs-dataverse-master-data-lookup-10.png)](./media/tcs-dataverse-master-data-lookup-10.png)

4. Seleziona **CompanyInfoEntity** nei risultati di ricerca, seleziona la casella di controllo **Visibile**, quindi seleziona **Salva**.

    [![Impostazione della visibilità dell'entità.](./media/tcs-dataverse-master-data-lookup-11.png)](./media/tcs-dataverse-master-data-lookup-11.png)

5. Ripeti i passaggi precedenti per le seguenti entità cui fa riferimento la configurazione di Calcolo imposte:

    - CompanyInfoEntity
    - CurrencyEntity
    - CustCustomerV3Entity
    - DeliveryTermsEntity
    - EcoResProductCategoryEntity
    - EcoResReleasedProductV2Entity
    - LogisticsAddressCountryRegionTranslationEntity
    - LogisticsAddressStateEntity
    - PurchProcurementChargeCDSEntity
    - SalesChargeCDSEntity
    - TaxGroupEntity
    - TaxItemGroupHeadingEntity
    - VendVendorV2Entity
    - InventOperationalSiteV2Entity
    - TaxExemptCodeEntity
    - InventWarehouseEntity

    > [!NOTE]
    > Solo i primi 5.000 record di un'entità possono essere recuperati da Dataverse e resi disponibili nell'elenco a discesa della configurazione Calcolo imposte.

Per ulteriori informazioni, vedi [Abilitare entità virtuali di Microsoft Dataverse](../../fin-ops-core/dev-itpro/power-platform/enable-virtual-entities.md).

## <a name="set-up-the-connected-application-for-tax-calculation"></a><a name='set-up'></a>Impostare l'applicazione connessa per Calcolo imposte

1. In RCS, apri l'area di lavoro **Gestione funzionalità** e abilita le seguenti funzionalità:

    - Supporto origini dati Dataverse per creazione di report elettronici
    - Supporto origini dati Dataverse per servizio imposte
    - Funzionalità di globalizzazione

2. Vai a **Creazione di report elettronici**, quindi, nella sezione **Collegamenti correlati**, seleziona **Applicazioni connesse**.

    [![Applicazioni connesse.](./media/tcs-dataverse-master-data-lookup-12.png)](./media/tcs-dataverse-master-data-lookup-12.png)

3. Seleziona **Nuovo** per aggiungere un record e immetti le seguenti informazioni.

    - **Nome** - immetti un nome.
    - **Tipo**: seleziona **Dataverse**.
    - **Applicazione**: immetti il valore **URL ambiente** del tuo ambiente Dataverse, di cui hai preso nota al [Passaggio 1. Abilitare l'integrazione Microsoft Power Platform e aprire l'ambiente Dataverse](#enable).
    - **ID tenant**: immetti il tenant.
    - **URL personalizzato**: immetti l'URL Dataverse e aggiungi **/api/data/v9.1**.

4. Seleziona **Verifica connessione**, quindi, nella finestra di dialogo visualizzata, seleziona **Fare clic qui per la connessione all'applicazione remota selezionata**.

    [![Verifica della connessione.](./media/tcs-dataverse-master-data-lookup-13.png)](./media/tcs-dataverse-master-data-lookup-13.png)
5. Assicurati che venga visualizzato un messaggio "Operazione riuscita" a indicare che la connessione è stata correttamente stabilita.

    [![Messaggio di operazione riuscita.](./media/tcs-dataverse-master-data-lookup-14.png)](./media/tcs-dataverse-master-data-lookup-14.png)

## <a name="import-and-set-up-the-dataverse-model-mapping-configuration"></a><a name='import'></a>Importare e impostare la configurazione di mapping del modello Dataverse

Microsoft fornisce configurazioni di mapping del modello predefinite per le entità dalle app per la finanza e le operazioni a Calcolo imposte.

1. In RCS, vai a **Creazione di report elettronici**.
2. Nella sezione **Provider di configurazione**, nel riquadro per il provider **Microsoft**, seleziona **Repository**.

    [![Repository.](./media/tcs-dataverse-master-data-lookup-15.png)](./media/tcs-dataverse-master-data-lookup-15.png)

3. Seleziona il record **Repository di configurazioni globali**, quindi seleziona **Apri**.
4. In **Modello di dati fiscali** \> **Modello di dati per il calcolo delle imposte**, seleziona la configurazione **Mapping del modello Dataverse**.
5. Nella Scheda dettaglio **Versioni**, seleziona una versione corrispondente alla versione delle app per la finanza e le operazioni, quindi seleziona **Importa**.

    [![Importazione della configurazione di mapping del modello Dataverse.](./media/tcs-dataverse-master-data-lookup-16.png)](./media/tcs-dataverse-master-data-lookup-16.png)

    > [!IMPORTANT]
    > La configurazione **Mapping del modello Dataverse** viene applicata soltanto alla versione più aggiornata importata. Pertanto, non devi importare una versione della configurazione **Mapping del modello Dataverse** superiore alla versione della configurazione di Calcolo imposte che prevedi di implementare. Ad esempio, se prevedi di implementare la versione 40.50.225 della configurazione di Calcolo imposte, devi importare solo la versione 40.50.13 della configurazione di **Mapping del modello Dataverse**. Non devi importare la versione 40.54.14. In caso contrario, si verificherà una mancata corrispondenza del modello di dati nella configurazione.

6. Torna a **Creazione di report elettronici** e seleziona il riquadro **Configurazioni imposte**.
7. Seleziona la configurazione **Mapping del modello Dataverse**, quindi seleziona **Modifica**.
8. Impostare l'opzione **Impostazione predefinita per mapping di modello** su **Sì**.
9. Nel campo **Applicazione connessa**, seleziona l'applicazione connessa impostata al [Passaggio 7. Impostare l'applicazione connessa per Calcolo imposte](#set-up).
10. Imposta l'opzione **Imposta visibilità tabella virtuale** su **Sì** per impostare come visibili tutte le entità virtuali correlate a Calcolo imposte.

La configurazione della funzionalità di ricerca dei dati master è ora completa. Un elenco a discesa per campi quali **Persona giuridica**, **Account fornitore**, **Codice articolo** e **Termine di consegna** da Dynamics 365 Finance verrà ora abilitato nella configurazione **Versione funzionalità Calcolo imposte**.

[![Elenco a discesa delle persone giuridiche.](./media/tcs-dataverse-master-data-lookup-17.png)](./media/tcs-dataverse-master-data-lookup-17.png)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
