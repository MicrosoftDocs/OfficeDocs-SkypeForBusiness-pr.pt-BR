---
title: Requisitos de balanceamento de carga para Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
description: 'Resumo: revise as considerações de balanceamento de carga antes de implementar Skype for Business Server.'
ms.openlocfilehash: 4bdfc9d9958154df8ce485c945dbe8accd630ed8
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840993"
---
# <a name="load-balancing-requirements-for-skype-for-business"></a>Requisitos de balanceamento de carga para Skype for Business
 
**Resumo:** Revise as considerações de balanceamento de carga antes de implementar Skype for Business Server.
  
O balanceamento de carga distribui o tráfego entre os servidores em um pool. Se você tiver pools de Front-End, pools de Servidor de Mediação ou pools de Servidor de Borda, precisará implantar o balanceamento de carga para esses pools.
  
Skype for Business Server oferece suporte a dois tipos de soluções de balanceamento de carga para tráfego de cliente para servidor: balanceamento de carga DNS (Sistema de Nomes de Domínio) e balanceamento de carga de hardware (geralmente abreviado como HLB). O balanceamento de carga DNS oferece várias vantagens, incluindo administração mais simples, solução de problemas mais eficiente e a capacidade de isolar grande parte do seu tráfego Skype for Business Server de quaisquer possíveis problemas de balanceador de carga de hardware.
  
Decida por si mesmo qual solução de balanceamento de carga é apropriada para cada pool em sua implantação, mas tenha em mente as seguintes restrições: 
  
- A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS em uma interface e o balanceamento de carga de hardware em outra.
    
- Alguns tipos de tráfego exigem um balanceador de carga de hardware. Por exemplo, o tráfego HTTP requer um balanceador de carga de hardware em vez do balanceamento de carga DNS. O balanceamento de carga DNS não funciona com o tráfego web de cliente-servidor.
    
