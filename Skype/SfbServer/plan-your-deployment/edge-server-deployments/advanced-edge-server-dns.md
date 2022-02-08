---
title: Planejar a implantação do Servidor de Borda Avançada para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: Revise cenários para Skype for Business Server de implantação, quer você queira um único servidor ou prefira um pool de servidores com DNS ou HLB.
ms.openlocfilehash: 6d2b0e53e3b0b94f19cdac70399a0bb512822cb8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62387979"
---
# <a name="plan-advanced-edge-server-deployment-for-skype-for-business-server"></a>Planejar a implantação do Servidor de Borda Avançada para Skype for Business Server
 
**Resumo:** Revise cenários para Skype for Business Server de implantação. Se você deseja um único servidor ou prefere um pool de servidores com DNS ou HLB, este tópico deve ajudar.
  
Quando se trata de planejamento do Sistema de Nomes de Domínio (DNS) para Skype for Business Server, muitos fatores podem entrar na sua decisão. Se a estrutura de domínio da sua organização já estiver em uso, isso pode ser uma questão de revisar como você irá prosseguir. Vamos começar com os tópicos encontrados abaixo:
  
- [Passo a passo de Skype for Business serviços de localização de clientes](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS de cérebro dividido](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configuração automática sem DNS de cérebro dividido](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Recuperação de desastre DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSDR)
    
- [Balanceamento de carga DNS](../../plan-your-deployment/network-requirements/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Passo a passo de Skype for Business serviços de localização de clientes
<a name="WalkthroughOfSkype"> </a>

Skype for Business clientes são semelhantes às versões anteriores dos clientes do Lync na forma como encontram e acessam serviços no Skype for Business Server. Esta seção detalha o processo de localização do servidor.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Este é um registro de host A para o serviço descoberta automática nos serviços Web internos.* 
    
2. lyncdiscover.\<domain\>
    
     *Este é um registro de host A para o serviço de Descoberta Automática nos serviços Web externos.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Este é um registro SRV para conexões TLS internas.* 
    
4. _sip._tls.\<domain\>
    
     *Este é um registro SRV para conexões TLS externas.* 
    
5. sipinternal.\<domain\>
    
     *Este é um registro de host A para o pool de Front-End ou Diretor, resolvêvel somente na rede interna.* 
    
6. sip.\<domain\>
    
     *Este é um registro de host A para o pool de Front-End ou Diretor, resolvêvel somente na rede interna.* 
    
7. sipexternal.\<domain\>
    
     *Este é um registro de host A para o serviço de Borda de Acesso, quando o cliente é externo.* 
    
O serviço de Descoberta Automática sempre é favorecido, pois esse é o método preferencial para o local do serviço, e os outros são métodos de fallback.
  
> [!NOTE]
> Ao criar registros SRV, é importante lembrar que eles precisam apontar para um DNS A (e AAAA se você estiver usando endereçamento IPv6) no mesmo domínio no qual o registro SRV DNS está sendo criado. Por exemplo, se o registro SRV estiver no contoso.com, o registro A (e AAAA) a que ele aponta não poderá estar fabrikam.com. 
  
Se você estiver inclinado a fazer isso, você pode configurar seu dispositivo móvel para a descoberta manual de serviços. Se é isso que você está procurando fazer, cada usuário precisa configurar suas configurações de dispositivo móvel com as URIs completas do serviço de Descoberta Automática interna e externa, incluindo o protocolo e o caminho, da seguinte maneira:
  
- Para acesso externo: https://\<ExtPoolFQDN\>/Descoberta Automática/autodiscoverservice.svc/Root
    
- Para acesso interno: https://\<IntPoolFQDN\>/Descoberta Automática/AutoDiscover.svc/Root
    
Recomendamos que você use a descoberta automática em vez da descoberta manual. Mas se você estiver fazendo alguns problemas ou testes, as configurações manuais podem ser muito úteis.
  
## <a name="split-brain-dns"></a>DNS de cérebro dividido
<a name="SplitBrainDNS"> </a>

Esta é uma configuração DNS em que você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com solicitações internas, enquanto a segunda zona DNS lida com solicitações externas.
  
Por que uma empresa faria isso? Eles podem ter um requisito para usar o mesmo namespace interna e externamente, mas é claro que isso levará a muitos registros DNS SRV e A serem exclusivos de uma zona ou outra, e onde há duplicação, os endereços IP associados a esses registros seriam exclusivos.
  
Isso apresenta alguns desafios. O mais importante é que o DNS de cérebro dividido **não é suportado** para o Mobility. Isso se deve aos registros DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover precisa ser definido em seu servidor DNS externo, enquanto o LyncDiscoverInternal precisa ser definido em seu servidor DNS interno).
  
Vamos listar os registros DNS para as zonas internas e externas aqui, mas você pode encontrar exemplos detalhados na seção Requisitos ambientais do Servidor de Borda.
  
### <a name="internal-dns"></a>DNS Interno

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual ela é autoritativa.
    
