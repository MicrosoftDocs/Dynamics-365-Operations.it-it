---
title: Anteprima di Dynamics 365 Commerce 10.0.29 (ottobre 2022)
description: Questo articolo descrive le funzionalità nuove o modificate in Microsoft Dynamics 365 Commerce 10.0.29.
author: josaw1
ms.date: 08/17/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2022-08-01
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 1e05f53f9ecb0a1994828172f6999a0bd5c208bc
ms.sourcegitcommit: f2175fe5e900d39f34167d671aab5074b09cc1b8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/17/2022
ms.locfileid: "9306234"
---
# <a name="preview-of-dynamics-365-commerce-10029-october-2022"></a>Anteprima di Dynamics 365 Commerce 10.0.29 (ottobre 2022)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Questo articolo elenca le funzionalità nuove o modificate nella versione di anteprima 10.0.29 di Microsoft Dynamics 365 Commerce. Questa versione ha il numero di build 10.0.1326 ed è disponibile con il seguente programma:

- **Anteprima della versione:** agosto 2022
- **Disponibilità generale della versione (aggiornamento automatico):** settembre 2022
- **Disponibilità generale della versione (aggiornamento automatico):** ottobre 2022

## <a name="features-included-in-this-release"></a>Funzionalità incluse in questa versione

Questa tabella elenca le funzionalità incluse in questa versione. Possiamo aggiornare questo articolo per includere le funzionalità che sono state aggiunte nella build dopo che questo articolo è stato inizialmente pubblicato.

| Area funzionale | Funzionalità | Ulteriori informazioni | Abilitato da |
|---------|------------------|----------------|--------------| 
| B2B | [Abilita supporto per contratto di vendita nei canali](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-b2b-sales-agreement-contract-based-pricing) | Questa funzionalità consente alle organizzazioni venditrici business-to-business (B2B) di utilizzare contratti di vendita in Commerce headquarters per definire i prezzi basati su contratto per i propri acquirenti. Quando un acquirente B2B effettua acquisti sul sito Web di e-commerce, i prezzi basati su contratto configurati per l'organizzazione acquirente B2B vengono automaticamente applicati all'intera esperienza di individuazione, acquisto e pagamento di prodotti. | Gestione funzionalità<p>*Supporto per contratto di vendita nei canali commerciali* |
| Customer Service | [Abilita servizio clienti con Multicanale per Customer Service di Dynamics 365](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/chat-dynamics-365-commerce-omnichannel-customer-service) | Un'esperienza di assistenza clienti di prim'ordine è la chiave per fornire un'esperienza commerciale personalizzata e piacevole ai consumatori. Esistono attualmente molteplici punti di contatto commerciali, come punti vendita fisici, canali online e canali social network. I consumatori si aspettano un'esperienza di supporto personalizzata in tutti questi punti di contatto. Questa funzionalità ti consente di aumentare le conversioni del carrello in vendite, di accrescere il coinvolgimento personalizzato con i consumatori e di migliorare il servizio clienti grazie all'integrazione con Multicanale per Customer Service di Dynamics 365. | Abilitata da amministratori/creatori |
| e-commerce | Supporto per il confronto dei prodotti nell'e-commerce | Consenti agli acquirenti di confrontare i prodotti in un'ampia gamma di categorie di modo che possano prendere personalmente la decisione di acquisto corretta. Questa funzionalità è disponibile per i siti business-to-consumer (B2C) e B2B. | Generatore di siti | 
| Gift card | Supporto per tabelle di gift card di prodotti al dettaglio per la condivisione di dati tra aziende | Commerce headquarters supporta la possibilità di abilitare la condivisione di dati tra aziende per specifiche tabelle nell'architettura di Dynamics. Con questa funzionalità, Dynamics 365 Commerce aggiunge supporto per la condivisione di dati tra aziende per le tabelle di gift card di prodotti al dettaglio. Pertanto, ora i dati di una gift card di un'azienda possono essere duplicati in un'altra azienda nell'ambiente. Le modifiche apportate alla tabella di gift card dell'azienda di origine verranno condivise nella tabella di gift card dell'azienda duplicata. | Sviluppatori |
| Globalizzazione | [Abilita le funzionalità di localizzazione di Commerce per il nuovo Commerce SDK](/dynamics365-release-plan/2022wave2/commerce/dynamics365-commerce/enable-commerce-localization-features-new-commerce-sdk) | La nuova funzionalità offre la possibilità di abilitare le funzionalità di localizzazione di Commerce da Commerce headquarters utilizzando il framework o i parametri di gestione delle funzionalità. Gli esempi di integrazione fiscale sono ora inclusi nel Commerce SDK e supportano gli imballaggi indipendenti. Questa funzionalità consente anche l'adozione dell'app Store Commerce da parte dei clienti globali di Commerce.<p><p>Questa versione include funzionalità di localizzazione di Commerce ed esempi di integrazione fiscale per [Austria](../localizations/emea-aut-fi-sample.md), [Repubblica Ceca](../localizations/emea-cze-fi-sample.md), [Francia](../localizations/emea-fra-cash-registers.md), [Germania](../localizations/emea-deu-fi-sample.md), [Italia](../localizations/emea-ita-fpi-sample.md), [Norvegia](../localizations/emea-nor-cash-registers.md) e [Polonia](../localizations/emea-pol-fpi-sample.md). | Abilitata da amministratori/creatori |
| Prestazioni | Rimuovi dipendenza RTS per scenari "modifica cliente" | Disponibilità elevata e prestazioni elevate sono aspettative basilari per i canali POS e di e-commerce. Per aiutare a soddisfare queste aspettative, i canali di Dynamics 365 Commerce non devono più fare affidamento sulla comunicazione in tempo reale con Commerce headquarters quando vengono modificate le informazioni sui clienti. La possibilità di modificare le informazioni sui clienti in modo asincrono per clienti asincroni e non asincroni può aiutare a ridurre le chiamate in tempo reale a Commerce headquarters. | Abilitata da amministratori/creatori |

