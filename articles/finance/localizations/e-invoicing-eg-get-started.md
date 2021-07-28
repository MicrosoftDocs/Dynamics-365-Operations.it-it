---
title: Introduzione alla fatturazione elettronica per l'Egitto
description: Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per l'Egitto in Finance e Supply Chain Management.
author: gionoder
ms.date: 04/20/2021
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
ms.openlocfilehash: 133c47d52bb301f862888c367d19fd58701ecb3c
ms.sourcegitcommit: 92ff867a06ed977268ffaa6cc5e58b9dc95306bd
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "6340131"
---
# <a name="get-started-with-electronic-invoicing-for-egypt"></a>Introduzione alla fatturazione elettronica per l'Egitto

[!include [banner](../includes/banner.md)]

Questo argomento fornisce informazioni introduttive sulla fatturazione elettronica per l'Egitto. Questo argomento guida l'utente attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e completa i passaggi descritti in [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica Fattura elettronica egiziana (EG)

Alcuni dei parametri della **Funzione di fatturazione elettronica per la fattura elettronica egiziana (EG)** vengono pubblicati con valori predefiniti. Rivedi i valori e, se necessario, aggiorna i valori per riflettere meglio le operazioni aziendali prima di distribuire la funzionalità di fatturazione elettronica nell'ambiente di servizio.

Questa sezione è a complemento della sezione **Configurazione specifica del paese per la funzionalità di fatturazione elettronica** nell'argomento [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

### <a name="prerequisites"></a>Prerequisiti

Prima di completare la procedura in questa sezione è necessario:

- Crea un segreto del certificato digitale, come descritto nella sezione **Creare un segreto del certificato digitale** in [Introduzione all'amministrazione del servizio per la fatturazione elettronica](e-invoicing-get-started-service-administration.md). A scopo di test, l'ufficio tributario egiziano fornisce certificati digitali di test specifici che devono essere utilizzati solo durante le fasi di test e convalida della soluzione. Per ulteriori informazioni, consulta il sito Web dell'ufficio tributario egiziano utilizzando il collegamento fornito in [SDK per la fatturazione elettronica per l'Egitto](https://sdk.sit.invoicing.eta.gov.eg/faq/).

1. In RCS, nell'area di lavoro **Funzionalità di globalizzazione** della sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
2. Nella pagina **Funzionalità della fatturazione elettronica**, verifica che la funzionalità di fatturazione elettronica **Fattura elettronica egiziana (EG)** creata sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
4. Nella scheda **Imposta**, nella griglia, selezionare la configurazione della funzionalità **Fattura di vendita**.
5. Selezionare **Modifica** e nella scheda **Azioni** nel gruppo di campi **Azioni**, selezionare **Firma documento JSON per ufficio tributario egiziano**.
6. Nel gruppo di campi **Parametri**, selezionare il parametro, **Nome certificato** e selezionare il nome del certificato digitale creato da utilizzare con la funzionalità Fatture elettroniche.
7. Nel gruppo di campi **Azioni**, selezionare **Integrazione con il servizio ETA egiziano**. Ripetere questo passaggio per le due occorrenze di questa azione.
8. Nel gruppo di campi **Parametri**, selezionare **URL servizio Web** e **Accesso URL servizio** e, se necessario, esaminare i parametri URL. Consultare il sito Web dell'ufficio tributario egiziano per ottenere l'URL di test e produzione, utilizzando il collegamento fornito in [SDK per la fatturazione elettronica per l'Egitto](https://sdk.sit.invoicing.eta.gov.eg/faq/).
9. Selezionare **Salva**, quindi chiudere la pagina.
10. Per distribuire la funzionalità di fatturazione elettronica all'ambiente del servizio, vedi [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-the-application-setup-for-the-egyptian-electronic-invoice-eg-electronic-invoicing-feature"></a>Configurazione specifica del paese dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica Fattura elettronica egiziana (EG)

Completa questi passaggi prima di distribuire la configurazione dell'applicazione nell'applicazione Finance o Supply Chain Management Connected.

Questa sezione è a complemento della sezione **Configurazione specifica del paese dell'impostazione dell'applicazione** nell'argomento [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

1. In RCS, nell'area di lavoro **Funzionalità di globalizzazione** della sezione **Funzionalità**, seleziona il riquadro **Fatturazione elettronica**.
2. Nella pagina **Funzionalità dela fatturazione elettronica**, verificare che la funzionalità di fatturazione elettronica **Fattura elettronica egiziana (EG)** sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
4. Nella scheda **Impostazioni**, selezionare **Impostazione applicazioni** e nel campo **Applicazione connessa**, selezionare l'applicazione in cui si desidera eseguire la distribuzione.
5. Nel campo **Nome tabella** verificare che il giornale di registrazione fatture cliente sia selezionato.
6. Selezionare **Tipi di risposta** e quindi **Nuovo**.
7. Nel campo **Tipo di risposta** immettere "Response" e nel campo **Descrizione**, immettere "Description".
8. Nel campo **Stato invio**, seleziona **In sospeso**.
9. Nel campo **Mapping modello**, selezionare **Mapping del modello dal messaggio di risposta** con **(Anteprima) Formato di importazione dei messaggi di risposta**, quindi selezionare **Salva**.
10. Selezionare **Nuovo**, quindi nel campo **Tipo di risposta**, immettere "ResponseData" come valore fisso. Nel campo **Descrizione** immettere "Description".
11. Nel campo **Stato invio**, seleziona **In sospeso**.
12. Nel campo **Nome entità di dati**, selezionare **Intestazioni fattura di vendita V2**.
13. Nel campo **Mapping modello**, selezionare **Importazione dati di risposta Egitto** con **(Anteprima) Importazione dati di risposta Egitto**, quindi selezionare **Salva**.
14. Per distribuire la configurazione dell'applicazione all'applicazione connessa Finance o Supply Chain Management, vedi [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md).

## <a name="privacy-notice"></a>Informativa sulla privacy

L'abilitazione della funzionalità **Fattura elettronica egiziana (EG)** potrebbe richiedere l'invio di dati limitati, incluso l'ID registrazione fiscale dell'organizzazione. Questi dati verranno trasmessi ad agenzie di terze parti autorizzate dall'ufficio tributario allo scopo di inviare fatture elettroniche a questo ufficio tributario nel formato predefinito richiesto per l'integrazione con il servizio Web del governo. Un amministratore può abilitare e disabilitare la funzionalità selezionando **Amministrazione organizzazione** > **Impostazione** > **Parametri del documento elettronico**. Nella scheda **Funzionalità**, selezionare la riga che contiene la funzionalità **Fattura elettronica egiziana (EG)**, quindi effettuare la selezione appropriata. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione alla fatturazione elettronica](e-invoicing-get-started.md)
- [Fatture elettroniche dei clienti in Egitto](emea-egy-e-invoices.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
