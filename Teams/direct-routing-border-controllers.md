---
title: Controladores de Borda de Sessão certificados para Roteamento Direto
ms.author: crowe
ms.reviewer: FilippSe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: high
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
hideEdit: true
f1.keywords:
- NOCSH
description: Saiba mais sobre quais SBCs (Controladores de Borda de Sessão) foram certificados para Roteamento Direto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1d9859b15b881d53a2f1b3c5b39442331e51be2e
ms.sourcegitcommit: 74d3ab35c344d70b2399bc46a6ced3ab2762a470
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60138217"
---
# <a name="session-border-controllers-certified-for-direct-routing"></a>Controladores de Borda de Sessão certificados para Roteamento Direto

A Microsoft faz parceria com fornecedores selecionados de Controlador de Borda da Sessão (SBC) para garantir que seus SBCs sejam compatíveis com o Roteamento Direto.

A Microsoft trabalha com cada fornecedor para:

- Trabalhe em conjunto nos protocolos de interconexão SIP.
- Execute testes intensos usando um laboratório de terceiros. Somente os dispositivos aprovados nos testes são certificados.
- Execute testes diários com todos os dispositivos certificados em ambientes de produção e pré-produção. A validação dos dispositivos em ambientes de pré-produção garante que as novas versões do código de Roteamento Direto na nuvem funcionarão com os SBCs certificados.
- Tem um processo de suporte conjunto com os fornecedores de SBCs.

  > [!NOTE]
  > A Microsoft só dá suporte ao Sistema de Telefonia se um dispositivo ou dispositivos certificado estiver conectado por meio do Roteamento Direto. A Microsoft se reserva o direito de rejeitar casos de suporte em que há um dispositivo não certificado conectado ao Sistema de Telefonia via Roteamento Direto. Se a Microsoft determinar que o problema de Roteamento Direto de um cliente está com o dispositivo SBC de um fornecedor, o cliente precisará contatar o fornecedor do SBC para obter suporte.

As tabelas que seguem a lista de dispositivos certificados para Roteamento Direto. (Para obter informações sobre quais fornecedores de SBC dão suporte à Otimização de Mídia Local, consulte [Configurar otimização de mídia local para roteamento direto](direct-routing-media-optimization-configure.md).)

