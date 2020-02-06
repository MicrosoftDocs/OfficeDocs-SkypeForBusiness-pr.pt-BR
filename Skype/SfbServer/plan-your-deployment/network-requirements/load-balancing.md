---
title: Requisitos de balanceamento de carga para o Skype for Business
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumo: revise as considerações de balanceamento de carga antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 199c93528d89786573bdac16077f1e32feb1fe6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802041"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos de balanceamento de carga para o Skype for Business
 
**Resumo:** Examine as considerações de balanceamento de carga antes de implementar o Skype for Business Server.
  
O balanceamento de carga distribui o tráfego entre os servidores em um pool. Se você tiver pools de front-end, pools do servidor de mediação ou pools do servidor de borda, será necessário implantar o balanceamento de carga para esses pools.
  
O Skype for Business Server dá suporte a dois tipos de soluções de balanceamento de carga para tráfego de cliente para servidor: o balanceamento de carga do sistema de nomes de domínio (DNS) e o balanceamento de carga de hardware (geralmente abreviados como HLB). O balanceamento de carga de DNS oferece várias vantagens, incluindo administração mais simples, solução de problemas mais eficiente e capacidade de isolar grande parte do tráfego do Skype for Business Server de qualquer problema potencial de balanceador de carga de hardware.
  
Decida se a solução de balanceamento de carga é adequada para cada pool na sua implantação, mas lembre-se das seguintes restrições: 
  
- A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.
    
- Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.
    
