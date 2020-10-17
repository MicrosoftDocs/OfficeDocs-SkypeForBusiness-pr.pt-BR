---
title: 'Lync Server 2013: aplicando uma política de arquivamento aos usuários'
description: 'Lync Server 2013: aplicando uma política de arquivamento aos usuários.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying an Archiving policy to users
ms:assetid: 624a7d3e-389d-403a-97e5-f7bb17023ef3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521004(v=OCS.15)
ms:contentKeyID: 48184290
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54b82a68a75da7b389167097d8b08358cf680e1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544967"
---
# <a name="applying-an-archiving-policy-to-users-in-lync-server-2013"></a>Aplicando uma política de arquivamento aos usuários no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Se um usuário tiver sido habilitado para o Lync Server 2013 e você tiver criado uma ou mais políticas de usuário para arquivamento para usuários hospedados no Lync Server 2013, poderá implementar o suporte de arquivamento para usuários específicos aplicando as políticas apropriadas aos usuários ou grupos de usuários. Por exemplo, se você criar uma política para oferecer suporte ao arquivamento de comunicações internas, você pode aplicá-la a pelo menos um usuário ou grupo de usuários para dar suporte ao arquivamento das comunicações do Lync Server 2013 do usuário.

<div>


> [!NOTE]  
> Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlam se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e que suas caixas de correio sejam colocadas In-Place isenção. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.<BR>Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento. Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools</A> na documentação de operações.



</div>

Use o procedimento descrito neste tópico para aplicar uma política de usuário de arquivamento criada anteriormente a uma ou mais contas de usuário ou a grupos de usuários.

<div>

## <a name="to-apply-an-archiving-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário de arquivamento a uma conta de usuário

1.  A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar usuário do Lync Server** em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    <div>
    

    > [!NOTE]  
    > As configurações <STRONG> &lt; automáticas &gt; </STRONG> aplicam as configurações de instalação padrão do servidor. Essas configurações são aplicadas automaticamente pelo servidor.

    
    </div>

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de arquivamento de Per-User usando cmdlets do Windows PowerShell

As políticas de arquivamento por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para atribuir uma política de arquivamento por usuário a um único usuário

  - O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para atribuir uma política de arquivamento por usuário a vários usuários

  - Este comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que possuem contas hospedadas no pool de registradores atl-cs-001.litwareinc.com. Para obter detalhes sobre o parâmetro Filter usado nesse comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

</div>

<div>

## <a name="to-assign-a-per-user-archiving-policy"></a>Para atribuir uma política de arquivamento por usuário

  - O comando a seguir cancela a atribuição de todas as políticas de arquivamento por usuário atribuídas anteriormente a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado pela política global ou pela política de seu site local (se houver uma). Uma política de site prevalece sobre a política global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

</div>

Para obter detalhes, consulte a documentação do cmdlet [Grant-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
[Atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

