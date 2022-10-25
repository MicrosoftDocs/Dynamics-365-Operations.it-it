---
title: Modalità di creazione clienti asicroni
description: Questo articolo descrive la modalità di creazione dei clienti asincroni in Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 10/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-12-17
ms.openlocfilehash: b2926339021991f87dd3eadef94da3b500c954cf
ms.sourcegitcommit: 40c80a617b903c2b26e44b41147e0021c5cb680d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2022
ms.locfileid: "9690291"
---
# <a name="asynchronous-customer-creation-mode"></a>Modalità di creazione clienti asicroni

[!include [banner](includes/banner.md)]

Questo articolo descrive la modalità di creazione dei clienti asincroni in Microsoft Dynamics 365 Commerce.

In Commerce, vi sono due modalità di creazione di clienti: sincrona (o sync) e asincrona (o async). Per impostazione predefinita, i clienti vengono creati in modalità sincrona. In altre parole, vengono creati in Commerce headquarters in tempo reale. La creazione di clienti in modalità sincrona è vantaggiosa perché i nuovi clienti sono immediatamente disponibili per la ricerca nei canali. Tuttavia, ha anche uno svantaggio. Poiché genera chiamate [Commerce Data Exchange: Servizio in tempo reale](dev-itpro/define-retail-channel-communications-cdx.md#realtime-service) a Commerce Headquarters, le prestazioni possono essere alterate se vengono effettuate molte chiamate simultanee per la creazione di clienti.

Se l'opzione **Crea cliente in modalità asincrona** è impostata su **Sì** nel profilo di funzionalità del punto vendita (**Retail e Commerce \> Impostazione canale \> Impostazione punto vendita online \> Profili funzionalità**), le chiamate di servizio in tempo reale non vengono utilizzate per creare record cliente nel database del canale. La creazione di clienti in modalità asincrona non influisce sulle prestazioni di Commerce Headquarters. Un identificatore univoco globale (GUID) temporaneo viene assegnato a ogni nuovo record cliente asincrono e utilizzato come ID account cliente. Questo GUID non è visibile agli utenti POS. Quegli utenti vedranno invece **In attesa di sincronizzazione** come ID account cliente.

> [!IMPORTANT]
> Se il POS è offline, il sistema crea automaticamente i clienti in modo asincrono, anche se la modalità di creazione di clienti asincrona è disabilitata. Pertanto, indipendentemente dalla selezione tra la creazione cliente sincrona o asincrona, gli amministratori di Commerce headquarters devono creare e pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, in modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce headquarters.

## <a name="async-customer-limitations"></a>Limitazioni dei clienti asincroni

La funzionalità dei clienti asincroni presenta attualmente la seguente limitazione:

- Le carte fedeltà non possono essere emesse ai clienti asincroni a meno che il nuovo ID account cliente non sia stato sincronizzato di nuovo con il canale.

## <a name="async-customer-enhancements"></a>Miglioramenti dei clienti asincroni

Per aiutare le organizzazioni a utilizzare la modalità di creazione di clienti asincroni per gestire i clienti e per ridurre le comunicazioni in tempo reale con Commerce headquarters, sono stati implementati i seguenti miglioramenti per ottenere la parità tra le modalità sincrona e asincrona nei canali. 

| Miglioramento delle funzionalità | Versione di Commerce | Dettagli funzionalità |
|---|---|---|
| Miglioramenti delle prestazioni quando le informazioni sui clienti vengono recuperate dal database del canale | 10.0.20 e versioni successive | Per migliorare le prestazioni, l'entità cliente viene suddivisa in entità più piccole. Il sistema recupera quindi solo le informazioni necessarie dal database del canale. |
| Possibilità di creare indirizzi in modo asincrono durante il checkout | 10.0.22 e versioni successive | <p>Opzione funzionalità: **Abilita creazione asincrona per gli indirizzi cliente**</p><p>Dettagli funzionalità:</p><ul><li>Possibilità di aggiungere indirizzi senza effettuare chiamate di servizio in tempo reale a Commerce headquarters</li><li>Possibilità di identificare in modo univoco gli indirizzi nel database del canale senza utilizzare un ID record (valore **RecId**)</li><li>Rilevamento di timestamp per la creazione degli indirizzi</li><li>Sincronizzazione di indirizzi in Commerce headquarters</li></ul><p>Questa funzionalità ha effetto sia sui clienti sincroni che su quelli asincroni. Per modificare gli indirizzi in modo asincrono oltre a crearli in modo asincrono, è necessario abilitare la funzionalità **Abilita modifica clienti in modalità asincrona**.</p> |
| Abilitare la parità tra la creazione di clienti sincrona e asincrona. | 10.0.24 e versioni successive | <p>Opzione funzionalità: **Abilita creazione avanzata di clienti asincroni**</p><p>Dettagli funzionalità: possibilità di acquisire informazioni aggiuntive, come titolo, affiliazioni del cliente predefinito e informazioni di contatto secondarie (numero di telefono e indirizzo e-mail), mentre si creano clienti in modo asincrono</p> |
| Messaggi di errore intuitivi | 10.0.28 e versioni successive | Questi miglioramenti aiutano a migliorare i messaggi di errore intuitivi se un utente non può modificare immediatamente le informazioni mentre è in corso la sincronizzazione. È possibile abilitare questi miglioramenti usando l'impostazione **Rendi determinati elementi dell'interfaccia utente non modificabili da un cliente asincrono** in **Impostazioni sito \> Estensioni** nel generatore di siti di Commerce. |
| Possibilità di modificare le informazioni sui clienti in modo asincrono | 10.0.29 e versioni successive | <p>Opzione funzionalità: **Abilita modifica dei clienti in modalità asincrona**</p><p>Dettagli funzionalità: possibilità di modificare i dati dei clienti in modo asincrono</p><p>Per le risposte alle domande comuni sui problemi relativi alla modifica delle informazioni sui clienti in modo asincrono, vedere [Domande frequenti sulla modalità di creazione di clienti asincroni](async-customer-mode-faq.md).</p> |
| Possibilità di controllare la sincronizzazione delle operazioni di gestione dei clienti | 10.0.31 e versioni successive | Questo miglioramento consente agli utenti di controllare la sincronizzazione delle operazioni di gestione dei clienti in Commerce headquarters. Consente inoltre agli utenti di apportare modifiche se necessarie e sincronizzare i dati. |

### <a name="feature-switch-hierarchy"></a>Gerarchia delle opzioni delle funzionalità

A causa della gerarchia delle opzioni delle funzionalità, prima di abilitare la funzionalità **Abilita modifica dei clienti in modalità asincrona**, è necessario abilitare le seguenti funzionalità: 

- **Miglioramenti delle prestazioni per gli ordini cliente e le transazioni cliente**: questa funzionalità è obbligatoria a partire dalla versione 10.0.28 di Commerce. 
- **Abilita creazione avanzata di clienti asincroni**
- **Abilita creazione asincrona per gli indirizzi cliente**

Per le risposte alle domande più comuni sulla risoluzione dei problemi, vedere [Domande frequenti sulla modalità di creazione di clienti asincroni](async-customer-mode-faq.md). 

Dopo aver abilitato le precedenti funzionalità, devi pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, di modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce Headquarters.

### <a name="customer-creation-in-pos-offline-mode"></a>Creazione di clienti in modalità offline POS

Come indicato in precedenza, se il POS è offline, il sistema crea automaticamente i clienti in modo asincrono, anche se la modalità di creazione di clienti asincrona è disabilitata. Pertanto, gli amministratori di Commerce Headquarters devono creare e pianificare un processo batch ricorrente per il **processo P**, il processo **Sincronizza clienti e partner commerciali dalla modalità asincrona** e il processo **1010**, di modo che qualsiasi cliente asincrono sia convertito in cliente sincrono in Commerce Headquarters.

> [!NOTE]
> Se l'opzione **Filtra tabelle di dati di clienti condivise** è impostata su **Sì** nella pagina **Schema del canale di commercio** (**Retail e Commerce \> Impostazione sedi centrali \> Utilità di pianificazione di commercio \> Gruppo di database canale**), i record cliente non vengono creati in modalità offline POS. Per ulteriori informazioni, vedere [Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion).

## <a name="additional-resources"></a>Risorse aggiuntive

[Gestione dei clienti nei punti vendita](customer-mgmt-stores.md)

[Convertire i clienti asincroni in clienti sincroni](convert-async-to-sync.md)

[Attributi cliente](dev-itpro/customer-attributes.md)

[Esclusione di dati offline](dev-itpro/implementation-considerations-cdx.md#offline-data-exclusion)
