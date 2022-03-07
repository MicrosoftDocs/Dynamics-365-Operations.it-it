---
title: Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile
description: Questo argomento fornisce informazioni introduttive sul componente aggiuntivo per la fatturazione elettronica per il Brasile in Finance e Supply Chain Management.
author: gionoder
manager: AnnBe
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: eaf9433ad2d9ccf3d3c5632d0f2d4fe772ff8bde
ms.sourcegitcommit: 543772ee97efe215cf6f2ec6e092cc1568919f20
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "5592672"
---
# <a name="get-started-with-the-electronic-invoicing-add-on-for-brazil"></a>Introduzione al componente aggiuntivo per la fatturazione elettronica per il Brasile 

[!include [banner](../includes/banner.md)]

Questo argomento spiega come iniziare a usare il componente aggiuntivo per la fatturazione elettronica per il Brasile. Le procedure in questo argomento guida l'utente attraverso i passaggi di configurazione che dipendono dal paese in Regulatory Configuration Services (RCS) e completa i passaggi descritti nell'argomento [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica NF-e brasiliano (BR)

La configurazione della funzionalità di fatturazione elettronica NF-e brasiliano (BR) richiede il completamento di passaggi specifici. Alcuni dei parametri delle configurazioni sono pubblicati con valori predefiniti, quindi devono essere esaminati e aggiornati per adattarsi meglio alle operazioni aziendali.

### <a name="prerequisites"></a>Prerequisiti

Prima di completare la procedura in questa sezione, creare una funzionalità di fatturazione elettronica NF-e brasiliano (BR) per l'organizzazione, come descritto nella sezione **Crea una funzionalità di fatturazione elettronica nel provider dell'organizzazione** dell'argomento [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

1. In RCS, nella sezione **Funzionalità** dell'area di lavoro **Funzionalità di globalizzazione**, selezionare il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
2. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, verificare che la funzionalità di fatturazione elettronica **NF-e brasiliano (BR)** creata sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
4. Nella scheda **Impostazioni**, nella griglia, selezionare **Invia** e quindi **Modifica**.
5. Nella scheda **Azioni**, nel gruppo di campi **Azioni**, selezionare l'azione **(Anteprima) Firma documento xml**.
6. Nel gruppo di campi **Parametri**, selezionare **Nome certificato** e nel campo **Valore** immettere il nome del certificato associato al parametro dell'insieme di credenziali delle chiavi.
7. Nella scheda **Azioni**, nel gruppo di campi **Azioni**, selezionare l'azione **(Anteprima) Chiama servizio SEFAZ brasiliano**.
8. Nel gruppo di campi **Parametri**, selezionare il parametro **Indirizzo URL**.
9. Nel campo **Valore**, se necessario, esaminare e aggiornare l'URL dei servizi web pubblicati dalla documentazione SEFAZ per il proprio stato e quindi selezionare **Salva**.
10. Nella scheda **Regole di applicabilità**, nel gruppo di campi **Configurazione della regola di applicabilità**, esaminare e aggiornare il campo **Stato** come necessario per lo stesso stato a cui si riferisce l'URL dei servizi web.
11. Selezionare **Salva**, quindi chiudere la pagina.
12. Per configurare la configurazione dell'applicazione, vedere [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nf-e-br-electronic-invoicing-feature"></a>Configurazione specifica del paese dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica NF-e brasiliano (BR)

La configurazione dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica NF-e brasiliano (BR) richiede il completamento di passaggi specifici. Completare questi passaggi prima di distribuire la funzionalità di fatturazione elettronica nell'ambiente dei servizi del componente aggiuntivo per la fatturazione elettronica.

### <a name="prerequisites"></a>Prerequisiti

Prima di completare la procedura in questa sezione, creare e avviare la configurazione dell'applicazione della funzionalità di fatturazione elettronica NF-e brasiliano (BR), come descritto nella sezione **Configurare l'impostazione dell'applicazione** dell'argomento [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

1. In RCS, nella sezione **Funzionalità** dell'area di lavoro **Funzionalità di globalizzazione**, selezionare il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
2. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, verificare che la funzionalità di fatturazione elettronica **NF-e brasiliano (BR)** sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata.
4. Nella scheda **Impostazioni**, selezionare **Impostazione applicazioni** e nel campo **Applicazione connessa**, selezionare l'applicazione in cui si desidera eseguire la distribuzione.
5. Nel campo **Nome tabella**, verificare se l'opzione **Intestazione documento fiscale** è selezionata.
6. Selezionare **Tipi di risposta** e quindi **Nuovo**.
7. Nel campo **Tipo di risposta** immettere "Response" come valore fisso e nel campo **Descrizione**, immettere "Description".
8. Nel campo **Stato invio**, seleziona **In sospeso**.
9. Nel campo **Mapping modello**, selezionare **Mapping del modello dal messaggio di risposta** con **(Anteprima) Formato di importazione dei messaggi di risposta**, quindi selezionare **Salva**.
10. Selezionare **Nuovo** e nel campo **Tipo di risposta** immettere "ResponseData" come valore fisso e nel campo **Descrizione**, immettere "Description".
11. Nel campo **Stato invio**, seleziona **In sospeso**.
12. Nel campo **Mapping modello**, selezionare **Importazione dei dati di risposta** con **(Anteprima) Formato importazione dati di risposta NF-e (BR)**, quindi selezionare **Salva**.
13. Per distribuire la funzionalità di fatturazione elettronica, vedere [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configurazione specifica del paese per la funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR)

La configurazione della funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR) richiede il completamento di passaggi specifici. Alcuni dei parametri delle configurazioni sono pubblicati con valori predefiniti, quindi devono essere esaminati e aggiornati per adattarsi meglio alle operazioni aziendali.

### <a name="prerequisites"></a>Prerequisiti

Prima di completare la procedura in questa creazione, creare una funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR) nell'organizzazione. Ciò è descritto nella sezione **Configurare la funzionalità di fatturazione elettronica** nell'argomento,[Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

1. In RCS, nella sezione **Funzionalità** dell'area di lavoro **Funzionalità di globalizzazione**, selezionare il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
2. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, verificare che la funzionalità di fatturazione elettronica **Brasiliano NFS-e ABRASF Curitiba (BR)** creata sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata e nella scheda **Impostazioni**, nella griglia, selezionare **Invia**.
4. Selezionare **Modifica** e nella scheda **Azioni** nel gruppo di campi **Azioni**, selezionare la prima occorrenza di **(Anteprima) Firma documento xml**.
5. Nel gruppo di campi **Parametri**, selezionare **Nome certificato**.
6. Nel campo **Valore**, immettere il nome del certificato associato al parametro dell'insieme di credenziali delle chiavi.
7. Nel gruppo di campi **Azioni**, selezionare la seconda occorrenza di **(Anteprima) Firma documento xml**.
8. Nel gruppo di campi **Parametri**, selezionare **Nome certificato**.
9. Nel campo **Valore**, immettere il nome del certificato associato al parametro dell'insieme di credenziali delle chiavi.
10. Nella scheda **Azioni**, nel gruppo di campi **Azioni**, selezionare l'azione **(Anteprima) Chiama servizio SEFAZ brasiliano**.
11. Nel gruppo di campi **Parametri**, selezionare il parametro **Indirizzo URL**.
12. Nel campo **Valore**, se necessario, esaminare e aggiornare l'URL dei servizi web pubblicati dall'ufficio entrate della città di Curitiba e quindi selezionare **Salva**.
13. Nella scheda **Impostazioni**, nella griglia, selezionare **Richiedi informazioni** e quindi **Modifica**.
14. Nella scheda **Azioni**, nel gruppo di campi **Azioni**, selezionare l'azione **(Anteprima) Chiama servizio SEFAZ brasiliano**.
15. Nel gruppo di campi **Parametri**, selezionare il parametro **Indirizzo URL**.
16. Nel campo **Valore**, se necessario, esaminare e aggiornare l'URL dei servizi web pubblicati dall'ufficio entrate della città di Curitiba.
17. Selezionare **Salva**, quindi chiudere la pagina.
18. Per configurare la configurazione dell'applicazione, vedere [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

## <a name="country-specific-configuration-of-application-setup-for-brazilian-nfs-e-abrasf-curitiba-br-electronic-invoicing-feature"></a>Configurazione specifica del paese dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR)

La configurazione dell'impostazione dell'applicazione per la funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR) richiede il completamento di passaggi specifici prima di distribuire la funzionalità di fatturazione elettronica nell'ambiente di servizio del componente aggiuntivo per la fatturazione elettronica.

