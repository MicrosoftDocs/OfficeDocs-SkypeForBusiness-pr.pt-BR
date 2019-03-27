---
title: Requisitos de balanceamento de carga para o Skype for Business
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumo: Revise a carga balanceamento considerações antes de implementar Skype para Business Server.'
ms.openlocfilehash: a7e8e70088c83276c36334c5d9a1e3be1538ca38
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897886"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos de balanceamento de carga para o Skype for Business
 
**Resumo:** Revise o considerações de balanceamento antes de implementar Skype para Business Server.
  
Balanceamento de carga distribui o tráfego entre os servidores em um pool. Se você tiver pools de Front-End, pools do servidor de mediação ou pools de servidor de borda, você precisará implantar o balanceamento de carga para esses pools.
  
Skype para Business Server suporta dois tipos de soluções para o tráfego de cliente-para-servidor de balanceamento de carga: frequentemente balanceamento (abreviados como HLB) de carga de hardware e balanceamento de carga de sistema de nome de domínio (DNS). A carga de DNS balanceamento oferece várias vantagens, incluindo a capacidade de isolar grande parte da sua Skype para tráfego de servidor de negócios de quaisquer possíveis problemas de Balanceador de carga de hardware, a solução de problemas mais eficiente e administração mais simples.
  
Decidir sozinho que solução de balanceamento de carga é apropriada para cada pool em sua implantação, mas tenha em mente as seguintes restrições: 
  
- A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.
    
- Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.
    