## <a name="feature-state-changes-in-this-release"></a>Modifica allo stato della funzionalità in questa versione

Questa tabella elenca le funzionalità diventate obbligatore o attivate per impostazione predefinita nella versione 10.0.29. Tutte queste funzionalità verranno automaticamente attivate per il tuo sistema non appena esegui l'aggiornamento alla versione 10.0.29. Le funzionalità obbligatorie non possono essere disattivate, ma le funzionalità che sono attivate per impostazione predefinita possono comunque essere disattivate utilizzando [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

La tabella elenca anche le funzionalità che in precedenza erano in anteprima pubblica, ma che sono state modificate per diventare generalmente disponibili nella versione 10.0.29. Questa modifica indica che le funzionalità sono ora consigliate per l'uso in ambienti di produzione. Queste funzionalità sono disattivate per impostazione predefinita, salvo diversa indicazione. Di conseguenza, devi utilizzare [Gestione funzionalità](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) per abilitarle e utilizzarle.

| Funzionalità | Titolo | Nuovo stato funzionalità |
| --- | --- | --- |
| BrazilRetailLocalizationFeature_BR |(Brasile) Funzionalità di Commerce specifica per il Brasile | In base all'impostazione predefinita |
| RetailAdvancedGTETaxAdjustmentFeature | (India) Applica GST calcolata per le transazioni di vendita al dettaglio in Retail POS nei rendiconti della vendita al dettaglio | In base all'impostazione predefinita |
| RetailChronologicalInvoicePostingFeature_IT | (Italia) Abilita fatture al dettaglio registrate senza ordine cronologico | In base all'impostazione predefinita |
| RetailDiscountWithoutTaxAdjustingFeature_MX | (Messico) Rettifica sconto in CFDI vendita al dettaglio globale | In base all'impostazione predefinita |
| RetailFiscalIntegrationConfigurationEnhancementFeature | Sostituzioni profilo tecnico fiscale di integrazione fiscale | In base all'impostazione predefinita |
| RetailFiscalIntegrationConnectorLocationFeature | Integrazione fiscale diretta dai registri POS | In base all'impostazione predefinita |
| RetailFiscalIntegrationLocalStorageBackupEnableFeature | Backup archiviazione locale di integrazione fiscale | In base all'impostazione predefinita |
| RetailFiscalIntegrationPostponeFiscalRegistrationFeature | Registrazione posticipata dei documenti | In base all'impostazione predefinita |
| RetailFiscalIntegrationRegistrationProcessTerminalExceptionFeature | Stato della registrazione fiscale dei registri POS | In base all'impostazione predefinita |
| RetailGSTInvoiceAddressTaxCalculationFeature_IN | (India) Calcola l'imposta GST in base all'indirizzo fattura per gli ordini e-commerce | In base all'impostazione predefinita |
| RetailInvoicesDefaultSalesDocumentStatusFeature_PL | (Polonia) Stato del documento di vendita predefinito per le fatture di vendita al dettaglio | In base all'impostazione predefinita |
| RetailRecalculateRoundingOfTaxBaseAmountsFeature_MX | (Messico) Ricalcolo di arrotondamento per importi imponibili nella funzionalità globale CFDI per Retail. | In base all'impostazione predefinita |
| RetailSupplementaryInvoiceFeature | Abilitare le fatture supplementari per le transazioni cash-and-carry completate nei punti vendita al dettaglio | In base all'impostazione predefinita |
| RetailInventoryBufferAndInventoryLevelEnableFeature   |  Abilita buffer di magazzino e livelli di scorte    |  In base all'impostazione predefinita|
|RetailInboundOutboundInventoryValidationFeature|   Abilita convalida nelle operazioni di magazzino in entrata e in uscita POS   |   In base all'impostazione predefinita   |
|  RetailInventoryChannelCalculationConsolidationFeature    |  Logica di calcolo avanzata per l'inventario lato canale e-commerce |   In base all'impostazione predefinita   |
|RetailInventoryAdjustmentsInPointOfSaleFeature|    Rettifiche di inventario nel POS   |  In base all'impostazione predefinita  |
| RetailMultiplePickupDeliveryModeFeature |  Supporto per più modalità di consegna ritiro     |   Obbligatorio    |
|  RetailProductAvailabilityOptimizationFeature |   Calcolo disponibilità prodotto ottimizzata  |  Obbligatorio |
|   RetailPricingDataManagerV2Feature   |   Prestazioni migliorate per il motore dei prezzi di Commerce |   Obbligatorio |
|  RetailPricingPreventUnintendedRecalculationFeature   | Impedisci calcolo non intenzionale dei prezzi per ordini commerciali    |  Obbligatorio  |
| RetailTeamsIntegration    |   Abilita integrazione Microsoft Teams| Obbligatorio   |  
| ConsumerEFDSyncProcessFeature_BR | (Brasile) Elaborazione sincrona NFC-e | In base all'impostazione predefinita |
| RetailFiscalIntegrationInternalAndExternalServicesEnableFeature | Supporto per connettori interni ed esterni nel framework di integrazione fiscale | Obbligatorio |
| RetailTaxRegistrationIdEnableFeature_BR | (Brasile) Cerca clienti in Retail POS per partite IVA | Obbligatorio |
| RetailTaxRegistrationIdEnableFeature_IN | (India) Cerca clienti in Retail POS per partite IVA | Obbligatorio |
| RetailTaxRegistrationIdEnableFeature_IT | (Italia) Gestione informazioni cliente in Retail POS | Obbligatorio |
| RetailTaxRegistrationIdEnableFeature_PL | (Polonia) Gestione informazioni cliente in Retail POS | Obbligatorio |
| RetailUpdateReturnOriginalTransactionIdGlobalEnableFeature_IN | (GST vendita al dettaglio per India) Aggiorna note di accredito con riferimenti a fatture originali | Obbligatorio |
| RetailUserDefinedCertificateProfileFeature | Profili certificato definiti dall'utente per i punti vendita al dettaglio | Obbligatorio |
  

