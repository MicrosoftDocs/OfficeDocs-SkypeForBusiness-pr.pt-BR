---
title: Advanced DNS do servidor de borda planejando Skype para Business Server 2015
ms.author: heidip
author: microsoftheidi
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: f3a5895f-f64f-44eb-9a5e-8d606ac1fc38
description: 'Resumo: Revise os cenários de Skype para opções de implantação de negócios Server 2015. Se você deseja que um único servidor ou preferir um pool de servidores com o DNS ou HLB, este tópico deve ajudar.'
ms.openlocfilehash: 52a083f0df806d719cba2b596ded1e016c838ea8
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="advanced-edge-server-dns-planning-for-skype-for-business-server-2015"></a>Advanced DNS do servidor de borda planejando Skype para Business Server 2015
 
**Resumo:** analise cenários para as opções de implantação do Skype for Business Server 2015. Se você quiser um único servidor ou se preferir um pool de servidores com DNS ou HLB, este tópico deve ajudar.
  
Quando se trata de sistema de nome de domínio (DNS) planejando Skype para Business Server 2015, existem muitos fatores que podem ser reproduzidos em sua decisão. Se a estrutura de domínio de sua organização já estiver em vigor, pode ser só uma questão de analisar como continuar. Começaremos com os tópicos abaixo:
  
