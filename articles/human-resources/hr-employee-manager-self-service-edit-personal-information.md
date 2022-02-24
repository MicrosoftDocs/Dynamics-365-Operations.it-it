---
title: Modifica informazioni personali
description: Questo articolo descrive come modificare le informazioni personali nel self service dipendente e manager.
author: andreabichsel
manager: AnnBe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Human Resources
ms.custom: 51941
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0158bd4ee74e24006e338c0477ee0ac4210b1bf5
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/13/2020
ms.locfileid: "4419124"
---
# <a name="edit-personal-information"></a>Modifica informazioni personali

È possibile modificare le informazioni personali in Dynamics 365 Human Resources nell'**area di lavoro self-service dipendente**.

Le informazioni personali che è possibile modificare sono:

- Indirizzi
- Dettagli contatto
- Contatti personali
- Numeri di identificazione
- Metodo di pagamento
- Immagine utilizzata nelle risorse umane

I parametri impostati nella rubrica globale determinano i ruoli che possono visualizzare le informazioni personali.

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
  
5. Per modificare i contatti personali, selezionare la scheda **Contatti personali**. È possibile designare contatti di emergenza, beneficiari e persone a carico. Un contatto può essere una persona o un'organizzazione. La funzionalità **Gestione vantaggi** utilizza le informazioni sul contatto personali. Per ulteriori informazioni, vedere [Configurare le opzioni di idoneità del contatto personale](hr-benefits-setup-contact-eligibility-options.md).

6. Per modificare i numeri di identificazione, ad esempio il numero di previdenza sociale, selezionare la scheda **Numeri di identificazione**. Le modifiche potrebbero essere sottoposte a un processo di approvazione se l'organizzazione ha impostato un flusso di lavoro di approvazione.

    - Per aggiungere un numero di identificazione, selezionare **Nuovo**. Completare i campi come necessario e selezionare **Salva**.
    - Per modificare un numero, selezionare **Modifica**. Modificare i campi come necessario e selezionare **Salva**.

7. Per modificare i metodi con cui si viene pagati, selezionare la scheda **Informazioni di pagamento personali**. Questa scheda è disponibile solo se i metodi di pagamento sono abilitati nel modulo **Parametri risorse umane**. HR può abilitare **Assegno circolare**, **Contante**, **Assegno**, **Pagamento elettronico** o **Altro**. Le risorse umane possono anche disabilitare la convalida del pagamento elettronico (utilizzata per le retribuzioni negli Stati Uniti) e la convalida del conto bancario e del numero di registrazione.

8. Per modificare l'immagine visualizzata in Risorse umane per il profilo, selezionare la scheda **Immagine**. A seconda delle impostazioni dell'organizzazione, le immagini potrebbero essere instradate all'approvazione.

    - Per caricare un'immagine, selezionare **Carica nuova immagine**.
    - Per rimuovere un'immagine, selezionare l'immagine, quindi selezionare **Rimuovi**.

