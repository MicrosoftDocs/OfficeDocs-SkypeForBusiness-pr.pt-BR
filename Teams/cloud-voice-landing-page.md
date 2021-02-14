---
title: Planejar sua solução de voz no Microsoft Teams
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
- m365solution-scenario
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Saiba mais sobre os recursos de voz na nuvem do Microsoft Teams e as decisões de implantação que você tomará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16a2aea0d367c720cf36c8010670a34472ab43a
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701329"
---
# <a name="plan-your-teams-voice-solution"></a>Planejar sua solução de voz do Teams 

Este artigo ajuda você a decidir qual solução de voz da Microsoft é ideal para sua organização. Depois de decidir, o artigo fornece um roteiro para o conteúdo que permitirá que você implemente a solução escolhida.

> [!NOTE]
> Para obter orientações sobre como planejar uma solução de voz do Teams como parte de seu plano geral para atualizar para o Teams do Skype for Business Server, consulte as considerações [PSTN](upgrade-to-Teams-on-prem-pstn-considerations.md)para atualizar para o Teams do Skype for Business local.

Talvez você queira a solução mais simples do Sistema &mdash; telefônico com Plano de Chamada. Esta é a solução de toda a nuvem da Microsoft que fornece funcionalidade de PbX (Private Branch Exchange) e chamadas para a PSTN (Rede Telefônica Pública Comutado), conforme mostrado no diagrama a seguir. Com essa solução, a Microsoft é sua operadora PSTN.

![O Diagrama 1 mostra o Sistema de Telefonia com Plano de Chamada](media/voice-solutions-simple.png)

Se você responder sim ao seguinte, o Sistema de Telefonia com Plano de Chamada é a solução certa para você:

- O Plano de Chamada está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft ao PSTN.

No entanto, sua situação pode ser mais complexa. Por exemplo, você pode ter escritórios em locais onde o Plano de Chamada não está disponível. Ou talvez você precise de uma solução de combinação que suporte uma implantação complexa e multi-nacional, com requisitos diferentes para locais geográficos diferentes. A Microsoft oferece suporte a uma combinação de soluções: 

- Sistema telefônico com Plano de Chamada
- Sistema telefônico com sua própria operadora PSTN com Roteamento Direto
- Uma solução de combinação que usa o Sistema telefônico com o Plano de Chamada e o Sistema de Telefonia com Roteamento Direto

## <a name="what-do-you-need-to-read"></a>O que você precisa ler?

**Obrigatório para todos.** Algumas das seções deste artigo pertencem a todas as organizações. Por exemplo, todos devem ler sobre o Sistema telefônico e entender as opções de conexão com a PSTN (Rede Telefônica Pública Comutado). 


