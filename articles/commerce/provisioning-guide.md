---
title: Provisioning di un ambiente di valutazione Dynamics 365 Commerce
description: Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 12/17/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b675d4af6fb9a080f3f3a13e64b2c5b6ad4b783
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6022424"
---
# <a name="provision-a-dynamics-365-commerce-evaluation-environment"></a>Provisioning di un ambiente di valutazione Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento illustra come eseguire il provisioning di un ambiente di valutazione Microsoft Dynamics 365 Commerce.

Prima di iniziare, è consigliabile dare una rapida occhiata a questo argomento per avere un'idea di ciò che richiede il processo.

> [!NOTE]
> Gli ambienti di valutazione di Commerce non sono generalmente disponibili e sono concessi a partner e clienti in base alla richiesta. Per ulteriori informazioni, contattare il partner Microsoft.

Per eseguire correttamente il provisioning di un ambiente di valutazione Commerce, è necessario creare un progetto con un nome e un tipo di prodotto specifici. Anche l'ambiente e Commerce Scale Unit hanno alcuni parametri specifici che devono essere utilizzati quando si prevede di eseguire il provisioning di e-Commerce in seguito. Le istruzioni in questo argomento descrivono tutti i passaggi necessari per completare il provisioning e i parametri da utilizzare.

Dopo aver completato il provisioning dell'ambiente di valutazione di Commerce, è necessario completare alcuni passaggi post-provisioning per prepararlo all'uso. Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che si desidera valutare. È sempre possibile completare i passaggi facoltativi in seguito.

