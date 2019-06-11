---
title: Resumo de DNS - borda consolidada em escala com balanceadores de carga de hardware
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 8453297c-da1d-4b9e-a37e-6721458c6feb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398670(v=OCS.15)
ms:contentKeyID: 48184700
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d411b004edde96314e3c06d7f28a9f9d294688ad
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829353"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Resumo de DNS - borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-01-27_

Os requisitos de registro de DNS para acesso remoto ao Lync Server 2013 são bem simples em comparação com aqueles para certificados e portas. Além disso, muitos registros são opcionais, dependendo de como você configura os clientes que executam o Lync 2013 e se você habilita a Federação.

Para obter detalhes sobre os requisitos de DNS do Lync 2013, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

Para obter detalhes sobre como configurar a configuração automática de clientes do Lync 2013 se a divisão do DNS não estiver configurada, consulte a seção "configuração automática sem DNS de Brain" em [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

A tabela a seguir contém um resumo dos registros DNS necessários para dar suporte à topologia de borda consolidada redimensionada (balanceamento de carga de hardware) da figura. Observe que determinados registros DNS são necessários somente para a configuração automática de clientes do Lync. Se você pretende usar objetos de política de grupo (GPOs) para configurar os clientes do Lync, os registros associados não são necessários.

<div>

## <a name="important-edge-server-network-adapter-requirements"></a>IMPORTANTE: requisitos do adaptador de rede do Edge Server

Para evitar problemas de roteamento, verifique se há pelo menos dois adaptadores de rede em seus servidores de borda e se o gateway padrão está definido somente no adaptador de rede associado à interface externa. Por exemplo, conforme mostrado na figura de cenário de borda consolidada dimensionada na [borda consolidada dimensionada com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md), o gateway padrão apontaria para o firewall externo.

Você pode configurar dois adaptadores de rede em cada um dos seus servidores de borda da seguinte maneira:

  - **Adaptador de rede 1 (interface interna)**
    
    Interface interna com 172.25.33.10 atribuído.
    
    Nenhum gateway padrão.
    
    Verifique se há uma rota da rede que contém a interface interna do servidor de borda para qualquer rede que contenha clientes ou servidores do Lync Server que executam o Lync Server (por exemplo, de 172.25.33.0 para 192.168.10.0).

  - **Adaptador de rede 2 (interface externa)**
    
    Três endereços IP públicos são atribuídos a esse adaptador de rede, por exemplo, 131.107.155.10 para serviço de borda do Access, 131.107.155.20 para serviço de borda de webconferência, 131.107.155.30 para o serviço de borda A/V.
    
    <div>
    

    > [!NOTE]
    > Os endereços IP atribuídos às interfaces de rede externa reais do servidor de borda podem depender do balanceamento de carga de hardware que você escolher. Consulte a documentação do balanceador de carga de hardware para compreender os requisitos de endereço IP real.<BR>É possível, mas não recomendado, usar um único endereço IP para todas as três interfaces de serviço de borda. Embora isso salve endereços IP, ele exige números de porta diferentes para cada serviço. O número da porta padrão é 443/TCP, o que garante que os firewalls remotos permitam que o tráfego seja permitido. Alterar os valores de porta para (por exemplo) 5061/TCP para o serviço de borda de acesso, 444/TCP para o serviço de borda de Webconferências e 443/TCP para o serviço de borda A/V pode causar problemas para usuários remotos nos quais um firewall para os quais estejam atrás não permite o tráfego 5061/TCP e 444/TCP. Além disso, três endereços IP distintos facilitam a solução de problemas devido à capacidade de filtrar por endereço IP.

    
    </div>
    
    O endereço IP do serviço de borda do Access é primário com o gateway padrão definido como roteador voltado para a Internet (131.107.155.1).
    
    Serviço de borda de Webconferência e os endereços IP dos serviços de borda A/V secundário.

<div>


> [!TIP]
> A configuração do servidor de borda com dois adaptadores de rede é uma das duas opções. A outra opção é usar um adaptador de rede para o lado interno e três adaptadores de rede para o lado externo do servidor de borda. O principal benefício dessa opção é um adaptador de rede distinto por serviço de servidor de borda e uma coleta de dados possivelmente mais concisa quando a solução de problemas é necessária



</div>

### <a name="dns-records-required-for-scaled-consolidated-edge-hardware-load-balanced-example"></a>Registros DNS necessários para borda consolidada dimensionada, balanceamento de carga de hardware (exemplo)

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
<td><p>Interface externa do serviço de borda do Access (contoso). Repita conforme necessário para todos os domínios SIP com usuários habilitados para Lync</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externo</p></td>
<td><p>webcon.contoso.com</p></td>
<td><p>131.107.155.20</p></td>
<td><p>Interface externa do serviço de borda de Webconferência</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externo</p></td>
<td><p>av.contoso.com</p></td>
<td><p>131.107.155.30</p></td>
<td><p>Interface externa de serviço de borda A/V</p></td>
</tr>
<tr class="even">
<td><p>DNS/SRV/443 externos</p></td>
<td><p>_sip._tls.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa do serviço de borda do Access. Obrigatório para configurar automaticamente o Lync 2013 e os clientes do Lync 2010 para trabalhar externamente. Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync.</p></td>
</tr>
<tr class="odd">
<td><p>DNS/SRV/5061 externo</p></td>
<td><p>_sipfederationtls._tcp.contoso.com</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>Interface externa do serviço de borda do acesso SIP necessária para descoberta automática de DNS de parceiros federados conhecidos como "domínio SIP permitido" (chamado de Federação aprimorada nas versões anteriores). Repita conforme necessário para todos os domínios SIP com usuários habilitados para o Lync e clientes móveis do Microsoft Lync que usam o serviço de notificação por Push ou o serviço de notificação por push da Apple</p></td>
</tr>
<tr class="even">
<td><p>DNS interno/A</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>172.25.33.10</p></td>
<td><p>Interface interna de borda consolidada</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

