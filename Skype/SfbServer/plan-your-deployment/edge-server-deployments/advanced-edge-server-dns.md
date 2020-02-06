---
title: Planejamento DNS de servidor de borda avançado para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumo: examine os cenários das opções de implantação do Skype for Business Server. Se você deseja um único servidor ou prefere um pool de servidores com DNS ou HLB, este tópico deve ajudar.'
ms.openlocfilehash: 098d25a23745c035813cfc5c0ea6d291999c3704
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803381"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Planejamento DNS de servidor de borda avançado para o Skype for Business Server
 
**Resumo:** Cenários de revisão para as opções de implantação do Skype for Business Server. Se você deseja um único servidor ou prefere um pool de servidores com DNS ou HLB, este tópico deve ajudar.
  
Quando se trata de planejamento DNS (Domain Name System) para o Skype for Business Server, há muitos fatores que podem ser executados na sua decisão. Se a estrutura de domínio de sua organização já estiver em vigor, pode ser só uma questão de analisar como continuar. Começaremos com os tópicos abaixo:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Os clientes do Skype for Business são semelhantes às versões anteriores dos clientes do Lync em como localizam e acessam serviços no Skype for Business Server. Esta seção detalha o processo de local do servidor.
  
1. lyncdiscoverinternal. \<domínio\>
    
     *Um registro de host do serviço de Descoberta Automática nos serviços Web internos.* 
    
2. lyncdiscover. \<domínio\>
    
     *Um registro de host do serviço de Descoberta Automática nos serviços Web externos.* 
    
3. _sipinternaltls. _tcp. \<domínio\>
    
     *Um registro SRV para conexões TLS internas.* 
    
4. _sip. _tls. \<domínio\>
    
     *Um registro SRV para conexões TLS externas.* 
    
5. sipinternal. \<domínio\>
    
     *Esse é um registro de host para o pool ou o diretor de front-end, que é resolvível somente na rede interna.* 
    
6. SPI. \<domínio\>
    
     *Esse é um registro de host para o pool ou o diretor de front-end, que é resolvível somente na rede interna.* 
    
7. sipexternal. \<domínio\>
    
     *Esse é um registro de host para o serviço de borda de acesso, quando o cliente é externo.* 
    
O serviço de Descoberta Automática é sempre considerado o método preferencial para local do serviço, e os outros estão métodos de fallback.
  
> [!NOTE]
> Ao criar registros SRV, é importante lembrar que eles devem apontar para um DNS A (e AAAA, se você estiver usando endereçamento IPv6) no mesmo domínio em que o registro SRV do DNS for criado. Por exemplo, se o registro SRV estiver em contoso.com, o registro A (e AAAA) para o qual aponta não poderá estar em fabrikam.com. 
  
Se você quiser, é possível definir seu dispositivo móvel para descoberta manual de serviços. Se for isso que você desejar fazer, cada usuário precisa definir as configurações de seus dispositivos móveis com os URIs completos, internos e externos, do serviço de Descoberta Automática, incluindo o protocolo e o caminho, da seguinte forma:
  
- Para acesso externo: https://\<ExtPoolFQDN\>/autodiscover/autodiscoverservice.svc/root
    
- Para acesso interno: https://\<IntPoolFQDN\>/autodiscover/autodiscover.svc/root
    
Recomendamos que você use a descoberta automática em oposição à descoberta manual. Mas, se você estiver solucionando problemas ou fazendo testes, as configurações manuais podem ser muito úteis.
  
## <a name="split-brain-dns"></a>DNS de dupla personalidade
<a name="SplitBrainDNS"> </a>

Esta é uma configuração de DNS na qual você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com os pedidos internos, enquanto a segunda zona DNS lida com os pedidos externos.
  
Por que uma empresa faria isso? Pode haver a necessidade de usar o mesmo namespace internamente e externamente, mas isso levaria a muitos SRV e registros A de DNS exclusivos para uma ou outra zona e, onde houver duplicação, os endereços IP associados a esses registros seriam exclusivo.
  
Isso apresenta alguns desafios. O mais importante é que o DNS Split-Brain **não é compatível** com a mobilidade. Isso ocorre por causa dos registros de DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve ser definido no servidor DNS externo, enquanto que LyncDiscoverInternal deve ser definido em seu servidor DNS interno).
  
Listaremos os registros de DNS das zonas internas e externas aqui, mas você pode encontrar exemplos detalhados na seção requisitos de ambiente do servidor de borda.
  
### <a name="internal-dns"></a>DNS Interno

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativo.
    
