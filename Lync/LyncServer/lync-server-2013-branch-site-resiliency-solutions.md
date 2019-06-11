---
title: 'Lync Server 2013: Soluções de resiliência do site de filial'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a>Soluções de resiliência do site de filial no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-10_

A resiliência de sites de filial proporciona vantagens evidentes à sua organização. Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter o serviço Enterprise Voice e o correio de voz (se você definir as configurações de redirecionamento de caixa postal para obter detalhes, consulte [requisitos de resiliência de site para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)). Entretanto, em sites com menos de 25 usuários, a solução de resiliência poderá não gerar um retorno adequado sobre o investimento.

Há três opções para fornecer a resiliência do site de filial. A tabela a seguir o ajudará a determinar qual opção é a melhor para sua organização.

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
<td><p>Hospedar entre 25 e 1.000 usuários no seu site de filial e se o retorno sobre o investimento não permitir uma implantação completa ou quando não houver suporte administrativo local disponível</p></td>
<td><p>Aparelho de Filial Persistente</p>
<p>O appliance de ramificação sobreviventes é um servidor blade padrão do setor com um servidor de registro e mediação do Lync Server executado no Windows Server 2008 R2. O aparelho de ramificação sobreviventes também contém um gateway PSTN (rede telefônica pública comutada). Dispositivos qualificados de terceiros (desenvolvidos por parceiros da Microsoft no programa de qualificação/certificação SBA [Aparelho de Filial Persistente]) fornecem uma conexão PSTN contínua em caso de falha da WAN, mas essa abordagem não oferece presença e conferência resilientes porque esses recursos dependem dos Servidores Front-End do site central.</p>
<p>Para obter detalhes sobre aparelhos de ramificação sobreviventes &quot;, consulte detalhes do aplicativo da&quot; ramificação sobreviventes mais adiante neste tópico.</p>
<p><strong>Observação:</strong> Se você decidir usar também um tronco SIP com o seu aparelho de ramificação sobreviventes, entre em contato com o fornecedor da sua agência para saber mais sobre qual provedor de serviços é melhor para a sua organização.</p></td>
</tr>
<tr class="even">
<td><p>Host entre os usuários do 1000 e do 2000 no seu site da sua filial, sem conexão de WAN resistente e com administradores treinados do Lync Server disponíveis</p></td>
<td><p>Servidor de ramificação sobreviventes ou dois aparelhos de ramificação sobreviventes.</p>
<p>O servidor de ramificação sobreviventes é uma reunião do Windows Server que especifica requisitos de hardware que têm software do Lync Server registrar e Media Server instalado. Ele deve estar conectado a um provedor de serviços telefônicos por meio de um gateway PSTN ou de um tronco SIP.</p>
<p>Para obter detalhes sobre os servidores de ramificação &quot;sobreviventes, consulte detalhes do servidor&quot; de ramificação sobreviventes, posteriormente neste tópico.</p></td>
</tr>
<tr class="odd">
<td><p>Se você precisar de recursos de presença e conferência além dos recursos de voz para até 5000 usuários, e tiver administradores do Lync Server treinados disponíveis</p></td>
<td><p>Implante como um site central com um servidor Standard Edition e não como um site de filial.</p>
<p>Uma implantação completa do Lync Server fornece uma conexão PSTN contínua e uma presença de presença resiliente e uma conferência em caso de falha de WAN.</p>
<p>Para obter detalhes sobre como se preparar para esta solução, consulte <a href="lync-server-2013-planning-for-your-organization.md">planejamento da organização para o Lync Server 2013</a>, determinando os <a href="lync-server-2013-determining-your-system-requirements.md">requisitos do sistema para o Lync Server 2013</a>, determinando os <a href="lync-server-2013-determining-your-infrastructure-requirements.md">requisitos de infraestrutura do Lync Server 2013</a>e outras seções relevantes da documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a>Topologias de resiliência

A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.

**Opções de resiliência do site de filial**

