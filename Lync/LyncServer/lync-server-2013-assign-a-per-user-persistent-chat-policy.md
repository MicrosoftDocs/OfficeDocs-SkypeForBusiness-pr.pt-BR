---
title: 'Lync Server 2013: atribuir uma política de chat persistente por usuário'
description: 'Lync Server 2013: atribua uma política de chat persistente por usuário.'
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
ms.openlocfilehash: 637f1947fff7f4e919e5f9c252c047b2d0e60392
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563597"
---
# <a name="assign-a-per-user-persistent-chat-policy-in-lync-server-2013"></a>Atribuir uma política de chat persistente por usuário no Lync Server 2013

 


Você pode atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server 2013 ou o Shell de gerenciamento do Lync Server 2013. Para obter detalhes sobre como criar políticas de usuário para o servidor de chat persistente, consulte [criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md).

## <a name="to-assign-a-per-user-persistent-chat-policy-with-lync-server-control-panel"></a>Para atribuir uma política de chat persistente por usuário com o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Usuários**.

4.  Utilize um dos métodos a seguir para localizar um usuário:
    
      - Na caixa **Buscar usuários**, digite toda ou a primeira parte do nome de exibição, nome, sobrenome, nome da conta do Gerenciador de Contas de Segurança (SAM), endereço SIP ou linha do Uniform Resource Identifier (URI) da conta de usuário, e então clique em **Localizar**.
    
      - Se você tiver uma consulta salva, clique no ícone **Abrir consulta**, utilize a caixa de diálogo **Abrir**  para obter a consulta (um arquivo .usf) e, então, clique em **Localizar**.

5.  (Opcional) Especifique critérios de busca adicionais para limitar os resultados:
    
    1.  Clique em **Adicionar filtro**.
    
    2.  Insira a propriedade de usuário digitando ou clicando na seta na lista suspensa para selecionar a propriedade.
    
    3.  Na lista suspensa **Igual a**, clique no operador (por exemplo, **Igual a** ou **Diferente de**).
    
    4.  Dependendo da propriedade do usuário selecionada, insira os critérios que você deseja usar para filtrar os resultados pesquisa, digitando-os ou clicando na seta na lista suspensa.
        

        > [!TIP]  
        > Para adicionar cláusulas de pesquisa à sua consulta, clique em <STRONG>Adicionar filtro</STRONG>.

    
    5.  Clique em **Localizar**.

6.  Clique em um usuário nos resultados da pesquisa, clique em **Ação** e em **Atribuir políticas**.
    

    > [!TIP]  
    > Se você deseja que a mesma política de chat persistente por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de chat persistente**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias políticas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt; manter como está &gt; </STRONG> selecionada por padrão para todas as políticas da caixa de diálogo. Para continuar usando a política previamente atribuída ao usuário, basta não fazer nenhuma alteração nessa configuração.

    
      - Selecione esta opção **\<Automatic\>** para permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de chat persistente por usuário definida anteriormente na página **política de chat persistente** .
        

        > [!TIP]  
        > Para ajudar a decidir a política que deseja atribuir, após clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos e permissões do usuário definidos na política.



8.  Quando terminar, clique em **OK**.

## <a name="assigning-a-per-user-persistent-chat-policy-by-using-windows-powershell-cmdlets"></a>Atribuindo uma política de chat persistente Per-User usando cmdlets do Windows PowerShell

Você também pode atribuir políticas de chat persistente por usuário usando o cmdlet **Grant-CsPersistentChatPolicy** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

## <a name="to-assign-a-per-user-persistent-chat-policy-to-a-single-user"></a>Para atribuir uma política de chat persistente por usuário a um único usuário

  - O comando a seguir atribui a política de chat persistente por usuário RedmondPersistentChatPolicy ao usuário Ken Myer.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName "RedmondPersistentChatPolicy"

## <a name="to-assign-a-per-user-persistent-chat-policy-to-multiple-users"></a>Para atribuir uma política de chat persistente por usuário a vários usuários

  - Este comando atribui a política de chat persistente por usuário RedmondUsersPersistentChatPolicy a todos os usuários que trabalham no departamento de ti. Para obter mais informações sobre o parâmetro LdapFilter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -LdapFilter "Department=IT" | Grant-CsPersistentChatPolicy -PolicyName "RedmondUsersPersistentChatPolicy"

## <a name="to-unassign-a-per-user-persistent-chat-policy"></a>Para cancelar a atribuição de uma política de chat persistente por usuário

  - O comando a seguir retira a atribuição de qualquer política de chat persistente por usuário atribuída anteriormente a Ken Myer. Depois que a atribuição da política for desfeita, Ken Myer será automaticamente gerenciado usando a política global ou, se houver, sua política de site local. Uma política de site tem preferência sobre a política global.
    
        Grant-CsPersistentChatPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsPersistentChatPolicy](https://technet.microsoft.com/library/jj204907\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criar uma política de usuário para chat persistente no Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

