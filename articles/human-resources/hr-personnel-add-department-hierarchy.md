---
title: Creare reparti e includerli nella gerarchia dei reparti
description: Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione. Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HierarchyDesigner, OMOperatingUnit, HcmPersonnelManagementWorkspace
audience: Application User
ms.custom: 63213
ms.assetid: 5dbc62fc-0184-4c0e-9856-e735fc68799e
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: cdc0440c02d0e66eaa89bfd875d8c8edf8d99c96
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688603"
---
# <a name="create-departments-and-include-them-in-the-department-hierarchy"></a>Creare reparti e includerli nella gerarchia dei reparti


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Un reparto è un'unità operativa che rappresenta una categoria o un'area operativa di un'organizzazione. Un reparto è responsabile di una specifica area dell'organizzazione, ad esempio la vendita, la contabilità o le risorse umane. È possibile utilizzare i reparti per creare report sulle aree operative. I reparti possono essere responsabili di profitti e perdite.

Un reparto può includere un gruppo di centri di costo. È possibile assegnare delle posizioni ai reparti. Per creare un reparto, fare clic su **Risorse umane** &gt; **Reparti** &gt; **Reparto**. Nella seguente tabella vengono illustrati i campi disponibili.

| Campo               | Descrizione                                                                                                                                                                                                       |
|---------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Nome**                | Immettere un nome per il reparto.                                                                                                                                                                                  |
| **Numero reparto**   | È possibile generare automaticamente un valore predefinito se un codice di sequenza numerica viene assegnato al riferimento **Numero organizzazione** nella pagina **Sequenze numeriche**.                                                 |
| **Nome di ricerca**         | Immettere un nome o un acronimo che possa essere utilizzato per cercare il reparto.                                                                                                                                            |
| **Promemoria**                | Immettere qui qualsiasi informazione aggiuntiva.                                                                                                                                                                            |
| **In gerarchia**        | Una casella di controllo selezionata indica che il reparto è incluso nella gerarchia reparti. Per informazioni su come aggiungere un reparto alla gerarchia reparti, vedere le informazioni più avanti in questo articolo. |
| **Numero DUNS**         | DUNS sta per Data Universal Number System. Si tratta di un numero a nove cifre emesso da Dun & Bradstreet.                                                                                                     |
| **Responsabile**             | Immettere i dati della persona che gestisce il reparto.                                                                                                                                                                    |
| **Indirizzi**           | Aggiungere le informazioni sull'indirizzo del reparto. Ad esempio, aggiungere l'indirizzo postale dell'edificio in cui si trova il reparto.                                                                          |
| **Informazioni contatto** | Aggiungere le informazioni sul contatto presso il reparto. Ad esempio, aggiungere un numero di telefono per il servizio assistenza del reparto.                                                                                           |

Per aggiungere un reparto alla gerarchia reparti, effettuare le operazioni indicate di seguito.

1.  Fare clic su **Risorse umane** &gt; **Reparti** &gt; **Gerarchia reparti**.
2.  Fare clic su **Modifica**, quindi selezionare l'organizzazione sotto alla quale si trova il reparto.
3.  Fare clic su **Inserisci** e selezionare **Reparto** nell'elenco.
4.  Nell'elenco dei reparti visualizzato, selezionare il reparto da aggiungere alla gerarchia.
5.  Salvare le modifiche. Viene visualizzato un messaggio che indica che è stata creata una versione bozza della gerarchia.
6.  Quando si è pronti, fare clic su **Pubblica** nella finestra di progettazione della gerarchia. È possibile immettere una data di validità che indica il momento in cui la gerarchia deve essere pubblicata. Ad esempio, per aggiungere un nuovo reparto all'inizio dell'anno di calendario successivo, impostare la data di validità sul 1° gennaio del nuovo anno. Le modifiche alla gerarchia diverranno effettive in tale data.

## <a name="steps-for-creating-a-department"></a>Passaggi per creare un reparto
Fare riferimento all'articolo [Definire nuovi reparti](./hr-personnel-define-departments.md) per la procedura dettagliata relativa alla creazione di un nuovo reparto. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
