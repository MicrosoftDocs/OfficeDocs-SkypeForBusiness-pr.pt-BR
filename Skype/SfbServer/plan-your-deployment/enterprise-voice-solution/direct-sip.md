---
title: Conexões SIP diretas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Há suporte para conexões SIP diretas entre o Skype for Business Server e os gateways PSTN e IP-PBX no Enterprise Voice.
ms.openlocfilehash: 1948e08d63aed9d49c70443a386adce6dc65f78e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803050"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexões SIP diretas no Skype for Business Server

Há suporte para conexões SIP diretas entre o Skype for Business Server e os gateways PSTN e IP-PBX no Enterprise Voice.

Você pode usar conexões SIP diretas para conectar o Skype for Business Server a um dos seguintes:

- Um PBX IP

- Um gateway PSTN

Para implementar uma conexão SIP direta, você deve seguir essencialmente as mesmas etapas de implantação que faria para implementar um tronco SIP. Em ambos os casos, você implementa a conexão usando a interface externa de um servidor de mediação. A única diferença é que você conecta troncos SIP a uma entidade externa, como um gateway ITSP, e conecta conexões SIP diretas a uma entidade interna dentro de sua rede local, como um IP-PBX ou um gateway de rede telefônica pública comutada (PSTN).

## <a name="direct-sip-deployment-options"></a>Opções de implantação de SIP Direto

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server autônomo
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se a sua organização usa uma das implantações descritas nesta seção, você pode usar o Skype for Business Server como a única solução de telefonia de parte ou de toda a organização. Esta seção descreve as seguintes implantações em detalhes:

- **Implantação incremental:** Essa opção pressupõe que você tenha uma infraestrutura existente de PBX (Exchange Branch Exchange) e pretende introduzir o Enterprise Voice de forma incremental para grupos ou equipes menores em sua organização.

- **Implantação somente VoIP:** essa opção pressupõe que você está considerando a implantação do Enterprise Voice em um site que não tem uma infraestrutura de telefonia tradicional.

#### <a name="incremental-deployment"></a>Implantação incremental

Na implantação incremental, o Skype for Business Server é a única solução de telefonia para equipes ou departamentos individuais, enquanto o restante dos usuários de uma organização continua a usar um PBX. Esta estratégia de implantação incremental oferece uma maneira de introduzir a telefonia IP na sua empresa por meio de programas pilotos controlados. Os grupos de usuários cujas necessidades de comunicação são mais bem servidos pela Microsoft Unified Communications são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente. Os grupos de outros grupos podem ser migrados para o Enterprise Voice, conforme necessário.

A opção incremental será recomendada se você tiver claramente definido os grupos de usuários que têm requisitos de comunicação em comum e que se desejam para gerenciamento centralizado. Essa opção também será eficiente se você tiver equipes ou departamentos que sejam espalhados por áreas geográficas grandes, em que a economia em tarifas de longa distância pode ser importante. Na verdade, essa opção é útil para criar equipes virtuais cujos membros podem ficar espalhados pelo mundo todo. Você pode criar, modificar ou desmanchar essas equipes em resposta rápida para atender às necessidades de negócios.

A figura a seguir mostra a topologia genérica para a implantação do Enterprise Voice atrás de um PBX. Esta é a topologia recomendada para implantação incremental.

**Opção de implantação incremental**

