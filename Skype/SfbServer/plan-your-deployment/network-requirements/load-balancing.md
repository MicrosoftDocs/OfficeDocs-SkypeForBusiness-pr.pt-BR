---
title: Requisitos de balanceamento de carga para o Skype for Business
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
ms.openlocfilehash: ed3572b16126ce16b423d4ffe0d60d1f84d6b3cf
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408162"
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
> Para obter informações sobre balanceadores de carga de hardware de terceiros, consulte [Infraestrutura para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
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
  
Se você implantar o balanceamento de carga do DNS, administração da sua organização sobrecarga de balanceadores de carga de hardware será minimizada. Além disso, a solução complexa de problemas relacionados à configuração incorreta de balanceadores de carga de tráfego SIP será eliminada. Você também pode impedir as conexões de servidor para que seja possível assumir servidores offline. O balanceamento de carga de DNS também garante que os problemas do balanceador de carga de hardware não afetem elementos do tráfego SIP, como o encaminhamento básico de chamadas.

O diagrama a seguir mostra um exemplo que inclui tanto interna e balanceamento de carga de DNS externo: 
  
**Diagrama da rede de borda que usa endereços IPv4 públicos**

![exemplo de diagrama de rede de DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se usar o balanceamento de carga DNS, você também poderá adquirir balanceadores de carga de hardware de custo mais baixo do que se usasse os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar os balanceadores de carga que passaram qualificação de interoperabilidade o teste com Skype Business Server. Para obter detalhes sobre o teste de interoperabilidade do balanceador de carga, consulte [Parceiros de Balanceador de carga do Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). O seu conteúdo se aplica a Skype para Business Server.
  
O balanceamento de carga DNS é suportado para pools de front-ends, pools de servidores de borda, pools de diretores e pools autônomos do Servidor de Mediação.
  
O balanceamento de carga do DNS normalmente é implementado no nível dos aplicativos. O aplicativo (por exemplo, um cliente executando o Skype para negócios), tenta se conectar a um servidor em um pool Estabelecendo conexão com um dos endereços IP retornados da consulta para o nome de domínio totalmente qualificado (FQDN) do pool de registrar o DNS A e AAAA (se for usado o endereçamento IPv6). 
  
Por exemplo, se houver três servidores front-end em um pool chamado pool01.contoso.com, acontecerá o seguinte:
  
- Clientes executando o Skype para negócios consultam DNS para pool01. contoso.com. A consulta retorna três endereços de IP e os armazena em cache da seguinte maneira (não necessariamente nesta ordem):
    
    pool01. contoso.com 192.168.10.90
    
    pool01. contoso.com 192.168.10.91
    
    pool01. contoso.com 192.168.10.92
    
- O cliente tenta estabelecer uma conexão TCP com um dos endereços IP. Em caso de falha, o cliente tenta o próximo endereço IP em cache.
    
- Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.
    
- Se o cliente experimenta todas as entradas em cache sem uma conexão bem-sucedida, o usuário é notificado de que nenhum servidor executando o Skype para Business Server está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga com base em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores de um pool. Normalmente, o DNS RR só habilita a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A e AAAA (se estiver usando o endereçamento IPv6) falhar, a conexão falha. Portanto, o round robin de DNS por si só é menos confiável do que o balanceamento de carga com base em DNS. O round robin de DNS pode ser usado em conjunto com o balanceamento de carga do DNS. 
  
O balanceamento de carga do DNS é usado para:
  
- Balanceamento de carga SIP entre servidores para servidores de borda
    
- Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada
    
- Evitar novas conexões a aplicativos UCAS (também conhecido como "drenagem")
    
- Balanceamento de carga de todo o tráfego do cliente para o servidor entre clientes e servidores de borda
    
O balanceamento de carga do DNS não pode ser usado para:
  
- Tráfego web do cliente para o servidor para diretor ou servidores de front-end
    
Balanceamento de carga do DNS e tráfego federado:
  
Se uma consulta SRV do DNS retornar vários registros, o serviço de borda de acesso sempre escolherá o registro SRV de DNS com a prioridade numérica mais baixa e peso numérico mais alto. O Internet Engineering Task Force "Um RR DNS para especificar a localização dos serviços (DNS SRV)" de documento [RFC 2782, RR SRV de DNS](https://www.ietf.org/rfc/rfc2782.txt) Especifica que, se houver vários SRV de DNS registros definidos, prioridade é usada primeiro, depois de peso. Por exemplo, o registro SRV do DNS A tem peso 20 e prioridade 40 e o registro SRV do DNS B tem peso 10 e prioridade 50. O registro SRV do DNS A com prioridade 40 será selecionado. As regras a seguir se aplicam à seleção de registros SRV de DNS:
  
- A prioridade é considerada primeiro. O cliente DEVE tentar entrar em contato com o host de destino definido pelo registro SRV do DNS com a prioridade numérica mais baixa que ele puder atingir. Os destinos com a mesma prioridade DEVEM ser examinados em uma ordem definida pelo campo de peso.
    
- O campo de peso especifica um peso relativo para as entradas com a mesma prioridade. Pesos superiores DEVEM ser informados com uma probabilidade maior de ser proporcionalmente selecionado. Os administradores de DNS devem usar o peso 0 quando não houver qualquer seleção de servidor para fazer. Na presença de registros contendo pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.
    
Se vários registros SRV do DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso escolherá o primeiro registro SRV recebido do servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Balanceamento de carga de DNS em pools de front-ends e de diretores

Você pode usar o  balanceamento de carga de DNS para o tráfego SIP em pools de front-ends e de diretores. Com o balanceamento de carga de DNS implantado, você também precisará usar os balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS do cliente para o servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80. 
  
Embora você ainda precise de balanceadores de carga de hardware para esses pools, a configuração e administração desses balanceadores será destinada principalmente ao tráfego HTTPS, ao qual os administradores dos balanceadores de carga de hardware estão acostumados.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Balanceamento de carga de DNS e suporte aos clientes e servidores mais antigos

Failover automático de balanceamento suporta apenas para servidores que executam o Skype para Business Server ou o Lync Server 2010 e para o Lync 2013 e Skype para clientes de negócios de carga do DNS. Versões anteriores do Office Communications Server e de clientes ainda podem se conectar aos pools executando o balanceamento de carga DNS, mas se eles não podem fazer com que uma conexão para o primeiro servidor que balanceamento de carga DNS se refere a eles, eles não conseguem fazer failover para outro servidor no pool . 
  
Além disso, se você estiver usando UM do Exchange, você deve usar o mínimo do Exchange 2010 SP1 para obter suporte para Skype para balanceamento de carga de DNS do servidor de negócios. Se você usar uma versão anterior do Exchange, seus usuários não terão acesso às funcionalidades de failover para estes cenários do UM do Exchange:
  
- A reprodução da caixa postal do Enterprise no telefone
    
- A transferência de chamadas de um atendedor automático de UM do Exchange
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>A implantação do balanceamento de carga DNS em  pools do Diretor e  pools de Front-End
<a name="BK_FE_Dir"> </a>

A implantação do balanceamento de carga de DNS nos pools de front-ends e de diretores requer a execução de algumas etapas extra com os registros de DNS e FQDNs.
  
- Um pool que usa o balanceamento de carga DNS deve ter dois FQDNs: regular pool FQDN que é usada pelo DNS e balanceamento de carga (por exemplo, pool01. contoso.com), resolve para o IPs físico dos servidores no pool e outro FQDN Web do pool services (tais como web01.contoso.com), que se resolva como o endereço IP virtual do pool. 
    
    No construtor de topologia, se você deseja implantar o DNS com carga balanceada para um pool, para criar esse FQDN extra para serviços da Web do pool selecione a caixa de seleção **FQDN do pool de serviços Web internos de substituição** e digite os nomes FQDN, no **especificar as URLs do Web Services para Este Pool** página.
    
- Para suportar o FQDN usado pelo balanceamento de carga de DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de Front-End ou servidor Front-End os serviços Web externos FQDN deve ser exclusivo. Por exemplo, se você definir os serviços Web externos FQDN de um servidor Front-End como **pool01. contoso.com**, você não pode usar **pool01. contoso.com** para outro pool de Front-End ou servidor Front-End. Se você estiver implantando o diretores também, o external FQDN definido para qualquer Diretor de serviços da Web ou pool de diretores deve ser exclusivo de qualquer outro diretor ou diretor do pool, bem como qualquer pool Front-End ou servidor Front-End. Caso decida substituir os serviços web internos com um FQDN auto-definido, cada FQDN deve ser exclusivo de qualquer outro pool de Front-End, diretor ou um pool de diretores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Balanceamento de carga de DNS em pools de servidores de borda
<a name="BK_Edge"> </a>

Você pode implantar o balanceamento de carga DNS em pools de servidor de borda. Se você fizer isso, deve estar ciente de algumas considerações.
  
Usar o balanceamento de carga de DNS nos servidores de borda provoca perda da capacidade de failover nos seguintes cenários:
  
- Federação com organizações que estão executando versões do Skype para Business Server lançadas anteriormente para o Lync Server 2010.
    
- Troca de mensagens instantâneas com usuários de serviços de mensagem instantânea (IM) pública AOL e Yahoo!, além dos provedores baseados em XMPP e servidores, como o Google Talk, atualmente o único parceiro XMPP com suporte.
    
Esses cenários funcionarão desde que todos os servidores de borda no pool estejam funcionando. Se houver um servidor de borda indisponível, as solicitações enviadas para esses cenários falharão, em vez de serem encaminhadas para outro servidor de borda.
  
 Se você estiver usando UM do Exchange, você deve usar um mínimo de Exchange 2013 para obter suporte para Skype Business servidor DNS para balanceamento de carga na borda. Se você usar uma versão mais antiga do Exchange, seus usuários remotos não terão funcionalidades de failover para estes cenários de UM do Exchange:
  
- A reprodução da caixa postal do Enterprise no telefone
    
- A transferência de chamadas de um atendedor automático de UM do Exchange
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
As interfaces de bordas interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga de DNS em uma interface de borda e o balanceamento de carga de hardware na outra interface.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando o balanceamento de carga de DNS em pools de servidores de borda

Para implantar o balanceamento de carga DNS na interface externa do seu pool de Servidor de Borda, são necessárias as seguintes entradas DNS:
  
- Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP desse serviço em um dos servidores de borda do pool.
    
- Para o serviço de borda de webconferência, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de webconferência (por exemplo, webconf.contoso.com) para o endereço IP desse serviço em um dos servidores de borda do pool.
    
- Para o serviço de borda de áudio e vídeo, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda de V em um dos servidores de borda no pool /.
    
Para implantar o balanceamento de carga de DNS na interface interna do pool de servidores de borda, você deve adicionar um registro A de DNS que resolva o FQDN interno do pool de servidores de borda para o endereço IP de cada servidor do pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usando o balanceamento de carga DNS em pools do servidor de mediação
<a name="BK_Mediation"> </a>

Você pode usar um balanceamento de carga de DNS em pools autônomos do Servidor de Mediação. Todo o tráfego SIP e de mídia será balanceado pelo balanceamento de carga de DNS.
  
Para implantar o balanceamento de carga de DNS em um pool do Servidor de Mediação, você deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloquer o Tráfego a um Servidor com Balanceamento de Carga DNS
<a name="BK_Mediation"> </a>

Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador. 
  
Observe que para tráfego de servidor-para-servidor, Skype para Business Server usa o balanceamento de carga de reconhecimento de topologia. Os servidores leem a topologia publicada no repositório de gerenciamento Central para obter os FQDNs dos servidores na topologia e distribuam automaticamente o tráfego entre os servidores. Para bloquear o recebimento de tráfego entre servidores em um servidor, você deve remover o servidor da topologia. 
  

