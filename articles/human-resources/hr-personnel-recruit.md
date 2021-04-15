---
title: Selezionare i candidati a una posizione
description: Questo argomento mostra come selezionare i candidati in Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9259cfa78d65f36da653c807a66e291b3cb01c63
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802529"
---
# <a name="recruit-job-candidates"></a>Selezionare i candidati a una posizione

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Dynamics 365 Human Resources aiuta a gestire le richieste di selezione. Aiuta anche a passare senza problemi i candidati a una posizione come dipendenti. Se l'organizzazione utilizza un'applicazione di selezione separata, il processo di selezione potrebbe includere i seguenti passaggi:

- Immettere la richiesta di selezione in Human Resources.
- Ricevere le referenze dei candidati in Human Resources dall'applicazione di selezione.
- Completare il processo di approvazione del candidato in Human Resources.

Se non si sta utilizzando un'applicazione di selezione separata, è possibile anche gestire manualmente i candidati in Human Resources.

>[!NOTE]
>Se si è un amministratore o uno sviluppatore e si desidera integrare Human Resources con un'applicazione di selezione di terze parti, vedi [Configurare l'integrazione di Dataverse](hr-admin-integration-common-data-service.md) e [Configurare le tabelle virtuali di Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)
>
> È anche possibile trovare app di integrazione di selezione in [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).
>
> Per provare la nostra funzione di anteprima per l'integrazione con LinkedIn Talent Hub, vedere [Integrazione con LinkedIn Talent Hub](hr-admin-integration-linkedin.md).

## <a name="enable-recruiting-requests"></a>Abilita richieste di selezione

Se si desidera inviare richieste di selezione in Human Resources, è necessario prima abilitare la funzionalità in **Parametri condivisi delle risorse umane**.

1. Nell'area di lavoro **Gestione personale** selezionare **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Parametri condivisi di risorse umane**.

3. Nella scheda **Selezione** sotto **RECLUTAMENTO**, impostare **Abilita richieste di selezione** su **Sì**.

## <a name="add-a-recruiting-request-location"></a>Aggiungere una posizione per la richiesta di selezione

Se l'organizzazione ha più sedi, è possibile aggiungerle in modo che i richiedenti possano selezionare una posizione in cui lavorerà la nuova recluta. La posizione sarà inclusa nell'offerta di lavoro.

1. Nella barra di ricerca, inserire **posizione della richiesta di selezione**.

2. Selezionare **Nuovo**.

3. Nel campo **Posizione della richiesta di selezione** immettere il nome della posizione.

   ![Aggiungere una posizione per la richiesta di selezione](./media/hr-recruit-0a-add-location.png)

4. Nel campo **Descrizione** immettere una descrizione per la posizione.

5. Sotto **Posizione**, selezionare **Aggiungi**. Se il popout **Nuovo indirizzo** viene visualizzato, immettere l'indirizzo della posizione.

   ![Immettere indirizzo](./media/hr-recruit-0b-address.png)

6. In **Informazioni sui contatti**, inserire le informazioni per il contatto della posizione.

7. Selezionare **Salva**.

## <a name="add-a-recruiting-request"></a>Aggiungere una richiesta di selezione

I responsabili possono inviare richieste di selezione in Human Resources. Se si utilizza un'applicazione di selezione separata, il completamento di questi passaggi invierà una richiesta di selezione e avvierà il processo di selezione in tale applicazione. Altrimenti, completare questa procedura per iniziare il flusso di lavoro per il processo di selezione interno.

1. Selezionare **Self-service dipendenti**.

2. Selezionare la scheda **Team personale**.

3. Selezionare **Richiesta di selezione**.

   ![Avviare una richiesta di selezione](./media/hr-recruit-1-request-to-recruit.png)

4. Completare i campi **Descrizione**, **Lavoro** e **Data di inizio stimata**.

   ![Completare la richiesta di selezione](./media/hr-recruit-2-request-to-recruit.png)

5. Selezionare **Continua**. Viene visualizzata la richiesta di selezione per la posizione.

6. In **Generale**, selezionare un responsabile assunzioni dal menu a discesa **Responsabile assunzioni** quindi selezionare una posizione nel menu a discesa **Posizione richiesta di selezione**.

7. In **Lavoro**, modificare le informazioni in base alle esigenze, quindi selezionare **Crea dettagli dal lavoro**.

   ![Crea dettagli dalla mansione](./media/hr-recruit-3-create-details-from-job.png)

   Il resto della richiesta di selezione verrà compilato con le informazioni predefinite per il lavoro inserito.

8. In **Descrizione esterna**, inserire una descrizione del lavoro per l'esterno.

9. In **Posizioni**, selezionare **Aggiungi**, quindi selezionare una posizione per questa richiesta di selezione.

   ![Aggiungere una posizione](./media/hr-recruit-4-select-position.png)

10. In **Competenze**, selezionare **Aggiungi**, quindi selezionare una competenza.

11. In **Requisiti di istruzione**, selezionare **Aggiungi**, quindi selezionare i valori dai menu a discesa **Istruzione** e **Livello di istruzione**.

   ![Aggiungere i requisiti di istruzione](./media/hr-recruit-5-select-educational-requirements.png)