Se você optar por usar o balanceamento de carga DNS para um pool mas ainda precisa implementar balanceadores de carga de hardware para o tráfego, como o tráfego HTTP, a administração dos balanceadores de carga de hardware é bastante simplificada. Por exemplo, configurar o balanceador de carga de hardware será mais simples, pois ele gerenciará apenas o tráfego HTTP e HTTPS, enquanto todos os outros protocolos serão gerenciados pelo balanceamento de carga DNS. Para obter detalhes, consulte [DNS Load Balancing](load-balancing.md#BKMK_DNSLoadBalancing). 
  
Para tráfego servidor para servidor, o Skype for Business Server usa balanceamento de carga com conhecimento de topologia. Os servidores leem a topologia publicada no armazenamento de Gerenciamento Central para obter os FQDNs dos servidores na topologia e distribuem automaticamente o tráfego entre os servidores. Os administradores não precisam configurar ou gerenciar esse tipo de balanceamento de carga. 
  
Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do Pool. Você também deve remover a entrada DNS do computador. 
  
## <a name="hardware-load-balancer-requirements"></a>Requisitos do balanceador de carga de hardware

A Skype for Business Server de Borda consolidada em escala é otimizada para balanceamento de carga DNS para novas implantações federando principalmente com outras organizações usando o Skype for Business Server ou o Lync Server. Se a alta disponibilidade for necessária para qualquer um dos cenários a seguir, um balanceador de carga de hardware deverá ser usado nos pools do Servidor de Borda para o seguinte: 
  
- Federação com organizações usando Office Communications Server 2007 R2 ou Office Communications Server 2007
    
- Exchange UM para usuários remotos usando Exchange UM antes de Exchange 2010 com SP1
    
- Conectividade para usuários públicos de mensagens instantâneas
    
> [!IMPORTANT]
> O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces. 
  
> [!NOTE]
> Se estiver usando um balanceador de carga de hardware, o balanceador de carga implantado para conexões com a rede interna deverá ser configurado para balancear apenas cargas do tráfego de servidores que executam o serviço de Borda de Acesso e o serviço de Borda A/V. Ele não poderá balancear a carga do tráfego do serviço interno de Borda de Webconferência ou do serviço interno de Proxy XMPP. 
  
> [!NOTE]
> O NAT de retorno do servidor direto (DSR) não é suportado com Skype for Business Server. 
  
Para determinar se o balanceador de carga de hardware dá suporte aos recursos necessários Skype for Business Server, consulte [Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md). 
  
### <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de Borda A/V

A seguir estão os requisitos do balanceador de carga de hardware para Servidores de Borda executando o serviço de Borda A/V:
  
- Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.
    
- Desativar a nagling TCP para o intervalo de portas externos de 50.000 a 59.999. 
    
- Não use NAT no firewall interno ou externo. 
    
- A interface interna da borda precisa estar em uma rede diferente da interface externa do Servidor de Borda e o roteamento entre elas precisa ser desabilitada. 
    
- A interface externa do Servidor de Borda executando o Serviço de Borda A/V deve usar endereços IP de tabela publicamente e nenhuma conversão nat ou porta em qualquer um dos endereços IP externos de borda. 
    
- O balanceador de carga não deve alterar o endereço de origem do cliente.
    
### <a name="other-hardware-load-balancer-requirements"></a>Outros requisitos do Balanceador de Carga de Hardware

Os requisitos de afinidade com base em cookie são muito reduzidos Skype for Business Server para serviços Web. Se você estiver implantando Skype for Business Server e não manterá nenhum Servidor Front-End do Lync Server 2010 ou pools de Front-End, não será necessário persistência baseada em cookie. No entanto, se você reter temporariamente ou permanentemente qualquer Servidor front-end do Lync Server 2010 ou pools de front-end, você ainda usará persistência baseada em cookie à medida que ele for implantado e configurado para o Lync Server 2010. 
  
> [!NOTE]
> **Se decidir usar a afinidade baseada em cookie mesmo que sua implantação não exija**, isso não causará um impacto negativo. 
  
Para implantações que **não usarão** afinidade baseada em cookie:
  
- No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.
    
Para implantações que **usarão** afinidade baseada em cookie:
  
- No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.
    
- O cookie do balanceador de carga de hardware NÃO DEVE ser marcado como httpOnly
    
- O cookie do balanceador de carga de hardware NÃO DEVE conter uma data de vencimento
    
- O cookie do balanceador de carga de hardware DEVE ser nomeado como **MS-WSMAN** (este é o valor que o serviço Web espera e não pode ser alterado)
    
- O cookie do balanceador de carga de hardware DEVE ser definido em todas as respostas HTTP para as quais a solicitação HTTP recebida não contém um cookie, independentemente de uma resposta HTTP anterior na mesma conexão TCP já ter obtido um cookie. Se o balanceador de carga otimiza a inserção de cookie para apenas uma ocorrência por conexão TCP, essa otimização NÃO DEVE ser usada
    
> [!NOTE]
> As configurações típicas do balanceador de carga de hardware usam afinidade de endereço de origem e uma duração de sessão TCP de 20 minutos, o que é bom para clientes do Lync Server e do Lync 2013 porque o estado da sessão é mantido por meio do uso do cliente e/ou da interação do aplicativo. 
  
Se estiver implantando dispositivos móveis, o balanceador de carga de hardware deverá ser capaz de balancear a carga da solicitação individual em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).
  
> [!CAUTION]
> Se você estiver implantando dispositivos móveis, o balanceador de carga de hardware deve ser capaz de balancear individualmente cada solicitação em uma conexão TCP. Os aplicativos móveis mais recentes do Apple iOS exigem a versão 1.2 do protocolo TLS.  
  
> [!CAUTION]
> Para obter detalhes sobre balanceadores de carga de hardware de terceiros, consulte [Infrastructure for Skype for Business](../../../SfbPartnerCertification/certification/infra-gateways.md).  
  
A seguir, são apresentados os requisitos do balanceador de carga de hardware para serviços Web do pool de diretores e de front-end:
  
