---
title: Opções de conectividade PSTN
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 07/08/2021
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
description: Saiba mais sobre Teams opções de chamada (conectividade PSTN) e as decisões que você tomará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b1b06178b269529b1d0227ff02d529c91ba1480
ms.sourcegitcommit: 5720fa12bdabdfc2988bf835c8cf95e4d64fa54e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2021
ms.locfileid: "53354510"
---
# <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

A Microsoft fornece recursos completos de Exchange (PBX) para sua organização por meio Sistema de Telefonia. No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa se conectar Sistema de Telefonia a Rede Telefônica Pública Comutado (PSTN).

Este artigo se concentra nas opções de conectividade PSTN. Para obter mais informações sobre soluções de voz da Microsoft, detalhando detalhes sobre Sistema de Telefonia recursos, consulte [Plan your Teams voice solution](cloud-voice-landing-page.md).

Para conectar Sistema de Telefonia ao PSTN, você pode escolher entre as seguintes opções:

- [**Plano de Chamada**](#phone-system-with-calling-plan). Uma solução completa na nuvem com a Microsoft como operadora PSTN.

- [**Roteamento**](#phone-system-with-direct-routing)Direto , que permite que você use sua própria operadora PSTN conectando seus Controladores de Borda de Sessão (SBC) a Sistema de Telefonia.

- [**Operador Conexão**](#phone-system-with-operator-connect), que está disponível atualmente apenas na **visualização pública.**  Com o Conexão operador, se sua operadora existente for participante do programa Conexão microsoft operator, eles poderão gerenciar a chamada PSTN e os Controladores de Borda de Sessão (SBCs). 

Você também pode escolher uma combinação de opções, que permite projetar uma solução para um ambiente complexo ou gerenciar uma migração em várias etapas.

Saiba que a opção ou as opções escolhidas afetam como alguns recursos Sistema de Telefonia estão configurados. Para obter mais informações, consulte [Considerações de](#configuration-considerations) configuração posteriormente neste artigo.


## <a name="phone-system-with-calling-plan"></a>Sistema de Telefonia com Plano de Chamada 

Sistema de Telefonia com o Plano de Chamadas é a solução de voz all-in-the-cloud da Microsoft para Teams usuários. Essa é a opção mais simples que conecta Sistema de Telefonia ao PSTN. Com essa opção, a Microsoft atua como sua operadora PSTN, conforme mostrado no diagrama a seguir:

![O Diagrama 1 mostra Sistema de Telefonia com Plano de Chamada](media/voice-solutions-simple.png)

Se você responder sim ao seguinte, Sistema de Telefonia com Plano de Chamada é a solução certa para você:

- O Plano de Chamada está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft à PSTN.

Com esta opção: 

- Você Telefone Microsoft sistema com planos de chamada domésticos ou internacionais que permitem a chamada para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).

- Você não exige implantação ou manutenção de uma implantação local porque o Plano de Chamada &mdash; opera fora do Microsoft 365.

- Observação: se necessário, você pode optar por conectar um Controlador de Borda de Sessão (SBC) com suporte por meio de Roteamento Direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia de terceiros suportados pelo SBC.

Essa opção requer conexão ininterrupta com Microsoft 365.

Para obter mais informações sobre o Plano de Chamada, consulte os seguintes artigos:

- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Como comprar um plano de chamadas](calling-plans-for-office-365.md)
- [Disponibilidade de país e região do Plano de chamadas](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar Plano de Chamada](set-up-calling-plans.md)


## <a name="phone-system-with-direct-routing"></a>Sistema de Telefonia com Roteamento Direto

Essa opção conecta Sistema de Telefonia à sua rede de telefonia usando Roteamento Direto, conforme mostrado no diagrama a seguir: 

![O Diagrama 5 mostra Sistema de Telefonia roteamento direto](media/voice-solution-with-direct-routing.png)

Se você responder sim às seguintes perguntas, Sistema de Telefonia com Roteamento Direto é a solução certa para você:

- Você deseja usar Teams com Sistema de Telefonia.
- Você precisa manter sua operadora PSTN atual.
- Você deseja misturar roteamento, com algumas chamadas passando pelo Plano de Chamadas, algumas por meio da sua operadora.
- Você precisa interoperar com PBXs e/ou equipamentos de terceiros, como pagers de sobrecarga, dispositivos analógicos e assim por diante.

Com esta opção:

- Você conecta seu próprio Controlador de Borda de Sessão (SBC) com suporte Sistema de Telefonia sem a necessidade de software local adicional.

- Você pode usar praticamente qualquer operadora de telefonia com Sistema de Telefonia.

- Você pode optar por configurar e gerenciar essa opção, ou ela pode ser configurada e gerenciada por sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).

- Você pode configurar a interoperabilidade entre seu equipamento de telefonia, como um PBX de terceiros e &mdash; dispositivos analógicos &mdash; e Sistema de Telefonia.

Esta opção requer o seguinte:

- Conexão ininterrupta com Microsoft 365.

- Implantando e mantendo um SBC com suporte.

- Um contrato com uma operadora de terceiros.
  (A menos que implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão em Sistema de Telefonia com Plano de Chamada.)

Para obter mais informações sobre Roteamento Direto, consulte os seguintes artigos:

- [Planejar o Roteamento Direto](direct-routing-plan.md)
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Gerenciar políticas de roteamento de voz para uso com Roteamento Direto](manage-voice-routing-policies.md)
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)