- Este contoso.com interno contém:
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para seu pool de Front-End, pool de diretores ou nome do pool de Diretores e todos os servidores internos que executam Skype for Business Server na rede da sua organização.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para sua interface interna de Borda para cada servidor de borda Skype for Business Server em sua rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor proxy reverso em sua rede  de perímetro (que é opcional para o gerenciamento de um proxy reverso).
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para configuração automática de cliente Skype for Business Server interna (que é **opcional** ).
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME para descoberta automática de serviços Web Skype for Business Server web (que é **opcional** ).
    
- Todas as Skype for Business Server de Borda internas em sua rede de perímetro usam essa zona DNS interna para resolver consultas contoso.com.
    
- Todos os servidores que executam o Skype for Business Server e clientes executando o Skype for Business Server na rede corporativa apontam para servidores DNS internos para resolver consultas para contoso.com ou usam o arquivo Host em cada Servidor de Borda e listaR registros A e AAAA (se você estiver usando endereçamento IPv6) para o servidor de próximo salto (especificamente para o pool diretor ou diretor)  VIP, VIP do pool front-end ou Edição Standard servidor).
    
### <a name="external-dns"></a>DNS externo

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual ela é autoritativa.
    
- Este contoso.com externo contém:
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou registros CNAME, para descoberta automática de serviços Web Skype for Business Server web. Isso é para uso com mobilidade.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para a interface externa de borda de cada Skype for Business Server servidor de borda ou VIP de carga de hardware balanceada (HLB) na rede de perímetro.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para a interface externa do servidor proxy reverso ou (VIP para um pool de servidores proxy reverso), na rede de perímetro.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para Skype for Business Server configuração automática do cliente (**opcional** ).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem DNS de cérebro dividido
<a name="NoSplitBrainDNS"> </a>

Se você não usar DNS de cérebro dividido, a configuração automática interna dos clientes que executam Skype for Business não funcionará, a menos que você esteja usando uma das soluções alternativas que temos aqui. Por que não? Como Skype for Business Server requer que o URI SIP do usuário seja igual ao domínio do pool de Front-End designado para configuração automática. Isso não mudou de versões anteriores do Lync Server.
  
Portanto, se você tiver dois domínios SIP em uso, precisará desses registros SRV DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se um usuário entrar como bob@contoso.com, esse registro funcionará para a configuração automática, pois o domínio SIP do usuário corresponde ao domínio do pool de Front-End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se um usuário entrar como alice@fabrikam.com, esse registro funcionará para a configuração automática do segundo domínio, novamente porque o domínio SIP corresponde ao pool de Front-End desse domínio.* 
    
Para levar o exemplo adiante, isso não funcionaria:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Um usuário que faz logo tim@litwareinc.com não funcionará para a configuração automática, pois seu domínio SIP (litwareinc.com) não corresponderá ao domínio no pool (fabrikam.com).* 
    
Portanto, agora que sabemos tudo isso, se você precisar de requisito automático para seus clientes Skype for Business sem DNS de cérebro dividido, você tem estas opções:
  
- **Objetos de Política de Grupo**
    
    Você pode usar GPOs (Objetos de Política de Grupo) para preencher os valores de servidor corretos.
    
    > [!NOTE]
    > Essa opção não habilita a configuração automática, mas automatiza a configuração manual. Se essa abordagem for usada, os registros SRV associados à configuração automática não são necessários. 
  
- **Comparação da zona interna**
    
    Você precisará criar uma zona em seu DNS interno que corresponda à zona DNS externa (por exemplo, contoso.com) e, em seguida, criar registros DNS A (e AAAA se você estiver usando endereçamento IPv6) que correspondam ao pool Skype for Business Server usado para configuração automática.
    
    Por exemplo, se você tiver um usuário no pool01.contoso.net, mas entrar no Skype for Business como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e, dentro dela, você precisará criar um registro DNS A (e AAAA se o endereçamento IPv6 estiver sendo usado) para pool01.contoso.com.
    
- **Zona interna exata**
    
    Se a criação de uma zona inteira em seu DNS interno não for uma opção para você, você poderá criar zonas de ponto de pino (dedicadas) que correspondam aos registros SRV necessários para configuração automática e preencher essas zonas usando dnscmd.exe. Dnscmd.exe é necessário porque a interface do usuário DNS não suportará a criação de zonas de ponto de pino.
    
    Por exemplo, se o domínio SIP for contoso.com e você tiver um pool de Front-End chamado pool01 que contenha dois Servidores Front-End, você precisará das seguintes zonas de ponto de pino e registros A em seu DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Você pode ter um segundo domínio SIP em seu ambiente. Nesse caso, você precisará das seguintes zonas de ponto de pino e registros A em seu DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.fabrikam.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.fabrikam.com. @ SRV 0 0 5061 pool01.fabrikam.com.
  dnscmd . /zoneadd pool01.fabrikam.com. /dsprimary
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.fabrikam.com. @ A 192.168.10.91
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

> [!NOTE]
> Você verá o FQDN do pool de front-end aparecer duas vezes, mas com dois endereços IP diferentes. Isso porque o balanceamento de carga DNS é usado. Se o HLB for usado, haverá apenas uma única entrada de pool front-end. 
  
