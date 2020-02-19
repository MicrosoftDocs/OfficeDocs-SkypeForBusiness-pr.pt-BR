---
title: Requisitos do balanceador de carga de hardware do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d54ad738824b2ccaa4daf7f67758a970c24cee6a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a>Requisitos do balanceador de carga de hardware para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-05-11_

A topologia de borda consolidada em escala do Lync Server 2013 é otimizada para o balanceamento de carga de DNS para novas implantações que se federam principalmente com outras organizações usando o Lync Server. Se a alta disponibilidade for necessária para qualquer um dos cenários a seguir, um balanceador de carga de hardware deverá ser usado nos pools do Servidor de Borda para o seguinte:

  - Federação com organizações que usam o Office Communications Server 2007 R2 ou o Office Communications Server 2007

  - UM do Exchange para usuários remotos usando o UM do Exchange antes do Exchange 2010 com SP1

  - Conectividade para usuários públicos de mensagens instantâneas

<div>


> [!IMPORTANT]  
> O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.



</div>

<div>


> [!NOTE]  
> Se estiver usando um balanceador de carga de hardware, o balanceador de carga implantado para conexões com a rede interna deverá ser configurado para balancear apenas cargas do tráfego de servidores que executam o serviço de Borda de Acesso e o serviço de Borda A/V. Ele não poderá balancear a carga do tráfego do serviço interno de Borda de Webconferência ou do serviço interno de Proxy XMPP.



</div>

<div>


> [!NOTE]  
> O NAT (retorno do servidor direto) não é suportado com o Lync Server 2013.



</div>

Para determinar se o seu balanceador de carga de hardware oferece suporte aos recursos necessários exigidos pelo Lync Server 2013, consulte "parceiros do balanceador [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452)de carga do lync Server 2010" em.

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a>Requisitos do balanceador de carga de hardware para servidores de borda que executam o serviço de Borda A/V

A seguir estão os requisitos do balanceador de carga de hardware para servidores de borda executando o serviço de borda A/V:

  - Desative o nagling de TCP para as portas interna e externa 443. Nagling é o processo de combinação de diversos pacotes pequenos em um único pacote maior para uma transmissão mais eficiente.

  - Desative o nagling de TCP para o intervalo de portas externas 50.000 a 59.999.

  - Não use NAT no firewall interno ou externo.

  - A interface interna da borda precisa estar em uma rede diferente da interface externa do Servidor de Borda e o roteamento entre elas precisa ser desabilitada.

  - A interface externa do servidor de borda que executa o serviço de borda A/V deve usar endereços IP roteáveis publicamente e sem NAT ou conversão de porta em qualquer um dos endereços IP externos de borda.

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a>Requisitos do balanceador de carga de hardware

Os requisitos de afinidade com base em cookies são bastante reduzidos no Lync Server 2013 para serviços Web. Se você estiver implantando o Lync Server 2013 e não mantiver servidores front-end do Lync Server 2010 ou pools de front-ends, não precisará de persistência baseada em cookie. No entanto, se você mantiver temporariamente ou permanentemente qualquer servidor front-end do Lync Server 2010 ou pools de front-ends, ainda usará a persistência baseada em cookie, pois ela será implantada e configurada para o Lync Server 2010.

<div>


> [!NOTE]  
> <STRONG>Se decidir usar a afinidade baseada em cookie mesmo que sua implantação não exija</STRONG>, isso não causará um impacto negativo.



</div>

Para implantações que **não usarão** afinidade baseada em cookie:

  - No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.

Para implantações que **usarão** afinidade baseada em cookie:

  - No proxy reverso que publica a regra da porta 4443, defina **Encaminhar cabeçalho de host** como Verdadeiro. Isso garantirá que a URL original seja encaminhada.

  - O cookie do balanceador de carga de hardware NÃO DEVE ser marcado como httpOnly

  - O cookie do balanceador de carga de hardware NÃO DEVE conter uma data de vencimento

  - O cookie do balanceador de carga de hardware DEVE ser nomeado como **MS-WSMAN** (este é o valor que o serviço Web espera e não pode ser alterado)

  - O cookie do balanceador de carga de hardware DEVE ser definido em todas as respostas HTTP para as quais a solicitação HTTP recebida não contém um cookie, independentemente de uma resposta HTTP anterior na mesma conexão TCP já ter obtido um cookie. Se o balanceador de carga otimiza a inserção de cookie para apenas uma ocorrência por conexão TCP, essa otimização NÃO DEVE ser usada

