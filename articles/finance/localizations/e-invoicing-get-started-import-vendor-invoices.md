---
title: Utilizzare il servizio Fatturazione elettronica per importare fatture fornitore
description: Questo argomento fornisce informazioni su come importare fatture fornitore utilizzando il servizio Fatturazione elettronica.
author: gionoder
ms.date: 08/03/2021
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
ms.openlocfilehash: 434bf1f6a5a727a71592493b85ab166cbeff2f0980c2c968c99973a03f4dc660
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751254"
---
# <a name="use-the-electronic-invoicing-service-to-import-vendor-invoices"></a>Utilizzare il servizio Fatturazione elettronica per importare fatture fornitore

[!include [banner](../includes/banner.md)]

[!include [banner](../includes/preview-banner.md)]

Questo argomento fornisce informazioni introduttive sull'importazione di fatture fornitore mediante il servizio Fatturazione elettronica. L'argomento descrive i passaggi di configurazione in Regulatory Configuration Services (RCS), Dynamics 365 Finance e Dynamics 365 Supply Chain Management che devi seguire per ricevere fatture fornitore elettroniche dai fornitori.

## <a name="set-up-vendor-invoice-import-in-rcs"></a>Configurare l'importazione di fatture fornitore in RCS
Per configurare l'importazione di fatture fornitore in RCS, procedi come segue:

1. Consulta l'elenco delle [funzionalità di Fatturazione elettronica generalmente disponibili](e-invoicing-configuration-rcs.md#generally-available-features).
2. Seleziona e importa la funzionalità Fatturazione elettronica. Per ulteriori informazioni, vedi [Importare una funzionalità di Fatturazione elettronica dal provider di configurazioni Microsoft](e-invoicing-get-started.md#import-an-electronic-invoicing-feature-from-the-microsoft-configuration-provider)
3. Crea una funzionalità di Fatturazione elettronica per l'organizzazione. Per ulteriori informazioni, vedi [Creare una funzionalità di Fatturazione elettronica sotto il provider dell'organizzazione](e-invoicing-get-started.md#create-an-electronic-invoicing-feature-under-your-organization-provider)

## <a name="configure-an-email-account-channel"></a>Configurare un canale di account di posta elettronica

Configura un canale di account di posta elettronica se la funzionalità di Fatturazione elettronica creata importa fatture fornitore elettroniche da file allegati ricevuti tramite posta elettronica.

1. In RCS, seleziona la funzionalità di Fatturazione elettronica che hai creato. Assicurati di selezionare la versione con lo stato **Bozza**.
2. Nella scheda **Impostazioni**, nella griglia, seleziona un'impostazione di funzionalità e quindi seleziona **Modifica**.
3. Nella scheda **Canale dati** nel gruppo di campi **Parametri**, seleziona **Indirizzo server** e inserisci il provider dell'account di posta elettronica.
4. Seleziona **Porta server** e inserisci la porta utilizzata dal provider dell'account di posta elettronica.
5. Seleziona **Segreto nome utente** e immetti il nome del segreto dell'insieme di credenziali delle chiavi che contiene l'ID dell'account utente di posta elettronica.
6. Seleziona **Segreto password utente** e immetti il nome del segreto dell'insieme di credenziali delle chiavi che contiene la password dell'account utente di posta elettronica.
7. Seleziona **Filtro oggetto**. Esamina e aggiorna la stringa che contiene l'oggetto e-mail predefinito per identificare il messaggio e-mail che contiene la fattura fornitore elettronica da importare.
8. Nella scheda **Regole di applicabilità**, esamina e aggiorna i criteri se necessario. Per ulteriori informazioni, vedi [Regole di applicabilità](e-invoicing-configuration-rcs.md#applicability-rules).
9. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="configure-a-microsoft-sharepoint-channel"></a>Configurare un canale di Microsoft SharePoint

Configura un canale di Microsoft SharePoint se la funzionalità di Fatturazione elettronica importa fatture fornitore elettroniche da file in cartelle SharePoint.

1. In RCS, seleziona la funzionalità di Fatturazione elettronica che hai creato. Assicurati di aver selezionato la **Versione** con lo stato **Bozza**.
2. Nella scheda **Impostazioni**, nella griglia, seleziona un'impostazione di funzionalità e quindi seleziona **Modifica**.
3. Nella scheda **Canale dati** nel gruppo di campi **Parametri**, seleziona **Indirizzo SharePoint** e inserisci l'URL SharePoint.
4. Seleziona **Porta server** e inserisci la porta utilizzata dal provider dell'account di posta elettronica.
5. Seleziona **ID applicazione** e immetti il nome del segreto dell'insieme di credenziali delle chiavi che contiene l'ID del client SharePoint.
6. Seleziona **Segreto applicazione** e immetti il nome del segreto dell'insieme di credenziali delle chiavi che contiene la password del client SharePoint.
7. Seleziona **Filtro file**. Esamina e aggiornare la maschera per filtrare i file che contengono la fattura fornitore elettronica da importare.
8. Nella scheda **Regole di applicabilità**, esamina e aggiorna i criteri se necessario. Per ulteriori informazioni, vedi [Regole di applicabilità](e-invoicing-configuration-rcs.md#applicability-rules).
9. Seleziona **Salva**, quindi chiudi la pagina

### <a name="deploy-an-electronic-invoicing-feature"></a>Distribuire una funzionalità di Fatturazione elettronica

Per distribuire la funzionalità di Fatturazione elettronica, vedi [Distribuire la funzionalità di fatturazione elettronica nell'ambiente del servizio](e-invoicing-get-started.md#deploy-the-electronic-invoicing-feature-to-service-environment).

## <a name="set-up-vendor-invoice-import-in-finance-and-supply-chain-management"></a>Configurare l'importazione di fatture fornitore in Finance e Supply Chain Management
Completa i passaggi nelle due sezioni seguenti per configurare diversi tipi di importazione di fatture fornitore.

### <a name="import-vendor-invoices-from-email"></a>Importare fatture fornitore da messaggi e-mail

1. Accedi all'ambiente Finance o Supply Chain Management e verifica di essere nella persona giuridica corretta.
2. Selezionare **Amministrazione organizzazione** > **Impostazione** > **Parametri documento elettronico**.
3. Nella scheda **Funzionalità**, assicurati che sia selezionato **NF-e federale - Fattura elettronica brasiliana**.
4. Nella scheda **Canali esterni**, nel gruppo di campi **Canali**, seleziona **Aggiungi**.
5. Nel campo **Canale**, immetti **NFe** (il nome del canale specificato nella configurazione del canale dati per la funzionalità di Fatturazione elettronica in RCS).
6. Nel campo **Descrizione** immettere una descrizione. Nel campo **Società**, selezionare la persona giuridica.
7. Nel campo **Contesto documento**, seleziona **Modello di contesto fattura cliente - Contesto documento fiscale**.
8. Nel gruppo di campi **Importa origini**, seleziona **Aggiungi**.
9. Nel campo **Nome**, immetti **XmlFile** (il nome del **Filtro allegati** specificato nella configurazione del canale dati per la funzionalità di Fatturazione elettronica in RCS).
10. Nel campo **Descrizione**, inserisci una descrizione e nel campo **Nome entità dati**, seleziona **Documenti XML NF-e ricevuti**.
11. Nel campo **Mapping modello**, seleziona **Importazione e-mail NF-e – Importazione e-mail NF-e(BR)** quindi seleziona **Salva**.
12. Nella scheda **Documento elettronico**, nel gruppo di campi **Creazione di report elettronici** seleziona **Aggiungi** e nel campo **Nome tabella**, seleziona **Documento XML NF-e ricevuti**.
13. Nel campo **Contesto documento**, seleziona **Richiesta di informazioni su contesto documento fiscale - Contesto fattura cliente**.
14. Nel campo **Mapping del modello di documento elettronico**, seleziona **Richiesta di informazioni su mapping – Mapping documento fiscale**.
15. Selezionare **Tipi di risposta** e quindi **Nuovo**.
16. Nel campo **Tipo di risposta**, immetti **Risposta**. Nel campo **Stato invio**, immetti **Programmato**.
17. Nel campo **Mapping modello**, seleziona **Mapping del modello dal messaggio di risposta - Formato di importazione dei messaggi di risposta**.
18. Selezionare **Salva**, quindi chiudere la pagina.

### <a name="import-peppol-electronic-vendor-invoices"></a>Importare fatture fornitore elettroniche PEPPOL

1. Accedi all'area di lavoro **Creazione di report elettronici** e seleziona **Configurazioni creazione di report elettronici**.
2. Seleziona **Modello di contesto della fattura cliente** e crea una configurazione derivata.
3. Nella versione **Bozza**, seleziona **Progettazione**.
4. Nell'albero **Modello di dati**, seleziona **Fattura cliente**, quindi seleziona **Mappa modello a origine dati**.
5. Nell'albero **Definizioni**, seleziona **Fattura cliente** e quindi seleziona **Progettazione**.
6. Nell'albero **Origini dati** seleziona **Contesto\_Canale**. Nel campo **Valore**, seleziona **PEPPOL**. Questo è il nome del canale specificato nella configurazione del canale dati per la funzionalità di Fatturazione elettronica in RCS. 
7. Selezionare **Salva**, quindi chiudere la pagina.
8. Chiudere la pagina.
9. Seleziona **Modello di contesto della fattura cliente** e nella Scheda dettaglio **Versioni** seleziona **Cambia stato** > **Completato**.
10. Vai a **Amministrazione organizzazione** > **Impostazione** > **Parametri documento elettronico** e nella scheda **Funzionalità** assicurati che sia selezionato **Fatture elettroniche globali PEPPOL**. 
11. Nella scheda **Canali esterni**, nel gruppo di campi **Canali**, seleziona **Aggiungi**.
12. Nel campo **Canale**, immetti **PEPPOL**. Nel campo **Descrizione** immettere una descrizione.
13. Nel campo **Società**, selezionare la persona giuridica. Nel campo **Contesto documento**, seleziona **Modello di contesto della fattura cliente - Contesto della fattura cliente**.
14. Selezionare **Salva**, quindi chiudere la pagina.


## <a name="receive-electronic-invoices"></a>Ricevere fatture elettroniche
Per ricevere fatture elettroniche, procedi come segue:

1. Vai a **Amministrazione organizzazione** > **Periodico** > **Documenti elettronici** > **Ricevi documenti elettronici**.
2. Seleziona **OK**, quindi chiudi la pagina.

## <a name="view-receive-logs-for-electronic-invoices"></a>Visualizzare i registri di ricevimento di fatture elettroniche

Per visualizzare i registri di ricevimento di fatture elettroniche, vai a **Amministrazione organizzazione** > **Periodico** > **Documenti elettronici** > **Registro di ricevimento documenti elettronici**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
