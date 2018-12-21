---
title: Soluções de telefonia da Microsoft
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Descreve as soluções de telefonia da Microsoft.
ms.openlocfilehash: 161fb7bdaf3b961940f41e47b2e14f2dbb8da601
ms.sourcegitcommit: c9c743ebfb7bc1f207348e983aa6db26894d1fa9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/21/2018
ms.locfileid: "27384283"
---
# <a name="microsoft-telephony-solutions"></a>Soluções de telefonia da Microsoft

Microsoft suporta várias opções, conforme você começa a sua jornada para equipes em nuvem da Microsoft. Este artigo ajuda você a decidir qual solução de telefonia (sistema telefônico na nuvem ou o Enterprise Voice no local) é ideal para os usuários em sua organização e como sua organização pode conectar para a comutação telefônica PSTN (rede pública) a Microsoft. 

Você deve usar este artigo junto com o diagrama técnico associado, que fornece um auxílio visual para tomar a decisão à direita para a sua organização:

- [Soluções de telefonia da Microsoft - PDF](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.pdf)

- [Soluções de telefonia da Microsoft - Visio](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/telephony-solutions/microsoft-telephony-solutions-12-18.vsdx)




## <a name="private-branch-exchange-pbx-options"></a>Opções de Private Branch Exchange (PBX)

### <a name="phone-system-office-365"></a>Sistema telefônico (Office 365)
  
Sistema telefônico é uma tecnologia da Microsoft para habilitar o controle de chamada e os recursos de Private Branch Exchange (PBX) na nuvem com a Microsoft Teams e/ou Skype Office 365 para o Business Online. 

Sistema telefônico funciona com equipes ou Skype para clientes corporativos Online e dispositivos de certificados. Esse sistema permite que você substitua o sistema PBX existente por um conjunto de recursos fornecidos diretamente pelo Office 365, que está bem integrado com a experiência de produtividade de nuvem da empresa. Para conectar o sistema telefônico para a comutação telefônica PSTN (rede pública), você pode escolher chamar planejar da Microsoft ou seu próprio operadora de telefonia.

Para obter mais informações, consulte [o que é o sistema telefônico no Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365).

### <a name="enterprise-voice-skype-for-business-server"></a>Enterprise Voice (Skype para Business Server)

Enterprise Voice é a tecnologia da Microsoft para habilitar o controle de chamada e os recursos de Private Branch Exchange (PBX) no Skype local para o Business Server. Essa opção só pode ser conectada para a rede telefônica pública comutada usando seu próprio operadora de telefonia. 

