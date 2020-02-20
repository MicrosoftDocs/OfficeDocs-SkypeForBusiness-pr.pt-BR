---
title: 'Lync Server 2013: escolhendo uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b91fc332c5eff86cd23393492bcd760bbda18db3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Escolhendo uma topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Última modificação do tópico:** 2013-02-21_

Ao escolher uma topologia, você pode usar uma das seguintes opções de topologia suportadas:

<div>


> [!NOTE]
> A menos que indicado de outra forma, se você tiver experiência com o Microsoft Lync Server 2010, você encontrará aqui uma orientação totalmente inalterada.



</div>

  - [Única borda consolidada com endereços IP privados e NAT no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> A interface de Borda interna e externa devem usar o mesmo tipo de balanceamento de carga. Não é possível usar o balanceamento de carga DNS na interface de Borda e o balanceamento de carga de hardware na outra interface de Borda.



</div>

A tabela a seguir resume a funcionalidade disponível com as topologias do Microsoft Lync Server 2013 com suporte. Os títulos de coluna indicam a funcionalidade disponível para uma determinada opção de configuração de borda. Usando a opção borda em escala (balanceamento de carga DNS) como exemplo, você pode ver que ele oferece suporte à alta disponibilidade, pode usar endereços IP privados não roteáveis (com NAT) ou endereços IP públicos roteáveis atribuídos às interfaces externas de borda e reduz o custo porque um o balanceador de carga de hardware não é necessário.

Cenários de failover de borda suportados com balanceamento de carga DNS são sessões ponto a ponto do Lync para Lync, sessões de conferência do Lync, sessões do Lync para PSTN e o Office 365. Cenários de failover de borda que não se beneficiam do balanceamento de carga DNS são failover para o usuário remoto Exchange Unified Messaging (UM) (antes do Exchange 2010 SP1), conectividade de IM (mensagens instantâneas públicas) e Federação com servidores executando o Office Communications Do.

### <a name="summary-of-edge-server-topology-options"></a>Resumo das opções de topologia do servidor de borda

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>Topologia</th>
<th>Alta disponibilidade</th>
<th>Registros DNS A adicionais necessários para servidor de borda externo no pool de borda</th>
<th>Failover de borda para sessões do Lync para Lync</th>
<th>Failover de borda para sessões de Federação do Lync para Lync EUM/PIC/OCS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda única usando NAT</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="even">
<td><p>Borda única usando IP público</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
<td><p>Não</p></td>
</tr>
<tr class="odd">
<td><p>Borda dimensionada (balanceamento de carga DNS) usando NAT</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Borda dimensionada (balanceamento de carga DNS) usando IP público</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Carga balanceada de hardware de borda em escala)</p></td>
<td><p>Sim</p></td>
<td><p>Não (um registro DNS A por VIP)</p></td>
<td><p>Sim</p></td>
<td><p>Sim</p></td>
</tr>
</tbody>
</table>


**\*** O failover para conectividade de IM (mensagens instantâneas) públicas e a Federação com servidores que executam o Office Communications Server não estão disponíveis com o balanceamento de carga DNS. O failover de UM (usuário remoto) do Exchange usando o balanceamento de carga DNS exige o Exchange Server 2010 SP1 ou mais recente.



> [!NOTE]
> As topologias de borda única e borda dimensionada (balanceamento de carga DNS) podem usar:
> <ul><li><p>Endereços IP públicos roteáveis</p></li>
> <li><p>Endereço IP privado não roteável se a NAT (conversão de endereço de rede simétrica) for usada</p></li>
>
> <ul><li> Se você usar o endereço IP público ou o endereço IP privado com NAT, ainda usará o mesmo número de endereços IP com base em sua opção de configuração no construtor de topologias. Você pode configurar o servidor de borda para usar um único endereço IP com portas distintas por serviço ou usar endereços IP distintos por serviço, mas usar a mesma porta (por padrão, TCP 443).</li></ul>>
> Se você decidir usar endereços IP privados não roteáveis com NAT:
> <ul><li><p>Você deve usar endereços IP privados roteáveis em todas as três interfaces externas</p></li>
> <li><p>Você deve configurar o NAT simétrico para tráfego de entrada e saída</p></li></ul>>
> A topologia de borda em escala (carga de hardware balanceada) deve usar endereços IP públicos.



O Lync Server 2013 oferece suporte à colocação de acesso, Webconferência e interfaces externas de borda A/V por trás de um roteador ou firewall que realiza a conversão de endereços de rede (NAT) para topologias de servidor de borda consolidadas simples e em escala.

