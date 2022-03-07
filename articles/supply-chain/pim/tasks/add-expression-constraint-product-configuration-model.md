---
title: Aggiungere un vincolo di espressione a un modello di configurazione prodotto
description: In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569651"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Aggiungere un vincolo di espressione a un modello di configurazione prodotto

[!include [banner](../../includes/banner.md)]

In questa procedura vengono descritti i passaggi per aggiungere una nuova espressione di vincolo a un modello di configurazione prodotto. Indica come è possibile impostare come obbligatorio che la protezione angolare deve essere applicata a un altoparlante se l'utente ha selezionato che la griglia anteriore è in metallo. La procedura utilizza il componente High end speaker nella società di dati dimostrativi USMF.

## <a name="create-an-expression-constraint"></a>Creare un vincolo di espressione

1. Vai a **Gestione informazioni sul prodotto \> Prodotti \> Modelli di configurazione prodotto**.
3. Nell'elenco trovare e selezionare il record desiderato.
    * In questo esempio viene utilizzato il modello High end speaker.  
4. Nell'elenco fare clic sul collegamento nella riga selezionata.
5. Espandere la sezione **Vincoli**.
6. Selezionare **Aggiungi**.
7. Selezionare **Crea**.
8. Digitare un valore nel campo **Nome**.

## <a name="enter-expression"></a>Immetti espressione

1. Seleziona **Modifica espressione**.
    * Se si sblocca l'interfaccia utente nella registrazione attività in questa fase, è possibile utilizzare IntelliSense e l'elenco dei simboli per creare l'espressione del vincolo.  
2. Nel campo **ConstraintBody**, immettere 'Implies[FrontGrill=="Metal", CornerProtection] '.
    * La logica dell'espressione dice: se la griglia anteriore è in metallo, è necessario selezionare l'opzione di protezione angolare.  
3. Selezionare **Convalida**.
    * La funzione di convalida viene eseguita tramite l'espressione di vincolo e controllata per la presenza di errori di sintassi.  
4. Selezionare **Chiudi**.
5. Selezionare **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]