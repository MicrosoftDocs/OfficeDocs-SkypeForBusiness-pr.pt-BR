---
title: 'Lync Server 2013: soluções de resiliência de site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72d07e1ccdae6c433de92057e6e9414fff20153
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluções de resiliência de site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-10_

Há algumas vantagens óbvias para fornecer resiliência de site de filial para sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter o serviço Enterprise Voice e a caixa postal (se você definir configurações de redirecionamento de caixa postal; para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). No entanto, para sites com menos de 25 usuários, uma solução de resiliência pode não fornecer um retorno de investimento suficiente.

Se decidir fornecer a resiliência do site de filial, você tem três opções. Use a tabela a seguir para ajudá-lo a determinar qual opção é a melhor para sua organização.

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se você…</th>
<th>Recomendamos que você use um(a)…</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hospede entre 25 e 1.000 usuários no seu site de filial se o retorno sobre o investimento não suportar uma implantação completa ou em um local em que o suporte administrativo não estiver disponível</p></td>
<td><p>Aplicativo de Filial Persistente</p>
<p>O aparelho de filial persistente é um servidor de lâmina padrão da indústria com um registrador de servidor do Lync e servidor de mediação executando no Windows Server 2008 R2. O aparelho de filial persistente também contém um gateway PSTN (rede telefônica pública comutada). Dispositivos qualificados de terceiros (desenvolvidos pelos parceiros da Microsoft no programa de qualificação/certificação SBA [aparelho de filial persistente]) fornece uma conexão PSTN contínua caso uma WAN falhe, mas essa abordagem não fornece a presença e a conferência resilientes porque esses recursos dependem do servidores Front-End no site central.</p>
<p>Para obter detalhes sobre aparelhos de filial persistente, &quot;consulte detalhes do aparelho de filial&quot; persistente, posteriormente neste tópico.</p>
<p><strong>Observação:</strong> Se você optar por usar também um tronco SIP com seu aparelho de filial persistente, entre em contato com seu fornecedor de aparelho de filial persistente para saber mais sobre qual provedor de serviços é melhor para sua organização.</p></td>
</tr>
<tr class="even">
<td><p>Host entre 1000 e 2000 usuários no seu site de filial, não tem uma conexão WAN resiliente e tenha administradores treinados do Lync Server disponíveis</p></td>
<td><p>Servidor de filial persistente ou dois aparelhos de filial persistente.</p>
<p>O servidor de filial persistente é uma reunião do Windows Server, requisitos de hardware específicos que tem o software de servidor de mediação e registrador do Lync Server instalado. Ele deve ser conectado a um gateway PSTN ou a um tronco SIP a um provedor de serviço telefônico.</p>
<p>Para obter detalhes sobre servidores de filial persistente, &quot;consulte detalhes do servidor de filial&quot; persistente, posteriormente neste tópico.</p></td>
</tr>
<tr class="odd">
<td><p>Se você precisar de recursos de presença e conferência, além de recursos de voz para até 5000 usuários, e tiver administradores treinados do Lync Server disponíveis</p></td>
<td><p>Implante como um site central com um servidor Standard Edition e não como um site de filial.</p>
<p>Uma implantação completa do Lync Server fornece uma conexão PSTN contínua e uma presença e conferência resiliente no caso de falha da WAN.</p>
<p>Para obter detalhes sobre a preparação para esta solução, consulte <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinando seus requisitos de sistema para o Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinando seus requisitos de infraestrutura para o Lync Server 2013</a>e outras seções relevantes da documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologia de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de resiliência de ramificação de voz](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opções de resiliência de ramificação de voz")

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Detalhes do aparelho de filial persistente

O aparelho de filial persistente do Lync Server inclui os seguintes componentes:

  - Um Registrador para a autenticação do usuário, registro e roteamento de chamada

  - Um Servidor de Mediação para a manipulação de sinalização entre o Registrador e o gateway PSTN

  - Um gateway PSTN para o roteamento de chamadas ao PSTN como um transporte fallback no caso de uma interrupção da WAN

  - SQL Server Express para armazenamento de dados do usuário local

O aparelho de filial persistente também inclui troncos PSTN, portas analógicas e um adaptador Ethernet.

Se a conexão WAN do site de filial com um site central ficar indisponível, os usuários da ramificação interna continuarão a ser registrados com o registrador de aparelho de filial persistente e obter serviço de voz sem interrupção usando a conexão de aparelho de filial persistente à PSTN. Os usuários do site de filial que se conectam de casa ou de outro locais remotos serão capazes de se registrar com um servidor Registrador em um site central quando um link de WAN ao site de filial estiver indisponível. Esses usuários terão a funcionalidade de comunicações completamente unificadas com única exceção de que as chamadas de entrada ao site de filial irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deve ser restabelecida aos usuários do site de filial. Nem o failover para o aparelho de filial persistente nem a restauração do serviço requer a presença de um administrador de ti.

O Lync Server oferece suporte para até dois dispositivos de filial persistente em um site de filial.

<div>


> [!NOTE]  
> Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral de implantação de aparelho de filial persistente

O aparelho de filial persistente é fabricado por fabricantes de equipamentos originais em parceria com a Microsoft e implantado em nome de revendedores de valor agregado. Essa implantação deve ocorrer somente depois que o Lync Server tiver sido implantado no site central, uma conexão WAN com o site de filial estiver em vigor e os usuários do site de filial estiverem habilitados para o Enterprise Voice.

Para obter detalhes sobre essas fases, consulte [implantando um servidor ou aparelho de filial persistente com o Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) na documentação de implantação.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Direitos do usuário</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurar os serviços de domínio do Active Directory para o aparelho de filial persistente</p></td>
<td><p><strong>No site central:</strong></p>
<ol>
<li><p>Crie uma conta de usuário de domínio (ou uma identidade corporativa) para o técnico que instalará e ativará o aparelho de filial persistente no site de filial.</p></li>
<li><p>Crie uma conta de computador (com o FQDN (nome de domínio totalmente qualificado) aplicável para o aparelho de filial persistente nos serviços de domínio do Active Directory.</p></li>
<li><p>No construtor de topologias, crie e publique o aparelho de filial persistente.</p></li>
</ol></td>
<td><p>O usuário técnico deve ser um membro do RTCUniversalSBATechnicians. O aparelho de filial persistente deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o construtor de topologias.</p></td>
</tr>
<tr class="even">
<td><p>Instale e ative o aparelho de filial persistente.</p></td>
<td><p><strong>No site de filial:</strong></p>
<ol>
<li><p>Conecte o aparelho de filial persistente a uma porta Ethernet e uma porta PSTN.</p></li>
<li><p>Inicie o aparelho de filial persistente.</p></li>
<li><p>Ingresse o aparelho de filial persistente no domínio, usando a conta de usuário de domínio criada para o aparelho de filial persistente no site central. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador.</p></li>
<li><p>Configure o aparelho de filial persistente usando a interface de usuário do OEM.</p></li>
<li><p>Teste a conectividade do PSTN.</p></li>
</ol></td>
<td><p>O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Detalhes do servidor de filial persistente

Em Construtor de topologia, crie o site de filial, adicione o servidor de filial persistente a esse site e, em seguida, execute o assistente de implantação do Lync Server no computador onde você deseja instalar a função.

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantando o Lync Server 2013](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

