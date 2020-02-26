---
title: Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx
description: In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4477a0a43971b5322c6acd6971cba2e79e2dc8c6
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001134"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx


[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

Se una richiesta non ha esito positivo, il server genera risposte per errori di codice stato HTTP. Il codice stato 404 viene acquisito e restituito se una pagina non è presente e il codice stato 500 viene acquisito e restituito in caso di errore nel server. In Dynamics 365 Commerce, gli utenti dell'applicazione possono creare pagine di risposte per errori di codice stato che sono visibili agli utenti per tali risposte.

## <a name="build-a-status-code-error-response-page"></a>Creare una pagina di risposte per errori di codice stato

Per iniziare a creare una pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Nel Web browser preferito, accedere a Dynamics 365 Commerce. 
1. Selezionare il sito per il quale si desidera creare una pagina di risposte per errori di codice stato 4xx/5xx.

### <a name="build-the-template"></a>Creare il modello

Per creare il modello per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Andare a **Modelli \> Nuovo modello**.
1. Assegnare un nome al nuovo modello.
1. Creare il modello in base alla struttura che la pagina di risposte per errori di codice stato deve avere.
1. Archiviare il modello e pubblicarlo.

### <a name="build-the-status-code-error-response-page"></a>Creare la pagina di risposte per errori di codice stato

Per creare la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Andare a **Pagine \> Nuova pagina**.
1. Assegnare un nome alla pagina di risposte per errori di codice stato, ma **non** impostare il campo **URL**.
1. Creare la pagina.
1. Archiviare la pagina e pubblicarla.

> [!NOTE]
> È possibile creare pagine di risposte per errori di codice stato 4xx e 5xx. In alternativa, è possibile utilizzare la stessa pagina di risposte per errori di codice stato per entrambe le categorie di errore.

### <a name="set-up-a-redirect-for-the-status-code-error-response-page"></a>Impostare un reindirizzamento per la pagina di risposte per errori di codice stato

Per impostare un reindirizzamento per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Andare a **URL \> Nuovo \> Nuovo alias** e selezionare la pagina di risposte per errori di codice stato creata in precedenza.
1. Nel campo **Alias**, immettere **default-4xx** o **default-5xx**, a seconda della pagina di risposte di errore di codice stato per la quale si sta impostando un reindirizzamento. Questi alias devono essere pubblicati. In caso contrario, il reindirizzamento non funzionerà.
1. Selezionare **OK** per eseguire il commit del collegamento.

> [!NOTE]
> Se si utilizza una singola pagina di risposte per errori di codice stato per entrambe le categorie di errore, ripetere questa procedura per collegare un alias per l'altra categoria di errore alla stessa pagina.

## <a name="additional-resources"></a>Risorse aggiuntive

[Utilizzare i modelli](work-with-templates.md)

[Aggiungere una nuova pagina del sito](add-new-page.md)

[Creare un URL di pagina](create-page-url.md)