### <a name="prerequisites"></a>Prerequisiti

Prima di completare la procedura in questa sezione, creare e avviare la funzionalità di fatturazione elettronica Brasiliano NFS-e ABRASF Curitiba (BR), come descritto nella sezione **Configurare l'impostazione dell'applicazione** dell'argomento [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md).

1. In RCS, nella sezione **Funzionalità** dell'area di lavoro **Funzionalità di globalizzazione**, selezionare il riquadro **Componente aggiuntivo per la fatturazione elettronica**.
2. Nella pagina **Funzionalità del componente aggiuntivo per la fatturazione elettronica**, verificare che la funzionalità di fatturazione elettronica **Brasiliano NFS-e ABRASF Curitiba (BR)** sia selezionata.
3. Nella scheda **Versioni** verificare che la versione **Bozza** sia selezionata e nella scheda **Impostazioni**, selezionare **Impostazione applicazioni**.
4. Nel campo **Applicazione connessa**, selezionare l'applicazione in cui si desidera eseguire la distribuzione.
5. Nel campo **Nome tabella**, verificare che l'intestazione del documento fiscale sia selezionata.
6. Selezionare **Tipi di risposta** e quindi **Nuovo**.
7. Nel campo **Tipo di risposta** immettere "ABRASFCuritibaSubmitResponse" come valore fisso e nel campo **Descrizione**, immettere "Description".
8. Nel campo **Stato invio**, seleziona **In sospeso**.
9. Nel campo **Mapping modello**, selezionare **importazione dei messaggi di risposta** con **(Anteprima) Importazione di messaggi di risposta NFS-e ABRASF Curitiba (BR)**, quindi selezionare **Salva**.
10. Selezionare **Nuovo** e nel campo **Tipo di risposta** immettere "ABRASFCuritibaSubmitResponseData" come valore fisso e nel campo **Descrizione**, immettere "Description".
11. Nel campo **Stato invio**, seleziona **In sospeso**.
12. Nel campo **Mapping modello**, selezionare **Importazione dei dati di risposta** con **(Anteprima) Formato importazione dati di risposta NFS-e ABRASF (BR)**, quindi selezionare **Salva**.
13. Selezionare **Nuovo** e nel campo **Tipo di risposta** immettere "ABRASFCuritibaInquireResponse" come valore fisso e nel campo **Descrizione**, immettere "Description".
14. Nel campo **Stato invio**, seleziona **In sospeso**.
15. Nel campo **Mapping modello**, selezionare **Importazione dei messaggi di risposta** con **(Anteprima) Importazione di messaggi di risposta NFS-e ABRASF Curitiba (BR)**.
16. Selezionare **Salva** e ritornare all'argomento [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md) per distribuire la funzionalità di fatturazione elettronica.

