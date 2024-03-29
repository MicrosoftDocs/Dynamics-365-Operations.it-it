---
title: Configurare i parametri dell'area di lavoro controllo costi
description: Utilizzare questa procedura per configurare l'area di lavoro di controllo costi in modo che i responsabili a diversi livelli di un'organizzazione possano ottenere dati approfonditi per gli oggetti di costo, ad esempio centri di costo e gruppi di prodotti.
author: kfend
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c38b6f2664426513ea46b16b4cd54d69d71d1399
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710559"
---
# <a name="configure-cost-control-workspace-parameters"></a>Configurare i parametri dell'area di lavoro controllo costi

[!include [banner](../../includes/banner.md)]

Utilizzare questa procedura per configurare l'area di lavoro di controllo costi in modo che i responsabili a diversi livelli di un'organizzazione possano ottenere dati approfonditi per gli oggetti di costo, ad esempio centri di costo e gruppi di prodotti. La società dimostrativa USP2 è stata utilizzata per creare questa registrazione.

1. Andare a Contabilità industriale > Impostazioni > Configurazione area di lavoro controllo costi.
2. Fare clic su Nuovo.
3. Digitare un valore nel campo Nome.
4. Nel campo Descrizione digitare un valore.
5. Selezionare Sì nel campo Pubblicato.
    * Se si imposta questa opzione su Sì, gli utenti assegnati a uno di questi ruoli possono visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile, addetto alla contabilità o controller oggetto di costo. Se si imposta questa opzione su Sì, solo gli utenti assegnati a uno di questi ruoli possono visualizzare il report nell'area di lavoro di controllo costi: responsabile della contabilità industriale, contabile o addetto alla contabilità.  
6. Espandere l'area di filtro dei dati.
7. Nel campo Unità di controllo costi immettere o selezionare un valore.
8. Nel campo Versione originale budget immettere o selezionare un valore.
9. Nel campo Gerarchia dimensioni di elemento di costo immettere o selezionare un valore.
10. Nel campo Gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
11. Espandere la sezione Assegna record di calcolo.
12. Fare clic su Nuovo.
13. Nell'elenco contrassegnare la riga selezionata.
14. Nel campo Periodo di calendario fiscale immettere o selezionare un valore.
15. Nel campo Versione effettiva immettere o selezionare un valore.
16. Espandere la sezione Periodi fiscali per colonna.
17. Selezionare Sì nel campo Periodo corrente.
18. Espandere la sezione Colonne da visualizzare per costi.
19. Selezionare Sì nel campo Costo fisso.
20. Selezionare Sì nel campo Costo variabile.
21. Selezionare Sì nel campo Costo totale.
22. Fare clic su Salva.
23. Chiudere la pagina.
24. Andare a Contabilità industriale > Aree di lavoro > Controllo costi.
25. Selezionare un rendiconto per visualizzare i costi fissi, variabili, totali e non classificati per i periodi fiscali selezionati.
26. Nel campo Periodo di calendario fiscale immettere o selezionare un valore.
27. Nel campo Nodo gerarchia dimensioni di oggetto di costo immettere o selezionare un valore.
    * Dopo aver selezionato una gerarchia di dimensioni di oggetto di costo, espandere la gerarchia dimensioni di elemento di costo per visualizzare i valori di costo desiderato. Ad esempio, è possibile espandere la gerarchia nei costi generali di produzione per visualizzare il valore.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