- Para VIPs de serviços Web internos, defina a persistência Source_addr (porta interna 80, 443) no balanceador de carga de hardware. Para Skype for Business Server, Source_addr persistência significa que várias conexões provenientes de um único endereço IP são sempre enviadas a um servidor para manter o estado da sessão.
    
- Use um tempo de ociosidade de TCP de 1.800 segundos.
    
- No firewall entre o proxy reverso e o balanceador de carga de hardware do pool de próximo salto, crie uma regra para permitir https: tráfego na porta 4443, do proxy reverso para o balanceador de carga de hardware. O balanceador de carga de hardware deve ser configurado para ouvir as portas 80, 443 e 4443.
    
### <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumo dos requisitos de afinidade do balanceador de carga de hardware

|**Local do cliente/usuário**|**Requisitos de afinidade de FQDN de serviços Web externos**|**Requisitos de afinidade de FQDN de serviços Web internos**|
|:-----|:-----|:-----|
|Lync Web App (usuários internos e externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (somente usuários externos)  <br/> Dispositivo móvel (usuários internos e externos)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
|Lync Web App (somente usuários internos)  <br/> Dispositivo móvel (não implantado)  <br/> |Sem afinidade  <br/> |Afinidade do endereço de origem  <br/> |
   
### <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoramento de portas dos balanceadores de carga de hardware

Defina o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço de Servidor front-end (RTCSRV) parar porque o servidor front-end ou pool de front-end falhar, o monitoramento HLB também deve parar de receber tráfego nos Serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte:
  
**Pool de Usuários do Servidor Front-End - Interface Interna HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web-int_mco_443_vs  <br/> 443  <br/> |443  <br/> |Front-end  <br/> 5061  <br/> |Origem  <br/> |HTTPS  <br/> |
|\<pool\>web-int_mco_80_vs  <br/> 80  <br/> |80  <br/> |Front-end  <br/> 5061  <br/> |Origem  <br/> |HTTP  <br/> |
   
**Pool de Usuários do Servidor Front-End - Interface Externa HLB**

|**IP/porta virtual**|**Porta do nó**|**Máquina/monitor do nó**|**Perfil de persistência**|**Anotações**|
|:-----|:-----|:-----|:-----|:-----|
|\<pool\>web_mco_443_vs  <br/> 443  <br/> |4443  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTPS  <br/> |
|\<pool\>web_mco_80_vs  <br/> 80  <br/> |8080  <br/> |Front-end  <br/> 5061  <br/> |Nenhum  <br/> |HTTP  <br/> |
   
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="BKMK_DNSLoadBalancing"> </a>

Skype for Business Server habilita o balanceamento de carga DNS, uma solução de software que pode reduzir consideravelmente a sobrecarga de administração para o balanceamento de carga em sua rede. O balanceamento de carga DNS equilibra o tráfego de rede exclusivo Skype for Business Server, como tráfego SIP e tráfego de mídia.
  
Se você implantar o balanceamento de carga DNS, a sobrecarga de administração da sua organização para balanceadores de carga de hardware será minimizada. Além disso, a solução complexa de problemas relacionados à configuração incorreta de balanceadores de carga de tráfego SIP será eliminada. Você também pode impedir as conexões de servidor para que seja possível assumir servidores offline. O balanceamento de carga DNS também garante que os problemas de balanceador de carga de hardware não afetem elementos do tráfego SIP, como o roteamento básico de chamada.

O diagrama a seguir mostra um exemplo que inclui o balanceamento de carga DNS interno e externo: 
  
**Diagrama de rede de borda usando endereços IPv4 públicos**

![exemplo de diagrama de rede DNS.](../../media/2cc9546e-5560-4d95-8fe4-65a792a0e9c3.png)
  
Se você usar o balanceamento de carga DNS, também poderá adquirir os balanceadores de carga de hardware de custo mais baixo do que se usasse os balanceadores de carga de hardware para todos os tipos de tráfego. Você deve usar balanceadores de carga que passaram no teste de qualificação de interoperabilidade com Skype for Business Server. Para obter detalhes sobre o teste de interoperabilidade do balanceador de carga, consulte [Lync Server 2010 Load Balancer Partners](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md). O conteúdo lá se aplica a Skype for Business Server.
  
O balanceamento de carga DNS é compatível com pools de Front-end, pools de Servidor de Borda, pools de Diretores e pools de Servidor de mediação autônomos.
  
O balanceamento de carga do DNS normalmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando um Skype for Business), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o FQDN (nome de domínio totalmente qualificado do pool). 
  
