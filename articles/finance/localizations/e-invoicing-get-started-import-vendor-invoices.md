---
title: Utilizzare il servizio Fatturazione elettronica per importare fatture fornitore
description: Questo argomento fornisce informazioni su come importare fatture fornitore utilizzando il servizio Fatturazione elettronica.
author: gionoder
ms.date: 09/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f3b3a27436d32cf25d09f368e4a32018d7559bf6
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983825"
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
3. Sulla scheda **Canale dati** nel gruppo di campi **Parametri**, nel campo **Canale dati**, immettere il nome del canale. Il nome del canale non deve contenere più di dieci caratteri.
4. Nel campo **Indirizzo server**, immettere il provider dell'account di posta elettronica. Ad esempio, l'indirizzo del server per **https://outlook.live.com/** è **imap-mail.outlook.com**.
5. Nel campo **Porta server**, immettere la porta utilizzata dal provider dell'account di posta elettronica. Ad esempio, la porta del server per **https://outlook.live.com/** è **993**.
6. Nel campo **Segreto nome utente**, immettere il nome del segreto dell'insieme di credenziali delle chiavi che contiene l'ID dell'account utente di posta elettronica. Questo segreto deve essere creato nell'insieme di credenziali delle chiavi di Azure e configurato nell'ambiente del servizio. 
7. Nel campo **Segreto password utente**, immettere il nome del segreto dell'insieme di credenziali delle chiavi che contiene la password dell'account utente di posta elettronica.
8. Facoltativo - Immettere i valori nei campi **Filtro da**, **Filtro oggetto** e **Filtro data**.
9. Immettere i nomi delle cartelle della casella di posta in cui saranno presenti i messaggi:

    - Importato di: **Cartella principale**
    - Salvati dopo l'elaborazione riuscita: **Cartella di archivio**
    - Salvati dopo l'elaborazione non riuscita: **Cartella degli errori** Non è necessario creare queste cartelle nella casella di posta. Le cartelle vengono create automaticamente dopo l'importazione e l'elaborazione della prima fattura elettronica. 
   
10. Nel gruppo di campi **Filtro allegati**, aggiungere le informazioni sul filtro dei file. Vengono elaborati solo gli allegati che soddisfano il filtro definito. Ad esempio, è possibile impostare "\*.xml" per gli allegati con estensione xml. Il nome dell'allegato viene utilizzato in Dynamics 365 Finance o Dynamics 365 Supply Chain Management durante la configurazione. 
11. Nella scheda **Regole di applicabilità**, esaminare e aggiornare i criteri in base alle necessità. Il campo **Canale** deve essere uguale al **Canale dati** fornito in precedenza. Per ulteriori informazioni, vedi [Regole di applicabilità](e-invoicing-configuration-rcs.md#applicability-rules).
12. Selezionare **Salva**, quindi chiudere la pagina.

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

## <a name="set-up-vendor-invoice-import-in-finance-or-supply-chain-management"></a>Configurare l'importazione di fatture fornitore in Finance o Supply Chain Management
Completa i passaggi nelle due sezioni seguenti per configurare diversi tipi di importazione di fatture fornitore.

### <a name="import-brazilian-nf-e-from-email"></a>Importare NF-e brasiliana da messaggi e-mail

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
2. Selezionare **Modello contesto fattura cliente**, quindi **Crea configurazione** > **Deriva da Nome: modello di contesto fattura cliente, Microsoft** per creare una configurazione derivata.
3. Nella versione **Bozza**, selezionare **Progettazione** e nell'albero **Modello di dati**, selezionare **Mappa modello a origine dati**.
4. Nell'albero **Definizioni**, selezionare **DataChannel** e quindi selezionare **Progettazione**.
5. Nell'albero **Origine dati**, espandere il contenitore **$Context\_Channel**. Nel campo **Valore**, selezionare **Modifica** e immettere il nome del canale dati. Questo è il nome del canale specificato nella configurazione del canale dati per la funzionalità di Fatturazione elettronica in RCS. 
7. Selezionare **Salva**, quindi chiudere la pagina.
8. Chiudere la pagina.
9. Selezionare la configurazione derivata appena creata dal **Modello contesto fattura cliente** e, nella Scheda dettaglio **Versioni**, selezionare **Cambia stato** > **Completato**.
10. Vai a **Amministrazione organizzazione** > **Impostazione** > **Parametri documento elettronico** e nella scheda **Funzionalità** assicurati che sia selezionato **Fatture elettroniche globali PEPPOL**. 
11. Nella scheda **Canali esterni**, nel gruppo di campi **Canali**, seleziona **Aggiungi**.
12. Nel campo **Canale** immettere il nome del canale di dati e nel campo **Descrizione** immettere una descrizione.
13. Nel campo **Società**, selezionare la persona giuridica. 
14. Nel campo **Contesto documento**, selezionare la nuova configurazione derivata da **Modello contesto fattura cliente**. La descrizione del mapping dovrebbe essere **Contesto canale dati**.
15. Nel gruppo di campi **Importa origini**, seleziona **Aggiungi**.
16. Nel campo **Nome** immettere **Nome filtro allegati** e nel campo **Nome entità dati**, selezionare **Intestazione fattura fornitore**.
17. Nel campo **Mapping modello**, selezionare **Importazione fattura fornitore - Importa fattura fornitore**.
18. Fare clic su **Salva**, quindi chiudere la pagina.


## <a name="receive-electronic-invoices"></a>Ricevere fatture elettroniche

Il servizio di fatturazione elettronica esegue due passaggi durante l'importazione delle fatture dai canali di dati:

1. Accede alla casella di posta ed esegue la lettura dei messaggi e-mail.
2. Elabora i messaggi e-mail. 
    
Per eseguire questi due passaggi, il client deve chiamare il servizio manualmente per ogni passaggio. Tuttavia, si consiglia di impostare batch per la ricezione di documenti elettronici.

Per ricevere fatture elettroniche, procedi come segue:

1. Vai a **Amministrazione organizzazione** > **Periodico** > **Documenti elettronici** > **Ricevi documenti elettronici**.
2. Seleziona **OK**, quindi chiudi la pagina.


## <a name="view-receive-logs-for-electronic-invoices"></a>Visualizzare i registri di ricevimento di fatture elettroniche

Per visualizzare i registri di ricevimento di fatture elettroniche, vai a **Amministrazione organizzazione** > **Periodico** > **Documenti elettronici** > **Registro di ricevimento documenti elettronici**.
Se non sono visibili fatture elaborate correttamente, rimuovere il filtro della tabella.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