![Opções de resiliência] de ramificação de voz (images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opções de resiliência") de ramificação de voz

</div>

<div>

## <a name="survivable-branch-appliance-details"></a>Detalhes do Aparelho de Filial Persistente

O aparelho de ramificação do Lync Server que se resobreviver inclui os seguintes componentes:

  - Um Registrador Avançado para autenticação do usuário, registro e roteamento de chamadas

  - Um Servidor de Mediação para tratar a sinalização entre o Registrador Avançado e o gateway PSTN

  - Um gateway PSTN para o roteamento de chamadas para a PSTN como um transporte fallback no caso de uma interrupção da WAN

  - O SQL Server Express para armazenamento de dados local do usuário

O aparelho de ramificação sobreviventes também inclui troncos PSTN, portas analógicas e adaptador Ethernet.

Se a conexão de WAN do site de filial com um site central ficar indisponível, os usuários da ramificação interna continuarão a ser registrados com o registrador de appliances da ramificação sobreviventes e obter serviço de voz ininterrupto usando a conexão de aparelho de ramificação sobreviventes para a PSTN. Os usuários do site de filial que se conectarem de casa ou de outros locais remotos serão capazes de se registrar em um servidor do Registrador Avançado em um site central quando um link WAN com o site de filial não estiver disponível. Esses usuários contarão com total funcionalidade de comunicações unificadas, sendo a única exceção as chamadas de entrada para o site de filial, que irão para a caixa postal. Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deverá ser restabelecida para os usuários do site de filial. Nem o failover para o aparelho de ramificação sobreviventes nem a restauração do serviço exige a presença de um administrador de ti.

O Lync Server tem suporte para até dois appliances de ramificação sobreviventes em um site de filial.

<div>


> [!NOTE]  
> Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a>Visão geral da implantação do aparelho de filial persistente

O aparelho para filiais sobreviventes é fabricado por fabricantes de equipamento original em parceria com a Microsoft e implantado em nome de revendedores de valor agregado. Essa implantação só deve ocorrer após a implantação do Lync Server no site central, uma conexão de WAN com o site de filial e os usuários do site de filiais estiverem habilitados para o Enterprise Voice.

Para obter detalhes sobre essas fases, consulte Implantando [um aplicativo ou aplicativo de ramificação sobreviventes com o Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) na documentação de implantação.


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
<td><p>Configurar os serviços de domínio do Active Directory para o aparelho de ramificação sobreviventes</p></td>
<td><p><strong>No site central:</strong></p>
<ol>
<li><p>Crie uma conta de usuário de domínio (ou identidade empresarial) para o técnico que instalará e ativará o aparelho de ramificação sobreviventes no site da filial.</p></li>
<li><p>Crie uma conta de computador (com o nome de domínio totalmente qualificado (FQDN) aplicável) para o aparelho de ramificação sobreviventes nos serviços de domínio Active Directory.</p></li>
<li><p>Em Construtor de topologia, crie e publique o aparelho de ramificação sobreviventes.</p></li>
</ol></td>
<td><p>A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians. O aparelho de ramificação sobreviventes deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o construtor de topologias.</p></td>
</tr>
<tr class="even">
<td><p>Instale e ative o aparelho de ramificação sobreviventes.</p></td>
<td><p><strong>No site de filial:</strong></p>
<ol>
<li><p>Conecte o aparelho de ramificação sobreviventes a uma porta Ethernet e a uma porta PSTN.</p></li>
<li><p>Inicie o aparelho de ramificação sobreviventes.</p></li>
<li><p>Ingresse na ramificação da ramificação sobreviventes para o domínio usando a conta de usuário do domínio criada para o aparelho de ramificação sobreviventes no site central. Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador.</p></li>
<li><p>Configure o aparelho de ramificação sobreviventes usando a interface de usuário do OEM.</p></li>
<li><p>Teste a conectividade PSTN.</p></li>
</ol></td>
<td><p>A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a>Detalhes do Servidor de Filial Persistente

Em Construtor de topologias, crie o site de ramificação, adicione o servidor de ramificação sobreviventes a esse site e execute o assistente de implantação do Lync Server no computador onde você deseja instalar a função.

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