Per informazioni relative a come configurare l'ambiente di valutazione di Commerce dopo il provisioning, consultare [Configurare un ambiente di valutazione di Commerce](cpe-post-provisioning.md). Per informazioni su come configurare funzionalità facoltative per l'ambiente di valutazione Commerce, vedere [Configurare le funzionalità facoltative per un ambiente di valutazione Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning dell'ambiente di valutazione Commerce:

- Essere inseriti nel programma di valutazione e aver ottenuto la capacità per un ambiente di valutazione.
- Si dispone dell'accesso al portale di Microsoft Dynamics Lifecycle Services (LCS).
- Si è un partner o cliente di Microsoft Dynamics 365 e si è in grado di creare un progetto Dynamics 365 Commerce.
- Si dispone dell'accesso di amministratore alla sottoscrizione Microsoft Azure o si è in contatto con un amministratore della sottoscrizione che può fornire assistenza se necessario.
- Si ha a disposizione l'ID tenant di Azure Active Directory (Azure AD).
- È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo Amministratori del sistema di e-Commerce e si dispone del relativo ID.
- È stato creato un gruppo di sicurezza Azure AD da utilizzare come gruppo di moderatori di Valutazioni e revisioni e devi disporre del relativo ID. (Questo gruppo di sicurezza può essere lo stesso del gruppo di amministratori del sistema e-Commerce).

Si noti che questo elenco non è esaustivo. In caso di problemi, contattare il partner Microsoft.

## <a name="provision-your-commerce-evaluation-environment"></a>Eseguire il provisioning di un ambiente di valutazione Commerce

Queste procedure spiegano come eseguire il provisioning di un ambiente di valutazione Commerce. Dopo averle completate, l'ambiente di valutazione Commerce sarà pronto per la configurazione. Tutte le attività descritte qui possono verificarsi nel portale di LCS.

### <a name="create-a-new-project"></a>Crea un nuovo progetto

Per creare un nuovo progetto in LCS, completare i passaggi seguenti:

1. Nella home page di LCS, selezionare il segno più (**+**) per creare un progetto.
1. Nel riquadro destro, seguire uno di questi passaggi:

    - Se si è un partner, scegliere **Migrare, creare soluzioni e ottenere informazioni**.
    - Se si è un cliente, scegliere **Pre-vendite potenziali**.

1. Immettere un nome, una descrizione e il settore.
1. Nel campo **Nome prodotto**, selezionare **Dynamics 365 Commerce**.
1. Nel campo **Versione prodotto**, selezionare **Dynamics 365 Commerce**.
1. Nel campo **Metodologia**, selezionare **Metodologia di implementazione di Dynamics Retail**.
1. Facoltativo, è possibile importare ruoli e utenti da un progetto esistente.
1. Selezionare **Crea**. Appare la visualizzazione del progetto.

### <a name="add-the-azure-connector"></a>Aggiungere il connettore di Azure

Per aggiungere il connettore di Azure al progetto LCS, seguire i passaggi in [Completare il processo di onboarding di Azure Resource Manager (ARM)](../fin-ops-core/dev-itpro/deployment/arm-onboarding.md).

### <a name="deploy-the-environment"></a>Distribuire l'ambiente

Per distribuire l'ambiente, attenersi a questa procedura.

> [!NOTE]
> Potrebbe non essere necessario completare i passaggi 6, 7 e/o 8, poiché le pagine con una singola opzione vengono ignorate. Nella visualizzazione **Parametri dell'ambiente**, confermare che il testo **Dynamics 365 Commerce - Demo (10.0.* x* con update *xx* della piattaforma)** appaia direttamente sopra il campo **Nome ambiente**. Per dettagli, vedere l'illustrazione che appare dopo il passaggio 8.

1. Nel menu superiore, selezionare **Distribuzione ambienti ospitati nel cloud**.
1. Selezionare **Aggiungi** per aggiungere un ambiente.
1. Nel campo **Versione applicazione**, selezionare la versione più recente. Se si ha la necessità di selezionare una versione dell'applicazione diversa dalla versione più recente, non selezionare una versione precedente alla versione **10.0.14**.
1. Nel campo **Versione piattaforma**, utilizzare la versione della piattaforma che viene scelta automaticamente per la versione dell'applicazione selezionata. 

    ![Selezione delle versioni della piattaforma e dell'applicazione](./media/project1.png)

1. Selezionare **Avanti**.
1. Selezionare **Demo** come topologia dell'ambiente.

    ![Selezionare della topologia dell'ambiente 1](./media/project2.png)

1. Nella pagina **Ambiente di distribuzione**, inserire un nome di ambiente. Non modificare le impostazioni avanzate.

    ![Pagina dell'ambiente di distribuzione](./media/project4.png)

1. Regolare le dimensioni della VM come richiesto. (Si consiglia un'unità di stockkeeping VM \[SKU\] **D13 v2** .)
1. Rivedere i termini relativi ai prezzi e alle licenze, quindi selezionare la casella di controllo per accettarli.
1. Selezionare **Avanti**.
1. Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Distribuisci**. Si ritorna alla visualizzazione **Distribuzione ambienti ospitati nel cloud** e il proprio l'ambiente deve essere visualizzato nell'elenco.

    L'ambiente richiesto viene visualizzato come accodato e quindi in fase di distribuzione. Il completamento dei flussi di lavoro dell'ambiente richiederà del tempo. Pertanto, ricontrollare dopo circa 6-9 ore.

1. Prima di procedere, assicurarsi che lo stato dell'ambiente sia **Distribuito**.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inizializzare Commerce Scale Unit (cloud)

Per inizializzare CSU, procedi come segue.

1. Nella visualizzazione **Distribuzione ambienti ospitati nel cloud**, selezionare l'ambiente nell'elenco.
1. Nella visualizzazione dell'ambiente a destra, selezionare **Dettagli completi**. Vengono visualizzati i dettagli dell'ambiente.
1. In **Funzionalità ambiente**, selezionare **Gestisci**.
1. Nella scheda **Commerce**, selezionare **Inizializza**. Vengono visualizzati i parametri di inizializzazione della CSU.
1. Nel campo **Area**, selezionare la stessa area o l'area vicina a quella in cui è stato distribuito l'ambiente.
1. Lasciare invariato il campo **Versione**.
1. Selezionare **Inizializza**.
1. Nella pagina di conferma della distribuzione, verificare che i dettagli siano corretti, quindi selezionare **Sì**. Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **Commerce** selezionata. La CSU è stata accodata per il provisioning.
1. Prima di procedere, assicurarsi che lo stato dell'ambiente CSU sia **Completato**. L'inizializzazione dura circa 2-5 ore.

Se non si riesce a trovare il collegamento **Gestione** nella vista dei dettagli dell'ambiente, contattare il contatto Microsoft per assistenza.

È possibile che venga visualizzato il seguente messaggio di errore durante il processo di distribuzione:

> Gli ambienti di valutazione (demo/test) devono registrare l'applicazione del connettore dell'unità di scala \<application ID\> in headquarters.

Se l'inizializzazione CSU non riesce e viene visualizzato questo messaggio di errore, prendi nota dell'ID applicazione, che è un identificatore univoco globale (GUID), quindi segui i passaggi nella sezione successiva per registrare l'applicazione di distribuzione CSU in Commerce headquarters.

### <a name="register-the-csu-deployment-application-in-commerce-headquarters-if-required"></a>Registrare l'applicazione di distribuzione CSU in Commerce headquarters (se necessario)

Per registrare l'applicazione di distribuzione CSU in Commerce headquarters, segui questi passaggi.

1. In Commerce headquarters, passa a **Amministrazione sistema \> Impostazione \> Applicazioni Azure Active Directory**.
1. Nella colonna **ID cliente** immetti l'ID applicazione del messaggio di errore di inizializzazione CSU ricevuto.
1. Nella colonna **Nome** inserisci un testo descrittivo (ad esempio, **Valutazione CSU**).
1. Nella colonna **ID utente** immetti **RetailServiceAccount**.
1. Riprova l'inizializzazione e la distribuzione di CSU da LCS.

### <a name="initialize-e-commerce"></a>Inizializzare e-Commerce

Per inizializzare e-Commerce, procedere come segue.

1. Nella scheda **e-Commerce**, rivedere il consenso di valutazione e quindi selezionare **Configura**.
1. Immettere un nome per **Nome ambiente e-Commerce**. Da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.
1. Nel campo **Nome Commerce Scale Unit**, selezionare la CSU nell'elenco. (L'elenco dovrebbe avere una sola opzione).

    Il campo **Geografia e-Commerce** viene impostato automaticamente.

1. Selezionare **Avanti** per continuare.
1. Nel campo **Nomi host supportatiN**, immettere qualsiasi dominio valido, ad esempio `www.fabrikam.com`.
1. Nel **Gruppo di sicurezza AAD per amministratore sistema**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare il gruppo di sicurezza corretto nell'elenco.
1.  Nel **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare il gruppo di sicurezza corretto nell'elenco.
1. Lasciare l'opzione **Abilita servizio Valutazioni e recensioni** impostata su **Sì**.
1. Selezionare **Inizializza**. Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **e-Commerce** selezionata. L'inizializzazione di e-Commerce è stata avviata.
1. Prima di procedere, attendere che lo stato dell'inizializzazione di e-Commerce sia **Inizializzazione riuscita**.
1. In **Collegamenti** in basso a destra, prendi nota degli URL per i seguenti collegamenti:

    * **Sito di e-Commerce**: il collegamento alla radice del tuo sito di e-Commerce.
    * **Creazione di siti Web di Commerce**: il collegamento allo strumento di gestione del sito.

## <a name="next-steps"></a>Passaggi successivi

Per proseguire il processo di provisioning e configurazione dell'ambiente di valutazione Commerce, consultare [Configurare un ambiente di valutazione Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dell'ambiente di valutazione Dynamics 365 Commerce](cpe-overview.md)

[Configurare un ambiente di valutazione Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente di valutazione Dynamics 365 Commerce](cpe-bopis.md)

[Configurare le funzioni facoltative per un ambiente di valutazione Dynamics 365 Commerce](cpe-optional-features.md)

[Domande frequenti sull'ambiente di valutazione Dynamics 365 Commerce](cpe-faq.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (cloud)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]