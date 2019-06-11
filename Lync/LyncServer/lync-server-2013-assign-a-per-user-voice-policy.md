---
title: 'Lync Server 2013: atribuir uma política de voz por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e74bebc202a9e8d9fbc7b925c14bbe030e4c577
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844991"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Atribuir uma política de voz por usuário no Lync Server 2013

 


Políticas de voz globais e em nível de site são automaticamente atribuídas a todas as contas de usuário do Lync Server 2013 habilitadas para o Enterprise Voice. Você também pode atribuir políticas de voz a usuários específicos usando o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. Use os procedimentos deste tópico para atribuir explicitamente políticas por usuário a usuários do Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Para atribuir uma política de voz específica do usuário usando o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar usuário do Lync Server** em **política de voz**, selecione a política de usuário que você deseja aplicar.
    

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de política global e do servidor padrão.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de voz por usuário usando cmdlets do Windows PowerShell

Você pode atribuir políticas de voz por usuário usando o Windows PowerShell e o cmdlet **Grant-CsVoicePolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Para atribuir uma política de voz por usuário a um único usuário

  - O comando a seguir atribui a RedmondVoicePolicy de política de voz por usuário ao usuário Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Para atribuir uma política de voz por usuário a vários usuários

  - Esse comando atribui a política de voz por usuário FinanceVoicePolicy a todos os usuários que têm contas na unidade organizacional Finance no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Para cancelar a atribuição de uma política de voz por usuário

  - O comando a seguir não atribui a atribuição de nenhuma política de voz por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsVoicePolicy](https://technet.microsoft.com/en-us/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Desabilitar um usuário para o Enterprise Voice no Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Shell de Gerenciamento do Lync Server 2013](lync-server-2013-lync-server-management-shell.md)

