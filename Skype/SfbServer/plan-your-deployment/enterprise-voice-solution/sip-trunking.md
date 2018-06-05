---
title: Tronco SIP no Skype for Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: Saiba mais sobre o tronco SIP no Skype para Business Server Enterprise Voice
ms.openlocfilehash: 01f8401f6573220c8995df99f863bfd95a08ffb8
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19504100"
---
# <a name="sip-trunking-in-skype-for-business-server-2015"></a>Tronco SIP no Skype for Business Server 2015
 
Saiba mais sobre o tronco SIP no Skype para Business Server Enterprise Voice
  
O SIP é usado para iniciar e gerenciar sessões de comunicações de VoIP para o serviço telefônico básico e para vários serviços de comunicação em tempo real adicionais, como sistema de mensagens instantâneas, conferência, detecção de presença e multimídia. Esta seção fornece informações de planejamento para a implementação de troncos SIP, um tipo de conexão SIP que ultrapassa o limite de sua rede local.
  
## <a name="what-is-sip-trunking"></a>O que é o tronco SIP?

Um tronco SIP é uma conexão do IP estabelece um vínculo de comunicações SIP entre sua organização e um provedor de serviços de telefonia de Internet (ITSP), além do firewall. Normalmente, um tronco SIP é usado para conectar o site central da sua organização para um ITSP. Em alguns casos, você também pode optar por usar um tronco SIP para conectar a filial a um ITSP.
  
Implantando um tronco SIP pode ser um grande passo na direção simplificando telecomunicações da sua organização e preparação para melhorias atualizadas para comunicação em tempo real. Uma das principais vantagens do tronco SIP é que você pode consolidar conexões da sua organização para a rede telefônica pública comutada (PSTN) em um site central, em vez de seu predecessor, tempo divisão TDM (multiplexação por) tronco, que normalmente requer um tronco separado de cada site de filial.
  
### <a name="cost-savings"></a>Redução de custo

As reduções de custo associadas ao tronco SIP podem ser substanciais:
  
- Geralmente, as chamadas de longa distância custam menos através de um tronco SIP.
    
- Você pode cortar os custos de gerenciamento e reduzir a complexidade da implementação.
    
- A interface de tarifa básica (BRI) e a interface de tarifa primária (PRI) podem ser eliminadas se você conectar um tronco SIP diretamente ao ITSP, por um custo significativamente inferior. Nos troncos TDM, os provedores de serviço cobram as chamadas por minuto. O custo do tronco SIP pode ser baseado no uso da largura de banda, e você pode comprar incrementos menores e mais econômicos. (O custo real depende do modelo de serviço do que você escolhe).
    
#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>Tronco SIP vs. hospedagem de um gateway PSTN ou IP-PBX

Uma vez que os troncos SIP se conectam diretamente ao provedor de serviço, você pode eliminar os seus gateways PSTN e seu custo de gerenciamento e complexidade. O uso de um tronco SIP pode levar a cortes substanciais no custo, através da manutenção e administração reduzida. 
  
### <a name="expanded-voip-services"></a>Serviços de VoIP expandidos

Os recursos de voz são frequentemente a principal motivação para implantar o tronco SIP, mas o suporte de voz é apenas a primeira etapa. Troncos SIP, você pode estender os recursos de VoIP e habilitar Skype para Business Server fornecer um conjunto avançado de serviços. Por exemplo:
  
- Detecção de presença avançada para dispositivos que não estejam executando o Skype para Business Server pode oferecer melhor integração com telefones móveis, permitindo ver quando um usuário está em uma chamada de telefone celular.
    
- As chamadas de emergência E9-1-1 permite que as autoridades que atender a 911 chamadas determinem a localização do chamador do seu número de telefone.
    
> [!NOTE]
> Consulte o ITSP para obter uma lista de serviços que eles suportam e podem habilitar para sua organização. 
  
### <a name="sip-trunks-vs-direct-sip-connections"></a>Troncos SIP vs. conexões SIP diretas

