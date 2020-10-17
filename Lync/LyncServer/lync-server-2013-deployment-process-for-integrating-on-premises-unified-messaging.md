---
title: Processo de implantação para integração de Unificação de mensagens local
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
ms.openlocfilehash: 53dcbeb362387c31a97ad1e26713b642f82b2390
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529118"
---
# <a name="deployment-process-for-integrating-on-premises-unified-messaging-and-lync-server-2013"></a>Processo de implantação para integração de Unificação de mensagens local e Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-17_

Se você deseja integrar a UM (Unificação de mensagens) do Exchange com o Lync Server 2013, você deve executar as tarefas descritas neste tópico. Além disso, certifique-se de examinar as práticas recomendadas de planejamento e implantação descritas em [diretrizes para integrar a Unificação de mensagens local e o Lync Server 2013](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md). Este tópico pressupõe que você implantou o Lync Server 2013 com um servidor de mediação colocado e que você habilitou usuários para o Lync Server 2013, mas não necessariamente que você tenha executado todas as etapas de implantação e configuração para habilitar o Enterprise Voice, conforme descrito em [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) na documentação de implantação.

<div>

## <a name="unified-messaging-integration-process"></a>Processo de integração de Unificação de mensagens

<div>


> [!IMPORTANT]
> É importante que você coordene com os administradores do Exchange da sua organização para confirmar as tarefas que cada um executará para ajudar a garantir uma integração tranqüila e bem-sucedida.



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
<th>Grupos e funções exigidos</th>
<th>Documentação da implantação</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Implante uma das seguintes opções:</p>
<ul>
<li><p>Microsoft Exchange Server 2007 Service Pack 1 (SP2) ou Service Pack mais recente</p></li>
<li><p>Microsoft Exchange Server 2010 ou Service Pack mais recente</p></li>
<li><p>Microsoft Exchange Server 2013</p></li>
</ul></td>
<td><p>Se você estiver usando o Microsoft Exchange Server 2013, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</p>
<ul>
<li><p>Acesso para Cliente</p></li>
<li><p>Caixa de correio</p></li>
</ul>
<p>Se o Microsoft Exchange Server 2013 e UM (Unificação de mensagens) do Exchange estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013.</p>
<p>Se você estiver usando o Exchange 2010, instale as seguintes funções do Exchange Server na mesma floresta ou em uma floresta diferente como o Lync Server 2013:</p>
<ul>
<li><p>Unificação de Mensagens</p></li>
<li><p>Transporte de Hub</p></li>
<li><p>Acesso para Cliente</p></li>
<li><p>Caixa de correio</p></li>
</ul>
<p>Se o Lync Server 2013 e a Unificação de mensagens do Exchange estiverem instalados em florestas diferentes, configure cada floresta do Exchange para confiar na floresta do Lync Server 2013.</p></td>
<td><p>Administradores corporativos (se este for o primeiro servidor do Exchange na organização)</p>
<p>-OU-</p>
<p>Administrador da organização do Exchange (se este não for o primeiro servidor do Exchange na organização)</p></td>
<td><p>Consulte a documentação apropriada para sua versão do Exchange Server:</p>
<dl>
<dt><span></span></dt>
<dd><p>Documentação de implantação do Exchange Server 2007 em <a href="https://go.microsoft.com/fwlink/p/?linkid=268694">https://go.microsoft.com/fwlink/p/?LinkId=268694</a> .</p>
</dd>
<dt><span></span></dt>
<dd><p>Documentação de implantação do Exchange Server 2010 ou Service Pack mais recente em <a href="https://go.microsoft.com/fwlink/p/?linkid=268695">https://go.microsoft.com/fwlink/p/?LinkId=268695</a> .</p>
</dd>
<dt><span></span></dt>
<dd><p>Microsoft Exchange Server 2013 planejamento e implantação em <a href="https://go.microsoft.com/fwlink/p/?linkid=266569">https://go.microsoft.com/fwlink/p/?LinkId=266569</a> .</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p>Instalar certificados.</p></td>
<td><p>Baixe e instale certificados para cada servidor de UM do Exchange de uma autoridade de certificação raiz confiável (AC). Os certificados são necessários para a MTLS (segurança de nível de transporte) mútuo entre os servidores que executam o UM do Exchange e o Lync Server 2013.</p></td>
<td><p>Administradores</p></td>
<td><p><a href="lync-server-2013-configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging.md">Configurar certificados no servidor que executa a Unificação de mensagens do Microsoft Exchange Server</a></p></td>
</tr>
<tr class="odd">
<td><p>Crie e configure um novo plano de discagem SIP do UM do Exchange.</p></td>
<td><p>No servidor UM do Exchange, crie um plano de discagem SIP com base nos requisitos de implantação específicos da sua organização.</p></td>
<td><p>Administrador da organização do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte &quot; como criar um plano de discagem de URI SIP de Unificação &quot; de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=268632">https://go.microsoft.com/fwlink/p/?linkId=268632</a> .</p>
<p>Para o Exchange 2010 ou Service Pack mais recente, consulte &quot; criar um plano de discagem de um &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268674">https://go.microsoft.com/fwlink/p/?linkId=268674</a> .</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="even">
<td><p>Definir configurações de segurança para o plano de discagem SIP do UM do Exchange.</p></td>
<td><p>Para criptografar o tráfego de voz da empresa, defina as configurações de segurança no plano de discagem SIP do UM do Exchange como <strong>SIP protegido</strong> ou <strong>protegido</strong>. Esta é uma etapa especialmente importante se você implantou ou planeja implantar dispositivos do Lync Phone Edition em seu ambiente. Para que dispositivos do Lync Phone Edition funcionem em um ambiente com integração com UM do Exchange, as configurações de criptografia do Lync Server devem ser alinhadas com as configurações de segurança do plano de discagem de UM do Exchange Para obter detalhes, consulte a documentação de implantação.</p></td>
<td><p>Administrador da organização do Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></p>
<p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte também:</p>
<p>&quot;Como configurar a segurança em um plano de discagem de Unificação de mensagens &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268696">https://go.microsoft.com/fwlink/p/?LinkId=268696</a> .</p>
<p>Para o Exchange 2010 ou Service Pack mais recente, consulte também:</p>
<p>&quot;Configurar a segurança VoIP em um plano de discagem de UM &quot; <a href="https://go.microsoft.com/fwlink/p/?linkid=268697">https://go.microsoft.com/fwlink/p/?LinkId=268697</a> .</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="odd">
<td><p>Adicione servidores de Unificação de mensagens ao plano de discagem SIP UM do Exchange.</p></td>
<td><p>Para habilitar um servidor de Unificação de mensagens recém-instalado para responder e processar chamadas de entrada, você deve adicionar o servidor de Unificação de mensagens a um plano de discagem de UM. Nesse caso, adicione o servidor ao plano de discagem SIP UM do Exchange.</p></td>
<td><p>Administradores</p>
<p>Administradores do Exchange Server</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte &quot; como adicionar um servidor de Unificação de mensagens a um plano de discagem &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268681">https://go.microsoft.com/fwlink/p/?linkId=268681</a> .</p>
<p>Para o Exchange 2010 ou Service Pack mais recente, consulte &quot; Exibir ou configurar as propriedades de um servidor de um &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268682">https://go.microsoft.com/fwlink/p/?linkId=268682</a> .</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="even">
<td><p>Configurar caixas de correio com endereços SIP.</p></td>
<td><p>Atribua endereços SIP às caixas de correio de usuários do Enterprise Voice que usarão os recursos de UM do Exchange.</p></td>
<td><p>Administrador do Lync Server 2013</p>
<p>Administrador de destinatários do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte &quot; como adicionar, remover ou modificar um endereço SIP para um usuário do UM-Enabled &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268698">https://go.microsoft.com/fwlink/p/?LinkId=268698</a> .</p>
<p>Para o Exchange 2010 ou Service Pack mais recente, consulte &quot; modificar um endereço SIP para um usuário do UM-Enabled &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268699">https://go.microsoft.com/fwlink/p/?LinkId=268699</a> .</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
<tr class="odd">
<td><p>Execute o script exchucutil.ps1.</p></td>
<td><p>No servidor que executa os serviços de UM do Exchange, abra o Shell de gerenciamento do Exchange e execute o exchucutil.ps1 script, que faz o seguinte:</p>
<ul>
<li><p>Concede ao Lync Server 2013 permissão para ler objetos dos serviços de domínio do Active Directory da UM do Exchange, especificamente, os planos de discagem SIP criados na tarefa anterior.</p></li>
<li><p>Cria um objeto de gateway IP de Unificação de mensagens no Active Directory para cada pool do Lync Server 2013 Enterprise Edition ou servidor Standard Edition que hospeda os usuários habilitados para o Enterprise Voice.</p></li>
<li><p>Cria um grupo de busca de UM do Exchange para cada gateway. O identificador piloto do grupo de busca será o nome do plano de discagem associado ao gateway correspondente. Eles precisam ser mapeados 1:1 se houver mais de um plano de discagem.</p></li>
</ul></td>
<td><p>Administrador da organização do Exchange</p>
<p>Administrador de destinatários do Exchange</p></td>
<td><p><a href="lync-server-2013-configure-unified-messaging-on-microsoft-exchange.md">Configurar a Unificação de mensagens no Microsoft Exchange para o Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configure os planos de discagem do Lync Server 2013.</p></td>
<td><p>Se você estiver integrando com o Exchange 2007 SP1 ou Service Pack mais recente ou o Exchange 2010, crie um novo plano de discagem do Enterprise Voice com um nome que corresponda ao nome de domínio totalmente qualificado (FQDN) do plano de discagem do UM do Exchange.</p>



