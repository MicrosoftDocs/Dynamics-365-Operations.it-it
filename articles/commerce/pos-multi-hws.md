---
title: Terminali di pagamento dedicati e prompt per una stampante e un cassetto di cassa
description: Questo argomento fornisce informazioni sulla possibilità di disporre di un terminale di pagamento dedicato e di richiedere all'utente di selezionare un cassetto di cassa e una stampante di ricevute.
author: rubendel
ms.date: 05/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: 141393
ms.assetid: e23e944c-15de-459d-bcc5-ea03615ebf4c
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2019-03-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 8a3c7eb9580f9155dd33f6351f37eb1edd269a3d
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018635"
---
# <a name="dedicated-payment-terminals-and-prompts-for-a-printer-and-cash-drawer"></a>Terminali di pagamento dedicati e prompt per una stampante e un cassetto di cassa

[!include [banner](includes/banner.md)]

Questo argomento fornisce informazioni sulla possibilità di disporre di un terminale di pagamento dedicato e di richiedere all'utente di selezionare un cassetto di cassa e una stampante di ricevute.

## <a name="overview"></a>Panoramica

I rivenditori moderni sono alla ricerca di soluzioni per semplificare l'esperienza di pagamento nel punto vendita. Le recenti tendenze di pagamento senza carta mediante mezzi elettronici contribuiscono non solo a rendere l'esperienza di acquisto più agevole, ma riducono anche la necessità di disporre di una gamma completa di periferiche per ogni addetto del negozio.

Microsoft Dynamics 365 Commerce supporta queste tendenze mediante uno scenario in cui un dispositivo POS (punto di vendita) dispone in permanenza di un terminale di pagamento dedicato, ma non di una stampante di ricevute o di un cassetto di cassa. Quando gli addetti devono stampare una ricevuta o ricevere un pagamento in contanti, gli viene richiesto di selezionare una stazione hardware in cui tali dispositivi sono configurati.

## <a name="key-terms"></a>Termini importanti

| Termine | Descrizione |
|---|---|
| Registro | L'entità utilizzata per configurare un'istanza di un registratore di cassa POS. |
| Dispositivo | Una rappresentazione dell'istanza fisica di un registratore di cassa POS e dell'applicazione Modern POS che gli è stata assegnata. |
| Stazione hardware dedicata | La logica di business della stazione hardware è integrata nelle applicazioni Modern POS per Windows e Modern POS per Android. |
| Porta per apertura cassetto di cassa (d/k) | Un metodo tradizionale per collegare un cassetto di cassa a una stampante di ricevute. |
| Periferiche di rete | Supporto integrato per terminali di pagamento, stampanti di ricevute e cassetti di cassa utilizzabili in rete. |

## <a name="supported-pos-clients-and-devices"></a>Client e dispositivi POS supportati

La funzionalità descritta in questo argomento è supportata da Modern POS per Windows e dal Modern POS per Client POS Android.

Questa funzionalità supporta terminali di pagamento e stampanti di ricevute utilizzabili in rete. È possibile fornire supporto per cassetti di cassa collegando il cassetti di cassa alla stampante di ricevute utilizzabile in rete tramite la porta d/k.

Il supporto predefinito per questa funzionalità è fornito dal [Connettore pagamenti di Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3). Tuttavia, altri connettori pagamenti potrebbero essere supportati tramite il kit SDK di Commerce per pagamenti. Le stampanti di ricevute supportate includono stampanti per ricevute utilizzabili in rete di Star Micronics ed Epson.

Per configurare le stampanti di ricevute Star Micronics, utilizzare l'utility per stampanti Star Micronics per configurare il dispositivo di modo che possa essere utilizzato in rete. Questa utility fornirà anche l'indirizzo IP del dispositivo.

Per configurare le stampanti di ricevute Epson, utilizzare l'utility ePOS-Print di Epson per configurare il dispositivo in modo da utilizzare i protocolli di rete.

Per ulteriori informazioni su come configurare le periferiche di rete, vedere [Panoramica sul supporto delle periferiche di rete](./dev-itpro/network-peripherals.md).

## <a name="set-up-a-dedicated-payment-terminal-and-a-prompt-for-a-printer-and-cash-drawer"></a>Configurare un terminale di pagamento dedicato e un prompt per una stampante e un cassetto di cassa

### <a name="set-up-hardware-profiles"></a>Impostare profili hardware

