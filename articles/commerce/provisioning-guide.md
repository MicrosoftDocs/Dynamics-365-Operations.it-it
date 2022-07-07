---
title: Eseguire il provisioning dell'ambiente sandbox di Dynamics 365 Commerce
description: Questo articolo spiega come eseguire il provisioning di un ambiente sandbox Microsoft Dynamics 365 Commerce per l'utilizzo di demo o sandbox con dati demo integrati.
author: psimolin
ms.date: 06/14/2022
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
ms.openlocfilehash: 3ada30fc9d86d236b71d018ef77f2ae8573f2285
ms.sourcegitcommit: 252cb41c3029b623354698463f7b44a29fd9f184
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/15/2022
ms.locfileid: "9013136"
---
# <a name="provision-a-dynamics-365-commerce-sandbox-environment"></a>Eseguire il provisioning dell'ambiente sandbox di Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo articolo spiega come eseguire il provisioning di un ambiente sandbox Microsoft Dynamics 365 Commerce per l'utilizzo di demo con dati demo integrati. Il processo per la configurazione di un ambiente di produzione è simile ma più elaborato poiché molti dei prerequisiti dell'ambiente sandbox sono già forniti nei dati demo.

Prima di iniziare, è consigliabile dare una rapida occhiata a questo articolo per avere un'idea di ciò che richiede il processo.

Per eseguire correttamente il provisioning di un ambiente sandbox di Commerce, devi specificare alcuni parametri per l'ambiente e Commerce Scale Unit (CSU) che verranno utilizzati quando esegui il provisioning di Commerce in un secondo momento. Le istruzioni in questo articolo descrivono tutti i passaggi necessari per completare il provisioning e i parametri da utilizzare.

Dopo aver completato il provisioning dell'ambiente di Commerce, è necessario completare alcuni passaggi post-provisioning per prepararlo all'uso. Alcuni passaggi sono facoltativi, a seconda degli aspetti del sistema che vuoi usare. È sempre possibile completare i passaggi facoltativi in seguito.

Per informazioni relative a come configurare l'ambiente di Commerce dopo il provisioning, consulta [Configurare un ambiente sandbox Commerce](cpe-post-provisioning.md). Per informazioni su come configurare funzionalità facoltative per l'ambiente Commerce, vedi [Configurare le funzionalità facoltative per un ambiente sandbox Commerce](cpe-optional-features.md).

## <a name="prerequisites"></a>Prerequisiti

I seguenti prerequisiti devono essere presenti prima di poter eseguire il provisioning dell'ambiente di Commerce:

- Si dispone dell'accesso al portale di Microsoft Dynamics Lifecycle Services (LCS).
- Sei un partner o cliente esistente Microsoft Dynamics 365 e hai un progetto di implementazione già creato e disponibile per l'uso in LCS.  
- Hai creato un gruppo di sicurezza Azure Active Directory (Azure AD) da utilizzare come gruppo Amministratori del sistema di Commerce e hai il relativo ID.
- Hai creato un gruppo di sicurezza Azure AD da utilizzare come gruppo di moderatori di valutazioni e revisioni e hai il relativo ID. (Questo gruppo di sicurezza può essere lo stesso del gruppo di amministratori del sistema Commerce).
- Hai distribuito un'istanza di headquarters all'interno di LCS. Per altre informazioni, vedi [Distribuire un nuovo ambiente](/dynamics365/fin-ops-core/dev-itpro/deployment/deployenvironment-newinfrastructure).

Si noti che questo elenco non è esaustivo. In caso di problemi, contattare il partner Microsoft.

## <a name="provision-your-commerce-environment"></a>Eseguire il provisioning di un ambiente Commerce

Queste procedure spiegano come eseguire il provisioning di un ambiente Commerce. Dopo averle completate, l'ambiente Commerce sarà pronto per la configurazione. Tutti i passaggi descritti di seguito possono verificarsi nel portale di LCS.

### <a name="initialize-the-commerce-scale-unit-cloud"></a>Inizializzare Commerce Scale Unit (cloud)

Per inizializzare CSU, procedi come segue.

