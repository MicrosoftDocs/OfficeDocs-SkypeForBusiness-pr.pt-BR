---
title: 'Lync Server 2013: habilitar usuários do Lync para controle de chamada remota'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a400b5a071a3540f65c38d606724df10883931e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Habilitar usuários do Lync para controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-21_

Você pode configurar os usuários do Lync para controle de chamada remota usando as políticas de provisionamento em banda que são baseadas em servidor. Você pode gerenciar as configurações de provisionamento em banda usando o painel de controle do Lync Server ou a interface de linha de comando do Shell de gerenciamento do Lync Server. Essas ferramentas substituem o snap-in WMI (Instrumentação de gerenciamento do Windows) usado para gerenciar as configurações de política de grupo em versões anteriores.

Se preferir permitir que os usuários definam suas próprias configurações de controle de chamada remota no Lync, você pode definir as configurações de controle de chamada remota para usuários no servidor sem especificar o **URI do servidor de linha** e os valores de **URI da linha** . Certifique-se de comunicar o **URI do servidor de linha** apropriado e os valores de URI da **linha** para seus usuários e forneça as instruções para definir essas configurações. Para o procedimento para configurar manualmente o controle de chamada remota no Lync Server, consulte "configurar opções e números de <https://go.microsoft.com/fwlink/p/?linkid=210132> telefones" na documentação do cliente do Lync no site do Microsoft Office.

Se você tiver uma implantação existente do Communications Server 2007 R2 ou Communications Server 2007, os clientes do Communicator 2007 R2 e do Communicator 2007 continuarão a usar a política de grupo durante a migração lado a lado. No entanto, se você quiser que as configurações de política sejam transportadas para os clientes Lync, será necessário configurar as definições equivalentes de provisionamento em banda do Lync Server.

<div>


> [!NOTE]  
> Para habilitar um usuário para controle de chamada remota, você precisa fornecer ao usuário um URI de linha e um URI de servidor de linha. Conforme descrito nas <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tarefas de implantação do controle de chamada remota no Lync Server 2013</A>, você precisará se certificar de usar a sintaxe exigida pelo gateway para essas configurações.<BR>Certifique-se de que o domínio no URI do servidor de linha é o mesmo que o domínio de destino especificado no parâmetro MatchUri quando você configurou a rota estática para o gateway.<BR>O URI da linha especifica o número de telefone atribuído ao usuário no formato E. 164, com o prefixo "TEL:" (por exemplo, Tel: + 14255550150). Se você deseja configurar um número de extensão, o formato é tel:+14255550150;ext=111. Se você configurou anteriormente o URI de linha do usuário e o valor não foi alterado, não é necessário especificar o URI de linha ao habilitar o usuário para controle de chamada remota.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Para habilitar o controle de chamada remota para usuários habilitados em Lync utilizando o Shell de Gerenciamento

1.  Faça logon em um computador onde o Shell de gerenciamento do Lync Server está instalado como um membro do grupo RTCUniversalServerAdmins ou como uma função de controle de acesso baseado em função à qual você atribuiu o cmdlet **set-CsUser** .

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Para usar o cmdlet **Set-CsUser** para configurar o controle de chamada remota para um usuário habilitado em Lync existente, faça o seguinte:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Por exemplo:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Para configurar os usuários para o controle de chamada remota usando o Painel de Controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite todos (ou a primeira parte) do nome de exibição, nome, sobrenome, nome da conta Sam, endereço SIP ou URI de linha da conta de usuário que você deseja e clique em localizar (em inglês), e em **Localizar**.

5.  Na tabela, clique na conta de usuário que deseja modificar.

6.  No menu **Editar**, clique em **Modificar**.

7.  Em **Telefonia**, faça um dos seguintes:
    
      - Para habilitar o controle de chamada remota para permitir que o usuário controle seu telefone de PBX (Private Branch Exchange) do Lync 2013 para fazer chamadas de áudio de PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI de linha**, especifique o número de telefone do usuário. Em **URI do servidor de linha**, especifique o URI SIP do gateway SIP/CSTA.
    
      - Para habilitar o controle de chamada remota, mas desabilitar as chamadas de áudio do PC para PC e permitir que apenas o usuário controle seu telefone PBX do Lync 2013 para fazer chamadas de PC para telefone, clique em **controle de chamada remota somente**. Em **URI de linha**, especifique o número de telefone do usuário. Em **URI do servidor de linha**, especifique o URI SIP do gateway SIP/CSTA.

8.  Ao concluir, clique em **Confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

