---
title: 'Lync Server 2013: planejamento de implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b0efc4a6a9e9f195705801969b8459c17855388
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planejamento de implantações híbridas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-05-25_

Você deve considerar os requisitos a seguir para usuários e sua infraestrutura de rede ao planejar uma implantação híbrida.

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Você deve ter o seguinte configurado no seu ambiente para implementar e implantar uma implantação híbrida.

  - Um locatário do Microsoft Office 365 com o Skype for Business online habilitado. Observe que você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.

  - Uma única implantação local (infraestrutura) do Skype for Business Server ou do Lync Server que é implantada em uma topologia com suporte. Consulte requisitos de topologia.
    
    Para obter informações sobre como configurar sua implantação do Lync Server 2013 ou do Lync Server 2010 para o híbrido, consulte [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).

  - Ferramentas administrativas do Skype for Business Server 2015. Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, poderá usar as ferramentas administrativas do Lync Server 2013.

  - Para dar suporte ao logon único com o Office 365 para que os usuários possam usar as mesmas credenciais de logon para entrar no Office como eles fazem no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect. Você também pode usar o AD FS (serviços de Federação do Active Directory) para logon único com o Office 365.
    
    Para mais informações, confira [Integrar suas identidades locais ao Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Uma solução de sincronização de diretório único para manter os objetos do Active Directory online e on-line sincronizados. Para obter detalhes sobre a sincronização de diretórios, consulte [ferramentas de integração de diretórios](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Suporte ao cliente do Lync

Há algumas diferenças nos recursos suportados nos clientes do Lync, bem como os recursos disponíveis em ambientes locais e online. Antes de decidir onde você deseja usuários domésticos em sua organização, você pode exibir o suporte ao cliente para as várias configurações do Lync Server. Os seguintes clientes são compatíveis com o Skype for Business online em uma implantação híbrida do Lync:

  - Lync 2010

  - Lync 2013

  - Aplicativo Lync da Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync para Mac 2011

  - Sistema de salas do Lync

  - Lync Basic 2013

Para obter detalhes sobre o suporte ao cliente, consulte os seguintes tópicos:

  - [Clientes para Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tabelas de comparação de clientes para o Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tabelas de comparação de clientes móveis para o Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

Para configurar sua implantação para o híbrido com o Skype for Business Online, você precisa ter uma das seguintes topologias compatíveis:

  - Uma implantação do Skype for Business Server 2015 com todos os servidores que executam o Skype for Business Server 2015.

  - Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.

  - Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as atualizações cumulativas mais recentes.
    
      - O servidor de borda de Federação e o servidor de próximo salto do servidor de borda de Federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes.
    
      - As ferramentas administrativas do Skype for Business Server 2015 ou do Lync Server 2013 devem ser instaladas em pelo menos um servidor ou estação de trabalho de gerenciamento.

  - Uma implantação mista do Lync Server 2013 e do Skype for Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype for Business Server 2015:
    
      - Pelo menos um pool corporativo ou servidor Standard Edition
    
      - O pool de diretores associado à Federação SIP, se existir
    
      - O pool de borda associado à Federação SIP

  - Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype for Business Server 2015:
    
      - Pelo menos um pool corporativo ou servidor Standard Edition
    
      - O pool de diretores associado à Federação SIP, se existir
    
      - O pool de borda associado à Federação SIP para o site

  - Uma implantação mista do Lync Server 2010 e Lync Server 2013 com as seguintes funções de servidor em pelo menos um site executando o Lync Server 2013:
    
      - Pelo menos um pool corporativo ou servidor Standard Edition no site
    
      - O pool de diretores associado à Federação SIP, se existir no site
    
      - O pool de borda associado à Federação SIP para o site

<div>


> [!IMPORTANT]  
> Todo o gerenciamento de usuários, incluindo as movimentações de usuários entre o local e o UNRESOLVED_TOKEN_VAL (skypeforbusiness) online, precisa ser feito usando a última versão instalada das ferramentas administrativas. As ferramentas administrativas devem ser instaladas em um servidor separado que tenha acesso de conexão à implantação local existente e à Internet. O cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-CsUser</A> para mover os usuários da sua implantação local para o UNRESOLVED_TOKEN_VAL (skype16_online) deve ser executado a partir das ferramentas administrativas conectadas à sua implantação local.



</div>

Para obter mais informações sobre as topologias suportadas, consulte [topologias compatíveis no Lync server 2013](lync-server-2013-supported-topologies.md)e [Lync Server 2013 Reference topologias for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).

Para obter informações sobre como solucionar problemas de implantações híbridas e conectar o PowerShell ao Lync Online, consulte [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisitos para listas de Federação permitidas/bloqueadas

A lista de domínios permitidos inclui domínios que têm um FQDN (nome de domínio totalmente qualificado) de borda de parceiro configurado. Às vezes, eles são chamados de *servidores parceiros permitidos* ou *parceiros de Federação direta*. Você deve estar familiarizado com a diferença entre a Federação aberta e a Federação fechada, conhecidas como *descoberta de parceiro* e lista de domínios de *parceiros permitidos*, respectivamente, em implantações locais.

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

  - A correspondência de domínio deve ser configurada da mesma para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a Federação deverá ser configurada para seu locatário online. Se a descoberta de parceiro não estiver habilitada, a Federação fechada deverá ser configurada para seu locatário online.

  - A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista de domínios bloqueados para seu locatário online.

  - A lista de domínios permitidos na implantação local deve corresponder exatamente à lista de domínios permitidos para seu locatário online.

  - A Federação deve ser habilitada para comunicações externas para o locatário online, que é configurado usando o painel de controle do Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Configurações de DNS

Ao criar registros DNS para implantações híbridas, todos os registros de DNS externos do Lync devem apontar para a infraestrutura local. Para obter detalhes sobre os registros DNS necessários, consulte [requisitos de DNS (sistema de nomes de domínio) para o Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Além disso, você precisa garantir que a resolução DNS descrita na tabela a seguir funcione em sua implantação local:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Registro DNS</p></td>
<td><p>Resolvível por</p></td>
<td><p>Requisito de DNS</p></td>
</tr>
<tr class="even">
<td><p>Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos os domínios SIP com suporte que resolvem os IP externos de borda de acesso</p></td>
<td><p>Servidor (es) de borda</p></td>
<td><p>Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber onde rotear o tráfego federado para o domínio SIP dividido entre o local e o online.</p></td>
</tr>
<tr class="odd">
<td><p>Registro (s) de DNS para o FQDN do serviço de webconferência de borda, por exemplo, webcon.contoso.com resolvendo IP (s) externo de borda de Webconferência</p></td>
<td><p>Computadores de usuários conectados à rede corporativa interna</p></td>
<td><p>Permitir que os usuários online apresentem ou exibam conteúdo em reuniões hospedadas no local. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, pesquisas e anotações compartilhadas.</p></td>
</tr>
</tbody>
</table>


Dependendo de como o DNS é configurado em sua organização, talvez seja necessário adicionar esses registros à zona de DNS hospedada internamente para o (s) domínio (s) SIP correspondente para fornecer resolução DNS interna a esses registros.

</div>

<div>

## <a name="firewall-considerations"></a>Considerações do firewall

Os computadores em sua rede devem ser capazes de realizar pesquisas de DNS da Internet padrão. Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.

Dependendo do local do seu data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de. Outlook.com). Se os firewalls da sua organização não dão suporte a configurações de nome de curinga, será necessário determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.

Consulte o tópico de ajuda sobre [URLs e intervalos de endereços IP do Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisitos de porta e protocolo

Além dos requisitos de porta para a comunicação interna do Lync Server 2013, você também deve configurar as seguintes portas.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocolo/porta</th>
<th>Aplicativos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Abrir entrada</p>
<ul>
<li><p>Serviços de Federação do Active Directory (função do servidor de federação)</p>
<p>Para obter mais informações, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</p></li>
<li><p>Serviços de Federação do Active Directory (função do servidor do proxy)</p></li>
<li><p>Portal do Microsoft Online Services</p></li>
<li><p>Portal Minha Empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente do Lync (comunicação com o Lync Online do Lync Server local)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 e 443</p></td>
<td><p>Abrir entrada</p>
<ul>
<li><p>Ferramenta de Sincronização de Diretórios do Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Abrir entrada/saída no servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Abrir entrada/saída para sessões de compartilhamento de dados</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Abrir entrada/saída para áudio, vídeo, sessões de compartilhamento de aplicativos</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Abrir entrada/saída para sessões de áudio e vídeo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Abrir saída para sessões de áudio e vídeo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Dados e contas de usuário

Em uma implantação híbrida do Lync Server 2013, qualquer usuário que você deseja hospedar no Lync Online deve ser criado primeiro na implantação local, para que a conta de usuário seja criada nos serviços de domínio do Active Directory. Você pode então mover o usuário para o Skype for Business Online, que irá mover a lista de contatos do usuário.

Ao sincronizar as contas de usuário entre suas implantações locais e Lync Online do Lync com o AD FS e o DirSync, você precisa sincronizar as contas do AD para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo que os usuários Não são movidos para o Lync Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online em sua organização poderá não funcionar conforme o esperado.

<div>


> [!IMPORTANT]  
> Se o usuário for criado usando o portal online para o Office 365, a conta de usuário não será sincronizada com o Active Directory local, e o usuário não existirá no Active Directory local. Se você já criou usuários no Lync Online e deseja configurar o híbrido com um Lync Server local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync no local no Lync Server 2013</A>.



</div>

Você também deve considerar os seguintes problemas relacionados ao usuário ao planejar uma implantação híbrida.

  - **Contatos do usuário**   o limite de contatos para os usuários do Lync Online é de 250. Qualquer contato além desse número será removido da lista de contatos do usuário quando a conta for movida para o Lync Online.

  - ****   As listas de contatos de mensagens instantâneas e de presença, os grupos e as ACLs (listas de controle de acesso) são migrados com a conta de usuário.

  - **Dados de conferência, conteúdo de reunião e reuniões**   agendadas esse conteúdo não é migrado com a conta de usuário. Os usuários devem reagendar as reuniões depois que suas contas forem migradas para o Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Recursos e políticas de usuário

  - Em um ambiente híbrido do Lync Server 2013, os usuários podem ser habilitados para mensagens instantâneas, voz e reuniões tanto no local quanto no online, mas não em ambos simultaneamente.

  - **Cliente do Lync**     alguns usuários podem exigir uma nova versão do cliente quando forem movidos para o Lync Online. Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um pool do Lync Server 2013 antes da migração para o Lync Online.
    
    Para obter mais informações sobre o suporte ao cliente, consulte [clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and Lync [clients and Network Ports supported](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Políticas e configurações locais (não-usuário)**   online e políticas locais exigem configuração separada. Você não pode definir políticas globais que se aplicam a ambos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

