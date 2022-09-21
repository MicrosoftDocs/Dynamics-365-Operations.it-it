---
title: Modulo Chat di Commerce con Multicanale per Customer Service
description: Questo articolo descrive il modulo Chat di Commerce con Multicanale per Customer Service in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-07-20
ms.openlocfilehash: b8eaed3eb015e96b1db6fa2297c341ea9d3ff8ad
ms.sourcegitcommit: b1df4db7facb5e7094138836c41a65c4a158f01d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/13/2022
ms.locfileid: "9473811"
---
# <a name="commerce-chat-with-omnichannel-for-customer-service-module"></a>Modulo Chat di Commerce con Multicanale per Customer Service

[!include [banner](includes/banner.md)]

Questo articolo descrive il modulo *Chat di Commerce con Multicanale per Customer Service* in Microsoft Dynamics 365 Commerce.

Nella versione 10.0.29 di Commerce, è stato aggiunto un nuovo modulo Chat di Commerce con Multicanale per Customer Service alla libreria di moduli Commerce. La funzionalità di chat di Commerce offre ai clienti di e-commerce le funzionalità di chat di Multicanale per Customer Service di Dynamics 365, che include il supporto per gli agenti live per rispondere alle domande dei clienti, fornire un servizio clienti e facilitare le vendite per i clienti di Commerce.

La funzionalità di chat di Commerce consente ai rivenditori di raggiungere i seguenti obiettivi:

- Aumentare l'engagement personalizzato con i clienti per migliorare la fidelizzazione degli stessi.
- Migliorare il servizio clienti attraverso l'integrazione di agenti umani e chatbot self-service.
- Aiutare gli agenti ad acquisire esperienza attraverso i dati di profili dei clienti, ordini e acquisti in tempo reale che guidano i miglioramenti operativi e l'engagement.
- Migliorare la soddisfazione generale dei clienti per aumentare le vendite.

Le seguenti funzionalità sono disponibili in Chat di Commerce:

- Chat di Commerce con Multicanale per Customer Service
- L'aggiunta di **Servizio clienti di Commerce** come scheda applicazione nell'esperienza agente in Multicanale per Customer Service di Dynamics 365

## <a name="prerequisites-for-omnichannel-for-customer-service"></a>Prerequisiti per Multicanale per Customer Service

Come prerequisito, devi configurare la chat nel widget Amministrazione di Multicanale per Customer Service e ottenere alcuni dei parametri per configurare l'esperienza di chat di Commerce. Per istruzioni, vedi [Configurare un canale di chat](/dynamics365/customer-service/set-up-chat-widget).

Dopo aver configurato la chat nel widget Amministrazione di Multicanale per Customer Service, otterrai uno script simile all'esempio seguente.

`<script id="Microsoft_Omnichannel_LCWidget" src="https://oc-cdn-ocprod.azureedge.net/livechatwidget/scripts/LiveChatBootstrapper.js" data-app-id="xxxx-xxx-4be7-bcd5-1d118ecffe1f" data-org-id="5a0e73c0-xxxx-xxxxx-xxx- 76df135f375d" data-org-url="https://xxsxxxxssdb348f-crm.omnichannelengagementhub.com"></script>`

Copia questo script, in quanto avrai bisogno dei valori in esso contenuti per configurare il modulo chat.

### <a name="commerce-chat-with-omnichannel-for-customer-service-mandatory-fields"></a>Campi obbligatori di Chat di Commerce con Multicanale per Customer Service

La tabella seguente mostra i valori di script del widget Amministrazione di Multicanale per Customer Service necessari per configurare il modulo Chat di Commerce con Multicanale per Customer Service.

| Proprietà del widget | Description |
| ------------- |--------------|
| Origine script | Il valore di **src** nello script del widget di chat. |
| ID applicazione dati | Il valore di **data-app-id** nello script del widget di chat. |
| ID organizzazione dati | Il valore di **data-org-id** nello script del widget di chat. |
| URL organizzazione dati | Il valore di **data-org-url** nello script del widget di chat. |

## <a name="configure-the-commerce-chat-experience-for-your-e-commerce-site"></a>Configurare l'esperienza di chat di Commerce per il sito di e-commerce

Un modo consigliato per implementare l'esperienza di chat per il tuo sito di e-commerce consiste nell'aggiungere il modulo Chat di Commerce con Multicanale per Customer Service al frammento di intestazione condiviso utilizzato nelle pagine del tuo sito di e-commerce.

Per aggiungere il modulo di chat a un frammento di intestazione del tuo sito nel generatore di siti di Commerce, procedi come segue.

1. Nel generatore di siti per il tuo sito, vai a **Frammenti**.
1. Selezionare **Nuovo**.
1. Nella finestre di dialogo **Seleziona un frammento**, seleziona il modulo **Chat di Commerce con Multicanale per Customer Service**, immetti un nome per il frammento, quindi seleziona **OK**.
1. Nella vista struttura, seleziona lo slot **Msdyn365 cs chat connector**.
1. Nel riquadro **Proprietà chat** a destra, procedi nel seguente modo:

    1. Nel campo **Origine script**, immetti il valore **src** ottenuto dallo script di Multicanale per Customer Service.
    1. Nel campo **ID applicazione dati**, immetti il valore **data-app-id** ottenuto dallo script di Multicanale per Customer Service.
    1. Nel campo **ID organizzazione dati**, immetti il valore **data-org-id** ottenuto dallo script di Multicanale per Customer Service.
    1. Nel campo **URL organizzazione dati**, immetti il valore **data-org-url** ottenuto dallo script di Multicanale per Customer Service.

    ![Creazione di un frammento del modulo Chat di Commerce nel generatore di siti di Commerce.](media/Commerce-chat-creating-new-fragment.png)