12. In **Commento**, aggiungere commenti se necessario.

13. In **Compensazione**, selezionare un livello dal menu a discesa **Livello** e quindi regolare **Soglia bassa**, **Punto di controllo**, e **Soglia alta** come necessario.

14. Quando la richiesta di selezione è completa e si è pronti per iniziare il processo di selezione, selezionare **Attiva** nella barra dei menu.

   ![Attivare la richiesta di selezione](./media/hr-recruit-6-activate-recruit-request.png)

15. Selezionare **Salva**.

## <a name="view-and-edit-your-recruiting-requests"></a>Visualizzare e modificare le richieste di selezione

Se si è un responsabile e si desidera visualizzare le richieste:

1. Selezionare **Self-service dipendenti**.

2. Selezionare la scheda **Team personale**.

3. In **Informazioni team personale**, selezionare la scheda **Richieste di selezione**.

   ![Selezionare la scheda Richieste di selezione](./media/hr-recruit-7-recruiting-requests.png)

4. Per visualizzare o modificare una richiesta di selezione, selezionarla nella griglia.

Se si è un professionista delle risorse umane e si desidera visualizzare tutte le richieste di selezione:

1. Selezionare **Gestione personale**.

2. Selezionare **Richieste di selezione**.

   ![Visualizzare le richieste di selezione in Gestione personale](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. Per visualizzare o modificare una richiesta di selezione, selezionarla nella griglia.

## <a name="add-or-edit-a-candidate-profile"></a>Aggiungere o modificare un profilo candidato

Se l'organizzazione è integrata con un'altra applicazione per gestire le richieste di selezione, le richieste di selezione vengono inoltrate a tale applicazione. L'applicazione di selezione invia quindi le informazioni sul candidato a Human Resources. Altrimenti, è possibile seguire i processi interni di selezione e inserire manualmente le informazioni sui candidati.

1. Selezionare **Gestione personale**.

2. Selezionare **Collegamenti**.

3. Sotto **Selezione**, selezionare **Candidati**.

   ![Visualizzare i candidati](./media/hr-recruit-9-candidates.png)

4. Per aggiungere un candidato, selezionare **Nuovo**. Per modificare un candidato esistente, selezionare il candidato dall'elenco, quindi selezionare **Modifica**. Viene visualizzato il profilo del candidato.

5. Sotto **Riepilogo candidato**, immettere o modificare le informazioni sul candidato secondo le necessità.

6. Sotto **Richiesta di selezione**, selezionare una richiesta di selezione a cui collegare il candidato. Quindi completare i campi **Data di inizio stimata**, **Responsabile assunzioni**, **Posizione** e **Descrizione** come appropriato.

   ![Collegare una richiesta di selezione](./media/hr-recruit-10-link-to-recruiting-request.png)

7. Completare tutte le informazioni nelle seguenti aree che si desidera includere nel record del candidato:
   - **Commenti**
   - **Esperienza professionale**
   - **Informazioni contatto**
   - **Percorso formativo**
   - **Competenze**
   - **Attestati**
   - **Screening**

8. Selezionare **Salva**.

## <a name="hire-a-candidate"></a>Assumere un candidato

Quando si è pronti per assumere un candidato, seguire questa procedura per passare il candidato a dipendente.

1. Nel modulo del candidato, selezionare **Assumi**.

   ![Assumere un candidato](./media/hr-recruit-11-hire.png)

2. Nel modulo **Assumi nuovo lavoratore** sotto **Dettagli**, completare tutti i campi.

   ![Inserire i dettagli della nuova assunzione](./media/hr-recruit-12-hire-new-worker.png)

3. Sotto **Dettagli posizione**, verificare e modificare le informazioni secondo le necessità.

4. Sotto **Elenchi di controllo per l'integrazione**, selezionare gli elenchi di controllo per l'integrazione pertinenti per questo dipendente.

5. Selezionare **Continua** per creare il record del dipendente.

   >[!NOTE]
   >A seconda dei flussi di lavoro dell'organizzazione, il record del candidato può essere sottoposto a ulteriori passaggi di approvazione prima di diventare un record del dipendente.

## <a name="decide-not-to-hire-a-candidate"></a>Decidere di non assumere un candidato

Se si decide di non assumere un candidato, seguire questa procedura per rimuoverlo dal processo di valutazione. 

1. Nel modulo del candidato, selezionare **Non assumere**.

   ![Non assumere un candidato](./media/hr-recruit-13-do-not-hire.png)

2. Selezionare un **Codice motivo** e includere eventuali commenti.

3. Selezionare **OK**.

## <a name="dismiss-a-candidate"></a>Licenziare un candidato

Se necessario, è possibile licenziare un candidato dopo averlo assunto. Ad esempio, un candidato potrebbe rifiutare l'offerta o non presentarsi il primo giorno.

- Nel modulo del candidato, selezionare **Licenzia candidato**.

  ![Chiudi il candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a>Vedere anche

[Configurare tabelle virtuali in Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[Organizzare la forza lavoro](hr-personnel-departments-jobs-positions.md)<br>
[Impostare i componenti di una mansione](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