![Diagrama de opções de migração departamental](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se você estiver conectando a implantação do Skype for Business Server a um parceiro SIP certificado, um gateway PSTN (rede telefônica pública comutada) entre o servidor de mediação e o PBX não será necessário. Para obter uma lista de parceiros SIP diretos certificados, consulte o [programa de interoperabilidade aberto da Microsoft Unified Communications](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado pelo servidor de mediação.

Nessa topologia, os departamentos ou grupos de domínio selecionados são habilitados para o Enterprise Voice. Um gateway PSTN conecta o grupo de trabalho habilitado para o protocolo de voz com o protocolo de Internet (VoIP) ao PBX. Os usuários que estão habilitados para o Enterprise Voice, incluindo trabalhadores remotos, se comunicam pela rede IP. Chamadas por usuários do Enterprise Voice para a PSTN e para colegas de trabalho que não estão habilitados para Enterprise Voice são roteadas para o gateway PSTN apropriado. As chamadas de colegas que ainda estão no sistema PBX ou de chamadores no PSTN são roteadas para o gateway PSTN, que encaminha as chamadas para o Skype for Business Server para roteamento.

Há duas configurações recomendadas para conectar a Enterprise Voice a uma infraestrutura PBX existente para interoperabilidade: Enterprise Voice atrás do PBX e do Enterprise Voice na frente do PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice atrás do PBX

Quando o Enterprise Voice é implantado por trás do PBX, todas as chamadas da PSTN chegam no PBX, que roteia chamadas para usuários do Enterprise Voice para um gateway PSTN e chamadas para usuários do PBX para o PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice na frente do PBX

Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam no gateway PSTN, que roteia chamadas para usuários do Enterprise Voice para o Skype for Business Server e chamadas para usuários do PBX para o PBX. Chamadas para a PSTN dos usuários da Enterprise Voice e PBX são roteadas pela rede IP para o gateway PSTN mais econômico. A tabela a seguir mostra as vantagens e desvantagens desta configuração.

**Vantagens e desvantagens da implantação do Enterprise Voice na frente do PBX**

|**Vantagens**|**Desvantagens**|
|:-----|:-----|
|O PBX ainda atende aos usuários não habilitados para o Enterprise Voice.  <br/> |Os gateways existentes podem não oferecer suporte aos recursos ou à capacidade desejados.  <br/> |
|O PBX manipula todos os dispositivos anteriores.  <br/> |Requer um tronco do gateway para o PBX e do gateway para o servidor de mediação. Você pode precisar de mais troncos do provedor de serviços.  <br/> |
|Os usuários do Enterprise Voice mantêm os mesmos números de telefone.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Implantação somente VoIP

O Enterprise Voice oferece novas empresas, e também novos sites do Office para empresas existentes, com a oportunidade de implementar uma solução VoIP completa sem precisar se preocupar com a integração com o PBX ou incorrer à implantação e à manutenção substanciais custos de uma infraestrutura de PBX IP. Esta solução aceita funcionários locais e remotos.

Nesta implantação, todas as chamadas são roteadas pela rede IP. As chamadas para a PSTN são roteadas para o gateway PSTN apropriado. O Skype for Business ou o Lync Phone Edition funciona como um softphone. O controle de chamada remota não está disponível e é desnecessário porque não há telefones PBX para os usuários controlarem. Os serviços de correio de voz e atendedor automático estão disponíveis por meio da implantação opcional da Unificação de mensagens (UM) do Exchange.

> [!NOTE]
> Além da infraestrutura de rede necessária para dar suporte ao Skype for Business Server, uma implantação somente VoIP pode usar um gateway pequeno e qualificado para dar suporte a máquinas de fax e dispositivos analógicos.

A figura a seguir mostra uma topologia típica para uma implantação somente de VoIP.

**Opção de implantação somente VoIP**

![Opção de implantação do Greenfidle](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado pelo servidor de mediação.

## <a name="pstn-gateway-deployment-options"></a>Opções de implantação do gateway PSTN

### <a name="pstn-gateways"></a>Gateways PSTN

Gateways de rede telefônica pública comutada (PSTN) são componentes de hardware de terceiros que traduzem sinais e mídias entre a infraestrutura de voz empresarial e a PSTN, diretamente ou por meio da conexão com troncos SIP. Em qualquer topologia, o gateway termina a PSTN. O gateway está isolado em sua própria sub-rede e está conectado à rede corporativa por meio do servidor de mediação.

Uma empresa com vários sites normalmente implantou um ou mais gateways em cada site. Os sites de ramificação podem se conectar à PSTN por meio de um gateway ou por meio de um aparelho de ramificação sobreviventes, que combina o gateway e os servidores em uma única caixa. Se os sites de filiais usarem um gateway, um servidor de registrador e mediação será necessário no site, a menos que o link de WAN seja resiliente. Um ou mais servidores de mediação, que são posicionados em servidores front-end, podem encaminhar chamadas para um ou mais gateways em cada site. Recomendamos que o registrador, o servidor de mediação e o gateway necessários no site sejam implantados como um aparelho de ramificação sobreviventes.

Determinar o número, o tamanho e a localização dos gateways PSTN talvez seja a decisão mais importante e cara que você deve fazer ao planejar sua infraestrutura empresarial.

Aqui estão as principais perguntas a serem consideradas. Tenha em mente que as respostas para essas perguntas são todas interdependentes

- Quantos gateways PSTN são necessários? A resposta depende do número de usuários, do número previsto de chamadas simultâneas (carga de tráfego) e do número de sites (cada site precisa de um).

- Qual é o tamanho dos gateways? A resposta depende do número de usuários no site e na carga do tráfego.

- Onde os gateways devem estar localizados? A resposta depende em parte da topologia e em parte da distribuição geográfica da sua organização.

  Você também deve considerar as opções de topologia do gateway (para obter detalhes, consulte Topologias de gateway mais adiante neste tópico).

#### <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Os servidores de mediação podem rotear chamadas por meio de vários gateways, Session Borderting (SBCs) fornecido pelos provedores de serviços de telefonia pela Internet ou uma combinação dos dois. Além disso, vários servidores de mediação no pool podem interagir com vários gateways. A rota lógica definida entre um servidor de mediação e um gateway é chamada de tronco. Quando um usuário interno coloca uma chamada PSTN, a lógica de roteamento de saída no pool de front-ends escolhe qual tronco deve ser roteado por todas as combinações possíveis que podem estar disponíveis para roteamento com essa chamada específica. Com o balanceamento de carga de DNS, se uma chamada não entrar em contato com um gateway devido a um problema com um servidor de mediação específico no pool, a chamada será repetida em um servidor de mediação alternativo no pool.

Para obter detalhes sobre o planejamento de vários gateways, consulte [M:N trunk in the Skype for Business Server](m-n-trunk.md).

Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [rotas de chamadas](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologias de gateway

Ao considerar as questões fundamentais de implantação de gateway, siga estas etapas:

1. Conte os sites nos quais você deseja fornecer conectividade PSTN usando o Enterprise Voice.

2. Estimar o tráfego em cada site (número de usuários e número médio de chamadas por hora por hora por usuário).

3. Implante um ou mais gateways em cada site para manipular o tráfego previsto.

Com essa topologia, chamadas entre trabalhadores em cada site e entre sites são roteadas pela intranet. As chamadas para a PSTN são roteadas na rede de IP da empresa para os gateways mais próximos ao local dos números de destino. Mas e se a sua organização oferecer suporte a dezenas ou centenas de sites ou até a milhares de sites distribuídos em um ou mais continentes, pois muitas instituições financeiras e outras grandes empresas fazem? Nesses casos, a implantação de um gateway separado em cada site não é prática.

Para solucionar esse problema, muitas grandes empresas preferem implantar um ou alguns sites centrais de telefonia grandes.

Nessa topologia, vários gateways grandes suficientes para acomodar a carga de usuário prevista são implantados em cada site central. Todas as chamadas para os usuários na empresa são encaminhadas pelo provedor de serviços telefônicos da empresa para um site central. A lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou pela PSTN.

#### <a name="gateway-location"></a>Localização do gateway

O local do gateway também pode determinar os tipos de gateway que você escolher e como eles são configurados. Há dezenas de protocolos PSTN, nenhum dos quais é um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não é um problema, mas se você localizar gateways em vários países/regiões, cada um deve ser configurado de acordo com os padrões PSTN desse país/região. Além disso, os gateways certificados para a operação, por exemplo, no Canadá, podem não ser certificados na Índia, Brasil ou na União Européia.

#### <a name="gateway-size-and-number"></a>Tamanho e número do gateway

Os gateways PSTN que a maioria das organizações considerará a implantação de intervalo em tamanho de 2 a até 960 portas. (Ainda há gateways maiores, mas eles são usados principalmente por provedores de serviço de telefonia.) Ao estimar o número de portas necessárias para sua organização, use as seguintes diretrizes:

- Organizações com uso leve de telefonia (uma chamada PSTN por usuário por hora) devem atribuir uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, será necessário um gateway com duas portas.

- Organizações com uso moderado de telefonia (duas chamadas PSTN por usuário por hora) devem atribuir uma porta para cada 10 usuários. Por exemplo, se você tiver usuários do 100, precisará de um total de 10 portas alocadas entre um ou mais gateways.

- Organizações com uso intenso de telefonia (três ou mais chamadas PSTN por usuário por hora) devem atribuir uma porta para cada cinco usuários. Por exemplo, se você tiver usuários do 47.000, precisará de um total de 9.400 portas alocadas entre pelo menos 10 gateways maiores.

- Portas adicionais podem ser adquiridas à medida que aumenta o número de usuários ou o volume de tráfego da sua organização.

Para qualquer número específico de usuários que você precisa dar suporte, você tem a opção de implantar mais gateways ou menos, ou menores. Como regra, um mínimo de dois gateways para uma organização é recomendado para manter a disponibilidade se um gateway falha.

Cada gateway PSTN que você implantar deve ter pelo menos um servidor de mediação correspondente.


