---
title: Resumo de DNS - Única borda consolidada com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50aae14309e55919eb3f65560cd7cd0e7f1b1283
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumo de DNS - Única borda consolidada com endereços IP públicos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2017-03-09_

Os requisitos de registro de DNS para acesso remoto ao Lync Server 2013 são bem simples em comparação com aqueles para certificados e portas. Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.

Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obter detalhes sobre a configuração automática de clientes que executam o Lync 2013 se a divisão do DNS não estiver configurada, consulte "configuração automática sem DNS Split-Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte à topologia de borda consolidada única mostrada na figura única de topologia de borda consolidada. Observe que determinados registros DNS são necessários somente para a configuração automática dos clientes Lync 2013 e Lync 2010. Se você pretende usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros de configuração automática associados não são necessários.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos do adaptador de rede do Edge Server

Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa. Por exemplo, conforme mostrado na topologia de borda consolidada única com endereços IP públicos configurados em [uma única aresta consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), o gateway padrão apontaria para o roteador externo no perímetro da Internet ou firewall que pode fornecer um endereço IP público. A relação de rede para interfaces do servidor de borda é uma relação de rota em vez de uma relação NAT.

Você pode configurar dois adaptadores de rede em seu servidor de borda da seguinte maneira:

  - **Adaptador de rede 1 (interface interna)**
    
    Interface interna com 172.25.33.10 atribuído.
    
    Não há nenhum gateway padrão definido.
    
    Verifique se há uma rota da rede que contém a interface interna de borda para qualquer rede que contenha servidores que estejam executando o Lync Server 2013 ou o Lync Server 2013 clientes (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 2 (interface externa)**
    
    Três endereços IP públicos são atribuídos a esse adaptador de rede, por exemplo 131.107.155.10 para Edge do Access, 131.107.155.20 para Edge de webconferência, 131.107.155.30 para Edge do AV.
    
    <div>
    

    > [!NOTE]
    > É possível, mas não recomendado, usar um único endereço IP para todas as três interfaces de serviço de borda. Embora isso salve endereços IP, ele exige números de porta diferentes para cada serviço. O número da porta padrão é 443/TCP, o que garante que os firewalls remotos permitam que o tráfego seja permitido. Alterar os valores de porta para (por exemplo) 5061/TCP para a borda de acesso, 444/TCP para a Web de Webconferência e 443/TCP para a borda do AV pode causar problemas para usuários remotos nos quais um firewall para os quais estejam atrás não permite o tráfego sobre 5061/TCP e 444/TCP. Além disso, três endereços IP distintos facilitam a solução de problemas devido à capacidade de filtrar por endereço IP.

    
    </div>
    
    O endereço IP público da borda do Access é primário com o gateway padrão definido para o roteador público (131.107.155.1).
    
    Os endereços de IP de borda da Web e de borda A/V são endereços IP adicionais na seção **avançado** das propriedades de **protocolo TCP/IPv4 (TCP/IPv4)** e **protocolo IP versão 6 (TCP/IPv6)** da **área local Propriedades de conexão** no Windows Server.

<div>


> [!TIP]
> A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções. A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda. O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e uma coleta de dados possivelmente mais concisa quando a solução de problemas é necessária



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>Registros DNS necessários para a aresta consolidada única com endereços IP públicos (exemplo)

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>Registro FQDN/DNS</th>
<th>Endereço IP/FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10</p></td>
<td><p>Interface externa da borda do Access (contoso) Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externa da borda de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externa de borda A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS/SRV/443 externos</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa do Access Edge. Obrigatório para configurar automaticamente o Lync 2013 e os clientes do Lync 2010 para trabalhar externamente. Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS/SRV/5061 externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Borda de acesso SIP interface externa necessária para a descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamada de Federação aprimorada nas versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interna de borda consolidada</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> Os registros listados na tabela anterior são mostrados com uma extensão <EM>.net</EM> ou uma extensão <EM>. com</EM> para realçar em qual zona eles precisam residir, se você não estiver usando o DNS Split-Brain. Se você estiver usando DNS Split-Brain, todos os registros ficarão na mesma zona, com a única distinção se eles estiverem na versão interna ou externa. Para obter detalhes, consulte "split-brain DNS" em <A href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>Registros necessários para Federação


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP/registro de host FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5061 externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Borda de acesso SIP interface externa necessária para a descoberta automática de DNS da sua Federação para outros parceiros de Federação potenciais e é conhecida como "domínios SIP permitidos" (chamado de Federação aprimorada nas versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p>



> [!IMPORTANT]
> Esse registro SRV é necessário para a mobilidade e a equipe de compensação da notificação por push

</td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo de DNS para o protocolo de mensagens extensíveis e de presença


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Local/tipo/porta</th>
<th>FQDN</th>
<th>Endereço IP/registro de host FQDN</th>
<th>Mapas para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/SRV/5269 externo</p></td>
<td><p>_xmpp-server._tcp.contoso.com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>Interface externa de proxy XMPP no serviço de borda do Access ou no pool de bordas. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync nos quais o contato com contatos do XMPP é permitido pela configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário compatível com o Lync. Um domínio XMPP permitido também deve ser configurado na política de parceiros federados do XMPP. Consulte os tópicos em <strong>Consulte também</strong> para obter detalhes adicionais</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por exemplo)</p></td>
<td><p>Endereço IP do serviço de borda de acesso em seu servidor de borda ou em um pool de bordas que hospeda o proxy XMPP</p></td>
<td><p>Aponta para o serviço de borda de acesso ou o pool de bordas que hospeda o serviço de proxy XMPP. Geralmente, o registro SRV que você cria aponta para esse registro de host (A ou AAAA)</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

