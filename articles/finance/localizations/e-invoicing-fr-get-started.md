---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per la Francia
description: Questo articolo fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per la Francia.
author: dkalyuzh
ms.date: 07/07/2022
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2022-00-02
ms.dyn365.ops.version: AX 10.0.29
ms.openlocfilehash: 3ac4af8c131e35d9a499d0d558c7cce1d4872b37
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573280"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-france"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica per la Francia

[!include [banner](../includes/banner.md)]

Questo articolo fornisce informazioni introduttive sulla fatturazione elettronica per la Francia. Ti guida attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Service (RCS). Questi passaggi completano quelli descritti in [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica Servizio di invio Chorus Pro francese (FR)

Sono necessari alcuni passaggi per configurare la funzionalità di fatturazione elettronica **Servizio di invio Chorus Pro francese (FR)**. Alcuni dei parametri della configurazione sono pubblicati con valori predefiniti. Questi valori devono essere esaminati e aggiornati di modo che riflettano meglio le operazioni aziendali.

### <a name="prerequisites"></a>Prerequisiti

Prima di iniziare le procedure in questo articolo, completa i seguenti prerequisiti:

- Acquisisci familiarità con la fatturazione elettronica. Per ulteriori informazioni, vedi [Panoramica della fatturazione elettronica](e-invoicing-service-overview.md).
- Iscriviti per RCS e configura la fatturazione elettronica. Per ulteriori informazioni, vedere gli articoli seguenti:

    - [Iscriversi al servizio di fatturazione elettronica e installarlo](e-invoicing-sign-up-install.md)
    - [Impostare le risorse di Azure per la fatturazione elettronica](e-invoicing-set-up-azure-resources.md)
    - [Installa il componente aggiuntivo per microservizi in Lifecycle Services](e-invoicing-install-add-in-microservices-lcs.md)
    - [Attivare e configurare l'integrazione con la fatturazione elettronica](e-invoicing-activate-setup-integration.md) - Utilizza le informazioni in questo articolo per attivare l'integrazione tra l'app Microsoft Dynamics 365 Finance o Dynamics 365 Supply Chain Management e il servizio di fatturazione elettronica.
    - [Codici NAF e numeri Siret](emea-fra-naf-codes-siret-numbers.md) e [Impostare codici NAF e numeri Siret](tasks/fr-00003-naf-codes-siret-numbers.md) – Utilizza le informazioni in questi articoli per impostare codici NAF e numeri Siret nelle tue persone giuridiche. 

- La tua organizzazione deve essere registrata per utilizzare Chorus Pro. Microsoft fornisce l'integrazione con Chorus Pro in modalità OAuth2 tramite un'API. Per informazioni dettagliate sulla registrazione a Chorus Pro e sull'attivazione dell'applicazione, consulta la [documentazione ufficiale](https://communaute.chorus-pro.gouv.fr/documentation/help-for-api-developers-in-oauth2-mode/).

    Procedi come segue per eseguire la registrazione a Chorus Pro.

    1. Vai [portale PISTE](https://piste.gouv.fr/en/component/apiportal/registration) per iniziare la registrazione. 
    2. Registra un'applicazione e attiva le credenziali di Open Authorization (OAuth).
    3. Copia e salva l'ID client delle credenziali OAuth e la chiave privata. Utilizzerai queste informazioni nei passaggi successivi.
    4. Vai al [portale Chorus Pro](https://portail.chorus-pro.gouv.fr/aife_csm/?id=aife_enrollment) per eseguire la registrazione. 
    5. Crea un account tecnico per l'accesso alle API. Per ulteriori informazioni, vedi [Creazione di un account tecnico per l'accesso alle API in produzione](https://communaute.chorus-pro.gouv.fr/documentation/creation-of-a-technical-account-for-an-api-access-in-production/).
    6. Copia l'ID utente dell'account tecnico e la password. Utilizzerai queste informazioni nei passaggi successivi.

## <a name="country-specific-configuration-of-the-application-setup-for-the-french-chorus-pro-submission-fr-electronic-invoicing-feature"></a>Configurazione specifica del paese dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica Servizio di invio Chorus Pro francese (FR)

Alcuni dei parametri della funzionalità di fatturazione elettronica **Servizio di invio Chorus Pro francese (FR)** vengono pubblicati con valori predefiniti. Prima di distribuire la funzionalità di fatturazione elettronica all'ambiente del servizio, esamina i valori predefiniti e aggiornali come necessario, di modo che riflettano meglio le operazioni aziendali.

1. In Azure Key Vault, crea segreti e il riferimento corrispondente. Per ulteriori informazioni, vedi [Certificati e segreti del cliente](e-invoicing-customer-certificates-secrets.md).
2. Importa l'ultima versione della funzionalità di globalizzazione **Servizio di invio Chorus Pro francese (FR)** come descritto in [Importare funzionalità dal repository globale](e-invoicing-import-feature-global-repository.md).
3. Crea una copia della funzionalità di globalizzazione importata e seleziona il provider di configurazione. Per ulteriori informazioni, vedi [Creare una funzionalità di globalizzazione](e-invoicing-create-new-globalization-feature.md).
4. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
5. Nella griglia della scheda **Configurazioni**, seleziona la configurazione della funzionalità **Fattura di vendita UBL derivata**.
6. Seleziona **Modifica** e nella scheda **Pipeline di elaborazione**, nella sezione **Pipeline di elaborazione**, seleziona **(Anteprima) Integrare con il servizio francese Chorus Pro** con il nome di azione **Invio Chorus Pro francese**.
7. Nella sezione **Parametri**, nel campo **Nome segreto dell'ID cliente**, seleziona il nome segreto che hai creato per l'ID client nell'insieme di credenziali delle chiavi.
8. Nel campo **Nome segreto del segreto client**, seleziona il nome segreto che hai creato per il segreto client nell'insieme di credenziali delle chiavi.
9. Nel campo **Nome segreto di accesso tecnico**, seleziona il nome segreto che hai creato per l'accesso all'account tecnico nell'insieme di credenziali delle chiavi.
10. Nel campo **Nome segreto della password tecnica**, seleziona il nome segreto che hai creato per la password dell'account tecnico nell'insieme di credenziali delle chiavi.
11. Nella scheda **Pipeline di elaborazione, nella sezione** **Pipeline di elaborazione**, seleziona **Integrare con il servizio francese Chorus Pro** con il nome di azione **Stato richiesta Chorus Pro francese**.
12. Nella sezione **Parametri**, nel campo **Nome segreto dell'ID cliente**, seleziona il nome segreto che hai creato per l'ID client nell'insieme di credenziali delle chiavi.
13. Nel campo **Nome segreto del segreto client**, seleziona il nome segreto che hai creato per il segreto client nell'insieme di credenziali delle chiavi.
14. Nel campo **Nome segreto di accesso tecnico**, seleziona il nome segreto che hai creato per l'accesso all'account tecnico nell'insieme di credenziali delle chiavi.
15. Nel campo **Nome segreto della password tecnica**, seleziona il nome segreto che hai creato per la password dell'account tecnico nell'insieme di credenziali delle chiavi.
16. Selezionare **Salva**, quindi chiudere la pagina.
17. Ripeti i passaggi da 6 a 16 per la configurazione delle funzionalità **Fattura progetto UBL derivata**, **Nota di accredito vendita UBL derivata** e **Nota di accredito di progetto UBL derivata**.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md)
