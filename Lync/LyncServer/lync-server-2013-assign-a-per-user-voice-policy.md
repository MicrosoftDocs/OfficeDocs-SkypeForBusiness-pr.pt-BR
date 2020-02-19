---
title: 'Lync Server 2013: atribuir uma política de voz por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6a10e2fb6d8e17352eb8a96be57b24e706fc5d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134387"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Atribuir uma política de voz por usuário no Lync Server 2013

 


As políticas de voz globais e no nível do site são atribuídas automaticamente a todas as contas de usuário do Lync Server 2013 habilitadas para o Enterprise Voice. Você também pode atribuir políticas de voz a usuários específicos usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. Use os procedimentos neste tópico para atribuir explicitamente políticas por usuário aos usuários do Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Para atribuir uma política de voz específica do usuário usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar Usuário do Lync Server**, em **Política de voz**, selecione a política de usuário que você deseja aplicar.
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de política global ou de servidor padrão.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de voz por usuário usando cmdlets do Windows PowerShell

Você pode atribuir políticas de voz por usuário usando o Windows PowerShell e o cmdlet **Grant-CsVoicePolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Para atribuir uma política de voz por usuário a um único usuário

  - O comando a seguir atribui a política de voz por usuário RedmondVoicePolicy ao usuário Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Para atribuir uma política de voz por usuário a vários usuários

  - Esse comando atribui a política de voz por usuário FinanceVoicePolicy a todos os usuários que tenham contas no OU de finanças no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Para cancelar a atribuição de uma política de voz por usuário

  - O comando a seguir desatribui a política de voz por usuário anteriormente atribuída a Ken Myer. Depois que a política de voz por usuário é desatribuida, Ken Myer será automaticamente gerenciado usando uma política global ou, se existir, a política do seu site local. A política de site tem precedência sobre a política global.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Desabilitar um usuário para o Enterprise Voice no Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Shell de gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md)