Por exemplo, se houver três servidores front end em um pool chamado pool01.contoso.com, acontecerá o seguinte:
  
- Clientes executando Skype for Business DNS de consulta para pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte forma (não necessariamente nesta ordem):
    
    pool01.contoso.com 192.168.10.90
    
    pool01.contoso.com 192.168.10.91
    
    pool01.contoso.com 192.168.10.92
    
- O cliente tenta estabelecer uma conexão TCP (Transmission Control Protocol) com um dos endereços IP. Em caso de falha, o cliente tenta o próximo endereço IP em cache.
    
- Se a conexão TCP for bem-sucedida, o cliente negociará tLS para se conectar ao registrador principal no pool01.contoso.com.
    
- Se o cliente tentar todas as entradas armazenadas em cache sem uma conexão bem-sucedida, o usuário será notificado de que nenhum servidor que Skype for Business Server estiver disponível no momento.
    
> [!NOTE]
> O balanceamento de carga baseado em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP correspondentes aos servidores em um pool. Normalmente o DNS RR só habilita a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com o único endereço IP retornado pela consulta DNS A e AAAA (se você estiver usando endereçamento IPv6) falhar, a conexão falhará. Portanto, o round robin de DNS por si só é menos confiável do que o balanceamento de carga baseado em DNS. O round robin de DNS pode ser usado em conjunto com o balanceamento de carga do DNS. 
  
O balanceamento de carga do DNS é usado para:
  
- SIP de balanceamento de carga de servidor para servidor para os Servidores de Borda
    
- Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada
    
- Evitar novas conexões a aplicativos UCAS (também conhecido como "drenagem")
    
- Balanceamento de carga de todo o tráfego cliente-para-servidor entre clientes e Servidores de Borda
    
O balanceamento de carga do DNS não pode ser usado para:
  
- Tráfego web de cliente para servidor para o Diretor ou servidores front-end
    
Balanceamento de carga do DNS e tráfego federado:
  