1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.
1. Vai a **Frammenti** e apri il frammento di intestazione per il tuo sito.
1. Nello slot **Contenitore predefinito** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il frammento di chat creato in precedenza, quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="add-commerce-headquarters-as-an-application-tab-for-omnichannel-for-customer-service"></a>Aggiungere Commerce headquarters come scheda applicazione per Multicanale per Customer Service

Puoi aggiungere un scheda applicazione per Commerce headquarters in Multicanale per Customer Service. Gli agenti live possono quindi utilizzare l'interfaccia utente per l'esperienza agente di Multicanale per Customer Service per accedere facilmente al modulo Customer Service di Dynamics 365 Commerce che contiene informazioni contestuali per il cliente insieme alle informazioni sui relativi ordini cliente. Inoltre, gli agenti del servizio clienti possono effettuare nuovi ordini, avviare resi e verificare le informazioni sullo stato degli ordini.

### <a name="create-a-new-application-tab-that-loads-commerce-headquarters-in-an-iframe-module"></a>Creare una nuova scheda applicazione che carica Commerce headquarters in un modulo iFrame 

Per creare una nuova scheda applicazione che carica Commerce headquarters in un modulo iFrame, procedi come segue.

1. Apri [Power Apps Maker Portal](https://make.powerapps.com).
1. Nel riquadro di spostamento a sinistra, seleziona **App**.
1. Seleziona **Interfaccia di amministrazione di Customer Service**.
1. Vai a **Esperienza agente**.
1. Per **Modelli schede applicazione**, seleziona **Gestisci**.
1. Crea una nuova scheda applicazione di tipo **Sito web di terze parti**. Per istruzioni, vedi [Gestire modelli di schede applicazione](/dynamics365/app-profile-manager/application-tab-templates?tabs=customerserviceadmincenter).
1. Sotto **Parametri**, nel campo **Valore** del parametro **url**, immetti il seguente URL, dove `<YourOrganizationHeadquartersURL>` e `<LegalEntityname>` vengono sostituiti con valori appropriati. Il servizio clienti multicanale legge **{AccountNumber}** dal contesto della chat. Pertanto, lascia invariato **{AccountNumber}**.

    `https://<YourOrganizationHeadquartersURL>/?mi=MCRCustomerService&cmp=<LegalEntityName>&embedded=true&customerId={AccountNumber}`

1. Lascia vuoto il campo **Valore** del parametro **data**.

![Creazione di una scheda applicazione in Multicanale per Customer Service di Dynamics 365.](media/OC-CS-Admin-Application-Tab-Parameters.png)

## <a name="enable-a-new-application-tab-for-customer-agents-in-dynamics-365-omnichannel-for-customer-service"></a>Abilitare una nuova scheda applicazione per gli agenti dei clienti in Multicanale per Customer Service di Dynamics 365

Per abilitare una nuova scheda applicazione per gli agenti dei clienti in Multicanale per Customer Service di Dynamics 365, procedi come segue.
    
1. Apri [Power Apps Maker Portal](https://make.powerapps.com).
1. Nel riquadro di spostamento a sinistra, seleziona **App**.
1. Seleziona **Interfaccia di amministrazione di Customer Service**.
1. Vai a **Servizio Clienti \> Flussi di lavoro**.
1. Apri il flusso di lavoro che hai creato per i tuoi agenti, quindi sotto **Impostazioni avanzate**, seleziona **Sessioni predefinite**.
1. Sotto **Schede applicazione**, seleziona **Aggiungi scheda applicazione esistente**, quindi aggiungi la nuova scheda applicazione creata in precedenza. Questo passaggio garantisce la visualizzazione di una scheda applicazione che carica Commerce headquarters in un modulo iFrame quando un agente riceve una chiamata in chat dal tuo sito Web di e-commerce.

## <a name="add-context-variables-in-dynamics-365-omnichannel-for-customer-service"></a>Aggiungere variabili di contesto in Multicanale per Customer Service di Dynamics 365

Per aggiungere variabili di contesto in Multicanale per Customer Service di Dynamics 365, procedi come segue.

1. Apri [Power Apps Maker Portal](https://make.powerapps.com).
1. Nel riquadro di spostamento a sinistra, seleziona **App**.
1. Seleziona **Interfaccia di amministrazione di Customer Service**.
1. Vai a **Servizio Clienti \> Flussi di lavoro**.
1. Apri il flusso di lavoro che hai creato per i tuoi agenti, quindi sotto **Impostazioni avanzate**, vai alla sezione **Variabile di contesto**.
1. Seleziona **Modifica**, quindi aggiungi **AccountNumber** come variabile di contesto di tipo **testo**. Questa variabile consentirà a Commerce headquarters di caricare informazioni sui clienti con numeri di conto corrispondenti.

> [!NOTE]
> Se vuoi leggere gli indirizzi email e i nomi degli utenti che hanno effettuato l'accesso da un canale di e-commerce, puoi aggiungere **E-mail** e **Nome** come variabili di contesto di tipo **testo**, oltre alla variabile di contesto **AccountNumber**.
