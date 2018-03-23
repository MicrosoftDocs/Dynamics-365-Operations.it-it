---
title: Gestire gli utenti di collaborazione fornitore
description: "In questo argomento viene descritto come è possibile richiedere il provisioning di nuovi utenti di collaborazione fornitore e come aggiungere nuovi contatti per la collaborazione fornitore."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: smmContactPerson, VendVendorContactPerson, VendVendorPortalUser
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 220744
ms.assetid: edc19ad0-3565-4d47-98ac-dda6098f63ac
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 80374d6dce8aa5d5f2e5afc0656b42236ac974ec
ms.openlocfilehash: 036e8079bd976087514a074529dd4593c5a2b0a5
ms.contentlocale: it-it
ms.lasthandoff: 03/13/2018

---

# <a name="manage-vendor-collaboration-users"></a>Gestire gli utenti di collaborazione fornitore

[!include[banner](../includes/banner.md)]


In questo argomento viene descritto come è possibile richiedere il provisioning di nuovi utenti di collaborazione fornitore e come aggiungere nuovi contatti per la collaborazione fornitore. 

L'interfaccia di collaborazione fornitore in Microsoft Dynamics 365 for Finance and Operations mostra informazioni sugli ordini fornitore, fatture e scorte di spedizione ai fornitori esterni. È possibile creare nuovi contatti per la collaborazione fornitore e richiedere il provisioning di nuovi  utenti se si lavora come fornitore esterno con il ruolo di sicurezza **Amministratore fornitore (esterno)** o simili autorizzazioni. È inoltre possibile eseguire queste attività se si lavora come responsabile di approvvigionamento. In questo argomento, questo ruolo si riferisce a un responsabile di approvvigionamento che lavora all'interno della società a cui appartiene l'istanza di Finance and Operations. Per ulteriori informazioni sull'utilizzo della collaborazione fornitore se si è un fornitore esterno, vedere [Collaborazione fornitore con i clienti](vendor-collaboration-work-customers-dynamics-365-operations.md).  

Per ulteriori informazioni sull'utilizzo della collaborazione fornitore se si è un responsabile approvvigioanmento, vedere [Collaborazione fornitore con i fornitori esterni](vendor-collaboration-work-external-vendors.md).

## <a name="add-new-vendor-collaboration-contacts"></a>Aggiungere nuovi contatti per la collaborazione fornitore
Se si desidera che un utente possa accedere alla collaborazione fornitore, questo deve innanzitutto essere aggiunto come contatto per la collaborazione fornitore. È inoltre possibile voler aggiungere contatti per i dipendenti della società che non utilizzeranno la collaborazione fornitore. Ad esempio, potrebbero essere il punto di contatto per altri tipi di informazioni di approvvigionamento. I nuovi contatti vengono aggiunti nella pagina **Tutti i contatti** a cui si accede dal menu **Collaborazione fornitore** &gt; **Contatti**. Per aggiungere un nuovo contatto:

1.  Fare clic su **Nuovo**.
2.  Immettere i dettagli del contatto primario.
3.  Scegliere quale persona giuridica rappresentano nella società e con quale persona giuridica lavoreranno nella società con cui collaboreranno. È possibile effettuare questa operazione selezionando una coppia **Persona giuridica nella società personale** /**Persona giuridica nella società cliente**.
4.  Fare clic su **Crea**.

Se si desidera eliminare un contatto, è solo possibile eliminare quelli che sono stati creati.

## <a name="vendor-collaboration-user-requests"></a>Richieste utente collaborazione fornitore
Le richieste di utente di collaborazione fornitore possono essere generate da un responsabile di approvvigionamento o da un amministratore del fornitore esterno.

-   Se si è un fornitore esterno, le richieste si inviano dalla pagina **Tutti i contatt** i  nel modulo **Collaborazione fornitore**.
-   Se si è un responsabile di approvvigionamento, le richieste si inviano dalla pagina **Visualizza contatto**. A tale scopo, nel record fornitore, nella sezione **Impostazione** del riquadro azioni, selezionare **Contatt** i&gt;  **Visualizza contatti**.

È possibile effettuare una richiesta di provisioning di un utente, di disattivazione di un utente o di modifica di ruoli di sicurezza. Se si è un amministratore di un fornitore esterno, è necessario essere registrati come contatto per i conti fornitore per cui si desidera effettuare richieste utente e si deve poter accedere all'interfaccia di collaborazione fornitore per tali conti fornitore.  

Quando una richiesta viene inviata viene aggiunta all'elenco **Richieste utente collaborazione fornitore** nel modulo **Collaborazione fornitore** e all'elenco **Richieste utente collaborazione fornitore** nel modulo **Approvvigionamento** (il modulo Approvvigionamento non è accessibile agli utenti esterni).

### <a name="provision-a-user"></a>Eseguire il provisioning di un utente

Prima di poter richiedere il provisoning di un nuovo utente, tale persona deve essere impostata come contatto per uno o più conti fornitore. Per creare una richiesta per un nuovo utente di collaborazione fornitore:

1.  Nella pagina **Tutti i contatti**, fare clic su **Provisioning utente fornitore**.
2.  Immettere un indirizzo di posta elettronica per l'utente. Questo indirizzo verrà utilizzato dall'utente per accedere a Finance and Operations. Se l'indirizzo di posta elettronica appartiene a un dominio registrato come tenant con Microsoft Azure, l'indirizzo di posta elettronica deve essere un account Azure Active Directory (AAD) esistente perché il processo di provisioning venga completato correttamente. Se l'indirizzo di posta elettronica non appartiene a un dominio registrato con Microsoft Azure, un account ADD verrà creato durante il processo di provisioning e il nuovo utente riceverà un invito per posta. Indirizzi di posta elettronica consumer con domini quali @hotmail.com, @gmail.com o @comcast.net non possono essere utilizzati per registrare un utente Finance and Operations.
3.  Impostare l'opzione **Accesso a collaborazione fornitore consentito** su **Sì** per tutte le persone giuridiche a cui l'utente deve accedere.
4.  Nella sezione **Assegna ruoli utente**, selezionare la casella di controllo **Assegna** per i ruoli di sicurezza che il nuovo utente deve avere.
5.  Fare clic su **Invia**.

Quando la richiesta di utente fornitore viene inviata, il campo **Accesso a collaborazione fornitore consentito** viene impostato su **Sì** per il conto fornitore selezionato e un flusso di lavoro di richiesta utente è avviato. Durante il flusso di lavoro, un nuovo utente viene creato in Finance and Operations e i ruoli di sicurezza vengono assegnati. Inoltre, un servizio Azure B2B viene attivato che avvia l'interazione con il portale di Azure e associa un account AAD nuovo o esistente con l'account utente Finance and Operations. Per ulteriori informazioni, vedere [Che cos'è la collaborazione B2B di Azure AD?](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b).

### <a name="inactivate-a-user"></a>Disattivare un utente

Sono disponibili due modi per rimuovere l'accesso alla collaborazione fornitore per un utente:

-   Nella pagina **Contatti** per il fornitore, impostare l'opzione **Accesso a collaborazione fornitore consentito** su **No** per il contatto. Questa operazione può essere effettuata singolarmente per persona giuridica di cui la persona è un contatto. Questa opzione può essere utilizzata solo dai responsabili di approvvigionamento.
-   Disattivare l'intero account utente, inviando una richiesta **Disattiva utente fornitore**.

Per richiedere la disattivazione di un utente;

1.  Nella pagina **Tutti i contatti**, fare clic su **Disattiva** **utente fornitore**.
2.  Scrivere un commento nel campo **Motivazione aziendale**.
3.  Fare clic su **Invia**.

### <a name="modify-security-roles"></a>Modificare i ruoli di sicurezza

La pagina **Gestisci ruoli utente fornitore** corrisponde  alla pagina **Provisioning utente fornitore** tranne che l'elenco dei ruoli di sicurezza può essere modificato.  

Per richiedere che i ruoli di sicurezza vengano modificati per un utente:

1.  Nella pagina **Tutti i contatti**, fare clic su **Gestisci** **ruoli utente fornitore**.
2.  Scrivere un commento nel campo **Motivazione aziendale**.
3.  Nella sezione **Gestisci ruoli utente**, selezionare i ruoli di sicurezza che si desidera assegnareo deselezionare quelli che si desidera rimuovere.
4.  Fare clic su **Invia**.





