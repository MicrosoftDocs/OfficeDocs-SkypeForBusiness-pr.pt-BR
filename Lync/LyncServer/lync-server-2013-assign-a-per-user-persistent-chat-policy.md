---
title: 'Lync Server 2013: atribuir uma política de chat persistente por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user Persistent Chat policy
ms:assetid: e22168f2-fde1-4f0a-b194-1fc881436822
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721908(v=OCS.15)
ms:contentKeyID: 49733842
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 616a171d4aedcc6014ddea3c5993a097d410a5e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722821"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Atribuir uma política de chat persistente por usuário no Lync Server 2013

 


Você pode atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. Para obter detalhes sobre como criar políticas de usuário para o servidor de chat persistente, consulte [criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Para atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Usuários**.

4.  Use um dos seguintes métodos para localizar um usuário:
    
      - Na caixa **Pesquisar usuários**, digite todo ou parte do nome de exibição, nome, sobrenome, nome da conta SAM, endereço SIP ou URI de linha da conta do usuário e clique em **Localizar**.
    
      - Se você salvou uma consulta, clique no ícone **Abrir consulta**, use a caixa de diálogo **Abrir** para recuperar a consulta (um arquivo .usf) e clique em **Localizar**.

5.  (Opcional) Especifique o critério de pesquisa adicional para reduzir os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade do usuário digitando ou clicando na seta da lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade do usuário selecionada, insira o critério que deseja usar para filtrar os resultados de pesquisa digitando ou clicando na seta da lista suspensa.
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa adicionais à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

    
    5.  Clique em **Localizar**.

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em seguida, clique em **Atribuir políticas**.
    

    > [!TIP]  
    > Se quiser que a mesma política de chat persistente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de chat persistente**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Selecione ** \<automático\> ** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de chat persistente por usuário definida anteriormente na página **política de chat persistente** .
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para visualizar os direitos e permissões do usuário definidos na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de chat persistente por usuário usando cmdlets do Windows PowerShell

Você também pode atribuir políticas de bate-papo persistentes por usuário usando o cmdlet **Grant-CsPersistentChatPolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>Para atribuir uma política de chat persistente por usuário a um único usuário

  - O comando a seguir atribui a política de chat persistente por usuário RedmondPersistentChatPolicy ao usuário Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>Para atribuir uma política de chat persistente por usuário a vários usuários

  - Esse comando atribui a política de chat persistente por usuário RedmondUsersPersistentChatPolicy a todos os usuários que trabalham para o departamento de ti. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>Para cancelar a atribuição de uma política de chat persistente por usuário

  - O comando a seguir não atribui atribuições de qualquer política de chat persistente por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/jj204907\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criar uma política de usuário para Chat Persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

