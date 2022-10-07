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
- highpri
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
- seo-marvel-may2020
search.appverid: MET150
description: Saiba mais sobre as opções de chamada do Teams (conectividade PSTN) e as decisões que você tomará para sua organização.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f547528f39e92be1660f670cad44c66726fe3ef2
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999636"
---
# <a name="pstn-connectivity-options"></a>Opções de conectividade PSTN

A Microsoft fornece recursos completos de PBX (Private Branch Exchange) para sua organização por meio do Sistema de Telefonia. No entanto, para permitir que os usuários façam chamadas fora da sua organização, você precisa conectar o Sistema de Telefonia à Rede Telefônica Pública Comunada (PSTN).

Este artigo se concentra nas opções de conectividade PSTN. Para obter mais informações sobre soluções de voz da Microsoft, incluindo detalhes sobre os recursos do Sistema de Telefonia, consulte [Planejar sua solução de voz do Teams](cloud-voice-landing-page.md).

Para conectar o Sistema de Telefonia ao PSTN, você pode escolher entre as seguintes opções:

- [**Plano de chamada**](#phone-system-with-calling-plan). Uma solução totalmente na nuvem com a Microsoft como sua operadora PSTN.

- [**Conexão do operador**](#phone-system-with-operator-connect). Com o Operator Connect, se sua operadora existente participar do programa Microsoft Operator Connect, ela poderá gerenciar chamadas PSTN e SBCs (Controladores de Borda de Sessão).

- [**Operadora de Conexão Móvel.**](#phone-system-with-operator-connect-mobile) Com Operadora de Conexão Móvel, o número de telefone habilitado para SIM de um usuário também é o número de telefone do Teams. Se sua operadora existente participar do programa Microsoft Operadora de Conexão Móvel, ela poderá gerenciar o serviço para trazer chamadas PSTN para o Teams.  **Operadora de Conexão Móvel é uma versão prévia pública.**

- [**Roteamento**](#phone-system-with-direct-routing) Direto, que permite que você use sua própria operadora PSTN conectando seus controladores de borda de sessão (SBC) ao sistema de telefonia.

Você também pode escolher uma combinação de opções, que permite criar uma solução para um ambiente complexo ou gerenciar uma migração de várias etapas.

A opção ou as opções escolhidas afetam como alguns recursos do Sistema de Telefonia são configurados. Para obter mais informações, consulte [Considerações de](#configuration-considerations) configuração mais adiante neste artigo.

## <a name="phone-system-with-calling-plan"></a>Sistema de Telefonia com Plano de Chamadas

O Sistema de Telefonia com Plano de Chamadas é a solução de voz na nuvem da Microsoft para usuários do Teams. Essa solução é a opção mais simples que conecta o Sistema de Telefonia ao PSTN. Com essa opção, a Microsoft atua como sua operadora PSTN, conforme mostrado no diagrama a seguir:

![O Diagrama 1 mostra o Sistema de Telefonia com o Plano de Chamadas.](media/voice-solutions-simple.png)

Se você responder sim ao seguinte, o Sistema de Telefonia com Plano de Chamada será a solução certa para você:

- O Plano de Chamadas está disponível em sua região.
- Você não precisa manter sua operadora PSTN atual.
- Você deseja usar o acesso gerenciado pela Microsoft ao PSTN.

Com esta opção:

- Você obtém o Sistema de Telefonia com Planos de Chamadas Nacionais ou Internacionais adicionados que permitem a chamada para telefones em todo o mundo (dependendo do nível de serviço que está sendo licenciado).

- Você não precisa de implantação ou manutenção&mdash;de uma implantação local porque o Plano de Chamadas opera fora do Microsoft 365.

- Observação: você pode conectar um SBC (Controlador de Borda de Sessão) com suporte por meio do Roteamento Direto para interoperabilidade com PBXs de terceiros, dispositivos analógicos e outros equipamentos de telefonia compatíveis com o SBC.

Essa opção requer conexão ininterrupta com o Microsoft 365.

Para obter mais informações sobre o Plano de Chamadas, consulte os seguintes artigos:

- [Qual plano de chamadas é ideal para você?](calling-plan-landing-page.md)
- [Como comprar um plano de chamadas](calling-plans-for-office-365.md)
- [Disponibilidade de país e região do Plano de chamadas](./country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
- [Configurar Plano de Chamadas](set-up-calling-plans.md)

## <a name="phone-system-with-operator-connect"></a>Sistema de Telefonia com Conexão de Operador

Com o Operator Connect, se sua operadora existente participar do programa Microsoft Operator Connect, ela poderá gerenciar o serviço para trazer chamadas PSTN para o Teams. Sua operadora gerencia os serviços de chamada PSTN e os controladores de borda de sessão (SBCs), permitindo que você economize na compra e no gerenciamento de hardware.

O Operator Connect pode ser a solução certa para sua organização se:

- O Plano de Chamadas da Microsoft não está disponível em sua localização geográfica.
- Sua operadora preferencial é participante do programa Microsoft Operator Connect.
- Você deseja encontrar uma nova operadora para habilitar a chamada no Teams.

Para obter informações sobre os benefícios e requisitos do Operator Connect e para obter uma lista de operadoras que participam deste programa, consulte [Plan Operator Connect](operator-connect-plan.md). Para obter informações sobre como configurar o Operator Connect, consulte [Configurar Conexão do Operador](operator-connect-configure.md).

## <a name="phone-system-with-operator-connect-mobile"></a>Sistema de Telefonia com Operadora de Conexão Móvel

**Operadora de Conexão Móvel é uma versão prévia pública.**

Se sua operadora existente participar do programa Microsoft Operadora de Conexão Móvel, ela poderá gerenciar o serviço para trazer chamadas PSTN para o Teams. Com Operadora de Conexão Móvel, o número de telefone habilitado para SIM de um usuário também é o número de telefone do Teams.  Os usuários podem usar um único número de telefone no Microsoft Teams em suas linhas de serviço móvel e de mesa.  

Você pode considerar uma combinação de serviços. Por exemplo, você pode escolher Operadora de Conexão Móvel para suas organizações de vendas e de campo que exigem suporte móvel, mas outra solução para sua organização de call center local que depende de telefones de mesa. 

Operadora de Conexão Móvel pode ser a solução certa para sua organização se:

- Você deseja usar um número de celular primário habilitado para SIM da empresa para o Telefone do Teams como uma solução de número único.
- Seu operador preferido é um participante do programa Microsoft Operadora de Conexão Móvel.
- Você deseja encontrar um novo operador para habilitar a chamada no Teams.

Para obter informações sobre os benefícios e requisitos do Operadora de Conexão Móvel e para links para operadoras que participam deste programa, consulte [Plano Operadora de Conexão Móvel](operator-connect-mobile-plan.md). Para obter informações sobre como configurar Operadora de Conexão Móvel, consulte [Configurar Operadora de Conexão Móvel](operator-connect-mobile-configure.md).

## <a name="phone-system-with-direct-routing"></a>Sistema de Telefonia com Roteamento Direto

Essa opção conecta o Sistema de Telefonia à sua rede de telefonia usando o Roteamento Direto, conforme mostrado no diagrama a seguir: 

![O Diagrama 5 mostra o Sistema de Telefonia com Roteamento Direto.](media/voice-solution-with-direct-routing.png)

Se você responder sim às seguintes perguntas, o Sistema de Telefonia com Roteamento Direto será a solução certa para você:

- Você deseja usar o Teams com o Sistema de Telefonia.
- Você precisa manter sua operadora PSTN atual.
- Você quer misturar roteamento, com algumas chamadas passando pelo Plano de Chamadas, algumas por meio da operadora.
- Você precisa interoperar com PBXs de terceiros e/ou equipamentos como pagers de sobrecarga, dispositivos analógicos e assim por diante.

Com esta opção:

- Você conecta seu próprio SBC (Controlador de Borda de Sessão) com suporte ao Sistema de Telefonia sem a necessidade de software local adicional.

- Você pode usar praticamente qualquer operadora de telefonia com o Sistema de Telefonia.

- Você pode configurar e gerenciar essa opção ou ela pode ser configurada e gerenciada por sua operadora ou parceiro (pergunte se sua operadora ou parceiro fornece essa opção).

- Você pode configurar a interoperabilidade entre seu equipamento de telefonia&mdash;, como um PBX de terceiros e dispositivos analógicos&mdash;e o Sistema de Telefonia.

Essa opção requer o seguinte:

- Conexão ininterrupta com o Microsoft 365.

- Implantação e manutenção de um SBC com suporte.

- Um contrato com uma operadora de terceiros.
  (A menos que implantado como uma opção para fornecer conexão com PBX de terceiros, dispositivos analógicos ou outros equipamentos de telefonia para usuários que estão no Sistema de Telefonia com Plano de Chamadas.)

Para obter mais informações sobre o Roteamento Direto, consulte os seguintes artigos:

- [Planejar o Roteamento Direto](direct-routing-plan.md)
- [Configurar o Roteamento Direto](direct-routing-configure.md)
- [Gerenciar políticas de roteamento de voz para uso com o Roteamento Direto](manage-voice-routing-policies.md)
- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Lista de controladores de borda da sessão certificados para Roteamento Direto](direct-routing-border-controllers.md)

## <a name="configuration-considerations"></a>Considerações sobre configuração

A maioria dos recursos do Sistema de Telefonia é a mesma, independentemente da opção de conectividade PSTN que você escolher. Por exemplo, as configurações de chamada sem resposta e encaminhamento, transferência de chamada, música personalizada em espera, estacionamento de chamadas, linha compartilhada e aplicativos de voz estão disponíveis. Para obter uma lista completa dos recursos do Sistema de Telefonia, confira aqui [o que você obtém com o Sistema de Telefonia](here-s-what-you-get-with-phone-system.md).

No entanto, há algumas diferenças na funcionalidade que afetam a forma como você configura determinados recursos do Sistema de Telefonia. Por exemplo, o Roteamento Direto requer etapas adicionais para configurar o roteamento de chamadas. Como outro exemplo, o Roteamento Direto fornece LBR (Roteamento Baseado em Localização). A LBR permite restringir o bypass de chamada tarifada em determinadas localizações geográficas em que ela não é permitida. 

A tabela a seguir realça as diferenças de configuração primárias. As seções que seguem a tabela fornecem links para mais informações e detalhes.

| Opção | Descrição | Gerenciamento de números de telefone | Roteamento de chamadas | Disponibilidade de chamadas de emergência |
| :------------| :-------| :-------| :-------| :-------| 
| Planos de Chamadas | - A Microsoft atua como operadora PSTN.<br>- Você não precisa comprar nem gerenciar SBCs.| Obtido por meio da Microsoft.| - Gerenciado pela Microsoft. <br> -Administração configura os planos de discagem do usuário para a conversão de números. | -Habilitado pela Microsoft. <br> -Administração registra endereços. <br> -Chamada dinâmica com suporte. |
| Conexão do operador | -A operadora gerencia a conectividade PSTN e os SBCs. <br> - Você não precisa comprar nem gerenciar SBCs. | - Obtido por meio da transportadora. <br> - Números associados a endereços de emergência gerenciados pela operadora. | - Gerenciado por operadora. <br>-Administração configura os planos de discagem do usuário para a conversão de números. | -Habilitado por operadora. <br> -Administração registra endereços. <br> -Chamada dinâmica com suporte. |
| Operadora de Conexão Móvel | -A operadora gerencia SIM-Enabled número de celular, conectividade PSTN e SBCs. <br> - Você não precisa comprar nem gerenciar SBCs. | - Obtido por meio da transportadora. <br> -Números associados a endereços de emergência gerenciados pela operadora. | - Gerenciado por operadora. <br> Administração configura planos de discagem do usuário para conversão de números. |- Habilitado por operadora. <br> – Administração registra endereços. <br> - Chamada dinâmica com suporte. <br> - Operadora com suporte para chamada de emergência de discador nativo. |
| Roteamento Direto | - Requer um SBC certificado adquirido de um fornecedor de terceiros.<br>- Conecte seu SBC ao Sistema de Telefonia.<br> - Use sua operadora PSTN existente. | Obtido por meio da transportadora. | - Requer configuração extra por administrador.<br>-Administração configura planos de discagem de tronco para conversão de números. <br>-LBR disponível para restringir o desvio de chamada tarifada. | - Requer configuração extra por administrador. <br>-Endereços registrados sem suporte. <br>-Chamada dinâmica com suporte, mas requer configuração adicional. |


### <a name="phone-number-management"></a>Gerenciamento de números de telefone

A Microsoft tem dois tipos de números de telefone disponíveis: números de assinante (usuário), que podem ser atribuídos aos usuários em sua organização e números de serviço, disponíveis como números de serviço de chamada tarifada e gratuita. Os números de serviço têm uma capacidade de chamada simultânea maior do que os números de assinante e podem ser atribuídos a serviços como Audioconferência, Atendedores Automáticos ou Filas de Chamadas.

Você precisará decidir:

- Quais locais de usuário precisam de novos números de telefone da Microsoft?
- De qual tipo de número de telefone (assinante ou serviço) preciso?
- Como fazer portar números de telefone existentes para o Teams?

A maneira como você adquire e gerencia números de telefone difere dependendo da opção de conectividade PSTN.

- Para obter informações sobre como gerenciar números de telefone para o Plano de Chamadas, consulte [Gerenciar números de telefone para Planos de Chamadas](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).

- Para obter informações sobre como gerenciar números de telefone com o Operator Connect, consulte [Configurar números de telefone com a Conexão de Operador](operator-connect-configure.md#set-up-phone-numbers).

- Para obter informações sobre como gerenciar números de telefone com Operadora de Conexão Móvel, consulte [Configurar números de telefone com Operadora de Conexão Móvel](operator-connect-mobile-configure.md#set-up-phone-numbers).

- Para obter informações sobre como gerenciar números de telefone para Roteamento Direto, consulte [Configurar o número de telefone e habilitar a voz corporativa](direct-routing-enable-users.md#configure-the-phone-number-and-enable-enterprise-voice).

### <a name="call-routing-and-dial-plans"></a>Roteamento de chamadas e planos de discagem

A maneira como você configura o roteamento de chamadas difere dependendo da opção de conectividade PSTN.  

- Para Planos de Chamadas, a maior parte do roteamento de chamadas é tratada pela infraestrutura do Plano de Chamadas da Microsoft. Você configura planos de discagem do usuário para fins de conversão de números para autorização de chamada e roteamento de chamadas. Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).

- Para o Operator Connect e Operadora de Conexão Móvel, a maioria do roteamento de chamadas é gerenciada pela operadora. Você configura planos de discagem do usuário para fins de conversão de números para autorização de chamada e roteamento de chamadas. Para obter mais informações, consulte [O que são planos de discagem?](what-are-dial-plans.md).

- Para Roteamento Direto, você deve configurar o roteamento de chamadas especificando as rotas de voz e atribuindo políticas de roteamento de voz aos usuários. Você pode configurar planos de discagem para conversão de números no nível do tronco para garantir a interoperabilidade com controladores de borda de sessão (SBCs). Para obter mais informações, consulte [Configurar o roteamento de voz para Roteamento Direto](direct-routing-voice-routing.md), Gerenciar políticas de roteamento [de voz](manage-voice-routing-policies.md) e [Traduzir números de telefone](direct-routing-translate-numbers.md). 

### <a name="location-based-routing-for-direct-routing"></a>Location-Based roteamento direto

Em alguns países e regiões, é ilegal ignorar a operadora PSTN para diminuir os custos de chamadas de longa distância. Location-Based LBR (Roteamento Direto) permite restringir o bypass de chamada tarifada para usuários do Teams com base em sua localização geográfica. Para obter mais informações sobre como planejar e configurar o LBR, consulte os seguintes artigos:

- [Planejar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-plan.md)
- [Configurar definições de rede para o Roteamento baseado na localização](location-based-routing-configure-network-settings.md)
- [Habilitar o Roteamento baseado na localização para o Roteamento direto](location-based-routing-enable.md)
- [Estudo de caso da Contoso: Location-Based roteamento](voice-case-study-location-based-routing.md)<br>
  Descreve como uma empresa fictícia multi-nacional, a Contoso, implementou Location-Based roteamento para sua organização.

### <a name="emergency-calling"></a>Chamada de emergência

A maneira como você configura chamadas de emergência diferem dependendo da opção de conectividade PSTN.

- Para o Plano de Chamadas, cada usuário é habilitado automaticamente para chamadas de emergência. O usuário deve ter um endereço de emergência registrado associado ao número de telefone atribuído. Há suporte para chamadas de emergência dinâmicas (com base na localização do cliente do Teams). Para obter mais informações, consulte [Considerações sobre planos de chamadas](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-calling-plans) 

- Para o Operator Connect, cada usuário é habilitado automaticamente para chamadas de emergência. O usuário deve ter um endereço de emergência registrado associado ao número de telefone atribuído. Há suporte para chamadas de emergência dinâmicas (com base na localização do cliente do Teams). Para obter mais informações, consulte [Considerações para Conexão do Operador](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect). 

- Por Operadora de Conexão Móvel, cada usuário é habilitado automaticamente para chamadas de emergência. Chamadas de emergência são roteadas automaticamente para a Operadora de Conexão Móvel para um determinado número. Há suporte para chamadas de emergência dinâmicas (com base na localização do cliente do Teams). Para obter mais informações, consulte [Considerações sobre Operadora de Conexão Móvel](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-operator-connect-mobile). 

- Para Roteamento Direto, você deve definir políticas de chamada de emergência para usuários usando uma política de roteamento de chamadas de emergência do Teams (TeamsEmergencyCallRoutingPolicy). A política definirá números de emergência e seu destino de roteamento associado. Não há suporte para locais de emergência registrados para usuários de Roteamento Direto. Para chamadas de emergência dinâmicas, a configuração adicional é necessária para rotear chamadas de emergência e, possivelmente, para a conectividade do parceiro. Para obter mais informações, consulte [Considerações sobre roteamento direto](what-are-emergency-locations-addresses-and-call-routing.md#considerations-for-direct-routing).

#### <a name="for-more-information"></a>Para obter mais informações

Para obter mais informações sobre conceitos e terminologia de chamadas de emergência e como configurar chamadas de emergência e chamadas de emergência dinâmicas, consulte os seguintes artigos:

- [Gerenciar chamadas de emergência](what-are-emergency-locations-addresses-and-call-routing.md)
- [Planejar e configurar chamadas de emergência dinâmicas](configure-dynamic-emergency-calling.md)
- [Gerenciar políticas de chamadas de emergência](manage-emergency-calling-policies.md)
- [Gerenciar políticas de roteamento de chamadas de emergência para Roteamento Direto](manage-emergency-call-routing-policies.md)
- [Estudo de caso da Contoso: Chamada de emergência](voice-case-study-emergency-calling.md)<br>
  Descreve como uma empresa fictícia multi-nacional, Contoso, implementou chamadas de emergência para sua organização.

### <a name="network-topology-for-voice-features"></a>Topologia de rede para recursos de voz

Se você estiver implantando chamadas de emergência dinâmicas ou Location-Based roteamento direto, defina as configurações de rede para esses recursos no Microsoft Teams. Para saber como definir as configurações de rede para regiões de rede, sites de rede, sub-redes de rede e endereços IP confiáveis, consulte os seguintes artigos:

- [Configurações de rede para recursos de voz na nuvem no Microsoft Teams – Conceitos e terminologia](cloud-voice-network-settings.md)
- [Gerenciar sua topologia de rede para recursos de voz na nuvem no Microsoft Teams](manage-your-network-topology.md)