- Essa zona interna contoso.com contém:
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para o pool de front-end, o pool de directors ou o nome do pool de diretor e todos os servidores internos que executam o Skype for Business Server na rede da sua organização.
    
  - Registros A e AAAA do DNS (se você estiver usando endereçamento IPv6) para a interface interna do seu Edge para cada servidor de borda do Skype for Business Server na sua rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor de proxy reverso na sua rede de perímetro (que é **opcional** para o gerenciamento de um proxy reverso).
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para configuração automática interna do cliente do Skype for Business Server (que é **opcional** ).
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web do Skype for Business Server (que é **opcional** ).
    
- Todas as interfaces de borda interna do Skype for Business Server na sua rede de perímetro usam essa zona DNS interna para a resolução de consultas para o contoso.com.
    
- Todos os servidores que executam o Skype for Business Server e clientes que executam o Skype for Business Server na rede corporativa, apontam para servidores DNS internos para a resolução de consultas para o contoso.com ou usam o arquivo host em cada servidor de borda e lista de A e AAAA (se você estiver usando Endereçamento IPv6) para o próximo servidor de salto (especificamente para o diretor de diretor ou diretor de diretor, VIP de pool de front-end ou servidor Standard Edition).
    
### <a name="external-dns"></a>DNS Externo

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativo
    
