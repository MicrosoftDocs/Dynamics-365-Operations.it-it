---
title: Abilitare e utilizzare la condivisione multicanale
description: In questo argomento viene descritto come abilitare e utilizzare la funzionalità di condivisione multicanale di Creazione di siti Web di Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 10/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3990365dda0a0cff7adcc1d97120293d43f6e858
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "4973133"
---
# <a name="enable-and-use-cross-channel-sharing"></a>Abilitare e utilizzare la condivisione multicanale

[!include [banner](includes/banner.md)]

In questo argomento viene descritto come abilitare e utilizzare la funzionalità di condivisione multicanale di Creazione di siti Web di Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Panoramica

La condivisione multicanale consente ai rivenditori di riutilizzare e condividere contenuto tra più canali di un sito. Questa funzionalità è utile quando i canali del sito hanno una lingua di base compatibile o numerosi elementi di contenuto in comune.

Per utilizzare la condivisione multicanale è necessario abilitare un canale predefinito in cui verrà cercato contenuto disponibile quando non viene trovata una versione specifica del canale del contenuto richiesto. Il contenuto che si intende condividere tra i canali viene creato nel canale predefinito. Tale contenuto può essere localizzato per qualsiasi lingua utilizzata in qualsiasi canale del sito.

## <a name="when-to-use-cross-channel-sharing"></a>Quando utilizzare la condivisione multicanale

La condivisione multicanale è utile quando più canali in un unico sito possono condividere contenuto. Ad esempio, un rivenditore che ha più marchi e vetrine raggruppate in un unico sito può condividere contenuto tra alcune o tutte le vetrine. Questo contenuto condiviso può includere pagine per termini e condizioni, termini di pagamento, metodi di spedizione e domande frequenti (FAQ).

La condivisione multicanale supporta anche i frammenti. Pertanto, una pagina di contenuto che contiene frammenti specifici del canale può essere creata come contenuto multicanale. In questo caso, sebbene la maggior parte del contenuto sarà condivisa tra i canali, i frammenti specifici del canale in una pagina multicanale verranno visualizzati solo quando vengono richiesti dal canale della vetrina corrispondente.

I siti che hanno un solo canale o i siti che hanno più canali che non possono condividere contenuto, non trarranno vantaggio dalla condivisione multicanale.

## <a name="enable-cross-channel-sharing"></a>Abilitare la condivisione multicanale

La condivisione multicanale è abilitata a livello di sito. Questa operazione è unidirezionale. In altre parole, una volta abilitata, la condivisione multicanale non può essere disabilitata.

Per abilitare la condivisione multicanale in Creazione di siti Web di Commerce, segui questi passaggi.

1. Vai a **Impostazioni sito \> Funzionalità**.
1. Imposta la funzionalità **Multicanale** su **Attivato**.

    ![Opzione Multicanale impostata su Attivato in Creazione di siti Web di Commerce](./media/enabling-cross-channel-sharing.png)

Dopo aver abilitato la condivisione multicanale, le relative informazioni verranno visualizzate nella sezione **Canali** in **Impostazioni sito \> Funzionalità**, come mostra l'esempio nell'illustrazione seguente.

