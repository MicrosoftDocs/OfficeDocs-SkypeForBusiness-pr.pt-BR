---
title: Resumo de DNS-borda consolidada única com endereços IP públicos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Single consolidated edge with public IP addresses
ms:assetid: 7b83eae4-aa1a-4cc6-8077-42176d56cab5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205025(v=OCS.15)
ms:contentKeyID: 48184601
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e0604a018b4b558612e2e2a3802ca97676b58b2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501228"
---
# <a name="dns-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a>Resumo de DNS-borda consolidada única com endereços IP públicos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2017-03-09_

Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas. Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.

Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obter detalhes sobre a configuração automática de clientes que executam o Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte "configuração automática sem Split-Brain DNS" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

A tabela a seguir contém um resumo dos registros DNS requeridos para oferecer suporte à topologia de borda consolidada única exibida na imagem Topologia de Borda Consolidada Única. Observe que determinados registros DNS são necessários apenas para a configuração automática dos clientes Lync 2013 e Lync 2010. Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros de configuração automática associados não serão necessários.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos do adaptador de rede do servidor de borda

Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa. Por exemplo, conforme mostrado na topologia de borda consolidada única com endereços IP públicos em [uma única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md), o gateway padrão apontaria para o roteador externo no seu perímetro de Internet ou firewall que pode fornecer um endereço IP público. A relação de rede para interfaces de servidor de borda é uma relação de rota em vez de uma relação NAT.

Você pode configurar dois adaptadores de rede em seu Servidor de Borda da seguinte forma:

  - **Adaptador de rede 1 (Interface Interna)**
    
    Interface interna com 172.25.33.10 atribuído.
    
    Nenhum gateway padrão definido.
    
    Certifique-se de que há uma rota da rede que contém a interface interna da borda para qualquer rede que contenha servidores que executam os clientes do Lync Server 2013 ou do Lync Server 2013 (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 2 (Interface Externa)**
    
    Três endereços IP públicos são atribuídos a este adaptador de rede, por exemplo, 131.107.155.10 para Borda de Acesso, 131.107.155.20 para Borda de Conferência da Web, 131.107.155.30 para Borda AV.
    
    <div>
    

    > [!NOTE]
    > É possível, embora não seja recomendado, usar um único endereço IP para as três interfaces de serviço de Borda. Embora isso não salve endereços IP, exige diferentes números de porta para cada serviço. O número de porta padrão é 443/TCP, que garante que a maioria dos firewalls remotos permitirão o tráfego. Mudar os valores de porta para (por exemplo) 5061/TCP para Borda de Acesso, 444/TCP para Borda de Conferência da Web e 443/TCP para Borda AV pode causar problemas para usuários remotos que estejam protegidos por um firewall que não permite tráfego além de 5061/TCP e 444/TCP. Além disso, três endereços IP distintos tornam a resolução de problemas mais fácil por poderem filtrar o endereço IP.

    
    </div>
    
    O endereço IP público de Borda de Acesso é primário com gateway padrão definido para o roteador público (131.107.155.1).
    
    Endereços IP públicos de Webconferência e Borda A/V são endereços IP adicionais na seção **Avançado** das propriedades do **Protocolo de Internet Versão 4 (TCP/IPv4)** e **Protocolo de Internet Versão 6 (TCP/IPv6)** das **Propriedades de Conexão de Área Local ** no Windows Server.

<div>


> [!TIP]
> A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções. A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda. O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária



</div>

### <a name="dns-records-required-for-single-consolidated-edge-with-public-ip-addresses-example"></a>Registros DNS Exigidos para a Borda Única Consolidada com Endereços IP Únicos (Exemplo)

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
<td><p>131.107.155.10</p></td>
<td><p>Interface externa da borda de acesso (contoso) repete como necessário para todos os domínios SIP com usuários habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externa da borda de webconferências</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externa da Borda de A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa de borda de acesso. Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente. Repita conforme for necessário para todos os domínios SIP com usuários Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa de borda de acesso SIP. Requerido para descoberta de DNS automática de parceiros federados, conhecida como "Domínio SIP Permitido" (chamada de federação avançada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interna da Borda Consolidada</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]
> Os registros listados na tabela anterior são exibidos com uma extensão <EM>.net</EM> ou <EM>.com</EM> para destacar em qual zona precisam residir caso você não esteja usando split-brain DNS. Se você estiver usando split-brain DNS, todos os registros devem estar na mesma zona, com a única distinção sendo se estão na versão interna ou externa. Para obter detalhes, consulte "split-brain DNS" em <A href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="records-required-for-federation"></a>Registros exigidos para Federação


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
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa da Borda de Acesso SIP Exgido para requisitos da descoberta de DNS de sua federação a outros potenciais parceiros da federação e é conhecido como “domínios SIP permitidos” (chamado Federação avançada em lançamentos prévios).Repetir conforme necessário para todos os domínios SIP com usuários Lync</p>



> [!IMPORTANT]
> Este registro SRV é exigido para mobilidade e a notificação push para liberação de espaço

</td>
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
<th>Mapeia para/Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS Externo/SRV/5269</p></td>
<td><p>_xmpp-server._tcp. contoso. com</p></td>
<td><p>xmpp.contoso.com</p></td>
<td><p>XMPP interface externa do proxy no serviço de borda de acesso ou no pool de borda. Repita conforme necessário para todos os domínios SIP internos com usuários habilitados para Lync onde contato com contatos do XMPP é permitido por meio da configuração da política de acesso externo por meio de uma política global, política de site onde o usuário está localizado ou política de usuário aplicada ao usuário habilitado para Lync. Um domínio XMPP permitido também deve ser configurado na política de Parceiros Federados XMPP. Veja os tópicos em <strong>Consulte também </strong> para mais detalhes</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
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

