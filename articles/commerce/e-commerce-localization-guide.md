---
title: Guida alla localizzazione e-commerce di Dynamics 365 Commerce
description: Questo argomento descrive come localizzare un sito di e-commerce Microsoft Dynamics 365 Commerce in lingue aggiuntive e configurare il sito per supportare più canali.
author: bicyclingfool
ms.date: 04/29/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2017-06-20
ms.openlocfilehash: 1e9d91036ceeb9161dc8ee903532b2cf3ca435e2
ms.sourcegitcommit: 26c726bd0b00935e3d2c31fdc5a3b2ae03a8a2b0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2022
ms.locfileid: "8661527"
---
# <a name="dynamics-365-commerce-e-commerce-localization-guide"></a>Guida alla localizzazione e-commerce di Dynamics 365 Commerce

[!include [banner](includes/banner.md)]

Questo argomento descrive come localizzare un sito di e-commerce Microsoft Dynamics 365 Commerce in lingue aggiuntive e configurare il sito per supportare più canali, e copre anche i concetti e la terminologia relativi al processo.

Le funzionalità di e-commerce in Dynamics 365 Commerce sono state progettate per consentire esperienze online che possono essere adattate a paesi e lingue specifici, ma allo stesso tempo consentono il massimo riutilizzo di modelli, pagine, contenuti e media. Puoi anche creare un sito di base e poi espanderti in nuovi mercati aggiungendo il supporto per paesi e lingue aggiuntivi nel tempo.

## <a name="definitions"></a>Definizioni

**Impostazioni locali, identificatore delle impostazioni locali**: le impostazioni locali (note anche come identificatore di impostazioni locali) definisce una lingua associata a un paese o un'area. Ad esempio, l'identificatore delle impostazioni locali "fr-ca" è associato al francese canadese.

**Lingua di base**: la lingua in cui sviluppi il contenuto del tuo sito prima di esportarlo per la localizzazione.

**Canale, punto vendita online**: un canale (noto anche come punto vendita online) definisce i metodi di pagamento, i gruppi di prezzi, le gerarchie di prodotti, gli assortimenti e i prodotti per una vetrina di e-commerce online.

## <a name="concepts"></a>Concetti

### <a name="url-driven-experience"></a>Esperienza basata su URL

I siti di e-commerce Dynamics 365 Commerce offrono ai clienti esperienze localizzate e commercializzate uniche attraverso canali e identificatori delle impostazioni locali. I canali definiscono i prodotti, le categorie, le valute e i metodi di pagamento univoci per un mercato e gli identificatori delle impostazioni locali determinano la lingua del contenuto visualizzato dai clienti. Un sito di e-commerce utilizza gli URL per differenziare tra esperienze commercializzate e localizzate. Gli URL del sito per queste esperienze uniche di canale e impostazioni locali sono definiti per un sito nella pagina **Impostazioni del sito \>  Canali** nel generatore di siti Dynamics 365 Commerce.

Nel generatore di siti, un URL è una combinazione di dominio e percorso che definisce il punto di ingresso per una combinazione univoca di canale e impostazioni locali. Nell'esempio seguente, un negozio online fittizio chiamato Fabrikam Inc. definisce quattro combinazioni univoche di canale e impostazioni locali e associa ciascuna combinazione a un URL univoco che offre contenuti ai clienti.

| Dominio                     |  Percorso      | Canale       |   Impostazioni locali     |
|------------------------|--------|--------------------------------|--------|
| `https://fabrikam.com` | /      | Negozio online esteso Fabrikam | it  |
| `https://fabrikam.com` | /es    | Negozio online esteso Fabrikam | es     |
| `https://fabrikam.ca`  | /      | Punto vendita online Contoso    | fr-ca  |
| `https://fabrikam.ca`  | /en-ca | Punto vendita online Contoso    | en-ca  |

#### <a name="domain"></a>Dominio