[Saiba mais sobre o Roteamento Direto](https://aka.ms/dr). Se você tiver dúvidas sobre o programa de certificação de SBCs para Roteamento Direto, envie um e-mail para drsbccertification@microsoft.com.<br/>

## <a name="certified-sbc-vendors"></a>Fornecedores SBC certificados

|                                                       Fornecedor                                                        |       Produto       | Sem bypass de mídia | Bypass de mídia | Versão de software | 911 Compatível com o Provedor de Serviços* | Compatível com ELIN |  
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|  
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  Compatível 7.20A.258 (Recomendado 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  Compatível 7.20A.258 (Recomendado 7.40A.100)   | &#10004;   |  &#10004;  |  
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  Compatível 7.20A.258 (Recomendado 7.40A.100)   |   &#10004;   |  &#10004;  |
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  Compatível 7.20A.258 (Recomendado 7.40A.100)   |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   &#10004;     |  Suporte para 7.20A.250 (recomendado 7.20A.258)  |  &#10004;   |  &#10004;  |
|                                                                                                                     | Mediant 9000 SBC  |     &#10004;     |   &#10004;     |  Compatível 7.20A.258 (Recomendado 7.40A.100)   | &#10004;     |  &#10004;  |
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  Compatível 7.20A.258 (Recomendado 7.40A.100) |  &#10004;    |  &#10004;  |   
|                                                                                                                     | Mediant Cloud Edition SBC  |     &#10004;     |   &#10004;     |  Compatível 7.20A.258 (Recomendado 7.40A.100) |  &#10004;    |  &#10004;  |
|  [Comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5100/5110       |     &#10004;     |   &#10004;    |       Suporte para 8.2 e 7.2 (Recomendado 9.2)       | &#10004;   |     |
|                                                                                                                     |      SBC 5200/5210       |     &#10004;     |  &#10004;    |       Suporte para 8.2 e 7.2 (Recomendado 9.2)       |   &#10004; |    |
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       Suporte para 8.2 e 7.2 (Recomendado 9.2)       |   &#10004;  | |
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       Suporte para 8.2 e 7.2 (Recomendado 9.2)       |    &#10004;  |  |
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       Suporte para 8.2 e 7.2 (Recomendado 9.2)          |  &#10004;    |    |
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      8.x ou 9.x     |   &#10004;  |  &#10004;     |
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     8.x ou 9.x     |   &#10004;   |     &#10004;     |
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      8.x ou 9.x    |   &#10004;    |     &#10004;     |
| | Série EdgeMarc |  &#10004; | | Porta 15.6.1 | |  
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |           |       1.4       |     |    |
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   &#10004;    |  &#10004;  |
|    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  &#10004;    |  &#10004;  |
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   &#10004;   |  &#10004;  |
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   &#10004;   |  &#10004;  |
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      3.20 com suporte (Recomendado 4.0)        |  &#10004;    |  &#10004;   |
|                     [Metaswitch](https://www.metaswitch.com/products/core-network/perimeta-sbc)                               |     Perimeta SBC        |     &#10004;   | &#10004; |      4.7 (4.9 para Bypass de Mídia)      | &#10004; | &#10004; |  
|                     [Cisco](https://www.cisco.com/c/en/us/solutions/enterprise/interoperability-portal/networking_solutions_products_genericcontent0900aecd805bd13d.html)                               |     Elemento de borda unificada cisco (CUBE) para roteadores de serviços integrados da série 1000        |     &#10004;   | &#10004; |      Suportado no IOS XE Amsterdam 17.2.1r (recomendado 17.6.1a)         |    &#10004;     |   |  
|                                   |     Elemento de borda unificada cisco (CUBE) para roteadores de serviços integrados da série 4000        |     &#10004;   | &#10004; |   Suportado no IOS XE Amsterdam 17.2.1r (recomendado 17.6.1a)         |   &#10004;      |    |  
|                                   |     Cube (Elemento de Borda Unificada) da Cisco para Roteador de Serviços de Nuvem da Série 1000V       |     &#10004;   | &#10004; |      Suportado no IOS XE Amsterdam 17.2.1r (recomendado 17.3.3)         |    &#10004;     |    |  
|                                 |     CUBE (Elemento de Borda Unificada da Cisco) para roteadores dos Serviços de Agregação da Série 1000      |     &#10004;   | &#10004; |      Suportado no IOS XE Amsterdam 17.2.1r (recomendado 17.6.1a)         |    &#10004;     |    |
|                                 |     Cube (Elemento de Borda Unificada da Cisco) para Plataformas de Borda do Cube 8000      |     &#10004;   | &#10004; |      Suportado no IOS XE Amsterdam 17.3.2 (recomendado 17.6.1a)      |    &#10004;     |    |
|                     [Avaya](https://support.avaya.com/products/P0997/avaya-session-border-controller-for-enterprise/8.1.x)|    Controlador de Borda de Sessão Avaya para Empresas (ASBCE)    |     &#10004;     |       &#10004;     |       Versão 8.1.1 (8.1.2 para Bypass de Mídia)      |     |    |
|                     [Nokia](https://documentation.nokia.com/aces/cgi-bin/chk_access.cgi/3TB30222GBAAACZZA.zip)|    Controlador de Borda de Sessão da Nokia    |     &#10004;     |           |       19.5 (1908)       |     |    |
|                     |    Controlador de Borda de Sessão da Nokia    |     &#10004;     |           |       20.8       |      &#10004;        |    |
|                     [Italtel](https://www.italtel.com/italtel-provides-direct-routing-sbc-for-microsoft-teams/)|    NetMatch-S CI     |     &#10004;     |           |       5.0 com suporte (Recomendado 5.1)     |     |    |
|                     [Ericsson](https://www.ericsson.com/en/portfolio/digital-services/cloud-communication/enterprise-communication/business-communication-services-and-enablers/sip-trunking)|    vSBC 2.16     |     &#10004;     |           |              |     |    |
|                     [Cataleya](https://cataleya.com/orchidplatforms/)|    Link de Vínculo Orchid    |     &#10004;     |           |      3.1        |     |    |
|                     [ULTATEL](https://www.ultatel.com/services/direct-routing-teams-sbc)|    Teams SBC    |     &#10004;     |     &#10004;      |      1.6        |     |    |
|                     [Atos](https://unify.com/en/solutions/voice-platforms/session-border-controller)|    Controlador de Borda da Sessão Do Atos Unify OpenScape   |     &#10004;     |          |      V10R1.2       |     |    |
|                     [Sansay Inc.](https://www.sansay.com/solutions/microsoft-teams/)|    vmVSXi   |     &#10004;     |     &#10004;     |      10.5.1.354-vm-S-x64      |     |    |
|                     [Redes Enghouse](https://www.enghousenetworks.com/portfolio/network-infrastructure/cloud-native-session-border-controller-sbc/)|    Dialogic BorderNet SBC   |     &#10004;     |     &#10004;     |      3.9.0-786      |     |    |
|                     [Patton Electronics Co.](https://www.patton.com/microsoft/)|    Patton SmartNode eSBC   |     &#10004;     |         |      3.19.x      |     |    |
|                     [Tecnologias M5 (anteriormente conhecidas como Media5 Corporation)](https://www.m5t.com/solutions/sentinel-sbc-ms-teams-certified/)|    Série Mediatrix Sentinel   |     &#10004;     |         |      DGW 48.0.2340 (DGW recomendado 48.1.2503)      |     |    |
|                     [Ekinops](https://www.ekinops.com/solutions/voice-data-access/microsoft-direct-routing-sbc)|    Ekinops Session Border Controller (ONeSBC)   |     &#10004;     |     &#10004;     |      6.6.1m5ha1      |     |    |
|                     |    Ekinops Virtual Session Border Controller (ONEvSBC)   |     &#10004;     |    &#10004;      |      6.6.1m5ha1      |     |    |
|                     [46 Labs LLC](https://46labs.com/docs/hcvoice/teams/)|    Voz Hiperconvergente   |     &#10004;     |     &#10004;      |      HCVoice 1.0.6       |     |    |

<br/>

\* **911 prestadores de serviços**

- [Roteamento de Local Dinâmico de Largura de Banda](https://www.bandwidth.com/partners/microsoft-teams-direct-routing/)
- [ERS (Serviço de Roteamento de Emergência Intrado)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Gateway de Emergência Intrado (EGW)](https://www.west.com/safety-services/enterprise-e911-solutions/microsoft-teams-e911-solutions/)
- [Inteliquent](https://www.inteliquent.com/services/emergency-services/e911)

<br/>

## <a name="support-for-local-media-optimization"></a>Suporte para Otimização de Mídia Local

A tabela a seguir descreve quais fornecedores de SBC têm suporte para [Otimização de Mídia Local.](direct-routing-media-optimization.md) 

| Fornecedor | Produto |    Versão de software |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.258 | 
|            |  Controlador de borda da sessão Mediant 2600 |  7.20A.258 | 
|            |  Controlador de borda da sessão Mediant 4000 |  7.20A.258 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.258 | 
|            |  Controlador de borda da sessão Virtual Edition |   7.20A.258 | 
|            |  Mediant Cloud Edition SBC | 7.20A.258 |
| [Ribbon SBC Core](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Ribbon SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |




## <a name="direct-routing-and-analog-devices-interoperability"></a>Roteamento Direto e interoperabilidade de dispositivos analógicos

A tabela a seguir lista os dispositivos verificados para interoperabilidade entre o Roteamento Direto e Dispositivos Analógicos.

|                                                       Fornecedor                                                        |       Produto       | Verificado
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-1](https://www.audiocodes.com/media/2373/mp-1xx-and-mp-124-datasheet.pdf)   |     &#10004;     |
| [AudioCodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   [ATA-2](https://www.audiocodes.com/media/2399/mediapack-20x-mp-20x-analog-telephone-adapters-datasheet.pdf)   |     &#10004;     | 
| [Cisco](https://www.cisco.com/c/en/us/products/collateral/unified-communications/ata-190-series-analog-telephone-adapters/datasheet-c78-740013.html) |  Adaptador de Telefone Analógico multiplataforma ATA 191 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |   SOFTWARE AP1100 Versão 8.3.0.1.2 |     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP3900 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP4600 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP6300 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software AP6350 Versão 8.3.0.1.2|     &#10004;     |
| [Oracle](https://www.oracle.com/technical-resources/documentation/acme-packet.html) |  Software VME versão 8.3.0.1.2 |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 1000. Versão do software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [SBC 2000. Versão do software: 8.1.1 (build 527)](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 302. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 304. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 2900A. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4806. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 4808. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [Faixa de Opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions) |   [EdgeMarc 6000. Versão do software: 16.1.1](https://ribboncommunications.com/products/service-provider-products/cloud-and-edge/session-border-controllers/session-border-controllers-edge-appliances)   |     &#10004;     |
| [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/) |  anynode com o Grandstream GXW42xx (V1.0.7.10) |     &#10004;     |
  
Para fazer comentários sobre o Teams, como ideias de novos recursos, visite o [UserVoice](https://microsoftteams.uservoice.com).


[!INCLUDE [uservoice-disclaimer-note](includes/uservoice-disclaimer-note.md)]

Observe a certificação concedida a uma versão principal. Isso significa que há suporte para o firmware com qualquer número no firmware SBC após a versão principal.