Usar NAT para todas as interfaces externas de Borda exige o uso do balanceamento de carga DNS. Quando comparado ao uso de balanceadores de carga de hardware, o uso do balanceamento de carga DNS sem NAT permite reduzir o número de endereços IP públicos por servidor de borda em um pool de borda, conforme descrito na lista a seguir:

  - Lync Server 2013 a borda consolidada dimensionada (balanceamento de carga DNS) exige três endereços IP públicos para cada servidor de borda em um pool de borda.

  - Lync Server 2013 a borda consolidada dimensionada (carga de hardware balanceada) exige três endereços IP públicos para endereços IP virtuais do balanceador de carga (um requisito de tempo que não aumenta à medida que mais servidores de borda são adicionados ao pool) mais três endereços IP públicos por Servidor de borda em um pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para borda consolidada em escala (endereço IP por função)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de Servidores de Borda por pool</th>
<th>Número de endereços IP necessários Lync Server 2013 (balanceamento de carga DNS)</th>
<th>Número de endereços IP necessários Lync Server 2013 (carga de hardware balanceada)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>duas</p></td>
<td><p>6 </p></td>
<td><p>3 (1 por VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3D</p></td>
<td><p>9 </p></td>
<td><p>3 (1 por VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>quatro</p></td>
<td><p>12</p></td>
<td><p>3 (1 por VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>0,5</p></td>
<td><p>15 </p></td>
<td><p>3 (1 por VIP) + 15</p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a>Requisitos de endereço IP para borda consolidada em escala (endereço IP único para todas as funções)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de Servidores de Borda por pool</th>
<th>Número de endereços IP necessários Lync Server 2013 (balanceamento de carga DNS)</th>
<th>Número de endereços IP necessários Lync Server 2013 (carga de hardware balanceada)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>duas</p></td>
<td><p>duas</p></td>
<td><p>1 (1 por VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3D</p></td>
<td><p>3D</p></td>
<td><p>1 (1 por VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>quatro</p></td>
<td><p>quatro</p></td>
<td><p>1 (1 por VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>0,5</p></td>
<td><p>0,5</p></td>
<td><p>1 (1 por VIP) + 5</p></td>
</tr>
</tbody>
</table>


Os principais pontos de decisão para a seleção de topologia são alta disponibilidade e balanceamento de carga. O requisito de alta disponibilidade pode influenciar a decisão de balanceamento de carga.

  - **Alta disponibilidade**   Se você precisar de alta disponibilidade, implante pelo menos dois servidores de borda em um pool. Um único pool de borda aceitará até doze servidores de borda. Se for necessário mais capacidade, você poderá implantar vários pools de borda. Como regra geral, 10% de uma determinada base de usuários precisarão de acesso externo.
    
    <div>
    

    > [!IMPORTANT]
    > O construtor de topologias permitirá configurar até vinte servidores de borda em um único pool de borda. O número máximo de servidores de borda testados e suportados em um pool é de doze e o construtor de topologias que permite um número maior que doze não devem ser interpretados como suporte implícito para mais de doze servidores de borda em um único pool de borda.

    
    </div>

  - **Balanceamento de carga de hardware**   O balanceamento de carga de hardware tem suporte para balanceamento de carga de servidores de borda do Lync Server 2013 ao usar endereços IP roteáveis publicamente para as interfaces externas de borda. Por exemplo, você poderia usar essa abordagem em situações em que o failover é necessário para qualquer um dos seguintes aplicativos:
    
      - Conectividade a redes públicas de mensagens instantâneas
    
      - Federação com empresas que executam o Microsoft Office Communications Server 2007 ou o Microsoft Office Communications Server 2007 R2
    
      - Acesso externo à UM (Unificação de mensagens) do Exchange 2007 ou a UM do Exchange 2010
        
        <div>
        

        > [!IMPORTANT]
        > O balanceamento de carga DNS para o Exchange 2010 SP1 e mais recente é suportado para UM do Exchange.

        
        </div>
    
    Esses três aplicativos continuarão a funcionar, mas eles não são compatíveis com o balanceamento de carga DNS e só se conectarão ao primeiro servidor de borda no pool. Se esse servidor não estiver disponível, a conexão falhará. Por exemplo, se vários servidores de borda são implantados em um pool para lidar com a carga de tráfego federado, apenas um proxy de acesso realmente recebe tráfego enquanto os outros estão ociosos.

<div>


> [!IMPORTANT]
> É recomendável usar o balanceamento de carga DNS se você estiver se Federando com empresas que usam o Lync Server 2010 e o Microsoft Office 365. Lembre-se de que há impactos significativos no desempenho se a maioria dos seus parceiros federados estiverem usando o Office Communications Server 2007 ou o Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

