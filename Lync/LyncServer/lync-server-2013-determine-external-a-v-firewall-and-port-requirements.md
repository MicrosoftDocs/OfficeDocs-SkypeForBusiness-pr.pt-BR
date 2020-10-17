---
title: 'Lync Server 2013: determinar firewall A/V externo e requisitos de porta'
description: 'Lync Server 2013: determinar firewall A/V externo e requisitos de porta.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 38c2a8c1e8e332a4a1e65adb87a1e962e82941c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550927"
---
# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a>Determinar firewall A/V externo e requisitos de porta para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

A comunicação de áudio/vídeo (A/V) pode ser um complexo. Devido à natureza dos protocolos usados em A/V e como os clientes e servidores usam os protocolos, uma seção especial é garantida para explicar as diferenças entre as versões do cliente e do servidor.

Use a seguinte firewall de A/V e tabela de porta para determinar os requisitos de firewall e quais portas abrir. Em seguida, revise a terminologia NAT (conversão de endereço de rede) porque o NAT pode ser implementado de várias maneiras diferentes. Para obter um exemplo detalhado das configurações de porta de firewall, consulte as arquiteturas de referência em [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a>Uso de protocolo geral para UDP e TCP no tráfego de áudio/vídeo e mídia

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
<td><p>VIA</p></td>
<td><p>Protocolo de camada de transporte preferencial para áudio e vídeo</p></td>
</tr>
<tr class="even">
<td><p>TCP</p></td>
<td><p>Protocolo de camada de transporte de fallback para áudio e vídeo</p>
<p>Protocolo de camada de transporte necessário para compartilhamento de aplicativos para o Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013</p>
<p>Protocolo de camada de transporte necessário para transferência de arquivo para Lync Server 2010 e Lync Server 2013</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a>Requisitos de porta de firewall A/V externo para acesso de usuário externo

Os requisitos de porta de firewall para as interfaces de SIP e de conferência externas (e internas) são consistentes, independentemente da versão do cliente ou da versão do parceiro de Federação.

O mesmo não se aplica à interface externa de borda de áudio/vídeo. Para federação com o Office Communications Server 2007, o serviço de borda A/V requer que as regras de firewall externas permitam que o tráfego RTP/TCP e RTP/UDP no intervalo de porta de 50.000 a 59.999 fluam em ambas as direções. A tabela anterior pressupõe que o Lync Server 2013 é o parceiro de Federação principal e está sendo configurado para se comunicar com um dos outros tipos de parceiros de Federação listados.

Configurar o intervalo de porta de áudio/vídeo de 50000-59.999 deve levar em conta que o intervalo de porta conterá as portas de origem para comunicações com parceiros de Federação. Em detalhes, considere que uma comunicação é iniciada a partir de um parceiro de Federação. A comunicação das portas de serviço de borda a/V no intervalo de 50000 59.999 se conectará à porta TCP 443 esperada do serviço de borda A/V do parceiro. Por outro lado, o tráfego de entrada para sua porta de serviço de borda A/V TCP 443 terá uma porta de origem no intervalo de 50000 59.999.

Firewalls e políticas diferentes para a administração de firewall podem exigir que apenas as regras de destino sejam configuradas ou podem exigir que a origem e o destino sejam configurados. Se seus requisitos forem somente para portas de destino, os requisitos de áudio/vídeo são:


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
<th>Porta de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualquer</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualquer</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


Se suas políticas exigem definições de regra de firewall de entrada e saída, os requisitos de áudio/vídeo são:


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
<th>Porta de destino</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>TCP 50000-59.999</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>UDP 3478</p></td>
<td><p>UDP 3478</p></td>
</tr>
<tr class="odd">
<td><p>Qualquer</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>TCP 443</p></td>
</tr>
<tr class="even">
<td><p>Qualquer</p></td>
<td><p>Interface de serviço de borda A/V</p></td>
<td><p>Qualquer</p></td>
<td><p>UDP 3478</p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> O Microsoft Office Communications Server 2007 requer uma configuração um pouco diferente. O intervalo de portas TCP e UDP de 50000-59.999 deve estar aberto e de saída. Este requisito é apenas para o Office Communicator 2007. O Office Communications Server 2007 R2, Lync Server 2010 e Lync Server 2013 só exigem o intervalo de TCP 50000-59.999 Open outbound.



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a>Requisitos de NAT para o serviço de borda

Os seguintes requisitos de NAT se aplicam se você optar por configurar endereços IP privados não roteáveis para o serviço de borda:

  - O NAT só pode ser usado com o balanceamento de carga DNS. NAT não é compatível com uma topologia de borda de HLB (balanceamento de carga de hardware).

  - O NAT só pode ser usado na interface de borda externa. O NAT não é suportado na interface de borda interna.

  - NAT deve ser simétrico para tráfego de entrada e saída.
    
  - Para o tráfego da Internet, o NAT deve alterar o endereço IP de destino do endereço IP público habilitado para NAT do serviço de borda a/V para seu endereço IP externo. O endereço IP de origem deve permanecer intacto, para que o serviço de borda a/V possa encontrar o caminho de mídia ideal.
  
  Por exemplo, na direção de entrada na figura abaixo, o endereço IP público 131.107.155.30 foi alterado para o endereço IP externo (privado) 10.45.16.10. O endereço IP de origem permaneceu inalterado.
  
  - Para o tráfego do serviço de borda a/V para a Internet, o NAT deve alterar o endereço IP de origem do endereço IP externo do serviço de borda a/V para o endereço IP público habilitado para NAT.

Por exemplo, na direção de saída na figura abaixo, o endereço IP externo (privado) 10.45.16.10 foi alterado para o endereço IP público 131.107.155.30.

**A figura abaixo mostra como o NAT altera o endereço IP de destino para o tráfego de entrada e o endereço IP de origem para o tráfego de saída.**

![Alterando endereços IP de destino/origem](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Alterando endereços IP de destino/origem")

Os principais pontos são:

  - O tráfego de entrada no servidor que executa o serviço de borda A/V, o endereço IP de origem não é alterado, mas o endereço IP de destino é alterado de 131.107.155.30 para o endereço IP convertido de 10.45.16.10.

  - Tráfego de saída do servidor que executa o serviço de borda A/V de volta para a estação de trabalho, o endereço IP de origem muda do endereço IP público do servidor para o endereço IP público do servidor que executa o serviço de borda A/V. O IP de destino permanece no endereço IP público da estação de trabalho. Depois que o pacote deixa o primeiro dispositivo NAT de saída, a regra no dispositivo NAT altera o endereço IP de origem do servidor que executa o endereço IP da interface externa do serviço de borda A/V (10.45.16.10) para seu endereço IP público (131.107.155.30).

</div>

</div>

<span> </span>

</div>

</div>

</div>

