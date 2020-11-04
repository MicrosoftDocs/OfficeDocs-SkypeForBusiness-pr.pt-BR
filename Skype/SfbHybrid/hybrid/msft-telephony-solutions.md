---
title: Soluções de telefonia da Microsoft
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 'Saiba mais sobre as soluções de telefonia da Microsoft: sistema de telefonia (Private Branch Exchange-PBX) e opções de conectividade PSTN (planos de chamadas e roteamento direto).'
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: 3f5e4f0cf0cb027ed0c18b98c85b123634687a77
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878535"
---
# <a name="microsoft-telephony-solutions"></a>Soluções de telefonia da Microsoft

A Microsoft dá suporte a várias opções à medida que você começa sua jornada para o Teams na nuvem da Microsoft. Este artigo ajuda você a decidir qual solução de telefonia da Microsoft (sistema telefônico na nuvem ou o Enterprise Voice no local) é a mais adequada para os usuários em sua organização e como sua organização pode se conectar à PSTN (rede telefônica pública comutada).

Você deve usar este artigo junto com o diagrama técnico associado, que fornece um auxílio visual para tomar a decisão certa para sua organização:

- [Soluções de telefonia da Microsoft-PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluções de telefonia da Microsoft-Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opções de PBX (central privada de comutação)

### <a name="phone-system-microsoft-365-or-office-365"></a>Sistema de telefonia (Microsoft 365 ou Office 365)
  
O sistema de telefonia é a tecnologia da Microsoft para habilitar o controle de chamadas e os recursos de PBX (central privada de comutação telefônica) na nuvem do Microsoft 365 ou do Office 365 com o Microsoft Teams e/ou o Skype for Business online.

O sistema de telefonia funciona com o Microsoft Teams ou clientes do Skype for Business Online e dispositivos certificados. O sistema de telefonia permite substituir seu sistema PBX existente por um conjunto de recursos fornecidos diretamente pelo Microsoft 365 ou Office 365 e totalmente integrado à experiência de produtividade de nuvem da empresa. Para conectar o sistema de telefonia à rede telefônica pública comutada (PSTN), você pode escolher o plano de chamadas da Microsoft ou sua própria operadora de telefonia.

Para obter mais informações, consulte [o que é o sistema de telefonia no Microsoft 365 ou no Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Enterprise Voice (Skype for Business Server)

O Enterprise Voice é a tecnologia da Microsoft para habilitar o controle de chamadas e os recursos de PBX (central privada de comutação) no Skype for Business Server local. Essa opção do Skype for Business só pode ser conectada à rede telefônica pública comutada usando sua própria operadora de telefonia.

Para obter mais informações, consulte [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Conexão com as opções PSTN (rede telefônica pública comutada)

Você pode optar por se conectar à rede telefônica pública comutada (PSTN) por:

- Usando o plano de chamadas da Microsoft no Microsoft 365 ou no Office 365 
- Conectando sua própria operadora de telefonia

### <a name="calling-plan-microsoft-365-or-office-365"></a>Plano de chamadas (Microsoft 365 ou Office 365)

Essa opção conecta o sistema de telefonia do Microsoft 365 ou do Office 365 à rede telefônica pública comutada (PSTN) para habilitar chamadas para telefones fixos e celulares em todo o mundo. Com o plano de chamadas, a Microsoft é a operadora PSTN.

Confira mais informações em [planos de chamadas para o Microsoft 365 ou o Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-microsoft-365-or-office-365-and-skype-for-business-on-premises"></a>Conectar sua própria portadora de telefonia (Microsoft 365 ou Office 365 e Skype for Business no local)

Essa opção conecta o sistema de telefonia no Microsoft 365 ou no Office 365 ou no sistema Enterprise Voice no Skype for Business no local para sua rede de telefonia. Essa opção requer um SBC (controlador de borda de sessão) suportado. Em alguns casos, essa opção pode exigir software adicional da Microsoft implantado no local.

## <a name="which-solution-is-right-for-your-organization"></a>Qual é a solução certa para a sua organização?

Você pode escolher uma solução all-in-Cloud, uma solução connect-your-companhia própria ou uma combinação entre as operadoras de terceiros e as transportadoras de terceiros:

- Sistema de telefonia com plano de chamadas (todos na nuvem)

- Sistema de telefonia com portadora própria via roteamento direto

- Sistema de telefonia com sua própria operadora via Skype for Business Server ou Cloud Connector Edition

- Enterprise Voice no Skype for Business Server com portadora própria

A solução que você escolher depende das suas necessidades atuais e futuras, como:

- Se você deseja que o ou o sejam obrigatórios para manter a funcionalidade fornecida por sua implantação local.
- Qual cliente você deseja implantar para os seus usuários.
- Qual é o seu plano para mover pessoas para a nuvem.
- Se você precisa interoperar com PBXs de terceiros e outros equipamentos de telefonia.

Considere as seguintes questões para determinar a melhor solução para sua organização:

- Você tem uma implantação existente do Skype for Business Server?
- Os usuários são hospedados no Skype for Business no local, na nuvem no Skype for Business online ou em ambos? 
- Você deseja mover os usuários locais para a nuvem?
- O plano de chamadas PSTN da Microsoft está disponível em sua região?
- Você deseja ou precisa manter sua operadora de telefonia atual?  Por exemplo, você precisa manter sua operadora atual por causa de um contrato existente?
- Você tem um PBX herdado local existente que você deseja ou precisa manter?
- O seu PBX herdado atual oferece recursos exclusivos fundamentais para a sua empresa?
- Qualquer um ou todos os seus usuários exigem recursos não oferecidos atualmente no sistema de telefonia?

Observe o seguinte:

- Todas as quatro opções podem coexistir umas com as outras, caso você precise criar uma solução para um ambiente complexo ou gerenciar a migração de várias etapas.
- O sistema de telefonia com a própria operadora via Skype for Business Server ou Cloud Connector Edition só pode ser implantado com o Skype for Business Server ou o Cloud Connector. A coexistência do Skype for Business Server e do Cloud Connector não é suportada em uma única empresa.

## <a name="phone-system-with-calling-plan"></a>Sistema de telefonia com plano de chamadas


O sistema de telefonia com plano de chamadas é uma opção tudo na nuvem para usuários do teams ou Skype for Business Online, conforme mostrado no diagrama a seguir:

![Sistema de telefonia com plano de chamadas](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Sistema de telefonia da Microsoft com planos de chamadas domésticas ou internacionais adicionados que permitem a chamada para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado). 
- Como o plano de chamada PSTN Opera de fora do Microsoft 365 ou do Office 365, essa opção não requer implantação ou manutenção de nenhuma implantação local.
- Os clientes podem conectar um SBC com suporte via roteamento direto para interoperabilidade com PBX de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros suportados pelo SBC.

| Requisitos de infraestrutura                   | Obrigatório?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupta com o Microsoft 365 ou o Office 365 | Sim |
| Disponível em todo o mundo *                            | Não  |
| Requer a implantação e a manutenção de um SBC (controlador de borda de sessão) suportado | Não |
| Requer contrato com portadora de terceiros      | Não   |
| Requer a implantação e a manutenção do Skype for Business Server ou do Cloud Connector Edition | Não |

\* Para obter mais informações sobre os países onde o plano de chamadas está disponível, confira [disponibilidade de áudio e planos de chamadas por país e região](https://docs.microsoft.com/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Se você responder sim às perguntas a seguir, esta é a solução certa para você:

- O plano de chamadas está disponível na sua região.
- Não é necessário manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à rede telefônica pública comutada (PSTN).
- Você não deseja gerenciar controladores de borda de sessão por conta própria.
- O Microsoft Teams e/ou o Skype for Business online tem todos os recursos exigidos pela sua organização.

Para obter mais informações, consulte [o que é o sistema de telefonia no microsoft 365 e o office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) e [planos de chamadas para o Microsoft 365 ou o Office 365](https://docs.microsoft.com/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema de telefonia com portadora própria via roteamento direto

Essa opção fornece um sistema de telefonia da Microsoft na nuvem com praticamente qualquer portadora de telefonia para usuários do teams.

![Sistema de telefonia com sua operadora via roteamento direto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Conecte seu próprio SBC com suporte ao sistema de telefonia da Microsoft diretamente sem precisar de software adicional local.  
- Use praticamente qualquer portadora de telefonia com o sistema de telefonia da Microsoft.
- Podem ser configurados e gerenciados por clientes ou pela operadora ou pelo parceiro (pergunte se sua operadora ou seu parceiro fornece essa opção).
- Configure a interoperabilidade entre seu equipamento de telefonia, como um PBX de terceiros e dispositivos analógicos, e o sistema de telefonia da Microsoft.

| Requisitos de infraestrutura                   | Obrigatório?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupta com o Microsoft 365 ou o Office 365 | Sim |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e a manutenção de um SBC (controlador de borda de sessão) suportado | Sim |
| Requer contrato com uma operadora de terceiros *      | Sim   |
| Requer a implantação e a manutenção do Skype for Business Server ou do Cloud Connector Edition | Não |

\* A menos que seja implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão no sistema de telefonia com planos de chamadas.

Se você responder sim às perguntas a seguir, esta é a solução certa para você:

- Você deseja usar o Microsoft Teams com o sistema de telefonia.
- Você precisa manter sua operadora PSTN atual.
- Você deseja misturar o roteamento, algumas chamadas estão passando por planos de chamadas, algumas por meio de sua operadora
- Você precisa interoperar com PBXs de terceiros e/ou equipamentos que contenham pagers de sobrecarga, dispositivos analógicos
- O Microsoft Teams tem todos os recursos exigidos pela sua organização.

Para obter mais informações, consulte [o que é o sistema de telefonia no Microsoft 365 e o Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365) e [planejar o roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema de telefonia com sua própria operadora via Skype for Business Server ou Cloud Connector Edition

> [!Important]
> O Skype for Business online será desativado no dia 31 de julho de 2021 depois do qual o serviço não estará mais acessível.  Além disso, a conectividade PSTN entre seu ambiente local por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business online não terá mais suporte.  Saiba como conectar sua rede de telefonia local ao Microsoft Teams usando o [Roteamento direto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).

Essa opção fornece um sistema de telefonia da Microsoft na nuvem com conectividade a uma rede de telefonia local para usuários do Skype for Business online.

![Sistema de telefonia com sua operadora por meio do Skype for Business Server ou do Cloud Connector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Conecte seu próprio SBC com suporte ao sistema de telefonia da Microsoft por meio do Skype for Business Server ou do Skype for Business Cloud Connector Edition implantado no local. 
- Use praticamente qualquer portadora de telefonia com o sistema de telefonia da Microsoft. 
- Se você já tiver o Skype for Business Server local, poderá aproveitá-lo;  Se não fizer isso, você pode implantar uma versão mais clara – Cloud Connector Edition.


| Requisitos de infraestrutura                   | Obrigatório?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupta com o Microsoft 365 ou o Office 365 | Sim |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e a manutenção de um SBC (controlador de borda de sessão) suportado | Sim |
| Requer contrato com portadora de terceiros      | Sim   |
| Requer a implantação e a manutenção do Skype for Business Server ou do Cloud Connector Edition | Sim |



Se você responder sim às perguntas a seguir, esta é a solução certa para você:

- Você deseja usar o Skype for Business online para seus usuários.
- O plano de chamada PSTN não está disponível em sua região.
- Você precisa manter sua operadora PSTN atual.

Para obter mais informações, consulte [o que é o sistema de telefonia no Microsoft 365 e Office 365](https://docs.microsoft.com/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype for Business Server 2019](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-server-2019)e [Plan for Skype for Business Cloud Connector Edition](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Recomendação: quando as condições de negócios mudam, por exemplo, não é mais necessário manter sua operadora PSTN, considere mudar para o Microsoft Teams usando as opções 1 ou 2 para:
- Reduzir os custos de manutenção
- Ter acesso aos recursos mais recentes lançados pela Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Enterprise Voice no Skype for Business Server com portadora própria

Essa opção fornece o Enterprise Voice no local com conectividade a uma rede de telefonia local para usuários locais do Skype for Business.

![Enterprise Voice no Skype for Business Server com portadora própria](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Conecte seu próprio SBC com suporte ao sistema do Enterprise Voice no servidor local do Skype for Business.
- Use se precisar de sustentabilidade local.
- Use praticamente qualquer portadora de telefonia com o sistema de telefonia da Microsoft. 
- Opção mais complexa para implantar e manter.

| Requisitos de infraestrutura                   | Obrigatório?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupta com o Microsoft 365 ou o Office 365 | Não |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e a manutenção de um SBC (controlador de borda de sessão) suportado | Sim |
| Requer contrato com portadora de terceiros      | Sim   |
| Requer a implantação e manutenção do Skype for Business Server | Sim |

Para obter mais informações, consulte [Plan for Enterprise Voice in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Recomendação: quando as condições de negócios mudam, por exemplo, não é mais necessário manter sua operadora PSTN, considere mudar para o Microsoft Teams usando as opções 1 ou 2 para:
- Reduzir os custos de manutenção
- Ter acesso aos recursos mais recentes lançados pela Microsoft