Se vários registros DNS são retornados por uma consulta DNS SRV, o serviço de Borda de Acesso sempre escolhe o registro SRV DNS com a prioridade numérica mais baixa e maior peso numérico. O documento da Força de Tarefa de Engenharia da Internet "Um DNS RR para especificar o local dos serviços (DNS SRV)" [RFC 2782, DNS SRV RR](https://www.ietf.org/rfc/rfc2782.txt) especifica que, se houver vários registros SRV DNS definidos, a prioridade será usada primeiro e, em seguida, o peso. Por exemplo, o registro SRV DNS A tem um peso de 20 e uma prioridade de 40 e registro SRV DNS B tem um peso de 10 e prioridade de 50. O registro SRV DNS A com prioridade 40 será selecionado. As seguintes regras se aplicam à seleção de registro SRV DNS:
  
- Prioridade é considerada primeiro. Um cliente DEVE tentar contatar o host de destino definido pelo registro SRV DNS com a prioridade numerada mais baixa que ele pode alcançar. Destinos com a mesma prioridade DEVEM ser tentados em uma ordem definida pelo campo de peso.
    
- O campo de peso especifica um peso relativo para entradas com a mesma prioridade. Pesos maiores DEVEM receber uma probabilidade proporcionalmente maior de ser selecionado. Os administradores DNS DEVEM usar o Peso 0 quando não houver nenhuma seleção de servidor a ser usada. Na presença de registros que contenham pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.
    
Se vários registros SRV DNS com igual prioridade e peso são retornados, o serviço de Borda de Acesso selecionará o registro SRV que foi recebido primeiro do servidor DNS.
  
### <a name="dns-load-balancing-on-front-end-pools-and-director-pools"></a>Balanceamento de carga DNS em  pools do Diretor e  pools de Front-End

Você pode usar o  balanceamento de carga DNS para o tráfego SIP em pools de Front-End e  pools do Diretor. Com o balanceamento de carga DNS implantado, você precisará usar também os balanceadores de carga de hardware para esses pools, mas somente para tráfego HTTPS de cliente-servidor. O balanceador de carga de hardware é usado para tráfego HTTPS de clientes nas portas 443 e 80. 
  
Embora você ainda precisará de balanceadores de carga de hardware para estes pools, sua configuração e administração será principalmente para o tráfego HTTPS, aos quais os administradores dos balanceadores de carga de hardware estão acostumados.
  
#### <a name="dns-load-balancing-and-supporting-older-clients-and-servers"></a>Balanceamento de carga DNS e suporte aos clientes e servidores mais antigos

O balanceamento de carga DNS dá suporte apenas ao failover automático para servidores que executam o Skype for Business Server ou o Lync Server 2010 e para clientes do Lync 2013 e Skype for Business. As versões anteriores dos clientes e do Office Communications Server ainda podem se conectar aos pools que executam o balanceamento de carga DNS, mas se eles não puderem fazer uma conexão com o primeiro servidor ao que o balanceamento de carga DNS os refere, eles não poderão fazer fail over para outro servidor no pool. 
  
Além disso, se você estiver usando Exchange UM, deverá usar um mínimo de Exchange 2010 SP1 para obter suporte para Skype for Business Server balanceamento de carga DNS. Se você usar uma versão anterior do Exchange, os usuários não terão recursos de failover para esses Exchange de UM:
  
- Tocar suas Enterprise caixa postal no telefone
    
- Transferindo chamadas de um Atendedor Automático UM do Exchange
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
#### <a name="deploying-dns-load-balancing-on-front-end-pools-and-director-pools"></a>A implantação do balanceamento de carga DNS em  pools do Diretor e  pools de Front-End
<a name="BK_FE_Dir"> </a>

A  implantação do balanceamento DNS de carga nos pools de Front-Ends e  pools do Diretor requer a execução de algumas etapas extras com os registros DNS e FQDNs.
  
- Um pool que usa balanceamento de carga DNS deve ter dois FQDNs: o FQDN de pool regular que é usado pelo balanceamento de carga DNS (como pool01.contoso.com) e resolve para os IPs físicos dos servidores no pool e outro FQDN para os serviços Web do pool (como o web01.contoso.com), que resolve para o endereço IP virtual do pool. 
    
    No Construtor de Topologias, se você quiser implantar o balanceamento de carga DNS para um pool, para criar esse FQDN extra para os serviços Web do pool, selecione a caixa de seleção Substituir **FQDN** do pool de Serviços Web internos e digite o FQDN, na página Especificar as **URLs** de Serviços Web para este Pool.
    
- Para suportar o FQDN usado pelo balanceamento de carga DNS, você deve provisionar o DNS para resolver o FQDN do pool (como pool01.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante). Você deve incluir somente os endereços IP dos servidores que estão atualmente implantados.
    
    > [!CAUTION]
    > Se você tiver mais de um pool de Front-End ou Servidor Front-End, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um Servidor Front-End como **pool01.contoso.com**, não poderá usar o **pool01.contoso.com** para outro pool de Front-End ou Servidor Front-End. Se você também estiver implantando Diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deve ser exclusivo de qualquer outro diretor ou pool de diretores, bem como qualquer pool de Front-End ou Servidor Front-End. Se decidir substituir os serviços Web internos por um FQDN auto-definido, cada FQDN deverá ser exclusivo de qualquer outro pool de Front-End, Diretor ou pool de Diretores.
  
### <a name="dns-load-balancing-on-edge-server-pools"></a>Balanceamento de carga DNS em pools de servidor de borda
<a name="BK_Edge"> </a>

Você pode implantar o balanceamento de carga DNS em pools de servidor de borda. Se você fizer isso, deve estar ciente de algumas considerações.
  
Usar o balanceamento de carga DNS nos servidores de borda provoca uma perda da capacidade de failover nos seguintes cenários:
  
- Federação com organizações que executam versões de Skype for Business Server lançadas antes do Lync Server 2010.
    
- Troca de mensagens instantâneas com usuários de serviços públicos de mensagens instantâneas (IM) AOL e Yahoo!, além de provedores e servidores baseados em XMPP, como o Google Talk, atualmente o único parceiro XMPP com suporte.
    
Esses cenários funcionarão desde que todos os servidores de borda no pool estejam funcionando. Se um servidor de borda estiver disponível, as solicitações enviadas para esses cenários falharão, em vez de rotear para outro servidor de borda.
  
 Se você estiver usando Exchange UM, deverá usar um mínimo de Exchange 2013 para obter suporte para Skype for Business Server balanceamento de carga DNS no Edge. Se você usar uma versão anterior do Exchange, os usuários remotos não terão recursos de failover para esses Exchange de UM:
  
- Tocar suas Enterprise caixa postal no telefone
    
- Transferindo chamadas de um Atendedor Automático UM do Exchange
    
Todos os outros cenários UM do Exchange funcionarão corretamente.
  
A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.
  
#### <a name="deploying-dns-load-balancing-on-edge-server-pools"></a>Implantando o Balanceamento de Carga DNS em Pools de Servidor de Borda

Para implantar o balanceamento de carga DNS na interface externa do seu pool de Servidor de Borda, são necessárias as seguintes entradas DNS:
  
- Para o serviço de Borda de Acesso, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de Borda de Acesso (por exemplo, sip.contoso.com) para o endereço IP do serviço de Borda de Acesso em um dos Servidores de Borda no pool.
    
- Para o serviço de Borda de WebConferência, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de Borda de WebConferência (por exemplo, webconf.contoso.com) para o endereço IP do serviço de Borda de WebConferência em um dos Servidores de Borda no pool.
    
- Para o serviço de Borda de Áudio/Vídeo, você precisa de uma entrada para cada servidor no pool. Cada entrada deve resolver o FQDN do serviço de Borda de Áudio/Vídeo (por exemplo, av.contoso.com) para o endereço IP do serviço de Borda A/V em um dos Servidores de Borda no pool.
    
Para implantar o balanceamento de carga DNS na interface interna do pool de Servidor de Borda, você deve adicionar um registro DNS A, que resolve o FQDN interno do pool do Servidor de Borda para o endereço IP de cada servidor do pool.
  
### <a name="using-dns-load-balancing-on-mediation-server-pools"></a>Usando o balanceamento de carga DNS em pools do servidor de mediação
<a name="BK_Mediation"> </a>

Você pode usar um  balanceamento de carga DNS em pools do Servidor de Mediação autônomos. Todo o tráfego SIP e de mídia é balanceado pelo balanceamento de carga DNS.
  
Para implantar o balanceamento de carga DNS em um pool do Servidor de Mediação, vcê deve provisionar o DNS para resolver o FQDN do pool (por exemplo, mediationpool1.contoso.com) para os endereços IP de todos os servidores no pool (por exemplo, 192.168.1.1, 192.168.1.2 e assim por diante).
  
### <a name="blocking-traffic-to-a-server-with-dns-load-balancing"></a>Bloqueando o tráfego para um servidor com balanceamento de carga DNS
<a name="BK_Mediation"> </a>

Se você usar o balanceamento de carga DNS e precisar bloquear o tráfego para um computador específico, não é suficiente apenas remover as entradas de endereço IP do FQDN do Pool. Você também deve remover a entrada DNS do computador. 
  
Observe que, para o tráfego servidor para servidor, Skype for Business Server usa balanceamento de carga com conhecimento de topologia. Os servidores leem a topologia publicada no armazenamento de Gerenciamento Central para obter os FQDNs dos servidores na topologia e distribuem automaticamente o tráfego entre os servidores. Para impedir que um servidor receba tráfego de servidor para servidor, você deve remover o servidor da topologia. 
