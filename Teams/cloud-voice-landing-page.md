---
title: Planejar sua solução de voz em Microsoft Teams
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
description: Saiba mais sobre os Microsoft Teams de voz na nuvem e as decisões de implantação que você tomará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 391b8e2f30aa5e64fcb4b9e418af49341c2b9042
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901928"
---
# <a name="plan-your-teams-voice-solution"></a>Planejar sua solução Teams voz 

Este artigo ajuda você a decidir qual solução de voz da Microsoft é ideal para sua organização. Depois que você decidir, o artigo fornece um roteiro para o conteúdo que permitirá implementar sua solução escolhida.

> [!NOTE]
> Para obter orientações sobre como planejar uma solução de voz Teams como parte do seu plano geral de atualização para o Teams do Skype for Business Server, consulte Considerações da [PSTN](upgrade-to-teams-on-prem-pstn-considerations.md)para atualizar para o Teams do Skype for Business local.

Talvez você queira a solução mais simples Sistema de Telefonia &mdash; com Plano de Chamada. Esta é a solução all-in-the-cloud da Microsoft que fornece a funcionalidade de PbX (Private Branch Exchange) e chamadas para a PSTN (Rede Telefônica Pública Comutado), conforme mostrado no diagrama a seguir. Com essa solução, a Microsoft é sua operadora PSTN.

![O Diagrama 1 mostra Sistema de Telefonia com Plano de Chamada](media/voice-solutions-simple.png)

Se você responder sim ao seguinte, Sistema de Telefonia com Plano de Chamada é a solução certa para você:

- O Plano de Chamada está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à PSTN.

No entanto, sua situação pode ser mais complexa. Por exemplo, você pode ter escritórios em locais onde o Plano de Chamada não está disponível. Ou você pode precisar de uma solução de combinação que suporte uma implantação complexa e multi-nacional, com requisitos diferentes para locais geográficos diferentes. A Microsoft oferece suporte a uma combinação de soluções: 

- Sistema de Telefonia com Plano de Chamada
- Sistema de Telefonia com sua própria operadora PSTN com operador Conexão (atualmente disponível apenas em **visualização pública**)
- Sistema de Telefonia com sua própria operadora PSTN com Roteamento Direto
- Uma solução de combinação que usa Sistema de Telefonia com Plano de Chamadas, Sistema de Telefonia com Conexão operador e/ou Sistema de Telefonia com Roteamento Direto


## <a name="what-do-you-need-to-read"></a>O que você precisa ler?

**Obrigatório para todos.** Algumas das seções deste artigo pertencem a todas as organizações. Por exemplo, todos devem ler sobre Sistema de Telefonia e entender as opções para se conectar à PSTN (Rede Telefônica Pública Comucionária). 


