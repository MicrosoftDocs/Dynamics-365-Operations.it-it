---
title: Panoramica connettore pagamenti di Dynamics 365 per Adyen
description: Questo articolo fornisce una panoramica del connettore pagamenti di Microsoft Dynamics 365 per Adyen.
author: rassadi
ms.date: 11/16/2022
ms.topic: overview
audience: Application User, Developer, IT Pro
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2019-01-01
ms.openlocfilehash: 58d88e023b73ce19331bd6f54644a62d8f6f35af
ms.sourcegitcommit: 3aa3dedc3123cb079614762e2718841c2f7d7d35
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/30/2022
ms.locfileid: "9812088"
---
# <a name="dynamics-365-payment-connector-for-adyen-overview"></a>Panoramica connettore pagamenti di Dynamics 365 per Adyen

[!include [banner](../includes/banner.md)]

Questo articolo fornisce una panoramica del connettore pagamenti di Microsoft Dynamics 365 per Adyen e include un elenco completo di caratteristiche e funzionalità supportate. Gli articoli correlati trattano la registrazione di Adyen, la configurazione del connettore, le domande frequenti e la guida alla risoluzione dei problemi per alcuni problemi comuni.

## <a name="key-terms"></a>Termini importanti

| Termine | Description |
|---|---|
| Connettore pagamenti | Un'estensione che facilita la comunicazione tra Microsoft Dynamics 365 Commerce (e componenti associati) e un servizio di pagamento. Il connettore descritto in questo articolo è stato implementato utilizzando il kit SDK standard. |
| Carta presente | Fa riferimento alle transazioni di pagamento in cui una carta fisica viene presentata e utilizzata in un terminale di pagamento connesso al sistema POS di Dynamics 365. |
| Carta non assente | Si riferisce a transazioni di pagamento in cui non è presente una carta fisica, come scenari di e-commerce o call center. In questi scenari, le informazioni relative al pagamento vengono immesse manualmente su un sito Web di e-commerce, un flusso di call center o sul punto vendita o sul terminale di pagamento. |

## <a name="supported-features-functionality-versions-and-terminals"></a>Funzionalità, caratteristiche, versioni e terminali supportati

Il connettore pagamenti Dynamics 365 per Adyen predefinito utilizza l'SDK per i pagamenti standard. Pertanto, non ha funzionalità speciali che non sono disponibili anche per altri connettori di pagamento.

### <a name="supported-versions"></a>Versioni supportate

#### <a name="microsoft-dynamics-365-supported-versions"></a>Versioni supportate Microsoft Dynamics 365
Il connettore pagamenti Dynamics 365 per Adyen di proprietà è supportato in Microsoft Dynamics 365 Finance versione 8.1.3 (gennaio 2019) o successiva e in Microsoft Dynamics 365 Retail versione 8.1.3 o successiva. Tuttavia, terze parti possono ancora sviluppare altri connettori di pagamento per Adyen per versioni precedenti di Microsoft Dynamics 365.

#### <a name="supported-adyen-firmware-versions"></a>Versioni firmware Adyen supportate

L'elenco seguente descrive le versioni minime e massime del firmware Adyen supportate per ciascuna versione di Microsoft Dynamics 365 Retail POS.

---

# <a name="10025"></a>[10.0.25](#tab/10-0-25)
### <a name="dynamics-365-retail-pos-version-10025"></a>Dynamics 365 Retail POS versione 10.0.25
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_73p6 |

# <a name="10026"></a>[10.0.26](#tab/10-0-26)
### <a name="dynamics-365-retail-pos-version-10026"></a>Dynamics 365 Retail POS versione 10.0.26
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10027"></a>[10.0.27](#tab/10-0-27)
### <a name="dynamics-365-retail-pos-version-10027"></a>Dynamics 365 Retail POS versione 10.0.27
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p13 |

# <a name="10028"></a>[10.0.28](#tab/10-0-28)
### <a name="dynamics-365-retail-pos-version-10028"></a>Dynamics 365 Retail POS versione 10.0.28
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_73p6 | adyen_v1_75p22 |

# <a name="10029"></a>[10.0.29](#tab/10-0-29)
### <a name="dynamics-365-retail-pos-version-10029"></a>Dynamics 365 Retail POS versione 10.0.29
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

