---
title: Impostazioni di amministrazione in Attract
description: "In questo argomento viene descritto come attivare funzionalità specifiche per le organizzazioni e gli utenti in Attract."
author: 
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: fb7b5e5b98ddb8e0e44fccbb0ddbb05199265414
ms.contentlocale: it-it
ms.lasthandoff: 12/07/2018

---

# <a name="admin-settings-in-attract"></a>Impostazioni di amministrazione in Attract
[!include[banner](../includes/banner.md)]

L'interfaccia di amministrazione di Microsoft Dynamics 365 for Talent: Attract contiene impostazioni di configurazione, opzioni di integrazione e opzioni di impostazione per l'applicazione Attract.

## <a name="company-information"></a>Informazioni sulla società

Immettere un nome visualizzato per la società e aggiungere un logo della società. Il Nome visualizzato e il logo possono quindi essere utilizzati nelle offerte di lavoro e nell'esperienza di inserimento.

## <a name="linkedin-integration"></a>Integrazione di LinkedIn

Impostare l'integrazione con LinkedIn Recruiter System Connect (RSC). Dopo avere effettuato la connessione a LinkedIn utilizzando le credenziali di LinkedIn, è possibile sincronizzare il profilo LinkedIn, le domande di lavoro, il riscontro sui colloqui e le note del team di assunzione relativi a un candidato. Una licenza completa di LinkedIn Recruiter è obbligatoria. Per ulteriori informazioni su LinkedIn Recruiter, vedere [Recruiter System Connect (RSC) - Domande frequenti](https://www.linkedin.com/help/recruiter/answer/90483).

## <a name="user-permissions"></a>Autorizzazioni utente

Assegnare ruoli agli utenti nell'organizzazione. I ruoli seguenti sono disponibili: **Amministratore**, **Selezionatore**, **Responsabile assunzioni** e **Sola lettura**. Per ulteriori informazioni su  autorizzazioni utente, vedere [Gestione della sicurezza e dei ruoli in Attract](./security-attract.md).

## <a name="feature-management"></a>Gestione funzionalità

Quando nuove funzionalità vengono aggiunte, potrebbero essere rilasciate in una versione di anteprima pubblica. Le funzionalità di anteprima pubblica non soddisfano tutti i requisiti del servizio. Ricevendole, si accetta di condividere i dati con sistemi esterni. È possibile che l'organizzazione non richieda tutte le nuove funzionalità che sono state rilasciate. È possibile attivare e disattivare le funzionalità di anteprima, a seconda delle esigenze dell'organizzazione.

## <a name="template-management"></a>Gestione modello

Un modello di processo contiene tutte le attività che devono essere incluse durante il processo di assunzione per una posizione lavorativa. L'organizzazione può consentire a tutti i membri del team o solo agli amministratori di creare modelli di processo di assunzione. Per consentire ai membri del team di creare i propri modelli di processo di assunzione, attivare la funzionalità Gestione modello. Per ulteriori informazioni sui modelli di processo, vedere [Modelli di processo in Attract](./process-templates-attract.md).

## <a name="email-template-settings"></a>Impostazioni del modello di messaggio di posta elettronica

Le organizzazioni possono creare modelli di messaggi di posta elettronica per diversi scenari. È possibile selezionare l'immagine di intestazione da includere nei modelli di messaggio di posta elettronica. L'intestazione selezionata verrà visualizzata in tutti i modelli di messaggio di posta elettronica. Nel piè di pagina del modello, è possibile aggiungere un collegamento alla Informativa sulla privacy dell'organizzazione e alle condizioni di utilizzo per le comunicazioni. Per ukteriori informazioni, vedere [Modelli di messaggio di posta elettronica in Attract](./email-templates.md).

## <a name="offer-process"></a>Processo di offerta

È possibile configurare il processo di approvazione per gli annunci di lavoro. Ad esempio, è possibile specificare se l'offerta deve essere approvata prima che venga inviata a un candidato. Puoi anche specificare che gli approvatori devono lasciare un commento con la decisione per l'offerta.

Due flussi di lavoro di approvazione sono disponibili: **Parallelo** e **Sequenziale**.

- **Parallelo** - Le approvazioni vengono inviate a tutti gli approvatori contemporaneamente.
- **Sequenziale** - le approvazioni vengono inviate agli approvatori in un ordine sequenziale specifico.

È inoltre possibile configurare le opzioni relative all'esperienza del candidato. Ad esempio, una opzione consente di specificare se i candidati possono rifiutare un'offerta senza ulteriore discussione. Se si imposta **Consentire ai candidati di rifiutare un'offerta senza discussione aggiuntiva** su **No**, il pulsante **Rifiuta offerta** è disponibile per i candidati. Se si imposta questa opzione su **Sì**, i candidati possono rifiutare l'offerta selezionando un motivo e quindi facendo clic su **Rifiuta offerta**.

È possibile anche impostare e applicare una data di scadenza per le offerte. Se si imposta **Richiedere una data di scadenza per tutte le offerte** su **Sì**, le offerte scadono dopo il numero di ore o di giorni specificato.

Per ulteriori informazioni sulla gestione delle offerte, vedere [Configurare la gestione delle offerte](./offer-setup.md).

