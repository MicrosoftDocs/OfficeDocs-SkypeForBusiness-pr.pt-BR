---
title: 'Estudo de caso da Contoso: Sistema de Telefonia para uma empresa multi-nacional'
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
description: 'Teams caso de voz para empresas multinacionais: sistema de telefonia'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 95ba8e36948a3d61a2e81f9c1954919709eb3a77
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823662"
---
# <a name="contoso-case-study-phone-system-for-a-multi-national-corporation"></a>Estudo de caso da Contoso: Sistema de Telefonia para uma empresa multi-nacional

Dependendo da localização geográfica e de outros fatores, a Contoso tinha escritórios usando as seguintes soluções de telefonia:

- Tipo de site A: Skype for Business Enterprise Voice

- Tipo de site B: sistemas de telefonia herdados tradicionais

- Tipo de site C: uma combinação de Skype for Business Enterprise Voice sistemas de telefonia herdados tradicionais


Para implementar uma solução do Telefone Microsoft System para toda a organização, a Contoso&mdash;precisava determinar para cada tipo de site&mdash;quais das seguintes opções seriam usadas com o Sistema de Telefonia para se conectar à PSTN (Rede Telefônica Pública Comunada):

- Sistema de Telefonia com Plano de Chamada 

- Sistema de Telefonia com a própria operadora PSTN por meio do Roteamento Direto 

- Combinação de Sistema de Telefonia com Plano de Chamada e Sistema de Telefonia com a própria operadora PSTN por meio do Roteamento Direto
 
Para determinar a solução certa para sua organização, a Contoso usou Planejar sua solução de voz [Teams](/microsoftteams/cloud-voice-landing-page) e a sessão Do Ignite 2019 chamada no [Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/what-s-new-for-calling-in-microsoft-teams-ignite-2019-edition/ba-p/974935).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de site A: Skype for Business Enterprise Voice 

A Contoso Skype for Business Enterprise Voice configurada como hub e spoke. Havia um local central que manteve o gateway PSTN na região que forneceu a conexão com o PSTN para os usuários Skype for Business Enterprise Voice no país. Muitas vezes, esses escritórios satélite não têm sua própria saída de Internet. Os números para esses usuários residiam no tronco SIP que se conecta a um SBC existente. 

Para determinar se o SBC já implantado é certificado para Roteamento Direto e Bypass de Mídia, a Contoso verificou a Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto](direct-routing-border-controllers.md).  

Os hábitos de discagem do usuário eram discar um usuário no sistema de telefonia herdado usando uma extensão, mesmo quando o usuário tem um cliente Skype for Business disponível para áudio ponto a ponto. 

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida por nossa implantação local?<br>
  Um. Não 

- Q. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br>
  Um. Não 

- Q. Precisamos manter nossa operadora de terceiros atual?<br> Um. Sim (países regulamentados) e Não 

- Q. Precisamos implantar o ROI em SBCs?<br> Um. Sim e Não  

- Q. Os Planos de Chamadas PSTN da Microsoft estão disponíveis nesta região?<br> Um. Sim e Não 

Com base nas respostas para suas perguntas, a Contoso decidiu:

- Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para Sistema de Telefonia planos de chamadas. 

- Mova os usuários que não estão localizados em uma região onde os planos de chamadas PSTN estão disponíveis, os usuários localizados em um site em que o ROI nos SBCs ainda não foram atendidos e os usuários que residiam em um país que tenha regulamentos de telefonia para Sistema de Telefonia com Roteamento Direto. 

O diagrama a seguir mostra a implantação Skype for Business Enterprise Voice inicial e como essa implantação foi migrada para os Planos de Chamadas da Microsoft e o Roteamento Direto:

![O diagrama mostra os estados antes e depois.](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de site B: sistemas de telefonia herdados tradicionais

A Contoso tinha muitos escritórios que aproveitaram sistemas de telefonia herdados. Havia um subconjunto de usuários que tinham um número de telefone E1.64, enquanto outros tinham apenas uma extensão. Esses números residiam no tronco TDM para o gateway PSTN. A discagem intra-site foi configurada aproveitando um código do site na frente da extensão para determinar para onde rotear a chamada. Os hábitos de discagem dos usuários eram discar por extensão.   

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida por nossa implantação local?<br>
  Um. Não 

- Q. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> Um. Sim

- Q. Precisamos manter nossa operadora de terceiros atual?<br> Um. Não 

- Q. O Plano de Chamadas da Microsoft PSTN está disponível em nossa região?<br> Um. Sim e Não 

Com base nas respostas para suas perguntas, a Contoso decidiu: 

- Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para Sistema de Telefonia planos de chamadas. 

- Mova os usuários que não estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para Sistema de Telefonia roteamento direto. 

- Manter uma conexão PSTN com dispositivos analógicos comercialmente críticos.

Os diagramas a seguir mostram a implantação original do sistema herdado com sites remotos e a migração para uma implantação de Roteamento Direto com Otimização de Mídia Local:

**Implantação herdada original** 
![ Um diagrama mostra os estados antes e depois.](media/voice-case-study-2.png)


**Implantação com Roteamento Direto**

![Um diagrama mostrando os estados antes e depois.](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de site C: combinação de Skype for Business Enterprise Voice e sistemas de telefonia herdados tradicionais

A Contoso Skype for Business Enterprise Voice os números dos usuários residem no tronco SIP para o SBC da operadora. Os números dos sistemas de telefonia tradicionais residiam no tronco TDM para o gateway PSTN.   

A Contoso baseou sua decisão nas seguintes perguntas:

- Q. Precisamos manter a funcionalidade fornecida por nossa implantação local?<br>
  Um. Não 

- Q. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> Um. Não 

- Q. Precisamos manter nossa operadora de terceiros atual?<br> Um. Não 

- Q. Precisamos implantar o ROI em SBCs?<br> Um. Sim e Não  

- Q. O Plano de Chamadas PSTN da Microsoft está disponível nesta região?<br> Um. Não 

Com base nas respostas para suas perguntas, a Contoso decidiu o seguinte: 

- Para os usuários de telefonia herdados que serão habilitados para Roteamento Direto, a Contoso porificou os números do tronco TDM para o Tronco SIP para o SBC, pois o SBC é certificado para Roteamento Direto. 

- Para dar suporte a um subconjunto de usuários migrando para o Sistema de Telefonia e permitir o roteamento contínuo por meio do sistema herdado, o sistema de telefonia herdado foi configurado como o próximo salto para o SBC.   

- Além disso, para incentivar a alteração de comportamento do usuário e remover a dependência da discagem entre extensões entre sites, a Contoso forneceu diretrizes para usar Teams para todas as chamadas internas.  

Os diagramas a seguir mostram a implantação original Skype for Business Enterprise Voice sistema de telefonia herdado e a migração para uma implantação mista usando o Roteamento Direto:

**Implantação misturada original**
![ Diagrama 1 mostrando o estado anterior.](media/voice-case-study-4.png)

**Implantação mista com Roteamento Direto**
![ Diagrama 2 mostrando o estado anterior.](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planos de Chamadas

Para determinar os requisitos de configuração para Planos de Chamadas, a Contoso examinou as decisões de [implantação principais do Plano de Chamada](calling-plan-landing-page.md#core-deployment-decisions). As decisões resultantes foram tomadas: 

- Q. Meus usuários precisam de chamadas internacionais?<br> Um. Sim 

- Q. Cada um dos meus usuários tem um número de telefone DID direto para dentro?<br> R. Não hoje. Todos os usuários habilitados receberão um DID. 

- Q. Deseja mascarar ou desabilitar a ID do chamador?<br> Um. A ID do chamador de um usuário será mascarada para o número local da Contoso. 


## <a name="direct-routing"></a>Roteamento Direto

A Contoso participou do Ignite para se manter Office 365 recursos, incluindo aqueles disponíveis com o Telefone e o Roteamento Direto. Liderança técnica e arquitetos usaram as diretrizes fornecidas durante o Ignite 2019 para determinar sua direção.  Sessões de chave que foram usadas: 

- [Planejar o sucesso com o Microsoft Teams Roteamento Direto](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)

- [Atualizações para Roteamento Direto](https://docs.shanehoey.com/videos/ignite/ignite19-planfor%20successwithteamsdirectrouting/)


## <a name="configuration"></a>Configuração

### <a name="calling-plans-sites"></a>Sites de Planos de Chamadas

Para obter licenças e atribuir números de telefone aos usuários, a Contoso seguiu as etapas em [Configurar Planos de Chamadas](set-up-calling-plans.md). 

Devido ao número de usuários que precisavam receber números de telefone, a Contoso decidiu usar o PowerShell para atribuir os números de telefone. Para saber como atribuir números usando o PowerShell&mdash;&mdash;, além de outras configurações, a Contoso usou a [Teams do PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Sites de Roteamento Direto

Para conectar a infraestrutura de telefonia local da Contoso ao Microsoft Teams, o administrador da Contoso seguiu as etapas em Configurar Roteamento Direto [](direct-routing-configure.md) e examinou o vídeo roteamento direto no [Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obter diretrizes.  A Contoso também se referi à documentação de implantação de roteamento direto pelo fornecedor certificado do SBC. 

Depois que o Roteamento Direto foi configurado entre o SBC e o Telefone Microsoft, foi necessário que a Contoso testa a configuração. Para fazer isso, os administradores da Contoso usaram o cliente do Testador SIP que foi discutido na sessão 'Atualizações para Roteamento Direto no [Ignite 2019](https://techcommunity.microsoft.com/t5/microsoft-teams-events-blog/ignite-live-blog-session-vce20-updates-for-direct-routing/ba-p/1025138). O script e a documentação do cliente do Testador SIP foram baixados do script do PowerShell para testar as conexões do Controlador de Borda da Sessão de Roteamento Direto.   


### <a name="local-media-optimization"></a>Otimização de mídia local

A Contoso viu a oportunidade de aproveitar a Otimização de Mídia Local nas diferentes regiões em todo o mundo. Os cenários com suporte para a Contoso são descritos na Otimização [de Mídia Local para Roteamento Direto](direct-routing-media-optimization.md). A configuração da otimização de mídia local foi concluída seguindo as diretrizes do fornecedor SBC e da Microsoft. As etapas de configuração para Otimização de Mídia Local incluem: 

- Configurar o usuário e os sites SBC 

- Configure o SBC de acordo com a especificação do fornecedor SBC, 

- Adicionar endereços IP confiáveis externos a cada site usado para Otimização de Mídia Local    

- Definir a topologia de rede 

- Definir a topologia de rede virtual 

- Determinar o modo: Sempre Ignorar ou Somente para usuários locais 

## <a name="networking-considerations"></a>Considerações de rede

A Contoso tinha vários usuários que precisavam trabalhar remotamente por um longo período de tempo depois de serem habilitados para Sistema de Telefonia. Os usuários usaram VPN para acessar determinados aplicativos de Linha de Negócios. Durante a VPN, os usuários Sistema de Telefonia experimentaram uma degradação da qualidade da chamada. 

Para resolver o problema de qualidade, a Contoso implementou o túnel dividido de VPN, o que permitiu que o tráfego Office 365 atravessasse a Internet enquanto a conexão com os aplicativos internos permanecesse na VPN. Para implementar o túnel dividido de VPN, a Contoso seguiu as diretrizes para implementar o túnel [dividido de VPN para Office 365](/office365/enterprise/office-365-vpn-implement-split-tunnel).  

