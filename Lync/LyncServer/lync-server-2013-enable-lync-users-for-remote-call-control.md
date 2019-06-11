---
title: 'Lync Server 2013: Habilitar usuários do Lync para controle de chamada remotas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6eae16d6dae46bab4f6cf745bc2e2a827eabcb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Habilitar usuários do Lync para controle de chamada remota no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-21_

Você pode configurar os usuários do Lync para controle de chamada remota usando políticas de provisionamento em banda com base em servidor. Você pode gerenciar as configurações de provisionamento em banda usando o painel de controle do Lync Server ou a interface de linha de comando do Shell de gerenciamento do Lync Server. Essas ferramentas substituem o snap-in de instrumentação de gerenciamento do Windows (WMI) que foi usado para gerenciar as configurações de política de grupo nas versões anteriores.

Se preferir permitir que os usuários configurem suas próprias configurações de controle de chamada remota no Lync, você pode definir as configurações de controle de chamada remota para os usuários no servidor sem especificar o **URI do servidor de linhas** e os valores de **URI da linha** . Certifique-se de que você comunique os valores apropriados de **URI** e de URI do **servidor de linha** para seus usuários e forneça aos usuários as instruções para definir essas configurações. Para obter o procedimento para configurar manualmente o controle de chamada remota no Lync Server, consulte "definir opções e números <http://go.microsoft.com/fwlink/p/?linkid=210132> de telefones" na documentação do cliente do Lync no site do Microsoft Office.

Se você tiver uma implantação existente do Communications Server 2007 R2 ou Communications Server 2007 implantação, os clientes do Communicator 2007 R2 e do Communicator 2007 continuarão a usar a política de grupo durante a migração lado a lado. No entanto, se desejar que as configurações de política sejam transferidas para clientes do Lync, você precisará configurar as configurações equivalentes de provisionamento em banda do Lync Server.

<div>


> [!NOTE]  
> Para habilitar um usuário para controle de chamada remota, você precisa fornecer ao usuário um URI de linha e um URI de servidor de linha. Conforme descrito nas <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">tarefas de implantação do controle de chamada remota no Lync Server 2013</A>, você precisa se certificar de usar a sintaxe exigida pelo gateway para essas configurações.<BR>Certifique-se de que o domínio no URI do servidor de linha seja o mesmo que o domínio de destino que você especificou no parâmetro MatchUri quando configurou a rota estática para o gateway.<BR>O URI da linha especifica o número de telefone atribuído ao usuário no formato E. 164, com o prefixo "TEL:" (por exemplo, Tel: + 14255550150). Se você quiser configurar um número de ramal, o formato será Tel: + 14255550150; ext = 111. Se você configurou anteriormente o URI da linha do usuário e o valor não foi alterado, você não precisa especificar o URI da linha quando habilitar o usuário para o controle de chamada remota.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Para habilitar o controle de chamada remota para usuários habilitados para Lync usando o Shell de gerenciamento

1.  Faça logon em um computador em que o Shell de gerenciamento do Lync Server está instalado como membro do grupo RTCUniversalServerAdmins ou como uma função de controle de acesso baseado em função à qual você atribuiu o cmdlet **set-CsUser** .

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Para usar o cmdlet **set-CsUser** para configurar o controle de chamada remota para um usuário existente compatível com o Lync, faça o seguinte:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Por exemplo:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Para configurar usuários para o controle de chamada remota usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Na caixa **Pesquisar usuários** , digite todos (ou a primeira parte) do nome para exibição, nome, sobrenome, nome da conta do Gerenciador de contas de segurança (Sam), endereço SIP ou URI (Uniform Resource Identifier) da conta de usuário que você deseja e, em seguida, clique em ** Localizar**.

5.  Na tabela, clique na conta de usuário que você deseja modificar.

6.  No menu **Editar** , clique em **Modificar**.

7.  Em **telefonia**, siga um destes procedimentos:
    
      - Para habilitar o controle de chamada remota para permitir que o usuário controle o telefone do seu PBX (Private Branch Exchange) do Lync 2013 para fazer chamadas de áudio PC para PC e chamadas de PC para telefone, clique em **controle de chamada remota**. Em **URI de linha**, especifique o número de telefone do usuário. Em **URI do servidor de linha**, ESPECIFIQUE o URI SIP do gateway de SIP/CSTA.
    
      - Para habilitar o controle de chamada remota, mas desabilitar as chamadas de áudio do PC para PC e permitir que somente o usuário controle o telefone PBX do Lync 2013 para fazer chamadas de PC para telefone, clique em **controle de chamada remota somente**. Em **URI de linha**, especifique o número de telefone do usuário. Em **URI do servidor de linha**, ESPECIFIQUE o URI SIP do gateway de SIP/CSTA.

8.  Quando terminar, clique em **confirmar**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

