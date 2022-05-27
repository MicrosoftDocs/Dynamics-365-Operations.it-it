---
title: Integrazione con LinkedIn Talent Hub
description: In questo argomento viene descritto come impostare l'integrazione tra Microsoft Dynamics 365 Human Resources e LinkedIn Talent Hub.
author: jaredha
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d14a8cb1973e0ed55ef10ddb43415eba80eb5c1b
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8717113"
---
# <a name="integrate-with-linkedin-talent-hub"></a>Integrazione con LinkedIn Talent Hub

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

> [!IMPORTANT]
> L'integrazione tra Dynamics 365 Human Resources e LinkedIn Talent Hub descritta in questo argomento è stata ritirata il 31 dicembre 2021. Il servizio di integrazione non sarà più disponibile dopo tale data. Le organizzazioni che non utilizzano già il servizio di integrazione non potranno implementare il servizio prima del ritiro.

[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) è una piattaforma ATS (applicant tracking system). Consente di reperire, gestire e assumere dipendenti in un unico posto. Integrando Microsoft Dynamics 365 Human Resources con LinkedIn Talent Hub, è possibile creare facilmente i record dei dipendenti in Human Resources per i candidati che sono stati assunti per una posizione.

## <a name="setup"></a>Attrezzaggio

Un amministratore di sistema deve completare le attività di configurazione per abilitare l'integrazione con LinkedIn Talent Hub. Innanzitutto, nell'ambiente Power Apps, è necessario configurare un utente e un ruolo di sicurezza per concedere a LinkedIn Talent Hub le autorizzazioni appropriate per scrivere i dati in Human Resources.

### <a name="link-your-environment-to-linkedin-talent-hub"></a>Collegare l'ambiente a LinkedIn Talent Hub

1. Aprire [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).

2. Nel menu a discesa dell'utente, selezionare **Impostazioni del prodotto**.

3. Nel riquadro di spostamento a sinistra, nella sezione **Avanzate** selezionare **Integrazioni**.

4. Selezionare **Autorizza** per l'integrazione di Microsoft Dynamics 365 Human Resources.

