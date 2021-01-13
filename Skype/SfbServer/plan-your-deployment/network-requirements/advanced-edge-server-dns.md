---
title: Planejamento avançado de DNS do Servidor de Borda para o Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumo: revise os cenários das opções de implantação do Skype for Business Server. Quer você queira um único servidor ou prefira um pool de servidores com DNS ou HLB, este tópico deve ajudar.'
ms.openlocfilehash: 5a41baac30f3bf6a1e20ae34db009dae0cec40af
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825321"
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server"></a>Planejamento avançado de DNS do Servidor de Borda para o Skype for Business Server
 
**Resumo:** Revise os cenários das opções de implantação do Skype for Business Server. Quer você queira um único servidor ou prefira um pool de servidores com DNS ou HLB, este tópico deve ajudar.
  
No que diz respeito ao planejamento de DNS (Sistema de Nomes de Domínio) para o Skype for Business Server, há muitos fatores que podem ser relevantes para sua decisão. Se a estrutura de domínio da sua organização já estiver em uso, isso pode ser uma questão de analisar como você irá continuar. Vamos começar com os tópicos encontrados abaixo:
  
- [Passo a passo dos serviços de localização de clientes do Skype for Business](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [DNS de dupla cabeça](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Configuração automática sem DNS de dupla dupla](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [Recuperação de desastre de DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [Balanceamento de carga DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Passo a passo dos serviços de localização de clientes do Skype for Business
<a name="WalkthroughOfSkype"> </a>

Os clientes do Skype for Business são semelhantes às versões anteriores dos clientes do Lync na forma como encontram e acessam serviços no Skype for Business Server. Esta seção detalha o processo de localização do servidor.
  
1. lyncdiscoverinternal.\<domain\>
    
     *Esse é um registro de host A para o serviço de Descoberta Automática nos serviços Web internos.* 
    
2. lyncdiscover.\<domain\>
    
     *Este é um registro de host A para o serviço de Descoberta Automática nos serviços Web externos.* 
    
3. _sipinternaltls._tcp.\<domain\>
    
     *Este é um registro SRV para conexões TLS internas.* 
    
4. _sip._tls.\<domain\>
    
     *Este é um registro SRV para conexões TLS externas.* 
    
5. sipinternal.\<domain\>
    
     *Trata-se de um registro de host A para o pool de Front-End ou Diretor, que pode ser resolvido somente na rede interna.* 
    
6. sip.\<domain\>
    
     *Trata-se de um registro de host A para o pool de Front-End ou Diretor, que pode ser resolvido somente na rede interna.* 
    
7. sipexternal.\<domain\>
    
     *Esse é um registro de host A para o serviço de Borda de Acesso, quando o cliente é externo.* 
    
O serviço descoberta automática é sempre favorecido, pois esse é o método preferencial para o local do serviço, e os outros são métodos de fallback.
  
> [!NOTE]
> Ao criar registros SRV, é importante lembrar que eles precisam apontar para um DNS A (e AAAA se você estiver usando endereçamento IPv6) no mesmo domínio no qual o registro SRV dns está sendo criado. Por exemplo, se o registro SRV estiver contoso.com, o registro A (e AAAA) para o fabrikam.com. 
  
Se você estiver propenso a fazer isso, poderá configurar seu dispositivo móvel para descoberta manual de serviços. Se você quiser fazer isso, cada usuário precisará definir suas configurações de dispositivo móvel com os URIs completos do serviço de Descoberta Automática interna e externa, incluindo o protocolo e o caminho, da seguinte maneira:
  
- Para acesso externo: https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root
    
- Para acesso interno: https:// \<IntPoolFQDN\> /AutoDiscover/AutoDiscover.svc/Root
    
Recomendamos que você use a descoberta automática em vez da descoberta manual. Mas se você estiver solucionando problemas ou testando, as configurações manuais podem ser muito úteis.
  
## <a name="split-brain-dns"></a>DNS de dupla cabeça
<a name="SplitBrainDNS"> </a>

Esta é uma configuração DNS em que você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com solicitações internas, enquanto a segunda zona DNS lida com solicitações externas.
  
Por que uma empresa faria isso? Eles podem ter a necessidade de usar o mesmo namespace interna e externamente, mas é claro que isso fará com que muitos registros SRV e A de DNS sejam exclusivos para uma ou outra zona e, onde houver duplicação, os endereços IP associados a esses registros serão exclusivos.
  
Isso apresenta alguns desafios. O mais importante é que o DNS split-brain **não é suportado** para Mobilidade. Isso se deve aos registros DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve ser definido em seu servidor DNS externo, enquanto LyncDiscoverInternal precisa ser definido em seu servidor DNS interno).
  
Listamos os registros DNS das zonas interna e externa aqui, mas você pode encontrar exemplos detalhados na seção de requisitos ambientais do Servidor de Borda.
  
### <a name="internal-dns"></a>DNS Interno

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativa.
    
- Este contoso.com interno contém:
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para seu pool de Front-End, pool de Diretores ou nome do pool de Diretores e todos os servidores internos executando o Skype for Business Server na rede da sua organização.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para sua interface interna de Borda para cada Servidor de Borda do Skype for Business Server em sua rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a  interface interna de cada servidor proxy reverso em sua rede de perímetro (que é opcional para o gerenciamento de um proxy reverso).
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para configuração automática do cliente interno do Skype for Business Server (que é **opcional).**
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) ou CNAME para descoberta automática dos Serviços Web do Skype for Business Server (que é **opcional).**
    
- Todas as interfaces de Borda interna do Skype for Business Server em sua rede de perímetro usam essa zona DNS interna para resolver consultas para contoso.com.
    
- Todos os servidores que executam o Skype for Business Server e clientes que executam o Skype for Business Server na rede corporativa apontam para servidores DNS internos para resolver consultas no contoso.com ou usam o arquivo Host em cada Servidor de Borda e registros A e AAAA (se você estiver usando endereçamento IPv6) para o servidor do próximo salto (especificamente para o VIP do Diretor ou do pool de Diretores , VIP do pool de front-end ou servidor Standard Edition).
    
### <a name="external-dns"></a>DNS externo

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativa.
    
- Este contoso.com externo contém:
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) ou CNAME, para descoberta automática de serviços Web do Skype for Business Server. Isso é para uso com mobilidade.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para a interface externa de Borda de cada Servidor de Borda do Skype for Business Server ou VIP com balanceamento de carga de hardware (HLB) na rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para a interface externa do servidor proxy reverso ou (VIP para um pool de servidores proxy reverso), na rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para configuração automática de cliente do Skype for Business Server **(opcional).**
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem DNS de dupla dupla
<a name="NoSplitBrainDNS"> </a>

Se você não usar o DNS split-brain, a configuração automática interna dos clientes que executam o Skype for Business não funcionará, a menos que você esteja usando uma das soluções alternativas que temos aqui. Por que não? Como o Skype for Business Server requer que o URI sip do usuário corresponder ao domínio do pool de Front-End designado para configuração automática. Isso não mudou em versões anteriores do Lync Server.
  
Portanto, se você tiver dois domínios SIP em uso, precisará destes registros SRV dns:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se um usuário entrar como bob@contoso.com, esse registro funcionará para a configuração automática, pois o domínio SIP do usuário corresponde ao domínio do pool de front-end (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se um usuário entrar como alice@fabrikam.com, esse registro funcionará para a configuração automática do segundo domínio, novamente porque o domínio SIP corresponde ao pool de Front-End desse domínio.* 
    
Para levar o exemplo adiante, isso não funcionaria:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Um usuário que entrar como tim@litwareinc.com não funcionará para a configuração automática, pois seu domínio SIP (litwareinc.com) não combina com o domínio no pool (fabrikam.com).* 
    
Agora que sabemos tudo isso, se você precisar de requisitos automáticos para seus clientes do Skype for Business sem DNS split-brain, terá estas opções:
  
- **Objetos de Política de Grupo**
    
    Você pode usar GPOs (Objetos de Política de Grupo) para preencher os valores corretos do servidor.
    
    > [!NOTE]
    > Essa opção não habilita a configuração automática, mas automatiza a configuração manual. Se essa abordagem for usada, os registros SRV associados à configuração automática não são necessários. 
  
- **Comparação da zona interna**
    
    Você precisará criar uma zona em seu DNS interno que corresponda à zona dns externa (por exemplo, contoso.com) e, em seguida, criar registros A (e AAAA de DNS se você estiver usando endereçamento IPv6) que correspondam ao pool do Skype for Business Server usado para configuração automática.
    
    Por exemplo, se você tiver um usuário no pool01.contoso.net, mas entrar no Skype for Business como bob@contoso.com, crie uma zona DNS interna chamada contoso.com e, dentro dela, você precisará criar um registro DNS A (e AAAA se endereçamento IPv6 estiver sendo usado) para pool01.contoso.com.
    
- **Zona interna exata**
    
    Se a criação de uma zona inteira no DNS interno não for uma opção para você, você poderá criar zonas de ponto de pino (dedicadas) que correspondam aos registros SRV necessários para a configuração automática e popular essas zonas usando dnscmd.exe. Dnscmd.exe é necessário porque a interface do usuário DNS não suportará a criação de zonas de ponto de pino.
    
    Por exemplo, se seu domínio SIP for contoso.com e você tiver um pool de Front-End chamado pool01 que contenha dois Servidores Front-End, você precisará das seguintes zonas de ponto de pino e registros A no DNS interno:
    
  ```console
  dnscmd . /zoneadd _sipinternaltls._tcp.contoso.com. /dsprimary
  dnscmd . /recordadd _sipinternaltls._tcp.contoso.com. @ SRV 0 0 5061 pool01.contoso.com.
  dnscmd . /zoneadd pool01.contoso.com. /dsprimary
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.90
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  dnscmd . /recordadd pool01.contoso.com. @ A 192.168.10.91 
  dnscmd . /recordadd pool01.contoso.com. @ AAAA <IPv6 address>
  ```

    Você pode ter um segundo domínio SIP em seu ambiente. Nesse caso, você precisará das seguintes zonas pin-point e registros A em seu DNS interno:
    
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
> Você verá que o FQDN do pool de Front-End aparece duas vezes, mas com dois endereços IP diferentes. Isso porque o balanceamento de carga DNS é usado. Se o HLB for usado, haverá apenas uma única entrada de pool de Front-End. 
  
> [!NOTE]
> Além disso, os valores FQDN do pool de Front End mudam entre os exemplos contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso porque os usuários que estão fazendo o uso de qualquer domínio SIP usarão o mesmo pool de Front-End para configuração automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperação de desastre de DNS
<a name="DNSDR"> </a>

Para configurar o DNS para redirecionar o tráfego Web do Skype for Business Server para os sites de recuperação de desastres (DR) e failover, você precisa usar um provedor DNS que suporte GeoDNS. Você pode configurar seus registros DNS para dar suporte à recuperação de desastre, para que os recursos que usam serviços Web continuem mesmo se um pool de Front End inteiro ficar inonte. Esse recurso dr dá suporte a URLs simples de Descoberta Automática, Reunião e Discagem.
  
Defina e configure registros A (AAAA) de host DNS adicionais se estiver usando IPv6 para resolução interna e externa de serviços Web em seu provedor GeoDNS. Os detalhes a seguir pressupom pools emparelhados, geograficamente dispersos, e que o GeoDNS suportado por seu provedor tem **DNS** round robin ou está configurado para usar Pool1 como primário e faz o fails over para Pool2 em caso de perda de comunicações ou falha de energia. 
  
Todos os registros DNS nesta tabela são exemplos.
  
|**Registro GeoDNS**|**Registros de pool**|**Registros CNAME**|**Configurações de DNS (selecione uma opção)**|
|:-----|:-----|:-----|:-----|
|Meet-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias para Pool1InternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias a ser Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Meet-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Meet.contoso.com alias para Pool1ExternalWebFQDN.contoso.com  <br/> Meet.contoso.com alias para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias para Pool1InternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Dialin.contoso.com alias para Pool1ExternalWebFQDN.contoso.com  <br/> Dialin.contoso.com alias para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Lyncdiscoverinternal.contoso.com alias para Pool1InternalWebFQDN.contoso.com  <br/> Lyncdiscoverinternal.contoso.com alias para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Lyncdiscover.contoso.com alias para Pool1ExternalWebFQDN.contoso.com  <br/> Lyncdiscover.contoso.com alias para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Scheduler-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias para Pool1InternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
|Scheduler-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Scheduler.contoso.com alias para Pool1ExternalWebFQDN.contoso.com  <br/> Scheduler.contoso.com alias para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use primary, connect to secondary if there's a failure  <br/> |
   
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="DNSLB"> </a>

O balanceamento de carga DNS geralmente é implementado no nível do aplicativo. O aplicativo (por exemplo, um cliente executando o Skype for Business) tenta se conectar a um servidor em um pool conectando-se a um dos endereços IP retornados da consulta de registro DNS A e AAAA (se o endereçamento IPv6 for usado) para o FQDN do pool.
  
Por exemplo, se houver três Servidores front-end em um pool chamado pool01.contoso.com, ocorrerá o seguinte:
  
- Clientes executando o DNS de consulta do Skype for Business pool01.contoso.com. A consulta retorna três endereços IP e os armazena em cache da seguinte forma (em alguma ordem):
    
   |||
   |:-----|:-----|
   |pool01.contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01.contoso.com  <br/> |192.168.10.92  <br/> |
   
- O cliente tenta estabelecer uma conexão TCP com um dos endereços IP. Se isso falhar, ele tentará o próximo endereço IP armazenado em cache dessa lista.
    
- Se a conexão TCP for bem-sucedida, o cliente negocia o TLS para se conectar ao registrador principal no pool01.contoso.com.
    
- Se o cliente tentar todas as entradas em cache sem uma conexão bem-sucedida, o usuário receberá uma notificação de que nenhum servidor que executa o Skype for Business Server está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga baseado em DNS é diferente do round robin de DNS (DNS RR), que normalmente se refere ao balanceamento de carga, confiando no DNS para dar uma ordem diferente de endereços IP para os servidores em seu pool. Normalmente, o DNS RR habilita a distribuição de carga, mas não permite que você habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A (ou AAAA em um cenário IPv6) falhar, essa conexão falhará. Isso torna o DNS RR menos confiável do que o balanceamento de carga baseado em DNS. Você ainda pode usar o DNS RR em conjunto com o balanceamento de carga baseado em DNS, se precisar fazer isso. 
  
Use o balanceamento de carga DNS para:
  
- Balancear a carga SIP de servidor para servidor para os Servidores de Borda.
    
- Balanceamento de carga de aplicativos do Unified Communication Application Services (UCAS), como o Atendente Automático de Conferência, o Grupo de Resposta e o Estacionamento de Chamada.
    
- Impedir novas conexões com aplicativos UCAS (também conhecidos como esvaziamento).
    
- Balanceamento de carga de todo o tráfego de cliente para servidor entre clientes e Servidores de Borda.
    
Não é possível usar o balanceamento de carga DNS para:
  
- Tráfego da Web de cliente para servidor para seus Servidores Front-End ou um Diretor.
    
Para aprofundar um pouco mais sobre como um registro SRV dns é selecionado quando registros DNS mutiple são retornados por uma consulta, o serviço de Borda de Acesso sempre seleciona o registro com a prioridade numérica mais baixa e, se um desempate for necessário, o maior peso numérico. Isso é consistente com a [documentação da Internet Engineering Task Force.](https://www.ietf.org/rfc/rfc2782.txt)
  
Portanto, por exemplo, se seu primeiro registro SRV dns tiver um peso 20 e uma prioridade de 40, e seu segundo registro SRV DNS tiver um peso 10 e uma prioridade de 50, o primeiro registro será escolhido porque tem a prioridade mais baixa de 40. A prioridade sempre vai primeiro, e esse é o host que um cliente direcionará primeiro. E se houver dois destinos com a mesma prioridade? 
  
Nesse caso, o peso é considerado. Pesos maiores devem receber uma alta probabilidade, nessa circunstância, de serem selecionados. Os administradores de DNS devem usar o peso 0 quando não houver seleção de servidor para fazer. Na presença de registros com pesos maiores do que 0, os registros com peso 0 têm uma chance muito pequena de trazer selecionados.
  
Então, o que acontece se vários registros SRV dns com prioridade e peso iguais como retornados? Nessa situação, o serviço de Borda de Acesso escolherá primeiro o registro SRV que recebeu do servidor DNS.
  

