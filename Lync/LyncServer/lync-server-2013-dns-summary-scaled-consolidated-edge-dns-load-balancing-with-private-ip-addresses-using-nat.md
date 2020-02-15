---
title: 'Lync Server 2013: Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: 11bc7b84-91cf-48f9-ad0e-06ad30b46a2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398201(v=OCS.15)
ms:contentKeyID: 48183447
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d01a7ea8c2f27c9cbd2a90624743dac55116c784
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Resumo de DNS-borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas. Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.

Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obter detalhes sobre como configurar a configuração automática dos clientes do Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte a seção "configuração automática sem DNS de Split Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única. Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes do Lync 2013. Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos do adaptador de rede do servidor de borda

Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa. Por exemplo, conforme mostrado na figura de cenário de borda consolidada em escala na [borda consolidada em escala, o balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md), o gateway padrão apontaria para o firewall externo.

Você pode configurar os dois adaptadores de rede em seu Servidor de Borda conforme a seguir:

  - **Adaptador de rede 1 - Nó 1 (Interface interna)**
    
    Interface interna com 172.25.33.10 designados.
    
    Nenhum gateway padrão definido.
    
    Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 2 - Nó 2 (Interface externa)**
    
    Interface interna com 172.25.33.40 designados.
    
    Nenhum gateway padrão está definido.
    
    Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 1 (Interface interna)**
    
    Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 10.45.16.10 para Borda de Acesso, 10.45.16.20 para Borda de Webconferência e 10.45.16.30 para Borda de AV.
    
    <div>
    

    > [!NOTE]  
    > É possível, embora não recomendável, usar um único endereço IP para todas as três interfaces de serviço de Borda. Apesar de economizar endereços IP, isso requer números de porta diferentes para cada serviço. O número de porta padrão é 443/TCP, o que garante que a maior parte dos firewalls remotos permita o tráfego. Alterar os valores de porta para (por exemplo) 5061/TCP para Borda de Acesso, 444/TCP para Borda de Webconferência e 443/TCP para Borda de AV pode causar problemas para usuários remotos cujo firewall atrás do qual estão não permitir o tráfego sobre as portas 5061/TCP e 444/TCP. Além disso, três endereços IP distintos facilita a solução de problemas pois permite filtragem por endereço IP.

    
    </div>
    
    O endereço IP público da Borda de Acesso é o principal com o gateway padrão definido como o roteador integrado (10.45.16.1).
    
    Endereços IP privados de Borda de Webconferências e de A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo IP versão 4 (TCP/IPv4)** e do **Protocolo IP versão 6 (TCP/IPv6)** das **Propriedades da Conexão Local** no Windows Server.

  - **Adaptador de rede 2 Nó 2 (Interface externa)**
    
    Três endereços IP privados são atribuídos a este adaptador de rede, por exemplo, 10.45.16.11 para Borda de Acesso, 10.45.16.21 para Borda de Webconferência e 10.45.16.31 para Borda de AV.
    
    O endereço IP público da Borda de Acesso é o principal com o gateway padrão definido como roteador integrado (10.45.16.1).
    
    Endereços IP privados de Borda de Webconferências e de A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo IP versão 4 (TCP/IPv4)** e do **Protocolo IP versão 6 (TCP/IPv6)** das **Propriedades da Conexão Local** no Windows Server.

<div>


> [!TIP]  
> A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções. A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda. O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-example"></a>Registros de DNS necessários para a Topologia de borda consolidada em escala (DNS com balanceamento de carga): Borda Consolidada

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
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>131.107.155.10 e 131.107.155.11</p></td>
<td><p>Interface externa da Borda de Acesso (Contoso). Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20 e 131.107.155.21</p></td>
<td><p>Interface externa da Borda de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30 e 131.107.155.31</p></td>
<td><p>Interface externa da Borda de A/V.</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/SRV/443</p></td>
<td><p>_sip. _tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa de borda de acesso. Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente. Repita conforme for necessário para todos os domínios SIP com usuários Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa da Borda de Acesso SIP. Requerida para descoberta automática de DNS de parceiros federados conhecidos como "Domínio SIP Permitido" (chamado de federação aprimorada em versões anteriores). Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS Interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10 e 172.25.33.11</p></td>
<td><p>Interface interna da Borda Consolidada</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="records-required-for-federation"></a>Registros requeridos para federação


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
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/SRV/5061</p></td>
<td><p>_sipfederationtls. _tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa da Borda de Acesso SIP Exgido para requisitos da descoberta de DNS de sua federação a outros potenciais parceiros da federação e é conhecido como “domínios SIP permitidos” (chamado Federação avançada em lançamentos prévios).Repetir conforme necessário para todos os domínios SIP com usuários Lync</p>
<div>

> [!IMPORTANT]  
> Este registro SRV é exigido para mobilidade e a notificação push para liberação de espaço


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary--public-instant-messaging-connectivity"></a>Resumo DNS – Public Instant Messaging Connectivity


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
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface de serviço de borda de acesso</p></td>
<td><p>Interface externa da borda de acesso (Contoso)Repetir conforme necessário para todos os domínios SIP com usuários Lync</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="dns-summary-for-extensible-messaging-and-presence-protocol"></a>Resumo DNS para Mensagens Extensíveis e Protocolo de Presença


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
<th>Mapeia para/comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/SRV/5269</p></td>
<td><p>_xmpp-Server. _tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao Usuário habilitado para Lync. Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP. Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>xmpp.contoso.com (por exemplo)</p></td>
<td><p>Endereço IP do serviço de borda de acesso no servidor de borda ou no pool de borda que hospeda o proxy do XMPP</p></td>
<td><p>Aponta para o serviço de borda de acesso ou o pool de borda que hospeda o serviço de proxy XMPP. Tipicamente, o registro SRV que você criar apontará para este host (A ou AAAA) record</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