## <a name="phone-system-with-operator-connect"></a>Sistema de Telefonia com operador Conexão

Com o Conexão operador, atualmente em visualização pública, se sua operadora existente for participante do programa de Conexão do Microsoft Operator, eles poderão gerenciar o serviço para trazer a chamada PSTN para Teams. Sua operadora gerencia os serviços de chamada PSTN e controladores de borda de sessão (SBCs), permitindo que você salve na compra e gerenciamento de hardware.

O Conexão operador pode ser a solução certa para sua organização se:

- O Plano de Chamada da Microsoft não está disponível em sua localização geográfica.
- Sua operadora preferencial é participante do programa Conexão Microsoft Operator.
- Você deseja encontrar uma nova operadora para habilitar a chamada no Teams.

Para obter informações sobre os benefícios e requisitos do Operador Conexão e para obter uma lista de operadoras participantes deste programa, consulte [Plan Operator Conexão](operator-connect-plan.md). Para obter informações sobre como configurar o operador Conexão, consulte [Configure Operator Conexão](operator-connect-configure.md).

## <a name="configuration-considerations"></a>Considerações sobre configuração

A maioria Sistema de Telefonia recursos são os mesmos, independentemente da opção de conectividade PSTN escolhida. Por exemplo, as configurações de chamada sem resposta e encaminhamento, transferência de chamada, música personalizada em espera, estacionamento de chamadas, linha compartilhada e aplicativos de voz estão disponíveis. Para obter uma lista completa de Sistema de Telefonia recursos, consulte Aqui está [o que você obter com Sistema de Telefonia](here-s-what-you-get-with-phone-system.md).

No entanto, há algumas diferenças na funcionalidade que afetam a forma como você configura determinados Sistema de Telefonia recursos. Por exemplo, o Roteamento Direto exige etapas adicionais para configurar o roteamento de chamadas. Como outro exemplo, o Roteamento Direto fornece o Roteamento Baseado em Local (LBR), para que você possa restringir o desvio de chamada de chamada em determinados locais geográficos onde ele não é permitido. 


### <a name="phone-number-management"></a>Telefone gerenciamento de números

A Microsoft tem dois tipos de números de telefone disponíveis: números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização, e números de serviço, disponíveis como números de serviço de chamada e chamada gratuita. Os números de serviço têm maior capacidade de chamada simultânea do que números de assinantes e podem ser atribuídos a serviços como Audioconferência, Atendimento Automático ou Filas de Chamada.

Você precisará decidir:

- Quais locais de usuários precisam de novos números de telefone da Microsoft?
- De que tipo de número de telefone (assinante ou serviço) preciso?
- Como posso portar números de telefone existentes para Teams?

A forma como você adquire e gerencia números de telefone difere dependendo da sua opção de conectividade PSTN.

