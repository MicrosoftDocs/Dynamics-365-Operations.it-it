---
title: Modulo chat di Commerce con Power Virtual Agents
description: In questo articolo viene descritto il modulo chat di Commerce con Power Virtual Agents che integra Microsoft Power Virtual Agents con i siti Web di Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-09-07
ms.openlocfilehash: 838990cb638479c9c90ba0e38794ecedd55e95b3
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9691085"
---
# <a name="commerce-chat-with-power-virtual-agents-module"></a>Modulo chat di Commerce con Power Virtual Agents

[!include [banner](includes/banner.md)]

In questo articolo viene descritto il modulo chat di Commerce con Power Virtual Agents che integra Microsoft Power Virtual Agents con i siti Web di Dynamics 365 Commerce.

La funzionalità di chat di Commerce con Power Virtual Agents consente ai clienti di e-commerce di Dynamics 365 di utilizzare le funzionalità del chatbot di Power Virtual Agents per gestire le loro query. A partire da Dynamics 365 Commerce versione 10.0.30, questa funzionalità può essere incorporata nei siti di e-commerce utilizzando il modulo Chat di Commerce con Power Virtual Agents che fa parte della raccolta di moduli di Commerce.

La funzionalità Chat di Commerce con Power Virtual Agents aiuta le aziende a raggiungere i seguenti obiettivi:

- Aumentare l'interazione personalizzata con i loro clienti e migliorare la fidelizzazione degli stessi.
- Migliorare il servizio clienti attraverso l'integrazione di chatbot self-service.
- Migliorare la soddisfazione generale dei clienti e pertanto aumentare le vendite.

> [!NOTE]
> Per conoscere le differenze tra le applicazioni Multicanale per Customer Service di Dynamics 365 e Power Virtual Agents, vedi [Panoramica dei moduli della chat di Commerce](/commerce-chat-modules-overview.md).

## <a name="prerequisites-for-using-power-virtual-agents"></a><a id="prereq"></a>Prerequisiti per l'utilizzo di Power Virtual Agents

Per utilizzare la funzionalità di Chat di Commerce con Power Virtual Agents, devi prima creare un chatbot Power Virtual Agents per il tuo sito Web di e-commerce. Per istruzioni, vedi [Creare un bot dell'agente virtuale avanzato](/power-virtual-agents/authoring-first-bot).

Dopo aver configurato il chatbot, devi copiare i valori dei parametri del chatbot **ID bot** e **ID tenant** per configurare l'esperienza di chat di Commerce. Per informazioni su come copiare questi valori, vedi [Recuperare i parametri del tuo bot di Power Virtual Agents](/power-virtual-agents/publication-connect-bot-to-custom-application#retrieve-your-power-virtual-agents-bot-parameters).

## <a name="configure-your-e-commerce-site"></a>Configurare il sito di e-commerce 

Un modo consigliato per implementare l'esperienza di chat per il tuo sito di e-commerce consiste nell'aggiungere il modulo Chat di Commerce con Power Virtual Agents al frammento di intestazione condiviso utilizzato nelle pagine del tuo sito di e-commerce.

Per aggiungere il modulo di chat a un frammento di intestazione del tuo sito nel generatore di siti di Commerce, procedi come segue.

1. Nel generatore di siti di Commerce per il tuo sito, vai a **Frammenti**.
1. Selezionare **Nuovo**.
1. Nella finestre di dialogo **Seleziona un frammento**, seleziona il modulo **Chat di Commerce con Power Virtual Agents**, immetti un nome per il frammento, quindi seleziona **OK**.
1. Nella vista struttura, seleziona lo slot **Msdyn365 pva chat connector**.
1. Nel riquadro delle proprietà chat a destra, procedi nel seguente modo:

    1. In **Parametri del bot**, nel campo **URL della rete CDN della webchat Bot Framework**, lascia il valore predefinito (ad esempio, `https://cdn.botframework.com/botframework-webchat/latest/webchat.js`).
    1. Nel campo **URL di autenticazione Bot Framework Direct Line**, lascia il valore predefinito (ad esempio, `https://powerva.microsoft.com/api/botmanagement/v1/directline/directlinetoken`).
    1. Nel campo **ID bot**, immetti il valore **ID bot** di Power Virtual Agents che hai copiato nella sezione [Prerequisiti per l'utilizzo di Power Virtual Agents](#prereq).
    1. Nel campo **ID tenant**, immetti il valore **ID tenant** che hai copiato.

1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.
1. Vai a **Frammenti** e apri il frammento di intestazione per il tuo sito.
1. Nello slot **Contenitore predefinito** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi frammento**.
1. Nella finestra di dialogo **Seleziona moduli**, seleziona il frammento di chat creato in precedenza, quindi seleziona **OK**.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il frammento, quindi selezionare **Pubblica** per pubblicarlo.

## <a name="proactive-chat-parameters"></a>Parametri della chat proattiva

Per un elenco completo dei parametri di configurazione della chat proattiva, vedi [Parametri della chat proattiva del modulo di chat di Commerce](chat-proactive-chat-parameters.md).

> [!NOTE]
> Attualmente, Power Virtual Agents non supporta l'autenticazione di Azure Active Directory B2C (Azure AD B2C). Supporta solo le chiamate Retail Cloud Scale Unit (RCSU) anonime per ottenere la disponibilità del prodotto o interagire con altre API anonime. Le chiamate alle API autenticate tramite chatbot di Power Virtual Agents richiedono un accesso esplicito del cliente.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica delle funzionalità della chat di Commerce](commerce-chat-overview.md)

[Modulo Chat di Commerce con Multicanale per Customer Service](commerce-chat-module.md)

[Parametri della chat proattiva del modulo di chat di Commerce](chat-proactive-chat-parameters.md)