| Obrigatório para todos | Descrição |
| :------------|:-------|
| [**Sistema de Telefonia**](#phone-system) | A tecnologia da Microsoft para habilenciar o controle de chamada e recursos de Exchange de filial privada (PBX) na nuvem Microsoft 365 com Microsoft Teams. |
| [**Opções de conectividade PSTN (Rede Telefônica Pública Comucionária)**](#public-switched-telephone-network-connectivity-options) | Uma opção entre usar a Microsoft como sua operadora de telefonia ou conectar sua própria operadora de telefonia Microsoft Teams usando roteamento direto ou Conexão. Combinado com Sistema de Telefonia, as opções de conectividade PSTN permitem que os usuários façam chamadas telefônicas em todo o mundo.|

**Dependendo de seus requisitos.** Algumas das seções deste artigo são pertinentes, dependendo da implantação e dos requisitos existentes. Por exemplo, Location-Based roteamento só é necessário para clientes de Roteamento Direto em locais geográficos que não permitem o desvio de tarifa.

Considere quais dessas configurações adicionais você pode precisar:

![O Diagrama 2 mostra componentes de voz adicionais, como Telefone números da Microsoft, planos de discagem e roteamento de chamadas e assim por diante.](media/voice-consider-additional-components.png)

| Dependendo de seus requisitos | Descrição |
| :------------|:-------|
| [**Telefone números da Microsoft**](#phone-numbers-from-microsoft) | Como obter e gerenciar números de telefone da Microsoft e como transferir números existentes para a Microsoft. Leia isso se precisar obter números de telefone para o Plano de Chamadas da Microsoft, transferir números existentes, obter números de serviço e assim por diante. |
| [**Planos de discagem e roteamento de chamadas**](#dial-plans-and-call-routing) | Como configurar e gerenciar planos de discagem que traduzem números de telefone discados em um formato alternativo (normalmente formato E.164) para autorização de chamada e roteamento de chamadas. Leia isso se você precisar entender quais são os planos de discagem e se precisa especificar planos de discagem para sua organização.|
| [**Chamada de emergência**](#emergency-calling) | Como gerenciar e configurar a chamada de &mdash; emergência, dependendo da sua opção de conectividade PSTN. Leia esta seção se você estiver usando o Plano de Chamadas da Microsoft ou o Roteamento Direto e precisar entender como gerenciar chamadas de emergência para sua organização. |
| [**Roteamento baseado em local para roteamento direto**](#location-based-routing-for-direct-routing) |Como usar Location-Based roteamento (LBR) para restringir o desvio de chamada Microsoft Teams usuários com base em sua localização geográfica. Leia esta seção se sua organização estiver usando Roteamento Direto em um local que não permita o desvio de tarifa.
| [**Topologia de rede para recursos de voz na nuvem**](#network-topology-for-voice-features) | Se sua organização estiver implantando Location-Based roteamento (LBR) para Roteamento Direto ou chamada de emergência dinâmica, você deve definir as configurações de rede para uso com esses recursos em Microsoft Teams. Leia esta seção se você estiver implementando LBR para Roteamento Direto ou se estiver implementando chamadas de emergência dinâmicas com Plano de Chamadas ou Roteamento Direto. |
| [**Migrar sua solução de voz existente**](#migrate-your-existing-voice-solution-to-teams) | O que você precisa pensar ao migrar sua solução de voz para Teams.  Leia esta seção se você estiver migrando de uma solução de voz existente para Teams. 



> [!Important]
> Este artigo se concentra em soluções de voz com Microsoft Teams. Embora as soluções com o Skype for Business Online ainda estão disponíveis (conforme descrito em soluções de telefonia da [Microsoft),](/SkypeForBusiness/hybrid/msft-telephony-solutions)é importante entender que o Skype for Business Online será retirado em 31 de julho de 2021.  Após essa data, o Skype for Business online não estará mais acessível. Além disso, a conectividade PSTN entre seu ambiente local, seja por meio do Skype for Business Server ou do Cloud Connector Edition e Skype for Business Online, não terá &mdash; &mdash; mais suporte. Este artigo apresenta Teams soluções de voz e como você pode conectar sua rede de telefonia local, se necessário, Teams usando roteamento direto ou Conexão.


## <a name="phone-system"></a>Sistema de Telefonia

Sistema de Telefonia é a tecnologia da Microsoft para habilenciar o controle de chamada e recursos de PBX (Private Branch Exchange) na nuvem Microsoft 365 ou Office 365 com Microsoft Teams.

Sistema de Telefonia funciona com Teams ou Skype for Business e dispositivos certificados. Sistema de Telefonia permite substituir seu sistema PBX existente por um conjunto de recursos diretamente entregues de Microsoft 365 ou Office 365. 

As chamadas entre usuários em sua organização são tratadas internamente Sistema de Telefonia e nunca vão para a PSTN (Rede Telefônica Pública Comucionária). Isso se aplica a chamadas entre usuários de sua organização localizados em diferentes áreas geográficas, eliminando os custos de longa distância dessas chamadas internas.

Este artigo apresenta os seguintes Sistema de Telefonia principais recursos e funcionalidades e as decisões de implantação que você precisará considerar:

- [Atendedores automáticos e filas de chamadas](#auto-attendants-and-call-queues)
- [Caixa Postal da Nuvem](#cloud-voicemail)
- [Identidade de chamada](#calling-identity)

![O Diagrama 3 mostra Telefone sistema contém atendedores automáticos e consultas de chamada, caixa postal na nuvem e identidade de chamada](media/phone-system-contains.png)

Para obter informações sobre todos os Sistema de Telefonia e como configurar o Sistema de Telefonia, consulte os seguintes artigos:

- [Veja o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md)
- [Configurar o Sistema de telefonia da sua organização](setting-up-your-phone-system.md)<br>
  Descreve como comprar e atribuir Sistema de Telefonia licenças, gerenciar números de telefone e configurar créditos de comunicação para números de chamada gratuita. 

Para obter informações sobre como gerenciar dispositivos com suporte, consulte [Manage your devices in Microsoft Teams](devices/device-management.md) and Teams [Marketplace](https://www.microsoft.com/microsoft-365/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1).


### <a name="auto-attendants-and-call-queues"></a>Atendimentos automáticos e filas de chamada

Os atendentes automáticos permitem configurar opções de menu para rotear chamadas com base na entrada do chamador. Filas de chamada são áreas de espera para chamadores. Usados em conjunto, os atendimentos automáticos e filas de chamada podem roteá-los facilmente para a pessoa ou departamento apropriado em sua organização.

Para obter informações sobre os atendimentos automáticos e filas de chamada, consulte os seguintes artigos:

- [Planejar Teams atendimentos automáticos e filas de chamada](plan-auto-attendant-call-queue.md)
- [Configurar um atendimento automático](create-a-phone-system-auto-attendant.md)
- [Criar uma fila de chamadas](create-a-phone-system-call-queue.md) 
- [Estudo de caso da Contoso: Atendimentos automáticos e filas de chamada](voice-case-study-call-queues.md)<br>
  Descreve como uma corporação multinacional fictícia, Contoso, implementou atendimentos automáticos e filas de chamadas para sua solução de voz.

### <a name="cloud-voicemail"></a>Caixa Postal na Nuvem

Caixa postal na Nuvem, alimentado pelos serviços de Caixa Postal do Azure, oferece suporte a depósitos de caixa postal para Exchange caixas de correio somente. Ele não dá suporte a sistemas de email de terceiros. 

A Caixa Postal na Nuvem inclui transcrição da mensagem de voz que, por padrão, está habilitada para todos os usuários da organização. Suas necessidades de negócios podem exigir que você desabilite a transcrição de caixa postal para usuários específicos ou para todos em toda a organização.

Para usuários somente online, Caixa postal na Nuvem é automaticamente configurada e provisionada para usuários depois que eles são atribuídos a uma Sistema de Telefonia de usuário. Para Sistema de Telefonia usuários com uma caixa de correio Exchange, você precisará executar etapas de configuração extras. 

Para obter mais informações sobre Caixa postal na Nuvem e sua configuração, consulte os seguintes artigos:

- [Configurar a Caixa postal na nuvem](set-up-phone-system-voicemail.md)
- [Definir políticas de caixa postal em sua organização](manage-voicemail-policies.md)


### <a name="calling-identity"></a>Identidade de chamada

Por padrão, todas as chamadas de saída usam o número de telefone atribuído como identidade de chamada (ID do chamador). O destinatário da chamada pode identificar o autor da chamada rapidamente e decidir se deseja aceitar ou rejeitar a chamada. Para obter informações sobre como configurar a ID do chamador ou para alterar ou bloquear a ID do chamador, consulte [Definir a ID](set-the-caller-id-for-a-user.md)do chamador para um usuário . 

## <a name="public-switched-telephone-network-connectivity-options"></a>Opções de conectividade de Rede Telefônica Pública Comutado

Sistema de Telefonia fornece recursos pbx completos para sua organização. No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa se conectar Sistema de Telefonia a Rede Telefônica Pública Comutado (PSTN). Para conectar Sistema de Telefonia ao PSTN, você pode escolher uma das seguintes opções:

- [**Sistema de Telefonia com Plano de Chamada.**](#phone-system-with-calling-plan) Uma solução completa na nuvem com a Microsoft como operadora PSTN.

- [**Sistema de Telefonia com sua própria operadora PSTN**](#phone-system-with-own-pstn-carrier-with-direct-routing) usando o Roteamento Direto para conectar seu ambiente local a Teams.

- [**Sistema de Telefonia com sua própria operadora PSTN**](operator-connect-plan.md)usando o operador Conexão , que está disponível no momento apenas na **visualização pública.**  Com o Conexão operador, se o operador existente for um participante do programa de Conexão do Microsoft Operator, ele poderá gerenciar o serviço para trazer a chamada PSTN para Teams. Para obter informações sobre os benefícios e requisitos do operador Conexão e para obter uma lista de operadores participantes deste programa, consulte [Plan Operator Conexão](operator-connect-plan.md).

Você também pode escolher uma combinação de opções, que permite projetar uma solução para um ambiente complexo ou gerenciar uma migração em várias etapas (mais sobre migração posterior).

### <a name="phone-system-with-calling-plan"></a>Sistema de Telefonia com Plano de Chamada 

Conforme descrito anteriormente neste artigo, Sistema de Telefonia com Plano de Chamadas é a solução de voz all-in-the-cloud da Microsoft para Teams usuários. Essa é a opção mais simples que conecta Telefone Microsoft System à PSTN (Rede Telefônica Pública Comucionária) para habilitar chamadas para telefones fixos e celulares em todo o mundo. Com essa opção, a Microsoft fornece a funcionalidade de Exchange de Filial Privada (PBX) para sua organização e atua como sua operadora PSTN, conforme mostrado no diagrama a seguir:

![O Diagrama 4 mostra Sistema de Telefonia com atendimentos automáticos, filas de chamada, ID do chamador e muito mais, e a Microsoft como operadora PSTN](media/voice-solution-microsoft-complete.png)

Se você responder sim ao seguinte, Sistema de Telefonia com Plano de Chamada é a solução certa para você:

- O Plano de Chamada está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à PSTN.

Com esta opção: 

- Você Telefone Microsoft sistema com planos de chamada domésticos ou internacionais que permitem a chamada para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).

- Você não exige implantação ou manutenção de uma implantação local porque o Plano de Chamada opera fora do Microsoft 365 &mdash; ou Office 365.

- Observação: se necessário, você pode optar por conectar um Controlador de Borda de Sessão (SBC) com suporte por meio de Roteamento Direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros suportados pelo SBC.

Essa opção requer conexão ininterrupta com Microsoft 365 ou Office 365.

Para obter mais informações sobre o Plano de Chamada, consulte os seguintes artigos:

- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Como comprar um plano de chamadas](calling-plans-for-office-365.md)
- [Disponibilidade de país e região do Plano de chamadas](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar Plano de Chamada](set-up-calling-plans.md)


### <a name="phone-system-with-own-pstn-carrier-with-direct-routing"></a>Sistema de Telefonia com a própria operadora PSTN com Roteamento Direto

Essa opção conecta Telefone Microsoft Sistema à sua rede de telefonia usando Roteamento Direto, conforme mostrado no diagrama a seguir: 

![O Diagrama 5 mostra Sistema de Telefonia roteamento direto](media/voice-solution-with-direct-routing.png)

Se você responder sim às seguintes perguntas, Sistema de Telefonia com Roteamento Direto é a solução certa para você:

- Você deseja usar Teams com Sistema de Telefonia.
- Você precisa manter sua operadora PSTN atual.
- Você deseja misturar roteamento, com algumas chamadas passando pelo Plano de Chamadas, algumas por meio da sua operadora.
- Você precisa interoperar com PBXs e/ou equipamentos de terceiros, como pagers de sobrecarga, dispositivos analógicos e assim por diante.

Com esta opção:

- Você conecta seu próprio SBC com suporte Telefone Microsoft Sistema sem a necessidade de software local adicional.

- Você pode usar praticamente qualquer operadora de telefonia com Telefone Microsoft System.

- Você pode optar por configurar e gerenciar essa opção, ou ela pode ser configurada e gerenciada por sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).

- Você pode configurar a interoperabilidade entre seu equipamento de telefonia, como um PBX de terceiros e dispositivos analógicos &mdash; &mdash; e Telefone Microsoft System.


Esta opção requer o seguinte:

- Conexão ininterrupta com Microsoft 365 ou Office 365.

- Implantando e mantendo um SBC com suporte.

- Um contrato com uma operadora de terceiros.
  (A menos que implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão em Sistema de Telefonia com Plano de Chamada.)

Para obter mais informações sobre Roteamento Direto, consulte os seguintes artigos:

- [Roteamento Direto do Sistema Telefônico](direct-routing-landing-page.md)
- [Planejar o Roteamento Direto](direct-routing-plan.md)
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Gerenciar políticas de roteamento de voz para uso com Roteamento Direto](manage-voice-routing-policies.md)
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)

## <a name="phone-numbers-from-microsoft"></a>Telefone números da Microsoft

A Microsoft tem dois tipos de números de telefone *disponíveis:* números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização, e números de serviço, disponíveis como números de serviço de chamada e chamada gratuita.  Os números de serviço têm maior capacidade de chamada simultânea do que números de assinantes e podem ser atribuídos a serviços como Audioconferência, Atendimento Automático ou Filas de Chamada.

Você precisará decidir:

- Quais locais de usuários precisam de novos números de telefone da Microsoft?
- De que tipo de número de telefone (assinante ou serviço) preciso? 
- Como posso portar números de telefone existentes para Teams?

Para obter mais informações sobre como gerenciar números de telefone em sua organização, incluindo obter novos números ou transferir números de saída, consulte os seguintes artigos:

- [Gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 
- [Diferentes tipos de números de telefone usados para o Plano de Chamadas](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Obter números de telefone para seus usuários](getting-phone-numbers-for-your-users.md)
- [Transferir números de telefone para Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)

## <a name="dial-plans-and-call-routing"></a>Planos de discagem e roteamento de chamadas

Um plano de discagem é um conjunto de regras de normalização que convertem números de telefone discados em um formato alternativo (normalmente formato E.164) para autorização de chamada e roteamento de chamadas.

Você precisará decidir o seguinte: 

- Minha organização precisa de um plano de discagem personalizado?
- Quais usuários exigem um plano de discagem personalizado?
- Qual plano de discagem de locatário deve ser atribuído a cada usuário?

Para obter mais informações, consulte os seguintes artigos: 

- [O que são planos de discagem?](what-are-dial-plans.md)
- [Planejar planos de discagem de locatários](what-are-dial-plans.md#planning-for-tenant-dial-plans)
- [Criar e gerenciar planos de discagem](create-and-manage-dial-plans.md)

## <a name="emergency-calling"></a>Chamada de emergência

A forma como você configura chamadas de emergência difere dependendo da sua opção de conectividade PSTN: Plano de Chamadas da Microsoft ou Roteamento Direto. A chamada de emergência dinâmica para o Plano de Chamadas da Microsoft e Sistema de Telefonia Roteamento Direto fornece a capacidade de configurar e rotear chamadas de emergência e notificar a equipe de segurança com base no local atual do cliente Teams. Para obter mais informações sobre conceitos e terminologia de chamada de emergência e como configurar a chamada de emergência dinâmica, consulte os seguintes artigos:

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
- [Estudo de caso contoso: Chamada de emergência](voice-case-study-emergency-calling.md)<br>
  Descreve como uma corporação multi-nacional fictícia, Contoso, implementou a chamada de emergência para sua organização.

## <a name="location-based-routing-for-direct-routing"></a>Location-Based roteamento para roteamento direto

Em alguns países e regiões, é ilegal ignorar o provedor PSTN (Rede Telefônica Pública Comutado) para diminuir os custos de chamadas de longa distância. Location-Based Roteamento para Roteamento Direto permite restringir o desvio de tarifa para usuários Microsoft Teams com base em sua localização geográfica. Para obter mais informações sobre como planejar e configurar Location-Based Roteamento (LBR), consulte os seguintes artigos:

- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Estudo de caso contoso: Location-Based routing](voice-case-study-location-based-routing.md)<br>
  Descreve como uma corporação multi-nacional fictícia, Contoso, implementou Location-Based roteamento para sua organização.

## <a name="network-topology-for-voice-features"></a>Topologia de rede para recursos de voz

Se você estiver implantando chamadas de emergência dinâmicas ou Location-Based roteamento para Roteamento Direto, você deve configurar configurações de rede para uso com esses recursos em Microsoft Teams. Para saber como configurar configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:

- [Configurações de rede para recursos de voz na nuvem Microsoft Teams - Conceitos e terminologia](cloud-voice-network-settings.md)
- [Gerenciar sua topologia de rede para recursos de voz na nuvem Microsoft Teams](manage-your-network-topology.md)

## <a name="migrate-your-existing-voice-solution-to-teams"></a>Migre sua solução de voz existente para Teams

Para uma organização que está atualizando para Teams, o objetivo final é mover todos os usuários para o modo TeamsOnly. O Sistema de Telefonia com Teams só é suportado quando o usuário está no modo TeamsOnly. Se você precisar de informações básicas sobre como atualizar para Teams, comece aqui:

- [Introdução à atualização para o Microsoft Teams](upgrade-start-here.md)
- [Sobre a estrutura de atualização](upgrade-framework.md)
- [Estratégias de atualização para administradores de IT](upgrade-to-teams-on-prem-implement.md)

Ao migrar sua solução de voz, há quatro cenários de chamadas possíveis ao migrar para o modo TeamsOnly:

- [**Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.**](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans) Após a atualização, esse usuário continuará a ter um Plano de Chamada da Microsoft.

- **[Um usuário no Skype for Business Online,](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)** com funcionalidade de voz local por meio Skype for Business local ou Cloud Connector Edition . A atualização do usuário para Teams precisa ser coordenada com a migração do usuário para Roteamento Direto para garantir que o usuário teamsOnly tenha funcionalidade PSTN.

- Um usuário Skype for Business local com o Enterprise Voice , que estará mudando para online e mantendo a conectividade **[](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)PSTN local.** Migrar esse usuário para Teams requer mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com a migração do usuário para Roteamento Direto. 

- **[Um usuário em Skype for Business local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)** com Enterprise Voice , que estará mudando para online e usando um plano de Chamada da Microsoft.  Migrar esse usuário para Teams requer mover a conta de Skype for Business local do usuário para a nuvem e coordenar essa movimentação com A) a porta do número de telefone desse usuário para um Plano de Chamadas da Microsoft ou B) atribuindo um novo número de assinante de regiões disponíveis.

Para obter mais informações sobre como implementar sua migração de voz para cada um desses cenários, incluindo informações sobre quando você precisa configurar a conectividade híbrida e como migrar usuários com funcionalidade de voz local para Roteamento Direto, consulte os &mdash; &mdash; seguintes artigos:

- [Considerações do PSTN ao atualizar para Teams — para administradores de IT](upgrade-to-teams-on-prem-pstn-considerations.md)

- [Estudo de caso de migração de voz contoso](voice-case-study-overview.md)<br>
  O estudo de caso descreve como uma empresa multi-nacional fictícia, Contoso, implementou uma solução Teams voz para sua organização. Ele contém os seguintes artigos:

  - [Teams plano de atualização](voice-case-study-migration-plan.md)
  - [Sistema de Telefonia e opções de conectividade PSTN](voice-case-study-phone-system.md)
  - [Implementação de Roteamento Baseado em Local](voice-case-study-location-based-routing.md)
  - [Chamada de emergência](voice-case-study-emergency-calling.md)
  - [Atendedores automáticos e filas de chamadas](voice-case-study-call-queues.md)
  - [Audioconferência](voice-case-study-audio-conferencing.md)