> [!NOTE]
> Você precisará fazer isso para cada plano de discagem de UM.


<p>Se você estiver integrando com o Exchange 2010 SP1, certifique-se de que os planos de discagem do Enterprise Voice em nível global/local ou de pool adequados foram configurados.</p>



> [!NOTE]
> Se você estiver integrando com o Exchange 2010 SP1, o plano de discagem do Lync Server e os nomes do plano de discagem SIP da UM do Exchange não precisam corresponder.

</td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configuring-dial-plans.md">Configurando planos de discagem no Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Execute a ferramenta de integração do UM do Exchange.</p></td>
<td><p>No Lync Server 2013, execute <strong>ocsumutil.exe</strong>, que:</p>
<ul>
<li><p>Cria objetos de contato de acesso do assinante e atendedor automático.</p></li>
<li><p>Valida que há um plano de discagem do Enterprise Voice com um nome que corresponde ao FQDN do plano de discagem do UM do Exchange. Se você estiver executando o Exchange 2010 SP1 ou posterior, os nomes do plano de discagem não precisarão corresponder e você poderá ignorar o aviso da ferramenta sobre isso.</p></li>
</ul>
<p>Essa ferramenta funciona examinando as configurações do Active Directory para UM do Exchange e permitindo que o administrador do Lync Server 2013 visualize, crie e edite objetos de contato.</p></td>
<td><p>RTCUniversalServerAdmins <em>e</em> RTCUniversalUserAdmins</p>



