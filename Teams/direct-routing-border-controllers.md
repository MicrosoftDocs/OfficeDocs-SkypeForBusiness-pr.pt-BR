---
title: Lista de controladores de borda da sessão certificados para Roteamento Direto
ms.author: crowe
ms.reviewer: NMuravlyannikov
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
description: A Microsoft faz parceria com fornecedores selecionados de SBC (controlador de borda da sessão) para garantir que seus SBCs sejam compatíveis com o Roteamento Direto.
ms.openlocfilehash: b574911c2d819e665f088ec8be12f24e1830daf2
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837581"
---
# <a name="list-of-session-border-controllers-certified-for-direct-routing"></a>Lista de controladores de borda da sessão certificados para Roteamento Direto

A Microsoft faz parceria com fornecedores selecionados de Controlador de Borda da Sessão (SBC) para garantir que seus SBCs sejam compatíveis com o Roteamento Direto. 

O Microsoft funciona com cada fornecedor para: 

- Trabalhe em conjunto com os protocolos SIP Interconnection.
- Realize testes intensivos usando um laboratório de terceiros. Somente os dispositivos que passam nos testes são certificados. 
- Executar testes diários com todos os dispositivos certificados em ambientes de produção e de pré-produção. A validação dos dispositivos em ambientes de pré-produção garante que as novas versões do código de Roteamento Direto na nuvem funcionarão com os SBCs certificados. 
- Estabeleça um processo de suporte conjunto com os fornecedores do SBC.


  > [!NOTE]
  > A Microsoft só oferece suporte ao sistema telefônico se um dispositivo ou dispositivos certificados estiverem conectados por meio de roteamento direto. A Microsoft se reserva o direito de rejeitar casos de suporte em que um dispositivo não certificado está conectado ao sistema telefônico por meio de roteamento direto. 

A tabela a seguir lista os dispositivos certificados para Roteamento Direto. 

[Saiba mais sobre o Roteamento Direto](https://aka.ms/dr). Se você tiver dúvidas sobre o programa de certificação SBC para roteamento direto, entre em contato com a drsbccertification@microsoft.com.


|                                                       Fornecedor                                                        |       Produto       | Ignorar não em mídia | Bypass de mídia | Versão do software | Validado com provedores E911 | Compatível com ELIN
|---------------------------------------------------------------------------------------------------------------------|---------------------|------------------|--------------|------------------|-----------------|------------------|
| [Audiocodes](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams) |   Mediant 500 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |
|                                                                                                                     |   Mediant 800 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |
|                                                                                                                     |  Mediant 2600 SBC   |     &#10004;     |   &#10004;    |  7.20 a. 250   |     |    |    
|                                                                                                                     |  Mediant 4000 SBC   |     &#10004;     |   &#10004;     |  7.20 a. 250   |     |    |    
|                                                                                                                     | Mediant 1000B SBC  |     &#10004;     |   Pendente     |  7.20 a. 250  |    |    |    
|                                                                                                                     | Mamédia 9000 SBC  |     &#10004;     |   &#10004;     |  7.20 a. 250   |    |    |                                                                       
|                                                                                                                     | Virtual Edition SBC |     &#10004;     |   &#10004;     |  7.20 a. 250 |    |    |    
|  [Comunicações da faixa de opções](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-skype-business)  |      SBC 5110       |     &#10004;     |   &#10004;    |       V 7.2       |  Inentrada ERS <br>Inentrada EGW |   Não |    
|                                                                                                                     |      SBC 5210       |     &#10004;     |  &#10004;    |       V 7.2       |   Inentrada ERS <br>Inentrada EGW  | Não   |    
|                                                                                                                     |      SBC 5400       |     &#10004;     |   &#10004;   |       V 7.2       |  Inentrada ERS <br>Inentrada EGW    |Não|    
|                                                                                                                     |      SBC 7000       |     &#10004;     |   &#10004;    |       V 7.2       |   Inentrada ERS <br>Inentrada EGW  |  Não  |    
|                                                                                                                     |       SBC SWe       |     &#10004;     |   &#10004;   |       V 7.2       |   Inentrada ERS <br>Inentrada EGW |   Não |    
|                                                                                                                     |      SBC 1000       |     &#10004;     |   &#10004;    |      v 8.0.3 (Build 537)     |  Inentrada ERS <br>Inentrada EGW   |  Pendente  |    
|                                                                                                                     |      SBC 2000       |     &#10004;     |   &#10004;   |     v 8.0.3 (Build 537)     |  Inentrada ERS <br>Inentrada EGW  |  Pendente  |    
|                                                                                                                     |    SBC SWe Lite     |     &#10004;     |  &#10004;    |      v 8.0.3 (Build 216)    |  Inentrada ERS <br>Inentrada EGW   |  Pendente  |    
|                     [Thinktel](https://www.thinktel.ca/services/think-365/think-365-overview/)                      |    Think 365 SBC    |     &#10004;     |   Pendente    |       V1.4       |     |    |    
|                     [Oracle](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)                      |    AP 1100      |    &#10004;     |    &#10004;    |   8.3.0.0.1 |   Inentrada ERS <br>Inentrada EGW  |    |    
|                                                                                                                    |    AP 3900           |    &#10004;     |    &#10004;   |   8.3.0.0.1  |   Inentrada ERS <br>Inentrada EGW  |    |    
|                                                                                                                    |      AP 4600         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |   Inentrada ERS <br>Inentrada EGW |    |    
|                                                                                                                    |      AP 6300         |    &#10004;   |    &#10004;     |     8.3.0.0.1  |  Inentrada ERS <br>Inentrada EGW  |    |    
|                                                                                                                   |      AP 6350           |    &#10004;   |    &#10004;    |     8.3.0.0.1  |   Inentrada ERS <br>Inentrada EGW |    |                                            
|                                                                                                                    |      VME           |    &#10004;    |    &#10004;    |     8.3.0.0.1   |   Inentrada ERS <br>Inentrada EGW  |    |    
|                     [TE-SYSTEMS](https://www.anynode.de/anynode-and-microsoft-teams/)                               |     anynode         |     &#10004;   |  &#10004;   |      v3.16.2      |     |    |    

Para dar a seus comentários sobre o produto sobre equipes, como ideias para novos recursos, confira nota do [UserVoice](https://microsoftteams.uservoice.com) a certificação concedida a uma versão principal. Isso significa que o firmware com qualquer número no firmware SBC após a versão principal tem suporte.
