---
title: Estudo de caso do Teams voice Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Estudo de caso de voz do Teams para corporação multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785944"
---
# <a name="contoso-case-study-phone-system"></a>Estudo de caso da Contoso: Sistema telefônico

Dependendo da localização geográfica e de outros fatores, a Contoso tinha escritórios usando as seguintes soluções de telefonia:

- Tipo de Site A: Skype for Business Enterprise Voice

- Tipo de site B: sistemas tradicionais de telefonia herdados

- Tipo de Site C: uma combinação do Skype for Business Enterprise Voice e sistemas tradicionais de telefonia herdados


Para implementar uma solução do Microsoft Phone System para toda a organização, a Contoso teve que determinar para cada tipo de site qual das seguintes opções seria usada com o Sistema telefônico para se conectar à &mdash; PSTN (Rede Telefônica Pública &mdash; Comutado):

- Sistema telefônico com Plano de Chamada 

- Sistema telefônico com sua própria operadora PSTN por meio de Roteamento Direto 

- Combinação do Sistema telefônico com o Plano de Chamada e o Sistema telefônico com a própria operadora PSTN por meio do Roteamento Direto
 
Para determinar a solução certa para sua organização, a Contoso usou soluções de telefonia da [Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e a Chamada de sessão Ignite 2019 [no Microsoft Teams.](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions)  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de Site A: Skype for Business Enterprise Voice 

O Skype for Business Enterprise Voice da Contoso foi criado como um hub e falado. Havia um local central que mantém o gateway PSTN na região que forneceu a conexão com o PSTN para os usuários do Skype for Business Enterprise Voice no país. Muitas vezes, esses escritórios de satélite não têm sua própria saída de Internet. Os números desses usuários residiam no tronco SIP que se conecta a um SBC existente. 

Para determinar se o SBC já implantado é certificado para Roteamento Direto e Bypass de Mídia, a Contoso verificou a Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)  

Os hábitos de discagem do usuário eram discar para um usuário no sistema de telefonia herdado usando uma extensão, mesmo quando o usuário tem um cliente Skype for Business disponível para áudio ponto a ponto. 

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida pela nossa implantação local?<br>
  Um. Não 

- Q. Precisamos operar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br>
  Um. Não 

- Q. Precisamos manter nossa operadora terceirizada atual?<br> Um. Sim (países regulamentados) e Não 

- Q. Precisamos implantar o ROI em SBCs?<br> Um. Sim e Não  

- Q. Os Planos de Chamada PSTN da Microsoft estão disponíveis nesta região?<br> Um. Sim e Não 

Com base nas respostas às suas perguntas, a Contoso decidiu:

- Mova os usuários localizados em uma região onde os planos de chamada PSTN estão disponíveis para o Sistema de Telefonia com Planos de Chamada. 

- Mova os usuários que não estão localizados em uma região onde os planos de chamada PSTN estão disponíveis, os usuários localizados em um site onde o ROI nos SBCs ainda não foram atendidos e os usuários que residiram em um país que tenha regulamentos de telefonia para o Sistema de Telefonia com Roteamento Direto. 

O diagrama a seguir mostra a implantação inicial do Skype for Business Enterprise Voice e como essa implantação foi migrada para os Planos de Chamada da Microsoft e o Roteamento Direto:

![Diagrama mostrando estados antes e depois](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de site B: sistemas tradicionais de telefonia herdados

A Contoso tinha muitos escritórios que utilizava sistemas de telefonia herdados. Havia um subconjunto de usuários que tinha um número de telefone E1.64, enquanto outros tinham apenas uma extensão. Esses números residiam no tronco TDM do gateway PSTN. A discagem no local foi configurada aproveitando um código de site na frente da extensão para determinar para onde encaminhar a chamada. Os hábitos de discagem dos usuários eram discar por extensão.   

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida pela nossa implantação local?<br>
  Um. Não 

- Q. Precisamos operar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> Um. Sim

- Q. Precisamos manter nossa operadora terceirizada atual?<br> Um. Não 

- Q. O Plano de Chamada PSTN da Microsoft está disponível em nossa região?<br> Um. Sim e Não 

Com base nas respostas às suas perguntas, a Contoso decidiu: 

- Mova os usuários localizados em uma região onde os planos de chamada PSTN estão disponíveis para o Sistema de Telefonia com Planos de Chamada. 

- Mova os usuários que não estão localizados em uma região onde os planos de chamada PSTN estão disponíveis para o Sistema de Telefonia com Roteamento Direto. 

- Mantenha uma conexão PSTN com dispositivos analógicos críticos comerciais.

Os diagramas a seguir mostram a implantação original do sistema herdados com sites remotos e a migração para uma implantação de Roteamento Direto com Otimização de Mídia Local:

**Implantação herdda original**  
 ![ Diagrama mostrando estados antes e depois](media/voice-case-study-2.png)


**Implantação com Roteamento Direto**

![Diagrama mostrando estados antes e depois](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de site C: combinação do Skype for Business Enterprise Voice e sistemas tradicionais de telefonia herdados

Os números dos usuários do Skype for Business Enterprise Voice da Contoso residem no tronco SIP do SBC da operadora. Os números dos sistemas de telefonia tradicionais residiam no tronco TDM para o gateway PSTN.   

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida pela nossa implantação local?<br>
  Um. Não 

- Q. Precisamos operar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> Um. Não 

- Q. Precisamos manter nossa operadora terceirizada atual?<br> Um. Não 

- Q. Precisamos implantar o ROI em SBCs?<br> Um. Sim e Não  

- Q. O Plano de Chamada PSTN da Microsoft está disponível nesta região?<br> Um. Não 

Com base nas respostas às suas perguntas, a Contoso decidiu o seguinte: 

- Para os usuários de telefonia herdados que serão habilitados para Roteamento Direto, a Contoso portou os números do tronco TDM para o Tronco SIP do SBC, uma vez que o SBC é certificado para Roteamento Direto. 

- Para dar suporte a um subconjunto de usuários que se movem para o Sistema telefônico e para permitir o roteamento contínuo pelo sistema herdado, o sistema de telefonia herdado foi definido como o próximo salto para o SBC.   

- Além disso, para incentivar a mudança de comportamento do usuário e remover a dependência com a discagem de extensão inter e intra-site, a Contoso forneceu orientação para usar o Teams para todas as chamadas internas.  

Os diagramas a seguir mostram a implantação original do Skype for Business Enterprise Voice e o sistema de telefonia herdado e a migração para uma implantação mista usando o Roteamento Direto:

**Implantação mista original** 
 ![ Diagrama mostrando antes do estado](media/voice-case-study-4.png)

**Implantação mista com Roteamento Direto** 
 ![ Diagrama mostrando antes do estado](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planos de Chamadas

Para determinar os requisitos de configuração para Planos de Chamada, a Contoso revisões das decisões de implantação principais do Plano [de Chamada.](calling-plan-landing-page.md#core-deployment-decisions) As decisões resultantes foram tomadas: 

- Q. Meus usuários precisam de chamada internacional?<br> Um. Sim 

- Q. Cada um dos meus usuários tem um número de telefone DID direto para dentro?<br> R. Não hoje. Todos os usuários habilitados receberão um DID. 

- Q. Quero mascarar ou desabilitar a ID de chamador?<br> Um. A ID de chamada de um usuário será mascarada para o número local da Contoso. 


## <a name="direct-routing"></a>Roteamento Direto

A Contoso participou do Ignite para se manter atualizado sobre os recursos do Office 365, incluindo aqueles disponíveis com o sistema De telefonia e o Roteamento Direto. A liderança técnica e os arquitetos usaram as orientações fornecidas durante o Ignite 2019 para determinar sua direção.  Principais sessões que foram usadas: 

- [Planejar o sucesso com o Roteamento Direto do Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Atualizações para Roteamento Direto](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuração

### <a name="calling-plans-sites"></a>Sites de Planos de Chamada

Para obter licenças e atribuir números de telefone aos usuários, a Contoso seguiu as etapas em [Configurar Planos de Chamada.](set-up-calling-plans.md) 

Devido ao número de usuários que precisavam ter números de telefone atribuídos, a Contoso decidiu usar o PowerShell para atribuir os números de telefone. Para saber como atribuir números usando o PowerShell, além de outras configurações, a Contoso usou a Visão Geral do &mdash; &mdash; [PowerShell do Teams.](teams-powershell-overview.md)  

### <a name="direct-routing-sites"></a>Sites de Roteamento Direto

Para conectar a infraestrutura de telefonia local da Contoso ao Microsoft Teams, [](direct-routing-configure.md) o administrador da Contoso seguiu as etapas em Configurar Roteamento Direto e reviu o vídeo roteamento direto no [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obter orientação.  A Contoso também se refere à documentação de implantação de roteamento direto pelo fornecedor SBC certificado. 

Depois que o Roteamento Direto foi configurado entre o SBC e o Microsoft Phone System, foi necessário que a Contoso testa a configuração. Para fazer isso, os administradores da Contoso usaram o cliente de Teste SIP que foi discutido na sessão Atualizações para Roteamento Direto no [Ignite 2019.](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions) O script e a documentação do cliente de Teste SIP foram baixados do script do PowerShell para testar as conexões do Controlador de Borda de Sessão de Roteamento Direto.   


### <a name="local-media-optimization"></a>Otimização de mídia local

A Contoso viu a oportunidade de aproveitar a Otimização de Mídia Local nas diferentes regiões do mundo. Os cenários com suporte para a Contoso são descritos na Otimização [de Mídia Local para Roteamento Direto.](direct-routing-media-optimization.md) A configuração da otimização de mídia local foi concluída seguindo as orientações do fornecedor SBC e da Microsoft. As etapas de configuração para Otimização de Mídia Local incluem: 

- Configurar o usuário e os sites SBC 

- Configurar o SBC de acordo com a especificação do fornecedor SBC, 

- Adicionar endereços IP confiáveis externos a cada site usado para Otimização de Mídia Local    

- Definir a topologia de rede 

- Definir a topologia de rede virtual 

- Determinar o modo: Sempre Ignorar ou Somente para usuários locais 

## <a name="networking-considerations"></a>Considerações sobre a rede

A Contoso tinha vários usuários que precisavam trabalhar remotamente por um longo período de tempo após a habilitação para o Sistema de Telefonia. Os usuários usavam VPN para acessar determinados aplicativos de Linha de Negócios. Durante a VPN, os usuários do Sistema de Telefonia experimentaram uma degradação da qualidade da chamada. 

Para resolver o problema de qualidade, a Contoso implementou o túnel de divisão VPN, que permitia que o tráfego do Office 365 percorresse a Internet enquanto a conexão com os aplicativos internos permanecesse na VPN. Para implementar o túnel de divisão VPN, a Contoso seguiu as diretrizes para implementar o túnel de divisão VPN para [o Office 365.](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel)  

 