# <a name="10030"></a>[10.0.30](#tab/10-0-30)
### <a name="dynamics-365-retail-pos-version-10030"></a>Dynamics 365 Retail POS versione 10.0.30
| Versione minima del firmware Adyen | Versione massima del firmware Adyen |
| --- | --- |
| adyen_v1_71p16 | adyen_v1_78p6 |

---

> [!NOTE]
> Adyen potrebbe rilasciare aggiornamenti della versione secondaria dopo che Microsoft ha testato la versione principale. Finché è supportata una versione principale, è possibile avere aggiornamenti della versione secondaria all'interno della stessa versione principale. Questi aggiornamenti sono normalmente correzioni molto mirate e non soddisfano la richiesta per un nuovo test completo, a condizione che la stessa versione principale del firmware sia stata precedentemente testata. Gli aggiornamenti non devono superare la versione massima del firmware Adyen elencata nella documentazione. 
>
> La migrazione da una versione del firmware Adyen precedente alla versione 53 alla versione 53 richiede POS KB **4577957** per gli aggiornamenti mensili di Commerce, versioni da 10.0.11 a 10.0.14. Se una di queste versioni è in uso e non include l'hotfix, il post-aggiornamento del terminale di pagamento consentirà solo pagamenti tramite NFC. L'applicazione dell'aggiornamento rapido al POS risolve questo problema. Se la versione POS è precedente alla versione 10.0.11, presenta una richiesta di supporto notando che una correzione per KB **4577957** è richiesta per un MPOS fuori servizio.
> 
> Per le versioni del firmware Adyen da 59p7 a 62p9, l'operazione **gift card in uscita** richiede l'immissione del PIN due volte negli scenari in cui la gift card viene inserita manualmente. Questo problema non viene riprodotto quando la gift card viene strisciata. Adyen sta indagando. 

### <a name="supported-payment-terminals"></a>Terminali di pagamento supportati
Il connettore pagamenti Dynamics 365 per Adyen sfrutta [l'API del terminale di pagamento Adyen](https://www.adyen.com/blog/introducing-the-terminal-api) indipendente dal dispositivo. Supporta tutti i terminali di pagamento supportati da questa API. Per un elenco completo dei terminali di pagamento supportati, vedi la pagina [terminali POS Adyen](https://www.adyen.com/pos-payments/terminals).

Il seguente video descrive le funzionalità del terminale di pagamento Android Adyen Castles SE1.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE5bKeM]

### <a name="supported-payment-instruments"></a>Strumento di pagamento supportati

#### <a name="supported-debit-and-credit-cards"></a>Carte di debito e di credito supportate

| Marchio | Variante | Carta presente | e-commerce | Servizio clienti |
|---|---|:-:|:-:|:-:|
| MasterCard | Credito | ✔ | ✔ | ✔ |
| MasterCard | Dare | ✔ | ✔ | ✔ |
| MasterCard | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| MasterCard | Apple Pay | ✔ |  |  |
| MasterCard | Samsung Pay | ✔ |  |  |
| MasterCard | Maestro | ✔ | ✔ | ✔ |
| MasterCard | Maestro Samsung Pay | ✔ |  |  |
| MasterCard | Maestro UK | ✔ | ✔ | ✔ |
| VISA | Credito | ✔ | ✔ | ✔ |
| VISA | Dare | ✔ | ✔ | ✔ |
| VISA | Alpha Bank Bonus | ✔ | ✔ | ✔ |
| VISA | Android Pay | ✔ |  |  |
| VISA | Apple Pay | ✔ |  |  |
| VISA | Samsung Pay | ✔ |  |  |
| VISA | VISA Checkout | ✔ | ✔ | ✔ |
| VISA | VISA Dankort | ✔ | ✔ | ✔ |
| VISA | VISA Hipotecario | ✔ | ✔ | ✔ |
| VISA | VISA Aravia Card | ✔ | ✔ | ✔ |
| AMEX | Credito | ✔ | ✔ | ✔ |
| AMEX | Dare | ✔ | ✔ | ✔ |
| AMEX | Android Pay | ✔ |  |  |
| AMEX | Apple Pay | ✔ |  |  |
| AMEX | Samsung Pay | ✔ |  |  |
| AMEX | AMEX Commercial | ✔ | ✔ | ✔ |
| AMEX | AMEX Consumer | ✔ | ✔ | ✔ |
| AMEX | AMEX Corporate | ✔ | ✔ | ✔ |
| AMEX | AMEX Small Business | ✔ | ✔ | ✔ |
| Individua | Standard | ✔ | ✔ | ✔ |
| Individua | Android Pay | ✔ |  |  |
| Individua | Apple Pay | ✔ |  |  |
| Individua | Samsung Pay | ✔ |  |  |
| Diners   | Standard | ✔ | ✔ | ✔ |
| Dineromail | Standard | ✔ | ✔ | ✔ |
| JCB | Standard | ✔ | ✔ | ✔ |
| Union Pay\* | Standard | ✔ |  |  |
| Interac Debit\* | Standard | ✔ |  |  |

