---
title: Immettere le competenze
description: Lavori e manager possono inserire competenze in Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: c2a35079f43b92b5ff6d68aa7068f3e1f68ce8c2c32d23cdd22798f95c9a0ff4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732227"
---
# <a name="enter-skills"></a>Immettere le competenze

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

È possibile immettere le competenze di destinazione o le competenze effettive per i lavoratori, i candidati o i contatti in Dynamics 365 Human Resources. Una competenza prevista è una competenza che la persona intende raggiungere. Una competenza effettiva è una competenza che la persona ha attualmente.

## <a name="create-a-workflow-to-auto-approve-skills"></a>Creare un flusso di lavoro per l'approvazione automatica delle competenze

Per immettere le competenze senza richiedere l'approvazione, è necessario creare un flusso di lavoro per l'approvazione automatica delle competenze.

> [!NOTE]
> Le competenze inserite dai lavoratori richiedono sempre l'approvazione del responsabile. Questo flusso di lavoro approva automaticamente solo le competenze immesse dai manager per conto dei loro lavoratori.

1. Nell'area di lavoro **Gestione personale** selezionare **Collegamenti**.

2. Sotto **Impostazione**, selezionare **Flussi di lavoro risorse umane**.

3. Selezionare **Nuovo**.

4. Nel riquadro **Crea flusso di lavoro**, seleziona **Competenze lavoratore**.

   [![Selezionare il flusso di lavoro delle competenze del lavoratore.](media/hr-develop-skills-new-workflow.png)](media/hr-develop-skills-new-workflow.png)

5. Nella finestra di dialogo **Aprire questo file?**, seleziona **Apri**. Quando viene richiesto, immetti le credenziali.

6. Nell'editor del flusso di lavoro, seleziona l'elemento del flusso di lavoro **Approva competenze** e trascinalo nel canvas.

   [![Selezionare Approva elemento del flusso di lavoro delle competenze.](media/hr-develop-skills-element.png)](media/hr-develop-skills-element.png)

7. Connetti l'elemento **Inizio** all'elemento **Approva competenze 1**, quindi connetti l'elemento **Approva competenze 1** all'elemento **Fine**. Potrebbe essere necessario scorrere verso il basso per visualizzare l'elemento **Fine**. Puoi trascinarlo più vicino agli altri elementi.

   [![Connettere elementi del flusso di lavoro.](media/hr-develop-skills-connect-elements.png)](media/hr-develop-skills-connect-elements.png)

8. Fai doppio clic sull'elemento del flusso di lavoro **Approva competenze 1**, quindi fai clic con il pulsante destro del mouse sull'elemento **Passaggio 1**. Fare clic con il pulsante destro del mouse sull'elemento **Passaggio 1**, quindi scegliere **Proprietà**.

9. Nella finestra **Proprietà**, seleziona **Condizione** sulla barra di spostamento a sinistra.

10. Seleziona **Esegui questo passaggio solo quando è soddisfatta la seguente condizione**.

11. Seleziona **Aggiungi condizione**. Dopo **Dove**, seleziona **Competenze self-service dipendenti** e quindi seleziona **Employee self service skills.Person**. Dopo **è**, seleziona **campo** e quindi seleziona **User to person relationship.Person**.

    [![Specificare la condizione.](media/hr-develop-skills-condition.png)](media/hr-develop-skills-condition.png)

12. Seleziona **Assegnazione** sulla barra di spostamento a sinistra.

13. Nella scheda **Tipo di assegnazione**, seleziona **Gerarchia**.

14. Nella scheda **Selezione gerarchia**, nel campo **Tipo di gerarchia:**, seleziona **Gerarchia manageriale**.

    [![Specificare la gerarchia manageriale.](media/hr-develop-skills-hierarchy.png)](media/hr-develop-skills-hierarchy.png)

15. Seleziona **Chiudi**, seleziona **Flusso di lavoro** nel percorso del canvas, quindi seleziona **Salva e chiudi**.

Per ulteriori informazioni sulla creazione di flussi di lavoro, vedere [Panoramica del sistema del flusso di lavoro](../fin-ops-core/fin-ops/organization-administration/overview-workflow-system.md?toc=/dynamics365/human-resources/toc.json).

## <a name="enter-skills-for-a-worker"></a>Immettere le competenze per un lavoratore

1. Seleziona un lavoratore.

2. Nella barra delle azioni della pagina **Lavoratore**, seleziona **Persona** e quindi seleziona **Competenze**.

3. Nella pagia **Competenze**, completa i seguenti campi per ciascuna competenze:

   - **Competenza**: seleziona una competenza.
   - **Tipo di livello**: seleziona **Effettivo** per una competenza che il lavoratore possiede già, oppure seleziona **Target** per una competenza verso la quale il lavoratore sta lavorando.
   - **Livello**: seleziona un livello per la competenza del lavoratore.
   - **Data di livello**: seleziona una data nello strumento calendario.
   - **Esaminatore**: se appropriato, seleziona un esaminatore dall'elenco. Puoi filtrare la tua ricerca.
   - **Anni di esperienza**: inserisci gli anni di esperienza.
   - **Verificato**: se la competenza è verificata, seleziona la casella.
   - **Verificato da**: inserisci il nome del verificatore.

4. Quando hai finito di inserire le competenze, seleziona **Salva**.

## <a name="see-also"></a>Vedere anche

[Configurare le abilità](hr-develop-skills.md)<br>
[Mappare le competenze](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]