5. Nella pagina **Dynamics 365 Human Resources** selezionare l'ambiente a cui collegare LinkedIn Talent Hub, quindi selezionare **Collega**.

    ![Onboarding di LinkedIn Talent Hub.](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > È possibile collegarsi solo ad ambienti in cui l'account utente dispone dell'accesso come amministratore sia all'ambiente Human Resources che a quello Power Apps associato. Se nessun ambiente è elencato nella pagina di collegamento di Human Resources, assicurarsi di disporre di ambienti Human Resources con licenza nel tenant e che l'utente che ha effettuato l'accesso alla pagina di collegamento disponga delle autorizzazioni di amministratore sia per l'ambiente Human Resources che per quello Power Apps.

### <a name="create-a-power-apps-security-role"></a>Creare un ruolo di sicurezza Power Apps

1. Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2. Nell'elenco **Ambienti** selezionare l'ambiente associato all'ambiente Human Resources a cui si desidera collegare l'istanza di LinkedIn Talent Hub.

3. Selezionare **Impostazioni**.

4. Espandere il nodo **Utenti + Autorizzazioni** e selezionare **Ruoli di sicurezza**.

5. Nella pagina **Ruoli di sicurezza** sulla barra degli strumenti selezionare **Nuovo ruolo**.

6. Nella scheda **Dettagli** immettere un nome per il ruolo, ad esempio **Integrazione HRIS LinkedIn Talent Hub**.

7. Nella scheda **Personalizzazione** selezionare l'autorizzazione **Lettura** del livello di organizzazione per le seguenti entità:

    - Entità
    - Campo
    - Rapporto

8. Salvare e chiudere il ruolo di sicurezza.

### <a name="create-a-power-apps-application-user"></a>Creare un utente dell'applicazione Power Apps

È necessario creare un utente dell'applicazione affinché l'adattatore LinkedIn Talent Hub conceda le autorizzazioni all'adattatore per scrivere i record dei candidati nell'ambiente Power Apps.

1. Apri l'[interfaccia di amministrazione di Power Platform](https://admin.powerplatform.microsoft.com).

2. Nell'elenco **Ambienti** selezionare l'ambiente associato all'ambiente Human Resources a cui si desidera collegare l'istanza di LinkedIn Talent Hub.

3. Selezionare **Impostazioni**.

4. Espandere il nodo **Utenti + Autorizzazioni** e selezionare **Utenti**.

5. Selezionare **Gestisci utenti in Dynamics 365**.

6. Utilizzare il menu a discesa sopra l'elenco per modificare la visualizzazione da quella predefinita **Utenti abilitati** a **Utenti dell'applicazione**.

    ![Visualizzazione Utenti di applicazioni.](./media/hr-admin-integration-power-apps-application-users.jpg)

7. Sulla barra degli strumenti selezionare **Nuovo**.

8. Nella pagina **Nuovo utente** effettuare i seguenti passaggi:

    1. Cambiare il valore del campo **Tipo di utente** su **Utente dell'applicazione**.
    2. Impostare il campo **Nome utente** su **Integrazione HRIS Dynamics365 HR LinkedIn**.
    3. Impostare il campo **ID applicazione** su **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    4. Immettere un valore nei campi **Nome**, **Cognome** e **Indirizzo di posta elettronica principale**.
    5. Nella barra degli strumenti selezionare **Salva \& chiudi**.

### <a name="assign-a-security-role-to-the-new-user"></a>Assegnare un ruolo di sicurezza al nuovo utente

Dopo aver salvato e chiuso il nuovo utente dell'applicazione nella sezione precedente, si torna alla pagina **Elenco utenti**.

1. Nella pagina **Elenco utenti** cambiare la visualizzazione in **Utenti dell'applicazione**.

2. Selezionare l'utente dell'applicazione creato nella sezione precedente.

3. Nella barra degli strumenti selezionare **Gestisci ruoli**.

4. Selezionare il ruolo di sicurezza creato in precedenza per l'integrazione.

5. Selezionare **OK**.

### <a name="add-an-azure-active-directory-app-in-human-resources"></a>Aggiungere un'app Azure Active Directory in Human Resources

1. In Dynamics 365 Human Resources, aprire la pagina **Applicazioni Azure Active Directory**.
2. Aggiungere un nuovo record all'elenco e impostare i seguenti campi:

    - **ID client**: immettere **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.
    - **Nome**: immettere il nome del ruolo di sicurezza Power Apps creato in precedenza, ad esempio **Integrazione HRIS LinkedIn Talent Hub**.
    - **ID utente**: selezionare un utente che dispone delle autorizzazioni per scrivere dati in Gestione del personale.

### <a name="create-the-table-in-dataverse"></a>Crea la tabella in Dataverse

> [!IMPORTANT]
> L'integrazione con LinkedIn Talent Hub dipende dalle tabelle virtuali in Dataverse per Human Resources. Come prerequisito per questo passaggio della configurazione, è necessario configurare le tabelle virtuali. Per informazioni su come configurare le tabelle virtuali, vedi [Configurare tabelle virtuali Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

1. In Human Resources, aprire la pagina **Integrazione di Dataverse**.

2. Selezionare la scheda **Tabelle virtuali**.

3. Filtrare l'elenco di entità in base all'etichetta di entità per trovare **Candidato esportato LinkedIn**.

4. Selezionare l'entità, quindi **Genera/Aggiorna**.

## <a name="exporting-candidate-records"></a>Esportazione dei record di candidato

Al termine della configurazione, i selezionatori e i professionisti di Human Resources (HR) possono utilizzare la funzione **Esporta in HRIS** in LinkedIn Talent Hub per esportare i record dei candidati assunti da LinkedIn Talent Hub in Human Resources.

### <a name="export-records-from-linkedin-talent-hub"></a>Esportare record da LinkedIn Talent Hub

Dopo che un candidato ha completato il processo di selezione ed è stato assunto, è possibile esportare il record del candidato da LinkedIn Talent Hub in Human Resources.

1. In LinkedIn Talent Hub, aprire il progetto per il quale è stato assunto il nuovo dipendente.

2. Selezionare un record di candidato.

3. Selezionare **Cambia fase**, quindi selezionare **Assunto**.

4. Nel menu con i puntini di sospensione (**...**) per il candidato, selezionare **Esporta in HRIS**.

5. Nel riquadro **Esporta in HRIS** immettere le informazioni che devono essere esportate:

    - Nel campo **Provider HRIS** selezionare **Microsoft Dynamics 365 Human Resources**.
    - Selezionare un valore per il nuovo dipendente nel campo **Data di inizio**.
    - Nel campo **Posizione lavorativa** immettere una posizione lavorativa per il nuovo dipendente.
    - Nel campo **Posizione** immettere la sede di lavoro del dipendente.
    - Immettere o verificare l'indirizzo e-mail del dipendente.

![Esportare nel riquadro HRIS in LinkedIn Talent Hub.](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a>Completare l'onboarding in Human Resources

I record dei candidati esportati da LinkedIn Talent Hub a Human Resources vengono visualizzati nella sezione **Candidati da assumere** della pagina **Gestione personale**.

1. In Human Resources, aprire la pagina **Gestione personale**.

2. Nella sezione **Candidati da assumere** selezionare **Assumi** per il candidato selezionato.

3. Nella finestra di dialogo **Assumi nuovo lavoratore** rivedere il record e aggiungere le informazioni richieste. È possibile anche selezionare il numero di posizione per cui il candidato è stato assunto.

Dopo aver immesso le informazioni richieste, è possibile continuare con i processi standard per la creazione dei record dei dipendenti e l'onboarding dei dipendenti.

I seguenti dettagli vengono importati e inclusi nel record del nuovo dipendente:

- Nome
- Cognome
- Data di inizio impiego
- Indirizzo di posta elettronica
- Numero di telefono

## <a name="see-also"></a>Vedere anche

[Configurare tabelle virtuali in Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Che cos'è Microsoft Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