> [!IMPORTANT]
> Para executar o ocsumutil.exe com êxito, o usuário deve pertencer a esses dois grupos.





> [!NOTE]
> Para criar objetos de contato, o usuário que executa o ocsumutil.exe deve ter a permissão correta para a UO (unidade organizacional) do Active Directory em que os novos objetos de contato estão armazenados. Essa permissão pode ser concedida executando-se o cmdlet <STRONG>Grant-CsOUPermission</STRONG> . Para obter detalhes, consulte a documentação do Shell de Gerenciamento do Lync Server.

</td>
<td><p><a href="lync-server-2013-configure-lync-server-2013-to-work-with-unified-messaging-on-microsoft-exchange-server.md">Configurar o Lync Server 2013 para trabalhar com a Unificação de mensagens no Microsoft Exchange Server</a></p></td>
</tr>
<tr class="even">
<td><p>Se necessário, execute outras etapas de configuração do Enterprise Voice.</p></td>
<td><p>Se você ainda não tiver configurado as configurações do Enterprise Voice em seus servidores ou usuários, siga um ou mais destes procedimentos:</p>
<ul>
<li><p>Implantar e configurar</p>
<p>Gateways PSTN (rede telefônica pública comutada) e servidores de mediação</p></li>
<li><p>Definir políticas de voz, registros de uso de PSTN e rotas de chamada de saída.</p></li>
<li><p>Habilitar usuários para o Enterprise Voice.</p></li>
<li><p>Opcionalmente, configure usuários específicos com planos de discagem.</p></li>
</ul>
<p>Outras etapas de configuração podem ser necessárias dependendo dos recursos do Enterprise Voice que você habilitar.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>RTCUniversalUserAdmins</p></td>
<td><p>Confira os tópicos nas seções a seguir:</p>
<ul>
<li><p><a href="lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md">Configurando políticas de voz, registros de uso de PSTN e rotas de voz no Lync Server 2013</a></p></li>
<li><p><a href="lync-server-2013-deploying-enterprise-voice.md">Implantando o Enterprise Voice no Lync Server 2013</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Habilitar usuários do Enterprise Voice para o UM do Exchange.</p></td>
<td><p>No servidor UM do Exchange, certifique-se de que uma política de caixa de correio de Unificação de mensagens tenha sido criada e que cada usuário tenha uma atribuição de número de ramal exclusivo e habilite o usuário para a Unificação de mensagens.</p></td>
<td><p>Administrador de destinatários do Exchange</p></td>
<td><p>Para o Exchange 2007 SP1 ou Service Pack mais recente, consulte &quot; como habilitar um usuário para Unificação de mensagens &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268700">https://go.microsoft.com/fwlink/p/?LinkId=268700</a> .</p>
<p>Para o Exchange 2010 ou Service Pack mais recente, consulte &quot; habilitar um usuário para Unificação de mensagens &quot; em <a href="https://go.microsoft.com/fwlink/p/?linkid=268701">https://go.microsoft.com/fwlink/p/?LinkId=268701</a> .</p>
<p>Para o Exchange 2013, consulte Unificação de mensagens em <a href="https://go.microsoft.com/fwlink/p/?linkid=266579">https://go.microsoft.com/fwlink/p/?LinkId=266579</a> .</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

