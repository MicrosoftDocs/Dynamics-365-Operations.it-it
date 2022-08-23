---
title: Modulo Accordion
description: In questo articolo vengono descritti i moduli Accordion e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: ec895476770f297825d6c88d0b0a5fef43a5c6ef
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2022
ms.locfileid: "9279158"
---
# <a name="accordion-module"></a>Modulo Accordion

[!include [banner](includes/banner.md)]

In questo articolo vengono descritti i moduli Accordion e la procedura per aggiungerli alle pagine di siti Web in Microsoft Dynamics 365 Commerce.

I moduli Accordion sono moduli simili a contenitori utilizzati per organizzare informazioni o moduli in una pagina fornendo una funzionalità comprimibile di tipo pannello. Un modulo Accordion può essere utilizzato in qualsiasi pagina.

In ogni modulo Accordion, è possibile aggiungere uno o più moduli Elemento accordion. Ogni modulo Elemento accordion rappresenta un pannello comprimibile. In ogni modulo Elemento accordion, è possibile aggiungere uno o più moduli. Non vi sono restrizioni sui tipi di moduli che possono essere aggiunti a un modulo Elemento accordion.

L'immagine seguente mostra un esempio di modulo Accordion utilizzato per organizzare le informazioni sulla pagina delle domande frequenti di un punto vendita.

![Esempio di modulo Accordion.](./media/ecommerce-accordion.PNG)

## <a name="accordion-module-properties"></a>Proprietà del modulo Accordion

| Nome proprietà | Valori | descrizione |
|---------------|--------|-------------|
| Intestazione | Testo | Questa proprietà specifica un'intestazione di testo facoltativa per il modulo Accordion. |
| Espandi tutto | **True** o **False** | Se il valore è impostato su **True**, la funzionalità di espansione/compressione è attivata, di modo che tutti gli elementi nel modulo Accordion possano essere espansi e compressi. |
| Stile interazione | **Indipendente** o **Espandi un solo elemento** | Questa proprietà definisce lo stile di interazione per gli elementi accordion. Se il valore è impostato su **Indipendente**, ogni elemento accordion può essere espanso o compresso indipendentemente. Se il valore è impostato su **Espandi un solo elemento**, è possibile espandere un solo elemento alla volta. Man mano che gli oggetti vengono espansi, gli oggetti precedentemente espansi vengono compressi. |

## <a name="accordion-item-module-properties"></a>Proprietà del modulo Elemento accordion

| Nome proprietà | Valori | Descrizione |
|----------------|--------|-------------|
| Funzione | Testo | Questa proprietà specifica il testo del titolo del modulo Elemento accordion. Selezionando l'area del titolo, gli utenti possono espandere o comprimere la sezione. |
| Espandi per impostazione predefinita | **True** o **False** | Se il valore è impostato su **True**, l'elemento accordion viene espanso per impostazione predefinita quando viene caricata la pagina. |

## <a name="add-an-accordion-module-to-a-faq-page"></a>Aggiungere un modulo Accordion a una pagina Domande frequenti

Per aggiungere un modulo Accordion a una pagina Domande frequenti e impostarne le proprietà in Creazione di siti Web, effettuare le seguenti operazioni.

1. Andare a **Pagine** e utilizzare il modello di marketing Fabrikam (o qualsiasi modello che non abbia restrizioni) per creare una nuova pagina denominata **Domande frequenti punto vendita**.
1. Nello slot **Principale** della **Pagina predefinita**, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** selezionare il modulo **Contenitore** e quindi **OK**.
1. Nello slot **Contenitore** seleziona i puntini di sospensione (**...**) quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Accordion** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Accordion, selezionare **Intestazione** accanto al simbolo della matita.
1. Nella finestra di dialogo **Intestazione**, sotto **Testo intestazione**, immettere **Domande frequenti**. Selezionare **OK**.
1. Nel riquadro delle proprietà del modulo Accordion, selezionare la casella di controllo **Mostra espandi tutto**, quindi nel campo **Stile interazione**, selezionare **Indipendente**.
1. Nello slot **Accordion** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Elemento Accordion** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Elemento accordion, sotto **Titolo**, immettere il testo del titolo (ad esempio, **Come si effettua un reso?**).
1. Nello slot **Elemento accordion** seleziona i puntini di sospensione (**...**), quindi seleziona **Aggiungi modulo**.
1. Nella finestra di dialogo **Seleziona moduli** seleziona il modulo **Blocco testo** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo Blocco di testo, immettere un paragrafo di testo (ad esempio, **I resi devono essere effettuati tramite il call center contattando 1-800-FABRIKAM. I prodotti devono essere restituiti entro 30 giorni dalla ricezione.**).
1. Nello slot **Accordion**, aggiungere altri modulo Elemento accordion. In ogni modulo Elemento accordion, aggiungere un modulo Blocco di testo che abbia contenuto.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. La pagina mostrerà un modulo Accordion con il contenuto aggiunto.
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica della libreria dei moduli](starter-kit-overview.md)

[Modulo contenitore](add-container-module.md)

[Modulo scheda](add-tab.md)

[Modulo blocco testo](add-content-rich-block.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