I domini vengono stabiliti quando configuri il tuo sito di e-commerce in Microsoft Dynamics Lifecycle Services (LCS). Dopo aver eseguito il provisioning dell'ambiente di e-commerce, puoi aggiungere più domini aprendo una richiesta di servizio. Per ulteriori informazioni su come impostare i domini per il tuo sito di e-commerce, vedi [Domini in Dynamics 365 Commerce](domains-commerce.md).

#### <a name="path"></a>Percorso

- Un percorso è una stringa arbitraria che, in combinazione con il dominio, viene mappata a una combinazione univoca di canale e impostazioni locali. Nell'esempio precedente, la stringa utilizzata come percorso corrisponde all'identificatore delle impostazioni locali a cui è mappato il percorso. Tuttavia, puoi utilizzare un approccio diverso.
- È possibile mappare una combinazione di canale e impostazioni locali a un dominio e un percorso vuoto ("/"). Nell'esempio precedente, i clienti che visitano `https://fabrikam.ca/` riceveranno i prodotti e gli assortimenti per il mercato canadese in francese canadese.
- Il generatore di siti commerciali ti impedisce di creare combinazioni duplicate di un dominio e un percorso. Tuttavia, puoi mappare combinazioni duplicate di canale e impostazioni locali a una diversa combinazione di dominio e percorso.

#### <a name="channel"></a>Canale

- I canali (noti anche come negozi online) definiscono i metodi di pagamento, i gruppi di prezzi, le gerarchie di prodotti, gli assortimenti e i prodotti per una vetrina di e-commerce online.
- I canali sono definiti, configurati e pubblicati in Dynamics 365 Commerce headquarters.
- Il generatore di siti può rilevare i negozi online che sono stati configurati in Commerce headquarters e sono disponibili per essere mappati a un sito.

Per ulteriori informazioni sui canali, vedi [Panoramica dei canali](channels-overview.md). Per ulteriori informazioni su come configurare un canale online, vedi [Impostare un canale online](channel-setup-online.md).

#### <a name="locale"></a>Impostazioni locali

- Le impostazioni locali sono l'identificatore effettivo utilizzato quando si trasferiscono file XLIFF (XML Localization Interchange File Format) per la localizzazione. Le impostazioni locali sono definite e pubblicate per ciascun canale in Commerce headquarters. Per informazioni su come configurare lingue e canali nel generatore di siti vedi la sezione successiva.
- Le stesse impostazioni locali possono essere mappate a più canali. In questo modo, una lingua comune può essere offerta su più mercati.

## <a name="configure-languages-and-channels-for-your-e-commerce-site"></a>Configurare lingue e canali per il sito e-commerce

Per impostazione predefinita, tutti i siti di e-commerce Dynamics 365 Commerce sono configurati per utilizzare un unico canale online e un'unica lingua, indipendentemente dal fatto che inizi con il sito demo Fabrikam o crei un nuovo sito da zero.

In questa configurazione, i clienti e i partner in genere sviluppano tutte le risorse che verranno utilizzate in tutti i paesi e le lingue. Queste risorse includono modelli, pagine, frammenti, contenuti e file multimediali. Tutto il contenuto del sito viene sviluppato nella prima lingua che hai selezionato per il tuo sito oppure, se stai utilizzando il sito demo Fabrikam, il contenuto del sito verrà sviluppato in inglese.

![Sito di e-commerce Dynamics 365 Commerce predefinito](media/loc-guide-1.png)

