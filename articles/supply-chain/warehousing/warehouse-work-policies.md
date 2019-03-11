---
title: Criteri di lavoro magazzino
description: i criteri di lavoro del magazzino controllano se il lavoro del magazzino viene creato da processi di magazzino durante la produzione, in base al tipo di ordine di lavoro, all'ubicazione del magazzino e al prodotto.
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSWorkPolicy
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 196561
ms.assetid: cbf48ec6-1836-48d5-ad66-a9b534af1786
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 0710eac8daba7f51f6b5d1522476b812a130960d
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2019
ms.locfileid: "325597"
---
# <a name="warehouse-work-policies"></a>Criteri di lavoro magazzino

[!include [banner](../includes/banner.md)]

I criteri di lavoro del magazzino in Microsoft Dynamics 365 for Finance and Operations controllano se il lavoro del magazzino viene creato da processi di magazzino durante la produzione, in base al tipo di ordine di lavoro, all'ubicazione del magazzino e al prodotto.

Questi criteri di lavoro controllano se il lavoro del magazzino è stato creato per i processi di magazzino in fase di produzione. È possibile impostare i criteri di lavoro mediante una combinazione di **tipi di ordine di lavoro**, una **ubicazione di magazzino** e un **prodotto**. Ad esempio, il prodotto L0101 viene dichiarato finito nell'ubicazione di uscita 001. Il prodotto finito viene successivamente consumato in un altro ordine di produzione all'ubicazione di uscita 001. In questo caso, è possibile impostare i criteri di lavoro per impedire che lavoro per lo stoccaggio di prodotti finiti venga creato quando si dichiara il prodotto L0101 finito nell'ubicazione di uscita 001. I criteri di lavoro sono una singola entità che può essere descritta con le seguenti informazioni:

-   **Nome dei criteri di lavoro**(identificatore univoco dei criteri di lavoro)
-   **Tipi di ordine di lavoro** e **Metodo di creazione lavoro**
-   **Ubicazioni di magazzino**
-   **Prodotti**

## <a name="work-order-types"></a>Tipi di ordine di lavoro
È possibile scegliere i seguenti tipi di ordine di lavoro:

-   Stoccaggio prodotti finiti
-   Stoccaggio co-prodotti e sottoprodotti
-   Prelievo materie prime

Il campo **Metodo di creazione lavoro** ha il valore **Mai**. Questo valore indica che i criteri di lavoro impediranno la creazione di lavoro di magazzino per il tipo di ordine di lavoro selezionato.

## <a name="inventory-locations"></a>Ubicazioni di magazzino
È possibile selezionare un'ubicazione a cui i criteri di lavoro vengono applicati. Se non si specifica una ubicazione associata ai criteri di lavoro, i criteri di lavoro non sono applicabili ad alcun processo. Nella pagina **Ubicazioni**, è inoltre possibile selezionare o annullare la selezione dei criteri di lavoro per una determinata ubicazione.

## <a name="products"></a>Prodotti
È possibile selezionare un prodotto a cui i criteri di lavoro vengono applicati. È possibile applicare i criteri di lavoro a tutti i prodotti o a prodotti selezionati.

## <a name="example"></a>Esempio
Nel seguente esempio, sono presenti due ordini di produzione, PRD-001 e PRD-00*2*. L'ordine di produzione PRD-001 ha un'operazione denominata **Assemblaggio**, in cui il prodotto SC1 viene dichiarato finito nell'ubicazione O1. L'ordine di produzione PRD-002 ha un'operazione denominata **Verniciatura** e utilizza il prodotto SC1 dall'ubicazione O1. L'ordine di produzione PRD-002 utilizza anche le materie prime RM1 dall'ubicazione O1. RM1 sono immagazzinate nell'ubicazione BULK-001 e verranno prelevate nell'ubicazione O1 dal lavoro di magazzino per il prelievo di materie prime. Il lavoro di prelievo viene generato quando l'ordine di produzione PRD-002 viene rilasciato. 

