---
title: Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni
description: Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductMaintainWorkspace, EcoResProductOpenCasesFormPart, EcoResProductDetailsExtended, BOMConsistOf, BOMTable, InventItemIdLookupSimple, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f86625821f8a01a6d4949f9dca538a279f52ce9c
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7565590"
---
# <a name="create-a-bill-of-materials-for-a-dimension-based-product-master"></a>Creare una distinta base per una rappresentazione generale prodotto basata su dimensioni

[!include [banner](../../includes/banner.md)]

Per questa procedura è necessario completare le 4 guide precedenti di questa sequenza di otto registrazioni. Nelle prime 4 registrazioni vengono impostati i dati necessari per completare questa procedura. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa attività viene in genere gestita nella finestra di progettazione del prodotto.

## <a name="select-the-product"></a>Selezionare il prodotto

1. Fare clic su **Gestione informazioni sul prodotto \> Prodotti \> Prodotti rilasciati**.
1. Nell'elenco contrassegnare la riga selezionata.
    * Individuare la rappresentazione generale prodotto rilasciata con la tecnologia di configurazione basata su dimensioni creata nella prima attività della guida di questa sequenza.  
1. Nel riquadro azioni selezionare **Progetta**.
1. Seleziona **Versioni DBA**.

## <a name="create-new-bom-and-bom-version"></a>Creare una nuova DBA e una nuova versione DBA

1. Selezionare **Nuovo**.
1. Selezionare **DBA e versione DBA**.
1. Digitare un valore nel campo **Nome**.
    * Impostazione di un sito  
    * In questa procedura non impostiamo un sito specifico per la DBA.  
1. Selezionare **OK**.
1. Selezionare **Nuovo**.
    * In questa procedura aggiungeremo quattro righe alla DBA. Due righe rappresentano le opzioni di cavo e due righe rappresentano le opzioni di gabinetto.  
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Numero articolo** immettere o selezionare un valore.
    * Selezionare il numero di articolo A0001, cavi HDMI 6.  
1. Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.
    * Selezionare il gruppo di configurazione dei cavi creato nella guida 4 di questa sequenza.  
1. Selezionare **Nuovo**.
    * Selezionare il numero di articolo A0002, cavi HDMI 12.  
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Numero articolo** immettere o selezionare un valore.
1. Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.
    * Selezionare di nuovo il gruppo di configurazioni dei cavi.  
1. Selezionare **Nuovo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Numero articolo** immettere o selezionare un valore.
    * Selezionare il numero di articolo D0002, cabinet.  
1. Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.
    * Selezionare il gruppo di configurazioni del cabinet per questa riga DBA.  
1. Selezionare **Nuovo**.
1. Nell'elenco contrassegnare la riga selezionata.
1. Nel campo **Numero articolo** immettere o selezionare un valore.
    * Selezionare il numero di articolo M0007 StandardCabinet come ultima riga DBA.  
1. Nel campo **Gruppo di configurazioni** immettere o selezionare un valore.
    * Selezionare il gruppo di configurazioni del cabinet per l'ultima riga DBA.  

## <a name="approve-and-activate"></a>Approva e attiva

1. Chiudere la pagina.
1. Selezionare **Approva**.
1. Nel campo **Approvato da** immettere o selezionare un valore.
1. Selezionare *Sì* nel campo **Approvare anche la distinta base?**.
1. Selezionare **OK**.
1. Selezionare **Attiva**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]