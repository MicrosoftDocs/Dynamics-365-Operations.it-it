---
title: Impedire la modifica delle informazioni personali
description: Impedire ai dipendenti di modificare i dettagli di contatto in Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/26/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EssWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 98cb7c2f1f57dacf303e2e9bc7779ce3ede6733e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8695874"
---
# <a name="restrict-editing-of-personal-information"></a>Impedire la modifica delle informazioni personali


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [applies to](../includes/applies-to-hr.md)]
[!include [preview feature](./includes/preview-feature.md)]

In questo argomento viene descritto come impedire ai dipendenti di modificare i dettagli di contatto in Dynamics 365 Human Resources. È possibile che si voglia impedire ai dipendenti di modificare determinati dettagli di contatto, come il loro indirizzo e-mail aziendale.

> [!NOTE]
> Per utilizzare questa funzionalità, è necessario dapprima abilitare **(Anteprima) Impedire ai dipendenti di aggiungere o modificare l'indirizzo e le informazioni di contatto per determinati scopi** in Gestione funzionalità. Per ulteriori informazioni sull'abilitazione delle funzionalità di anteprima, vedere [Gestire le funzionalità](hr-admin-manage-features.md).<br><br>![Abilitare la funzionalità di anteprima.](./media/hr-employee-self-service-restrict-enable.png)

## <a name="choose-the-information-an-employee-can-add-or-edit"></a>Scegliere le informazioni che un dipendente può aggiungere o modificare

1. In Human Resources, selezionare **Gestione dipendente**, Selezionare **Collegamenti**, quindi selezionare **Parametri Risorse umane**.

   ![Accedere a Parametri di Human Resources.](./media/hr-employee-self-service-human-resources-parameters.png)

2. Nella pagina **Parametri Risorse umane**, selezionare la scheda **Dipendente self-service**.

   ![Selezionare Self-service dipendenti.](./media/hr-employee-self-service-tab.png)

3. Nella scheda **Dipendente self service**, deselezionare tutte le informazioni nella sezione **Informazioni indirizzo e contatto** che i dipendenti non devono aggiungere o modificare. In questo esempio, abbiamo deselezionato le informazioni di contatto **Attività commerciale**.

   ![Impedire la modifica dell'informazione di contatto Attività commerciale.](./media/hr-employee-self-service-restrict-business.png)

4. Selezionare **Salva**.

   ![Salvare le modifiche.](./media/hr-employee-self-service-restrict-save.png)

## <a name="employee-experience"></a>Esperienza dei dipendenti

Dopo aver impedito ai dipendenti l'aggiunta o la modifica dei dettagli di contatto, questi possono vedere le informazioni, ma non possono modificarle.

In questo esempio, in cui ai dipendenti viene impedito di modificare i dettagli di contatto **Attività commerciale**, questi possono ancora vedere le informazioni in **Self-service dipendenti**:

![Visualizzare i dettagli di contatto aziendali.](./media/hr-employee-self-service-restrict-view.png)

Tuttavia, quando selezionano i dettagli di contatto aziendali, il riquadro **Modifica indirizzo** viene visualizzato come di sola lettura e non possono modificare alcun campo.

![Visualizzazione dei dettagli di contatto aziendali come di sola lettura.](./media/hr-employee-self-service-restrict-read-only.png)

Inoltre, se selezionano **Aggiungi** per aggiungere un nuovo indirizzo, non possono selezionare **Attività commerciale** nella casella a discesa **Scopo**.

![Il dipendente non può aggiungere un indirizzo aziendale.](./media/hr-employee-self-service-restrict-add.png)

La stessa cosa avviene quando i dipendenti selezionano **Dettagli contatto** nella pagina **Informazioni personali** e aggiungono un nuovo indirizzo. La casella a discesa **Scopo** mostra solo i tipi di informazioni che possono aggiungere. 

![Il dipendente non può selezionare Attività commerciale nella casella a discesa Scopo.](./media/hr-employee-self-service-restrict-purpose.png)

**Dettagli contatto** ora mostra **Scopo** nella griglia.

![Scopo visualizzato nella griglia Dettagli contatto.](./media/hr-employee-self-service-restrict-purpose-grid.png)

## <a name="see-also"></a>Vedere anche

[Panoramica del dipendente e del responsabile self-service](hr-employee-manager-self-service-overview.md)<br>
[Configurare i parametri di Human Resources](hr-setup-parameters.md)<br>
[Modifica informazioni personali](hr-employee-manager-self-service-edit-personal-information.md)
