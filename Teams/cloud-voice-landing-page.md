---
title: Voz no Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/29/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
- m365initiative-voice
- m365solution-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Saiba mais sobre os recursos de voz do Microsoft Teams Cloud e as decisões de implantação que você fará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 464f3591d86879db5830ca0abbea1bfbff538cec
ms.sourcegitcommit: 4dd8a326a7284872f0d14e0a61bd4fcbe2297c10
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071762"
---
# <a name="plan-your-teams-voice-solution"></a>Planejar a solução de voz do teams 

Este artigo ajuda você a decidir qual solução Microsoft Voice é ideal para sua organização. Depois de decidir, o artigo fornece um roteiro para o conteúdo que permitirá implementar a solução escolhida. 

Você pode querer o sistema de telefonia da solução mais simples &mdash; com plano de chamadas. Esta é a solução completa da Microsoft que fornece funcionalidade de PBX (Private Branch Exchange) e chamadas para a rede telefônica pública comutada (PSTN), conforme mostrado no diagrama a seguir. Com esta solução, a Microsoft é a sua operadora PSTN.

![O diagrama 1 mostra o sistema telefônico com plano de chamada](media/msft-voice-solutions-1.png)

Se você responder sim para o seguinte, o sistema telefônico com plano de chamadas será a solução certa para você:

- O plano de chamadas está disponível na sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à PSTN.

No entanto, sua situação pode ser mais complexa. Por exemplo, você pode ter escritórios em locais nos quais o plano de chamadas não está disponível. Ou talvez você precise de uma solução de combinação compatível com uma implantação complexa e multinacionais, com requisitos diferentes para locais geográficos diferentes. A Microsoft oferece suporte a uma combinação de soluções: 

- Sistema telefônico com plano de chamada
- Sistema telefônico com o seu próprio transportador PSTN com roteamento direto
- Uma solução de combinação que usa o sistema telefônico com plano de chamada e sistema telefônico com roteamento direto

## <a name="what-do-you-need-to-read"></a>O que você precisa ler?

**Obrigatório para todos.** Algumas das seções deste artigo pertencem a todas as organizações. Por exemplo, todos devem ler sobre o sistema telefônico e compreender as opções para se conectar à rede telefônica pública comutada (PSTN). 


