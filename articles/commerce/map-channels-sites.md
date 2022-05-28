---
title: Mappare i canali ai siti di e-commerce
description: Questo argomento descrive alcuni degli scenari di mapping dei canali più comuni in Microsoft Dynamics 365 Commerce che possono essere estrapolati per la maggior parte degli altri requisiti aziendali.
author: samjarawan
ms.date: 05/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 8ce272d63b4a37f99661333a02434708205ea19a
ms.sourcegitcommit: e4cc43b06ef3f0f562849e2c960025cb244d6017
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2022
ms.locfileid: "8743586"
---
# <a name="map-channels-to-e-commerce-sites"></a>Mappare i canali ai siti di e-commerce

Questo argomento descrive alcuni degli scenari di mapping dei canali più comuni in Microsoft Dynamics 365 Commerce che possono essere estrapolati per la maggior parte degli altri requisiti aziendali.

Dynamics 365 Commerce supporta molti scenari aziendali per il mapping dei [canali online](#channels) che hanno un set configurato di prodotti, prezzi e sconti alle esperienze del [sito di e-commerce](#e-commerce-sites) per i clienti.

Questo argomento copre i seguenti scenari:

- **Un canale in un'unica lingua con un'unica esperienza del sito di e-commerce.** Ad esempio, questo scenario potrebbe coinvolgere un sito con marchio singolo configurato per il mercato inglese statunitense.
- **Un canale in più lingue con un'unica esperienza del sito localizzata.** Ad esempio, questo scenario potrebbe coinvolgere un sito con marchio singolo configurato per il Canada con supporto per le lingue inglese e francese. In questo scenario, gli utenti che selezionano lingue diverse hanno la stessa esperienza del sito, ma è localizzata nella lingua selezionata di ogni utente.
- **Un canale in più lingue con un'esperienza del sito diversa per lingua.** Ad esempio, questo scenario potrebbe coinvolgere un sito con marchio singolo configurato per il Canada con supporto per le lingue inglese e francese. In questo scenario, esiste un'esperienza del sito unica per ogni lingua.
- **Canali multipli (in una lingua e/o in più lingue) che hanno un'unica esperienza di sito localizzata.** Ad esempio, questo scenario potrebbe coinvolgere un sito con marchio singolo configurato per l'Australia e la Nuova Zelanda. In questo scenario, entrambi i paesi condividono la stessa esperienza del sito in inglese, ma ogni paese è configurato con prodotti, valuta, prezzi, sconti e modalità di spedizione diversi.
- **Canali multipli (in una lingua e/o in più lingue) che hanno un'esperienza di sito diversa per canale.** Ad esempio, questo scenario potrebbe coinvolgere un sito con marchio singolo configurato per l'Australia, il Canada e la Germania in più lingue. In questo scenario, ogni paese ha un'unica esperienza del sito configurata con prodotti, valuta, prezzi, sconti e modalità di spedizione diversi.

## <a name="channels"></a>Canali

Un canale (noto anche come negozio online o canale online) rappresenta una vetrina di e-commerce online utilizzata per mappare prodotti, prezzi, sconti, lingue, metodi di pagamento, modalità di consegna, centri logistici e altri aspetti dell'esperienza online che sarà disponibile per i tuoi clienti e-commerce. I canali vengono creati e gestiti in Commerce headquarters e mappati a un'unica [persona giuridica](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json#legal-entities). La persona giuridica ha generalmente sede in un unico paese che richiede la dichiarazione fiscale per il canale e può essere configurata con una sola valuta.

Per ulteriori informazioni sui canali, vedi [Panoramica dei canali](channels-overview.md). Per ulteriori informazioni su come creare un canale online, vedi [Impostare un canale online](channel-setup-online.md).

L'illustrazione di esempio seguente da Commerce headquarters mostra i canali online predefiniti che vengono distribuiti con Dynamics 365 Commerce se è selezionata l'opzione dati demo.

![Canali dati demo predefiniti in Commerce headquarters.](media/channel-mapping-1.png)

## <a name="e-commerce-sites"></a>Siti di e-commerce

Un sito di e-commerce contiene un insieme di pagine del sito che i clienti utilizzano per navigare e fare acquisti. I siti di e-commerce sono gestiti in Commerce site builder.

Per ulteriori informazioni su come creare e gestire siti in Site Builder, vedere [Panoramica del sito di e-commerce](online-store-overview.md).

## <a name="common-channel-mapping-scenarios"></a>Scenari comuni di mapping dei canali

Dynamics 365 Commerce supporta un'ampia gamma di scenari di mapping dei canali. Gli scenari di mapping dei canali che seguono sono solo un sottoinsieme di tutti i possibili scenari di mapping dei canali. Sono intesi come una guida per aiutarti a pianificare qualsiasi scenario aziendale unico che hai. Il fittizio negozio di articoli sportivi Adventure Works incluso con i dati demo di Dynamics 365 Commerce viene utilizzato come esempio per ogni scenario.

### <a name="single-language-channel-that-has-a-single-e-commerce-site-experience"></a>Un canale in un'unica lingua con un'unica esperienza del sito di e-commerce

Nello scenario più elementare, un singolo canale ha un'unica lingua per vendere in un mercato unico. Un esempio per questo scenario è un negozio online Adventure Works configurato solo per il mercato inglese statunitense.

Nell'illustrazione di esempio seguente viene mostrata la configurazione di un canale in Commerce headquarters. In questa configurazione, il canale online supporta una sola lingua (**en-us**), una valuta unica (**Dollaro statunitense**) e un'unica entità aziendale (**usrt**) utilizzata per la dichiarazione dei redditi.

![Valori della persona giuridica, della valuta e della lingua per il negozio online Adventure Works evidenziati in Commerce headquarters.](media/channel-mapping-3.png)

Il singolo canale online può essere mappato su un singolo sito di e-commerce in Site Builder. Per informazioni su come creare un nuovo sito e mapparlo su un canale, vedi la sezione [Mappare un canale a un sito in Site Builder](#map-a-channel-to-a-site-in-site-builder) di questo argomento.

### <a name="multi-language-channel-that-has-a-single-localized-site-experience"></a>Un canale in più lingue con un'unica esperienza del sito localizzata

In questo scenario, un singolo canale supporta più di una lingua. Pertanto, i nomi dei prodotti, le descrizioni e gli attributi possono essere localizzati in Commerce headquarters. Per fornire un'esperienza completa del sito localizzato, i contenuti di marketing sul sito possono anche essere localizzati in Commerce Site Builder.

Il limite di questo scenario è che un singolo canale può essere configurato con una sola valuta, una sola persona giuridica e un insieme di prodotti e prezzi. Questa configurazione funziona meglio per i paesi che hanno un'unica valuta e più lingue (ad esempio, il Canada, che ha le lingue inglese e francese), un'unica persona giuridica e un unico insieme di prodotti e prezzi.

Ciascuna lingua in un canale può essere configurata con il proprio nome di dominio. Ad esempio, il dominio `www.adventure-works.ca` può essere configurato per la versione inglese canadese e il dominio `www.adventure-works-fr.ca` può essere configurato per la versione francese canadese. In alternativa, è possibile configurare lingue diverse in un canale in un unico dominio, quindi è possibile utilizzare un percorso diverso per ciascuna lingua. Ad esempio, il dominio `www.adventure-works.ca` può essere configurato per la versione inglese canadese e quindi il percorso `www.adventure-works.ca/fr` può essere utilizzato per la versione francese canadese. Il [rilevamento geografico](geo-detection-redirection.md) può anche essere abilitato per reindirizzare automaticamente un utente al sito corretto, in base alla posizione dell'utente.

Per informazioni su come consentire ai clienti di passare manualmente da una lingua all'altra, vedere la sezione [Aggiungere e configurare il modulo di selezione del sito](#add-and-configure-the-site-picker-module) di questo argomento. Per informazioni su come personalizzare pagine e frammenti localizzati, vedere la sezione [Gestire il contenuto del sito con più canali e lingue](#manage-site-content-that-has-multiple-channels-and-languages).

### <a name="multi-language-channel-that-has-a-different-site-experience-per-language"></a>Un canale in più lingue con un'esperienza del sito diversa per lingua

Potresti preferire uno scenario in cui un singolo canale supporta più di una lingua, ma per ogni lingua viene visualizzata un'esperienza del sito completamente diversa. Il metodo consigliato per l'implementazione di questo scenario consiste nell'utilizzare [varianti di pagina](#implement-page-variants-for-each-language) su un unico sito.

Un altro metodo consiste nel creare un nuovo sito di e-commerce per ogni lingua in Site Builder, quindi mappare ogni sito a un singolo canale online e lingua. Il risultato sarà un unico canale online mappato su più siti di e-commerce, uno per ogni lingua. Questo metodo per più siti richiede risorse di gestione aggiuntive, perché ci sarà più di un sito da gestire in Site Builder.

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-single-localized-site-experience"></a>Canali multipli (in una lingua e/o in più lingue) che hanno un'unica esperienza di sito localizzata

Un sito con marchio potrebbe richiedere più canali online per area geografica per supportare una valuta, un insieme di prodotti e un insieme di prezzi diversi per ciascun canale in un unico sito. Ad esempio, il sito Adventure Works potrebbe avere un canale online per il mercato canadese che ha più lingue, un canale per il mercato statunitense che ha una lingua e un canale per il mercato tedesco che ha una lingua. In questo scenario, ogni canale online sarà configurato per una persona giuridica specifica dell'area geografica e può avere lo stesso insieme di prodotti degli altri canali, un sottoinsieme di tali prodotti o un insieme diverso di prodotti. Ogni canale avrà anche i propri prezzi nella valuta dell'area geografica, tasse, sconti e modalità di spedizione.

In questo scenario, ogni mercato può essere configurata con i propri nomi di dominio. Ad esempio, il dominio `www.adventure-works.com` può essere configurato per il mercato statunitense e il dominio `www.adventure-works.de` può essere configurato per il mercato tedesco. In alternativa, ogni mercato può essere configurato per utilizzare un percorso diverso. Ad esempio, il dominio `www.adventure-works.com` può essere configurato per il mercato statunitense e il percorso `www.adventure-works.com/de` può essere utilizzato per il mercato tedesco. Il [rilevamento geografico](geo-detection-redirection.md) può anche essere abilitato per reindirizzare automaticamente gli utenti al sito corretto, in base alla loro area geografica.

Potresti anche volere che il tuo sito fornisca un elenco a discesa che consenta agli utenti di passare manualmente a un mercato specifico. Per ulteriori informazioni, vedere la sezione [Aggiungere e configurare il modulo di selezione del sito](#add-and-configure-the-site-picker-module) di questo argomento.

Per informazioni su come configurare più canali in un unico sito, vedere la sezione [Configurare più canali su un sito di e-commerce](#configure-multiple-channels-on-an-e-commerce-site).

### <a name="multiple-channels-single-language-andor-multi-language-that-have-a-different-site-experience-per-channel"></a>Canali multipli (in una lingua e/o in più lingue) che hanno un'esperienza di sito diversa per canale.

È consigliabile avere più canali per un singolo marchio in aree geografiche diverse e che ogni area geografica abbia un'esperienza del sito diversa. Esistono due metodi per implementare questo scenario:

- Utilizzare le [varianti di pagina](#implement-page-variants-for-each-language).
- Configura un sito diverso per ogni canale online in Site Builder, quindi mappa ogni sito a un canale e una lingua online diversi. Questo metodo richiede risorse di gestione aggiuntive, perché ci sarà più di un sito da gestire in Site Builder.

## <a name="cross-channel-sharing"></a>Condivisione tra canali

La condivisione multicanale è utile quando più canali in un unico sito possono condividere contenuto. Ad esempio, un rivenditore che ha più marchi e vetrine raggruppate in un unico sito può condividere contenuto tra alcune o tutte le vetrine. Il contenuto condiviso può includere pagine per termini e condizioni, termini di pagamento, metodi di spedizione e domande frequenti (FAQ). Per ulteriori informazioni, vedere [Abilitare e utilizzare la condivisione multicanale](cross-channel-sharing.md).

## <a name="map-a-channel-to-a-site-in-site-builder"></a>Mappare un canale a un sito in Site Builder

Esistono diversi metodi per creare e configurare i siti per utilizzare diversi canali online.

### <a name="create-a-new-site"></a>Creare un nuovo sito

Puoi creare un sito nuovo di zecca in Site Builder passando alla pagina elenco **Siti** e selezionando **Nuovo sito**. Quindi, nella finestra di dialogo **Nuovo sito** visualizzata, è possibile selezionare il canale online e la lingua predefiniti per il sito, come mostrato nell'illustrazione di esempio seguente.

![Creazione di un nuovo canale in Site Builder.](media/channel-mapping-4.png)

Il sito che crei in questo modo sarà vuoto e non includerà alcuna pagina del sito (ad esempio, una home page, pagine di categoria e pagine di prodotto).

Per ulteriori informazioni, vedere [Creare un sito di e-commerce](create-ecommerce-site.md).

### <a name="create-a-new-site-by-using-the-site-copy-operation"></a>Creare un nuovo sito utilizzando l'operazione di copia del sito

Invece di creare un nuovo sito vuoto come descritto nella sezione precedente, è consigliabile iniziare con una copia di uno dei siti iniziali forniti nella libreria del modulo Commerce, ad esempio il sito Fabrikam o Adventure Works.

Per copiare un sito esistente, vai alla pagina elenco **Siti** in Site Builder e seleziona **Copia sito**. Quindi, nella finestra di dialogo **Copia sito** visualizzata, è possibile selezionare il sito di origine e specificare il nome del sito di destinazione.

A questo punto, non puoi ancora selezionare il canale online e la lingua predefiniti per il sito. Tuttavia, è possibile configurare tali proprietà al termine dell'operazione di copia del sito. Quando selezioni per la prima volta il sito nella pagina elenco **Siti** in Site Builder , viene visualizzata la finestra di dialogo **Configura il sito** in cui è possibile selezionare il canale e la lingua predefiniti.

Per ulteriori informazioni sull'operazione di copia del sito, vedere [Copiare un sito di e-commerce](copy-ecommerce-site.md).

### <a name="manage-an-existing-site-channel"></a>Gestire un canale del sito esistente

Dopo che un sito è stato configurato con un canale, puoi gestire e aggiornare il canale dall'interno del sito selezionato in Site Builder in **Impostazioni del sito \> Canali**, come mostrato nell'illustrazione di esempio seguente.

![Gestione del mapping dei canali in Site Builder.](media/channel-mapping-7.png)

## <a name="support-multiple-sites-in-a-single-tenant"></a>Supportare più siti in un unico tenant

Molti siti con marchio possono coesistere in un unico tenant. L'illustrazione di esempio seguente mostra tre diversi siti con marchio (Adventure Works, Adventure Works Business e Fabrikam), ognuno dei quali è mappato a un canale online singolo diverso.

![Elenco dei siti in Site Builder.](media/channel-mapping-8.png)

## <a name="configure-a-single-domain-name-with-paths-for-multiple-sites"></a>Configurare un singolo nome di dominio con percorsi per più siti

Un singolo nome di dominio può essere utilizzato per più siti e i percorsi possono quindi essere utilizzati per separare i siti o le lingue. Ad esempio, il dominio `www.mycompany.com` è configurato per due diversi siti di e-commerce: uno per Fabrikam e uno per Adventure Works. In questo caso, il percorso predefinito (`www.mycompany.com`), noto anche come percorso vuoto, può essere utilizzato per il sito Fabrikam e un altro percorso (ad esempio, `www.mycompany.com/adventureworks`) può essere utilizzato per il sito Adventure Works. Un'altra opzione consiste nell'utilizzare un percorso personalizzato (ad esempio, `www.mycompany.com/fabrikam`) invece del percorso predefinito anche per il sito Fabrikam.

In alternativa, è possibile utilizzare un nome di dominio diverso per ogni sito (ad esempio, `www.adventure-works.com` e `www.fabrikam.com`). I percorsi possono quindi essere utilizzati per diverse lingue o aree geografiche (ad esempio, `www.adventure-works.com/fr-ca` per il Canada francese).

## <a name="configure-multiple-languages-on-a-site"></a>Configurare più lingue su un sito

Le lingue possono essere configurate per il sito di e-commerce in Site Builder in **Impostazioni sito \> Canali**. Nell'illustrazione di esempio seguente, ogni lingua è stata configurata utilizzando le impostazioni locali per il percorso, in modo che ogni lingua disponga di un URL univoco.

![Più lingue configurate su un sito.](media/channel-mapping-10.png)

Per aggiungere una nuova lingua del canale, vai a **Impostazioni sito \> Canali** e seleziona il collegamento al canale. Nel riquadro che appare a destra, seleziona **Aggiungi un'impostazione locale** per selezionare il canale e l'impostazione locale che desideri aggiungere. Quindi specifica il percorso da utilizzare per il canale selezionato.

### <a name="add-and-configure-the-site-picker-module"></a>Aggiungere e configurare il modulo di selezione del sito

Dopo aver configurato un sito con più lingue e/o canali, è consigliabile aggiungere un selettore di lingua all'intestazione della pagina del sito, in modo che gli utenti possano selezionare manualmente la lingua o il Paese. Il [modulo di intestazione](author-header-module.md) della libreria di moduli ha il supporto integrato per consentire agli utenti di selezionare una lingua utilizzando il [modulo di selezione del sito](site-selector.md). Il modulo di selezione sito può essere aggiunto al modulo di intestazione nel frammento di intestazione.

Per ulteriori informazioni su come aggiungere e configurare il modulo di selezione del sito, vedi [Modulo di selezione del sito](site-selector.md).

### <a name="implement-page-variants-for-each-language"></a>Implementare varianti di pagina per ciascuna lingua

In questo scenario è presente un solo canale, ma sono presenti più lingue. Puoi modificare l'aspetto di una pagina in base alla lingua selezionata creando una variante di pagina per essa. È quindi possibile aggiungere contenuto localizzato alla variante.

Quando hai una pagina aperta in Site Builder e selezioni il collegamento in alto a destra che mostra il canale e la lingua correnti, viene visualizzato un selettore di canale e lingua, come mostrato nell'illustrazione di esempio seguente. Se desideri sostituire la pagina per la lingua corrente, seleziona un'altra lingua, quindi seleziona **Modifica**. Puoi anche cambiare il canale se stai [gestendo un sito che ha più canali e lingue](#manage-site-content-that has-multiple-channels-and-languages).

![Modifica della lingua per una pagina in Site Builder.](media/channel-mapping-14.png)

Se la variante per la pagina o il frammento selezionato non è stata ancora creata, viene visualizzato un messaggio di avviso, come mostrato nell'illustrazione di esempio seguente. In questo caso, seleziona il collegamento **Crea variante di pagina** nel testo del messaggio. La finestra di dialogo che appare fornisce opzioni che ti consentono di iniziare con una copia di una variante esistente o di creare una pagina nuova di zecca da un modello.

![Richiedere la creazione di una variante di pagina in Site Builder](media/channel-mapping-16.png)

Se non crei una variante, la pagina originale viene visualizzata e mostra la lingua appropriata per le stringhe dei moduli e le informazioni sul prodotto da Commerce headquarters. Tuttavia, se il testo come il titolo di una pagina o altro contenuto di marketing è stato specificato direttamente nei moduli di pagina predefiniti, le stringhe per quel testo rimarranno nella lingua originale.

Invece di creare manualmente ogni pagina e ogni frammento, puoi esportare ogni pagina e ogni frammento in un file XML Localization Interchange File Format (XLIFF) che può quindi essere inviato per la localizzazione. Dopo che ogni XLIFF è stato localizzato, può essere importato come variante di pagina localizzata. Per esportare un file XLIFF da una pagina o da un frammento in Site Builder, o per importare un file XLIFF in una pagina o in un frammento, seleziona **Localizzazione** sulla barra dei comandi. Quindi seleziona **Esporta XLIFF** o **Importa XLIFF**, come mostrato nell'illustrazione di esempio seguente.

![Importazione o esportazione di una pagina o di un frammento in formato XLIFF.](media/channel-mapping-18.png)

## <a name="manage-site-content-that-has-multiple-channels-and-languages"></a>Gestire il contenuto del sito con più canali e lingue

Un sito con più canali e/o lingue memorizza una variante univoca di ogni pagina e frammento per ogni combinazione di canale e lingua. Questo comportamento consente alle varianti di pagina di contenere dati localizzati, ma offre anche la flessibilità di modificare l'aspetto di una pagina per una variante specifica.

Per informazioni su come lavorare con le varianti di pagina, vedi la sezione [Implementare varianti di pagina per ciascuna lingua](#implement-page-variants-for-each-language) di questo argomento.

## <a name="configure-multiple-channels-on-an-e-commerce-site"></a>Configurare più canali su un sito di e-commerce

Puoi aggiungere canali a un sito di e-commerce in Site Builder andando su **Impostazioni del sito \> Canali** e selezionando **Aggiungi un canale**. Quindi, nella finestra di dialogo **Aggiungi un canale** che appare puoi selezionare il canale online e le impostazioni locali predefinite.

## <a name="additional-resources"></a>Risorse aggiuntive

[Panoramica dei canali](channels-overview.md)

[Impostare un canale online](channel-setup-online.md)

[Panoramica organizzazioni e gerarchie organizzative](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md)

[Impostare il rilevamento geografico e il reindirizzamento](geo-detection-redirection.md)

[Abilitare e utilizzare la condivisione multicanale](cross-channel-sharing.md)

[Creare un sito di e-commerce](create-ecommerce-site.md)

[Copiare un sito di e-commerce](copy-ecommerce-site.md)

[Modulo di selezione sito](site-selector.md)
