---
title: Fatturazione elettronica per l'Egitto
description: Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per l'Egitto in Microsoft Dynamics 365 Finance e Dynamics 365 Supply Chain Management.
author: gionoder
ms.date: 02/09/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 6fe1dd4254db8b390c17558320a6eaff2b0dcd19
ms.sourcegitcommit: ffdb6794746ffe5461f9dcf34ed8e64976d22d2d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2022
ms.locfileid: "8371358"
---
# <a name="electronic-invoicing-for-egypt"></a>Fatturazione elettronica per l'Egitto

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per l'Egitto. Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Service (RCS). Questi passaggi completano i passaggi descritti in [Configurare la fatturazione elettronica](e-invoicing-set-up-overview.md).

## <a name="prerequisites"></a>Prerequisiti

Prima di iniziare le procedure in questo argomento, completa i seguenti prerequisiti:

- Acquisisci familiarità con la fatturazione elettronica come descritto in [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md).
- Iscriviti per RCS e configura la fatturazione elettronica. Per ulteriori informazioni, vedere gli argomenti seguenti:

    - [Iscriversi al servizio di fatturazione elettronica e installarlo](e-invoicing-sign-up-install.md)
    - [Impostare le risorse di Azure per la fatturazione elettronica](e-invoicing-set-up-azure-resources.md)
    - [Installa il componente aggiuntivo per microservizi in Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    
- Attiva l'integrazione tra l'applicazione Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management e il servizio di fatturazione elettronica come descritto in [Attivare e configurare l'integrazione con la fatturazione elettronica](e-invoicing-activate-setup-integration.md).
- Crea un segreto del certificato digitale in Azure Key Vault e configuralo come descritto in [Certificati e segreti del cliente](e-invoicing-customer-certificates-secrets.md). A scopo di test, l'ufficio tributario egiziano fornisce certificati digitali di test specifici che devono essere utilizzati solo durante le fasi di test e convalida della soluzione. Per ulteriori informazioni, vai al Web dell'ufficio tributario egiziano utilizzando il collegamento fornito in [SDK per la fatturazione elettronica per l'Egitto](https://sdk.sit.invoicing.eta.gov.eg/faq/).

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica egiziana

Alcuni dei parametri della **Fattura elettronica egiziana (EG)** vengono pubblicati con valori predefiniti. Prima di distribuire la funzionalità di fatturazione elettronica all'ambiente del servizio, rivedi i valori predefiniti e aggiornali in base alle esigenze in modo che riflettano meglio le operazioni aziendali.

1. Importa l'ultima versione della funzionalità di globalizzazione **Fattura elettronica egiziana (EG)** come descritto in [Importare funzionalità dal repository globale](e-invoicing-import-feature-global-repository.md).
2. Crea una copia della funzionalità di globalizzazione importata e seleziona il provider di configurazione per essa, come descritto in [Creare una funzione di globalizzazione](e-invoicing-create-new-globalization-feature.md).
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
4. Nella scheda **Configurazioni**, nella griglia, seleziona la configurazione della funzionalità **Fattura di vendita derivata**.
5. Seleziona **Modifica**.
6. Nella scheda **Pipeline di elaborazione**, nella sezione **Pipeline di elaborazione**, seleziona **Firma documento JSON per l'ufficio tributario egiziano**.
7. Nella sezione **Parametri**, seleziona **Nome certificato** e quindi seleziona il nome del certificato digitale creato.
8. Nella sezione **Processing pipeline**, seleziona **Integrazione con il servizio ETA egiziano**. Ripetere questo passaggio per le due occorrenze di questa azione.
9. Nella sezione **Parametri**, seleziona **URL servizio Web** e **URL servizio di accesso**. Quindi esamina i parametri URL. Per recuperare l'URL di test e produzione, vai al sito Web dell'ufficio tributario egiziano utilizzando il collegamento fornito in [SDK per la fatturazione elettronica per l'Egitto](https://sdk.sit.invoicing.eta.gov.eg/faq/).
10. Selezionare **Salva**, quindi chiudere la pagina.
11. Ripeti i passaggi da 4 a 10 per la configurazione della funzionalità **Fattura di progetto derivata**.

## <a name="country-specific-configuration-for-the-egyptian-electronic-invoice-eg-application-setup"></a>Configurazione specifica del paese per la configurazione dell'applicazione di fatturazione elettronica egiziana

Ci sono parametri che devono essere configurati nell'ambiente Finance o Supply Chain Management. Puoi completare questa configurazione in uno dei due modi seguenti:

- Direttamente nell'ambiente Finance o Supply Chain Management. Per altre informazioni, vedi [Impostare i parametri di fatturazione elettronica](e-invoicing-set-up-parameters.md).
- In RCS. Nell'ambito della configurazione della funzionalità di fatturazione elettronica, è possibile definire tutti i parametri e quindi distribuirli direttamente all'ambiente Finance o Supply Chain Management quando si distribuisce la funzione di fatturazione elettronica.

Per entrambe le opzioni, i parametri sono gli stessi. Se stai configurando la tua prima funzionalità nel servizio di fatturazione elettronica, ti consigliamo di seguire questi passaggi per impostare i parametri in RCS e quindi distribuirli alla tua applicazione connessa.

> [!NOTE]
> Alcune versioni delle funzioni di fatturazione elettronica potrebbero contenere un insieme predefinito di parametri specifici dell'applicazione per Finance o Supply Chain Management. In questo caso, è consigliabile verificare che i dati siano corretti. In caso contrario, imposta manualmente i parametri.

1. Trova la copia della funzionalità di globalizzazione **Fattura elettronica egiziana (EG)** che hai creato.
2. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
3. Nella scheda **Impostazioni**, selezionare **Impostazione applicazioni**.
4. Nel campo **Applicazioni connesse**, seleziona l'applicazione in cui vuoi distribuire i parametri.
5. Nella pagina **Tipi di documenti elettronici**, seleziona **Aggiungi** per creare un record.
6. Nel campo **Nome tabella**, aggiungi **CustInvoiceJour**.
7. Nel campo **Contesto**, aggiungi un riferimento al nome del mapping **Contesto fattura cliente**. La configurazione è **Modello contesto fattura cliente**.
8. Nel campo **Mapping documento elettronico**, aggiungi un riferimento al nome del mapping **Fattura cliente**. La configurazione è **Mapping modello di fattura**.
9. Seleziona **Salva**.
10. Nella pagina **Tipi di risposta** seleziona **Aggiungi**.
11. Nel campo **Tipo di risposta**, immetti **Risposta**.
12. Nel campo **Descrizione** immetti **Elabora risposta**.
13. Nel campo **Stato invio**, seleziona **In sospeso**.
14. Nel campo **Mapping modello**, seleziona **Importazione messaggio di risposta**. La configurazione è **Importazione del messaggio di risposta in Egitto (EG)**.
15. Seleziona **Salva**.
16. Seleziona **Aggiungi**.
17. Nel campo **Tipo di risposta**, immetti **ResponseData**.
18. Nel campo **Descrizione** immetti **Elabora dati risposta**.
19. Nel campo **Stato invio**, seleziona **In sospeso**.
20. Nel campo **Nome entità di dati**, seleziona **SalesInvoiceHeaderV2Entity**.
21. Nel campo **Mapping modello**, seleziona **Importazione dati risposta**. La configurazione è **Formato importazione dati risposta in Egitto (EG)**.
22. Selezionare **Salva**, quindi chiudere la pagina.
23. Chiudi la pagina.

Per distribuire una funzionalità nell'ambiente di servizio e una configurazione dell'applicazione nell'applicazione connessa Finance o Supply Chain Management, vedi [Completare, pubblicare e distribuire una funzionalità di globalizzazione](e-invoicing-complete-publish-deploy-globalization-feature.md)

## <a name="privacy-notice"></a>Informativa sulla privacy

L'abilitazione della funzionalità **Fattura elettronica egiziana** potrebbe richiedere l'invio di dati limitati. Questi dati includono l'ID di registrazione fiscale dell'organizzazione. Questi dati verranno trasmessi ad agenzie di terze parti autorizzate dall'ufficio tributario allo scopo di inviare fatture elettroniche a questo ufficio tributario nel formato predefinito richiesto per l'integrazione con il servizio Web del governo. Un amministratore può abilitare e disabilitare la funzionalità selezionando **Amministrazione organizzazione** \> **Impostazione** \> **Parametri del documento elettronico**. Nella scheda **Funzionalità**, selezionare la riga che contiene la funzionalità **Fattura elettronica egiziana (EG)**, quindi effettuare la selezione appropriata. I dati importati dai sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Per ulteriori informazioni consulta la sezione "Informativa sulla privacy" nella documentazione delle funzionalità specifiche del paese.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md)
- [Fatture elettroniche dei clienti in Egitto](emea-egy-e-invoices.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
