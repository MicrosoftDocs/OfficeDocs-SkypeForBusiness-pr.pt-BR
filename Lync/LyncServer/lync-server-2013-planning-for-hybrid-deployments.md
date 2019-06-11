---
title: 'Lync Server 2013: Planejando implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a>Planejamento de implantações híbridas do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-05-25_

Você deve considerar os requisitos a seguir para usuários e sua infraestrutura de rede durante o planejamento de uma implantação híbrida.

<div>

## <a name="infrastructure-requirements"></a>Requisitos de infraestrutura

Você deve ter os seguintes itens configurados no seu ambiente para implementar e implantar uma implantação híbrida.

  - Um locatário do Microsoft Office 365 com o Skype for Business online habilitado. Observe que você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.

  - Uma única implantação local (infraestrutura) do Skype for Business Server ou do Lync Server que é implantada em uma topologia com suporte. Consulte requisitos de topologia.
    
    Para obter informações sobre como configurar sua implantação do Lync Server 2013 ou do Lync Server 2010 para híbrido, confira Configurando implantações híbridas do [Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).

  - Ferramentas administrativas do Skype for Business Server 2015. Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, poderá usar as ferramentas administrativas do Lync Server 2013.

  - Para dar suporte ao logon único com o Office 365 para que os usuários possam usar as mesmas credenciais de logon para entrar no Office como se estivessem no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect. É possível também usar Serviços de Federação do Active Directory (AD FS) para login único com o Office 365.
    
    Para obter mais informações, consulte [integrando suas identidades locais com o Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).

  - Uma única solução de sincronização de diretório para manter seus objetos locais e online do Active Directory sincronizados. Para obter detalhes sobre a sincronização de diretório, consulte [ferramentas de integração de diretório](http://go.microsoft.com/fwlink/p/?linkid=530320).

</div>

<div>

## <a name="lync-client-support"></a>Suporte ao cliente do Lync

Há algumas diferenças nos recursos com suporte em clientes do Lync, bem como os recursos disponíveis em ambientes locais e online. Antes de decidir onde você deseja usuários domésticos em sua organização, você pode ver o suporte do cliente para as várias configurações do Lync Server. Os clientes a seguir são compatíveis com o Skype for Business online em uma implantação híbrida do Lync:

  - Lync 2010

  - Lync 2013

  - Aplicativo Lync Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync para Mac 2011

  - Sistema de Salas do Lync

  - Lync Basic 2013

Para obter detalhes sobre o suporte ao cliente, consulte os seguintes tópicos:

  - [Clientes para Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tabelas de comparação dos clientes para o Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tabela de comparação de clientes móveis para o Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a>Requisitos de topologia

Para configurar sua implantação do Hybrid com o Skype for Business Online, você precisa ter uma das seguintes topologias compatíveis:

  - Uma implantação do Skype for Business Server 2015 com todos os servidores que executam o Skype for Business Server 2015.

  - Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.

  - Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as atualizações cumulativas mais recentes.
    
      - O servidor de borda de Federação e o próximo servidor de salto do servidor de borda de Federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes.
    
      - O Skype for Business Server 2015 ou o Lync Server 2013 ferramentas administrativas devem ser instalados em pelo menos um servidor ou estação de trabalho de gerenciamento.

  - Uma implantação mista do Lync Server 2013 e do Skype for Business Server 2015 com as funções de servidor a seguir em pelo menos um site que executa o Skype for Business Server 2015:
    
      - Pelo menos um servidor Pool Enterprise ou Standard Edition. 
    
      - O Pool de Diretores associado à federação SIP, se ela existir.
    
      - O Pool de Borda associado à federação SIP.

  - Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015 com as funções seguintes servidores em pelo menos um site que executa o Skype for Business Server 2015:
    
      - Pelo menos um servidor Pool Enterprise ou Standard Edition. 
    
      - O Pool de Diretores associado à federação SIP, se ela existir.
    
      - O Pool de Borda associado à federação SIP do site.

  - Uma implantação mista do Lync Server 2010 e Lync Server 2013 com as funções de servidor a seguir em pelo menos um site executando o Lync Server 2013:
    
      - Pelo menos um servidor Pool Enterprise ou Standard Edition no site.
    
      - O Pool de Diretores associado à federação SIP, se ela existir no site.
    
      - O Pool de Borda associado à federação SIP do site.

<div>


> [!IMPORTANT]  
> Todo o gerenciamento de usuários, incluindo as movimentações de usuários entre o skypeforbusiness (local e o UNRESOLVED_TOKEN_VAL) online, precisa ser feito usando a versão mais recente instalada das ferramentas administrativas. As ferramentas administrativas devem ser instaladas em um servidor separado que conecta o acesso à implantação local existente e à Internet. O cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-CsUser</A> para mover os usuários da sua implantação local para o UNRESOLVED_TOKEN_VAL (skype16_online) deve ser executado nas ferramentas administrativas conectadas à sua implantação local.



</div>

Para obter mais informações sobre as topologias com suporte, consulte [topologias compatíveis no Lync server 2013](lync-server-2013-supported-topologies.md)e as [topologias de referência do Lync Server 2013 para implantações híbridas da empresa](http://go.microsoft.com/fwlink/p/?linkid=398709).

Para obter informações de solução de problemas de implantações híbridas e conexão do PowerShell com o Lync Online, consulte [Lync Online: Lync PowerShell e solução de problemas híbrida](http://go.microsoft.com/fwlink/p/?linkid=306718).

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a>Requisitos para listas de agrupamento permitidas/bloqueados

A lista Domínios permitidos contém domínios com um FQDN (nome de domínio totalmente qualificado) de Borda parceiro configurado. Por vezes, eles são chamados de *servidores parceiros permitidos* ou *parceiros de federação diretos*. Você deve estar familiarizado com a diferença entre a federação aberta e a federação fechada, conhecidas respectivamente como *descoberta de parceiros* e *lista de domínios dos parceiros permitidos* nas implantações locais.

Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:

  - O domínio correspondente deve ser o mesmo configurado para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para seu locatário online. Caso contrário, a federação fechada deverá ser configurada para seu locatário online.

  - A lista de domínios bloqueados da implantação local deve corresponder exatamente à do seu locatário online.

  - A lista de domínios permitidos da implantação local deve corresponder exatamente à do seu locatário online.

  - A Federação deve estar habilitada para comunicações externas do locatário online, que é configurado usando o painel de controle do Lync Online.

</div>

<div>

## <a name="dns-settings"></a>Configurações de DNS

Ao criar registros DNS para implantações híbridas, todos os registros DNS externos do Lync devem apontar para a infraestrutura local. Para obter detalhes sobre os registros de DNS necessários, consulte [requisitos do sistema de nomes de domínio (DNS) para o Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).

Além disso será necessário garantir que a resolução DNS descrita na tabela a seguir funciona em sua implantação local:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Registro DNS</p></td>
<td><p>Pode ser resolvido por</p></td>
<td><p>Requisitos de DNS</p></td>
</tr>
<tr class="even">
<td><p>Registro SRV DNS para sipfederationtls. _ TCP. &lt;sipdomain.com&gt; para todos os domínios SIP suportados para acessar IP externo da borda</p></td>
<td><p>Servidor(es) de borda</p></td>
<td><p>Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP que está dividido entre as instalações local e online.</p></td>
</tr>
<tr class="odd">
<td><p>Registro(s) A de DNS para FQDN do serviço de webconferência de borda, como webcon.contoso.com, que resolve IP(s) de borda de webconferência</p></td>
<td><p>Computadores de usuários conectados à rede corporativa interna</p></td>
<td><p>Habilitar usuários online para apresentar ou visualizar conteúdo em reuniões hospedadas localmente. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e observações compartilhadas. </p></td>
</tr>
</tbody>
</table>


Dependendo de como o DNS está configurado na sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para proporcionar resolução de DNS interna para esses registros.

</div>

<div>

## <a name="firewall-considerations"></a>Considerações sobre o firewall

Os computadores de sua rede devem ser capazes de realizar pesquisas DNS padrão na Internet. Se esses computadores puderem acessar os sites padrão da Internet, sua rede atenderá a esse requisito.

Dependendo da localização do seu data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de. Outlook.com). Se os firewalls de sua organização não oferecem suporte às configurações de nome com coringa, você deve determinar manualmente o intervalo de endereço IP que deseja permitir e as portas especificadas.

Consulte o tópico da ajuda sobre [URLs e intervalos de endereços IP do 365 do Office](http://go.microsoft.com/fwlink/p/?linkid=252942).

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a>Requisitos de protocolo e porta

Além dos requisitos de porta para comunicação interna do Lync Server 2013, você também deve configurar as portas a seguir.


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
<li><p>Serviços de Federação do Active Directory (função de servidor de Federação)</p>
<p>Para obter mais informações, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">noções básicas sobre os serviços de função do AD FS</a>.</p></li>
<li><p>Serviços de Federação do Active Directory (função de servidor proxy)</p></li>
<li><p>Portal do Microsoft Online Services</p></li>
<li><p>Portal da minha empresa</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Cliente do Lync (comunicação do Lync Server local com o Lync Online)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 e 443</p></td>
<td><p>Abrir entrada</p>
<ul>
<li><p>Ferramenta de sincronização de diretório do Microsoft Online Services</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Entrada/saída aberta no servidor de borda</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Entrada/saída aberta para sessões de compartilhamento de dados</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Entrada/saída aberta para o áudio, vídeo, sessões de compartilhamento de aplicativos</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Entrada/saída aberta para sessões de áudio e vídeo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Abrir saída para sessões de áudio e vídeo</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a>Contas de usuário e dados

Em uma implantação híbrida do Lync Server 2013, todos os usuários que você deseja Home no Lync Online devem ser criados primeiro na implantação local, para que a conta de usuário seja criada nos serviços de domínio Active Directory. Em seguida, você pode mover o usuário para o Skype for Business Online, o que vai mover a lista de contatos do usuário.

Ao sincronizar contas de usuário entre suas implantações locais do Lync e do Lync Online com o AD FS e o DirSync, você precisa sincronizar as contas do anúncio para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo se os usuários Não são movidos para o Lync Online. Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online na sua organização poderá não funcionar conforme o esperado.

<div>


> [!IMPORTANT]  
> Se o usuário for criado usando o portal online do Office 365, a conta de usuário não será sincronizada com o Active Directory local e o usuário não existirá no Active Directory local. Se você já tiver criado usuários no Lync Online e quiser configurar o híbrido com um Lync Server local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync local no Lync Server 2013</A>.



</div>

Você também deve considerar os seguintes problemas relacionados ao usuário ao se planejar para uma implantação híbrida.

  - **Contatos do usuário**   o limite de contatos para usuários do Lync Online é 250. Todos os contatos além desse número serão removidos da lista de contatos do usuário quando a conta for movida para o Lync Online.

  - ****   As listas de contatos de mensagens instantâneas e de presença, grupos e listas de controle de acesso (ACLs) são migrados com a conta de usuário.

  - **Dados de conferência, conteúdo da reunião e reuniões**   agendadas esse conteúdo não é migrado com a conta de usuário. Os usuários devem reagendar as reuniões depois que as contas são migradas para o Lync Online.

</div>

<div>

## <a name="user-policies-and-features"></a>Políticas e recursos do usuário

  - Em um ambiente híbrido do Lync Server 2013, os usuários podem ser habilitados para mensagens instantâneas, voz e reuniões locais ou online, mas não ambos simultaneamente.

  - **Cliente do Lync**     alguns usuários podem precisar de uma nova versão do cliente quando forem movidos para o Lync Online. Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um pool do Lync Server 2013 antes da migração para o Lync Online.
    
    Para obter mais informações sobre o suporte ao cliente, consulte [clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) e [clientes Lync compatíveis e configurações de porta de rede](http://go.microsoft.com/fwlink/p/?linkid=281901).

  - **Políticas locais e configurações (não pertencentes ao usuário)**   online e políticas locais exigem configuração separada. Você não pode definir políticas globais que se apliquem a ambas.

</div>

</div>

<span> </span>

</div>

</div>

</div>

