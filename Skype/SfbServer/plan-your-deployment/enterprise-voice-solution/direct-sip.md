---
title: Conexões SIP diretas no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: As conexões SIP diretas são suportadas entre o Skype for Business Server e gateways PSTN e IP-PBX no Enterprise Voice.
ms.openlocfilehash: 6e30a24bd4509d20a4ad19192e677e3bea21fff9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834451"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexões SIP diretas no Skype for Business Server

As conexões SIP diretas são suportadas entre o Skype for Business Server e gateways PSTN e IP-PBX no Enterprise Voice.

Você pode usar conexões SIP diretas para conectar o Skype for Business Server a um dos seguintes:

- Um PBX IP

- Um gateway PSTN

Para implantar uma conexão SIP direta, você segue, basicamente, as mesmas etapas de implantação de um tronco SIP. Em ambos os casos, implemente a conexão usando a interface externa de um Servidor de Mediação. A única diferença é que você conecta os troncos SIP a uma entidade externa, como um gateway ITSP, e conecta as conexões SIP diretas a uma entidade interna dentro da sua rede local, como um IP-PBX ou um gateway de uma Rede Telefônica Pública Comutada (PSTN).

## <a name="direct-sip-deployment-options"></a>Opções de implantação de SIP direto

### <a name="skype-for-business-server-stand-alone"></a>Skype for Business Server Stand-Alone
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se sua organização usa uma das implantações descritas nesta seção, você pode usar o Skype for Business Server como a única solução de telefonia para parte ou toda a organização. Esta seção descreve detalhadamente as seguintes implantações:

- **Implantação incremental:** Essa opção presume que você tenha uma infraestrutura pbx existente e pretende introduzir o Enterprise Voice incrementalmente para grupos ou equipes menores em sua organização.

- **Implantação somente VoIP:** essa opção pressupo que você está pensando em implantar o Enterprise Voice em um site que não tem uma infraestrutura de telefonia tradicional.

#### <a name="incremental-deployment"></a>Implantação Incremental

Na implantação incremental, o Skype for Business Server é a única solução de telefonia para equipes ou departamentos individuais, enquanto o restante dos usuários em uma organização continua a usar um PBX. Essa estratégia de implantação incremental fornece uma maneira de introduzir a telefonia IP em sua empresa por meio de programas piloto controlados. Os grupos de trabalho cujas necessidades de comunicação são melhor atendidas pelo Microsoft Unified Communications são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente. Grupos de trabalho adicionais podem ser migrados para o Enterprise Voice, conforme necessário.

A opção incremental é recomendada se você tiver definido claramente grupos de usuários que têm requisitos de comunicação em comum e que se prestam ao gerenciamento centralizado. Essa opção também é eficaz se você tiver equipes ou departamentos espalhados por áreas geográficas amplas, onde a economia em tarifas de longa distância pode ser significativa. Na verdade, essa opção é útil para criar equipes virtuais cujos membros podem estar espalhados pelo mundo. Você pode criar, modificar ou desaquelar essas equipes em resposta rápida aos requisitos de negócios em mudança.

A figura a seguir mostra a topologia genérica para implantação do Enterprise Voice por trás de um PBX. Esta é a topologia recomendada para implantação incremental.

**Opção de implantação incremental**

