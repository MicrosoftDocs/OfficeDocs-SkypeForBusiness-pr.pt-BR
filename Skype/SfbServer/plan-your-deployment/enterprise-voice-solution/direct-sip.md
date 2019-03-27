---
title: Conexões SIP diretas no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
description: Conexões SIP diretas são suportadas entre Skype para Business Server e os gateways PSTN e PBX IP no Enterprise Voice.
ms.openlocfilehash: 1ddcf66fb19f39661ffdd4cffdff754999db90d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30890126"
---
# <a name="direct-sip-connections-in-skype-for-business-server"></a>Conexões SIP diretas no Skype para Business Server

Conexões SIP diretas são suportadas entre Skype para Business Server e os gateways PSTN e PBX IP no Enterprise Voice.

Você pode usar conexões SIP diretas para conectar o Skype para Business Server a qualquer um dos seguintes procedimentos:

- Um IP-PBX

- Um gateway PSTN

Para implementar uma conexão de SIP direto, você seguir essencialmente as mesmas etapas de implantação, como faria para implementar um tronco SIP. Em ambos os casos, você pode implementar a conexão usando a interface externa de um servidor de mediação. A única diferença é que você conectar troncos SIP a uma entidade externa, como um gateway ITSP, e você conectar conexões SIP diretas a uma entidade interna em sua rede local, como um IP-PBX ou um gateway PSTN (rede) telefônica pública comutada.

## <a name="direct-sip-deployment-options"></a>Opções de implantação de SIP Direto

### <a name="skype-for-business-server-stand-alone"></a>Skype para Business Server autônomo
<a name="BKMK_CommunicationsServerStand-Alone"> </a>

Se sua organização usa uma das implantações descritas nesta seção, você pode usar o Skype para Business Server como a solução exclusiva de telefonia para a parte ou todo de uma organização. Esta seção descreve as seguintes implantações detalhes:

- **Implantação incremental:** Esta opção pressupõe que você tenha uma infraestrutura existente do exchange (PBX) privada de comutação e você pretende apresentar o Enterprise Voice incrementalmente para grupos menores ou equipes dentro da sua organização.

- **Implantação de somente VoIP:** esta opção pressupõe que você considera implantar o Enterprise Voice em um site que não tenha uma infraestrutura de telefonia tradicional.

#### <a name="incremental-deployment"></a>Implantação incremental

Na implantação incremental, Skype para Business Server é a solução exclusiva de telefonia para equipes individuais ou departamentos, enquanto o restante dos usuários em uma organização continuam a usar um PBX. Essa estratégia de implantação incremental possibilita a introdução da telefonia IP na empresa através de programas piloto controlados. Grupos de trabalho cuja comunicação necessidades são mais bem atendidas pela comunicação unificada da Microsoft são movidos para o Enterprise Voice, enquanto outros usuários permanecem no PBX existente. Grupos de trabalho adicionais podem ser migrados para o Enterprise Voice, conforme necessário.

A opção incremental recomenda-se claramente definidos que têm requisitos de comunicação em comum e que prestam ao gerenciamento centralizado de grupos de usuário. Essa opção também é eficaz se você tiver equipes ou departamentos que estão espalhados por áreas geográficas amplas, onde a economia em tarifas interurbanas pode ser significativa. Na verdade, essa opção é útil para criar equipes virtuais cujos membros estejam espalhados pelo mundo. Você pode criar, modificar ou dispersar essas equipes em resposta rápida às mudanças nos requisitos de negócios.

A figura a seguir mostra a topologia genérica da implantação do Enterprise Voice atrás de um PBX. Isso é a topologia recomendada para implantação incremental.

**Opção de implantação incremental**

![Diagrama de opção da migração departamental](../../media/Fig28_Departmental_migration_option.jpg)