\*I token delle carte ricorrenti Interac e Union Pay non sono forniti da Adyen, quindi non possono essere supportati per le transazioni con carta non presente.

#### <a name="supported-gift-cards"></a>Gift card supportate
| Schema | Carta presente | Carta non assente |
|---|:-:|---|
| Givex | ✔ | ✔ |
| SVS | ✔ | ✔ |

Per supportare questi schemi di gift card esterne tramite il connettore pagamenti di Dynamics 365 per Adyen, devi completare i passaggi aggiuntivi. Per ulteriori informazioni, vedi [Supporto per gift card esterne](/dynamics365/unified-operations/retail/dev-itpro/gift-card).

#### <a name="supported-wallets"></a>Portafogli supportati

| Schema | Carta presente | Carta non assente |
|---|---|---|
| Alipay | Il supporto verrà aggiunto in una versione successiva. | Numero |
| WeChat | Il supporto verrà aggiunto in una versione successiva. | Numero |

#### <a name="supported-card-present-input-methods"></a>La carta supportata presenta metodi di input
| Metodo di input | Supportata | Note |
|---|:-:|---|
| Dip | ✔ | |
| Passaggio | ✔ | |
| Tap | ✔ | |
| Inserimento manuale tramite interfaccia utente POS. |  | Non supportato al momento |
| Inserimento manuale tramite terminale di pagamento. | ✔ | Supporta l'inserimento manuale di carte di credito, di debito e regalo con inserimento di pin. | 


#### <a name="supported-card-present-countries"></a>Paesi con carta presente supportati

I seguenti paesi hanno componenti Commerce disponibili e supporto con carta presente di Adyen. Per l'attuale disponibilità internazionale di Commerce, visita la [pagina della disponibilità internazionale](/dynamics365/get-started/availability).

| Paese | Supportata |
| --- | :-: |
| Australia | ✔ |
| Austria | ✔ |
| Belgio | ✔ |
| Canada | ✔ |
| Repubblica Ceca | ✔ |
| Danimarca | ✔ |
| Estonia | ✔ |
| Finlandia | ✔ |
| Francia | ✔ |
| Germania | ✔ |
| RAS di Hong Kong | ✔ |
| Ungheria | ✔ |
| Islanda | ✔ |
| Irlanda | ✔ |
| Italia | ✔ |
| Giappone | Rilascio futuro |
| Lettonia | ✔ |
| Lituania | ✔ |
| Malaysia | ✔ |
| Paesi Bassi | ✔ |
| Nuova Zelanda | ✔ |
| Regno di Norvegia | ✔ |
| Polonia | ✔ |
| Singapore | ✔ |
| Svizzera | ✔ |
| Spagna | ✔ |
| Svezia | ✔ |
| Svizzera | ✔ |
| Regno Unito | ✔ |
| Stati Uniti | ✔ |
| Brasile | Rilascio futuro |

#### <a name="supported-card-not-present-countries"></a>Paesi con carta non presente supportati

