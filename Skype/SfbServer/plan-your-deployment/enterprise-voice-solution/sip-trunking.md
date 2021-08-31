---
title: Tronco SIP em Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Saiba mais sobre tronco SIP no Skype for Business Server Enterprise Voice
ms.openlocfilehash: d10f14a8c3f65309c52351a0721aa042faad47b6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728230"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>Tronco SIP em Skype for Business Server

Saiba mais sobre tronco SIP no Skype for Business Server Enterprise Voice

O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP (voz sobre IP) para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como serviços de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção oferece informações de planejamento para a implementação de troncos SIP, um tipo de conexão SIP que se estende além do limite da rede local.

## <a name="what-is-sip-trunking"></a>O que é o tronco SIP?

Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o site central da sua organização a um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar o site da filial a um ITSP.

A implantação de tronco SIP pode ser um grande passo para simplificar as telecomunicações da sua organização e preparar melhorias atualizadas para comunicações em tempo real. Uma das principais vantagens do tronco SIP é que você pode consolidar as conexões da sua organização com a PSTN (rede telefônica pública comutado) em um site central, em vez de seu tronco TDM (multiplexação de divisão de tempo) predecessor, que normalmente requer um tronco separado de cada site de filial.

### <a name="cost-savings"></a>Redução de custo

As reduções de custo associadas ao tronco SIP podem ser substanciais:

- Geralmente, as chamadas de longa distância custam menos através de um tronco SIP.

- Você pode cortar os custos de gerenciamento e reduzir a complexidade da implementação.

- A interface de tarifa básica (BRI) e a interface de tarifa primária (PRI) podem ser eliminadas se você conectar um tronco SIP diretamente ao ITSP, por um custo significativamente inferior. Nos troncos TDM, os provedores de serviço cobram as chamadas por minuto. O custo do tronco SIP pode ser baseado no uso da largura de banda, e você pode comprar incrementos menores e mais econômicos. (O custo real depende do modelo de serviço do que você escolhe).

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Tronco SIP versus hospedagem de um gateway PSTN ou IP-PBX

Uma vez que os troncos SIP se conectam diretamente ao provedor de serviço, você pode eliminar os seus gateways PSTN e seu custo de gerenciamento e complexidade. O uso de um tronco SIP pode levar a cortes substanciais no custo, através da manutenção e administração reduzida.

### <a name="expanded-voip-services"></a>Serviços de VoIP expandidos

Os recursos de voz são frequentemente o principal motivo para implantar o tronco SIP, mas o suporte de voz é apenas a primeira etapa. Com o tronco SIP, você pode estender os recursos VoIP e permitir Skype for Business Server fornecer um conjunto mais rico de serviços. Por exemplo:

- A detecção de presença aprimorada para dispositivos que não estão executando Skype for Business Server pode oferecer melhor integração com telefones celulares, permitindo que você veja quando um usuário está em uma chamada de telefone celular.

- A chamada de emergência do E9-1-1 permite que as autoridades que atendam às chamadas do 911 determinem a localização do chamador a partir de seu número de telefone.

> [!NOTE]
> Consulte o ITSP para obter uma lista de serviços que eles suportam e podem habilitar para sua organização.

### <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP vs. Conexões diretas do cabo SIP

O termo tronco  deriva da tecnologia de comutação de circuitos. Refere-se a uma linha física dedicada que conecta o equipamento de comutação telefônica. Assim como seu predecessor, troncos TDM (multiplexação de divisão de tempo), os troncos SIP são conexões entre duas redes SIP separadas, o Skype for Business Server enterprise e o ITSP. Diferentemente dos troncos de comutação de circuitos, os troncos SIP são conexões virtuais que podem ser estabelecidas sobre qualquer tipo de conexão de troncos SIP compatíveis.

As conexões SIP diretas, por outro lado, são conexões de SIP que não atravessam o limite de rede local (ou seja, elas se conectam a um gateway PSTN ou PBX dentro de sua rede interna). Para obter detalhes sobre como você pode usar conexões SIP diretas com Skype for Business Server, consulte [Direct SIP connections in Skype for Business Server](direct-sip.md).

## <a name="how-do-i-implement-sip-trunking"></a>Como implementar tronco SIP?

Para implementar o tronco SIP, você deve rotear a conexão por meio de um Servidor de Mediação, que atua como um proxy para sessões de comunicação entre clientes Skype for Business Server e o provedor de serviços e transcodifica mídia, quando necessário.

Cada Servidor de Mediação tem uma interface de rede interna e uma interface de rede externa. A interface interna se conecta aos Servidores Front-End. A interface externa é comumente chamada de interface de gateway porque tradicionalmente foi usada para conectar o Servidor de Mediação a um gateway PSTN (rede telefônica pública comutado) ou a um IP-PBX. Para implementar um tronco SIP, você conecta a interface externa do Servidor de Mediação ao componente de borda externa do ITSP. O componente de borda externa do ITSP pode ser um SBC (controlador de borda da sessão), um roteador ou um gateway.