- [Walkthrough of Skype for Business clients locating services](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#WalkthroughOfSkype)
    
- [Split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#SplitBrainDNS)
    
- [Automatic configuration without split-brain DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#NoSplitBrainDNS)
    
- [DNS disaster recovery](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSDR)
    
- [DNS load balancing](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB)
    
## <a name="walkthrough-of-skype-for-business-clients-locating-services"></a>Walkthrough of Skype for Business clients locating services
<a name="WalkthroughOfSkype"> </a>

Skype para clientes corporativos são semelhantes às versões anteriores dos clientes do Lync em como eles encontrar e acessar os serviços Skype para Business Server 2015. Esta seção detalha o processo de local do servidor.
  
1. lyncdiscoverinternal. \<domínio\>
    
     *Um registro de host do serviço de Descoberta Automática nos serviços Web internos.* 
    
2. lyncdiscover. \<domínio\>
    
     *Um registro de host do serviço de Descoberta Automática nos serviços Web externos.* 
    
3. sipinternaltls. \<domínio\>
    
     *Um registro SRV para conexões TLS internas.* 
    
4. _sip._tls. \<domínio\>
    
     *Um registro SRV para conexões TLS externas.* 
    
5. sipinternal. \<domínio\>
    
     *Esse é um registro host para o pool de Front-End ou diretor, pode ser resolvido apenas na rede interna.* 
    
6. SIP. \<domínio\>
    
     *Esse é um registro host para o pool de Front-End ou diretor, pode ser resolvido apenas na rede interna.* 
    
7. sipexternal. \<domínio\>
    
     *Este é um registro host para o serviço de borda de acesso, quando o cliente está externo.* 
    
O serviço de Descoberta Automática é sempre considerado o método preferencial para local do serviço, e os outros estão métodos de fallback.
  
> [!NOTE]
> Ao criar registros SRV, é importante lembrar que eles devem apontar para um DNS A (e AAAA, se você estiver usando endereçamento IPv6) no mesmo domínio em que o registro SRV do DNS for criado. Por exemplo, se o registro SRV estiver em contoso.com, o registro A (e AAAA) para o qual aponta não poderá estar em fabrikam.com. 
  
Se você quiser, é possível definir seu dispositivo móvel para descoberta manual de serviços. Se for isso que você desejar fazer, cada usuário precisa definir as configurações de seus dispositivos móveis com os URIs completos, internos e externos, do serviço de Descoberta Automática, incluindo o protocolo e o caminho, da seguinte forma:
  
- Para acesso externo: https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root
    
- Para acesso interno: https://\<IntPoolFQDN\>/AutoDiscover/AutoDiscover.svc/Root
    
Recomendamos que você use a descoberta automática em oposição à descoberta manual. Mas, se você estiver solucionando problemas ou fazendo testes, as configurações manuais podem ser muito úteis.
  
## <a name="split-brain-dns"></a>DNS de dupla personalidade
<a name="SplitBrainDNS"> </a>

Esta é uma configuração de DNS na qual você tem duas zonas DNS com o mesmo namespace. A primeira zona DNS lida com os pedidos internos, enquanto a segunda zona DNS lida com os pedidos externos.
  
Por que uma empresa faria isso? Pode haver a necessidade de usar o mesmo namespace internamente e externamente, mas isso levaria a muitos SRV e registros A de DNS exclusivos para uma ou outra zona e, onde houver duplicação, os endereços IP associados a esses registros seriam exclusivo.
  
Isso apresenta alguns desafios. O mais importante é que Split-Brain DNS **não tem suporte** para mobilidade. Isso ocorre por causa dos registros de DNS LyncDiscover e LyncDiscoverInternal (LyncDiscover deve ser definido no servidor DNS externo, enquanto que LyncDiscoverInternal deve ser definido em seu servidor DNS interno).
  
Vai listamos os registros DNS para as zonas internos e externos aqui, mas você pode encontrar exemplos detalhados na seção de requisitos de ambiente de servidor de borda.
  
### <a name="internal-dns"></a>DNS Interno

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativo.
    
- Essa zona interna contoso.com contém:
    
  - Os registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para seu pool de Front-End, o pool de diretor ou nome do pool de diretor e todos os servidores internos executando Skype para Business Server 2015 na rede da sua organização.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) registra sua interface interna de borda para cada Skype para o servidor de borda de 2015 Business Server na rede de perímetro.
    
  - Os registros DNS A e AAAA (se você estiver usando endereçamento IPv6) para a interface interna de cada servidor de proxy reverso na rede de perímetro (que é **opcional** para gerenciamento de um proxy reverso).
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para Skype interno para configuração automática do cliente Business Server 2015 (que é **opcional** ).
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou CNAME para descoberta automática do Skype para Business Server 2015 Web Services (que é **opcional** ).
    
- Todos os seu Skype para interfaces de borda internas Business Server 2015 na rede de perímetro use esta zona DNS interna para resolver consultas em contoso.com.
    
- Todos os servidores que executam o Skype para 2015 do servidor de negócios e clientes executando o Skype para Business Server 2015 na rede corporativa, apontem para servidores DNS internos para resolver consultas em contoso.com ou uso do arquivo de Host em cada servidor de borda e a lista A e AAAA se ( você estiver usando endereçamento IPv6) registros para o servidor de próximo salto (especificamente para o Diretor ou VIP do pool de diretor, Front End pool VIP ou servidor Standard Edition).
    
### <a name="external-dns"></a>DNS Externo

- Contém uma zona DNS chamada (por exemplo) contoso.com, para a qual é autoritativo
    
- Essa zona externa contoso.com contém:
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) ou CNAME registra, para a descoberta automática do Skype para serviços da web de negócios Server 2015. Isso é para usar com mobilidade.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para a interface externa da borda de cada Skype para o servidor de borda do Business Server 2015 ou carga de hardware balanceada VIP (HLB) na rede de perímetro.
    
  - Registros DNS A e AAAA (se você estiver usando endereçamento IPv6) e SRV para a interface externa do servidor de proxy reverso ou (VIP para um pool de servidores de proxy reverso), na rede de perímetro.
    
  - DNS A e AAAA (se você estiver usando endereçamento IPv6) e registros SRV para Skype para Business Server 2015 configuração automática do cliente (**opcional**).
    
## <a name="automatic-configuration-without-split-brain-dns"></a>Configuração automática sem DNS de dupla personalidade
<a name="NoSplitBrainDNS"> </a>

Se você não usar Split-Brain DNS, interna configuração automática de clientes executando o Skype para negócios não funcionará a menos que você estiver usando uma das soluções que temos aqui. Por que não? Porque Skype para Business Server 2015 requer o URI do SIP do usuário corresponder ao domínio do pool de Front-End designado para configuração automática. Isso não mudou de versões anteriores do Lync Server.
  
Portanto, se você tiver dois domínios SIP em uso, você precisará desses registros SRV de DNS:
  
- _sipinternaltls._tcp.contoso.com. 86400 IN SRV 0 0 5061 pool01.contoso.com
    
     *Se um usuário entrar como bob@contoso.com, este registro funcionaria para configuração automática, como o domínio SIP do usuário corresponde ao domínio do pool de Front-End (contoso.com).* 
    
- _sipinternaltls._tcp.fabrikam.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *Se um usuário entrar como alice@fabrikam.com, este registro funcionaria para configuração automática do segundo domínio, novamente, porque o domínio SIP coincide com o pool de Front-End para esse domínio.* 
    
Para aprofundar mais o exemplo, isso não funcionaria:
  
- _sipinternaltls._tcp.litwareinc.com. 86400 IN SRV 0 0 5061 pool01.fabrikam.com
    
     *O logon de usuário tim@litwareinc.com não funcionará para a configuração automática, porque seu domínio SIP (litwareinc.com) não corresponde ao domínio do pool (fabrikam.com).* 
    
Portanto, agora que sabemos que tudo isso, se você precisar requisito automático para sua Skype para clientes corporativos sem Split-Brain DNS, você tem estas opções:
  
- **Objetos de Política de Grupo**
    
    Você pode usar Objetos de Política de Grupo (GPOs) para popular os valores de servidor corretos.
    
    > [!NOTE]
    > Essa opção não habilita a configuração automática, mas automatiza a configuração manual. Se essa abordagem for utilizada, os registros SRV associados à configuração automática não serão necessários. 
  
- **Zona interna correspondente**
    
    Você precisará criar uma zona em seu DNS interno que coincida com sua zona de DNS externa (por exemplo, contoso.com) e, em seguida, crie A DNS (e AAAA se você estiver usando endereçamento IPv6) registros que correspondem do Skype para pool de negócios Server 2015 usado para automático configuração.
    
    Por exemplo, se você tiver um usuário hospedado no pool01. contoso.NET, mas sinais em Skype para negócios como bob@contoso.com, criar uma zona DNS interna, chamada contoso.com e dentro dela você precisa criar um DNS A (e AAAA se acessos do endereçamento IPv6) registro pool01. contoso.com.
    
- **Zona interna exata**
    
    Se criar uma zona inteira no DNS interno não for uma opção, você poderá criar zonas exatas (dedicadas) que correspondam aos registros SRV necessários para a configuração automática e popular estas zonas usando o dnscmd.exe. O dnscmd.exe é necessário porque a interface do usuário do DNS não é compatível com a criação de zonas exatas.
    
    Por exemplo, se o domínio SIP for contoso.com, e você tiver um pool de Front-End chamado pool01 que contém dois servidores Front-End, você precisará seguintes zonas exatas e registros em seu DNS interno:
    
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
> Você verá o pool de Front-End que FQDN aparece duas vezes, mas com dois endereços IP diferentes. Isso ocorre porque o balanceamento de carga DNS é usado. Se HLB for usado, seria só haver uma única entrada de pool de Front-End. 
  
> [!NOTE]
> Além disso, os valores FQDN do pool de Front-End alteram entre os exemplos de contoso.com e fabrikam.com, mas os endereços IP permanecem os mesmos. Isso ocorre porque os usuários que estiver entrando de qualquer domínio SIP usarão o mesmo pool de Front-End para configuração automática. 
  
## <a name="dns-disaster-recovery"></a>Recuperação de desastres de DNS
<a name="DNSDR"> </a>

Para configurar o DNS para redirecionar Skype para tráfego de web Business Server 2015 sua recuperação de desastres (DR) e em sites de failover, você precisará usar um provedor DNS que ofereça suporte a GeoDNS. Você pode configurar seus registros DNS para oferecer suporte a recuperação de desastres, para que os recursos que utilizam serviços web continuam mesmo se um pool de Front-End inteiro cair. Esse recurso de DR suporta URLs simples de Descoberta Automática, de reunião e discado.
  
Você define e configura registros adicionais de host de DNS A (AAAA, se estiver usando IPv6) para resolução de serviços da Web internos e externos em seu provedor GeoDNS. As informações a seguir supõem pools emparelhados e geograficamente dispersos, GeoDNS suportado por seu provedor **** com DNS round robin **ou** configurado para usar o Pool1 como primário e failover para o Pool2, em caso de perda de comunicações ou falha de energia.
  
Todos os registros DNS nesta tabela são exemplos.
  
|**Registro GeoDNS**|**Registros de pool**|**Registros CNAME**|**Configurações de DNS (selecione uma opção)**|
|:-----|:-----|:-----|:-----|
|Reunir-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com para Pool1InternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Reunir-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Meet.contoso.com para Pool1ExternalWebFQDN.contoso.com  <br/> Alias Meet.contoso.com para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Dialin-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com para Pool1InternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Dialin-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Dialin.contoso.com para Pool1ExternalWebFQDN.contoso.com  <br/> Alias Dialin.contoso.com para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Lyncdiscoverint-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscoverinternal.contoso.com para Pool1InternalWebFQDN.contoso.com  <br/> Alias Lyncdiscoverinternal.contoso.com para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Lyncdiscover-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Lyncdiscover.contoso.com para Pool1ExternalWebFQDN.contoso.com  <br/> Alias Lyncdiscover.contoso.com para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Agendador-int.geolb.contoso.com  <br/> |Pool1InternalWebFQDN.contoso.com  <br/> Pool2InternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com para Pool1InternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com para Pool2InternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
|Agendador-ext.geolb.contoso.com  <br/> |Pool1ExternalWebFQDN.contoso.com  <br/> Pool2ExternalWebFQDN.contoso.com  <br/> |Alias Scheduler.contoso.com para Pool1ExternalWebFQDN.contoso.com  <br/> Alias Scheduler.contoso.com para Pool2ExternalWebFQDN.contoso.com  <br/> |Round Robin entre pools  <br/> **OU** <br/> Use o primário, conecte-se ao secundário em caso de falha  <br/> |
   
## <a name="dns-load-balancing"></a>Balanceamento de carga DNS
<a name="DNSLB"> </a>

O balanceamento de carga do DNS normalmente é implantado no nível dos aplicativos. O aplicativo (por exemplo, um cliente executando o Skype para negócios), tenta se conectar a um servidor em um pool Estabelecendo conexão com um dos endereços IP retornados da consulta para o FQDN do pool de registrar o DNS A e AAAA (se for usado o endereçamento IPv6).
  
Por exemplo, se houver três servidores Front-End em um pool chamado pool01. contoso.com, o seguinte aconteceria:
  
- Clientes executando o Skype para negócios consultam DNS para pool01. contoso.com. A consulta retorna três endereços IP e a armazena em cache da seguinte maneira (em alguma ordem):
    
   |||
   |:-----|:-----|
   |pool01. contoso.com  <br/> |192.168.10.90  <br/> |
   |pool01. contoso.com  <br/> |192.168.10.91  <br/> |
   |pool01. contoso.com  <br/> |192.168.10.92  <br/> |
   
- O cliente tenta estabelecer uma conexão TCP com um dos endereços IP. Em caso de falha, o cliente tenta o próximo endereço IP em cache.
    
- Se a conexão TCP for bem -sucedida, o cliente negocia o TLS para se conectar ao Registrador Avançado primário em pool01.contoso.com.
    
- Se o cliente experimenta entradas tudo em cache sem uma conexão bem-sucedida, o usuário receberá uma notificação de que nenhum servidor executando o Skype para Business Server 2015 está disponível no momento.
    
> [!NOTE]
> O balanceamento de carga com base em DNS é diferente do round robin de DNS (DNS RR), que normalmente faz referência ao balanceamento de carga confiando no DNS para fornecer uma ordem diferente de endereços IP dos servidores de seu pool. Normalmente, o DNS RR habilita a distribuição de carga, mas não habilita o failover. Por exemplo, se a conexão com um endereço IP retornado pela consulta DNS A (ou AAAA, se estiver usando o endereçamento IPv6) falhar, a conexão falha. Portanto, o round robin de DNS é menos confiável do que o balanceamento de carga com base em DNS. O round robin de DNS ainda pode ser usado em conjunto com o balanceamento de carga DNS. 
  
O balanceamento de carga DNS é usado para:
  
- Servidor-para-servidor SIP para os servidores de borda de balanceamento de carga.
    
- Balanceamento de carga de aplicativos de Serviços de Aplicativos de Comunicações Unificadas (UCAS), como o Atendedor Automático de Conferências, Grupo de Resposta e Estacionamento de Chamada.
    
- Evitar novas conexões a aplicativos UCAS (também conhecido como drenagem).
    
- O balanceamento de carga todo o tráfego cliente-para-servidor entre clientes e servidores de borda.
    
O balanceamento de carga DNS não pode ser usado para:
  
- Tráfego web cliente-para-servidor para seus servidores Front-End ou um diretor.
    
Para ir um pouco mais aprofundado na como um registro de SRV de DNS selecionados quando o texto com várias registros DNS forem retornados por uma consulta, o serviço de borda de acesso sempre seleciona o registro com a prioridade numérica mais baixa e, se desempate for necessária, o peso numérico mais alto. Isso é consistente com [a documentação do Internet Engineering Task Force](https://www.ietf.org/rfc/rfc2782.txt).
  
Assim, por exemplo, se seu primeiro registro SRV de DNS tem um peso 20 e uma prioridade 40 e seu segundo registro SRV de DNS tem um peso 10 e uma prioridade 50, o primeiro registro vai ser escolhido, pois tem a prioridade menor de 40. A Prioridade é sempre considerada primeiro, e esse é o primeiro host de destino de um cliente. E se dois destinos tiverem a mesma prioridade? 
  
Nesse caso, o peso é considerado. Pesos maiores devem ter maior probabilidade, nessas circunstâncias, de serem escolhidos. Os administradores DNS devem usar peso 0 quando não houver nenhuma seleção de servidor para fazer. Na presença de registros contendo pesos maiores que 0, os registros com peso 0 devem ter uma chance muito pequena de serem selecionados.
  
Então, o que acontece se vários registros SRV de DNS com prioridade e peso iguais forem retornados? Nessa situação, a borda de acesso a serviço escolherá o registro SRV que ele obteve do administrador do servidor DNS primeiro.
  