O tronco termo é derivado da tecnologia de comutação por circuito. Ele se refere a uma linha física dedicada que conecta o equipamento de comutação telefônica. Como seu predecessor, troncos (TDM), a multiplexação de divisão de tempo troncos SIP são conexões entre duas redes separadas de SIP — o Skype Enterprise Business Server e o ITSP. Diferentemente dos troncos em circuitos comutados, os troncos SIP são conexões virtuais que podem ser estabelecidas em qualquer tipo de conexão de tronco SIP compatível.
  
As conexões SIP diretas, por outro lado, são conexões SIP que não cruzam o limite de rede local (ou seja, elas se conectam a um gateway PSTN (Rede Telefônica Pública Comutada) ou PBX dentro de sua rede interna). Para obter detalhes sobre como você pode usar conexões SIP diretas com Skype para Business Server, consulte [Direct SIP connections na Skype para Business Server 2015](direct-sip.md). 
  
## <a name="how-do-i-implement-sip-trunking"></a>Como implemento o tronco SIP?

Para implementar o tronco SIP, você deve rotear a conexão através de um servidor de mediação, que atua como um proxy para sessões de comunicação entre o Skype para clientes Business Server e o provedor de serviço e mídia de transcodificação, quando necessário.
  
Cada servidor de mediação tem uma interface de rede interna e uma interface de rede externa. A interface interna se conecta a servidores Front-End. A interface externa é geralmente denominada a interface do gateway, porque ele foi tradicionalmente usado para conectar o servidor de mediação para um gateway PSTN (rede) telefônica comutada pública ou um IP-PBX. Para implementar um tronco SIP, você pode conectar a interface externa do servidor de mediação ao componente de borda externa do ITSP. O componente de borda externa do ITSP pode ser um SBC (Controlador de Borda da Sessão), um roteador ou um gateway.
  
Para obter detalhes sobre servidores de mediação, consulte [componente de servidor de mediação em Skype para Business Server 2015](mediation-server.md). 
  
### <a name="centralized-vs-distributed-sip-trunking"></a>Tronco SIP centralizado versus distribuído

Um tronco SIP centralizado roteia todo o tráfego de VoIP, incluindo o tráfego de site de filial, por meio do seu site central. O modelo de implantação centralizada é simples, de forma econômica e geralmente é a abordagem recomendada para a implementação de troncos SIP com Skype para Business Server.
  
Tronco SIP distribuído é um modelo de implantação na qual você implementar locais troncos SIP em um ou mais sites de filiais. Tráfego de VoIP, em seguida, é encaminhado do site da filial diretamente a um provedor de serviço sem precisar passar por site central.
  
O tronco SIP distribuído é necessário somente nos seguintes casos: 
  
- O site de filial requer conectividade de telefone persistente (por exemplo, se WAN cair). Esse requisito deve ser analisado em cada site de filial; algumas das suas ramificações podem exigir a redundância e failover, enquanto outros podem não ter.
    
- Resiliência é necessária entre dois sites central. Você deve certificar-se de que um tronco SIP finaliza em cada site central. Por exemplo, se você tiver Dublin e Tukwila sites centrais e ambos usam o tronco SIP de apenas um site, se o tronco cair, os outros usuários do site não podem fazer chamadas PSTN.
    
- O site de filial e o site central são em diferentes países/regiões. Por motivos legais e de compatibilidade, você precisa de pelo menos um tronco SIP por país/região. Por exemplo, na União Europeia, as comunicações não podem deixar um país/região sem terminarem localmente em um ponto centralizado.
    
Dependendo da localização geográfica de sites e a quantidade de tráfego previsto dentro de sua empresa, você não deseja rotear todos os usuários através do tronco SIP central ou você pode optar por rotear alguns usuários por meio de um tronco SIP no seu site de filial. Para analisar suas necessidades, responda às seguintes perguntas:
  
- Qual é o tamanho cada site (ou seja, quantos usuários estão habilitados para o Enterprise Voice)? 
    
- Quais números DID (discagem direta interna) em cada local recebem a maioria das chamadas? 
    