Para obter detalhes sobre servidores de mediação, consulte [Componente do Servidor de Mediação em Skype for Business Server](mediation-server.md).

### <a name="centralized-vs-distributed-sip-trunking"></a>Tronco SIP centralizado versus distribuído

O tronco SIP centralizado encaminha todo o tráfego VoIP, incluindo o tráfego de site de filial, por meio de seu site central. O modelo de implantação centralizado é simples, econômico e geralmente é a abordagem recomendada para implementar troncos SIP com Skype for Business Server.

Tronco SIP distribuído é um modelo de implantação no qual você implementa troncos SIP locais em um ou mais sites de filial. O tráfego VoIP é então roteado do site de filial diretamente para um provedor de serviços sem passar pelo site central.

O tronco SIP distribuído é exigido somente nos seguintes casos:

- O site de filial requer conectividade de telefone de sobrevivência (por exemplo, se a WAN cair). Esse requisito deve ser analisado para cada site de filial; alguns de seus ramais podem exigir redundância e failover, enquanto outros podem não.

- A resiliência é necessária entre dois sites centrais. Você precisa garantir que um tronco SIP seja encerrado em cada site central. Por exemplo, se você tiver sites centrais dublin e Tukwila e ambos usarem apenas o tronco SIP de um site, se o tronco cair, os usuários do outro site não poderão fazer chamadas PSTN.

- O site de filial e o site central estão em diferentes países/regiões. Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região. Por exemplo, na União Europeia, as comunicações não podem deixar um país/região sem serem terminarem localmente em um ponto centralizado.

Dependendo da localização geográfica dos sites e do tráfego antecipado em sua empresa, talvez você não queira rotear todos os usuários pelo tronco SIP central ou pode optar por encaminhar alguns usuários por meio de um tronco SIP em seu site de filial. Para analisar suas necessidades, responda às seguintes perguntas:

- Qual é o tamanho de cada site (ou seja, quantos usuários estão habilitados para Enterprise Voice)?

- Quais números DID (discagem direta interna) em cada site recebem a maioria das chamadas?

A decisão sobre implantar um tronco SIP centralizado ou distribuído exige uma análise com bom custo benefício. Em alguns casos, pode ser vantajoso optar pelo modelo de implantação distribuído mesmo se não for necessário. Em uma implantação completamente centralizada, todo o tráfego de site de filial é roteado por links WAN. Em vez de pagar pela largura de banda exigida pelo link de WAN, convém usar o tronco SIP distribuído. Por exemplo, talvez você queira implantar um servidor Edição Standard em um site de filial com federação para o site central, ou talvez você queira implantar um Aparelho de Filial Desavivável ou um Servidor de FilialVivível com um gateway pequeno.

> [!NOTE]
> Para obter detalhes sobre o tronco SIP distribuído, consulte [Tronco SIP de site](branch-site.md)de filial em Skype for Business Server .

### <a name="supported-sip-trunking-connection-types"></a>Tipos de conexão de tronco SIP suportadas

Skype for Business Server dá suporte aos seguintes tipos de conexão para tronco SIP:

- MPLS (Multiprotocol Label Switching) é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes e cada pacote de dados recebe um rótulo para distinguir os dados de um assinante dos de outro. Esse tipo de conexão não exige VPN. Uma possível desvantagem é que o tráfego IP excessivo pode interferir com a operação VoIP, a menos que o tráfego VoIP tenha prioridade.

