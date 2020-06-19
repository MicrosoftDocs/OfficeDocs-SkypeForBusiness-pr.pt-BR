---
title: Estudo de caso da Contoso Voice Teams
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
description: Estudo de caso de voz do teams para Multi-National Corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7431515d40550a3f731c34f97ed8c10586424901
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44785944"
---
# <a name="contoso-case-study-phone-system"></a>Estudo de caso da Contoso: sistema telefônico

Dependendo da localização geográfica e de outros fatores, a Contoso tinha escritórios usando as seguintes soluções de telefonia:

- Tipo de site A: Skype for Business Enterprise Voice

- Tipo de site B: sistemas de telefonia herdados tradicionais

- Tipo de site C: uma combinação do Skype for Business Enterprise Voice e dos sistemas de telefonia herdados tradicionais


Para implementar uma solução de sistema telefônico da Microsoft para toda a sua organização, a Contoso tinha que determinar &mdash; para cada tipo &mdash; de site quais das seguintes opções seriam usadas com o sistema telefônico para se conectar à rede telefônica pública comutada (PSTN):

- Sistema telefônico com plano de chamada 

- Sistema telefônico com uma transportabilidade PSTN por meio do roteamento direto 

- Combinação de sistema telefônico com plano de chamada e sistema telefônico com a própria transportabilidade PSTN por meio do direcionamento direto
 