È necessario disporre di due tipi di profilo hardware. Il primo è assegnato al registratore di cassa. Il secondo è assegnato a una stazione hardware a livello di punto vedita e viene utilizzato per raggruppare in modo logico le stampanti di ricevute di rete e i cassetti di cassa.

#### <a name="set-up-a-hardware-profile-for-the-register"></a>Configurare un profilo hardware per il registratore di cassa

Per configurare il profilo hardware assegnato al registratore di cassa, attenersi alla seguente procedura.

1. In Dynamics 365 Commerce, cercare **Profilo hardware**.
2. Selezionare **Nuovo**.
3. Assegnare un numero di profilo hardware, quindi inserire una descrizione. Questo profilo hardware verrà assegnato al registratore di cassa stesso. Pertanto, una descrizione come **Dedicato con fallback** sarà sufficiente.
4. Nelle Schede dettaglio per diversi tipi di dispositivo, configurare i seguenti tipi di dispositivo.

    | Dispositivo | Tipo | Nome periferica | Dettagli aggiuntivi |
    |---|---|---|---|
    | Stampante | Rete | *Alcune* | Per il nome di dispositivo viene fatta la distinzione tra maiuscole e minuscole. L'**ID profilo ricevuta** dovrebbe essere uguale all'**ID profilo ricevuta** mappato alla stampante di rete configurata nel profilo hardware assegnato alla stazione hardware a livello di canale. |
    | Cassetto della cassa | Rete | *Alcune* | Per il nome di dispositivo viene fatta la distinzione tra maiuscole e minuscole. Impostare l'opzione **Consenti uso turno condiviso** su **Sì**. |
    | Servizio EFT | Adyen | Non applicabile | Per informazioni su come configurare il connettore Adyen predefinito, vedere [Connettore pagamenti di Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3). Altri connettori pagamenti possono essere supportati tramite il [kit SDK di Commerce per pagamenti](./dev-itpro/end-to-end-payment-extension.md). |
    | Tastierino PIN | Rete | **MicrosoftAdyenDeviceV001** | Nessuna. |

5. In Dynamics 365 Commerce, cercare **Registratori di cassa**.
6. Selezionare un registratore di cassa selezionando il relativo numero, quindi selezionare **Modifica**.
7. Assegnare il profilo hardware appena creato al registratore di cassa che deve utilizzare un terminale di pagamento dedicato. Il dispositivo mappato a questo registratore di cassa deve utilizzare l'applicazione Modern POS per Windows o Modern POS per Android.
8. Selezionare **Salva**.
9. Nel riquadro azioni, nella scheda **Registratori di cassa**, selezionare **Configura indirizzi IP**.
10. Nella Scheda dettaglio **Tastierino PIN**, immettere l'indirizzo IP del terminale di pagamento. Per informazioni su come ottenere l'indirizzo IP del terminale di pagamento utilizzando il connettore Adyen, vedere [Connettore di pagamento Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3).
11. Selezionare **Salva**.

#### <a name="set-up-a-hardware-profile-for-the-receipt-printer-and-cash-drawer"></a>Configurare un profilo hardware per la stampante di ricevute e il cassetto di cassa

Per configurare il profilo hardware utilizzato per raggruppare la stampante di ricevute di rete e il cassetto di cassa, attenersi alla seguente procedura.

1. In Dynamics 365 Commerce, cercare **Profilo hardware**.
2. Selezionare **Nuovo**.
3. Assegnare un numero di profilo hardware, quindi inserire una descrizione. Questo profilo hardware verrà utilizzato per raggruppare la stampante di ricevute e il cassetto di cassa. Pertanto, una descrizione come **Stampante di rete e cassetto di cassa** sarà sufficiente.
4. Nelle Schede dettaglio per diversi tipi di dispositivo, configurare i seguenti tipi di dispositivo.

    | Dispositivo | Tipo | Descrizione | Dettagli aggiuntivi |
    |---|---|---|---|
    | Stampante | Rete | **Epson** o **Star** | Per il nome di dispositivo viene fatta la distinzione tra maiuscole e minuscole. L'**ID profilo ricevuta** dovrebbe essere uguale all'**ID profilo ricevuta** mappato alla stampante di rete configurata nel profilo hardware assegnato al registratore di cassa. |
    | Cassetto di cassa | Fallback | **Epson** o **Star** | Per il nome di dispositivo viene fatta la distinzione tra maiuscole e minuscole. Impostare l'opzione **Consenti uso turno condiviso** su **Sì**. |

5. Selezionare **Salva**.