1. In LCS seleziona l'ambiente dall'elenco.
1. Nella visualizzazione **AMBIENTI** a destra, seleziona **Dettagli completi**. Vengono visualizzati i dettagli dell'ambiente.
1. Nella sezione **Gestisci ambiente** sotto **CARATTERISTICHE AMBIENTE**, seleziona **Gestisci**.
1. Nella scheda **Commerce Scale Units**, seleziona **Inizializza**. Viene visualizzata la vista **Aggiungi unità di scala**.
1. Nel campo **AREA**, seleziona la stessa area o l'area vicina a quella in cui è stato distribuito l'ambiente.
1. Nell'elenco a discesa **Versione** seleziona l'ultima versione disponibile.
1. Selezionare **Inizializza**.
1. Nella finestra di dialogo di avviso che chiede di confermare l'inizializzazione di Commerce Scale Unit, seleziona **sì**. La CSU è ora stata accodata per il provisioning.
1. Prima di procedere, assicurati che lo stato dell'ambiente CSU sia **COMPLETATO**. L'inizializzazione dura circa 2-5 ore.

Se non si riesce a trovare il collegamento **Gestione** nella vista dei dettagli dell'ambiente, contattare il contatto Microsoft per assistenza.

### <a name="initialize-e-commerce"></a>Inizializzare e-Commerce

Per inizializzare Commerce, procedi come segue.

1. Nella scheda **e-Commerce**, selezionare **Imposta**.
1. Immettere un nome per **Nome ambiente e-Commerce**. Da notare che ciò sarà visibile in alcuni degli URL che puntano all'istanza di e-Commerce.
1. Nel campo **Nome Commerce Scale Unit**, selezionare la CSU nell'elenco. (L'elenco dovrebbe avere una sola opzione).

    Il campo **Geografia e-Commerce** viene impostato automaticamente.

1. Selezionare **Avanti** per continuare.
1. Nel campo **Nomi host supportatiN**, immettere qualsiasi dominio valido, ad esempio `www.fabrikam.com`.
1. Nel **Gruppo di sicurezza AAD per amministratore sistema**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare il gruppo di sicurezza corretto nell'elenco.
1.  Nel **Gruppo di sicurezza AAD per moderatore di valutazioni e recensioni**, immettere le prime lettere del nome del gruppo di sicurezza che si desidera utilizzare, quindi selezionare il simbolo della lente di ingrandimento per visualizzare i risultati della ricerca. Selezionare il gruppo di sicurezza corretto nell'elenco.
1. Lasciare l'opzione **Abilita servizio Valutazioni e recensioni** impostata su **Sì**.
1. Selezionare **Inizializza**. Viene visualizzato di nuovo **Gestione di Commerce** con la scheda **e-Commerce** selezionata. L'inizializzazione di e-Commerce è stata avviata.
1. Prima di procedere, attendere che lo stato dell'inizializzazione di Commerce sia **INIZIALIZZAZIONE COMPLETATA**.
1. In **Collegamenti** in basso a destra, prendi nota degli URL per i seguenti collegamenti:

    * **Sito di e-Commerce**: il collegamento alla radice del tuo sito di e-Commerce.
    * **Creazione di siti Web di Commerce**: il collegamento allo strumento di gestione del sito.

## <a name="next-steps"></a>Passaggi successivi

Per proseguire il processo di provisioning e configurazione dell'ambiente di Commerce, consulta [Configurare un ambiente sandbox Commerce](cpe-post-provisioning.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Configurare un ambiente sandbox Dynamics 365 Commerce](cpe-post-provisioning.md)

[Configurare uno scenario BOPIS in un ambiente sandbox Dynamics 365 Commerce](cpe-bopis.md)

[Configurare le funzionalità facoltative per un ambiente sandbox Dynamics 365 Commerce](cpe-optional-features.md)

[Microsoft Lifecycle Services (LCS)](/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[Commerce Scale Unit (cloud)](/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[Portale di Microsoft Azure](https://azure.microsoft.com/features/azure-portal)

[Sito Web di Dynamics 365 Commerce](https://aka.ms/Dynamics365CommerceWebsite)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