Se optar por usar o balanceamento de carga DNS para um pool, mas ainda for necessário implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada. Por exemplo, a configuração do balanceador de carga de hardware será mais simples, pois gerenciará somente os tráfegos HTTP e HTTPS, enquanto os demais protocolos serão gerenciados pelo balanceamento de carga DNS. Para obter detalhes, consulte [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para tráfego de servidor-para-servidor, Skype para Business Server usa o balanceamento de carga de reconhecimento de topologia. Os servidores leem a topologia publicada no repositório de gerenciamento Central para obter os FQDNs dos servidores na topologia e distribuam automaticamente o tráfego entre os servidores. Os administradores não precisam configurar nem gerenciar esse tipo de balanceamento de carga. 
  
Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos do balanceador de carga do hardware

O Skype para Business Server dimensionada consolidada de borda topologia é otimizada para o balanceamento de carga DNS para novas implantações federar principalmente com outras organizações que usam o Skype para Business Server ou o Lync Server. Se a alta disponibilidade é necessária para qualquer um dos seguintes cenários, um balanceador de carga de hardware deve ser usado em pools de servidor de borda para o seguinte: 
  
- Federação com organizações que usam o Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- UM do Exchange para usuários remotos que usam UM do Exchange antes do Exchange 2010 com SP1
    
- Conectividade para usuários públicos de mensagens instantâneas
    
> [!IMPORTANT]
> O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces. 
  
> [!NOTE]
> Se estiver usando um balanceador de carga de hardware, o balanceador de carga implantado para conexões com a rede interna deverá ser configurado para balancear apenas cargas do tráfego de servidores que executam o serviço de Borda de Acesso e o serviço de Borda A/V. Ele não poderá balancear a carga do tráfego do serviço interno de Borda de Webconferência ou do serviço interno de Proxy XMPP. 
  
> [!NOTE]
> Direct server return NAT do DSR () não é suportado com Skype para Business Server. 
  
Para determinar se seu balanceador de carga de hardware suporta os recursos exigidos pelo Skype para Business Server, consulte [infraestrutura para Skype para negócios](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de Borda A/V

Estes são os requisitos de Balanceador de carga de hardware para servidores de borda executando A / serviço de borda V:
  
- Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.
    
- Desative o nagling TCP para o intervalo de portas externas 50.000 – 59.999. 
    
- Não use NAT no firewall interno ou externo. 
    
- Interface interna da borda precisa estar em uma rede diferente a interface externa do servidor de borda e roteamento entre elas deve ser desabilitado. 
    
- A interface externa do servidor de borda executando A / V serviço de borda deve usar endereços IP publicamente roteáveis e não NAT ou conversão de porta em qualquer um dos endereços IP externos borda. 
    
- O balanceador de carga não pode trocar o endereço da fonte do cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Outros requisitos do balanceador de carga de Hardware

Requisitos de afinidade baseada em cookie são enormemente reduzidos no Skype para Business Server para serviços Web. Se você estiver implantando o Skype para Business Server e não manterão os pools de Front End Servers do Lync Server 2010 ou Front-End, persistência baseada em cookie não é necessário. No entanto, se você irá temporariamente ou reter de forma permanente quaisquer pools de Front-End ou de Front End Servers do Lync Server 2010, você ainda usar persistência baseada em cookie conforme ele é implantado e configurado para o Lync Server 2010. 
  
> [!NOTE]
> **Se decidir usar afinidade baseada em cookie mesmo que sua implantação não exija**, isso não causará um impacto negativo. 
  
Para implantações que **não usarão** afinidade baseada em cookie:
  
- No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.
    
Para implantações que **usarão** afinidade baseada em cookie:
  
- No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.
    
- O cookie do balanceador de carga de hardware NÃO DEVE ser marcado como httpOnly
    
- O cookie do balanceador de carga de hardware NÃO DEVE conter uma data de vencimento
    
- O cookie do balanceador de carga de hardware DEVE ser nomeado como **MS-WSMAN** (esse é o valor que o serviço Web espera e não pode ser alterado)
    
- O cookie do balanceador de carga de hardware DEVE ser definido em todas as respostas HTTP para as quais a solicitação HTTP recebida não contém um cookie, independentemente de uma resposta HTTP anterior na mesma conexão TCP já ter obtido um cookie. Se o balanceador de carga otimiza a inserção de cookie para apenas uma ocorrência por conexão TCP, essa otimização NÃO DEVE ser usada
    
> [!NOTE]
> Configurações de Balanceador de carga de hardware típica usam a afinidade do endereço de origem e um mínimo de 20 TCP ciclo de vida de sessão, que é bom para clientes do Lync Server e o Lync 2013, porque o estado de sessão é mantido por meio do uso do cliente e/ou e a interação do aplicativo. 
  
Se estiver implantando dispositivos móveis, o balanceador de carga de hardware deverá ser capaz de balancear a carga da solicitação individual em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!CAUTION]
> Se você estiver implantando os dispositivos móveis, o balanceador de carga de hardware deve ser capaz de carregar individualmente balancear a cada solicitação de uma conexão TCP. Os aplicativos móveis mais recentes do Apple iOS exigem a versão 1.2 do protocolo TLS.  
  
> [!CAUTION]
> Para obter detalhes sobre balanceadores de carga de hardware de terceiros, consulte [infraestrutura para Skype para negócios](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
A seguir, são apresentados os requisitos do balanceador de carga de hardware para serviços Web do pool de diretores e de front-end:
  
- Para VIPs de serviços Web internos, defina a persistência Source_addr (porta interna 80, 443) no balanceador de carga de hardware. Para Skype para Business Server, a persistência de Source_addr significa que várias conexões provenientes de um único endereço IP sempre são enviadas para um servidor para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre o proxy reverso e o balanceador de carga do pool de próximo salto hardware, criar uma regra para permitir o https: tráfego na porta 4443, de um proxy reverso para o hardware balanceador de carga. O balanceador de carga de hardware deve ser configurado para ouvir as portas 80, 443 e 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumo dos requisitos de afinidade do balanceador de carga de hardware

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (apenas para usuários externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (apenas para usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoramento de portas dos balanceadores de carga de hardware

Defina o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço de servidor Front-End (RTCSRV) parar porque o servidor Front-End ou Front End pool falha, o monitoramento de HLB deve também parar de receber tráfego dos serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte:
  
**Pool de usuário do servidor Front-End - Interface interna de HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>int_mco_443_vs da web  <br/> 443  <br/> |443  <br/> |Front-End  <br/> 5061  <br/> |Origem  <br/> |HTTPS  <br/> |
|\<pool\>int_mco_80_vs da web  <br/> 80  <br/> |80  <br/> |Front-End  <br/> 5061  <br/> |Origem  <br/> |HTTP  <br/> |
   
**Pool de usuário do servidor Front-End - Interface externa de HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

Skype para Business Server habilita DNS com carga balanceada, uma solução de software que pode reduzir significativamente a administração de sobrecarga de balanceamento de carga em sua rede. Balanceamento de carga DNS equilibra o tráfego de rede que seja exclusivo para Skype para Business Server, como o tráfego SIP e tráfego de mídia.
  
Se você implantar o balanceamento de carga do DNS, administração da sua organização sobrecarga de balanceadores de carga de hardware será minimizada. Além disso, solução de problemas complexos de problemas relacionados à configuração incorreta de balanceadores de carga para o tráfego SIP será eliminada. Você também pode impedir que as conexões de servidor para que você possa tirar servidores offline. Balanceamento de carga DNS também garante que problemas de Balanceador de carga de hardware não afetam elementos de tráfego SIP como o roteamento de chamada básica.

O diagrama a seguir mostra um exemplo que inclui tanto interna e balanceamento de carga de DNS externo: 
  
**Diagrama da rede de borda que usa endereços IPv4 públicos**

![exemplo de diagrama de rede do DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se você usar o balanceamento de carga do DNS, você também poderá adquirir balanceadores de carga de hardware de menor custo que se você usar os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar os balanceadores de carga que passaram qualificação de interoperabilidade o teste com Skype Business Server. Para obter detalhes sobre o teste de interoperabilidade do balanceador de carga, consulte [Parceiros de Balanceador de carga do Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). O seu conteúdo se aplica a Skype para Business Server.
  
Balanceamento de carga DNS é suportado para pools de Front-End, pools do servidor de borda, pools do diretor e pools de servidor de mediação autônomos.
  
Balanceamento de carga DNS é normalmente implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando o Skype para negócios), tenta se conectar a um servidor em um pool Estabelecendo conexão com um dos endereços IP retornados da consulta para o nome de domínio totalmente qualificado (FQDN) do pool de registrar o DNS A e AAAA (se for usado o endereçamento IPv6). 
  
Por exemplo, se houver três servidores de front-end em um pool chamado pool01. contoso.com, acontecerá o seguinte:
  
- Clientes executando o Skype para negócios consultam DNS para pool01. contoso.com. A consulta retorna os endereços de IP três e armazena em cache da seguinte maneira (não necessariamente na ordem):
    
    pool01. contoso.com 192.168.10.90
    
    pool01. contoso.com 192.168.10.91
    
    pool01. contoso.com 192.168.10.92
    
- O cliente tentará estabelecer uma conexão de protocolo de controle de transmissão (TCP) para um dos endereços IP. Se isso falhar, o cliente experimenta o próximo endereço IP no cache.
    
- Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.
    
- Se o cliente experimenta todas as entradas em cache sem uma conexão bem-sucedida, o usuário é notificado de que nenhum servidor executando o Skype para Business Server está disponível no momento.
    
> [!NOTE]
> Balanceamento de carga baseado em DNS é diferente do DNS round robin (DNS RR) que normalmente se refere ao balanceamento de carga aplicando depender do DNS para fornecer uma ordem diferente do IP endereços correspondente para os servidores em um pool. Geralmente RR DNS somente permite carregar distribuição, mas não habilitar o failover. Por exemplo, se a conexão para o um endereço IP retornado pelo DNS A e AAAA (se você estiver usando endereçamento IPv6) consulta falhar, a conexão falha. Portanto, o DNS round robin por si só é menos confiável que o balanceamento de carga baseado em DNS. Você pode usar o DNS balanceamento de carga round robin em conjunto com o DNS. 
  
Balanceamento de carga DNS é usado para o seguinte:
  
- Servidor-para-servidor SIP para os servidores de borda de balanceamento de carga
    
- Aplicativos de serviços de aplicativos de comunicação unificada (UCAS) como conferência automático Attendant, grupo de resposta e estacionamento de chamada de balanceamento de carga
    
- Impedindo novas conexões a aplicativos UCAS (também conhecido como "drenagem")
    
- Todo o tráfego cliente-para-servidor entre clientes e servidores de borda de balanceamento de carga
    
Balanceamento de carga DNS não pode ser usado para o seguinte:
  
- Tráfego web cliente-para-servidor para diretor ou servidores Front-End
    
Tráfego federado e de balanceamento de carga de DNS:
  
Se vários registros DNS forem retornados por uma consulta SRV de DNS, a borda de acesso, serviço selecionará sempre o SRV de DNS registre-se com a prioridade numérica mais baixa e o peso numérico mais alto. O Internet Engineering Task Force "Um RR DNS para especificar a localização dos serviços (DNS SRV)" de documento [RFC 2782, RR SRV de DNS](https://www.ietf.org/rfc/rfc2782.txt) Especifica que, se houver vários SRV de DNS registros definidos, prioridade é usada primeiro, depois de peso. Por exemplo, registro SRV de DNS uma tem ponderação de 20 e uma prioridade de 40 e o registro SRV de DNS B tem um peso de 10 e a prioridade de 50. Um registro de SRV de DNS com prioridade 40 será selecionado. As seguintes regras se aplicam à seleção de registro SRV de DNS:
  
- Prioridade é considerada pela primeira vez. Um cliente deve tentar contatar o host de destino definido pelo registro SRV de DNS com a mais baixa prioridade numerada pode alcançar. Destinos com a mesma prioridade devem ser tentados em uma ordem definida no campo de peso.
    
- O campo de peso Especifica uma importância relativa para entradas com a mesma prioridade. Maiores espessuras devem ser dada proporcionalmente maior probabilidade de ser selecionada. Os administradores de DNS devem usar o peso 0 quando não houver qualquer seleção de servidor para fazer. Na presença de registros que contenham espessuras maiores do que 0, os registros com peso 0 devem ter uma muito pequena chance de serem selecionados.
    
Se vários registros SRV de DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso selecionará o registro SRV que foi recebido pela primeira vez do servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>DNS com carga balanceada no diretor e Pools de Front-End Pools

Você pode usar para o tráfego SIP em pools de Front-End e pools de diretor de balanceamento de carga DNS. Com balanceamento de carga DNS implantado, você ainda precisará também usar balanceadores de carga de hardware para estes pools, mas somente para tráfego HTTPS de cliente-para-servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes em portas 443 e 80. 
  
Embora você ainda precisará balanceadores de carga de hardware para estes pools, sua configuração e administração será principalmente para tráfego HTTPS, que os administradores dos balanceadores de carga de hardware estão acostumados.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>DNS balanceamento de carga e suporte a clientes e servidores mais antigos

Failover automático de balanceamento suporta apenas para servidores que executam o Skype para Business Server ou o Lync Server 2010 e para o Lync 2013 e Skype para clientes de negócios de carga do DNS. Versões anteriores do Office Communications Server e de clientes ainda podem se conectar aos pools executando o balanceamento de carga DNS, mas se eles não podem fazer com que uma conexão para o primeiro servidor que balanceamento de carga DNS se refere a eles, eles não conseguem fazer failover para outro servidor no pool . 
  
Além disso, se você estiver usando UM do Exchange, você deve usar o mínimo do Exchange 2010 SP1 para obter suporte para Skype para balanceamento de carga de DNS do servidor de negócios. Se você usar uma versão anterior do Exchange, os usuários não terão os recursos de failover para esses cenários UM do Exchange:
  
- Reproduzir suas mensagens de voz do Enterprise no telefone dela
    
- Transferindo chamadas de um Exchange atendedor automático de UM
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implantando DNS com carga balanceada no diretor e Pools de Front-End Pools
<a name="BK_FE_Dir"> </a>

Implantando o DNS balanceamento de carga em pools de Front-End e pools do Diretor requer executar algumas etapas extras com os registros de DNS e FQDNs.
  
- Um pool que usa o balanceamento de carga DNS deve ter dois FQDNs: regular pool FQDN que é usada pelo DNS e balanceamento de carga (por exemplo, pool01. contoso.com), resolve para o IPs físico dos servidores no pool e outro FQDN Web do pool services (tais como web01.contoso.com), que se resolva como o endereço IP virtual do pool. 
    
    No construtor de topologia, se você deseja implantar o DNS com carga balanceada para um pool, para criar esse FQDN extra para serviços da Web do pool selecione a caixa de seleção **FQDN do pool de serviços Web internos de substituição** e digite os nomes FQDN, no **especificar as URLs do Web Services para Este Pool** página.
    
- Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (por exemplo, pool01. contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP de servidores que são implantados no momento.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de Front-End ou servidor Front-End os serviços Web externos FQDN deve ser exclusivo. Por exemplo, se você definir os serviços Web externos FQDN de um servidor Front-End como **pool01. contoso.com**, você não pode usar **pool01. contoso.com** para outro pool de Front-End ou servidor Front-End. Se você estiver implantando o diretores também, o external FQDN definido para qualquer Diretor de serviços da Web ou pool de diretores deve ser exclusivo de qualquer outro diretor ou diretor do pool, bem como qualquer pool Front-End ou servidor Front-End. Caso decida substituir os serviços web internos com um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, diretor ou um pool de diretores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>DNS com carga balanceada em Pools de servidor de borda
<a name="BK_Edge"> </a>

Você pode implantar o DNS com carga balanceada em pools de servidor de borda. Se fizer isso, você deve estar ciente dos algumas considerações.
  
Usando o DNS o balanceamento de carga em seus servidores de borda provoca uma perda da capacidade de failover nos seguintes cenários:
  
- Federação com organizações que estão executando versões do Skype para Business Server lançadas anteriormente para o Lync Server 2010.
    
- Troca de mensagens instantâneas com usuários de serviços de mensagem instantânea (IM) pública AOL e Yahoo!, além dos provedores baseados em XMPP e servidores, como o Google Talk, atualmente o único parceiro XMPP com suporte.
    
Esses cenários funcionará desde que todos os servidores de borda no pool estão em execução, mas se um servidor de borda não estiver disponível, quaisquer solicitações para esses cenários que sejam enviadas a ele falhará, em vez de roteamento para outro servidor de borda.
  
 Se você estiver usando UM do Exchange, você deve usar um mínimo de Exchange 2013 para obter suporte para Skype Business servidor DNS para balanceamento de carga na borda. Se você usar uma versão anterior do Exchange, os usuários remotos não terá recursos de failover para esses cenários UM do Exchange:
  
- Reproduzir suas mensagens de voz do Enterprise no telefone dela
    
- Transferindo chamadas de um Exchange atendedor automático de UM
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando DNS com carga balanceada em Pools de servidor de borda

Para implantar o DNS com carga balanceada na interface externa do seu pool do servidor de borda, você precisa ter as seguintes entradas DNS:
  
- Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço em um dos servidores de borda no pool de borda de acesso.
    
- Para o serviço de borda de webconferência, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço em um dos servidores de borda no pool de borda de webconferência.
    
- Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda de V em um dos servidores de borda no pool /.
    
Para implantar o DNS com carga balanceada na interface interna do seu pool do servidor de borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool de servidores de borda para o endereço IP de cada servidor no pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usando o DNS com carga balanceada em Pools de servidor de mediação
<a name="BK_Mediation"> </a>

Você pode usar o DNS com carga balanceada em pools de servidor de mediação autônomos. Todo o tráfego SIP e a mídia é balanceado pelo balanceamento de carga do DNS.
  
Para implantar o DNS com carga balanceada em um pool do servidor de mediação, você deve provisionar o DNS para resolver o FQDN (por exemplo, mediationpool1.contoso.com) do pool para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueando o tráfego para um servidor com balanceamento de carga DNS
<a name="BK_Mediation"> </a>

Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador. 
  
Observe que para tráfego de servidor-para-servidor, Skype para Business Server usa o balanceamento de carga de reconhecimento de topologia. Os servidores leem a topologia publicada no repositório de gerenciamento Central para obter os FQDNs dos servidores na topologia e distribuam automaticamente o tráfego entre os servidores. Para bloquear um servidor de recebimento do tráfego de servidor-para-servidor, você deve remover o servidor da topologia. 
  

