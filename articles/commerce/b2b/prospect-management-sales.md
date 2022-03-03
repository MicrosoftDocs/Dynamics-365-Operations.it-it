---
title: Gestire utenti partner commerciali in siti Web di e-commerce B2B utilizzando Dynamics 365 Sales
description: Questo argomento descrive come utilizzare Microsoft Dynamics 365 Sales per gestire le approvazioni di partner commerciali per i siti Web di e-commerce business-to-business (B2B) di Dynamics 365 Commerce.
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: c6ac5409de5101c91b9348de800e3eaea9895c23
ms.sourcegitcommit: 4d52c67f52ad0add63cd905df61367b344389069
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/16/2022
ms.locfileid: "8312588"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Gestire utenti partner commerciali in siti Web di e-commerce B2B utilizzando Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

Questo argomento descrive come utilizzare Microsoft Dynamics 365 Sales per gestire le approvazioni di partner commerciali per i siti Web di e-commerce business-to-business (B2B) di Dynamics 365 Commerce. Le organizzazioni che hanno già investito nella soluzione Dynamics 365 Sales possono utilizzare i concetti di cliente potenziale e opportunità per il processo di approvazione di partner commerciali di e-commerce B2B.

Per informazioni di base sul processo di approvazione di partner commerciali B2B, vedi [Gestire utenti partner commerciali su siti Web di e-commerce B2B](manage-b2b-users.md).

I potenziali partner commerciali possono avviare il processo di onboarding a un sito Web di e-commerce B2B inviando una richiesta di onboarding tramite un collegamento nel sito Web B2B. Dopo che la richiesta è stata inviata e i processi pertinenti (come **P-0001** e **Sincronizza ordini e richieste di canale**) vengono eseguiti in Commerce headquarters, la richiesta di onboarding viene salvata nella pagina **Tutti i prospect** in Commerce headquarters. Il processo di approvazione di prospect partner commerciali possono quindi essere completato in Sales.

Dopo aver abilitato l'integrazione tra Sales e Commerce, la creazione di un prospect partner commerciale in Commerce provoca la creazione di un *cliente potenziale* in Sales.

L'illustrazione seguente mostra un esempio di una pagina di creazione di clienti potenziali per un prospect partner commerciale in Sales.

![Pagina di creazione di clienti potenziali in Dynamics 365 Sales.](../media/LeadInSales.png)

Nell'illustrazione, la sezione **Contatto** mostra la persona che ha presentato la richiesta di onboarding e la sezione **Società** mostra l'organizzazione. Una nota nella sezione **Sequenza temporale** indica che il cliente potenziale è stato generato dall'infrastruttura a doppia scrittura. Poiché è stato creato dall'infrastruttura a doppia scrittura, questo cliente potenziale non verrà visualizzato nell'elenco a discesa **Clienti potenziali aperti**. Apparirà invece in una nuova vista denominata **Tutti i clienti potenziali B2B di Commerce**.

In base al processo di qualifica standard di clienti potenziali in Sales, quando un utente "qualifica" il cliente potenziale, vengono creati un record *opportunità*, un record *contatto* e un record *account*. L'infrastruttura a doppia scrittura viene utilizzata per scrivere i record contatto e account in Commerce. Il contatto viene creato come cliente di tipo *persona* e l'azienda viene creata come cliente di tipo *organizzazione*. Se un utente seleziona **Chiudi come acquisito** per l'opportunità, il prospect è approvato in Commerce. L'approvazione di un prospect determina la creazione di una gerarchia clienti.

Tutti i processi aziendali rimanenti si verificano in Commerce. Questi processi includono l'invio di e-mail al partner commerciale, la definizione della gestione del limite di credito per gli utenti e l'aggiunta di più utenti al sito B2B. Tuttavia, se un utente annulla il cliente potenziale o contrassegna l'opportunità come persa anziché qualificare il lead, il prospect in Commerce viene contrassegnato come rifiutato e al richiedente viene inviata un'e-mail di rifiuto dell'onboarding.

## <a name="enable-integration-between-sales-and-commerce"></a>Abilitare l'integrazione di Sales e Commerce

L'integrazione di Sales e Commerce si basa sull'infrastruttura a doppia scrittura. Pertanto, la doppia scrittura deve essere abilitata e funzionante, di modo che i clienti creati in un sistema vengano scritti nell'altro sistema. Per ulteriori informazioni sull'infrastruttura a doppia scrittura, vedi [Panoramica della doppia scrittura](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Dopo che l'impostazione della doppia scrittura è stata completata, il partner di implementazione può accedere a [Microsoft AppSource](https://appsource.microsoft.com/) e cerca la soluzione denominata [Soluzioni Commerce a doppia scrittura](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Installa il pacchetto utilizzando la procedura guidata di installazione standard, quindi testalo creando un prospect in un sito B2B. Dopo la creazione del prospect, verifica che la richiesta sia visualizzata in **Tutti i prospect** in Commerce, quindi verifica che il prospect venga visualizzato come cliente potenziale in Sales.

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestire utenti partner commerciali in siti Web di e-commerce B2B](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