| Necessário para todos os | Descrição |
| :------------|:-------|
| [**Sistema de Telefonia**](#phone-system) | A tecnologia da Microsoft para habilitar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Microsoft 365 com o Microsoft Teams. |
| [**Opções de conectividade PSTN (rede telefônica pública comutada)**](#public-switched-telephone-network-connectivity-options) | Uma escolha entre usar a Microsoft como sua operadora de telefonia ou conectar sua própria operadora de telefonia ao Microsoft Teams usando o roteamento direto. Combinado com o sistema telefônico, as opções de conectividade PSTN permitem que os usuários façam chamadas para telefones no mundo todo.|

**Dependendo dos seus requisitos.** Algumas das seções neste artigo são pertinentes dependendo da implantação e dos requisitos existentes. Por exemplo, Location-Based roteamento só é necessário para os clientes de roteamento direto em locais geográficos que não permitem o bypass de chamada tarifada.


| Dependendo dos seus requisitos | Descrição |
| :------------|:-------|
| [**Números de telefone da Microsoft**](#phone-numbers-from-microsoft) | Como obter e gerenciar números de telefone da Microsoft e como transferir números existentes para a Microsoft. Leia isto se precisar obter números de telefone para o plano de chamadas da Microsoft, transferir números existentes, obter números de serviço e assim por diante. |
| [**Planos de discagem e encaminhamento de chamadas**](#dial-plans-and-call-routing) | Como configurar e gerenciar planos de discagem que convertem números de telefone discados em um formato alternativo (geralmente formato E. 164) para autorização de chamadas e encaminhamento de chamadas. Leia esta opção se você precisar entender quais são os planos de discagem e se precisará especificar planos de discagem para a sua organização.|
| [**Chamadas de emergência**](#emergency-calling) | Como gerenciar e configurar as chamadas de emergência &mdash; dependendo da opção de conectividade PSTN. Leia esta seção se estiver usando o plano de chamadas da Microsoft ou o roteamento direto e precisar compreender como gerenciar as chamadas de emergência para sua organização. |
| [**Roteamento baseado em local para roteamento direto**](#location-based-routing-for-direct-routing) |Como usar o roteamento de Location-Based (LBR) para restringir o bypass para usuários do Microsoft Teams com base em sua localização geográfica. Leia esta seção se a sua organização estiver usando o roteamento direto em um local que não permita o bypass de chamada tarifada.
| [**Topologia de rede para recursos de voz na nuvem**](#network-topology-for-voice-features) | Se a sua organização estiver implantando o roteamento de Location-Based (LBR) para roteamento direto ou chamadas de emergência dinâmicas, você deve definir as configurações de rede para usar com esses recursos no Microsoft Teams. Leia esta seção se você estiver implementando LBR para roteamento direto ou se estiver implementando chamadas de emergência dinâmicas com plano de chamada ou roteamento direto. |
| [**Migrar sua solução de voz existente**](#migrate-your-existing-voice-solution-to-teams) | O que você precisa pensar ao migrar sua solução de voz para o Microsoft Teams.  Leia esta seção se você estiver migrando de uma solução de voz existente para o Microsoft Teams. 



> [!Important]
> Este artigo se concentra em soluções de voz com o Microsoft Teams. Embora as soluções com o Skype for Business online ainda estejam disponíveis (conforme descrito nas [soluções de telefonia da Microsoft](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)), é importante entender que o Skype for Business online será desativado em 31 de julho de 2021.  Após essa data, o serviço Skype for Business online não será mais acessível. Além disso, a conectividade PSTN entre seu ambiente local, &mdash; seja por meio do Skype for Business Server ou do Cloud Connector Edition &mdash; e do Skype for Business Online, não será mais compatível. Este artigo apresenta as soluções de voz do Teams e como você pode conectar sua rede de telefonia local, se necessário, ao Teams usando o roteamento direto.


## <a name="phone-system"></a>Sistema Telefônico

O sistema de telefonia é a tecnologia da Microsoft para habilitar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Microsoft 365 ou do Office 365 com o Microsoft Teams.

O sistema de telefonia funciona com o Microsoft Teams ou clientes do Skype for Business e dispositivos certificados. O sistema telefônico permite substituir seu sistema PBX existente por um conjunto de recursos entregues diretamente do Microsoft 365 ou do Office 365. 

As chamadas entre os usuários da sua organização são manipuladas internamente no sistema telefônico e nunca vão para a PSTN (rede telefônica pública comutada). Isso se aplica a chamadas entre usuários de sua organização localizados em diferentes áreas geográficas, eliminando os custos de longa distância dessas chamadas internas.

Este artigo apresenta os seguintes recursos e funcionalidades importantes do sistema telefônico e as decisões de implantação que você precisará considerar:

- [Atendedores automáticos e filas de chamadas](#auto-attendants-and-call-queues)
- [Caixa Postal da Nuvem](#cloud-voicemail)
- [Identidade de chamada](#calling-identity)

Para saber mais sobre todos os recursos do sistema telefônico e como configurar o sistema telefônico, confira os seguintes artigos:

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)
- [Configurar o sistema telefônico em sua organização](setting-up-your-phone-system.md)<br>
  Descreve como comprar e atribuir licenças do sistema telefônico, gerenciar números de telefone e configurar créditos de comunicação para números de chamada gratuita. 

Para obter informações sobre o gerenciamento de dispositivos compatíveis, consulte [gerenciar seus dispositivos no Microsoft Teams e no](devices/device-management.md) [Teams Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Atendedores automáticos e filas de chamadas

Os atendedores automáticos permitem que você configure opções de menu para direcionar chamadas com base na entrada do chamador. As filas de chamadas estão aguardando áreas para chamadores. Usados juntos, atendedores automáticos e filas de chamadas podem facilmente direcionar os chamadores para a pessoa ou departamento apropriado de sua organização.

Para obter informações sobre atendedores automáticos e filas de chamadas, consulte os seguintes artigos:

- [Planejar os atendedores automáticos e as filas de chamadas do teams](plan-auto-attendant-call-queue.md)
- [Configurar um atendedor automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md) 
- [Estudo de caso da Contoso: atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md)<br>
  Descreve como uma corporação multinacionais fictícia, contoso, implementou atendedores automáticos e filas de chamadas para sua solução de voz.

### <a name="cloud-voicemail"></a>Caixa Postal na Nuvem

Correio de voz na nuvem, da plataforma de serviços de correio de voz do Azure, oferece suporte a depósitos de correio de voz para o Exchange Ele não é compatível com sistemas de email de terceiros. 

O correio de voz na nuvem inclui a transcrição de correio de voz, que é habilitada para todos os usuários da sua organização por padrão. Suas necessidades comerciais podem exigir que você desabilite a transcrição de correio de voz para usuários específicos ou todos em toda a organização.

Para usuários online, o correio de voz em nuvem é automaticamente configurado e provisionado para os usuários após a atribuição de uma licença do sistema telefônico. Para usuários de sistema telefônico com uma caixa de correio do Exchange, você precisará executar etapas de configuração adicionais. 

Para obter mais informações sobre o correio de voz em nuvem e sua configuração, consulte os seguintes artigos:

- [Configurar a caixa postal na nuvem](set-up-phone-system-voicemail.md)
- [Definir políticas de correio de voz em sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (identificação de chamadas). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Para obter informações sobre como configurar o recurso de identificação de chamadas ou para alterar ou bloquear o recurso de identificação de chamadas, consulte [definir a identificação de chamadas para um usuário](set-the-caller-id-for-a-user.md). 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opções de conectividade de rede telefônica comutada pública

O sistema telefônico oferece recursos de PBX completos para sua organização. No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa conectar o sistema telefônico à rede telefônica pública comutada (PSTN). Para conectar o sistema telefônico à PSTN, você pode escolher uma das seguintes opções:

- [**Sistema telefônico com plano de chamadas**](#phone-system-with-calling-plan). Uma solução completa na nuvem com a Microsoft como sua operadora PSTN.

- [**Sistema telefônico com sua própria transportabilidade PSTN usando o**](#phone-system-with-own-pstn-carrier-with-direct-routing) roteamento direto para conectar seu ambiente local ao Teams.

Você também pode escolher uma combinação de opções, que permite que você projete uma solução para um ambiente complexo ou gerencie uma migração em várias etapas (mais informações sobre a migração mais tarde).

### <a name="phone-system-with-calling-plan"></a>Sistema telefônico com plano de chamada 

Conforme descrito anteriormente neste artigo, sistema telefônico com plano de chamadas é a solução completa de voz da Microsoft para usuários do teams. Esta é a opção mais simples que conecta o sistema telefônico da Microsoft à rede telefônica pública comutada (PSTN) para permitir chamadas para telefones fixos e celulares em todo o mundo. Com essa opção, a Microsoft oferece funcionalidade de PBX (Private Branch Exchange) para sua organização e age como sua operadora PSTN, conforme mostrado no diagrama a seguir:

![O diagrama 1 mostra o sistema telefônico com plano de chamada](media/msft-voice-solutions-1a.png)

Se você responder sim para o seguinte, o sistema telefônico com plano de chamadas será a solução certa para você:

- O plano de chamadas está disponível na sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à PSTN.

Com essa opção: 

- Você tem um sistema telefônico da Microsoft com planos de chamadas domésticas ou internacionais que permitem fazer chamadas para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).

- Você não precisa de implantação nem manutenção de uma implantação local porque o &mdash; plano de chamadas funciona do Microsoft 365 ou do Office 365.

- Observação: se necessário, você pode optar por conectar um SBC (controlador de borda de sessão) compatível por meio do direcionamento direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros suportados pelo SBC.

Esta opção requer conexão ininterrupta com o Microsoft 365 ou o Office 365.

Para obter mais informações sobre o plano de chamada, consulte os seguintes artigos:

- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Como comprar um plano de chamadas](calling-plans-for-office-365.md)
- [Disponibilidade de país e região do Plano de chamadas](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurar plano de chamadas](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefônico com a própria portabilidade PSTN com roteamento direto

Esta opção conecta o sistema telefônico da Microsoft à sua rede de telefonia usando o roteamento direto, conforme mostrado no diagrama a seguir: 

![O diagrama 2 mostra o sistema telefônico com roteamento direto](media/msft-voice-solutions-2.png)

Se você responder sim para as seguintes perguntas, o sistema telefônico com roteamento direto é a solução certa para você:

- Você deseja usar o Microsoft Teams com o sistema telefônico.
- Você precisa manter sua operadora PSTN atual.
- Você deseja misturar o roteamento, com algumas chamadas passando pelo plano de chamadas, alguns pela sua operadora.
- Você precisa interoperar com PBXs de terceiros e/ou equipamentos, tais páginas de páginas indiretos, dispositivos analógicos e assim por diante.

Com essa opção:

- Você conecta seu próprio SBC compatível a um sistema telefônico da Microsoft sem a necessidade de software adicional local.

- Você pode usar praticamente qualquer operadora de telefonia com o sistema telefônico da Microsoft.

- Você pode optar por configurar e gerenciar essa opção ou pode ser configurada e gerenciada pela sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).

- Você pode configurar a interoperabilidade entre seu equipamento de telefonia &mdash; , como um PBX de terceiros e dispositivos analógicos &mdash; e o sistema de telefonia da Microsoft.


Essa opção requer o seguinte:

- Conexão ininterrupta com o Microsoft 365 ou o Office 365.

- Implantação e manutenção de um SBC compatível.

- Um contrato com uma operadora terceirizada.
  (A menos que seja implantada como uma opção para fornecer conexão a um PBX de terceiros, dispositivos analógicos ou outro equipamento de telefonia para usuários que estão no sistema telefônico com o plano de chamadas.)

Para obter mais informações sobre o roteamento direto, consulte os seguintes artigos:

- [Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)
- [Planejar o Roteamento Direto](direct-routing-plan.md)
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Gerenciar políticas de roteamento de voz para uso com roteamento direto](manage-voice-routing-policies.md)
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)


## <a name="phone-numbers-from-microsoft"></a>Números de telefone da Microsoft

A Microsoft tem dois tipos de números de telefone disponíveis: números de *assinante* (usuário), que podem ser atribuídos a usuários em sua organização e números de *serviço* , disponíveis como números de serviço de chamada tarifada e gratuita. Os números de serviço têm uma capacidade de chamada simultânea maior do que os números de assinantes e podem ser atribuídos a serviços como videoconferências, atendedores automáticos ou filas de chamadas.

Será preciso decidir:

- Quais locais de usuário precisam de novos números de telefone da Microsoft?
- Que tipo de número de telefone (assinante ou serviço) eu preciso? 
- Como faço para portar números de telefone existentes para o Microsoft Teams?

Para obter mais informações sobre o gerenciamento de números de telefone em sua organização, incluindo a obtenção de novos números ou a transferência de números de saída, consulte os seguintes artigos:

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diferentes tipos de números de telefone usados para o plano de chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md)
- [Transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planos de discagem e encaminhamento de chamadas

Um plano de discagem é um conjunto de regras de normalização que traduz os números de telefone discados em um formato alternativo (geralmente formato E. 164) para autorização de chamadas e encaminhamento de chamadas.

Será preciso decidir o seguinte: 

- Minha organização precisa de um plano de discagem personalizado?
- Quais usuários exigem um plano de discagem personalizado?
- Qual plano de discagem de locatário deve ser atribuído a cada usuário?

Para obter mais informações, consulte os seguintes artigos: 

- [O que são planos de discagem?](what-are-dial-plans.md)
- [Plano para planos de discagem de locatário](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Chamada de emergência

A maneira como você configura a chamada de emergência é diferente, dependendo da opção de conectividade PSTN: plano de chamada da Microsoft ou roteamento direto. Chamadas de emergência dinâmicas para o plano de chamadas e o roteamento direto do sistema telefônico fornecem a funcionalidade de configurar e direcionar chamadas de emergência e notificar o pessoal de segurança com base na localização atual do cliente do teams. Para obter mais informações sobre conceitos e terminologia de chamadas de emergência e como configurar chamadas de emergência dinâmicas, consulte os seguintes artigos:

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
- [Estudo de caso da Contoso: chamadas de emergência](voice-case-study-emergency-calling.md)<br>
  Descreve como uma corporação multinacionais fictícia, contoso, implementou chamadas de emergência para sua organização.

## <a name="location-based-routing-for-direct-routing"></a>Roteamento Location-Based para roteamento direto

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (rede telefônica pública comutada) para reduzir os custos de chamadas de longa distância. Location-Based roteamento para roteamento direto permite que você restrinja o bypass de chamadas para usuários do Microsoft Teams com base em sua localização geográfica. Para obter mais informações sobre como planejar e configurar o roteamento de Location-Based (LBR), consulte os seguintes artigos:

- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Estudo de caso da Contoso: Location-Based roteamento](voice-case-study-location-based-routing.md)<br>
  Descreve como uma corporação multinacionais fictícia, contoso, implementou o roteamento Location-Based para a sua organização.

## <a name="network-topology-for-voice-features"></a>Topologia de rede para recursos de voz

Se você estiver implantando chamadas de emergência dinâmicas ou roteamento Location-Based para roteamento direto, deve definir as configurações de rede para usar com esses recursos no Microsoft Teams. Para saber como definir as configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:

- [Configurações de rede para recursos de voz na nuvem no Microsoft Teams – conceitos e terminologia](cloud-voice-network-settings.md)
- [Gerenciar a topologia de rede para recursos de voz na nuvem no Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrar sua solução de voz existente para o Microsoft Teams

Para uma organização que está atualizando para o Microsoft Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly. Só há suporte para o uso do sistema telefônico com Teams quando o usuário está no modo TeamsOnly. Se precisar de informações básicas sobre a atualização para o Microsoft Teams, comece aqui:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Sobre a estrutura de atualização](upgrade-framework.md)
- [Atualize o Skype for Business para o Teams, para administradores de ti](upgrade-to-teams-on-prem-overview.md)

Ao migrar sua solução de voz, há quatro cenários de chamadas possíveis ao se mover para o modo TeamsOnly:

- [**Um usuário no Skype for Business Online, com um plano de chamadas da Microsoft**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans). Após a atualização, este usuário continuará a ter um plano de chamadas da Microsoft.

- **[Um usuário no Skype for Business Online, com funcionalidade de voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice) por meio do Skype for Business local ou da edição do Cloud Connector**. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o roteamento direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.

- **[Um usuário do Skype for Business no local com o Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), que será movido para online e mantendo a conectividade PSTN local**. Migrar este usuário para o Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com a migração do usuário para o roteamento direto. 

- **[Um usuário do Skype for Business no local com o Enterprise Voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), que se moverá para online e usando um plano de chamadas da Microsoft**.  Migrar este usuário para o Microsoft Teams requer mover a conta do Skype for Business no local para a nuvem e coordenar essa movimentação com uma a porta do número de telefone do usuário para um plano de chamadas da Microsoft ou B) atribuir um novo número de assinante de regiões disponíveis.

Para obter mais informações sobre como implementar sua migração de voz para cada um desses cenários &mdash; , incluindo informações sobre quando você precisa configurar a conectividade híbrida e como migrar usuários com funcionalidade de voz local para o roteamento direto, &mdash; consulte os seguintes artigos:

- [Considerações de PSTN durante a atualização para o Microsoft Teams – para administradores de ti](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Estudo de caso de migração de voz da contoso](voice-case-study-overview.md)<br>
  O estudo de caso descreve como uma corporação multinacionais fictícia, contoso, implementou uma solução de voz do teams para sua organização. Ele contém os seguintes artigos:

  - [Plano de atualização do teams](voice-case-study-migration-plan.md)
  - [Opções de conectividade PSTN e do sistema telefônico](voice-case-study-phone-system.md)
  - [Implementação de roteamento baseado em local](voice-case-study-location-based-routing.md)
  - [Chamadas de emergência](voice-case-study-emergency-calling.md)
  - [Atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md)
  - [Audioconferência](voice-case-study-audio-conferencing.md)












