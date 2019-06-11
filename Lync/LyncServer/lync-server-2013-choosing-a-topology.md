---
title: 'Lync Server 2013: Escolhendo uma topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3aa98d479ca2bfeaf6214bbd1e66bb3f41b09782
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a>Escolhendo uma topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

_**Tópico da última modificação:** 2013-02-21_

Ao escolher uma topologia, você pode usar uma das seguintes opções de topologia com suporte:

<div>


> [!NOTE]
> A menos que indicado de outra forma, se você tiver experiência com o Microsoft Lync Server 2010, verá aqui que a orientação é totalmente inalterada.



</div>

  - [Única borda consolidada com endereços IP privados e NAT no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [Única borda consolidada com endereços IP públicos no Lync Server 2013](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> As interfaces de Borda interna e externa precisam usar o mesmo tipo de balanceamento de carga. Não é possível usar balanceamento de carga DNS em uma interface de Borda e balanceamento de carga de hardware na outra interface de Borda.



</div>

A tabela a seguir resume a funcionalidade disponível com as topologias do Microsoft Lync Server 2013 com suporte. Os títulos de coluna indicam a funcionalidade disponível para uma determinada opção de configuração de borda. Usando a opção de borda em escala (carga balanceada) como exemplo, você pode ver que ele dá suporte à alta disponibilidade, pode usar endereços IP privados não roteáveis (com NAT) ou endereços IP roteáveis roteáveis atribuídos às interfaces externas de Edge e reduz o custo porque um o balanceador de carga de hardware não é necessário.

Cenários de failover de borda com suporte com balanceamento de carga de DNS são sessões ponto a ponto do Lync para Lync, sessões de conferência do Lync, sessões do Lync para PSTN e do Office 365. Cenários de failover de borda que não se beneficiam do balanceamento de carga de DNS são failover para a UM (de uma) (anterior ao Exchange 2010 SP1), a conectividade de mensagens instantâneas públicas (IM) e a Federação com servidores que executam o Office Communications Servidor.

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
<th>Registros DNS adicionais necessários para o servidor de borda externo no pool de bordas</th>
<th>Failover de borda para sessões do Lync para o Lync</th>
<th>Failover de borda para sessões de Federação do Lync-to-Lync do EUM/PIC/OCS</th>
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
<td><p>Borda em escala (balanceamento de carga de DNS) usando NAT</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p>Borda em escala (carga de DNS balanceada) usando o IP público</p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>Sim </p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p>Carga balanceada do hardware de borda em escala)</p></td>
<td><p>Sim</p></td>
<td><p>Não (um registro DNS A por VIP)</p></td>
<td><p>Sim</p></td>
<td><p>Sim </p></td>
</tr>
</tbody>
</table>


**\*** O failover para conectividade de mensagens instantâneas públicas (IM) e Federação com servidores que executam o Office Communications Server não está disponível com balanceamento de carga de DNS. O failover de UM (usuário remoto) do Exchange usando o balanceamento de carga de DNS exige o Exchange Server 2010 SP1 ou versão mais recente.



> [!NOTE]
> As topologias de borda única e de borda em escala (carga DNS balanceada) podem usar:
> <ul><li><p>Endereços IP públicos roteáveis</p></li>
> <li><p>Endereço IP privado não roteável se a NAT (conversão de endereços de rede) simétrica for usada</p></li>
>
> <ul><li> Se você usar o endereço IP público ou o endereço IP privado com NAT, ainda usará o mesmo número de endereços IP com base em sua opção de configuração no construtor de topologias. Você pode configurar o servidor de borda para usar um único endereço IP com portas distintas por serviço ou usar endereços IP distintos por serviço, mas usar a mesma porta (por padrão, TCP 443).</li></ul>>
> Se você decidir usar endereços IP privados não roteáveis com NAT:
> <ul><li><p>Você deve usar endereços IP particulares roteáveis em todas as três interfaces externas</p></li>
> <li><p>Você deve configurar o NAT simétrico para tráfego de entrada e saída</p></li></ul>>
> A topologia de borda em escala (carga de hardware balanceada) deve usar endereços IP públicos.



O Lync Server 2013 dá suporte à colocação de acesso, Webconferência e A/V de interfaces externas atrás de um roteador ou firewall que executa a NAT (conversão de endereços de rede) para topologias de servidor de borda consolidadas simples e em escala.

Usar NAT para todas as interfaces externas Edge requer o uso de balanceamento de carga de DNS. Quando comparado ao uso de balanceadores de carga de hardware, o uso de balanceamento de carga de DNS sem NAT permite reduzir o número de endereços IP públicos por servidor de borda em um pool de bordas conforme descrito na lista a seguir:

  - O Lync Server 2013 a borda consolidada dimensionada (carga de DNS balanceada) requer três endereços IP públicos para cada servidor de borda em um pool de bordas.

  - A borda consolidada do Lync Server 2013 redimensionada (carga de hardware balanceada) requer três endereços IP públicos para endereços IP virtuais do balanceador de carga (um requisito de tempo que não aumenta à medida que mais servidores de borda são adicionados ao pool) e três endereços IP públicos por Servidor de borda em um pool.

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a>Requisitos de endereço IP para borda consolidada em escala (endereço IP por função)

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Número de servidores de borda por pool</th>
<th>Número de endereços IP necessários Lync Server 2013 (DNS Load Balanced)</th>
<th>Número de endereços IP necessários Lync Server 2013 (hardware com balanceamento de carga)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>6</p></td>
<td><p>3 (1 por VIP) + 6</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>222</p></td>
<td><p>3 (1 por VIP) + 9</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>12</p></td>
<td><p>3 (1 por VIP) + 12</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>15</p></td>
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
<th>Número de servidores de borda por pool</th>
<th>Número de endereços IP necessários Lync Server 2013 (DNS Load Balanced)</th>
<th>Número de endereços IP necessários Lync Server 2013 (hardware com balanceamento de carga)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>2</p></td>
<td><p>1 (1 por VIP) + 2</p></td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>1 (1 por VIP) + 3</p></td>
</tr>
<tr class="odd">
<td><p>4</p></td>
<td><p>4</p></td>
<td><p>1 (1 por VIP) + 4</p></td>
</tr>
<tr class="even">
<td><p>5</p></td>
<td><p>5</p></td>
<td><p>1 (1 por VIP) + 5</p></td>
</tr>
</tbody>
</table>


Os principais pontos de decisão para a seleção de topologia são alta disponibilidade e balanceamento de carga. O requisito para alta disponibilidade pode influenciar a decisão de balanceamento de carga.

  - **Alta disponibilidade**   Se precisar de alta disponibilidade, implante pelo menos dois servidores de borda em um pool. Um único pool de bordas dará suporte a até doze servidores de borda. Se for necessário mais capacidade, você poderá implantar vários pools de bordas. Como regra geral, 10% de uma determinada base de usuários precisará de acesso externo.
    
    <div>
    

    > [!IMPORTANT]
    > O construtor de topologias permitirá configurar até vinte servidores de borda em um único pool de bordas. O número máximo de servidores de borda testados e com suporte em um pool é de doze e o construtor de topologias que permite que um número maior que doze não seja interpretado como suporte implícito para mais de doze servidores de extremidade em um único pool de bordas.

    
    </div>

  - **Balanceamento de carga de hardware**   O balanceamento de carga de hardware tem suporte para os servidores de borda do Lync Server 2013 de balanceamento de carga ao usar endereços IP roteáveis publicamente para as interfaces externas de Edge. Por exemplo, você usaria essa abordagem em situações em que o failover é necessário para qualquer um dos seguintes aplicativos:
    
      - Conectividade de mensagem de chat Pública
    
      - Federação com empresas que executam o Microsoft Office Communications Server 2007 ou o Microsoft Office Communications Server 2007 R2
    
      - Acesso externo ao Exchange 2007 Unified Messaging (UM) ou ao Exchange 2010 UM
        
        <div>
        

        > [!IMPORTANT]
        > O balanceamento de carga de DNS para Exchange 2010 SP1 e versão mais recente tem suporte para o Exchange UM.

        
        </div>
    
    Esses três aplicativos continuarão funcionando, mas não são compatíveis com balanceamento de carga de DNS e só se conectam ao primeiro servidor de borda do pool. Se esse servidor estiver indisponível, a conexão não será bem-sucedida. Por exemplo, se vários servidores de borda forem implantados em um pool para manipular a carga de tráfego federado, apenas um proxy de acesso realmente receberá o tráfego enquanto as outras estiverem ociosas.

<div>


> [!IMPORTANT]
> Usar o balanceamento de carga de DNS é recomendado se você estiver fazendo a Federação com empresas que usam o Lync Server 2010 e o Microsoft Office 365. Lembre-se de que há impactos significativos no desempenho se a maioria dos seus parceiros federados estiver usando o Office Communications Server 2007 ou o Office Communications Server 2007 R2.



</div>

</div>

<span> </span>

</div>

</div>

</div>