## <a name="additional-resources"></a>Risorse aggiuntive

### <a name="platform-updates-for-finance-and-operations-apps"></a>Aggiornamenti della piattaforma per app per finanza e operazioni

Microsoft Dynamics 365 Commerce 10.0.29 include gli aggiornamenti della piattaforma. Per ulteriori informazioni, vedi [Aggiornamenti della piattaforma per la versione 10.0.29 delle app per finanza e operazioni (ottobre 2022)](../../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-29.md). 

### <a name="bug-fixes"></a>Correzioni di bug

Per informazioni sulle correzioni di bug incluse in ognuno degli aggiornamenti che fanno parte della versione 10.0.29, accedi a Lifecycle Services (LCS) e visualizza l'[articolo KB](https://fix.lcs.dynamics.com/Issue/Details?bugId=726559&dbType=3&qc=ec3e3846199f5d3a27a0c4949e3902ffdbc87560f0cf928c4838b3bdd421633c). 

### <a name="dynamics-365-and-industry-clouds-2022-release-wave-2-plan"></a>Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022

Desideri sapere quali sono le funzionalità imminenti e rilasciate di recente nella nostra piattaforma o in una delle app aziendali?

Leggi [Dynamics 365 e cloud di settore: piano del secondo ciclo di rilascio del 2022](/dynamics365-release-plan/2022wave2/). Tutti i dettagli più completi sono stati raccolti in un unico documento utilizzabile per la pianificazione.

### <a name="removed-and-deprecated-features"></a>Funzionalità rimosse e deprecate

L'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) descrive le funzionalità che sono state rimosse o deprecate per Commerce.

- Una funzionalità *rimossa* non è più disponibile nel prodotto.
- Una funzionalità *deprecata* non si trova nella fase attiva di sviluppo e potrebbe essere rimossa in un aggiornamento futuro.

Prima che qualsiasi funzionalità venga rimossa dal prodotto, l'avviso di deprecazione verrà annunciato nell'articolo [Funzionalità rimosse o deprecate in Dynamics 365 Commerce](removed-deprecated-features-commerce.md) 12 mesi prima della rimozione.

Per le modifiche significative che influiscono solo sui tempi di compilazione, ma che sono binari compatibili con sandbox e ambienti di produzione, il tempo di deprecazione sarà inferiore a 12 mesi. In genere, si tratta di aggiornamenti funzionali che è necessario apportare al compilatore.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