A decisão de implantar um tronco SIP centralizado ou distribuído exige uma análise de custo-benefício. Em alguns casos, pode ser vantajoso optar pelo modelo de implantação distribuído mesmo se ele não for necessário. Em uma implantação centralizada completamente, todo o tráfego de site de filial é roteado em links de WAN. Em vez de pagar pela largura de banda necessária ao link de WAN, convém usar o tronco SIP distribuído. Por exemplo, talvez você queira implantar um servidor Standard Edition em um site de filial com federação para o site central, ou talvez você queira implantar um aparelho de filial persistente ou um servidor de filial persistente com um gateway pequeno.
  
> [!NOTE]
> Para obter detalhes sobre tronco SIP distribuído, consulte [tronco SIP de site de filial em Skype para Business Server 2015](branch-site.md). 
  
### <a name="supported-sip-trunking-connection-types"></a>Tipos de conexão de tronco SIP suportadas

Skype para Business Server suporta os seguintes tipos de conexão para tronco SIP:
  
- O MPLS é uma rede privada que direciona e transporta dados de um nó de rede para o próximo. A largura de banda em uma rede MPLS é compartilhada com outros assinantes, e cada pacote de dados é atribuído um rótulo a diferenciar os dados do assinante de um do outro. Esse tipo de conexão não exige VPN (rede virtual privada). Uma possível desvantagem é que o tráfego IP excessivo pode interferir na operação de VoIP, a menos que o tráfego VoIP tenha prioridade.
    
- Uma conexão privada sem outro tráfego, por exemplo, uma conexão de fibra ótica concedida ou uma linha T1, é normalmente o tipo de conexão mais confiável e seguro. Esse tipo de conexão oferece a maior capacidade de realização de chamadas, mas é geralmente o mais caro. Não é necessário VPN. As conexões privadas são adequadas para organizações com alto volume de chamadas ou com requisitos de segurança e disponibilidade rígidos.
    
- A Internet é o tipo de conexão menos caro, mas também o menos confiável. Conexão de Internet é a única Skype para SIP do servidor de negócios tronco conexão tipo que exige a VPN.
    
#### <a name="selecting-a-connection-type"></a>Selecionando um tipo de conexão

O tipo de conexão de tronco SIP mais apropriado para sua empresa depende de suas necessidades e de seu orçamento.
  
- Para uma empresa de médio ou grande porte, uma rede MPLS normalmente fornece o maior valor. Ela pode fornecer a largura de banda necessária por uma taxa mais barata do que uma rede privada especializada.
    
- Empresas de grande porte podem exigir uma conexão de fibra ótica, T1, T3 ou superior privada (E1, E3 ou superior na União Europeia).
    
- Para uma pequena empresa ou de site de filial com o volume de chamadas de baixa, o tronco SIP através da Internet, pode ser a melhor opção. Esse tipo de conexão não é recomendado para locais de médio ou grande porte.
    
### <a name="bandwidth-requirements"></a>Requisitos de largura de banda

A quantidade de largura de banda exigida pela sua implementação depende da capacidade da chamada (o número de chamadas simultâneas que você precisa suportar). A disponibilidade de largura de banda precisa ser levada em consideração para que você possa aproveitar ao máximo a capacidade de pico pela qual pagou. Use a fórmula a seguir para calcular o requisito de largura de banda de pico do tronco SIP:
  
Largura de banda de pico do tronco SIP = máximo de chamadas simultâneas x (64 kbps + tamanho do cabeçalho)
  
> [!NOTE]
> O tamanho do cabeçalho é de 20 bytes no máximo. 
  
### <a name="codec-support"></a>Suporte ao codec

Skype para Business Server suporta apenas os seguintes codecs:
  
- G.711 a-law (usado principalmente fora da América do Norte)
    
- G.711 µ-law (usado na América do Norte)
    
### <a name="internet-telephony-service-provider"></a>Provedor de Serviço de Telefonia pela Internet

