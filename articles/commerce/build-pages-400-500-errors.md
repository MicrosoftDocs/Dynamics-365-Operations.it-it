---
title: Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx
description: In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.
author: v-chgri
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6b35b3c07b1edd41e6a3763c0001529e125e4636
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799651"
---
# <a name="build-custom-response-pages-for-4xx5xx-status-code-errors"></a>Creare pagine di risposta personalizzate per gli errori di codice stato 4xx/5xx

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come creare pagine di risposta personalizzate per errori di codice stato 4xx e 5xx utilizzando gli strumenti di creazione in Microsoft Dynamics 365 Commerce.

Se una richiesta non ha esito positivo, il server genera risposte per errori di codice stato HTTP. Il codice stato 404 viene acquisito e restituito se una pagina non è presente e il codice stato 500 viene acquisito e restituito in caso di errore nel server. In Dynamics 365 Commerce, gli utenti dell'applicazione possono creare pagine di risposte per errori di codice stato che sono visibili agli utenti per tali risposte.

## <a name="build-a-status-code-error-response-page"></a>Creare una pagina di risposte per errori di codice stato

Per iniziare a creare una pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Nel Web browser preferito, accedere a Dynamics 365 Commerce. 
1. Selezionare il sito per il quale si desidera creare una pagina di risposte per errori di codice stato 4xx/5xx.

### <a name="build-the-template"></a>Creare il modello

Per creare il modello per la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Andare a **Modelli**.
1. Selezionare **Nuovo** per creare un modello di pagina.
1. Nella finestra di dialogo **Nuovo modello**, sotto **Nome modello**, immettere un nome per il nuovo modello e selezionare **OK**.
1. Creare il modello in base alla struttura che la pagina di risposte per errori di codice stato deve avere.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare il modello, quindi selezionare **Pubblica** per pubblicarlo. 

### <a name="build-the-status-code-error-response-page"></a>Creare la pagina di risposte per errori di codice stato

Per creare la pagina di risposte per errori di codice stato, effettuare le seguenti operazioni.

1. Andare a **Pagine**.
1. Selezionare **Nuovo** per creare una pagina.
1. Nella finestra di dialogo **Scegli un modello**, selezionare un modello, quindi in **Nome pagina**, inserire un nome per la pagina di risposta dell'errore del codice di stato. Lasciare vuoto il campo **URL pagina**.
1. Creare la pagina.
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]
