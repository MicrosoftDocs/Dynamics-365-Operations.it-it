---
title: Modulo Scheda
description: In questo argomento vengono descritti i moduli Scheda e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: e7d2cd7b7ce9446d77eff66433739c8ea6b1f309
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "6348298"
---
# <a name="tab-module"></a>Modulo scheda

[!include [banner](includes/banner.md)]

In questo argomento vengono descritti i moduli Scheda e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli Scheda sono moduli simili a contenitori utilizzati per organizzare le informazioni in una pagina di sito in schede. Possono essere utilizzati in qualsiasi pagina in cui le informazioni devono essere presentate in schede.

In ogni modulo Scheda, è possibile aggiungere uno o più moduli Elemento scheda. Ogni modulo Elemento scheda rappresenta una singola scheda. In ciascun modulo Elemento scheda, è possibile aggiungere uno o più moduli. Non vi sono restrizioni sui tipi di moduli che possono essere aggiunti a un modulo Elemento scheda.

L'immagine seguente mostra un esempio di modulo Scheda in una pagina di sito. In questo esempio, è selezionata la scheda **Spedizione**.

![Esempio di modulo Scheda.](./media/ecommerce-tab.PNG)

## <a name="tab-module-properties"></a>Proprietà dei moduli Scheda

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione | Testo | Questa proprietà specifica un'intestazione di testo facoltativa per il modulo Scheda. |
| Indice scheda attivo | Numero | Questa proprietà specifica la scheda che deve essere attiva per impostazione predefinita quando viene caricata una pagina. Se non viene fornito alcun valore, il primo elemento scheda è attivo per impostazione predefinita. |

## <a name="tab-item-module-properties"></a>Proprietà dei moduli Elemento scheda

| Nome proprietà | Valori | Descrizione |
|---------------|--------|-------------|
| Funzione | Testo | Questa proprietà specifica il testo del titolo del modulo Elemento scheda. |

## <a name="add-a-tab-module-to-a-page"></a>Aggiungere un modulo Scheda a una pagina

Per aggiungere un modulo Scheda a una pagina e impostare le proprietà, effettuare le seguenti operazioni.

1. Utilizzare il modello di marketing Fabrikam (o qualsiasi modello che non abbia restrizioni) per creare una nuova pagina denominata **Pagina delle politiche del punto vendita**.
1. Nello slot **Principale** della **Pagina predefinita**, selezionare i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** selezionare il modulo **Scheda** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Scheda, selezionare **Intestazione** accanto al simbolo della matita.
1. Nella finestra di dialogo **Intestazione**, sotto **Testo intestazione**, immettere il testo dell'intestazione (ad esempio, **Politiche**). Selezionare **OK**.
1. Nello slot **Scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Elemento scheda** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Elemento scheda, sotto **Titolo**, immettere il testo del titolo (ad esempio, **Consegna**).
1. Nello slot **Elemento scheda** selezionare i puntini di sospensione (**...**), quindi selezionare **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo**, selezionare il modulo **Blocco di testo** e quindi selezionare **OK**.
1. Nel riquadro delle proprietà del modulo Blocco di testo, sotto **RTF**, immettere un paragrafo di testo.
1. Nello slot **Scheda**, aggiungere altri moduli Elemento scheda che hanno titoli. In ogni modulo Elemento scheda, aggiungere un modulo Blocco di testo che abbia contenuto.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. La pagina mostrerà un modulo Scheda che contiene moduli Elemento scheda con il contenuto aggiunto.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo Accordion](add-accordion.md)

[Modulo blocco testo](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]