O modo de implementação do lado do provedor de serviços de uma conexão de tronco SIP varia de um ITSP para outro. Para obter informações de implantação, contate seu provedor de serviços. Para obter uma lista de provedores de serviços de tronco SIP certificados, consulte o [site da Microsoft Unified Communications programa de interoperabilidade aberta](https://go.microsoft.com/fwlink/p/?LinkId=287029).
  
Para obter detalhes sobre os provedores de tronco SIP certificado pela Microsoft, entre em contato com seu representante da Microsoft.
  
> [!IMPORTANT]
> Você deve usar um provedor de serviço certificado pela Microsoft para garantir que seu ITSP suporte todas as funcionalidades que atravessam o tronco SIP (por exemplo, configurar e gerenciar sessões e suportar todos os serviços de VoIP estendido). O suporte técnico da Microsoft não estender as configurações que usam provedores não certificados. Se você atualmente usa um provedor de serviço Internet não certificado para tronco SIP, é possível optar por continuar usando este provedor como seu ISP e usar um provedor certificado pela Microsoft para tronco SIP. 
  
### <a name="topologies-and-components-for-sip-trunking"></a>Topologias e componentes do tronco SIP

A figura a seguir ilustra a topologia de tronco SIP no Skype para Business Server.
  
**Topologia de tronco SIP**

![Topologia de tronco SIP](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)
  
Conforme mostra o diagrama, uma VPN (rede virtual privada) IP é usada para a conectividade entre a rede corporativa e o provedor de serviços da rede de telefonia pública comutada (PSTN). O objetivo desta rede privada é fornecer conectividade IP, aprimorar a segurança e (opcionalmente) obter garantias de qualidade de serviços (QoS). Devido à natureza de uma VPN, não é necessário usar protocolo TLS para o tráfego de sinalização SIP ou SRTP para tráfego de mídia.  As conexões entre a empresa e o provedor de serviços consistem, portanto, em conexões TCP básicas para SIP e RTP básico (via protocolo UDP) em mídia encapsulada através de uma VPN IP. Certifique-se de que todos os firewalls entre os roteadores VPN possuem portas abertas para permitir a comunicação e que os endereços IP nas bordas externas dos roteadores VPN sejam roteáveis publicamente.
  
> [!IMPORTANT]
> Contate seu provedor de serviços para determinar se ele oferece suporte para alta disponibilidade, incluindo failover. Em caso positivo, você precisará determinar os procedimentos para configurá-lo. Por exemplo, você precisa configurar apenas um endereço IP e um tronco SIP em cada servidor de mediação, ou você precisa configurar vários troncos SIP em cada servidor de mediação? > Se você tiver vários sites centrais, pergunte também se o provedor de serviço tem a capacidade de habilitar conexões para e de outro site central. 
  
> [!NOTE]
> Para o tronco SIP, é altamente recomendável que você implante servidores de mediação autônomo. Para obter detalhes, consulte [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) na documentação de implantação.
  
### <a name="securing-the-mediation-server-for-sip-trunking"></a>Como proteger o Servidor de Mediação para troncos SIP

Para fins de segurança, você deve configurar uma LAN virtual (VLAN) para cada conexão entre os dois roteadores VPN. O processo real para configurar uma VLAN varia de um fabricante de roteador para outro. Para detalhes, entre em contato com o fornecedor do seu roteador.
  
É recomendável seguir estas diretrizes:
  
- Configure um virtual LAN (VLAN) entre o servidor de mediação e o roteador VPN na rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada).
    
- Não permita que pacotes de transmissão ou multicast sejam transferidos do roteador para a VLAN.
    
- Bloqueie quaisquer regras de roteamento que direcionem o tráfego do roteador para qualquer lugar, mas o servidor de mediação.
    
Se você usa um servidor VPN, é recomendável seguir as seguintes diretrizes:
  
- Configure uma VLAN entre o servidor VPN e o servidor de mediação.
    
- Não permita que pacotes de transmissão ou multicast sejam transferidos do servidor VPN para a VLAN.
    
- Bloqueie qualquer regra de roteamento que roteia o tráfego do servidor VPN para qualquer lugar, mas o servidor de mediação.
    
- Criptografe dados na VPN usando GRE (encapsulamento de roteamento genérico).
    
## <a name="see-also"></a>Consulte também

[Tronco Branch site SIP no Skype para Business Server 2015](branch-site.md)