I seguenti paesi sono supportati da Adyen per le transazioni con carta non presente. [Contatta Adien](https://www.adyen.com/contact/sales) per i dettagli sul supporto per un paese specifico. Per l'attuale disponibilità internazionale di Commerce, visita la [pagina della disponibilità internazionale](/dynamics365/get-started/availability).

| Paese | 
| --- |
| Argentina |
| Armenia |
| Australia |
| Austria |
| Bahrein |
| Belgio |
| Brasile |
| Bulgaria |
| Canada |
| Cile |
| Cina |
| Colombia |
| Croazia |
| Cipro |
| Repubblica Ceca  |
| Danimarca |
| Egitto |
| Estonia |
| Finlandia |
| Francia |
| Georgia |
| Germania |
| Gibilterra |
| Grecia |
| Guernsey |
| RAS di Hong Kong |
| Ungheria |
| Islanda |
| India |
| Indonesia |
| Irlanda |
| Isola di Man |
| Israele |
| Italia |
| Giappone |
| Jersey |
| Corea |
| Kuwait |
| Lettonia |
| Lituania |
| Lussemburgo |
| Malaysia |
| Malta |
| Messico |
| Marocco |
| Paesi Bassi |
| Nuova Zelanda |
| Regno di Norvegia |
| Perù |
| Polonia |
| Portogallo |
| Qatar |
| Romania |
| Arabia Saudita |
| Serbia |
| Singapore |
| Slovacchia |
| Slovenia |
| Sudafrica |
| Spagna |
| Svezia |
| Svizzera |
| Taiwan |
| Tanzania |
| Thailandia |
| Turchia |
| Emirati Arabi Uniti (UAE) |
| Regno Unito |
| Stati Uniti d'America compreso Porto Rico  |

#### <a name="supported-dynamics-365-payment-features"></a>Funzionalità di pagamento di Dynamics 365 supportate

La tabella seguente mostra l'insieme di funzionalità supportate dal connettore pagamenti Dynamics 365 per Adyen. Queste funzionalità utilizzano miglioramenti introdotti nell'SDK dei pagamenti e in alcuni componenti a dicembre 2018. Non sono esclusivi del connettore pagamenti Dynamics 365 per Adyen. Per ulteriori informazioni su come utilizzare questi miglioramenti per un connettore pagamenti diverso, vedi [Creare un'integrazione di pagamento end-to-end per un terminale di pagamento](/dynamics365/unified-operations/retail/dev-itpro/end-to-end-payment-extension).

| Schema | Carta presente | Carta non assente |
|---|:-:|:-:|
| [Saldo liquidazione gift card](/dynamics365/unified-operations/retail/dev-itpro/gift-card-cash-out) | ✔ | |
| [Duplicare la protezione pagamenti](/dynamics365/unified-operations/retail/duplicate-payment-protection) | ✔ | |
| Tokenizzazione multicanale | ✔ | ✔ |
| Rimborsi collegati | ✔<br>(A partire da 10.0.1) | ✔<br>(A partire da 10.0.1) |
| [Risparmia sui pagamenti online](../dev-itpro/adyen-connector-listPI.md) | | ✔<br>(A partire da 10.0.2) | 
| [Gift card esterne per call center ed e-commerce](./gift-card.md) | ✔<br>(A partire da 10.0.10) | 
| [Reindirizzamento pagamento SCA](../adyen_redirect.md) | | ✔<br>(A partire da 10.0.12) |
| [Terminali di pagamento dedicati e prompt per una stampante e un cassetto di cassa](../pos-multi-hws.md) | ✔<br>(A partire da 10.0.12) | |
| [Supporto per le mance a livello di SDK tramite il connettore Adyen](tipping.md) | ✔<br>(A partire da 10.0.14) | |
| [Acquisizione incrementale per fatturazione ordini](incremental-capture.md) |  | ✔<br>(A partire da 10.0.18) |
| [Pagamenti del portafoglio](../wallets.md) |  | ✔<br>(A partire da 10.0.20) |
| [Google Pay con Adyen](google-pay-adyen.md) |  | ✔<br>(A partire da 10.0.27) |

## <a name="next-steps"></a>Passaggi successivi

Per informazioni sulla registrazione e sulla configurazione del connettore pagamenti Dynamics 365 per Adyen, consulta [Impostazione del connettore pagamenti di Dynamics 365 per Adyen](adyen-connector-setup.md).

## <a name="additional-resources"></a>Risorse aggiuntive

[Impostare Dynamics 365 Payment Connector per Adyen](adyen-connector-setup.md)

[Domande frequenti su Dynamics 365 Payment Connector per Adyen](adyen-connector-faq.md)

[Risolvere i problemi di Dynamics 365 Payment Connector per Adyen](adyen-connector-troubleshoot.md)

[Domande frequenti sui pagamenti](/dynamics365/unified-operations/retail/dev-itpro/payments-retail)

[!INCLUDE [footer-include](../../includes/footer-banner.md)]
