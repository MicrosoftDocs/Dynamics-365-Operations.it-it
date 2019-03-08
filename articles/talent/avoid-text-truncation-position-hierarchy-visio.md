---
title: Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio
description: In questo argomento viene descritto come risolvere un problema in cui i nomi di utenti e posizioni vengono troncati quando i clienti visualizzano la gerarchia posizioni in Microsoft Dynamics 365 for Talent. Il troncamento di testo può rendere difficile l'acquisizione di una schermata o la stampa della gerarchia.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b688a396e3b384aedb06c470b1634150ae7aa038
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "304968"
---
# <a name="avoid-text-truncation-on-the-position-hierarchy-and-export-to-visio"></a>Evitare il troncamento del testo nella gerarchia posizioni ed esportare in Visio

[!include [banner](includes/banner.md)]

**Uscita**

Quando un cliente visualizza la gerarchia posizioni in Microsoft Dynamics 365 for Talent, i nomi di utenti e posizioni sono troncati. Di conseguenza, può risultare difficile acquisire una schermata o stampare e distribuire la gerarchia.

![Gerarchia posizioni](media/position-h.png)

**Causa**

Questo comportamento è predefinito.

**Risoluzione**

Purtroppo, gli utenti non possono cambiare facilmente la dimensione del testo. Tuttavia, è possibile esportare la gerarchia posizioni da Talent e quindi importarla in Microsoft Visio. Sebbene l'articolo successivo sia scritto per Microsoft Dynamics AX 2012, il processo è valido anche per Talent: [Esportare una gerarchia posizioni in Microsoft Visio](https://docs.microsoft.com/en-us/dynamicsax-2012/appuser-itpro/export-a-position-hierarchy-to-microsoft-visio).

Seguire questa procedura per esportare in Visio.

1. In Talent, aprire la pagina elenco **Posizioni**.

    Per includere ulteriori informazioni nel diagramma della struttura organizzativa, aggiungere campi all'elenco **Posizioni**, di modo che siano disponibili quando si utilizza la procedura guidata in seguito in questa procedura.

2. Nel riquadro azioni, selezionare il pulsante **Apri in Microsoft Office**, quindi sotto **Esporta in Excel**, selezionare **Posizioni**. In alternativa, premere CTRL+T.

    ![Esportare la pagina elenco Posizioni in Excel](media/org-admin.png)

3. Salvare il file di Excel esportato.

    ![Finestra di dialogo Esporta in Excel](media/export-excel.png)

4. In Visio, selezionare **Visio - Crea nuovo**, quindi selezionare la categoria di modelli **Ufficio**.

    ![Nuovo diagramma](media/new.png)

5. Selezionare **Creazione guidata organigramma** e quindi selezionare **Crea**.

    ![Finestra di dialogo Creazione guidata organigramma](media/orgchart-wizard.png)

6. Selezionare **Informazioni memorizzate in un file o database** e quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 1](media/orgchart-wizard7.png)

7. Scegliere **Un file di testo, Org Plus (\*.txt) o Excel**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 2](media/orgchart-wizard3.png)

8. Selezionare il file di Excel esportato contenente la gerarchia posizioni, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 3](media/orgchart-wizard2.png)

9. Impostare il campo **Nome** su **Posizione**, impostare il campo **Subordinato a** su **Subordinato a**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 4](media/orgchart-wizard1.png)

10. Selezionare i campi che devono essere visualizzati in ogni nodo, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 5](media/orgchart-wizard5.png)

11. Aggiungere la colonna **Posizione** all'elenco **Campi proprietà forme**, quindi selezionare **Avanti**.

    ![Creazione guidata organigramma 6](media/orgchart-wizard6.png)

12. Le immagini non sono attualmente disponibili. Di conseguenza, nella pagina successiva, selezionare **Avanti**.
13. Selezionare **I dati aziendali verranno suddivisi sulle pagine in modo automatico**.

    ![Creazione guidata organigramma 7](media/orgchart-wizard4.png)

14. Selezionare **Fine**.

    Se sono presenti posizioni non incluse nella struttura, viene richiesto di includerle nel diagramma.

Nel diagramma generato in Visio ogni responsabile è visualizzato su un foglio di lavoro distinto.

In base ai campi selezionati da includere nel diagramma, ogni nodo visualizza le informazioni appropriate quando il file Visio viene generato.

![Diagramma della gerarchia](media/hierarchy.png)

**Opzione aggiuntiva**

In Talent, è inoltre possibile utilizzare l'area di lavoro **Persone** per visualizzare le informazioni relative alla gerarchia.