![Informazioni sui canali visibili dopo l'abilitazione della condivisione multicanale](./media/channels-cross-channel.png)

Inoltre, dopo aver abilitato la condivisione multicanale, il campo **Canale** in alto a destra in Creazione di siti Web di Commerce includerà un'opzione **Punto vendita online multicanale** che puoi utilizzare per gestire il contenuto multicanale, come mostrato nell'illustrazione seguente.

![Opzione Punto vendita online multicanale nel campo Canali dopo aver abilitato la condivisione multicanale](./media/cross-channel-dropdown.png)

## <a name="create-and-use-cross-channel-content"></a>Creare e utilizzare contenuto multicanale

Puoi creare e utilizzare contenuto multicanale in diversi modi. Ad esempio, puoi creare frammenti multicanale, creare pagine multicanale che utilizzano contenuto multicanale e specifico del canale e sovrascrivere frammenti multicanale con versioni di frammenti specifiche del canale.

### <a name="create-a-cross-channel-fragment"></a>Creare un frammento multicanale

Per creare un frammento multicanale in Creazione di siti Web di Commerce, segui questi passaggi.

1. Andare a **Frammenti** e selezionare **Nuovo** per creare un nuovo frammento.
1. Nella finestra di dialogo **Nuovo frammento**, selezionare il modulo **Banner promozionale**, quindi sotto **Nome frammento**, inserire un nome (ad esempio, **Banner multicanale**). Selezionare **OK**.
1. Nel riquadro delle proprietà del modulo **Banner promozionale** seleziona **Aggiungi messaggio** e quindi **Messaggio**.
1. Nella finestra di dialogo **Messaggio**, sotto **Testo**, immetti **Multicanale** e seleziona **OK**. 
1. Selezionare **Salva**, selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

Questo frammento multicanale può essere utilizzato su pagine multicanale o specifiche del canale create in qualsiasi canale del sito.

### <a name="create-a-cross-channel-page-that-uses-cross-channel-content"></a>Creare una pagina multicanale che utilizza contenuto multicanale

Le pagine multicanale possono essere utilizzate su qualsiasi canale del tuo sito. Pertanto, puoi creare una sola volta una pagina di contenuto condiviso ed eseguire eventuali aggiornamenti successivi in un'unica posizione. Ad esempio, una pagina **Termini e condizioni** multicanale che ha l'URL `/toc` può essere condivisa tra tutti i canali di un sito. Se gli URL di base dei canali del sito sono `www.fabrikam.com/brand1` e `www.fabrikam.com/brand2`, la stessa pagina **Termini e condizioni** multicanale condivisa sarà disponibile in entrambi gli URL dei canali del sito, rispettivamente all'indirizzo `www.fabrikam.com/brand1/toc` e `www.fabrikam.com/brand2/toc`. Se la pagina **Termini e condizioni** deve essere aggiornata in seguito, devi aggiornare solo la singola pagina condivisa.

Per creare una pagina multicanale in Creazione di siti Web di Commerce che utilizza contenuto multicanale, segui questi passaggi.

1. Accedi a **Pagine** e quindi seleziona **Nuovo** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, seleziona un modello, ad esempio **Marketing**.
1. Sotto **Nome pagina**, immetti un nome per la pagina (ad esempio **Pagina multicanale**).
1. Sotto **URL pagina**, inserisci l'URL di una pagina (ad esempio, **examplepage**), quindi seleziona **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi frammento**.
1. Nella finestra di dialogo **Aggiungi frammento**, selezionare il frammento multicanale creato in precedenza che ha un banner promozionale, quindi selezionare **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Il banner promozionale dovrebbe indicare "Multicanale".
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="create-a-channel-specific-page-that-uses-cross-channel-content"></a>Creare una pagina specifica del canale che utilizza contenuto multicanale

Utilizzando contenuto multicanale in pagine specifiche del canale, puoi creare un frammento di contenuto condiviso una volta e quindi utilizzarlo in pagine specifiche del canale. Questa "origine unica" è utile per il contenuto condiviso come termini e condizioni, termini di pagamento o informazioni di contatto.

Per creare una pagina specifica del canale in Creazione di siti Web di Commerce che utilizza contenuto multicanale, segui questi passaggi.

1. In un canale specifico, come **Punto vendita online esteso Fabrikam**, vai a **Pagine** e quindi seleziona **Nuova** per creare una nuova pagina.
1. Nella finestra di dialogo **Scegli un modello**, seleziona un modello, ad esempio **Marketing**.
1. Sotto **Nome pagina**, immetti un nome per la pagina (ad esempio **Pagina specifica del canale**).
1. Sotto **URL pagina**, immetti l'URL di una pagina (ad esempio, **channelspecificpage**), quindi seleziona **OK**.
1. Nello slot **Principale** della nuova pagina, selezionare il pulsante con i puntini di sospensione (**...**) e quindi **Aggiungi frammento**.
1. Nella finestra di dialogo **Aggiungi frammento**, sotto **Canale**, selezionare **Punto vendita online multicanale**. Il frammento multicanale che hai creato in precedenza deve essere visualizzato nell'elenco. Selezionalo e quindi seleziona **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Il banner promozionale dovrebbe indicare "Multicanale".
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

### <a name="create-a-channel-specific-version-of-a-cross-channel-page"></a>Creare una versione specifica del canale di una pagina multicanale

La condivisione multicanale supporta la sostituzione del contenuto multicanale. Ad esempio, tutti i canali del tuo sito tranne uno condividono lo stesso contenuto. Quel canale richiede contenuto differente. Per implementare contenuto differente, sostituisci il contenuto multicanale con contenuto specifico del canale creando una versione specifica del canale della pagina multicanale.

Per creare una versione specifica del canale di una pagina multicanale in Creazione di siti Web di Commerce, segui questi passaggi.

1. Nel campo **Canale** in alto a destra, seleziona **Punto vendita online multicanale**.
1. Apri la pagina multicanale che hai creato in precedenza.
1. Nel campo **Canale** in alto a destra, seleziona il canale che deve avere un contenuto specifico. L'editor di pagine mostra un messaggio che richiede di creare una nuova variante di pagina.
1. Seleziona **Crea variante di pagina**.
1. Nello slot **Principale** della variante di pagina, seleziona i puntini di sospensione (**...**) e quindi **Aggiungi modulo**.
1. Nella finestra di dialogo **Aggiungi modulo** seleziona il modulo **Banner promozionale** e quindi **OK**.
1. Nel riquadro delle proprietà del modulo **Banner promozionale** seleziona **Aggiungi messaggio** e quindi **Messaggio**.
1. Nella finestra di dialogo **Messaggio**, sotto **Testo**, immetti **Specifico del canale** e seleziona **OK**.
1. Selezionare **Salva**, quindi selezionare **Anteprima** per visualizzare l'anteprima della pagina. Il banner promozionale dovrebbe indicare "Specifico del canale".
1. Selezionare **Fine modifica** per archiviare la pagina, quindi selezionare **Pubblica** per pubblicarla.

Se quindi utilizzi l'URL di base del canale e vai all'URL della pagina multicanale in quel sito, vedrai il contenuto specifico del canale anziché il contenuto multicanale.

## <a name="additional-resources"></a>Risorse aggiuntive

[Modalità di aggiungere contenuti](add-manage-content.md)

[Glossario del modello di pagina](page-elements-overview.md)

[Stato e ciclo di vita documento](document-states-overview.md)

[Utilizzare i gruppi di pubblicazione](publish-groups.md)