Para determinar a solução certa para sua organização, a contoso usou [soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions) e as chamadas de sessão do Ignite 2019 [no Microsoft Teams](https://myignite.techcommunity.microsoft.com/sessions/83170?source=sessions).  

## <a name="site-type-a-skype-for-business-enterprise-voice"></a>Tipo de site A: Skype for Business Enterprise Voice 

O Skype for Business Enterprise Voice da Contoso foi configurado como Hub e spoke. Havia um local central que mantinha o gateway PSTN na região que forneceu a conexão com a PSTN para os usuários do Skype for Business Enterprise Voice em país. Geralmente, esses telefones de satélite não têm o seu próprio egresso na Internet. Os números para esses usuários residem no tronco SIP se conectando a um SBC existente. 

Para determinar se o SBC já implantado é certificado para roteamento direto e bypass de mídia, a contoso verificou a [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).  

Os hábitos de discagem do usuário eram discar um usuário no sistema de telefonia herdado usando uma extensão, mesmo quando o usuário tem um cliente Skype for Business disponível para o áudio ponto a ponto. 

A contoso baseou suas decisões nas seguintes perguntas:

- I. Precisamos manter a funcionalidade oferecida pela sua implantação local?<br>
  Um. Não 

- I. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br>
  Um. Não 

- I. Precisamos manter o nosso carro de terceiros atual?<br> A. Sim (países regulamentados) e não 

- I. Precisamos ter o ROI implantado no SBCs?<br> A. Sim e não  

- I. Os planos de chamada PSTN da Microsoft estão disponíveis nesta região?<br> A. Sim e não 

Com base nas respostas às suas perguntas, a Contoso decidiu:

- Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com planos de chamada. 

- Mover os usuários que não estão localizados em uma região em que os planos de chamada PSTN estão disponíveis, os usuários localizados em um site em que o ROI do SBCs ainda devem ser atendidos e os usuários residentes em um país que tenha regulamentos de telefonia para o sistema telefônico com roteamento direto. 

O diagrama a seguir mostra a implantação inicial do Skype for Business Enterprise Voice e como essa implantação foi migrada para os planos de chamada da Microsoft e para o roteamento direto:

![Diagrama mostrando o estado anterior e posterior](media/voice-case-study-1.png)

## <a name="site-type-b-traditional-legacy-telephony-systems"></a>Tipo de site B: sistemas de telefonia herdados tradicionais

A Contoso tinha muitos escritórios que aproveitaram os sistemas de telefonia herdados. Havia um subconjunto de usuários que tinham um número de telefone E 1.64 enquanto outras pessoas tinham apenas uma extensão. Esses números residem no tronco TDM para o gateway PSTN. A discagem dentro do site foi configurada aproveitando um código de site na frente da extensão para determinar onde direcionar a chamada. Os hábitos de discagem dos usuários eram discados por extensão.   

A contoso baseou suas decisões nas seguintes perguntas:

- I. Precisamos manter a funcionalidade oferecida pela sua implantação local?<br>
  Um. Não 

- I. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> A. Sim

- I. Precisamos manter o nosso carro de terceiros atual?<br> R. no 

- I. O plano de chamadas de PSTN da Microsoft está disponível na nossa região?<br> A. Sim e não 

Com base nas respostas às suas perguntas, a Contoso decidiu: 

- Mova os usuários que estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com planos de chamada. 

- Mova os usuários que não estão localizados em uma região em que os planos de chamada PSTN estão disponíveis para o sistema telefônico com roteamento direto. 

- Mantenha uma conexão PSTN com dispositivos analógicos críticos para empresas.

Os diagramas a seguir mostram a implantação de sistema original herdada com sites remotos e a migração para uma implantação de roteamento direto com a otimização de mídia local:

**Original legacy deployment**  
 Implantação ![ herdada original Diagrama mostrando o estado anterior e posterior](media/voice-case-study-2.png)


**Implantação com roteamento direto**

![Diagrama mostrando o estado anterior e posterior](media/voice-case-study-3.png)
 
## <a name="site-type-c-combination-of-skype-for-business-enterprise-voice-and-traditional-legacy-telephony-systems"></a>Tipo de site C: combinação do Skype for Business Enterprise Voice e sistemas de telefonia herdados tradicionais

Os números de usuários do Skype for Business Enterprise Voice do contoso residem no tronco SIP para o SBC da operadora. Os números dos sistemas de telefonia tradicionais residem no tronco TDM para o gateway PSTN.   

A contoso baseou suas decisões nas seguintes perguntas:

- I. Precisamos manter a funcionalidade oferecida pela sua implantação local?<br>
  Um. Não 

- I. Precisamos interoperar com sistemas PBX de terceiros e outros equipamentos de telefonia?<br> R. no 

- I. Precisamos manter o nosso carro de terceiros atual?<br> R. no 

- I. Precisamos ter o ROI implantado no SBCs?<br> A. Sim e não  

- I. O plano de chamada PSTN da Microsoft está disponível nesta região?<br> R. no 

Com base nas respostas às suas perguntas, a Contoso decidiu o seguinte: 

- Para os usuários de telefonia herdados que serão habilitados para roteamento direto, a contoso portou os números do tronco TDM para o tronco SIP para o SBC, pois o SBC é certificado para roteamento direto. 

- Para dar suporte a um subconjunto de usuários que se movem para o sistema telefônico e para permitir roteamento contínuo por meio do sistema herdado, o sistema de telefonia herdado foi configurado como o próximo salto para o SBC.   

- Além disso, para incentivar a mudança de comportamento do usuário e remover a dependência na discagem de extensão entre sites, a contoso forneceu orientação para usar o Microsoft Teams para todas as chamadas internas.  

Os diagramas a seguir mostram a implantação original do Skype for Business Enterprise Voice e do sistema de telefonia herdada e a migração para uma implantação mista usando o roteamento direto:

**Original mixed deployment** 
 Implantação ![ mista original Diagrama mostrando o estado anterior](media/voice-case-study-4.png)

**Implantação mista com roteamento direto** 
 ![ Diagrama mostrando o estado anterior](media/voice-case-study-4a.png)


## <a name="calling-plans"></a>Planos de Chamadas

Para determinar os requisitos de configuração dos planos de chamadas, a contoso revisou as [decisões básicas de implantação do plano de chamadas](calling-plan-landing-page.md#core-deployment-decisions). As decisões resultantes foram feitas: 

- I. Meus usuários precisam fazer chamadas internacionais?<br> A. Sim 

- I. Cada um dos meus usuários tem um número de telefone do Direct Inward?<br> A. não está hoje. Todos os usuários habilitados receberão um. 

- I. Desejo mascarar ou desabilitar o recurso de identificação de chamadas?<br> R. a identificação de chamadas para um usuário será mascarada para o número local da contoso. 


## <a name="direct-routing"></a>Roteamento Direto

A contoso participou Ignite para ficar atualizado sobre os recursos do Office 365, incluindo aqueles disponíveis com o sistema telefônico e o roteamento direto. Liderança técnica e arquitetos usaram as diretrizes fornecidas durante a Ignite 2019 para determinar sua direção.  Principais sessões que foram usadas: 

- [Plano de sucesso com o Microsoft Teams Direct Routing](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)

- [Atualizações para roteamento direto](https://myignite.techcommunity.microsoft.com/sessions/80381?source=sessions)


## <a name="configuration"></a>Configuração

### <a name="calling-plans-sites"></a>Sites de planos de chamada

Para obter licenças e atribuir números de telefone aos usuários, a contoso seguiu as etapas em [configurar planos de chamada](set-up-calling-plans.md). 

Devido ao número de usuários que precisavam de números de telefone atribuídos, a Contoso decidiu usar o PowerShell para atribuir os números de telefone. Para saber como atribuir números usando o PowerShell, &mdash; além de outras configurações, &mdash; a contoso usou a [visão geral do teams PowerShell](teams-powershell-overview.md).  

### <a name="direct-routing-sites"></a>Sites de roteamento direto

Para conectar a infraestrutura de telefonia local da Contoso ao Microsoft Teams, o administrador da Contoso seguiu as etapas em [Configurar o roteamento direto](direct-routing-configure.md) e analisou o [Roteamento direto de vídeo no Microsoft Teams](https://www.youtube.com/watch?v=1ASftX_Msb8&index=10&list=PLaSOUojkSiGnKuE30ckcjnDVkMNqDv0Vl) para obter diretrizes.  A contoso também se referiu à documentação de implantação de roteamento direto pelo fornecedor SBC certificado. 

Após o roteamento direto ter sido configurado entre o SBC e o sistema telefônico da Microsoft, era necessário que a contoso teste a configuração. Para isso, os administradores da Contoso usaram o cliente testador SIP que foi discutido na [sessão atualizações para roteamento direto no Ignite 2019](https://myignite.techcommunity.microsoft.com/sessions/83178?source=sessions). O script de cliente de teste SIP e a documentação foram baixados do script do PowerShell para testar conexões de controlador de borda de sessão de roteamento direto.   


### <a name="local-media-optimization"></a>Otimização de mídia local

A contoso viu a oportunidade de aproveitar a otimização de mídia local nas diferentes regiões do mundo todo. Os cenários com suporte para contoso estão descritos em [otimização de mídia local para roteamento direto](direct-routing-media-optimization.md). A configuração da otimização de mídia local foi concluída seguindo diretrizes do fornecedor do SBC e da Microsoft. As etapas de configuração para a otimização de mídia local incluem: 

- Configurar os sites usuário e SBC 

- Configurar o SBC de acordo com a especificação do fornecedor do SBC, 

- Adicionar endereços IP externos confiáveis a cada site usado para otimização de mídia local    

- Definir a topologia de rede 

- Definir a topologia de rede virtual 

- Determine o modo: sempre ignorar ou somente para usuários locais 

## <a name="networking-considerations"></a>Considerações de rede

A Contoso tinha vários usuários que precisavam trabalhar remotamente por um período de tempo prolongado depois que foram habilitados para o sistema telefônico. Os usuários usavam a VPN para acessar certos aplicativos de linha de negócios. Durante a VPN, os usuários do sistema telefônico sofreram uma degradação da qualidade da chamada. 

Para resolver o problema de qualidade, a contoso implementou o tunelamento de VPN, que permitia que o tráfego do Office 365 atravessasse a Internet enquanto a conexão com os aplicativos internos permaneceram na VPN. Para implementar o tunelamento de VPN, a contoso seguiu a orientação em [implementando o tunelamento de divisão VPN para o Office 365](https://docs.microsoft.com/office365/enterprise/office-365-vpn-implement-split-tunnel).  

 





