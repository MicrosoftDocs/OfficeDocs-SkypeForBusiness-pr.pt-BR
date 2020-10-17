---
title: Resumo de DNS-borda consolidada em escala com balanceadores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5847a43c6d07cf188c97cd8de6a47dfb83e1468
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501278"
---
# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumo de DNS-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-01-27_

Os requisitos de registro DNS para acesso remoto ao Lync Server 2013 são bem simples comparados com os de certificados e portas. Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.

Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obter detalhes sobre como configurar a configuração automática dos clientes do Lync 2013 se o DNS de Split-Brain não estiver configurado, consulte a seção "configuração automática sem DNS de Split Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

A tabela a seguir contém um resumo dos registros DNS necessários para oferecer suporte à Topologia de borda consolidada dimensionada (balanceamento de carga de hardware). Observe que determinados registros DNS são necessários apenas para a configuração automática para clientes do Lync. Se você planeja usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos do adaptador de rede do servidor de borda

Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa. Por exemplo, conforme mostrado na figura de cenário de borda consolidada em escala na [borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), o gateway padrão apontaria para o firewall externo.

Você pode configurar dois adaptadores de rede em cada um dos servidores de borda da seguinte maneira:

  - **Adaptador de rede 1 (Interface Interna)**
    
    Interface interna com o 172.25.33.10 atribuído.
    
    Nenhum gateway padrão.
    
    Verifique se há uma rota da rede que contém a interface interna do servidor de borda para qualquer rede que contenha clientes ou servidores do Lync Server que executam o Lync Server (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 2 (Interface Externa)**
    
    Três endereços IP públicos são atribuídos a este adaptador de rede, por exemplo, 131.107.155.10 para serviço de borda de acesso, 131.107.155.20 para serviço de borda de webconferência, 131.107.155.30 para o serviço de borda A/V.
    
    <div>
    

    > [!NOTE]
    > Os endereços IP atribuídos às interfaces de rede externa reais do servidor de borda podem depender do balanceador de carga de hardware que você escolher. Consulte a documentação do balanceador de carga de hardware para entender os requisitos de endereço IP real.<BR>É possível, embora não seja recomendado, usar um único endereço IP para as três interfaces de serviço de Borda. Embora isso não salve endereços IP, exige diferentes números de porta para cada serviço. O número de porta padrão é 443/TCP, que garante que a maioria dos firewalls remotos permitirão o tráfego. Alterar os valores de porta para (por exemplo) 5061/TCP para o serviço de borda de acesso, 444/TCP para o serviço de borda de Webconferência e 443/TCP para o serviço de borda A/V pode causar problemas para usuários remotos em que um firewall que estão por trás não permite o tráfego sobre 5061/TCP e 444/TCP. Além disso, três endereços IP distintos tornam a resolução de problemas mais fácil por poderem filtrar o endereço IP.

    
    </div>
    
    O endereço IP do serviço de borda de acesso é o principal com o gateway padrão definido para o roteador voltado para a Internet (131.107.155.1).
    
    Serviço de borda de Webconferência e endereços IP de serviço de borda A/V secundários.

<div>


> [!TIP]
> A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções. A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda. O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e coleta de dados potencialmente mais concisa quando a solução de problemas é necessária



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Registros DNS necessários para borda consolidada dimensionada com balanceamento de carga de hardware (exemplo)

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
<td><p>Interface externa do serviço de borda de acesso (contoso). Repetir conforme o necessário para todos os domínios SIP com usuários habilitados para o Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/A</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externa do serviço de borda de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/A</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externa do serviço de borda A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS Externo/SRV/443</p></td>
<td><p>_sip _sip._tls. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa do serviço de borda de acesso. Necessário para a configuração automática dos clientes do Lync 2013 e Lync 2010 para trabalhar externamente. Repita conforme for necessário para todos os domínios SIP com usuários Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS Externo/SRV/5061</p></td>
<td><p>_sipfederationtls _sipfederationtls._tcp. contoso. com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa do serviço de borda de acesso SIP necessária para a descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamado de Federação avançada em versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync e clientes móveis do Microsoft Lync que usam o serviço de notificação por Push ou o serviço de notificação por push da Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS/A interno</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interna da Borda Consolidada</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

