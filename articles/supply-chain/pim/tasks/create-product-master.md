---
title: Creare una rappresentazione generale prodotto
description: Creare una rappresentazione generale prodotto per le varianti predefinite.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductInventoryDimensionGroups
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4140232da68dacde49e236e587110be4f3bbea11fd6c2deec29aaa7ee9e107f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722345"
---
# <a name="create-a-product-master"></a>Creare una rappresentazione generale prodotto

[!include [banner](../../includes/banner.md)]

Creare una rappresentazione generale prodotto per le varianti predefinite. La società di dati dimostrativi utilizzata per creare questa procedura è USMF. Questa procedura è destinata al responsabile del design del prodotto.


## <a name="create-a-new-product-master"></a>Creare una nuova rappresentazione generale prodotto
1. Selezionare **Pannello di navigazione > Moduli > Gestione informazioni sul prodotto > Prodotti > Rappresentazioni generali prodotto**.
2. Fare clic su **Nuovo**.
3. Nel campo **Numero prodotto**, digitare un valore. Il numero deve essere univoco. Per il campo **Numero prodotto** è possibile impostare una sequenza numerica. In questo caso, l'utente non deve immettere alcun valore.
4. Digitare un valore nel campo **Nome prodotto**. Immettere un nome descrittivo per il prodotto. Il valore predefinito è il nome di ricerca, ma tale valore può essere modificato dall'utente.
5. Nel campo **Gruppo di dimensioni prodotto** fare clic sul pulsante a discesa per aprire la ricerca. Il gruppo di dimensioni prodotto determina quale delle 4 dimensioni possono essere utilizzate per creare varianti prodotto. In questo esempio viene utilizzato un gruppo con colore e dimensione.
6. Nell'elenco trovare e selezionare il record desiderato.
7. Nell'elenco fare clic sul collegamento nella riga selezionata. La **tecnologia di configurazione** predefinita è "Variante predefinita". Tale impostazione verrà utilizzata per questo esempio.
8. Fare clic su **OK**.

## <a name="select-product-dimension-groups"></a>Selezionare gruppi di dimensione prodotto
1. Nel campo **Gruppo di colori** fare clic sul pulsante a discesa per aprire la ricerca.
2. Trovare e selezionare il record desiderato nell'elenco.
3. Nell'elenco fare clic sul collegamento nella riga selezionata.
4. Nel campo **Gruppo di dimensioni** fare clic sul pulsante a discesa per aprire la ricerca.
5. Nell'elenco trovare e selezionare il record desiderato.
6. Nell'elenco fare clic sul collegamento nella riga selezionata.

## <a name="add-dimension-groups"></a>Aggiungere gruppi di dimensioni
1. Nel **riquadro azioni**, fare clic su **Prodotto**.
2. Fare clic su **Gruppi di dimensioni** per aprire la finestra di dialogo a discesa.
3. Nel campo **Gruppo di dimensioni di immagazzinamento** fare clic sul pulsante a discesa per aprire la ricerca. Le dimensioni di immagazzinamento consentono di controllare il modo in cui gli articoli vengono immagazzinati e prelevati dal magazzino. Ad esempio, una dimensione di immagazzinamento può includere il sito e il magazzino.
4. Nell'elenco trovare e selezionare il record desiderato.
5. Nell'elenco fare clic sul collegamento nella riga selezionata.
6. Nel campo **Gruppo di dimensioni di tracciabilità** fare clic sul pulsante a discesa per aprire la ricerca. Il gruppo di dimensioni di tracciabilità determina quali dimensioni di tracciabilità è possibile aggiungere a un prodotto. Ad esempio, numero batch e numero di serie vengono utilizzati per tenere traccia degli articoli di magazzino.
7. Nell'elenco trovare e selezionare il record desiderato.
8. Nell'elenco fare clic sul collegamento nella riga selezionata.
9. Fare clic su **OK**.
10. Fare clic su **Salva**.
11. Chiudere la pagina.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]