Se optar por usar o balanceamento de carga DNS para um pool, mas ainda for necessário implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada. Por exemplo, a configuração do balanceador de carga de hardware será mais simples, pois gerenciará somente os tráfegos HTTP e HTTPS, enquanto os demais protocolos serão gerenciados pelo balanceamento de carga DNS. Para obter detalhes, consulte [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para o tráfego de servidor para servidor, o Skype for Business Server usa o balanceamento de carga compatível com topologia. Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores. Os administradores não precisam configurar nem gerenciar esse tipo de balanceamento de carga. 
  
Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos do balanceador de carga do hardware

A topologia de borda consolidada do Skype for Business Server dimensionada é otimizada para o balanceamento de carga de DNS para novas implantações que se agrupam principalmente com outras organizações que usam o Skype for Business Server ou o Lync Server. Se for necessário alta disponibilidade para qualquer um dos seguintes cenários, um balanceador de carga de hardware deve ser usado em pools de servidor de borda para o seguinte: 
  
- Federação com organizações que usam o Office Communications Server 2007 R2 ou o Office Communications Server 2007
    
- Exchange UM para usuários remotos usando o Exchange UM antes do Exchange 2010 com SP1
    
- Conectividade para usuários públicos de mensagens instantâneas
    
> [!IMPORTANT]
> O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces. 
  
> [!NOTE]
> Se estiver usando um balanceador de carga de hardware, o balanceador de carga implantado para conexões com a rede interna deverá ser configurado para balancear apenas cargas do tráfego de servidores que executam o serviço de Borda de Acesso e o serviço de Borda A/V. Ele não poderá balancear a carga do tráfego do serviço interno de Borda de Webconferência ou do serviço interno de Proxy XMPP. 
  
> [!NOTE]
> O NAT do Direct Server Return (DSR) não é compatível com o Skype for Business Server. 
  
Para determinar se o balanceador de carga de hardware oferece suporte aos recursos necessários para o Skype for Business Server, consulte [infraestrutura para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de Borda A/V

Veja a seguir os requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de borda A/V:
  
- Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.
    
- Desative o TCP nagling para o intervalo de porta externa 50.000-59.999. 
    
- Não use NAT no firewall interno ou externo. 
    
- A interface interna de borda deve estar em uma rede diferente da interface externa do servidor de borda e o roteamento entre elas deve ser desativado. 
    
- A interface externa do servidor de borda que executa o serviço de borda A/V deve usar endereços IP roteáveis publicamente e sem NAT ou conversão de porta em qualquer um dos endereços IP externos de borda. 
    
- O balanceador de carga não pode trocar o endereço da fonte do cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Outros requisitos de balanceador de carga de hardware

Os requisitos de afinidade baseados em cookies são bastante reduzidos no Skype for Business Server para serviços Web. Se você estiver implantando o Skype for Business Server e não mantiver nenhum servidor front-end do Lync Server 2010 ou pools front-end, não precisará de persistência baseada em cookies. No entanto, se você mantiver temporariamente ou permanentemente qualquer um dos servidores de front-end do Lync Server 2010 ou grupos de front-end, ainda usará persistência baseada em cookies à medida que ela é implantada e configurada para o Lync Server 2010. 
  
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
> As configurações típicas do balanceador de carga de hardware usam a afinidade de endereço de origem e um tempo de vida de sessão TCP de 20 min, que é muito bom para os clientes do Lync Server e do Lync 2013 porque o estado da sessão é mantido por meio do uso do cliente e/ou da interação do aplicativo. 
  
Se estiver implantando dispositivos móveis, o balanceador de carga de hardware deverá ser capaz de balancear a carga da solicitação individual em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!CAUTION]
> Se você estiver implantando dispositivos móveis, o balanceador de carga de hardware deve ser capaz de balancear a carga individual de cada solicitação dentro de uma conexão TCP. Os aplicativos móveis mais recentes do Apple iOS exigem a versão 1.2 do protocolo TLS.  
  
> [!CAUTION]
> Para obter detalhes sobre balanceadores de carga de hardware de terceiros, consulte [infraestrutura para o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways).  
  
A seguir, são apresentados os requisitos do balanceador de carga de hardware para serviços Web do pool de diretores e de front-end:
  
- Para VIPs de serviços Web internos, defina a persistência Source_addr (porta interna 80, 443) no balanceador de carga de hardware. Para o Skype for Business Server, Source_addr persistência significa que várias conexões provenientes de um único endereço IP são sempre enviadas para um servidor para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre o proxy reverso e o balanceamento de carga de hardware do próximo pool de saltos, crie uma regra para permitir https: o tráfego na porta 4443, do proxy inverso para o balanceador de carga de hardware. O balanceador de carga de hardware deve ser configurado para ouvir as portas 80, 443 e 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumo dos requisitos de afinidade do balanceador de carga de hardware

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (somente usuários externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (somente usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoramento de portas dos balanceadores de carga de hardware

Defina o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço do servidor front-end (RTCSRV) parar porque o servidor front-end ou o pool de front-end falha, o monitoramento HLB também deve parar de receber tráfego nos serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte:
  
**Pool de usuários do servidor front-end-interface interna HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<int_mco_443_vs\>da Web de pool  <br/> 443  <br/> |443  <br/> |Front-End  <br/> 5061  <br/> |Origem  <br/> |HTTPS  <br/> |
|\<int_mco_80_vs\>da Web de pool  <br/> 80  <br/> |80  <br/> |Front-End  <br/> 5061  <br/> |Origem  <br/> |HTTP  <br/> |
   
**Pool de usuários do servidor front-end-interface externa HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Observações**|
|:-----|:-----|:-----|:-----|:-----|
|\<web_mco_443_vs\>de grupo  <br/> 443  <br/> |4443  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<web_mco_80_vs\>de grupo  <br/> 80  <br/> |8080  <br/> |Front-End  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BKMK_DNSLoadBalancing"> </a>

O Skype for Business Server permite o balanceamento de carga de DNS, uma solução de software que pode reduzir significativamente a sobrecarga de administração de balanceamento de carga na sua rede. O balanceamento de carga de DNS equilibra o tráfego de rede exclusivo para o Skype for Business Server, como tráfego SIP e tráfego de mídia.
  
Se você implantar o balanceamento de carga de DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada. Além disso, a solução de problemas complexa de problemas relacionados à configuração incorreta de balanceadores de carga para tráfego SIP será eliminada. Você também pode evitar conexões do servidor para que você possa colocar servidores offline. O balanceamento de carga de DNS também garante que os problemas de balanceador de carga de hardware não afetem os elementos do tráfego SIP, como roteamento de chamadas básicas.

O diagrama a seguir mostra um exemplo que inclui o balanceamento de carga de DNS interno e externo: 
  
**Diagrama da rede de borda que usa endereços IPv4 públicos**

![exemplo de diagrama de rede DNS](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se você usa o balanceamento de carga de DNS, também é possível comprar saldos de carga de hardware de baixo custo do que se você usava os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com o Skype for Business Server. Para obter detalhes sobre o teste de interoperabilidade do balanceamento de carga, consulte [parceiros do balanceador de carga do Lync Server 2010](https://go.microsoft.com/fwlink/p/?linkId=202452). O conteúdo aplica-se ao Skype for Business Server.
  
O balanceamento de carga de DNS tem suporte para pools front-end, pools do servidor de borda, pools de diretor e pools autônomos do servidor de mediação.
  
O balanceamento de carga de DNS geralmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando o Skype for Business), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados pela consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o pool FQDN (nome de domínio totalmente qualificado). 
  
Por exemplo, se houver três servidores front-end em um pool chamado pool01.contoso.com, ocorrerá o seguinte:
  
- Clientes que executam o Skype for Business Query DNS para pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte maneira (não necessariamente nesta ordem):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- O cliente tenta estabelecer uma conexão TCP (Transmission Control Protocol) a um dos endereços IP. Se isso falhar, o cliente tentará o próximo endereço IP no cache.
    
- Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.
    
- Se o cliente tentar todas as entradas armazenadas em cache sem uma conexão bem-sucedida, o usuário será notificado de que nenhum servidor executando o Skype for Business Server está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga baseado em DNS é diferente do rodízio de DNS (DNS RR) que geralmente se refere ao balanceamento de carga ao confiar no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores em um pool. Normalmente, o RR DNS habilita somente a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A e AAAA (se você estiver usando endereçamento IPv6) falhar, a conexão falhará. Portanto, o rodízio de DNS por si só é menos confiável do que o balanceamento de carga baseado em DNS. Você pode usar a repetição alternada de DNS em conjunto com o balanceamento de carga de DNS. 
  
O balanceamento de carga de DNS é usado para o seguinte:
  
- Balanceamento de carga do servidor para o servidor SIP para os servidores de borda
    
- Aplicativos UCAS (serviços de aplicativo de comunicação unificada) de balanceamento de carga, como atendedor automático de conferência, grupo de resposta e estacionamento de chamada
    
- Evitando novas conexões para aplicativos do UCAS (também conhecido como "descarga")
    
- Balanceamento de carga de todo o tráfego de cliente para servidor entre clientes e servidores de borda
    
O balanceamento de carga de DNS não pode ser usado para o seguinte:
  
- Tráfego da Web de cliente para servidor para director ou servidores front-end
    
Balanceamento de carga de DNS e tráfego federado:
  
Se vários registros DNS forem retornados por uma consulta de servidor DNS, o serviço de borda de acesso sempre escolhe o registro SRV DNS com a prioridade numérica mais baixa e a espessura numérica mais alta. O documento da força de tarefas de engenharia da Internet "um RR DNS para especificar o local dos serviços (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) especifica que, se houver vários registros SRV DNS definidos, a prioridade será usada primeiro e, em seguida, peso. Por exemplo, o registro SRV DNS A tem uma ponderação de 20 e uma prioridade de 40 e o registro SRV DNS B tem uma ponderação de 10 e prioridade de 50. Registro SRV DNS A with Priority 40 será selecionada. As regras a seguir se aplicam à seleção de registro SRV DNS:
  
- A prioridade é considerada primeiro. Um cliente deve tentar contatar o host de destino definido pelo registro SRV DNS com o menor prioridade numerada que ele pode alcançar. Os destinos com a mesma prioridade devem ser testados em uma ordem definida pelo campo peso.
    
- O campo peso especifica um peso relativo para entradas com a mesma prioridade. Atribuições maiores devem ter uma probabilidade mais alta proporcional mais alta de ser selecionada. Os administradores de DNS devem usar o peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros que contêm pesos maiores do que 0, os registros com peso 0 devem ter uma chance muito menor de serem selecionados.
    
Se vários registros SRV DNS com prioridade e peso iguais forem retornados, o serviço de borda de acesso selecionará o registro SRV que foi recebido primeiro do servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Balanceamento de carga de DNS em pools front-end e pools de diretor

Você pode usar o balanceamento de carga de DNS para o tráfego SIP em pools de front-end e em pools de diretor. Com o balanceamento de carga de DNS implantado, você ainda precisará usar balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente para servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80. 
  
Embora você ainda precise de balanceadores de carga de hardware para esses pools, a configuração e a Administração serão principalmente para tráfego HTTPS, para o qual os administradores de balanceamento de carga de hardware estão acostumados.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Balanceamento de carga de DNS e suporte a clientes e servidores mais antigos

O balanceamento de carga de DNS aceita failover automático somente para servidores que executam o Skype for Business Server ou o Lync Server 2010, e para os clientes do Lync 2013 e do Skype for Business. As versões anteriores dos clientes e do Office Communications Server ainda podem se conectar a pools que executam o balanceamento de carga de DNS, mas se não puderem fazer uma conexão com o primeiro servidor ao qual o balanceamento de carga de DNS a referencia, eles não poderão fazer failover para outro servidor no pool . 
  
Além disso, se você estiver usando o Exchange UM, deverá usar no mínimo o Exchange 2010 SP1 para obter suporte para o balanceamento de carga de DNS do Skype for Business Server. Se você usar uma versão anterior do Exchange, os usuários não terão recursos de failover para estes cenários do Exchange UM:
  
- Jogando o correio de voz corporativo em seu telefone
    
- Transferindo chamadas de um atendedor automático do Exchange UM
    
Todos os outros cenários do Exchange UM funcionarão corretamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>Implantando o balanceamento de carga de DNS em pools front-end e pools de diretor
<a name="BK_FE_Dir"> </a>

Implantar o balanceamento de carga de DNS nos pools front-end e nos pools de diretor exige que você execute algumas etapas adicionais com FQDNs e registros DNS.
  
- Um pool que usa o balanceamento de carga de DNS deve ter dois FQDNs: o FQDN do pool regular que é usado pelo balanceamento de carga de DNS (como pool01.contoso.com) e é resolvido para o IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como web01.contoso.com), que é resolvido para o endereço IP virtual do pool. 
    
    Em Construtor de topologia, se você quiser implantar o balanceamento de carga de DNS para um pool, para criar esse FQDN adicional para os serviços Web do pool, você deve selecionar a caixa de seleção **substituir FQDN do pool de serviços Web internos** e digitar o FQDN na página **especificar as URLs de serviços Web para este pool** .
    
- Para dar suporte ao FQDN usado pelo balanceamento de carga de DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão implantados no momento.
    
    > [!CAUTION]
    > Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como **pool01.contoso.com**, não será possível usar o **pool01.contoso.com** para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Balanceamento de carga de DNS nos pools do servidor de borda
<a name="BK_Edge"> </a>

Você pode implantar o balanceamento de carga de DNS nos pools do servidor de borda. Se fizer isso, você deve estar ciente de algumas considerações.
  
Usar o balanceamento de carga de DNS em seus servidores de borda causa uma perda de capacidade de failover nos seguintes cenários:
  
- Federação com organizações que estão executando versões do Skype for Business Server lançadas antes do Lync Server 2010.
    
- Troca de mensagens de chat com usuários de serviços de mensagens instantâneas (IM) e Yahoo!, além de provedores e servidores baseados em XMPP, como o Google Talk, atualmente o único parceiro XMPP com suporte.
    
Esses cenários funcionarão se todos os servidores de borda do pool estiverem em execução, mas se um servidor de borda estiver indisponível, todas as solicitações para esses cenários enviados a ele falharão, em vez de roteamento para outro servidor de borda.
  
 Se estiver usando o Exchange UM, você deve usar no mínimo o Exchange 2013 para obter suporte para o balanceamento de carga de DNS do Skype for Business Server no Edge. Se você usar uma versão anterior do Exchange, os usuários remotos não terão recursos de failover para estes cenários do Exchange UM:
  
- Jogando o correio de voz corporativo em seu telefone
    
- Transferindo chamadas de um atendedor automático do Exchange UM
    
Todos os outros cenários do Exchange UM funcionarão corretamente.
  
As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando o balanceamento de carga de DNS nos pools do servidor de borda

Para implantar o balanceamento de carga de DNS na interface externa do pool do servidor de borda, você precisa das seguintes entradas de DNS:
  
- Para o serviço de borda de acesso, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de borda de acesso em um dos servidores de borda do pool.
    
- Para o serviço da borda de webconferência, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de Webconferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço Web de Webconferência em um dos servidores de borda no pool.
    
- Para o serviço de borda de áudio/vídeo, você precisa de uma entrada para cada servidor do pool. Cada entrada deve resolver o FQDN do serviço de borda de áudio/vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de borda A/V em um dos servidores de borda do pool.
    
Para implantar o balanceamento de carga de DNS na interface interna do pool do servidor de borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do servidor de borda para o endereço IP de cada servidor do pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usar o balanceamento de carga de DNS nos pools do servidor de mediação
<a name="BK_Mediation"> </a>

Você pode usar o balanceamento de carga de DNS em pools de servidores de mediação autônomos. Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga de DNS.
  
Para implantar o balanceamento de carga de DNS em um pool do servidor de mediação, você deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores do pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueando o tráfego para um servidor com balanceamento de carga de DNS
<a name="BK_Mediation"> </a>

Se você usar um balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas do endereço IP do Pool FQDN. Você deve remover a entrada DNS do computador. 
  
Observe que, para o tráfego de servidor para servidor, o Skype for Business Server usa o balanceamento de carga compatível com topologia. Os servidores lêem a topologia publicada no repositório de gerenciamento central para obter os FQDNs dos servidores na topologia e distribuir automaticamente o tráfego entre os servidores. Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia. 
  

