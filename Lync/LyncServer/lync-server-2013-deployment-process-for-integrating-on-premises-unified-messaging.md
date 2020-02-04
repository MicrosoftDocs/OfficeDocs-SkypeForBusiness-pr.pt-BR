---
title: Processo de implantação para a integração de mensagens unificadas locais
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating on-premises Unified Messaging and Lync Server
ms:assetid: 269a4436-f09f-415b-96ab-49a64370a385
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425737(v=OCS.15)
ms:contentKeyID: 48183664
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76a45210fa90e5d2493885e54f07bb922f6d0495
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762609"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processo de implantação para integração de Unificação de Mensagens local com Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-12-17_

Se você quiser integrar o Exchange Unified Messaging (UM) com o Lync Server 2013, será necessário executar as tarefas descritas neste tópico. Além disso, certifique-se de rever as práticas recomendadas de planejamento e implantação descritas em [diretrizes para integrar a Unificação de mensagens e o Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Este tópico pressupõe que você implantou o Lync Server 2013 com um servidor de mediação posicionado e que você tenha habilitado usuários para o Lync Server 2013, mas não necessariamente que você tenha executado todas as etapas de implantação e configuração para habilitar o Enterprise Voice, conforme descrito em [implantando o Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.

<div>

## <a name="unified-messaging-integration-process"></a>Processo de integração do Unified Messaging

<div>


> [!IMPORTANT]
> É importante que você coordene com os administradores do Exchange da sua organização para confirmar as tarefas que cada um executará para garantir uma integração tranquila e bem-sucedida.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Fase</th>
<th>Etapas</th>
<th>Grupos e funções necessários</th>
<th>Documentação de Implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implante um dos seguintes:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack mais recente</p></li>
<li><p>Microsoft Exchange Server 2010 ou Service Pack mais recente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Se você estiver usando o Microsoft Exchange Server 2013, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</p>
<ul>
<li><p>Acesso do Cliente</p></li>
<li><p>Caixa de Correio</p></li>
</ul>
<p>Se o Microsoft Exchange Server 2013 e a Microsoft Exchange Unified Messaging (UM) estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta 2013 do Lync Server.</p>
<p>Se você estiver usando o Exchange 2010, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente do Lync Server 2013:</p>
<ul>
<li><p>Unified Messaging</p></li>
<li><p>Transporte de hub</p></li>
<li><p>Acesso do Cliente</p></li>
<li><p>Caixa de Correio</p></li>
</ul>
<p>Se o Lync Server 2013 e o Exchange Unified Messaging (UM) estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta 2013 do Lync Server.</p></td>
<td><p>Administradores de empresa (se esta for o primeiro Exchange Server na organização)</p>
<p>-OU-</p>
<p>Administrador da organização do Exchange (se este não for o primeiro Exchange Server na organização)</p></td>
<td><p>Consulte a documentação apropriada para sua versão do Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentação de implantação do Exchange Server <a href="http://go.microsoft.com/fwlink/p/?linkid=268694">http://go.microsoft.com/fwlink/p/?LinkId=268694</a>2007 em.</p>
</dd>
<dt><span></span></dt>
<dd><p>Exchange Server 2010 ou mais recente documentação de implantação do <a href="http://go.microsoft.com/fwlink/p/?linkid=268695">http://go.microsoft.com/fwlink/p/?LinkId=268695</a>Service Pack em.</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 planejamento e implantação em <a href="http://go.microsoft.com/fwlink/p/?linkid=266569">http://go.microsoft.com/fwlink/p/?LinkId=266569</a>.</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Instalar certificados.</p></td>
<td><p>Baixar e instalar certificados para cada servidor do Exchange UM de uma CA (autoridade de certificação) raiz confiável. Os certificados são necessários para a MTLS (Mutual Transport Level Security) entre os servidores que executam o Exchange UM e o Lync Server 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados no servidor que executa o Microsoft Exchange Server Unified Messaging</a></p></td>
</tr>
<tr class="odd">
<td><p>Crie e configure um novo plano de discagem SIP do Exchange UM.</p></td>
<td><p>No servidor Exchange UM, crie um plano de discagem SIP com base nas necessidades de implantação específicas da sua organização.</p></td>
<td><p>Administrador da organização do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte como criar um plano&quot; de discagem de URI <a href="http://go.microsoft.com/fwlink/p/?linkid=268632">http://go.microsoft.com/fwlink/p/?linkId=268632</a>SIP de Unificação de mensagens em.</p>
<p>Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte criar um plano&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268674">http://go.microsoft.com/fwlink/p/?linkId=268674</a>discagem de um em.</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Definir configurações de segurança para o plano de discagem do Exchange UM SIP.</p></td>
<td><p>Para criptografar o tráfego de voz da empresa, defina as configurações de segurança no plano de discagem do Exchange UM SIP como <strong>SIP protegido</strong> ou <strong>seguro</strong>. Essa é uma etapa especialmente importante se você tiver implantado ou planejar a implantação de dispositivos do Lync Phone Edition em seu ambiente. Para que os dispositivos do Lync Phone Edition funcionem em um ambiente com a integração de UM do Exchange, as configurações de criptografia do Lync Server devem ser alinhadas com as configurações de segurança do plano de discagem do UM Para obter detalhes, consulte a documentação de implantação.</p></td>
<td><p>Administrador da organização do Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></p>
<p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte também:</p>
<p>&quot;Como configurar a segurança em um plano&quot; de discagem da <a href="http://go.microsoft.com/fwlink/p/?linkid=268696">http://go.microsoft.com/fwlink/p/?LinkId=268696</a>Unificação de mensagens em.</p>
<p>Para o Exchange 2010 ou service pack mais recente, consulte também:</p>
<p>&quot;Configurar a segurança de VoIP em um plano&quot; <a href="http://go.microsoft.com/fwlink/p/?linkid=268697">http://go.microsoft.com/fwlink/p/?LinkId=268697</a>de discagem de um.</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Adicione servidores de Unificação de mensagens ao plano de discagem SIP do Exchange UM.</p></td>
<td><p>Para habilitar um servidor de Unificação de Mensagens recentemente instalado a responder e processar chamadas de entrada, você deve adicionar o servidor de Unificação de Mensagens a um plano de discagem de UM. Nesse caso, adicione o servidor ao plano de discagem do Exchange UM SIP.</p></td>
<td><p>Administradores</p>
<p>Administradores do Exchange Server</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar um servidor de Unificação&quot; de <a href="http://go.microsoft.com/fwlink/p/?linkid=268681">http://go.microsoft.com/fwlink/p/?linkId=268681</a>mensagens a um plano de discagem.</p>
<p>Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Exibir ou configurar as propriedades de um&quot; servidor <a href="http://go.microsoft.com/fwlink/p/?linkid=268682">http://go.microsoft.com/fwlink/p/?linkId=268682</a>de um em.</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="even">
<td><p>Configurar caixas de correio com endereços SIP.</p></td>
<td><p>Atribua endereços SIP às caixas de correio dos usuários do Enterprise Voice que usarão os recursos do Exchange UM.</p></td>
<td><p>Administrador do Lync Server 2013</p>
<p>Administrador de destinatários do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como adicionar, remover ou modificar um endereço SIP para um usuário&quot; habilitado para um. <a href="http://go.microsoft.com/fwlink/p/?linkid=268698">http://go.microsoft.com/fwlink/p/?LinkId=268698</a></p>
<p>Para o Exchange 2010 ou Service Pack mais recente &quot;, confira modificar um endereço SIP para um usuário&quot; habilitado <a href="http://go.microsoft.com/fwlink/p/?linkid=268699">http://go.microsoft.com/fwlink/p/?LinkId=268699</a>para um.</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Execute o script exchucutil.ps1.</p></td>
<td><p>No servidor que executa os serviços do Exchange UM, abra o Shell de gerenciamento do Exchange e execute o script exchucutil. ps1, que faz o seguinte:</p>
<ul>
<li><p>Concede permissão do Lync Server 2013 para ler objetos dos serviços de domínio do Active Directory de UM, especificamente, os planos de discagem SIP criados na tarefa anterior.</p></li>
<li><p>Cria um objeto gateway IP de Unificação de mensagens no Active Directory para cada pool do Lync Server 2013 Enterprise Edition ou um servidor Standard Edition que hospeda usuários habilitados para o Enterprise Voice.</p></li>
<li><p>Cria um grupo coletivo do Exchange UM para cada gateway. O identificador piloto do grupo de busca será o nome do plano de discagem associado ao gateway correspondente. Eles precisam ser mapeados individualmente se houver mais de um plano de discagem.</p></li>
</ul></td>
<td><p>Administrador da organização do Exchange</p>
<p>Administrador de destinatários do Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurar planos de discagem do Lync Server 2013.</p></td>
<td><p>Se você estiver integrando com o Exchange 2007 SP1 ou Service Pack mais recente ou o Exchange 2010, crie um novo plano de discagem do Enterprise Voice com um nome que corresponda ao nome de domínio totalmente qualificado (FQDN) do plano de discagem de UM do Exchange.</p>



> [!NOTE]
> Você precisará fazer isso para cada plano de discagem UM.


<p>Se você estiver integrando com o Exchange 2010 SP1, certifique-se de que os planos de discagem de voz corporativos e de nível global/nível de pool adequados foram configurados.</p>



> [!NOTE]
> Se você estiver integrando com o Exchange 2010 SP1, o plano de discagem do Lync Server e os nomes dos planos de discagem do Exchange UM SIP não precisam ser correspondentes.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurando planos de discagem no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Execute a ferramenta de integração de UM do Exchange.</p></td>
<td><p>No Lync Server 2013, execute <strong>ocsumutil. exe</strong>, que:</p>
<ul>
<li><p>Cria objetos de contato do Acesso do Assinante e Atendedor Automático.</p></li>
<li><p>Valida se há um plano de discagem de voz empresarial com um nome que corresponda ao FQDN do plano de discagem do Exchange. Se você estiver executando o Exchange 2010 SP1 ou posterior, os nomes dos planos de discagem não precisam corresponder, e você pode ignorar o aviso da ferramenta sobre isso.</p></li>
</ul>
<p>Essa ferramenta funciona examinando as configurações de UM do Active Directory para UM do Exchange e permitindo que o administrador do Lync Server 2013 exiba, crie e edite objetos de contato.</p></td>
<td><p>RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Para executar com êxito o ocsumutil.exe, o usuário deve pertencer aos dois grupos.





> [!NOTE]
> Para criar objetos de Contato, o usuário que executa ocsumutil.exe deve ter a permissão correta para a unidade organizacional (OU) do Active Directory onde novos objetos de contato são armazenados. Esta permissão pode ser concedida executando-se o cmdlet <STRONG>Grant-CsOUPermission</STRONG>. Para obter detalhes, consulte a documentação do Shell de gerenciamento do Lync Server.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar o Lync Server 2013 para trabalhar com a Unificação de Mensagens no Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Se necessário, realize outras etapas de configuração do Enterprise Voice.</p></td>
<td><p>Se você ainda não configurou as configurações do Enterprise Voice em seus servidores ou usuários, siga um ou mais destes procedimentos:</p>
<ul>
<li><p>Implantar e configurar</p>
<p>Gateways PSTN e Servidores de Mediação</p></li>
<li><p>Defina as políticas de voz, os registros de uso PSTN e os roteamentos de chamada de saída.</p></li>
<li><p>Habilite usuários para o Enterprise Voice.</p></li>
<li><p>Opcionalmente, configure usuários específicos com planos de discagem.</p></li>
</ul>
<p>Outras etapas de configuração podem ser necessárias dependendo dos recursos da Enterprise Voice que você habilitar.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Consulte os tópicos nas seções a seguir:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurar políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Habilitar usuários do Enterprise Voice para o Exchange UM.</p></td>
<td><p>No servidor Exchange UM, verifique se uma política de caixa de correio de Unificação de mensagens foi criada e se cada usuário tem uma atribuição de número de ramal exclusivo e, em seguida, habilite o usuário para a Unificação de mensagens.</p></td>
<td><p>Administrador de destinatários do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente &quot;, consulte Como habilitar um usuário para a&quot; Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=268700">http://go.microsoft.com/fwlink/p/?LinkId=268700</a>.</p>
<p>Para o Exchange 2010 ou Service Pack mais recente &quot;, consulte Habilitar um usuário para&quot; Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=268701">http://go.microsoft.com/fwlink/p/?LinkId=268701</a>.</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="http://go.microsoft.com/fwlink/p/?linkid=266579">http://go.microsoft.com/fwlink/p/?LinkId=266579</a>.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