- Essa zona externa contoso.com contém:
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática dos serviços da Web do Skype for Business Server. Isso é para uso com mobilidade.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a interface externa Edge de cada servidor de borda do Skype for Business Server ou VIP de carga de hardware (HLB) balanceada na rede de perímetro.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a interface externa do servidor proxy reverso ou (VIP para um pool de servidores proxy reverso), na rede de perímetro.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e Registros SRV para a configuração automática do cliente do Skype for Business Server ( **opcional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem DNS de dupla personalidade
<a name="NoSplitBrainDNS"> </a>

Se você não usar o DNS Split-Brain, a configuração interna automática de clientes que executam o Skype for Business não funcionará, a menos que você esteja usando uma das soluções alternativas aqui. Por que não? Como o Skype for Business Server exige que o URI SIP do usuário corresponda ao domínio do pool de front-end designado para configuração automática. Isso não mudou de versões anteriores do Lync Server.
  
Portanto, se você tiver dois domínios SIP em uso, você precisará desses registros SRV de DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se um usuário entrar como bob@contoso.com, esse registro funcionaria para configuração automática, pois o domínio SIP do usuário corresponde ao domínio do pool de front-ends (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se um usuário entrar como alice@fabrikam.com, esse registro funcionaria para a configuração automática do segundo domínio, novamente porque o domínio SIP corresponde ao pool de front-end desse domínio.* 
    
Para aprofundar mais o exemplo, isso não funcionaria:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *O logon de usuário tim@litwareinc.com não funcionará para a configuração automática, porque seu domínio SIP (litwareinc.com) não corresponde ao domínio do pool (fabrikam.com).* 
    
Agora que sabemos tudo isso, se você precisar de requisito automático para seus clientes do Skype for Business sem divisão-Brain DNS, terá estas opções:
  
- **Objetos de Política de Grupo**
    
    Você pode usar Objetos de Política de Grupo (GPOs) para popular os valores de servidor corretos.
    
    > [!NOTE]
    > Essa opção não habilita a configuração automática, mas automatiza a configuração manual. Se essa abordagem for utilizada, os registros SRV associados à configuração automática não serão necessários. 
  
- **Zona interna correspondente**
    
    Você precisará criar uma zona no seu DNS interno que corresponda à sua zona DNS externa (por exemplo, contoso.com) e, em seguida, criar registros DNS A (e AAAA se você estiver usando endereçamento IPv6) que correspondam ao pool do servidor do Skype for Business usado para automático configuração.
    
    Por exemplo, se você tiver um usuário hospedado no pool01.contoso.net, mas entrar no Skype for Business como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e dentro dela você precisará criar um registro DNS A (e AAAA se o endereçamento IPv6) para pool01.contoso.com.
    
- **Zona interna exata**
    
    Se criar uma zona inteira no DNS interno não for uma opção, você poderá criar zonas exatas (dedicadas) que correspondam aos registros SRV necessários para a configuração automática e popular estas zonas usando o dnscmd.exe. O dnscmd.exe é necessário porque a interface do usuário do DNS não é compatível com a criação de zonas exatas.
    
    Por exemplo, se o seu domínio SIP for contoso.com e você tiver um pool de front-end chamado pool01 que contém dois servidores front-end, você precisará das seguintes zonas de ponto de fixação e registros no seu DNS interno:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Você pode ter um segundo domínio SIP em seu ambiente. Nesse caso, você precisará das seguintes zonas exatas e registros A em seu DNS interno:
    
  ```
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Você verá que o FQDN do pool de front-end aparece duas vezes, mas com dois endereços IP diferentes. Isso ocorre porque o balanceamento de carga DNS é usado. Se HLB for usado, haverá apenas uma única entrada de pool de front-end. 
  
> [!NOTE]
> Além disso, os valores de FQDN do pool de front-end são alterados entre os exemplos contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso porque os usuários que estão entrando em um domínio SIP usarão o mesmo pool de front-end para configuração automática. 
  
## <a name="dns-disaster-recovery"></a>DNS disaster recovery
<a name="DNSDR"> </a>

Para configurar o DNS para redirecionar o tráfego da Web do Skype for Business Server para os sites de recuperação de desastres (DR) e de failover, você precisa usar um provedor de DNS que ofereça suporte a GeoDNS. Você pode configurar seus registros DNS para dar suporte à recuperação de desastres, para que os recursos que usam serviços Web continuem mesmo se um pool de front-end inteiro ficar inativo. Esse recurso de DR suporta URLs simples de Descoberta Automática, de reunião e discado.
  
Você define e configura registros adicionais de host de DNS A (AAAA, se estiver usando IPv6) para resolução de serviços da Web internos e externos em seu provedor GeoDNS. As informações a seguir supõem pools emparelhados e geograficamente dispersos, GeoDNS suportado por seu provedor **** com DNS round robin **ou** configurado para usar o Pool1 como primário e failover para o Pool2, em caso de perda de comunicações ou falha de energia.
  
Todos os registros DNS nesta tabela são exemplos.
  
|**Registro GeoDNS**|**Registros de Pool**|**Registros CNAME**|**Registros DNS (selecione uma opção)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
   
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="DNSLB"> </a>

O balanceamento de carga do DNS normalmente é implantado no nível dos aplicativos. O aplicativo (por exemplo, um cliente que executa o Skype for Business), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o FQDN do pool.
  
Por exemplo, se houver três servidores front-end em um pool chamado pool01.contoso.com, acontecerá o seguinte:
  
- Clientes que executam o Skype for Business Query DNS para pool01.contoso.com. A consulta retorna três endereços de IP e os armazena em cache da seguinte maneira (em qualquer ordem):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- O cliente tenta estabelecer uma conexão TCP com um dos endereços IP. Em caso de falha, o cliente tenta o próximo endereço IP em cache.
    
- Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.
    
- Se o cliente tentar todas as entradas armazenadas em cache sem uma conexão bem-sucedida, o usuário receberá uma notificação de que nenhum servidor executando o Skype for Business Server está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga com base em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP dos servidores de seu pool. Normalmente, o DNS RR habilita a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A (ou AAAA, se estiver usando o endereçamento IPv6) falhar, a conexão falha. Portanto, o round robin de DNS é menos confiável do que o balanceamento de carga com base em DNS. O round robin de DNS ainda pode ser usado em conjunto com o balanceamento de carga DNS. 
  
O balanceamento de carga DNS é usado para:
  
- Balancear a carga do servidor para o servidor SIP para os servidores de borda.
    
- Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada.
    
- Evitar novas conexões a aplicativos UCAS (também conhecido como drenagem).
    
- Balanceamento de carga todo o tráfego de cliente para servidor entre clientes e servidores de borda.
    
O balanceamento de carga DNS não pode ser usado para:
  
- Tráfego da Web de cliente para servidor para seus servidores front-end ou director.
    
Para ter um pouco mais de detalhes sobre como um registro SRV DNS é selecionado quando registros DNS mutiple são retornados por uma consulta, o serviço de borda de acesso sempre escolhe o registro com a prioridade numérica mais baixa e, se for necessário um disjuntor, a maior espessura numérica. Isso é consistente com a [documentação da Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Assim, por exemplo, se seu primeiro registro SRV de DNS tem um peso 20 e uma prioridade 40 e seu segundo registro SRV de DNS tem um peso 10 e uma prioridade 50, o primeiro registro vai ser escolhido, pois tem a prioridade menor de 40. A Prioridade é sempre considerada primeiro, e esse é o primeiro host de destino de um cliente. E se dois destinos tiverem a mesma prioridade? 
  
Nesse caso, o peso é considerado. Pesos maiores devem ter maior probabilidade, nessas circunstâncias, de serem escolhidos. Os administradores DNS devem usar peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros contendo pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.
  
Então, o que acontece se vários registros SRV de DNS com prioridade e peso iguais forem retornados? Nessa situação, o serviço de borda de acesso escolherá primeiro o registro SRV que ele recebeu do servidor DNS.
  

