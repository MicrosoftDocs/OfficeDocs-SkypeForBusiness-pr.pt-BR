---
title: 'Lync Server 2013: atribuir uma política de arquivamento por usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Assign a per-user archiving policy
ms:assetid: a12ca483-b235-460f-b3fe-130fb3087264
ms:mtpsurl: https://technet.microsoft.com/library/Gg182560(v=OCS.15)
ms:contentKeyID: 48185014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36d23e44e397a77f0d490d8fda27ee711d1c61c5
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111575"
---
# <a name="assign-a-per-user-archiving-policy-in-lync-server-2013"></a>Atribuir uma política de arquivamento por usuário no Lync Server 2013

 


A política de arquivamento é uma das configurações individuais de uma conta de usuário que você pode configurar no painel de controle do Lync Server 2013.

A implantação de uma ou mais políticas de arquivamento por usuário é opcional. Você também pode implantar apenas uma política de arquivamento de nível global ou política de arquivamento em nível de site. Se você implantar políticas por usuário, deverá atribui-las explicitamente aos usuários, grupos ou objeto de contato. Os requisitos de arquivamento são automaticamente padrão para aqueles definidos na política de conferência de nível global, quando nenhuma política específica de nível de site ou por usuário é atribuída.

Depois de criar pelo menos uma política de arquivamento por usuário, use os procedimentos neste tópico para atribuir a política que especifica apropriadamente se as comunicações internas de um determinado usuário, as comunicações externas ou ambas, serão arquivadas pelo servidor.

Para obter detalhes sobre como criar políticas de arquivamento por usuário, consulte [criando uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md).

## <a name="to-assign-a-per-user-archiving-policy"></a>Para atribuir uma política de arquivamento por usuário

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
    > Se você quiser que a mesma política de arquivamento por usuário seja aplicada a vários usuários, selecione vários usuários nos resultados da pesquisa, clique em <STRONG>ações</STRONG>e, em seguida, clique em <STRONG>atribuir políticas</STRONG>.



7.  Em **atribuir políticas**, em **política de arquivamento**, siga um destes procedimentos:
    

    > [!NOTE]  
    > Como há várias diretivas que você pode configurar usando a caixa de diálogo <STRONG>atribuir políticas</STRONG> , <STRONG> &lt;manter como está&gt; </STRONG> selecionado por padrão para cada política na caixa de diálogo. Continue usando a política atribuída anteriormente ao usuário não realizando alterações nesta configuração.

    
      - Permitir que o Lync Server 2013 escolha automaticamente a política de nível global ou, se definida, a política de nível de site.
    
      - Clique no nome de uma política de arquivamento por usuário definida anteriormente na página **política de arquivamento** .
        

        > [!TIP]  
        > Para ajudá-lo a decidir a política que você deseja atribuir, depois de clicar no nome da política, clique em <STRONG>Exibir</STRONG> para ver os direitos do usuário e as permissões definidas na política.



8.  Ao concluir, clique em **OK**.

## <a name="assigning-a-per-user-archiving-policy-by-using-windows-powershell-cmdlets"></a>Atribuir uma política de arquivamento por usuário usando cmdlets do Windows PowerShell

Você pode atribuir políticas de arquivamento por usuário usando o Windows PowerShell e o cmdlet **Grant-CsArchivingPolicy** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

## <a name="to-assign-a-per-user-archiving-policy-to-a-single-user"></a>Para atribuir uma política de arquivamento por usuário a um único usuário

  - O comando a seguir atribui a política de arquivamento por usuário RedmondArchivingPolicy ao usuário Ken Myer.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"

## <a name="to-assign-a-per-user-archiving-policy-to-multiple-users"></a>Para atribuir uma política de arquivamento por usuário a vários usuários

  - Esse comando atribui a política de arquivamento por usuário RedmondArchivingPolicy a todos os usuários que têm contas hospedadas no pool de registradores atl-cs-001.litwareinc.com. Para obter mais informações sobre o parâmetro Filter usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"

## <a name="to-unassign-a-per-user-archiving-policy"></a>Para cancelar a atribuição de uma política de arquivamento por usuário

  - O comando a seguir cancela a atribuição de qualquer política de arquivamento por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsArchivingPolicy](https://technet.microsoft.com/library/gg398475\(v=ocs.15\)) .

## <a name="see-also"></a>Confira também


[Criar uma política de arquivamento no Lync Server 2013 para habilitar ou desabilitar o arquivamento de comunicações internas ou externas para sites ou usuários específicos](lync-server-2013-create-archiving-policy-sites-users.md)  


[Como atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md)