## <a name="privacy-notice"></a>Informativa sulla privacy
L'abilitazione delle funzionalità **NF-e federale - Fattura elettronica brasiliana (BR)** e **NFS-e - Fattura elettronica del servizio brasiliano (città)** potrebbe richiedere l'invio di dati limitati, incluso l'ID registrazione fiscale dell'organizzazione. Questi dati vengono trasmessi ad agenzie di terze parti autorizzate dall'ufficio tributario allo scopo di inviare fatture elettroniche a questo ufficio tributario nel formato predefinito richiesto per l'integrazione con il servizio Web del governo. In veste di amministratore, è possibile abilitare o disattivare le funzionalità **NF-e federale - Fattura elettronica brasiliana (BR)** e **NFS-e - Fattura elettronica del servizio brasiliano (città)**. Per effettuare questa operazione, procedere come segue: 

1. Selezionare **Amministrazione organizzazione** > **Impostazione** > **Parametri documento elettronico**. 
2. Nella scheda **Funzionalità**, selezionare la riga che contiene la funzionalità **NF-e federale - Fattura elettronica brasiliana (BR)** o **NFS-e - Fattura elettronica del servizio brasiliano (città)** e selezionare la funzionalità. I dati importati da questi sistemi esterni in questo servizio online Dynamics 365 sono soggetti alla nostra [informativa sulla Privacy](https://go.microsoft.com/fwlink/?LinkId=512132). Consulta le sezioni dell'Informativa sulla privacy nella documentazione delle funzionalità specifiche del paese.

## <a name="additional-resources"></a>Risorse aggiuntive

- [Panoramica del componente aggiuntivo per la fatturazione elettronica](e-invoicing-service-overview.md)
- [Introduzione all'amministrazione dei servizi del componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started-service-administration.md)
- [Introduzione al componente aggiuntivo per la fatturazione elettronica](e-invoicing-get-started.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