Para obter mais informações, consulte [Plan for Enterprise Voice no Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

## <a name="connection-to-the-public-switched-telephone-network-pstn-options"></a>Conexão para as opções de rede de telefônica pública comutada (PSTN)

Você pode escolher conectar-se para a comutação telefônica PSTN (rede pública) por:

- Usando o plano de chamada da Microsoft no Office 365 
- Conectando seu próprio operadora de telefonia

### <a name="calling-plan-office-365"></a>Plano de chamada (Office 365)

Esta opção conecta o sistema de telefone da Microsoft Office 365 para o PSTN telefônica pública comutada rede () para habilitar chamadas para landlines e celulares em todo o mundo. Com chamar planejar, Microsoft é sua operadora da PSTN.

Para obter mais informações, consulte [Chamando planos do Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

### <a name="connect-your-own-telephony-carrier-office-365-and-skype-for-business-on-premises"></a>Conecte-se a sua própria operadora de telefonia (Office 365 e Skype para negócios local)

Essa opção se conecta a um sistema telefônico no Office 365 ou sistema de Enterprise Voice em Skype para negócios local à sua rede de telefonia. Essa opção exige um controlador de borda de sessão (SBC) com suporte. Em alguns casos, essa opção pode exigir softwares adicionais da Microsoft implantados no local.

## <a name="which-solution-is-right-for-your-organization"></a>Qual solução é adequada para sua organização?

Você pode escolher uma solução all nuvem, uma solução de conectar seu-proprietário-piloto ou uma mistura entre operadoras de terceiros e all nuvem:

- Sistema telefônico com chamar plano (todos na nuvem)

- Sistema telefônico com carro próprio via roteamento direto

- Sistema telefônico com carro próprio via Skype para Business Server ou nuvem conector Edition

- Enterprise Voice no Skype para servidor de negócios com o própria operadora

A solução que você escolher depende de suas necessidades atuais e futuras, tais como:

- Se você deseja —- ou são necessárias —-reter a funcionalidade fornecida pela sua implantação no local.
- Qual cliente que você deseja implantar para seus usuários.
- Seu plano de novidades sobre a transferência de pessoas para a nuvem.
- Se você precisa interoperar com 3º PBXs de terceiros e outros equipamentos de telefonia.

Considere as perguntas a seguir para determinar a melhor solução para sua organização:

- Você tem um Skype existente para implantação de servidor de negócios?
- Os usuários hospedados no Skype for Business no local, na nuvem em Skype para Business Online ou ambos? 
- Você deseja mover os usuários locais para a nuvem?
- Está PSTN chamar planejar da Microsoft disponível na sua região?
- Você deseja ou precisa manter sua operadora de telefonia atual?  Por exemplo, é preciso manter sua operadora atual por causa de um contrato existente?
- Você tem um PBX herdado local existente que você deseja ou precisa manter? 
- O seu PBX herdado atual oferece funcionalidades únicas que são cruciais para a sua empresa?
- Qualquer um ou todos os seus usuários exigem recursos oferecidos não está atualmente no sistema telefônico?

Observe o seguinte:

- Todas as quatro opções podem coexistir uns com os outros caso seja necessário projetar uma solução para o ambiente complexo ou gerenciando várias etapa migração.
- O sistema telefônico com carro próprio via Skype para Business Server ou nuvem conector Edition somente pode ser implantado com qualquer um dos Skype para Business Server ou nuvem Connector. Não há suporte para a coexistência do Skype para Business Server e o conector de nuvem em uma única empresa.

## <a name="phone-system-with-calling-plan"></a>Sistema telefônico com a chamada de plano


O sistema telefônico com chamar planejar é uma opção de all nuvem para equipes ou Skype para usuários corporativos Online, conforme mostrado no diagrama a seguir:

![Sistema telefônico com a chamada de plano](../../sfbserver2019/media/msft-telephony-solutions-1.png)


- Microsoft System de telefone com adicionado doméstico ou internacional chamar planos que permite a chamada para telefones em todo o mundo (dependendo do nível de serviço a serem licenciado). 
- Como planejar a chamada PSTN opera fora do Office 365, essa opção não requer implantação ou manutenção de qualquer implantação no local.
- Os clientes podem conectar um SBC suportado por meio de roteamento direto para a interoperabilidade com outros equipamentos de telefonia de terceiros 3º compatíveis com o SBC, dispositivos analógicos e 3º PBX de terceiros.

| Requisitos de infraestrutura                   | Necessário?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupto ao Office 365 | Sim |
| Disponível em todo o mundo *                            | Não  |
| Requer a implantação e manutenção de um controlador de borda de sessão (SBC) com suporte | Não |
| Requer o contrato com operadora de terceiros      | Não   |
| Requer a implantação e manutenção Skype para Business Server ou a edição de conector de nuvem | Não |

\*Para obter mais informações sobre os países onde chamar planejar está disponível, consulte [disponibilidade país e região para conferência de áudio e planos de chamada](https://docs.microsoft.com/en-us/MicrosoftTeams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans).


Se você responder Sim para as seguintes perguntas, isso é a solução certa para você:

- Chamar o plano ficará disponível na sua região.
- Você não precisará manter sua operadora da PSTN atual.
- Você deseja usar gerenciados pelo Microsoft access para a comutação telefônica PSTN (rede pública).
- Você não deseja gerenciar controladores de borda de sessão por conta própria.
- As equipes de e/ou Skype para Business Online tem todos os recursos que sua organização requer.

Para obter mais informações, consulte [What ' s sistema telefônico no Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) e [Chamar planos do Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/calling-plans-for-office-365).

## <a name="phone-system-with-own-carrier-via-direct-routing"></a>Sistema telefônico com carro próprio via roteamento direto

Essa opção oferece o sistema de telefone da Microsoft na nuvem com praticamente qualquer operadora de telefonia para usuários de equipes.

![Sistema telefônico com sua operadora via roteamento direto](../../sfbserver2019/media/msft-telephony-solutions-2.png)

- Conecte seu próprio SBC com suporte para o sistema de telefone da Microsoft diretamente, sem a necessidade de software adicional no local.  
- Use praticamente qualquer operadora de telefonia com o sistema de telefone da Microsoft.
- Podem ser configurados e gerenciados por clientes ou por sua operadora ou parceiro (solicitar se a sua operadora ou parceiro fornece essa opção).
- Configurar a interoperabilidade entre o equipamento de telefonia — como um PBX de terceiros e dispositivos analógicos — e o sistema de telefone da Microsoft.

| Requisitos de infraestrutura                   | Necessário?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupto ao Office 365 | Sim |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e manutenção de um controlador de borda de sessão (SBC) com suporte | Sim |
| Requer o contrato com terceiros operadora *      | Sim   |
| Requer a implantação e manutenção Skype para Business Server ou a edição de conector de nuvem | Não |

\*A menos que implantado como uma opção para fornecer conexão 3º PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão no sistema telefônico com planos de chamada.

Se você responder Sim para as seguintes perguntas, isso é a solução certa para você:

- Você deseja usar equipes com sistema telefônico.
- Você precisa manter sua operadora da PSTN atual.
- Você deseja misturar roteamento, algumas chamadas serão via chamar estiver planejando, alguns via sua operadora
- Você precisa interoperar com 3º PBXs de terceiros e/ou equipamento tais US sobrecarga pagers, dispositivos analógicos
- As equipes tem todos os recursos que sua organização requer.

Para obter mais informações, consulte [What ' s sistema telefônico no Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365) e [Planejar o roteamento direto](https://docs.microsoft.com/en-us/MicrosoftTeams/direct-routing-plan).


## <a name="phone-system-with-own-carrier-via-skype-for-business-server-or-cloud-connector-edition"></a>Sistema telefônico com carro próprio via Skype para Business Server ou nuvem conector Edition

Essa opção fornece o sistema de telefone da Microsoft na nuvem com conectividade para uma rede de telefonia no local para Skype para usuários corporativos Online.

![Sistema telefônico com sua operadora via Skype para Business Server ou nuvem conector Edition](../../sfbserver2019/media/msft-telephony-solutions-3.png)

 - Conecte seu próprio SBC com suporte para o sistema de telefone da Microsoft via Skype para Business Server ou Skype para o conector de nuvem Business Edition implantados no local. 
- Use praticamente qualquer operadora de telefonia com o sistema de telefone da Microsoft. 
- Se você já tiver Skype para Business Server local você pode aproveitá-lo;  Se você não fizer isso, você pode implantar uma versão mais leve – Edition do conector de nuvem.


| Requisitos de infraestrutura                   | Necessário?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupto ao Office 365 | Sim |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e manutenção de um controlador de borda de sessão (SBC) com suporte | Sim |
| Requer o contrato com operadora de terceiros      | Sim   |
| Requer a implantação e manutenção Skype para Business Server ou a edição de conector de nuvem | Sim |



Se você responder Sim para as seguintes perguntas, isso é a solução certa para você:

- Você deseja usar Skype para Business Online para seus usuários.
- Planejar a chamada PSTN não está disponível em sua região.
- Você precisa manter sua operadora da PSTN atual.

Para obter mais informações, consulte [o que é o sistema telefônico no Office 365](https://docs.microsoft.com/en-us/MicrosoftTeams/what-is-phone-system-in-office-365), [Skype para Business Server 2019](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-server-2019)e [Planejar Skype para o conector de nuvem Business Edition](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Recomendação: Ao business condições alterar – por exemplo, você não é mais necessário reter a sua operadora da PSTN –, considere mover para Teams da Microsoft usando as opções de 1 ou 2 para:
- Minimizar os custos de manutenção
- Acessem os recursos mais recentes lançada pela Microsoft

## <a name="enterprise-voice-in-skype-for-business-server-with-own-carrier"></a>Enterprise Voice no Skype para servidor de negócios com o própria operadora

Essa opção fornece o Enterprise Voice no local com conectividade para uma rede de telefonia no local para Skype para usuários do local de negócios.

![Enterprise Voice no Skype para servidor de negócios com o própria operadora](../../sfbserver2019/media/msft-telephony-solutions-4.png)

- Conecte seu próprio SBC com suporte ao sistema do Enterprise Voice no Skype para o servidor local de negócios.
- Use se precisar sustentabilidade local.
- Use praticamente qualquer operadora de telefonia com o sistema de telefone da Microsoft. 
- Opção mais complexa para implantar e manter.

| Requisitos de infraestrutura                   | Necessário?|
| :----------------------------------------------------| ---------:|
| Requer conexão ininterrupto ao Office 365 | Não |
| Disponível em todo o mundo                            | Sim  |
| Requer a implantação e manutenção de um controlador de borda de sessão (SBC) com suporte | Sim |
| Requer o contrato com operadora de terceiros      | Sim   |
| Requer a implantação e manutenção Skype para Business Server | Sim |

Para obter mais informações, consulte [Plan for Enterprise Voice no Skype para Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/enterprise-voice-solution/enterprise-voice?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json).

Recomendação: Ao business condições alterar – por exemplo, você não é mais necessário reter a sua operadora da PSTN –, considere mover para Teams da Microsoft usando as opções de 1 ou 2 para:
- Minimizar os custos de manutenção
- Acessem os recursos mais recentes lançada pela Microsoft











  