> [!NOTE]
> Além disso, os valores do FQDN do pool de front-end mudam entre os exemplos contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso porque os usuários que estão fazendo o registro em um dos domínios SIP usarão o mesmo pool de Front-End para configuração automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperação de desastre DNS
<a name="DNSDR"> </a>

Para configurar o DNS para redirecionar Skype for Business Server web para seus sites de recuperação de desastres (DR) e failover, você precisa usar um provedor DNS que oferece suporte a GeoDNS. Você pode configurar seus registros DNS para dar suporte à recuperação de desastres, para que os recursos que usam serviços Web continuem mesmo que um pool inteiro de Front-End seja baixado. Esse recurso dr dá suporte às URLs simples de Descoberta Automática, Reunião e Discagem.
  
Você define e configura registros adicionais de host DNS A (AAAA) se estiver usando registros IPv6 para resolução interna e externa de serviços Web em seu provedor GeoDNS. Os detalhes a seguir pressupom pools emparelhados, geograficamente dispersos, e que o GeoDNS  suportado pelo seu provedor **tem DNS** round-robin ou está configurado para usar Pool1 como principal e falha no Pool2 se houver qualquer perda de comunicações ou falha de energia.
  
Todos os registros DNS nesta tabela são exemplos.
  
|**Registro GeoDNS**|**Registros de pool**|**Registros CNAME**|**Configurações dns (selecione uma opção)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>   <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com  <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-int.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com para Meet-ext.geolb.contoso.com   <br/>  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário se houver uma falha  <br/> |
   
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="DNSLB"> </a>

O balanceamento de carga DNS geralmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando Skype for Business), tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o FQDN do pool.
  
Por exemplo, se houver três Servidores Front-End em um pool chamado pool01.contoso.com, o seguinte ocorrerá:
  
- Clientes executando Skype for Business DNS de consulta para pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte forma (em alguma ordem):
    
   |&nbsp;|&nbsp;|
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- O cliente tenta estabelecer uma conexão TCP com um dos endereços IP. Se isso falhar, ele tentará o próximo endereço IP que será armazenado em cache dessa lista.
    
- Se a conexão TCP for bem-sucedida, o cliente negociará tLS para se conectar ao registrador principal no pool01.contoso.com.
    
- Se o cliente tentar todas as entradas armazenadas em cache sem uma conexão bem-sucedida, o usuário receberá uma notificação de que nenhum servidor executando Skype for Business Server está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga baseado em DNS é diferente do DNS round robin (DNS RR), que normalmente se refere ao balanceamento de carga, confiando no DNS para dar uma ordem diferente de endereços IP para os servidores em seu pool. Normalmente, o DNS RR habilita a distribuição de carga, mas não permite que você habilita o failover. Por exemplo, se a conexão com o único endereço IP retornado pela consulta DNS A (ou AAAA em um cenário IPv6) falhar, essa conexão falhará. Isso torna o DNS RR menos confiável do que o balanceamento de carga baseado em DNS. Você ainda pode usar o DNS RR em conjunto com o balanceamento de carga baseado em DNS, se precisar fazer isso. 
  
Use o balanceamento de carga DNS para:
  
- Balancear o SIP de servidor para servidor para os Servidores de Borda.
    
- Balanceamento de carga Aplicativos UCAS (Unified Communication Application Services), como conferência Atendedor Automático, Grupo de Resposta e Estacionamento de Chamada.
    
- Impedir novas conexões com aplicativos UCAS (também conhecidos como esvaziamento).
    
- Balancear de carga todo o tráfego de cliente para servidor entre clientes e Servidores de Borda.
    
Não é possível usar o balanceamento de carga DNS para:
  
- Tráfego web de cliente para servidor para seus Servidores Front-End ou um Diretor.
    
Para aprofundar um pouco mais a forma como um registro SRV DNS é selecionado quando vários registros DNS são retornados por uma consulta, o serviço de Borda de Acesso sempre seleciona o registro com a menor prioridade numérica e, se um desempate for necessário, a maior carga numérica. Isso é consistente com a documentação da [Força de Tarefa de Engenharia da Internet](https://www.ietf.org/rfc/rfc2782.txt).
  
Portanto, por exemplo, se seu primeiro registro SRV DNS tiver um peso de 20 e uma prioridade de 40, e seu segundo registro SRV DNS tiver um peso de 10 e uma prioridade de 50, o primeiro registro será escolhido porque ele tem a prioridade mais baixa de 40. A prioridade sempre é a primeira, e esse é o host que um cliente irá direcionar primeiro. E se houver dois destinos com a mesma prioridade? 
  
Nesse caso, o peso é considerado. Pesos maiores devem receber uma alta probabilidade, nessa circunstância, de ser selecionado. Os administradores DNS devem usar o peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros que contenham pesos maiores que 0, os registros com peso 0 têm uma pequena chance de trazer selecionados.
  
Então, o que acontece se vários registros SRV DNS com igual prioridade e peso como retornados? Nessa situação, o serviço de Borda de Acesso escolherá primeiro o registro SRV que ele recebeu do servidor DNS.
  