### <a name="set-up-hardware-stations"></a>Configurare stazioni hardware

È necessario disporre di due stazioni hardware. La prima verrà mappata al registratore di cassa. La seconda verrà selezionata come richiesto, ogni volta che deve essere stampata una ricevuta o deve essere aperto un cassetto di cassa.

#### <a name="register-a-hardware-station"></a>Registrare una stazione hardware

1. In Dynamics 365 Commerce, cercare **Tutti i punti vendita**.
2. Selezionare un punto vendita selezionandone i valori **ID canale di vendita al dettaglio**, quindi selezionare **Modifica**.
3. Nella Scheda dettaglio **Stazioni hardware** selezionare **Aggiungi**.
4. Impostare il campo **Tipo di stazione hardware** su **Dedicata**.
5. Immettere una descrizione, ma non impostare altri valori per questa stazione hardware. Questa stazione hardware verrà sempre utilizzata per il registratore di cassa. 

#### <a name="set-up-a-hardware-station-for-the-receipt-printer-and-cash-drawer"></a>Configurare una stazione hardware per la stampante di ricevute e il cassetto di cassa

1. In Dynamics 365 Commerce, cercare **Tutti i punti vendita**.
2. Selezionare un punto vendita selezionandone i valori **ID canale di vendita al dettaglio**, quindi selezionare **Modifica**.
3. Nella Scheda dettaglio **Stazioni hardware** selezionare **Aggiungi**.
4. Impostare il campo **Tipo di stazione hardware** su **Dedicata**.
5. Immettere una descrizione. Questa stazione hardware verrà utilizzata per la stampante di ricevute e il cassetto di cassa.
6. Nel campo **Profilo hardware**, selezionare il profilo hardware precedentemente creato per la stampante di ricevute e il cassetto di cassa.
7. Selezionare **Salva**.
8. Con la stazione hardware per la stampante di ricevute e il cassetto di cassa ancora selezionata, selezionare **Configura indirizzi IP**.
9. Ottenere l'indirizzo IP per la stampante e immetterlo come indirizzo IP sia per la stampante di ricevute e il cassetto di cassa.
10. Selezionare **Salva**.
11. Cercare **Programmazioni della distribuzione**.
12. Selezionare la programmazione della distribuzione **1090**, quindi selezionare **Esegui adesso**.
13. Selezionare la programmazione della distribuzione **1070**, quindi selezionare **Esegui adesso**.

### <a name="set-up-the-system-to-prompt-for-receipt-printer-and-cash-drawer-selection-as-its-required"></a>Configurare il sistema di modo che venga richiesta la selezione della stampante di ricevute e del cassetto di cassa come richiesto

1. In un client POS supportato, chiudere il turno corrente, se un turno è aperto.
2. Accediere e quindi selezionare **Operazioni non relative al cassetto**.
3. Utilizzare l'operazione **Gestisci stazioni hardware** per accendere una stazione hardware.
4. Selezionare la stazione hardware creata per il registratore di cassa per renderla attiva.
5. Uscire dal POS, accedere di nuovo e aprire un turno.

Il terminale di pagamento assegnato al profilo hardware ora sarà sempre attivo e verrà visualizzato un prompt se è richiesta una stampante di ricevute o un registratore di cassa.

Molti commercianti che hanno richiesto questa funzionalità sono interessati a ridurre gli sprechi fornendo ricevute via e-mail e incoraggiando i pagamenti elettronici. A seconda della configurazione del POS, agli addetti del punto vendita viene richiesto di selezionare una stampante di ricevute o un registratore di cassa solo quando un cliente desidera una ricevuta fisica o pagare in contanti.

Agli addetti del punto vendita viene richiesto di selezionare una stazione hardware solo una volta per transazione, a meno che non sia necessario stampare una ricevuta e utilizzare contanti per il pagamento, ma il profilo hardware originariamente selezionato non include entrambi i dispositivi. In tal caso, all'addetto del punto vendita verrà nuovamente richiesto di selezionare una stazione hardware che può essere utilizzata per completare la transazione.

## <a name="related-articles"></a>Articoli correlati

- [Configurare l'app POS Hybrid su Android e iOS](./dev-itpro/hybridapp.md)
- [Connettore pagamenti di Dynamics 365 per Adyen](./dev-itpro/adyen-connector.md?tabs=8-1-3)
- [Panoramica sul supporto delle periferiche di rete](./dev-itpro/network-peripherals.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
