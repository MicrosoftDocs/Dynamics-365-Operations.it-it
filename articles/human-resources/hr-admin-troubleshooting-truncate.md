---
title: Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio
description: Questo argomento spiega come risolvere il problema dei nomi troncati degli individui e delle posizioni nella gerarchia delle posizioni in Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a9a8d22df0416ef417a6216c3131bfb6d40d200
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413537"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Uscita**

Quando un cliente visualizza la gerarchia posizioni in Microsoft Dynamics 365 Human Resources, i nomi di utenti e posizioni sono troncati. Di conseguenza, può risultare difficile acquisire una schermata o stampare e distribuire la gerarchia.

![Gerarchia posizioni.](media/position-h.png)

**Causa**

Questo comportamento è predefinito.

**Risoluzione**

Purtroppo, gli utenti non possono cambiare facilmente la dimensione del testo. Tuttavia, è possibile esportare la gerarchia posizioni da Human Resources e quindi importarla in Microsoft Visio. Sebbene l'articolo successivo sia scritto per Microsoft Dynamics AX 2012, il processo è valido anche per Human Resources: [Esportare una gerarchia posizioni in Microsoft Visio](/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Seguire questa procedura per esportare in Visio.

1. In Human Resources, aprire la pagina elenco **Posizioni**.

    Per includere più informazioni nel diagramma della struttura organizzativa, aggiungi dei campi all'elenco **Posizioni** , in modo che siano disponibili quando usi la **Creazione guidata organigramma** più avanti in questa procedura.

2. Nel riquadro azioni, selezionare il pulsante **Apri in Microsoft Office**, quindi sotto **Esporta in Excel**, selezionare **Posizioni**. In alternativa, premere CTRL+T.

    ![Esportare la pagina elenco Posizioni in Excel.](media/org-admin.png)

3. Salvare il file di Excel esportato.

    ![Finestra di dialogo Esporta in Excel.](media/export-excel.png)

4. In Visio, selezionare **Visio - Crea nuovo**, quindi selezionare la categoria di modelli **Ufficio**.

    ![Nuovo diagramma.](media/new.png)

5. Selezionare **Creazione guidata organigramma** e quindi selezionare **Crea**.

    ![Finestra di dialogo Creazione guidata organigramma.](media/orgchart-wizard.png)

6. Selezionare **Informazioni memorizzate in un file o database** e quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 1.](media/orgchart-wizard7.png)

7. Scegliere **Un file di testo, Org Plus (\*.txt) o Excel**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 2.](media/orgchart-wizard3.png)

8. Selezionare il file di Excel esportato contenente la gerarchia posizioni, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 3.](media/orgchart-wizard2.png)

9. Impostare il campo **Nome** su **Posizione**, impostare il campo **Subordinato a** su **Subordinato a**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 4.](media/orgchart-wizard1.png)

10. Selezionare i campi che devono essere visualizzati in ogni nodo, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 5.](media/orgchart-wizard5.png)

11. Aggiungere la colonna **Posizione** all'elenco **Campi proprietà forme**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 6.](media/orgchart-wizard6.png)

12. Le immagini non sono attualmente disponibili. Di conseguenza, nella pagina successiva, selezionare **Avanti**.
13. Selezionare **I dati aziendali verranno suddivisi sulle pagine in modo automatico**.

    ![Creazione guidata organigramma 7.](media/orgchart-wizard4.png)

14. Selezionare **Fine**.

    Se sono presenti posizioni non incluse nella struttura, viene richiesto di includerle nel diagramma.

Nel diagramma generato in Visio ogni responsabile è visualizzato su un foglio di lavoro distinto.

In base ai campi selezionati da includere nel diagramma, ogni nodo visualizza le informazioni appropriate quando il file Visio viene generato.

![Diagramma della gerarchia.](media/hierarchy.png)

**Opzione aggiuntiva**

In Human Resources, è inoltre possibile utilizzare l'area di lavoro **Persone** per visualizzare le informazioni relative alla gerarchia.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
