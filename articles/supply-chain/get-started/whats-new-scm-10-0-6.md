---
title: Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)
description: Questo argomento descrive le funzionalità nuove o modificate in Dynamics 365 Supply Chain Management 10.0.6.
author: josaw1
manager: tfehr
ms.date: 10/28/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: 9ee25036488d2f7f24c1691d36239f3f34caf0cb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4431197"
---
# <a name="whats-new-or-changed-in-dynamics-365-supply-chain-management-1006-november-2019"></a>Novità o modifiche in Dynamics 365 Supply Chain Management 10.0.6 (novembre 2019)

[!include [banner](../includes/banner.md)]

Questo argomento descrive le funzionalità nuove o modificate di Microsoft Dynamics 365 Supply Chain Management 10.0.6. Questa versione ha il numero di build 10.0.234. Mentre la data di disponibilità generale è a novembre, le nuove funzionalità sono disponibili per la versione anticipata a ottobre. Per ulteriori informazioni sulla versione 10.0.6, veder [Risorse aggiuntive](whats-new-scm-10-0-6.md#additional-resources).

## <a name="product-configuration-models-v2-data-entity"></a>Entità di dati modelli di configurazione prodotto V2

Viene rilasciata una seconda versione per l'entità di dati "Modelli di configurazione prodotto" (denominata "Modelli di configurazione prodotto V2"). Il modello predefinito "Modelli di configurazione prodotto 418" deve essere tale da utilizzare l'entità dati "Modelli di configurazione prodotto V2" nei modelli di framework di importazione/esportazione. Il modello non verrà aggiornato automaticamente, quindi è necessario caricarlo manualmente dal valore predefinito. L'entità V2 esporta una riga come file separato in un allegato anziché in linea, risolvendo i limiti di dimensione dell'entità V1. 
 
Cosa è necessario fare per ottenere questo cambiamento?
-    Poiché l'entità V1 è stata deprecata, è necessario iniziare la migrazione da V1 a V2. Se si utilizza il modello "Modelli di configurazione prodotto 418", è possibile fare clic sul pulsante "Carica modelli predefiniti" e ricaricare il modello "418 - Modelli di configurazione del prodotto"
-    Se è necessario mantenere la compatibilità con i sistemi esistenti, per ora è possibile continuare a utilizzare il modello esistente e l'entità (deprecata) V1 fino a quando non si spostano le integrazioni nel nuovo modello. 

## <a name="feature-management-enhancements"></a>Miglioramenti di gestione delle funzionalità
La gestione delle funzionalità ora consente di abilitare tutte le nuove funzionalità per impostazione predefinita, richiedere la conferma per abilitare una funzionalità e abilitare tutte le funzionalità che non sono già state abilitate. 


## <a name="purchase-agreement-responsible-party"></a>Parte responsabile del contratto di acquisto
Ora è possibile definire le parti responsabili primarie e secondarie nel modulo di classificazione del contratto di acquisto e nei contratti di acquisto risultanti.  Ciò fornisce all'utente l'accesso a chi supervisiona i contatti.

## <a name="rfq-link-on-the-purchase-order-line"></a>Collegamento RdO nella riga ordine fornitore
È possibile aggiungere un collegamento di riferimento dalle righe dell'ordine fornitore alle righe RdO corrispondenti da cui hanno origine, consentendo all'utente di ricevere facilmente la richiesta di supporto per il documento di offerta.

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="bug-fixes"></a>Correzioni di bug
Per informazioni sulle correzioni di bug incluse in ciascuno degli aggiornamenti che fanno parte di 10.0.6, accedere a Lifecycle Services (LCS) e visualizzare l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=369581&dbType=3&qc=ba058110be40fe16a39469298041b1a7baf82eb65bb9df4d864602d2c6bf93d7).

### <a name="platform-update-30"></a>Update 30 della piattaforma
Microsoft Dynamics 365 Supply Chain Management 10.0.6 include l'aggiornamento della piattaforma 30. Per ulteriori informazioni sull'aggiornamento 30 della piattaforma, vedere [Novità o modifiche nell'aggiornamento 30 della piattaforma](../../fin-ops-core/fin-ops/get-started/whats-new-platform-update-30.md).

### <a name="dynamics-365-2019-release-wave-2-plan"></a>Piano di rilascio della seconda ondata 2019 di Dynamics 365
Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Consultare il [piano di rilascio della seconda ondata 2019 di Dynamics 365](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-supply-chain-management-features"></a>Funzionalità di Supply Chain Management rimosse e deprecate

L'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) descrive le funzionalità che sono state o sono pianificate per essere rimosse o deprecate per Supply Chain Management.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'argomento [Funzionalità rimosse o deprecate in Dynamics 365 Supply Chain Management](removed-deprecated-features-scm-updates.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]