<div>


> [!NOTE]  
> Configurações típicas do balanceador de carga de hardware usam afinidade de endereço de origem e um tempo de vida de sessão de 20 min. TCP, que é bom para clientes do Lync Server e do Lync 2013 porque o estado da sessão é mantido por meio do uso do cliente e/ou da interação do aplicativo.



</div>

Se estiver implantando dispositivos móveis, o balanceador de carga de hardware deverá ser capaz de balancear a carga da solicitação individual em uma sessão TCP (na verdade, você deve poder balancear a carga de uma solicitação individual com base no endereço IP de destino).

<div>


> [!WARNING]  
> Os balanceadores de carga de hardware F5 têm um recurso chamado OneConnect que assegura que todas as solicitações de uma conexão TCP tenham a carga balanceada individualmente. Se estiver implantando dispositivos móveis, verifique se o fornecedor do balanceador de carga de hardware tem o mesmo recurso. Os aplicativos móveis mais recentes do Apple iOS exigem a versão 1.2 do protocolo TLS. O F5 oferece configurações específicas para isso.<BR>Para obter detalhes sobre balanceadores de carga de hardware de terceiros, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A>



</div>

A seguir, são apresentados os requisitos do balanceador de carga de hardware para serviços Web do pool de diretores e de front-end:

  - Para VIPs de serviços Web internos, defina\_persistência de endereço de origem (porta interna 80, 443) no balanceador de carga de hardware. Para o Lync Server 2013,\_a persistência do endereço de origem significa que várias conexões provenientes de um único endereço IP são sempre enviadas a um servidor para manter o estado da sessão.

  - Use um tempo de ociosidade de TCP de 1.800 segundos.

  - No firewall entre o proxy reverso e o balanceador de carga de hardware do pool de próximo salto, crie uma regra que permita o tráfego https: na porta 443 do proxy reverso para o balanceador de carga de hardware. O balanceador de carga de hardware deve ser configurado para ouvir as portas 80, 443 e 4443.

<div>


> [!IMPORTANT]  
> Para ler mais sobre a configuração do balanceador de carga de hardware, revise o <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Resumo de porta-borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a>Resumo dos requisitos de afinidade do balanceador de carga de hardware


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Local do cliente/usuário</th>
<th>Requisitos de afinidade de FQDN de serviços Web externos</th>
<th>Requisitos de afinidade de FQDN de serviços Web internos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (usuários internos e externos)</p>
<p>Dispositivo móvel (usuários internos e externos)</p></td>
<td><p>Sem afinidade</p></td>
<td><p>Afinidade do endereço de origem</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (apenas usuários externos)</p>
<p>Dispositivo móvel (usuários internos e externos)</p></td>
<td><p>Sem afinidade</p></td>
<td><p>Afinidade do endereço de origem</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (apenas usuários internos)</p>
<p>Dispositivo móvel (não implantado)</p></td>
<td><p>Sem afinidade</p></td>
<td><p>Afinidade do endereço de origem</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a>Monitoramento de portas dos balanceadores de carga de hardware

Defina o monitoramento de portas nos balanceadores de carga de hardware para determinar quando serviços específicos não estão mais disponíveis devido a uma falha de hardware ou comunicação. Por exemplo, se o serviço de servidor front-end (RTCSRV) parar porque o servidor front-end ou o pool de front-ends falha, o monitoramento do HLB também deve parar de receber tráfego nos serviços Web. Implante o monitoramento de portas no HLB para monitorar o seguinte:

### <a name="front-end-server-user-pool--hlb-internal-interface"></a>Pool de usuários do servidor front-end – interface interna do HLB

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
<th>IP/porta virtual</th>
<th>Porta do nó</th>
<th>Máquina/monitor do nó</th>
<th>Perfil de persistência</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;int_mco_443_vs&gt;da Web do pool</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origem</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;int_mco_80_vs&gt;da Web do pool</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Origem</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a>Pool de usuários do servidor front-end – interface externa do HLB

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
<th>IP/porta virtual</th>
<th>Porta do nó</th>
<th>Máquina/monitor do nó</th>
<th>Perfil de persistência</th>
<th>Observações</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;web_mco_443_vs&gt;de pool</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Nenhum</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;web_mco_80_vs&gt;de pool</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Front-end</p>
<p>5061</p></td>
<td><p>Nenhum</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