- Para obter informações sobre como gerenciar números de telefone para o Plano de Chamadas, consulte [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obter informações sobre como gerenciar números de telefone para Roteamento Direto, consulte [Configure the phone number and enable enterprise voice and voicemail](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail-online).

- Para obter informações sobre como gerenciar números de telefone com operador Conexão, consulte Configurar números de telefone [com operador Conexão](operator-connect-configure.md#set-up-phone-numbers).


### <a name="call-routing-and-dial-plans"></a>Roteamento de chamadas e planos de discagem

A forma como você configura o roteamento de chamadas difere dependendo da sua opção de conectividade PSTN.  

- Para Planos de Chamadas, a maior parte do roteamento de chamadas é manipulada pela infraestrutura do Plano de Chamadas da Microsoft. Configure os planos de discagem do usuário para fins de conversão de número para autorização de chamada e roteamento de chamadas. Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).

- Para Roteamento Direto, você deve configurar o roteamento de chamadas especificando as rotas de voz e atribuindo políticas de roteamento de voz aos usuários. Você pode configurar planos de discagem para conversão de número no nível do tronco para garantir a interoperabilidade com controladores de borda de sessão (SBCs). Para obter mais informações, consulte [Configure voice routing for Direct Routing](direct-routing-voice-routing.md), Manage voice routing [policies](manage-voice-routing-policies.md) and Translate [phone numbers](direct-routing-translate-numbers.md). 

- Para operador Conexão, a maior parte do roteamento de chamadas é gerenciada pela operadora.  Configure os planos de discagem do usuário para fins de conversão de número para autorização de chamada e roteamento de chamadas. Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).


### <a name="location-based-routing-for-direct-routing"></a>Location-Based roteamento para roteamento direto

Em alguns países e regiões, é ilegal ignorar a operadora PSTN para diminuir os custos de chamada de longa distância. Location-Based (LBR) para Roteamento Direto permite restringir o desvio de chamada para usuários Teams com base em sua localização geográfica. Para obter mais informações sobre como planejar e configurar a LBR, consulte os seguintes artigos:

- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Estudo de caso contoso: Location-Based routing](voice-case-study-location-based-routing.md)<br>
  Descreve como uma corporação multi-nacional fictícia, Contoso, implementou Location-Based roteamento para sua organização.


### <a name="emergency-calling"></a>Chamada de emergência

A forma como você configura a chamada de emergência difere dependendo da sua opção de conectividade PSTN.

- Para o Plano de Chamadas, cada usuário é automaticamente habilitado para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído. A chamada de emergência dinâmica (com base no local do Teams cliente) é suportada.  

- Para Roteamento Direto Teams, você deve definir políticas de chamadas de emergência para usuários usando uma política de roteamento de chamadas de emergência (TeamsEmergencyCallRoutingPolicy) para definir números de emergência e seu destino de roteamento associado. Locais de emergência registrados não são suportados para usuários de Roteamento Direto. Para chamadas de emergência dinâmicas, a configuração adicional é necessária para roteamento de chamadas de emergência e, possivelmente, para conectividade do parceiro.

- Para operador Conexão, cada usuário é automaticamente habilitado para chamadas de emergência e é necessário ter um endereço de emergência registrado associado ao número de telefone atribuído, mas só pode ser definido pelo parceiro de operadora. A chamada de emergência dinâmica (com base no local do Teams cliente) é suportada.

Para obter mais informações sobre conceitos e terminologia de chamada de emergência e como configurar a chamada de emergência e a chamada de emergência dinâmica, consulte os seguintes artigos:

- [Gerenciar chamada de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md)
- [Estudo de caso contoso: Chamada de emergência](voice-case-study-emergency-calling.md)<br>
  Descreve como uma corporação multi-nacional fictícia, Contoso, implementou a chamada de emergência para sua organização.


### <a name="network-topology-for-voice-features"></a>Topologia de rede para recursos de voz

Se você estiver implantando chamadas de emergência dinâmicas ou Location-Based roteamento para Roteamento Direto, você deve configurar configurações de rede para uso com esses recursos em Microsoft Teams. Para saber como configurar configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:

- [Configurações de rede para recursos de voz na nuvem Microsoft Teams - Conceitos e terminologia](cloud-voice-network-settings.md)
- [Gerenciar sua topologia de rede para recursos de voz na nuvem Microsoft Teams](manage-your-network-topology.md)



