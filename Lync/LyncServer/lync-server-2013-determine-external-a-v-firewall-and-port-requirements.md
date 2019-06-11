---
title: 'Lync Server 2013: Determinar firewall A/V externo e requisitos de porta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b278c60eaca69fd17508d0e82198a002484ce586
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829446"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Determinar firewall A/V externo e requisitos de porta para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

A comunicação de áudio/vídeo (A/V) pode ser um complexo. Por causa da natureza dos protocolos usados em A/V e de como os clientes e servidores usam os protocolos, uma seção especial tem a garantia de explicar as diferenças entre as versões do cliente e do servidor.

Use a seguinte tabela de firewall e porta de A/V para determinar os requisitos de firewall e quais portas abrir. Em seguida, examine a terminologia NAT (Network Address Translation) porque a NAT pode ser implementada de muitas maneiras diferentes. Para obter um exemplo detalhado das configurações de porta do firewall, consulte as arquiteturas de referência em [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Uso de protocolo geral para UDP e TCP em tráfego de áudio/vídeo e mídia

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Transporte de áudio/vídeo</th>
<th>Uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UDP</p></td>
<td><p>Protocolo preferencial de camada de transporte para áudio e vídeo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocolo de camada de transporte de fallback para áudio e vídeo</p>
<p>Protocolo de camada de transporte obrigatório para compartilhamento de aplicativos com o Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</p>
<p>Protocolo de camada de transporte necessário para transferência de arquivos para o Lync Server 2010 e Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Requisitos de porta de firewall externo A/V para acesso de usuários externos

Os requisitos de porta de firewall para interfaces SIP e de conferência externas (e internas) são consistentes, independentemente da versão do seu cliente ou da versão do parceiro de Federação.

O mesmo não é válido para a interface externa da borda de áudio/vídeo. Para a Federação com o Office Communications Server 2007, o serviço de borda A/V exige que as regras de firewall externo permitam o tráfego RTP/TCP e RTP/UDP no intervalo de porta 50.000 a 59.999 para fluir nas duas direções. A tabela anterior pressupõe que o Lync Server 2013 é o parceiro de Federação principal e está sendo configurado para se comunicar com um dos outros tipos de parceiros de Federação listados.

Configurar o intervalo de porta de áudio/vídeo de 50000-59.999 deve levar em conta que o intervalo de porta conterá as portas de origem para comunicações com os parceiros de Federação. Em detalhes, considere que uma comunicação seja iniciada de um parceiro de Federação. A comunicação das portas de serviço de borda a/V no intervalo de 50000 59.999 se conectará à porta TCP 443 do serviço de borda A/V do parceiro. Por outro lado, o tráfego de entrada para a sua porta de serviço de borda A/V TCP 443 terá uma porta de origem no intervalo de 50000 a 59.999.

Firewalls e políticas diferentes para administração de firewall podem exigir que apenas as regras de destino sejam configuradas ou podem exigir que a origem e o destino sejam configurados. Se seus requisitos são somente para portas de destino, os requisitos de áudio/vídeo são:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>IP de origem</th>
<th>IP de destino</th>
<th>Porta de Destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualquer um</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualquer um</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Se as suas políticas exigirem as definições de regras de firewall de entrada e saída, os requisitos de áudio/vídeo serão:


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>IP de origem</th>
<th>IP de destino</th>
<th>Porta de origem</th>
<th>Porta de Destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>TCP 50.000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualquer um</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualquer um</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer um</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> O Microsoft Office Communications Server 2007 requer uma configuração um pouco diferente. O intervalo de portas TCP e UDP de 50000-59.999 deve estar aberto em entrada e saída. Este requisito é somente para o Office Communicator 2007. O Office Communications Server 2007 R2, o Lync Server 2010 e o Lync Server 2013 exigem somente o intervalo de TCP 50000-59.999 Open outbound.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Requisitos de NAT para o serviço de borda

Os seguintes requisitos de NAT se aplicam se você optar por configurar endereços IP privados não roteáveis para o serviço de borda:

  - O NAT só pode ser usado com balanceamento de carga de DNS. Não há suporte para NAT com uma topologia de borda de HLB (balanceamento de carga de hardware).

  - O NAT só pode ser usado na interface de borda externa. Não há suporte para NAT na interface de borda interna.

  - O NAT deve ser simétrico para o tráfego de entrada e saída.
    
  - Para o tráfego da Internet, o NAT deve alterar o endereço IP de destino do endereço IP público compatível com NAT do serviço de borda A/V para seu endereço IP externo. O endereço IP de origem deve permanecer intacto, para que o serviço de borda a/V possa encontrar o caminho de mídia ideal.
  
  Por exemplo, na direção de entrada na figura abaixo, o endereço de IP público 131.107.155.30 foi alterado para o 10.45.16.10 de endereço IP externo (particular). O endereço IP de origem permaneceu inalterado.
  
  - Para o tráfego do serviço de borda a/V para a Internet, o NAT deve alterar o endereço IP de origem do endereço IP externo do serviço de borda a/V para o endereço IP público habilitado para NAT.

Por exemplo, na direção de saída na figura abaixo, o endereço IP externo (privado) 10.45.16.10 foi alterado para o endereço IP público 131.107.155.30.

**A figura a seguir mostra como o NAT altera o endereço IP de destino para o tráfego de entrada e o endereço IP de origem para o tráfego de saída.**

![Alterar os endereços IP de destino/origem] (images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Alterar os endereços IP de destino/origem")

Os principais pontos são:

  - O tráfego que está ligado ao servidor que executa o serviço de borda A/V, o endereço IP de origem não muda, mas o endereço IP de destino muda de 131.107.155.30 para o endereço IP traduzido do 10.45.16.10.

  - O tráfego de saída do servidor que executa o serviço de borda a/V de volta para a estação de trabalho, o endereço IP de origem muda do endereço IP público do servidor para o endereço IP público do servidor que executa o serviço de borda A/V. O IP de destino permanece no endereço IP público da estação de trabalho. Depois que o pacote deixar o primeiro dispositivo NAT de saída, a regra no dispositivo NAT alterará o endereço IP de origem do servidor que executa o endereço IP da interface externa do serviço de borda A/V (10.45.16.10) para o endereço IP público (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