[![Criteri di lavoro magazzino](./media/warehouse-work-policies.png)](./media/warehouse-work-policies.png) 

Quando si pianifica di configurazione dei criteri di lavoro di magazzino per questo scenario, valutare le seguenti informazioni:

-   Il lavoro di magazzino per lo stoccaggio di articoli finiti non è richiesto quando si dichiara SC1 come finito dall'ordine di produzione PRD-001 nell'ubicazione O1. Questo perché l'operazione **Verniciatura** per l'ordine di produzione PRD-002 utilizza SC1 nella stessa ubicazione.
-   Il lavoro di magazzino per il prelievo di materie prime è necessario per spostare le materie prime RM1 dall'ubicazione di magazzino BULK-001 all'ubicazione O1.

Di seguito è riportato un esempio dei criteri di lavoro che è possibile impostare, in base a queste considerazioni.


|                                       |                                       |
|---------------------------------------|---------------------------------------|
| <strong>Nome criteri di lavoro</strong><br> | <strong>Tipi di ordine di lavoro</strong><br> |
|         Nessuno stoccaggio 01     `          |     - Stoccaggio prodotto finito<br>      |
|                                       |    <strong>Ubicazioni</strong><br>     |
|                                       |                 - O1                  |
|                                       |    <strong>Prodotti</strong> <br>     |
|                                       |                 - SC1                 |

Nelle procedure riportate di seguito vengono fornite istruzioni dettagliate sull'impostazione dei criteri di lavoro di magazzino per questo scenario. Una impostazione di esempio che mostra come dichiarare finito un ordine di produzione  in un'ubicazione non controllata da targhe viene anche descritta.

## <a name="set-up-a-warehouse-work-policy"></a>Impostare criteri di lavoro magazzino
I processi del magazzino non includono sempre il lavoro in magazzino. Definendo i criteri di lavoro, è possibile impedire la creazione di lavoro per il prelievo delle materie prime e lo stoccaggio di prodotti finiti per un set di prodotti in ubicazioni specifiche. La società di dati dimostrativi USMF è stata utilizzata per creare questa procedura. 

PASSAGGI (21)

|     |                                                                            |
|-----|----------------------------------------------------------------------------|
| 1  | Andare a Gestione magazzino &gt; Impostazioni &gt; Lavoro &gt; Criteri di lavoro.        |
| 2  | Fare clic su Nuovo.                                                                 |
| 3  | Nel campo Nome criteri di lavoro digitare “No lavoro di stoccaggio".                    |
| 4  | Fare clic su Salva.                                                                |
| 5  | Scegliere Aggiungi.                                                                 |
| 6  | Nell'elenco contrassegnare la riga selezionata.                                        |
| 7  | Nel campo Tipo ordine di lavoro selezionare "Stoccaggio prodotti finiti".            |
| 8  | Scegliere Aggiungi.                                                                 |
| 9  | Nell'elenco contrassegnare la riga selezionata.                                        |
| 10. | Nel campo Tipo ordine di lavoro selezionare "Stoccaggio co-prodotti e sottoprodotti". |
| 11. | Espandere la sezione Ubicazioni di magazzino.                                    |
| 12. | Scegliere Aggiungi.                                                                 |
| 13 | Nell'elenco contrassegnare la riga selezionata.                                        |
| 14. | Nell'elenco di magazzino immettere "51".                                         |
| 15. | Nel campo Ubicazione immettere o selezionare "001".                              |
| 16. | Espandere la sezione Prodotti.                                               |
| 17. | Nel campo Selezione prodotto selezionare "Selezionato".                         |
| 18. | Scegliere Aggiungi.                                                                 |
| 19. | Nell'elenco contrassegnare la riga selezionata.                                        |
| 20. | Nel campo Numero articolo immettere o selezionare "L0101".                         |
| 21. | Fare clic su Salva.                                                                |

## <a name="report-a-production-order-as-finished-to-a-location-that-isnt-license-platecontrolled"></a>Dichiarare un ordine di produzione finito in un'ubicazione non controllata da targhe
In questa procedura è riportato un esempio di dichiarazione di finito a un'ubicazione che non controllata da targhe. I criteri di lavoro applicabili sono il prerequisito per questa attività. La procedura precedente mostra l'impostazione dei criteri di lavoro. 

PASSAGGI (25)

<table>
<tbody>
<tr>
<td colspan="3"><strong>Sottoattività: Impostare un'ubicazione di output.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Passare a Amministrazione organizzazione &gt; Risorse &gt; Gruppi di risorse.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Nell'elenco selezionare il gruppo di risorse &#39;5102&#39;.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Fare clic su Modifica.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Nel campo Magazzino di output immettere &#39;51&#39;.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Nel campo Ubicazione di output immettere &#39;001&#39;.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>L'ubicazione 001 non è un'ubicazione controllata da targa. È possibile impostare un'ubicazione di output senza targa solo se i criteri di lavoro applicabili sono disponibili per l'ubicazione.</td>
</tr>
<tr>
<td colspan="3"><strong>Sottoattività: Creare un ordine di produzione e segnalarlo come finito.</strong></td>
</tr>
<tr>
<td></td>
<td>1.</td>
<td>Chiudere la pagina.</td>
</tr>
<tr>
<td></td>
<td>2.</td>
<td>Fare clic su Controllo produzione &gt; Ordini di produzione &gt; Tutti gli ordini di produzione.</td>
</tr>
<tr>
<td></td>
<td>3.</td>
<td>Fare clic su Nuovo ordine di produzione.</td>
</tr>
<tr>
<td></td>
<td>4.</td>
<td>Nel campo Numero articolo immettere &#39;L0101&#39;.</td>
</tr>
<tr>
<td></td>
<td>5.</td>
<td>Fare clic su Crea.</td>
</tr>
<tr>
<td></td>
<td>6.</td>
<td>Nel riquadro azioni fare clic su Ordine di produzione.</td>
</tr>
<tr>
<td></td>
<td>7.</td>
<td>Fare clic su Stima.</td>
</tr>
<tr>
<td></td>
<td>8.</td>
<td>Fare clic su OK.</td>
</tr>
<tr>
<td></td>
<td>9.</td>
<td>Fare clic su Inizia.</td>
</tr>
<tr>
<td></td>
<td>10.</td>
<td>Fare clic sulla scheda Generale.</td>
</tr>
<tr>
<td></td>
<td>11.</td>
<td>Nel campo Consumo DBA automatico selezionare &#39;Mai&#39;.</td>
</tr>
<tr>
<td></td>
<td>12.</td>
<td>Fare clic su OK.</td>
</tr>
<tr>
<td></td>
<td>13.</td>
<td>Fare clic su Dichiarazione di finito.</td>
</tr>
<tr>
<td></td>
<td>14.</td>
<td>Fare clic sulla scheda Generale.</td>
</tr>
<tr>
<td></td>
<td>15.</td>
<td>Selezionare Sì nel campo Accetta errore.</td>
</tr>
<tr>
<td></td>
<td>16.</td>
<td>Fare clic su OK.</td>
</tr>
<tr>
<td></td>
<td>17.</td>
<td>Nel riquadro azioni fare clic su Magazzino.</td>
</tr>
<tr>
<td></td>
<td>18.</td>
<td>Fare clic su Dettagli lavoro.</td>
</tr>
<tr>
<td></td>
<td>19.</td>
<td>Quando l'ordine di produzione è stato dichiarato finito, nessun lavoro è stato generato per lo stoccaggio. Questa situazione si verifica perché vengono definiti criteri di lavoro che impediscono la generazione del lavoro quando il prodotto L0101 viene dichiarato finito all'ubicazione 001.</td>
</tr>
</tbody>
</table>