- Uma conexão privada sem outro tráfego—por exemplo, uma conexão de fibra ótica arrendada ou linha T1—é normalmente o tipo de conexão mais confiável e segura (por exemplo, uma conexão de fibra óptica. Este tipo de conexão oferece a maior capacidade de realização de chamadas, mas é geralmente o mais caro. VPN não é necessário. Conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.

- A Internet é o tipo de conexão menos caro, mas também o menos confiável. A conexão com a Internet é o único tipo Skype for Business Server de conexão SIP que requer VPN.

#### <a name="selecting-a-connection-type"></a>Selecionando um tipo de conexão

O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.

- Para uma empresa de médio ou grande porte, uma rede MPLS normalmente fornece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.

- Empresas de grande porte podem exigir uma conexão de fibra ótica T1, T3 ou superior (E1, E3 ou superior na União Europeia).

- Para uma pequena empresa ou site de filial com baixo volume de chamada, o tronco SIP pela Internet pode ser a melhor opção. Esse tipo de conexão não é recomendado para sites de médio ou grande porte.

### <a name="bandwidth-requirements"></a>Requisitos de largura de banda

A quantidade de largura de banda exigida pela sua implementação depende da capacidade da chamada (o número de chamadas simultâneas que você precisa suportar). A disponibilidade de largura de banda precisa ser levada em consideração para que você possa aproveitar ao máximo a capacidade de pico pela qual pagou. Use a fórmula a seguir para calcular o requisito de largura de banda de pico do tronco SIP:

Largura de banda de pico do tronco SIP = máximo de chamadas simultâneas x (64 kbps + tamanho do cabeçalho)

> [!NOTE]
> O tamanho do cabeçalho é de 20 bytes no máximo.

### <a name="codec-support"></a>Suporte ao codec

Skype for Business Server dá suporte apenas aos seguintes codecs:

- G.711 a-law (usado principalmente fora da América do Norte)

- G.711 µ-law (usado na América do Norte)

### <a name="internet-telephony-service-provider"></a>Provedor de Serviço de Telefonia pela Internet

Como você implementa o lado do provedor de serviço de uma conexão de tronco SIP varia de um ITSP para outro. Para obter informações de implantação, entre em contato com o seu provedor de serviços. Para ver uma lista de provedores de serviços de tronco SIP certificados, consulte o site do Programa de Interoperabilidade Aberta de Comunicações [Unificadas da Microsoft.](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)

Para obter detalhes sobre os provedores de tronco SIP certificado pela Microsoft, entre em contato com seu representante da Microsoft.

> [!IMPORTANT]
> Você deve usar um provedor de serviço certificado pela Microsoft para garantir que seu ITSP suporte todas as funcionalidades que atravessam o tronco SIP (por exemplo, configurar e gerenciar sessões e suportar todos os serviços de VoIP estendido). O suporte técnico da Microsoft não estender as configurações que usam provedores não certificados. Se você atualmente usa um provedor de serviço Internet não certificado para tronco SIP, é possível optar por continuar usando este provedor como seu ISP e usar um provedor certificado pela Microsoft para tronco SIP.

### <a name="topologies-and-components-for-sip-trunking"></a>Topologias e componentes para tronco SIP

A figura a seguir mostra a topologia de tronco SIP em Skype for Business Server.

**Topologia de tronco SIP**

![Topologia de Tronco SIP.](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

Conforme mostrado no diagrama, uma VPN (rede privada virtual ip) é usada para conectividade entre a rede corporativa e o provedor de serviço PSTN (rede telefônica pública comutado). O objetivo dessa rede privada é fornecer conectividade IP, aumentar a segurança e (opcionalmente) obter garantias de QoS (Qualidade de Serviço). Devido à natureza de uma VPN, você não precisa usar o TLS (Transport Layer Security) para tráfego de sinalização SIP ou o PROTOCOLO DE TRANSPORTE seguro em tempo real (SRTP) para o tráfego de mídia. As conexões entre a empresa e o provedor de serviços consistem, portanto, em conexões TCP simples para SIP e RTP (protocolo de transporte em tempo real) (sobre UDP) para mídia túnel por meio de uma VPN IP. Certifique-se de que todos os firewalls entre os roteadores VPN tenham portas abertas para permitir que os roteadores VPN se comuniquem e que os endereços IP nas bordas externas dos roteadores VPN sejam publicamente instável.

> [!IMPORTANT]
> Entre em contato com seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover. Em caso afirmativos, você precisará determinar os procedimentos para a configuração. Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada Servidor de Mediação ou você precisa configurar vários troncos SIP em cada Servidor de Mediação? > Se você tiver vários sites centrais, pergunte também se o provedor de serviços tem a capacidade de habilitar conexões de e para outro site central.

> [!NOTE]
> Para tronco SIP, recomendamos que você implante Servidores de Mediação autônomos. Para obter detalhes, [consulte Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) na documentação de Implantação.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>Proteger o Servidor de Mediação para Tronco SIP

Para fins de segurança, você deve configurar uma LAN virtual (VLAN) para cada conexão entre os dois roteadores VPN. O processo real para configurar uma VLAN varia de um fabricante de roteador para outro. Para obter detalhes, entre em contato com o fornecedor do roteador.

Recomendamos que você siga estas diretrizes:

- Configurar uma LAN virtual (VLAN) entre o Servidor de Mediação e o roteador VPN na rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede com tela).

- Não permita que pacotes de transmissão ou multicast sejam transferidos do roteador para a VLAN.

- Bloqueie quaisquer regras de roteamento que roteiem o tráfego do roteador para qualquer lugar, menos o Servidor de Mediação.

Se você usar um servidor VPN, recomendamos que você siga estas diretrizes:

- Configurar uma VLAN entre o servidor VPN e o Servidor de Mediação.

- Não permita que pacotes de transmissão ou multicast sejam transmitidos do servidor VPN para a VLAN.

- Bloqueie qualquer regra de roteamento que encaminhe o tráfego de servidor VPN para qualquer lugar, menos o Servidor de Mediação.

- Criptografe dados na VPN usando o encapsulamento de roteamento genérico (GRE).

## <a name="see-also"></a>Confira também

[Tronco SIP de site de filial no Skype for Business Server](branch-site.md)