> [!NOTE]
> È possibile configurare il sito demo Fabrikam per una lingua aggiuntiva in modo che lo sviluppo del contenuto possa essere eseguito in tale lingua. Per informazioni su come aggiungere una nuova lingua a un sito e un canale, vedi la sezione [Configurare una lingua aggiuntiva per il sito](#configure-an-additional-language-for-your-site) più avanti in questo argomento.

Tuttavia, il sistema di gestione dei contenuti (CMS) e il modello di pagina per i siti di e-commerce Dynamics 365 Commerce sono stati progettati per consentire l'espansione in nuovi mercati e impostazioni locali. Pertanto, attraverso un unico sito e-commerce, puoi gestire gli asset per un negozio online che abbraccia più mercati e lingue.

![Sito di e-commerce Dynamics 365 Commerce per più mercati e lingue](media/loc-guide-2.png)

### <a name="configure-an-additional-language-for-your-site"></a>Configurare una lingua aggiuntiva per il sito

Il processo di configurazione di una nuova lingua per un sito di e-commerce prevede tre passaggi.

#### <a name="step-1-add-the-language-to-your-channel-online-store-in-commerce-headquarters"></a>Passaggio 1: aggiungi la lingua al tuo canale (negozio online) in Commerce headquarters

1. In Commerce headquarters, vai al canale a cui vuoi aggiungere la nuova lingua. Seleziona **Retail e Commerce \> Canali \> Punti vendita online** per trovare l'elenco dei canali configurati in Commerce headquarters.
1. Apri il negozio online che è mappato al tuo sito selezionando il valore **ID canale di vendita al dettaglio**. Puoi verificare il negozio online che è mappato al tuo sito aprendo la pagina **Canali** delle impostazioni del sito nel generatore di siti di Commerce e guardando il nome del negozio online nella colonna **Canali**. 
1. Nella Scheda dettaglio **Lingue** selezionare **Aggiungi**. Nel campo **Lingua** seleziona il codice impostazioni locali per la nuova lingua. Quindi selezionare **Salva**.
1. Vai a **Vendita al dettaglio e commercio \> Vendita al dettaglio e commercio IT \> Programmazione della distribuzione**, ed esegui il processo **1070 Configurazione del canale**. Al termine dell'esecuzione del processo, puoi passare al passaggio 2 e aggiungere la lingua a un canale per il tuo sito nel generatore di siti.

![La scheda dettaglio Lingue di un negozio online in Commerce headquarters](media/loc-guide-3.png)

#### <a name="step-2-add-the-language-to-a-channel-in-site-builder"></a>Passaggio 2: aggiungi la lingua a un canale nel generatore di siti

Per aggiungere una lingua a un canale nel generatore di siti, attieniti alla seguente procedura.

1. Nel generatore di siti di Commerce apri il tuo sito, quindi apri la pagina **Canali** nelle impostazioni del sito.
1. Selezionare il nome del canale a cui vuoi aggiungere la lingua.
1. Nel riquadro di destra, seleziona **Aggiungi impostazioni locali**.
1. Nella finestra di dialogo **Aggiungi impostazioni locali**, sotto **Aggiungi impostazioni locali** seleziona la lingua che hai precedentemente aggiunto al canale in Commerce headquarters.
1. Seleziona il dominio e il percorso che i clienti richiederanno per visualizzare il tuo sito in questo canale e in questa lingua.
1. Se si desidera che la lingua sia la lingua predefinita per la visualizzazione, la creazione e l'aggiornamento di pagine e frammenti del generatore di siti, seleziona la casella di controllo **Utilizza come lingua del canale di creazione predefinita**. 
    > [!NOTE]
    > Questa impostazione ha effetto solo nel generatore di siti. Non riguarda l'esperienza del sito pubblicato per i tuoi clienti.
1. Seleziona **OK**.
1. Selezionare **Salva e pubblica**.

#### <a name="step-3-localize-your-site-content"></a>Passaggio 3: localizza i contenuti del tuo sito

Quando torni alla visualizzazione **Pagine** nel generatore di siti di Commerce, la nuova lingua sarà disponibile nel canale e nel selettore delle impostazioni locali in alto a destra. Ora puoi creare versioni localizzate delle pagine nella tua lingua di base.

Il processo per localizzare il contenuto delle tue pagine e frammenti è trattato nella sezione [Localizzare il contenuto del sito di e-commerce](#localize-e-commerce-site-content) più avanti in questo argomento.

### <a name="configure-a-new-channel-for-your-site"></a>Configurare un nuovo canale per il sito

I siti di e-commerce Dynamics 365 Commerce possono offrire esperienze definite su più canali online configurati in Commerce headquarters. Un sito utilizza più canali per mostrare ai clienti una configurazione univoca di metodi di pagamento, gruppi di prezzi, gerarchie di prodotti, assortimenti e una serie di prodotti. Un canale viene in genere utilizzato per configurare queste dimensioni per soddisfare i requisiti e le preferenze per l'esperienza associata ai singoli paesi. Tuttavia, questo approccio è una decisione aziendale presa dal cliente. Non è un requisito.

I prerequisiti e le attività associati all'impostazione di un canale (negozio online) esulano dall'ambito di questo documento. Per ulteriori informazioni su come configurare un canale online in Commerce headquarters, vedi [Nozioni di base sull'impostazione dei canali](channels-overview.md#channel-setup-basics). Per informazioni sui passaggi e sui requisiti specifici dei canali online, vedi [Creare un canale online](channel-setup-online.md).

Per aggiungere un canale al sito nel generatore di siti, attieniti alla seguente procedura.

1. Nel generatore di siti di Commerce vai a **Impostazioni sito \> Canali**. 
1. Seleziona **Aggiungi un canale**.
1. Nella finestra di dialogo **Aggiungi un canale**, sotto **Canale** seleziona il canale che vuoi aggiungere. 
    > [!NOTE]
    > Puoi aggiungere solo canali che non sono già stati aggiunti al tuo sito.
1. Seleziona le impostazioni locali predefinite per il canale. Se aggiungi nuove lingue al canale, puoi cambiare la lingua predefinita con una di esse.
1. Specifica il dominio e il percorso che costituiranno l'URL che offre contenuti ed esperienze per questa combinazione di canale e lingua.
1. Seleziona **OK**.
1. Selezionare **Salva e pubblica**.

## <a name="localize-e-commerce-site-content"></a>Localizzare il contenuto del sito di e-commerce

### <a name="xliff-basics"></a>Nozioni di base su XLIFF

XLIFF è un formato di file standard del settore per il passaggio di contenuti localizzabili tra gli strumenti di gestione dei contenuti. Il generatore di siti di Commerce utilizza il formato file XLIFF per esportare il contenuto dei metadati di pagine, frammenti e immagini in modo che possa essere localizzato e reimportato.

I clienti Microsoft Dynamics in genere lavorano con fornitori di localizzazione di terze parti come [Translated.com](https://translated.com/welcome) per tradurre i propri file XLIFF nelle lingue richieste.

### <a name="localize-assets-in-site-builder"></a>Localizzare le risorse nel generatore di siti

I seguenti asset del sito di e-commerce possono essere localizzati nel generatore di siti:

- Pagine
- Frammenti
- Risorse multimediali
- Moduli

Tutte le nuove pagine, frammenti e risorse multimediali vengono creati nel contesto del canale e della lingua attualmente selezionati nel selettore canale e impostazioni locali. Questa lingua è solitamente la tua "lingua di base", a condizione che tu non abbia configurato lingue o canali aggiuntivi. Nei siti in cui sono configurati più canali e lingue, la "lingua di base" è definita dal canale e dalle impostazioni locali che hai impostato come predefinite nella pagina **Canali** nelle impostazioni del sito.

I passaggi per la localizzazione del contenuto per pagine, frammenti e risorse multimediali sono simili. Eccezioni e differenze verranno evidenziate nei paragrafi che seguono. Tuttavia, i passaggi per la localizzazione del contenuto del modulo differiscono. Per ulteriori informazioni, vedi la sezione [Localizzare i moduli](#localize-modules) più avanti in questo argomento.

#### <a name="step-1-export-an-xliff-file"></a>Passaggio 1: esporta un file XLIFF

Per esportare un file XLIFF per una pagina, un frammento o un'immagine nel generatore di siti, segui questi passaggi.

1. Apri la risorsa per cui vuoi esportare il contenuto nella lingua di base, in modo che possa essere localizzata.
1. Sulla barra dei comandi, seleziona **Localizzazione \> Esporta XLIFF**.
    > [!NOTE]
    > L'opzione **Localizzazione** è visibile solo quando l'asset è nello stato **Modifica**.

Un file XLIFF denominato **\<assetname\>.xlf** verrà scaricato nella cartella di download del browser. Questo file XLIFF è specifico per la risorsa che stai localizzando. Esporterai un file XLIFF per ogni risorsa che desideri localizzare.

#### <a name="step-2-localize-the-xliff-file"></a>Passaggio 2: localizza il file XLIFF

Nella maggior parte dei casi, lavorerai con un fornitore di localizzazione per tradurre i tuoi file XLIFF. Tuttavia, se stai localizzando le risorse internamente o se desideri semplicemente testare il processo di localizzazione, devi apportare le seguenti modifiche a un file XLIFF:

- Aggiungi un attributo della lingua di destinazione all'elemento /xliff/file e imposta il valore sull'identificatore delle impostazioni locali della lingua in cui stai eseguendo la localizzazione. 
    > [!NOTE]
    > Questo identificatore di impostazioni locali deve corrispondere all'identificatore di impostazioni locali della pagina **Canali** nelle impostazioni del sito.
- Per ogni //elemento di origine, aggiungi un elemento gemello di destinazione in cui il valore del testo è la versione localizzata del contenuto di tale elemento di origine.

Per informazioni sullo schema che governa i file XLIFF, vedi la [Specifica XLIFF 1.2](http://docs.oasis-open.org/xliff/xliff-core/xliff-core.html).

> [!NOTE]
> Per localizzare una risorsa in più lingue, devi creare un file XLIFF localizzato per ciascuna di queste lingue.

#### <a name="step-3-import-the-localized-xliff-file"></a>Passaggio 3: importa il file XLIFF localizzato

Per importare un file XLIFF per una risorsa, attieniti alla seguente procedura.

1. Nel generatore di siti di Commerce apri la risorsa per cui desideri importare un file XLIFF.
1. Nel selettore di canali e impostazioni locali in alto a destra, seleziona il canale e la lingua per cui stai importando il contenuto localizzato.
1. Sulla barra dei comandi, seleziona **Localizzazione \> Importa XLIFF**. Quindi cerca e seleziona il file XLIFF localizzato per la risorsa e la lingua selezionate.

Dopo che il file XLIFF è stato importato correttamente, viene creata una "variante" della pagina, del frammento o della risorsa. Da quel momento in poi, tutte le modifiche apportate alla variante localizzata riguarderanno solo quella variante. Non influiranno sull'asset di base da cui è stata derivata la variante. Allo stesso modo, le modifiche alla risorsa di base non influiranno sulla variante di tale risorsa. 

Tuttavia, nel caso delle pagine, puoi apportare modifiche tra le varianti modificando il modello o il layout a cui tali pagine sono vincolate. Allo stesso modo, le modifiche a un frammento influiranno su tutte le pagine che dipendono da quella variante.

### <a name="images"></a>Immagini

Le immagini possono essere visualizzate in una pagina o in una variante del modulo solo se i metadati del contenuto associati a tali immagini sono localizzati. Attualmente, i seguenti metadati in una risorsa multimediale sono localizzabili:

- Testo alternativo
- Description
- Titolo

Al momento, non puoi localizzare il file binario per una risorsa digitale come un'immagine o un video. Il team del prodotto Dynamics 365 Commerce sta attualmente lavorando su questa funzionalità.

### <a name="localize-modules"></a>Localizzare i moduli

Le stringhe sottoposte al rendering come parte del modulo stesso (ad esempio, "Indietro" e "Avanti" in un modulo carosello) vengono localizzate separatamente dal contenuto del modulo. Per istruzioni, vedi [Localizzare un modulo](e-commerce-extensibility/localize-module.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Glossario del modello di pagina](page-elements-overview.md)

[Condivisione tra canali](cross-channel-sharing.md)

[Localizzare un modulo](e-commerce-extensibility/localize-module.md)

[File di definizione del modulo](e-commerce-extensibility/module-definition-file.md)

[Localizzare le risorse dell'estensione Commerce e file etichette](dev-itpro/extension-resource-localization.md)

[Globalizzare moduli utilizzando la classe CultureInfoFormatter](e-commerce-extensibility/globalize-modules.md)

[Impostazioni app: temi](e-commerce-extensibility/app-settings.md#themes-section)