| Obrigatório para todos | Descrição |
| :------------|:-------|
| [**Sistema de Telefonia**](#phone-system) | A tecnologia da Microsoft para habilenciar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Microsoft 365 com o Microsoft Teams. |
| [**Opções de conectividade PSTN (Rede Telefônica Pública Comutado)**](#public-switched-telephone-network-connectivity-options) | Uma opção entre usar a Microsoft como operadora de telefonia ou conectar sua própria operadora de telefonia ao Microsoft Teams usando o Roteamento Direto. Combinado com o Sistema telefônico, as opções de conectividade PSTN permitem que os usuários façam chamadas telefônicas em todo o mundo.|

**Dependendo de seus requisitos.** Algumas das seções deste artigo são pertinentes, dependendo da implantação e dos requisitos existentes. Por exemplo, o Location-Based roteamento só é necessário para clientes de Roteamento Direto em locais geográficos que não permitem ignorar tarifas.

Considere quais dessas configurações adicionais você pode precisar:

![O Diagrama 2 mostra componentes de voz adicionais, como números de telefone da Microsoft, planos de discagem e roteamento de chamadas e assim por diante.](media/voice-consider-additional-components.png)

| Dependendo de seus requisitos | Descrição |
| :------------|:-------|
| [**Números de telefone da Microsoft**](#phone-numbers-from-microsoft) | Como obter e gerenciar números de telefone da Microsoft e como transferir números existentes para a Microsoft. Leia isto se precisar obter números de telefone para o Plano de Chamada da Microsoft, transferir números existentes, obter números de serviço e assim por diante. |
| [**Planos de discagem e roteamento de chamadas**](#dial-plans-and-call-routing) | Como configurar e gerenciar planos de discagem que traduzem números de telefone discados em um formato alternativo (normalmente formato E.164) para autorização de chamada e roteamento de chamadas. Leia isso se você precisar entender quais são os planos de discagem e se precisa especificar planos de discagem para sua organização.|
| [**Chamada de emergência**](#emergency-calling) | Como gerenciar e configurar as chamada de emergência dependendo da sua opção de conectividade &mdash; PSTN. Leia esta seção se você estiver usando o Plano de Chamada da Microsoft ou o Roteamento Direto e precisar entender como gerenciar chamadas de emergência para sua organização. |
| [**Roteamento com base em local para Roteamento Direto**](#location-based-routing-for-direct-routing) |Como usar o Location-Based (LBR) para restringir o bypass de chamada tarifada para usuários do Microsoft Teams com base em sua localização geográfica. Leia esta seção se sua organização estiver usando o Roteamento Direto em um local que não permita o bypass de tarifas tarifada.
| [**Topologia de rede para recursos de voz na nuvem**](#network-topology-for-voice-features) | Se sua organização estiver implantando Location-Based roteamento (LBR) para Roteamento Direto ou chamadas de emergência dinâmicas, você deverá definir as configurações de rede para uso com esses recursos no Microsoft Teams. Leia esta seção se você estiver implementando a LBR para Roteamento Direto ou se estiver implementando chamadas de emergência dinâmicas com Plano de Chamada ou Roteamento Direto. |
| [**Migrar sua solução de voz existente**](#migrate-your-existing-voice-solution-to-teams) | O que você precisa pensar ao migrar sua solução de voz para o Teams.  Leia esta seção se você estiver migrando de uma solução de voz existente para o Teams. 



> [!Important]
> Este artigo se concentra em soluções de voz com o Microsoft Teams. Embora as soluções com o Skype for Business Online ainda estão disponíveis (conforme descrito nas soluções de telefonia [da Microsoft),](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)é importante compreender que o Skype for Business Online será retirado em 31 de julho de 2021.  Após essa data, o serviço Skype for Business Online não estará mais acessível. Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e do Skype for Business Online, não terá &mdash; &mdash; mais suporte. Este artigo apresenta as soluções de voz do Teams e como você pode conectar sua rede de telefonia local, se necessário, ao Teams usando o Roteamento Direto.


## <a name="phone-system"></a>Sistema de Telefonia

O Sistema de Telefonia é a tecnologia da Microsoft para habilenciar os recursos de controle de chamada e PBX (Private Branch Exchange) na nuvem do Microsoft 365 ou do Office 365 com o Microsoft Teams.

O Sistema telefônico funciona com o Teams ou clientes e dispositivos certificados do Skype for Business. O Sistema telefônico permite substituir seu sistema PBX existente por um conjunto de recursos fornecidos diretamente do Microsoft 365 ou do Office 365. 

As chamadas entre usuários em sua organização são tratadas internamente no Sistema Telefônico e nunca vão para a PSTN (Rede Telefônica Pública Comutado). Isso se aplica a chamadas entre usuários de sua organização localizados em diferentes áreas geográficas, eliminando os custos de longa distância dessas chamadas internas.

Este artigo apresenta os seguintes recursos e funcionalidades principais do Sistema de Telefonia e as decisões de implantação que você precisará considerar:

- [Atendedores automáticos e filas de chamadas](#auto-attendants-and-call-queues)
- [Caixa Postal da Nuvem](#cloud-voicemail)
- [Identidade de chamada](#calling-identity)

![O Diagrama 3 mostra que o sistema de telefonia contém atendedores automáticos e consultas de chamada, caixa postal na nuvem e identidade de Chamada](media/phone-system-contains.png)

Para obter informações sobre todos os recursos do Sistema de Telefonia e como configurar o Sistema de Telefonia, consulte os seguintes artigos:

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)
- [Configurar o Sistema telefônico em sua organização](setting-up-your-phone-system.md)<br>
  Descreve como comprar e atribuir licenças do Sistema de Telefonia, gerenciar números de telefone e configurar créditos de comunicação para números de chamada gratuita. 

Para obter informações sobre como gerenciar dispositivos compatíveis, consulte [Gerenciar seus dispositivos no Microsoft Teams e](devices/device-management.md) no Teams [Marketplace.](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


### <a name="auto-attendants-and-call-queues"></a>Assistentes automáticos e filas de chamada

Os atenderes automáticos permitem configurar opções de menu para rotear chamadas com base na entrada do chamador. Filas de chamada são áreas de espera para chamadores. Usados em conjunto, os atendimentos automáticos e as filas de chamada podem roteá-los facilmente para a pessoa ou o departamento apropriado em sua organização.

Para obter informações sobre os atendimentos automáticos e filas de chamada, consulte os seguintes artigos:

- [Planejar os atendimentos automáticos e filas de chamada do Teams](plan-auto-attendant-call-queue.md)
- [Configurar um assistente automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md) 
- [Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada](voice-case-study-call-queues.md)<br>
  Descreve como uma corporação multi-nacional fictícia, a Contoso, implementou os atendimentos automáticos e filas de chamadas para sua solução de voz.

### <a name="cloud-voicemail"></a>Caixa Postal na Nuvem

A Caixa Postal na Nuvem, da plataforma Azure Voicemail Services, dá suporte somente a depósitos de caixa postal nas caixas de correio do Exchange. Ele não dá suporte a sistemas de email de terceiros. 

A Caixa Postal na Nuvem inclui transcrição da mensagem de voz que, por padrão, está habilitada para todos os usuários da organização. Suas necessidades comerciais podem exigir que você desabilite a transcrição da caixa postal para usuários específicos ou para todos em toda a organização.

Somente usuários online, a Caixa Postal na Nuvem é configurada e provisionada automaticamente para os usuários depois que uma licença do Sistema de Telefonia é atribuída. Para usuários do Sistema telefônico com uma caixa de correio do Exchange, você precisará executar etapas de configuração adicionais. 

Para saber mais sobre a Caixa Postal na Nuvem e sua configuração, consulte os seguintes artigos:

- [Configurar a caixa postal na nuvem](set-up-phone-system-voicemail.md)
- [Definir políticas de caixa postal em sua organização](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)


### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID do chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Para obter informações sobre como configurar a ID de chamada ou para alterar ou bloquear a ID de chamada, consulte Definir a ID de chamada [de um usuário.](set-the-caller-id-for-a-user.md) 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opções de conectividade de Rede Telefônica Pública Comutado

O Sistema telefônico fornece recursos pbx completos para sua organização. No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa conectar o Sistema Telefônico à PSTN (Rede Telefônica Pública Comutado). Para conectar o Sistema Telefônico ao PSTN, você pode escolher uma das seguintes opções:

- [**Sistema telefônico com Plano de Chamada.**](#phone-system-with-calling-plan) Uma solução de toda a nuvem com a Microsoft como operadora PSTN.

- [**Sistema telefônico com sua própria operadora PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) usando o Roteamento Direto para conectar seu ambiente local ao Teams.

Você também pode escolher uma combinação de opções, que permite criar uma solução para um ambiente complexo ou gerenciar uma migração de várias etapas (mais sobre migração posterior).

### <a name="phone-system-with-calling-plan"></a>Sistema telefônico com Plano de Chamada 

Conforme descrito anteriormente neste artigo, o Sistema de Telefonia com Plano de Chamada é a solução de voz na nuvem da Microsoft para usuários do Teams. Essa é a opção mais simples que conecta o Microsoft Phone System à PSTN (Rede Telefônica Pública Comutado) para habilitar chamadas para telefones fixos e celulares em todo o mundo. Com essa opção, a Microsoft fornece a funcionalidade PbX (Private Branch Exchange) para sua organização e atua como sua operadora PSTN, conforme mostrado no diagrama a seguir:

![O Diagrama 4 mostra o Sistema telefônico com os Atenderdores Automáticos, filas de chamadas, ID de chamadas e muito mais, e a Microsoft como operadora PSTN](media/voice-solution-microsoft-complete.png)

Se você responder sim ao seguinte, o Sistema de Telefonia com Plano de Chamada é a solução certa para você:

- O Plano de Chamada está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft ao PSTN.

Com esta opção: 

- Você obterá o Microsoft Phone System com planos de chamadas nacionais ou internacionais adicionados que habilitam chamadas para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).

- Você não precisa de implantação ou manutenção de uma implantação local porque o Plano de Chamada opera fora do &mdash; Microsoft 365 ou do Office 365.

- Observação: se necessário, você pode optar por conectar um SBC (Controlador de Borda de Sessão) compatível por meio do Roteamento Direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros compatíveis com o SBC.

Essa opção requer conexão ininterrupta com o Microsoft 365 ou o Office 365.

Para obter mais informações sobre o Plano de Chamada, consulte os seguintes artigos:

- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Como comprar um plano de chamadas](calling-plans-for-office-365.md)
- [Disponibilidade de país e região do Plano de chamadas](https://docs.microsoft.com/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)
- [Configurar Plano de Chamada](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema telefônico com sua própria operadora PSTN com Roteamento Direto

Essa opção conecta o Microsoft Phone System à sua rede de telefonia usando Roteamento Direto, conforme mostrado no diagrama a seguir: 

![O Diagrama 5 mostra o Sistema telefônico com Roteamento Direto](media/voice-solution-with-direct-routing.png)

Se você responder sim às seguintes perguntas, o Sistema de Telefonia com Roteamento Direto é a solução certa para você:

- Você deseja usar o Teams com o Sistema telefônico.
- Você precisa manter sua operadora PSTN atual.
- Você deseja misturar o roteamento, com algumas chamadas passando pelo Plano de Chamada, algumas por meio da sua operadora.
- Você precisa operar com PBXs de terceiros e/ou equipamentos como pagers gerais, dispositivos analógicos e assim por diante.

Com esta opção:

- Conecte seu próprio SBC com suporte ao Microsoft Phone System sem a necessidade de software local adicional.

- Você pode usar praticamente qualquer operadora de telefonia com o Microsoft Phone System.

- Você pode optar por configurar e gerenciar essa opção, ou pode ser configurada e gerenciada por sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).

- Você pode configurar a interoperabilidade entre seu equipamento de telefonia, como um PBX de &mdash; terceiros e dispositivos analógicos &mdash; e o Microsoft Phone System.


Esta opção requer o seguinte:

- Conexão ininterrupta com o Microsoft 365 ou o Office 365.

- Implantando e mantendo um SBC com suporte.

- Um contrato com uma operadora de terceiros.
  (A menos que implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão no Sistema de Telefonia com Plano de Chamada.)

Para obter mais informações sobre o Roteamento Direto, consulte os seguintes artigos:

- [Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)
- [Planejar o Roteamento Direto](direct-routing-plan.md)
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Gerenciar políticas de roteamento de voz para uso com Roteamento Direto](manage-voice-routing-policies.md)
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Números de telefone da Microsoft

A Microsoft tem dois tipos de números de telefone *disponíveis:* números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização, e números de serviço, disponíveis como números de serviço de chamada tarifada e gratuita.  Os números de serviço têm uma capacidade de chamada simultânea maior do que os números de assinante e podem ser atribuídos a serviços como Audioconferência, Atendimento Automático ou Filas de Chamada.

Você precisará decidir:

- Quais locais de usuários precisam de novos números de telefone da Microsoft?
- De que tipo de número de telefone (assinante ou serviço) preciso? 
- Como faço para fazer a portabilidade de números de telefone existentes para o Teams?

Para obter mais informações sobre como gerenciar números de telefone em sua organização, incluindo obter novos números ou transferir números de saída, consulte os seguintes artigos:

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diferentes tipos de números de telefone usados para o Plano de Chamada](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md)
- [Transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planos de discagem e roteamento de chamadas

Um plano de discagem é um conjunto de regras de normalização que convertem números de telefone discados em um formato alternativo (normalmente formato E.164) para autorização de chamada e roteamento de chamadas.

Você precisará decidir o seguinte: 

- Minha organização precisa de um plano de discagem personalizado?
- Quais usuários exigem um plano de discagem personalizado?
- Qual plano de discagem de locatário deve ser atribuído a cada usuário?

Para obter mais informações, consulte os seguintes artigos: 

- [O que são planos de discagem?](what-are-dial-plans.md)
- [Planejar planos de discagem de locatário](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Chamada de emergência

A forma como você configura chamadas de emergência é diferente dependendo da sua opção de conectividade PSTN: Plano de Chamada da Microsoft ou Roteamento Direto. Chamadas de emergência dinâmicas para o Plano de Chamada da Microsoft e o Roteamento Direto do Sistema de Telefonia fornece a capacidade de configurar e encaminhar chamadas de emergência e notificar a equipe de segurança com base na localização atual do cliente teams. Para obter mais informações sobre conceitos e terminologia de chamada de emergência e como configurar chamada de emergência dinâmica, consulte os seguintes artigos:

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
- [Estudo de caso da Contoso: Chamada de emergência](voice-case-study-emergency-calling.md)<br>
  Descreve como uma corporação multi-nacional fictícia, a Contoso, implementou as chamada de emergência para sua organização.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based roteamento para roteamento direto

Em alguns países e regiões, é ilegal ignorar o provedor de PSTN (Rede Telefônica Pública Comutado) para reduzir os custos de chamadas a longa distância. Location-Based roteamento para Roteamento Direto permite restringir o bypass de chamadas tarifadas para usuários do Microsoft Teams com base em sua localização geográfica. Para obter mais informações sobre como planejar e configurar Location-Based roteamento (LBR), consulte os seguintes artigos:

- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Estudo de caso da Contoso: Location-Based Roteamento](voice-case-study-location-based-routing.md)<br>
  Descreve como uma corporação multinacional fictícia, a Contoso, implementou Location-Based roteamento para sua organização.

## <a name="network-topology-for-voice-features"></a>Topologia de rede para recursos de voz

Se você estiver implantando chamadas de emergência dinâmicas ou Location-Based roteamento para Roteamento Direto, deverá configurar as configurações de rede para uso com esses recursos no Microsoft Teams. Para saber como configurar as configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:

- [Configurações de rede para recursos de voz na nuvem no Microsoft Teams - Conceitos e terminologia](cloud-voice-network-settings.md)
- [Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migrar sua solução de voz existente para o Teams

Para uma organização que está atualizando para o Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly. O uso do Sistema telefônico com o Teams só é suportado quando o usuário está no modo TeamsOnly. Se você precisar de informações básicas sobre a atualização para o Teams, comece aqui:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Sobre a estrutura de atualização](upgrade-framework.md)
- [Atualizar do Skype for Business para o Teams — para administradores de IT](upgrade-to-teams-on-prem-overview.md)

Ao migrar sua solução de voz, há quatro cenários de chamadas possíveis ao migrar para o modo TeamsOnly:

- [**Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Após a atualização, esse usuário continuará a ter um Plano de Chamada da Microsoft.

- **[Um usuário no Skype for Business Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** com funcionalidade de voz local por meio do Skype for Business local ou do Cloud Connector Edition. A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.

- Um usuário no Skype for Business local com o **[Enterprise Voice,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)** que se move para a internet e mantém a conectividade PSTN local. Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para o Roteamento Direto. 

- **[Um usuário no Skype for Business local com](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** o Enterprise Voice, que vai se mudar para online e usar um plano de Chamada da Microsoft.  Migrar esse usuário para o Teams requer mover a conta do Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamada da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.

Para obter mais informações sobre como implementar sua migração de voz para cada um desses cenários, incluindo informações sobre quando você precisa configurar a conectividade híbrida e como migrar usuários com funcionalidade de voz local para Roteamento Direto, consulte os &mdash; &mdash; seguintes artigos:

- [Considerações do PSTN ao atualizar para o Teams — para administradores de IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Estudo de caso de migração de voz da Contoso](voice-case-study-overview.md)<br>
  O estudo de caso descreve como uma corporação multi-nacional fictícia, a Contoso, implementou uma solução de voz do Teams para sua organização. Ele contém os seguintes artigos:

  - [Plano de atualização do Teams](voice-case-study-migration-plan.md)
  - [Opções de conectividade PSTN e sistema telefônico](voice-case-study-phone-system.md)
  - [Implementação de Roteamento baseado em local](voice-case-study-location-based-routing.md)
  - [Chamada de emergência](voice-case-study-emergency-calling.md)
  - [Atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md)
  - [Audioconferência](voice-case-study-audio-conferencing.md)












