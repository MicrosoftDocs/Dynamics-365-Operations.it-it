---
title: Modifica informazioni personali
description: Questo articolo descrive come modificare le informazioni personali in Self service dipendenti e responsabile.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7e78873d0995334ac80ac22e8058b7fe0bc31ac
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686124"
---
# <a name="edit-personal-information"></a>Modifica informazioni personali


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile modificare le informazioni personali in Dynamics 365 Human Resources nell'area di lavoro **Self-service dipendenti**.

Le informazioni personali che è possibile modificare sono:

- Indirizzi
- Dettagli contatto
- Contatti personali
- Numeri di identificazione
- Metodo di pagamento
- Immagine utilizzata nelle risorse umane

>[!NOTE]
>È possibile che si sia in grado di modificare alcuni tipi di informazioni personali, come i dettagli di contatto aziendali. Per ulteriori informazioni, vedere [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md).

I parametri impostati nella pagina **Parametri rubrica globale** determinano quali ruoli possono visualizzare le informazioni personali.

1. In Risorse umane, selezionare **Self service dipendente**.

2. Selezionare **Modifica dettagli personali**.

3. Per cambiare l'indirizzo, selezionare la scheda **Indirizzi**. Le modifiche apportate vengono visualizzate nell'area di lavoro **Gestione personale** per avvisare le risorse umane.

    - Per aggiungere un nuovo indirizzo selezionare **Aggiungi**.
    - Per modificare un indirizzo esistente, selezionare l'indirizzo e quindi selezionare **Modifica**.
    - Per visualizzare una mappa, selezionare **Mappa**.
    - Per aggiungere o rimuovere un contatto, selezionare **Altre opzioni** e quindi selezionare **Avanzate**. In **Informazioni sul contatto** selezionare **Aggiungi** o **Rimuovi** e modificare i campi come necessario.
    - Per impostare il fuso orario e la posizione, selezionare **Altre opzioni** e quindi selezionare **Avanzate**. In **Generale**, modificare i campi come necessario.

4. Per modificare i dettagli del contatto, selezionare la scheda **Dettagli del contatto**. È possibile fornire diversi tipi di informazioni sul contatto, inclusi telefono, e-mail e collegamenti ai social media. È possibile impostare i dettagli di un contatto come primario, ma è possibile impostare solo uno di ogni tipo come primario.

    - Per aggiungere nuove informazioni sul contatto selezionare **Aggiungi**. Modificare i campi in base alle proprie esigenze.
    - Per modificare le informazioni di un contatto esistente, selezionare il contatto e quindi selezionare **Modifica**. Modificare i campi in base alle proprie esigenze.
    - Per impostare i dettagli di un contatto come privati, selezionare il contatto, selezionare **Avanzate**, quindi impostare l'interruttore **Privato** su **Sì**. Selezionare **OK**.
      >[!NOTE]
      >Il pulsante **Avanzate** non è disponibile se l'amministratore ha abilitato la funzionalità **(Anteprima) Impedire ai dipendenti di aggiungere o modificare l'indirizzo e le informazioni di contatto per determinati scopi** nell'ambiente. Per ulteriori informazioni, vedere [Impedire la modifica delle informazioni personali](hr-employee-self-service-restrict-editing.md).
  
5. Per modificare i contatti personali, selezionare la scheda **Contatti personali**. È possibile designare contatti di emergenza, beneficiari e persone a carico. Un contatto può essere una persona o un'organizzazione. La funzionalità **Gestione vantaggi** utilizza le informazioni sul contatto personali. Per ulteriori informazioni, vedere [Configurare le opzioni di idoneità del contatto personale](hr-benefits-setup-contact-eligibility-options.md).

6. Per modificare i numeri di identificazione, ad esempio il numero di previdenza sociale, selezionare la scheda **Numeri di identificazione**. Le modifiche potrebbero essere sottoposte a un processo di approvazione se l'organizzazione ha impostato un flusso di lavoro di approvazione.

    - Per aggiungere un numero di identificazione, selezionare **Nuovo**. Completare i campi come necessario e selezionare **Salva**.
    - Per modificare un numero, selezionare **Modifica**. Modificare i campi come necessario e selezionare **Salva**.

7. Per modificare i metodi con cui si viene pagati, selezionare la scheda **Informazioni di pagamento personali**. Questa scheda è disponibile solo se i metodi di pagamento sono abilitati nella pagina **Parametri risorse umane**. HR può abilitare **Assegno circolare**, **Contante**, **Assegno**, **Pagamento elettronico** o **Altro**. Le risorse umane possono anche disabilitare la convalida del pagamento elettronico (utilizzata per le retribuzioni negli Stati Uniti) e la convalida del conto bancario e del numero di registrazione.

8. Per modificare l'immagine visualizzata in Risorse umane per il profilo, selezionare la scheda **Immagine**. A seconda delle impostazioni dell'organizzazione, le immagini potrebbero essere instradate all'approvazione.

    - Per caricare un'immagine, selezionare **Carica nuova immagine**.
    - Per rimuovere un'immagine, selezionare l'immagine, quindi selezionare **Rimuovi**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