> [!NOTE]
> Se você estiver se conectando seu Skype para implantação de servidor de negócios para um parceiro certificado do SIP direto, não é necessário um gateway PSTN (rede) telefônica comutada pública entre o servidor de mediação e o PBX. Para obter uma lista de parceiros certificados SIP direto, consulte o [Microsoft Unified Communications programa de interoperabilidade aberta](https://go.microsoft.com/fwlink/p/?linkId=203309).

> [!NOTE]
> O caminho de mídia ilustrado tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar bypass de mídia, o caminho de mídia é roteado por meio do servidor de mediação.

Nessa topologia, departamentos selecionados ou grupos de trabalho estão habilitados para o Enterprise Voice. Um gateway PSTN vincula o Voice over Internet Protocol (VoIP)-habilitado para o grupo de trabalho para o PBX. Os usuários habilitados para o Enterprise Voice, incluindo funcionários remotos, se comunicar pela rede IP. Chamadas por usuários do Enterprise Voice à PSTN e para colegas não habilitados para o Enterprise Voice são roteadas para o gateway PSTN apropriado. Chamadas de colegas que ainda estão no sistema PBX ou de chamadores na PSTN, são roteadas para o gateway PSTN, que encaminha as chamadas para Skype para Business Server para roteamento.

Há duas configurações recomendadas para conectar o Enterprise Voice a uma infra-estrutura de PBX existente para interoperabilidade: Enterprise Voice atrás do PBX e Enterprise Voice na frente do PBX.

#### <a name="enterprise-voice-behind-the-pbx"></a>Enterprise Voice atrás do PBX

Quando o Enterprise Voice é implantado atrás do PBX, todas as chamadas da PSTN chegarem ao PBX, que roteia as chamadas para usuários do Enterprise Voice com um gateway PSTN e chamadas para os usuários do PBX para o PBX.

#### <a name="enterprise-voice-in-front-of-the-pbx"></a>Enterprise Voice na frente do PBX

Quando o Enterprise Voice é implantado na frente do PBX, todas as chamadas chegam ao gateway PSTN, que roteia as chamadas para usuários do Enterprise Voice para Skype para Business Server e chamadas para usuários do PBX para o PBX. Chamadas para o PSTN dos usuários do Enterprise Voice e PBX são roteadas pela rede IP para o gateway PSTN mais econômico. A tabela a seguir mostra as vantagens e desvantagens dessa configuração.

**Vantagens e desvantagens de implantar o Enterprise Voice na frente do PBX**

|**Vantagens**|**Desvantagens**|
|:-----|:-----|
|O PBX ainda serve aos usuários não habilitados para o Enterprise Voice.  <br/> |Os gateways existentes podem não suportar os recursos ou capacidade que você deseja.  <br/> |
|O PBX processa todos os dispositivos anteriores.  <br/> |Requer um tronco no gateway para o PBX e do gateway para o servidor de mediação. Talvez você precise mais troncos do provedor do serviço.  <br/> |
|Usuários do Enterprise Voice mantenha os mesmos números de telefone.  <br/> | <br/> |

#### <a name="voip-only-deployment"></a>Implantação de somente VoIP

O Enterprise Voice oferece novas empresas e também novos sites do office para negócios existentes, com a oportunidade para implementar uma solução de VoIP completos sem a necessidade de se preocupar com integração com PBX ou incorrer a substancial implantação e manutenção custos de uma infra-estrutura de PBX IP. Essa solução oferece suporte a funcionários locais e remotos.

Nesta implantação, todas as chamadas são roteadas pela rede IP. Chamadas para o PSTN são roteadas para o gateway PSTN apropriado. Skype para Lync Phone Edition ou comercial funciona como um softfone. Controle de chamada remota não estiver disponível e desnecessários porque não há nenhuma telefones PBX para os usuários controlarem. Caixa postal e serviços de atendedor automático estão disponíveis por meio da implantação opcional do Exchange Unified Messaging (UM).

> [!NOTE]
> Além da infra-estrutura de rede é necessária para suportar Skype para Business Server, uma implantação de somente VoIP pode usar um gateway pequeno, qualificado para dar suporte a dispositivos analógicos e máquinas de fax.

A figura a seguir mostra uma topologia típica de uma implantação de somente VoIP.

**Opção de implantação de somente VoIP**

![Implantação greenfidle](../../media/Fig29_Greenfield_deployment_option.jpg)

> [!NOTE]
> O caminho de mídia ilustrado tem o bypass de mídia habilitado (a configuração recomendada). Se você optar por desabilitar bypass de mídia, o caminho de mídia é roteado por meio do servidor de mediação.

## <a name="pstn-gateway-deployment-options"></a>Opções de implantação de Gateway PSTN

### <a name="pstn-gateways"></a>Gateways PSTN

Os gateways telefônica pública comutada (PSTN) de rede são componentes de hardware de terceiros que convertem a sinalização e mídia entre a infraestrutura do Enterprise Voice e a PSTN, diretamente ou por meio de conexão para troncos SIP. Em qualquer topologia, o gateway finaliza a PSTN. O gateway seja isolado em sua própria sub-rede e está conectado à rede corporativa por meio do servidor de mediação.

Uma empresa com vários sites geralmente seria implantar um ou mais gateways em cada site. Sites de filiais podem se conectar à PSTN através de um gateway ou por meio de um aparelho de filial persistente, que combina o gateway e servidores em uma única caixa. Se os sites de filiais usam um gateway, um registrador e o servidor de mediação são necessárias no site, a menos que o link de WAN seja resiliente. Um ou mais servidores de mediação, que são colocadas em servidores Front-End, pode rotear as chamadas para as um ou mais gateways em cada site. É recomendável que o registrador, servidor de mediação e gateway necessárias no site são implantadas como um aparelho de filial persistente.

Determinar o número, tamanho e local dos gateways PSTN é talvez a decisão mais importante e cara que você deve tomar ao planejar sua infraestrutura do Enterprise Voice.

Aqui estão as principais perguntas a serem considerados. Tenha em mente que as respostas a essas perguntas são interdependentes tudo

- Quantos gateways PSTN são necessários? A resposta depende do número de usuários, o número previsto de chamadas simultâneas (carga de tráfego) e o número de sites (cada site precisa de um).

- Que tamanho os gateways devem ter? A resposta depende do número de usuários no local e a carga de tráfego.

- Onde os gateways devem ser localizados? A resposta depende em parte na topologia e em parte da distribuição geográfica de sua organização.

  Você também deve considerar seu gateway opções de topologia (para obter detalhes, consulte topologias de Gateway posteriormente neste tópico).

#### <a name="mn-trunk-support"></a>Suporte de Tronco M:N

Os servidores de mediação pode rotear chamadas através de vários gateways, controladores de borda de sessão (SBCs) fornecidas por provedores de serviços de telefonia de Internet ou uma combinação dos dois. Além disso, vários servidores de mediação no pool podem interagir com diversos gateways. A rota lógica definida entre um servidor de mediação e gateway é chamada de um tronco. Quando um usuário interno faz uma chamada PSTN, a lógica de roteamento de saída no pool de Front-End escolhe qual tronco para roteamento sobre todas as combinações possíveis que podem estar disponíveis para roteamento de chamada específica. Com o balanceamento de carga do DNS, se uma chamada não alcançarem um gateway devido a um problema com um determinado servidor de mediação no pool, a chamada será repetida a um servidor de mediação alternativo no pool.

Para obter detalhes sobre o planejamento de vários gateways, consulte [tronco M:N no Skype para Business Server](m-n-trunk.md).

Para obter detalhes sobre outros aprimoramentos de roteamento de saída, consulte [Call Routes](https://technet.microsoft.com/library/a2ddf327-2ec4-407b-af0f-276f2b13eefd.aspx).

#### <a name="gateway-topologies"></a>Topologias de gateway

Ao considerar as perguntas fundamentais da implantação de gateway, siga estas etapas:

1. Conte os sites no qual você deseja fornecer conectividade PSTN usando o Enterprise Voice.

2. Estime o tráfego de cada site (número de usuários) e o número médio de chamadas por hora por usuário.

3. Implante um ou mais gateways em cada local para manipular o tráfego antecipado.

Nessa topologia, chamadas entre os funcionários em cada site e entre os sites são todos roteadas pela intranet. Chamadas para o PSTN são roteadas pela rede IP corporativa para os gateways mais próximos da localização dos números de destino. Mas e se sua organização suporta dezenas ou centenas ou até mesmo milhares de locais espalham por um ou mais continentes, como muitas instituições financeiras e outras empresas de grandes porte? Nesses casos, não é prático implantar um gateway separado em cada site.

Para resolver esse problema, muitas empresas grandes preferem implantar um ou alguns sites centrais de telefonia de grande porte.

Nessa topologia, vários gateways grandes, suficientes para acomodar a carga de usuários prevista são implantados em cada site central. Todas as chamadas para os usuários da empresa são encaminhadas pelo provedor de serviços de telefone da empresa a um site central. Lógica de roteamento no site central determina se a chamada deve ser roteada pela intranet ou para a PSTN.

#### <a name="gateway-location"></a>Localização dos gateways

Localização dos gateways também pode determinar os tipos de gateways que você escolher e como eles são configurados. Há vários protocolos de PSTN, sendo que nenhum deles constitui um padrão mundial. Se todos os seus gateways estiverem localizados em um único país/região, isso não é um problema, mas se você localizar gateways em vários países/regiões, cada um deve ser configurado de acordo com os padrões PSTN de país/região. Além disso, os gateways certificados para operação no, por exemplo, Canadá, não podem ser certificados na Índia, no Brasil ou na União Europeia.

#### <a name="gateway-size-and-number"></a>Número e tamanho de gateway

Os gateways PSTN que a maioria das organizações considera para implantação variam em tamanho de 2 a 960 portas. (Há gateways até maiores, mas esses são usados principalmente pelos provedores de serviços de telefone). Ao estimar o número de portas que necessárias para sua organização, use as seguintes diretrizes:

- Organizações com o uso de pouco uso do telefone (uma chamada PSTN por usuário por hora) devem alocar uma porta para cada 15 usuários. Por exemplo, se você tiver 20 usuários, você precisará de um gateway com duas portas.

- Organizações com o uso de uso moderado do telefone (duas chamadas PSTN por usuário por hora) devem alocar uma porta para cada 10 usuários. Por exemplo, se você tiver 100 usuários, você precisará de um total de 10 portas alocadas entre um ou mais gateways.

- Organizações com o uso de uso intenso do telefone (três ou mais chamadas PSTN por usuário por hora) devem alocar uma porta para cada cinco usuários. Por exemplo, se você tiver 47.000 usuários, você precisará de um total de 9.400 portas alocadas entre pelo menos 10 gateways de grande porte.

- Portas adicionais podem ser adquiridas como o número de usuários ou quantidade de tráfego em sua organização aumenta.

Para qualquer dado número de usuários que precisa suportar, você tem a opção de implantar gateways de menos, maiores ou menores. Como regra, é recomendável manter a disponibilidade se um gateway falhar um mínimo de dois gateways para uma organização.

Cada gateway PSTN implantado deve ter pelo menos um servidor de mediação correspondente.