![Diagrama da Opção de Migração Do Departamento](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se você estiver conectando sua implantação do Skype for Business Server a um parceiro SIP Direto certificado, um gateway PSTN (rede telefônica pública comutado) entre o Servidor de Mediação e o PBX não será necessário. Para uma lista de parceiros SIP diretos certificados, consulte o Programa de Interoperabilidade Aberta de Comunicações [Unificadas da Microsoft.](https://go.microsoft.com/fwlink/p/?linkId=203309)

> [!NOTE]
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do Servidor de Mediação.

Nessa topologia, os departamentos ou grupos de trabalho selecionados são habilitados para o Enterprise Voice. Um gateway PSTN vincula o grupo de trabalho habilitado para VoIP (Voice over Internet Protocol) ao PBX. Os usuários habilitados para o Enterprise Voice, incluindo funcionários remotos, se comunicam pela rede IP. As chamadas de usuários do Enterprise Voice para o PSTN e para colegas de trabalho que não estão habilitados para o Enterprise Voice são roteadas para o gateway PSTN apropriado. As chamadas de colegas que ainda estão no sistema PBX ou de chamadores na PSTN são roteadas para o gateway PSTN, que encaminha as chamadas para o Skype for Business Server para roteamento.

Há duas configurações recomendadas para conectar o Enterprise Voice a uma infraestrutura de PBX existente para interoperabilidade: Enterprise Voice por trás do PBX e Enterprise Voice na frente do PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice Behind o PBX

Quando o Enterprise Voice é implantado por trás do PBX, todas as chamadas do PSTN chegam ao PBX, que encaminha chamadas para usuários do Enterprise Voice para um gateway PSTN e chamadas para usuários de PBX para o PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice na frente do PBX

Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam ao gateway PSTN, que encaminha chamadas para usuários do Enterprise Voice para o Skype for Business Server e chamadas para usuários de PBX para o PBX. As chamadas para o PSTN de usuários do Enterprise Voice e do PBX são roteados pela rede IP para o gateway PSTN mais eficiente. A tabela a seguir mostra as vantagens e as desvantagens dessa configuração.

**Vantagens e desvantagens da implantação do Enterprise Voice na frente do PBX**

|**Vantagens**|**Desvantagens**|
|:-----|:-----|
|O PBX ainda atende usuários não habilitados para o Enterprise Voice.  <br/> |Gateways existentes podem não dar suporte aos recursos ou capacidade que você deseja.  <br/> |
|O PBX lida com todos os dispositivos anteriores.  <br/> |Requer um tronco do gateway para o PBX e do gateway para o Servidor de Mediação. Talvez seja necessário mais troncos do provedor de serviços.  <br/> |
|Os usuários do Enterprise Voice mantêm os mesmos números de telefone.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>VoIP-Only implantação

O Enterprise Voice oferece novos negócios e também novos sites de escritório para empresas existentes, com a oportunidade de implementar uma solução VoIP completa sem precisar se preocupar com a integração pbx ou incorrer nos custos substanciais de implantação e manutenção de uma infraestrutura IP-PBX. Essa solução oferece suporte a funcionários locais e remotos.

Nesta implantação, todas as chamadas são roteados pela rede IP. As chamadas para o PSTN são roteados para o gateway PSTN apropriado. O Skype for Business ou o Lync Phone Edition serve como um softphone. O controle de chamada remota não está disponível e não é necessário porque não há telefones PBX para os usuários controlarem. Os serviços de caixa postal e de atendimento automático estão disponíveis por meio da implantação opcional da Unificação de Mensagens (UM) do Exchange.

> [!NOTE]
> Além da infraestrutura de rede necessária para dar suporte ao Skype for Business Server, uma implantação somente VoIP pode usar um gateway pequeno e qualificado para dar suporte a aparelhos de fax e dispositivos analógicos.

A figura a seguir mostra uma topologia típica para uma implantação somente VoIP.

**Opção de implantação somente VoIP**

![Opção de implantação greenfidle](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> O caminho de mídia mostrado nesta figura tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar o bypass de mídia, o caminho de mídia será roteado através do Servidor de Mediação.

## <a name="pstn-gateway-deployment-options"></a>Opções de implantação do Gateway PSTN

### <a name="pstn-gateways"></a>Gateways PSTN

Gateways PSTN são componentes de hardware de terceiros que convertem sinais e mídia entre a infraestrutura do Enterprise Voice e da PSTN, diretamente ou por meio de troncos SIP. Em qualquer uma das topologias, o gateway encerra o PSTN. O gateway é isolado em sua própria sub-rede e conectado à rede corporativa por meio do Servidor de Mediação.

Normalmente, uma empresa com vários sites implantaria um ou mais gateways em cada site. Os sites de filial podem se conectar à PSTN por meio de um gateway ou por meio de um Aparelho de Filial Survivível, que combina gateway e servidores em uma única caixa. Se os sites de filial usarem um gateway, um Registrador e um Servidor de Mediação serão necessários no local, a menos que o link WAN seja resiliente. Um ou mais Servidores de Mediação, que são alocados em Servidores Front-End, podem encaminhar chamadas para um ou mais gateways em cada local. Recomendamos que o Registrador, o Servidor de Mediação e o gateway necessários no local sejam implantados como um Aparelho de FilialVivível.

Determinar o número, o tamanho e o local dos gateways PSTN é talvez a decisão mais importante e cara que você deve tomar ao planejar sua infraestrutura do Enterprise Voice.

Há várias perguntas a considerar. Tenha em mente que as respostas destas perguntas são interdependentes

- Quantos gateways PSTN são necessários? A resposta depende do número de usuários, do número antecipado de chamadas simultâneas (carga de tráfego) e do número de sites (cada site precisa de um).

- Qual deve ser o tamanho dos gateways? A resposta depende do número de usuários no site e da carga de tráfego.

- Onde os gateways devem ser localizados? A resposta depende em parte da topologia e em parte da distribuição geográfica de sua organização.

  Você também deve considerar suas opções de topologia de gateway (para obter detalhes, consulte Topologias de Gateway posteriormente neste tópico).

#### <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Os Servidores de Mediação podem rotear chamadas através de vários gateways, controladores de borda de sessão (SBCs) fornecidos por provedores de serviços de telefonia da Internet ou uma combinação dos dois. Além disso, vários Servidores de Mediação no pool podem interagir com vários gateways. A rota lógica definida entre um Servidor de Mediação e um gateway é chamada de tronco. Quando um usuário interno faz uma chamada PSTN, a lógica de roteamento de saída no pool de Front-End escolhe qual tronco rotear para fora de todas as combinações possíveis que podem estar disponíveis para o roteamento dessa chamada específica. Com o balanceamento de carga DNS, se uma chamada não conseguir alcançar um gateway devido a um problema com um Servidor de Mediação específico no pool, a chamada será recuperada para um Servidor de Mediação alternativo no pool.

Para obter detalhes sobre o planejamento de vários gateways, consulte [tronco M:N no Skype for Business Server.](m-n-trunk.md)

Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologias de gateway

Ao considerar as perguntas fundamentais da implantação de gateway, siga estas etapas:

1. Conte os sites nos quais você deseja fornecer conectividade PSTN usando o Enterprise Voice.

2. Estime o tráfego em cada site (número de usuários e número médio de chamadas por hora, por usuário).

3. Implante um ou mais gateways em cada site a fim de manipular o tráfego antecipado.

Com essa topologia, as chamadas entre os trabalhadores em cada site e entre sites são todas roteadas através de sua intranet. As chamadas para o PSTN são roteadas sobre a rede IP da empresa até os gateways mais próximos do local dos números de destino. Mas e se sua organização suportar dezenas ou centenas ou até mesmo milhares de sites espalhados em um ou mais continentes, assim como fazem muitas instituições financeiras e outras grandes empresas? Nesses casos, a implantação de um gateway separado em cada site não é prática.

Para resolver esse problema, muitas empresas de grande porte preferem implantar um ou alguns sites centrais de telefonia grandes.

Nessa topologia, vários gateways grandes suficientes para acomodar a carga de usuário antecipada são implantados em cada site central. Todas as chamadas aos usuários na empresa são encaminhadas pelo provedor de serviço de telefonia da empresa a um site central. A lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou pela PSTN.

#### <a name="gateway-location"></a>Local do gateway

O local do gateway também pode determinar os tipos de gateways que você escolhe e como eles são configurados. Há dezenas de protocolos PSTN, nenhum em um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não será um problema, mas se você localizar os gateways em diversos países/regiões, cada um precisa estar configurado de acordo com os padrões de PSTN nesse país/região. Além disso, os gateways certificados para operação no, por exemplo, Canadá, talvez não sejam certificados na Índia, Brasil ou União Europeia.

#### <a name="gateway-size-and-number"></a>Tamanho e número de gateways

Os gateways PSTN que a maioria das organizações considerará implantar variam com relação ao tamanho de 2 a 960 portas. (Há gateways ainda maiores, mas eles são usados principalmente pelos provedores de serviço de telefonia.) Ao estimar o número de portas exigido por sua organização, use as seguintes diretrizes:

- Organizações com uso leve de telefonia (uma chamada PSTN por usuário, por hora) deve alocar uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, precisará de um gateway com duas portas.

- Organizações com um uso moderado de telefonia (duas chamadas PSTN por usuário, por hora) deve alocar uma porta para cada 10 usuários. Por exemplo, se você tiver 100 usuários, precisará de um total de 10 portas alocadas entre um ou mais gateways.

- Organizações com uso pesado de telefonia (três ou mais chamadas PSTN por usuário, por hora) devem alocar uma porta para cada cinco usuários. Por exemplo, se você tiver 47.000 usuários, precisará de um total de 9.400 portas alocadas entre pelo menos 10 grandes gateways.

- É possível adquirir portas adicionais à medida que o número de usuários ou quantidade de tráfego em sua organização aumenta.

Para qualquer quantidade de usuários que você deve suportar, você tem a opção de implantar uma quantidade menor de gateways maiores ou menores. Como regra, recomenda-se um mínimo de dois gateways para uma organização a fim de manter a disponibilidade, caso um gateway falhe.

Cada gateway PSTN implantado deve ter pelo menos um Servidor de Mediação correspondente.


