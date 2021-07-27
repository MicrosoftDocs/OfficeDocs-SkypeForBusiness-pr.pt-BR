---
title: Controladores de Borda de Sessão certificados para Roteamento Direto
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: O administrador pode saber quais controladores de borda de sessão (SBCs) foram certificados para Roteamento Direto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: af721c97d809204eacc897c09a6f504a0d6d5722
ms.sourcegitcommit: e60547de6e33ad73ba02c9aa9b5d831100940fbe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2021
ms.locfileid: "53482324"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borda da sessão certificados para Roteamento Direto

A Microsoft faz parceria com fornecedores selecionados de Controlador de Borda da Sessão (SBC) para garantir que seus SBCs sejam compatíveis com o Roteamento Direto.

A Microsoft trabalha com cada fornecedor para:

- Trabalhe em conjunto nos protocolos de interconexão SIP.
- Execute testes intensos usando um laboratório de terceiros. Somente os dispositivos que passam nos testes são certificados.
- Execute testes diários com todos os dispositivos certificados em ambientes de produção e pré-produção. A validação dos dispositivos em ambientes de pré-produção garante que as novas versões do código de Roteamento Direto na nuvem funcionarão com os SBCs certificados.
- Estabeleça um processo de suporte conjunto com os fornecedores SBC.

  > [!NOTE]
  > A Microsoft só oferece suporte Sistema de Telefonia se um dispositivo ou dispositivo certificado estiver conectado por meio do Roteamento Direto. A Microsoft reserva o direito de rejeitar casos de suporte em que um dispositivo não certificado está conectado ao Sistema de Telefonia por meio do Roteamento Direto. Se a Microsoft determinar que o problema de Roteamento Direto de um cliente está com o dispositivo SBC de um fornecedor, o cliente precisará envolver o fornecedor SBC para suporte.

As tabelas que seguem os dispositivos de lista certificados para Roteamento Direto. (Para obter informações sobre quais fornecedores SBC suportam a Otimização de Mídia Local, consulte [Configure Local Media Optimization for Direct Routing](direct-routing-media-optimization-configure.md).)

[Saiba mais sobre o Roteamento Direto](https://aka.ms/dr).
Se você tiver dúvidas sobre o programa de certificação SBC para Roteamento Direto, entre em contato drsbccertification@microsoft.com.
<br/>

## <a name="certified-sbc-vendors"></a>Fornecedores SBC certificados

|                                                       Fornecedor                                                        |       Produto       | Bypass que não seja de mídia | Bypass de mídia | Versão do software | 911 Service Provider Capable* | ELIN capaz |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Suporte para 7.20A.250 (Recomendado 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Suporte para 7.20A.250 (Recomendado 7.20A.258)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Suporte para 7.20A.250 (Recomendado 7.20A.258)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Suporte para 7.20A.250 (Recomendado 7.20A.258)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pendente     |  Suporte para 7.20A.250 (Recomendado 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  Suporte para 7.20A.250 (Recomendado 7.20A.258)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Suporte para 7.20A.250 (Recomendado 7.20A.258) |  &#10004;    |  &#10004;  |
|  [Comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       8.2 e 7.2 com suporte (Recomendado 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       8.2 e 7.2 com suporte (Recomendado 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       8.2 e 7.2 com suporte (Recomendado 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       8.2 e 7.2 com suporte (Recomendado 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       8.2 e 7.2 com suporte (Recomendado 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x ou 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x ou 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x ou 9.x    |   &#10004;    |     &#10004;     |
| | Série EdgeMarc |  &#10004; | | 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      3.20 suportado (Recomendado 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metawitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 para Bypass de Mídia)      |     |    |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Cisco Unified Border Element (CUBE) para Roteadores de Serviços Integrados de Série 1000        |     &#10004;   | &#10004; |      IOS XE Amsterdã 17.2.1r com suporte (Recomendado 17.3.2)         |    &#10004;     |   |  
|                                   |     Elemento de Borda Unificada da Cisco (CUBE) para Roteadores de Serviços Integrados de Série 4000        |     &#10004;   | &#10004; |   IOS XE Amsterdã 17.2.1r com suporte (Recomendado 17.3.2)         |   &#10004;      |    |  
|                                   |     Cisco Unified Border Element (CUBE) para Roteador de Serviços de Nuvem da Série 1000V       |     &#10004;   | &#10004; |      IOS XE Amsterdã 17.2.1r com suporte (Recomendado 17.3.2)         |    &#10004;     |    |  
|                                 |     Elemento de Borda Unificada da Cisco (CUBE) para Roteadores de Serviços de Agregação de Série 1000      |     &#10004;   | &#10004; |      IOS XE Amsterdã 17.2.1r com suporte (Recomendado 17.3.2)         |    &#10004;     |    |
|                                 |     Elemento de Borda Unificada da Cisco (CUBE) para Plataformas de Borda do Catalyst 8000      |     &#10004;   | &#10004; |      IOS XE Amsterdã 17.3.2      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Avaya Session Border Controller for Enterprise ( ASBCE)    |     &#10004;     |       &#10004;     |       Versão 8.1.1 (8.1.2 para Bypass de Mídia)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Nokia Session Border Controller    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Nokia Session Border Controller    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       5.0 suportado (Recomendado 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Link da Orquídea    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Atos Unificar controlador de borda de sessão do OpenScape   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Redes Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [Tecnologias M5 (anteriormente conhecida como Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Série Mediatrix Sentinel   |     &#10004;     |         |      DGW 48.0.2340 (DGW recomendado 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Controlador de Borda de Sessão de Ekinops (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Controlador de Borda de Sessão Virtual de Ekinops (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Hyperconverged Voice   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

* 911 provedores de serviços

- [Roteamento de Localização Dinâmica da Largura de Banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [Serviço de Roteamento de Emergência Intrado (ERS)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Gateway de Emergência Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
<br/>

## <a name="direct-routing-and-analog-devices-interoperability"></a>Interoperabilidade de dispositivos analógicos e roteamento direto

A tabela a seguir lista dispositivos que são verificados para interoperabilidade entre Roteamento Direto e Dispositivos Analógicos.

|                                                       Fornecedor                                                        |       Produto       | Verificado
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adaptador de telefone analógico multiplataforma do ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   SOFTWARE AP1100 Versão 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  SOFTWARE AP3900 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  SOFTWARE AP4600 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP6300 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  SOFTWARE AP6350 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software VME Versão 8.3.0.1.2 |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versão do software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versão do software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode with Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Para nos dar comentários sobre o Teams, como ideias para novos recursos, consulte [Uservoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Observe a certificação concedida a uma versão principal. Isso significa que há suporte para o firmware com qualquer número no firmware SBC após a versão principal.
